# Microsoft.Crm.Caching.MailboxCacheData::get_CachedMailboxAttributes

- ea: `0x85410`
- end: `0x855ef`
- name: `Microsoft.Crm.Caching.MailboxCacheData::get_CachedMailboxAttributes`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x85437`: `enabledforincomingemail`
- `0x85442`: `incomingemaildeliverymethod`
- `0x85458`: `incomingemailstatus`
- `0x8549a`: `processanddeleteemails`
- `0x854c6`: `emailrouteraccessapproval`
- `0x8556b`: `lastsuccessfulsynccompletedon`
- `0x855ad`: `isserviceaccount`
- `0x855c3`: `isexchangecontactsimportscheduled`
- `0x855d9`: `exchangecontactsimportcompletedon`

## pseudocode

```c

```

## disassembly

```asm
0x85410  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x85415  dup
0x85416  ldstr    aName_0// "name"
0x8541b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85420  dup
0x85421  ldstr    aEmailaddress// "emailaddress"
0x85426  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8542b  dup
0x8542c  ldstr    aEmailserverpro_0// "emailserverprofile"
0x85431  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85436  dup
0x85437  ldstr    aEnabledforinco// "enabledforincomingemail"
0x8543c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85441  dup
0x85442  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x85447  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8544c  dup
0x8544d  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x85452  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85457  dup
0x85458  ldstr    aIncomingemails// "incomingemailstatus"
0x8545d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85462  dup
0x85463  ldstr    aActdeliverymet// "actdeliverymethod"
0x85468  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8546d  dup
0x8546e  ldstr    aActstatus// "actstatus"
0x85473  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85478  dup
0x85479  ldstr    aIsforwardmailb// "isforwardmailbox"
0x8547e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85483  dup
0x85484  ldstr    aUsername// "username"
0x85489  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8548e  dup
0x8548f  ldstr    aPassword// "password"
0x85494  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85499  dup
0x8549a  ldstr    aProcessanddele// "processanddeleteemails"
0x8549f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854a4  dup
0x854a5  ldstr    aRegardingobjec// "regardingobjectid"
0x854aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854af  dup
0x854b0  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0x854b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854ba  dup
0x854bb  ldstr    aStatecode// "statecode"
0x854c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854c5  dup
0x854c6  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x854cb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854d0  dup
0x854d1  ldstr    aAllowemailconn// "allowemailconnectortousecredentials"
0x854d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854db  dup
0x854dc  ldstr    aOwnerid// "ownerid"
0x854e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854e6  dup
0x854e7  ldstr    aOwneridtype// "owneridtype"
0x854ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854f1  dup
0x854f2  ldstr    aUndeliverablef// "undeliverablefolder"
0x854f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854fc  dup
0x854fd  ldstr    aEwsurl// "ewsurl"
0x85502  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85507  dup
0x85508  ldstr    aLastautodiscov// "lastautodiscoveredon"
0x8550d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85512  dup
0x85513  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x85518  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8551d  dup
0x8551e  ldstr    aLastsyncerror// "lastsyncerror"
0x85523  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85528  dup
0x85529  ldstr    aLastsyncerrorc// "lastsyncerrorcount"
0x8552e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85533  dup
0x85534  ldstr    aLastsyncerrorc_0// "lastsyncerrorcode"
0x85539  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8553e  dup
0x8553f  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x85544  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85549  dup
0x8554a  ldstr    aLastsyncerrorm// "lastsyncerrormachinename"
0x8554f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85554  dup
0x85555  ldstr    aItemsprocessed// "itemsprocessedforlastsync"
0x8555a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8555f  dup
0x85560  ldstr    aItemsfailedfor// "itemsfailedforlastsync"
0x85565  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8556a  dup
0x8556b  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x85570  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85575  dup
0x85576  ldstr    aLastsyncstarte// "lastsyncstartedon"
0x8557b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85580  dup
0x85581  ldstr    aCrmitemsbacklo// "crmitemsbacklog"
0x85586  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8558b  dup
0x8558c  ldstr    aIndividualstep// "individualstepdurations"
0x85591  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x85596  dup
0x85597  ldstr    aFolderhierarch// "folderhierarchy"
0x8559c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855a1  dup
0x855a2  ldstr    aVerboselogging// "verboseloggingenabled"
0x855a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855ac  dup
0x855ad  ldstr    aIsserviceaccou// "isserviceaccount"
0x855b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855b7  dup
0x855b8  ldstr    aPostponesendin// "postponesendinguntil"
0x855bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855c2  dup
0x855c3  ldstr    aIsexchangecont// "isexchangecontactsimportscheduled"
0x855c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855cd  dup
0x855ce  ldstr    aExchangecontac// "exchangecontactsimportstatus"
0x855d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855d8  dup
0x855d9  ldstr    aExchangecontac_0// "exchangecontactsimportcompletedon"
0x855de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855e3  dup
0x855e4  ldstr    aDataencryption// "dataencryptionkey"
0x855e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x855ee  ret
```
