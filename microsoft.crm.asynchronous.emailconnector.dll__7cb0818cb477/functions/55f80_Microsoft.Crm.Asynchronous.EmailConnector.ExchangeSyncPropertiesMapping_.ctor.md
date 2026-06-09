# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping::.ctor

- ea: `0x55f80`
- end: `0x56983`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping::.ctor`
- size: `2563`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x56dd0`
- `0x56ec0`

## string_xrefs

- `0x56170`: `company`
- `0x5631d`: `scheduledstart`
- `0x566ae`: `scheduledstart`
- `0x56328`: `scheduledend`
- `0x566b9`: `scheduledend`
- `0x563c2`: `crmserviceid`
- `0x5652d`: `crmserviceid`
- `0x563ee`: `scheduleddurationminutes`
- `0x5654e`: `scheduleddurationminutes`
- `0x566c4`: `scheduleddurationminutes`
- `0x5640f`: `seriesid`
- `0x5662a`: `deletedexceptionslist`
- `0x567ab`: `settaskpercentcomplete`
- `0x567c1`: `settaskstartdate`
- `0x568a8`: `settaskstartdate`
- `0x567cc`: `settaskduedate`
- `0x568b3`: `settaskduedate`
- `0x567d7`: `setcompletedate`
- `0x568be`: `setcompletedate`
- `0x56803`: `settaskstatus`
- `0x568ea`: `settaskstatus`
- `0x5680e`: `taskstartdate`
- `0x568f5`: `taskstartdate`
- `0x56819`: `taskduedate`
- `0x56900`: `taskduedate`
- `0x5682f`: `percentcomplete`
- `0x56845`: `crmtaskassigneduniqueid`

## pseudocode

```c

```

## disassembly

