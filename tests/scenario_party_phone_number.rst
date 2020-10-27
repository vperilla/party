===========================
Party Phone Number Scenario
===========================

Imports::

    >>> from proteus import Model, Wizard
    >>> from trytond.tests.tools import activate_modules

Install party::

    >>> config = activate_modules('party')

Create a country::

    >>> Country = Model.get('country.country')
    >>> spain = Country(name='Spain', code='ES')
    >>> spain.save()

Create a party related to the country::

    >>> Party = Model.get('party.party')
    >>> party = Party(name='Pam')
    >>> address, = party.addresses
    >>> address.country = spain
