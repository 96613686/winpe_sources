# Microsoft.Crm.Utility.ViewUtility::RetrieveDefaultColumns

- ea: `0x8d90`
- end: `0x94c2`
- name: `Microsoft.Crm.Utility.ViewUtility::RetrieveDefaultColumns`
- size: `1842`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8c60`

## callees

- `0x8d90`

## string_xrefs

- `0x9069`: `companyname`
- `0x9226`: `discountamount`
- `0x9231`: `totallineitemamount`
- `0x923c`: `totalamountlessfreight`
- `0x9252`: `freightamount`
- `0x925d`: `totalamount`
- `0x933e`: `quotedetail:quotedetailid:quotedetail:quotedetailid.volumediscountamount`
- `0x935f`: `quotedetail:quotedetailid:quotedetail:quotedetailid.baseamount`
- `0x936a`: `quotedetail:quotedetailid:quotedetail:quotedetailid.manualdiscountamount`
- `0x9375`: `quotedetail:quotedetailid:quotedetail:quotedetailid.extendedamount`

## pseudocode

```c

```

## disassembly

```asm
0x8d90  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8d95  stloc.0
0x8d96  ldarg.0
0x8d97  ldc.i4   0x400
0x8d9c  bgt.s    loc_8DD6
0x8d9e  ldarg.0
0x8d9f  ldc.i4.1
0x8da0  sub
0x8da1  switch   loc_8E85, loc_8F3A, loc_93CB, loc_9047, loc_949E, loc_949E, loc_949E, loc_8DF1
0x8dc6  ldarg.0
0x8dc7  ldc.i4   0x400
0x8dcc  beq      loc_93BB
0x8dd1  br       loc_949E
0x8dd6  ldarg.0
0x8dd7  ldc.i4   0x43C
0x8ddc  beq      loc_9112
0x8de1  ldarg.0
0x8de2  ldc.i4   0x43D
0x8de7  beq      loc_92CF
0x8dec  br       loc_949E
0x8df1  ldloc.0
0x8df2  ldstr    aSystemuserSyst// "systemuser:systemuserid:systemuser:syst"...
0x8df7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8dfc  ldloc.0
0x8dfd  ldstr    aSystemuserSyst_0// "systemuser:systemuserid:systemuser:syst"...
0x8e02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e07  ldloc.0
0x8e08  ldstr    aSystemuserSyst_1// "systemuser:systemuserid:systemuser:syst"...
0x8e0d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e12  ldloc.0
0x8e13  ldstr    aSystemuserSyst_2// "systemuser:systemuserid:systemuser:syst"...
0x8e18  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e1d  ldloc.0
0x8e1e  ldstr    aSystemuserSyst_3// "systemuser:systemuserid:systemuser:syst"...
0x8e23  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e28  ldloc.0
0x8e29  ldstr    aSystemuserSyst_4// "systemuser:systemuserid:systemuser:syst"...
0x8e2e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e33  ldloc.0
0x8e34  ldstr    aSystemuserSyst_5// "systemuser:systemuserid:systemuser:syst"...
0x8e39  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e3e  ldloc.0
0x8e3f  ldstr    aSystemuserSyst_6// "systemuser:systemuserid:systemuser:syst"...
0x8e44  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e49  ldloc.0
0x8e4a  ldstr    aSystemuserSyst_7// "systemuser:systemuserid:systemuser:syst"...
0x8e4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e54  ldloc.0
0x8e55  ldstr    aSystemuserSyst_8// "systemuser:systemuserid:systemuser:syst"...
0x8e5a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e5f  ldloc.0
0x8e60  ldstr    aSystemuserSyst_9// "systemuser:systemuserid:systemuser:syst"...
0x8e65  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e6a  ldloc.0
0x8e6b  ldstr    aSystemuserSyst_10// "systemuser:systemuserid:systemuser:syst"...
0x8e70  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e75  ldloc.0
0x8e76  ldstr    aSystemuserSyst_11// "systemuser:systemuserid:systemuser:syst"...
0x8e7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e80  br       loc_94C0
0x8e85  ldloc.0
0x8e86  ldstr    aName// "name"
0x8e8b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e90  ldloc.0
0x8e91  ldstr    aAddress1Line1// "address1_line1"
0x8e96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8e9b  ldloc.0
0x8e9c  ldstr    aAddress1Line2// "address1_line2"
0x8ea1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ea6  ldloc.0
0x8ea7  ldstr    aAddress1Line3// "address1_line3"
0x8eac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8eb1  ldloc.0
0x8eb2  ldstr    aAddress1City// "address1_city"
0x8eb7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ebc  ldloc.0
0x8ebd  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x8ec2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ec7  ldloc.0
0x8ec8  ldstr    aAddress1Postal// "address1_postalcode"
0x8ecd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ed2  ldloc.0
0x8ed3  ldstr    aAddress1Countr// "address1_country"
0x8ed8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8edd  ldloc.0
0x8ede  ldstr    aFax// "fax"
0x8ee3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ee8  ldloc.0
0x8ee9  ldstr    aTelephone1// "telephone1"
0x8eee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ef3  ldloc.0
0x8ef4  ldstr    aEmailaddress1// "emailaddress1"
0x8ef9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8efe  ldloc.0
0x8eff  ldstr    aWebsiteurl// "websiteurl"
0x8f04  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f09  ldloc.0
0x8f0a  ldstr    aAccountnumber// "accountnumber"
0x8f0f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f14  ldloc.0
0x8f15  ldstr    aCreditlimit// "creditlimit"
0x8f1a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f1f  ldloc.0
0x8f20  ldstr    aTickersymbol// "tickersymbol"
0x8f25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f2a  ldloc.0
0x8f2b  ldstr    aPrimarycontact// "primarycontactid"
0x8f30  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f35  br       loc_94C0
0x8f3a  ldloc.0
0x8f3b  ldstr    aFirstname// "firstname"
0x8f40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f45  ldloc.0
0x8f46  ldstr    aMiddlename// "middlename"
0x8f4b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f50  ldloc.0
0x8f51  ldstr    aLastname// "lastname"
0x8f56  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f5b  ldloc.0
0x8f5c  ldstr    aSalutation// "salutation"
0x8f61  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f66  ldloc.0
0x8f67  ldstr    aParentcustomer// "parentcustomerid"
0x8f6c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f71  ldloc.0
0x8f72  ldstr    aDepartment// "department"
0x8f77  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f7c  ldloc.0
0x8f7d  ldstr    aJobtitle// "jobtitle"
0x8f82  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f87  ldloc.0
0x8f88  ldstr    aAddress1Line1// "address1_line1"
0x8f8d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f92  ldloc.0
0x8f93  ldstr    aAddress1Line2// "address1_line2"
0x8f98  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8f9d  ldloc.0
0x8f9e  ldstr    aAddress1Line3// "address1_line3"
0x8fa3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fa8  ldloc.0
0x8fa9  ldstr    aAddress1City// "address1_city"
0x8fae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fb3  ldloc.0
0x8fb4  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x8fb9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fbe  ldloc.0
0x8fbf  ldstr    aAddress1Postal// "address1_postalcode"
0x8fc4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fc9  ldloc.0
0x8fca  ldstr    aAddress1Countr// "address1_country"
0x8fcf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fd4  ldloc.0
0x8fd5  ldstr    aFax// "fax"
0x8fda  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fdf  ldloc.0
0x8fe0  ldstr    aTelephone1// "telephone1"
0x8fe5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fea  ldloc.0
0x8feb  ldstr    aTelephone2// "telephone2"
0x8ff0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8ff5  ldloc.0
0x8ff6  ldstr    aEmailaddress1// "emailaddress1"
0x8ffb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9000  ldloc.0
0x9001  ldstr    aSpousesname// "spousesname"
0x9006  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x900b  ldloc.0
0x900c  ldstr    aAnniversary// "anniversary"
0x9011  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9016  ldloc.0
0x9017  ldstr    aBirthdate// "birthdate"
0x901c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9021  ldloc.0
0x9022  ldstr    aMobilephone// "mobilephone"
0x9027  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x902c  ldloc.0
0x902d  ldstr    aAssistantname// "assistantname"
0x9032  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9037  ldloc.0
0x9038  ldstr    aFullname// "fullname"
0x903d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9042  br       loc_94C0
0x9047  ldloc.0
0x9048  ldstr    aFirstname// "firstname"
0x904d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9052  ldloc.0
0x9053  ldstr    aLastname// "lastname"
0x9058  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x905d  ldloc.0
0x905e  ldstr    aSalutation// "salutation"
0x9063  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9068  ldloc.0
0x9069  ldstr    aCompanyname// "companyname"
0x906e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9073  ldloc.0
0x9074  ldstr    aAddress1Line1// "address1_line1"
0x9079  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x907e  ldloc.0
0x907f  ldstr    aAddress1Line2// "address1_line2"
0x9084  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9089  ldloc.0
0x908a  ldstr    aAddress1Line3// "address1_line3"
0x908f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9094  ldloc.0
0x9095  ldstr    aAddress1City// "address1_city"
0x909a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x909f  ldloc.0
0x90a0  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x90a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90aa  ldloc.0
0x90ab  ldstr    aAddress1Postal// "address1_postalcode"
0x90b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90b5  ldloc.0
0x90b6  ldstr    aAddress1Countr// "address1_country"
0x90bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90c0  ldloc.0
0x90c1  ldstr    aFax// "fax"
0x90c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90cb  ldloc.0
0x90cc  ldstr    aTelephone1// "telephone1"
0x90d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90d6  ldloc.0
0x90d7  ldstr    aEmailaddress1// "emailaddress1"
0x90dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90e1  ldloc.0
0x90e2  ldstr    aWebsiteurl// "websiteurl"
0x90e7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90ec  ldloc.0
0x90ed  ldstr    aMobilephone// "mobilephone"
0x90f2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x90f7  ldloc.0
0x90f8  ldstr    aPager// "pager"
0x90fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9102  ldloc.0
0x9103  ldstr    aFullname// "fullname"
0x9108  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x910d  br       loc_94C0
0x9112  ldloc.0
0x9113  ldstr    aQuotenumber// "quotenumber"
0x9118  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x911d  ldloc.0
0x911e  ldstr    aRevisionnumber// "revisionnumber"
0x9123  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9128  ldloc.0
0x9129  ldstr    aName// "name"
0x912e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9133  ldloc.0
0x9134  ldstr    aDescription// "description"
0x9139  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x913e  ldloc.0
0x913f  ldstr    aOpportunityid// "opportunityid"
0x9144  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9149  ldloc.0
0x914a  ldstr    aCustomerid// "customerid"
0x914f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9154  ldloc.0
0x9155  ldstr    aBilltoLine1// "billto_line1"
0x915a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x915f  ldloc.0
0x9160  ldstr    aBilltoLine2// "billto_line2"
0x9165  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x916a  ldloc.0
0x916b  ldstr    aBilltoLine3// "billto_line3"
0x9170  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9175  ldloc.0
0x9176  ldstr    aBilltoCity// "billto_city"
0x917b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9180  ldloc.0
0x9181  ldstr    aBilltoStateorp// "billto_stateorprovince"
0x9186  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x918b  ldloc.0
0x918c  ldstr    aBilltoCountry// "billto_country"
0x9191  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x9196  ldloc.0
0x9197  ldstr    aBilltoPostalco// "billto_postalcode"
0x919c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91a1  ldloc.0
0x91a2  ldstr    aBilltoTelephon// "billto_telephone"
0x91a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91ac  ldloc.0
0x91ad  ldstr    aBilltoFax// "billto_fax"
0x91b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91b7  ldloc.0
0x91b8  ldstr    aShiptoLine1// "shipto_line1"
0x91bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91c2  ldloc.0
0x91c3  ldstr    aShiptoLine2// "shipto_line2"
0x91c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91cd  ldloc.0
0x91ce  ldstr    aShiptoLine3// "shipto_line3"
0x91d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91d8  ldloc.0
0x91d9  ldstr    aShiptoCity// "shipto_city"
0x91de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91e3  ldloc.0
0x91e4  ldstr    aShiptoStateorp// "shipto_stateorprovince"
0x91e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x91ee  ldloc.0
0x91ef  ldstr    aShiptoCountry// "shipto_country"
0x91f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
  ... truncated ...
```