```asm
0x55f80  ldarg.0
0x55f81  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x55f86  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertyMapping>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x55f8b  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertyMapping> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping::_syncPropertiesMapping
0x55f90  ldarg.0
0x55f91  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x55f96  dup
0x55f97  ldstr    aYomifirstname// "yomifirstname"
0x55f9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fa1  dup
0x55fa2  ldstr    aYomilastname// "yomilastname"
0x55fa7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fac  dup
0x55fad  ldstr    aNickname// "nickname"
0x55fb2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fb7  dup
0x55fb8  ldstr    aJobtitle// "jobtitle"
0x55fbd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fc2  dup
0x55fc3  ldstr    aDepartment// "department"
0x55fc8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fcd  dup
0x55fce  ldstr    aManagername// "managername"
0x55fd3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fd8  dup
0x55fd9  ldstr    aAssistantname// "assistantname"
0x55fde  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fe3  dup
0x55fe4  ldstr    aAssistantphone// "assistantphone"
0x55fe9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55fee  dup
0x55fef  ldstr    aSpousesname// "spousesname"
0x55ff4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x55ff9  dup
0x55ffa  ldstr    aChildren// "children"
0x55fff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56004  dup
0x56005  ldstr    aBusinessphone// "businessphone"
0x5600a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5600f  dup
0x56010  ldstr    aHomephone// "homephone"
0x56015  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5601a  dup
0x5601b  ldstr    aOthertelephone// "othertelephone"
0x56020  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56025  dup
0x56026  ldstr    aMobilephone// "mobilephone"
0x5602b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56030  dup
0x56031  ldstr    aPager// "pager"
0x56036  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5603b  dup
0x5603c  ldstr    aBusinesshomepa// "businesshomepage"
0x56041  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56046  dup
0x56047  ldstr    aFtpsiteurl// "ftpsiteurl"
0x5604c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56051  dup
0x56052  ldstr    aWeddinganniver// "weddinganniversary"
0x56057  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5605c  dup
0x5605d  ldstr    aBirthday// "birthday"
0x56062  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56067  dup
0x56068  ldstr    aGovernmentid// "governmentid"
0x5606d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56072  dup
0x56073  ldstr    aBody// "body"
0x56078  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5607d  dup
0x5607e  ldstr    aSetbody// "setbody"
0x56083  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56088  dup
0x56089  ldstr    aSetnames// "setnames"
0x5608e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56093  dup
0x56094  ldstr    aLastname// "lastname"
0x56099  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5609e  dup
0x5609f  ldstr    aMiddlename// "middlename"
0x560a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560a9  dup
0x560aa  ldstr    aFirstname// "firstname"
0x560af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560b4  dup
0x560b5  ldstr    aSuffix// "suffix"
0x560ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560bf  dup
0x560c0  ldstr    aSalutation// "salutation"
0x560c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560ca  dup
0x560cb  ldstr    aSetemailaddres// "setemailaddresses1"
0x560d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560d5  dup
0x560d6  ldstr    aEmailaddress1// "emailaddress1"
0x560db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560e0  dup
0x560e1  ldstr    aSetemailaddres_0// "setemailaddresses2"
0x560e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560eb  dup
0x560ec  ldstr    aEmailaddress2// "emailaddress2"
0x560f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x560f6  dup
0x560f7  ldstr    aSetemailaddres_1// "setemailaddresses3"
0x560fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56101  dup
0x56102  ldstr    aEmailaddress3// "emailaddress3"
0x56107  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5610c  dup
0x5610d  ldstr    aSetfax// "setfax"
0x56112  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56117  dup
0x56118  ldstr    aFax// "fax"
0x5611d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56122  dup
0x56123  ldstr    aSetcrmparentac// "setcrmparentaccount"
0x56128  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5612d  dup
0x5612e  ldstr    aContactid// "contactid"
0x56133  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56138  dup
0x56139  ldstr    aCrmownerid// "crmownerid"
0x5613e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56143  dup
0x56144  ldstr    aStatuscode// "statuscode"
0x56149  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5614e  dup
0x5614f  ldstr    aSetcrmsecondpa// "setcrmsecondpagedata"
0x56154  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56159  dup
0x5615a  ldstr    aBusiness2// "business2"
0x5615f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56164  dup
0x56165  ldstr    aCallback// "callback"
0x5616a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5616f  dup
0x56170  ldstr    aCompany// "company"
0x56175  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5617a  dup
0x5617b  ldstr    aHome2// "home2"
0x56180  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56185  dup
0x56186  ldstr    aSetbusinessstr// "setbusinessstreet"
0x5618b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56190  dup
0x56191  ldstr    aAddress1Line1// "address1_line1"
0x56196  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5619b  dup
0x5619c  ldstr    aAddress1Line2// "address1_line2"
0x561a1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561a6  dup
0x561a7  ldstr    aAddress1Line3// "address1_line3"
0x561ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561b1  dup
0x561b2  ldstr    aSethomestreet// "sethomestreet"
0x561b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561bc  dup
0x561bd  ldstr    aAddress2Line1// "address2_line1"
0x561c2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561c7  dup
0x561c8  ldstr    aAddress2Line2// "address2_line2"
0x561cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561d2  dup
0x561d3  ldstr    aAddress2Line3// "address2_line3"
0x561d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561dd  dup
0x561de  ldstr    aSetothersstree// "setothersstreet"
0x561e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561e8  dup
0x561e9  ldstr    aAddress3Line1// "address3_line1"
0x561ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561f3  dup
0x561f4  ldstr    aAddress3Line2// "address3_line2"
0x561f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x561fe  dup
0x561ff  ldstr    aAddress3Line3// "address3_line3"
0x56204  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56209  dup
0x5620a  ldstr    aSetbusinessadd// "setbusinessaddress"
0x5620f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56214  dup
0x56215  ldstr    aAddress1City// "address1_city"
0x5621a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5621f  dup
0x56220  ldstr    aAddress1State// "address1_state"
0x56225  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5622a  dup
0x5622b  ldstr    aAddress1Countr// "address1_country"
0x56230  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56235  dup
0x56236  ldstr    aAddress1Postal// "address1_postalcode"
0x5623b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56240  dup
0x56241  ldstr    aAddress1Postof// "address1_postofficebox"
0x56246  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5624b  dup
0x5624c  ldstr    aSethomeaddress// "sethomeaddress"
0x56251  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56256  dup
0x56257  ldstr    aAddress2City// "address2_city"
0x5625c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56261  dup
0x56262  ldstr    aAddress2Countr// "address2_country"
0x56267  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5626c  dup
0x5626d  ldstr    aAddress2Postal// "address2_postalcode"
0x56272  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56277  dup
0x56278  ldstr    aAddress2Postof// "address2_postofficebox"
0x5627d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56282  dup
0x56283  ldstr    aAddress2State// "address2_state"
0x56288  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5628d  dup
0x5628e  ldstr    aSetothersaddre// "setothersaddress"
0x56293  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56298  dup
0x56299  ldstr    aAddress3City// "address3_city"
0x5629e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562a3  dup
0x562a4  ldstr    aAddress3Countr// "address3_country"
0x562a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562ae  dup
0x562af  ldstr    aAddress3Postal// "address3_postalcode"
0x562b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562b9  dup
0x562ba  ldstr    aAddress3Postof// "address3_postofficebox"
0x562bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562c4  dup
0x562c5  ldstr    aAddress3State// "address3_state"
0x562ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562cf  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping::_contactSyncPropertyKeys
0x562d4  ldarg.0
0x562d5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x562da  dup
0x562db  ldstr    aAttachments// "attachments"
0x562e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562e5  dup
0x562e6  ldstr    aSubject// "subject"
0x562eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562f0  dup
0x562f1  ldstr    aBody// "body"
0x562f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x562fb  dup
0x562fc  ldstr    aSetbody// "setbody"
0x56301  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56306  dup
0x56307  ldstr    aLocation// "location"
0x5630c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56311  dup
0x56312  ldstr    aIsalldayevent// "isalldayevent"
0x56317  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5631c  dup
0x5631d  ldstr    aScheduledstart// "scheduledstart"
0x56322  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56327  dup
0x56328  ldstr    aScheduledend// "scheduledend"
0x5632d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56332  dup
0x56333  ldstr    aActivityid// "activityid"
0x56338  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5633d  dup
0x5633e  ldstr    aCrmownerid// "crmownerid"
0x56343  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56348  dup
0x56349  ldstr    aOwneridtype// "owneridtype"
0x5634e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56353  dup
0x56354  ldstr    aCrmobjecttypec// "crmobjecttypecode"
0x56359  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5635e  dup
0x5635f  ldstr    aSetrequiredatt// "setrequiredattendees"
0x56364  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56369  dup
0x5636a  ldstr    aSetoptionalatt// "setoptionalattendees"
0x5636f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56374  dup
0x56375  ldstr    aSetorganizer// "setorganizer"
0x5637a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5637f  dup
0x56380  ldstr    aSetcrmregardin// "setcrmregarding"
0x56385  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5638a  dup
0x5638b  ldstr    aSetapptstatus// "setapptstatus"
0x56390  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x56395  dup
0x56396  ldstr    aOutlookownerap// "outlookownerapptid"
0x5639b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x563a0  dup
0x563a1  ldstr    aGlobalobjectid// "globalobjectid"
0x563a6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x563ab  dup
0x563ac  ldstr    aOrganizer// "organizer"
0x563b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x563b6  dup
0x563b7  ldstr    aSetcrmpartyinf// "setcrmpartyinfo"
0x563bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x563c1  dup
0x563c2  ldstr    aCrmserviceid// "crmserviceid"
0x563c7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
  ... truncated ...
```
