# Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::.cctor

- ea: `0xaa0`
- end: `0xd91`
- name: `Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::.cctor`
- size: `753`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0xabe`: `address1_composite`
- `0xb96`: `address2_composite`
- `0xc6e`: `address3_composite`
- `0xd38`: `createdby`
- `0xd44`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0xaa5  dup
0xaa6  ldstr    aAddress1Addres// "address1_addresstypecode"
0xaab  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xab0  pop
0xab1  dup
0xab2  ldstr    aAddress1City// "address1_city"
0xab7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xabc  pop
0xabd  dup
0xabe  ldstr    aAddress1Compos// "address1_composite"
0xac3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xac8  pop
0xac9  dup
0xaca  ldstr    aAddress1Countr// "address1_country"
0xacf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xad4  pop
0xad5  dup
0xad6  ldstr    aAddress1County// "address1_county"
0xadb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xae0  pop
0xae1  dup
0xae2  ldstr    aAddress1Fax// "address1_fax"
0xae7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xaec  pop
0xaed  dup
0xaee  ldstr    aAddress1Latitu// "address1_latitude"
0xaf3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xaf8  pop
0xaf9  dup
0xafa  ldstr    aAddress1Line1// "address1_line1"
0xaff  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb04  pop
0xb05  dup
0xb06  ldstr    aAddress1Line2// "address1_line2"
0xb0b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb10  pop
0xb11  dup
0xb12  ldstr    aAddress1Line3// "address1_line3"
0xb17  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb1c  pop
0xb1d  dup
0xb1e  ldstr    aAddress1Longit// "address1_longitude"
0xb23  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb28  pop
0xb29  dup
0xb2a  ldstr    aAddress1Postal// "address1_postalcode"
0xb2f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb34  pop
0xb35  dup
0xb36  ldstr    aAddress1Postof// "address1_postofficebox"
0xb3b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb40  pop
0xb41  dup
0xb42  ldstr    aAddress1Primar// "address1_primarycontactname"
0xb47  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb4c  pop
0xb4d  dup
0xb4e  ldstr    aAddress1Stateo// "address1_stateorprovince"
0xb53  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb58  pop
0xb59  dup
0xb5a  ldstr    aAddress1Teleph// "address1_telephone1"
0xb5f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb64  pop
0xb65  dup
0xb66  ldstr    aAddress1Teleph_0// "address1_telephone2"
0xb6b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb70  pop
0xb71  dup
0xb72  ldstr    aAddress1Teleph_1// "address1_telephone3"
0xb77  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb7c  pop
0xb7d  dup
0xb7e  ldstr    aAddress2Addres// "address2_addresstypecode"
0xb83  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb88  pop
0xb89  dup
0xb8a  ldstr    aAddress2City// "address2_city"
0xb8f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb94  pop
0xb95  dup
0xb96  ldstr    aAddress2Compos// "address2_composite"
0xb9b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xba0  pop
0xba1  dup
0xba2  ldstr    aAddress2Countr// "address2_country"
0xba7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbac  pop
0xbad  dup
0xbae  ldstr    aAddress2County// "address2_county"
0xbb3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbb8  pop
0xbb9  dup
0xbba  ldstr    aAddress2Fax// "address2_fax"
0xbbf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbc4  pop
0xbc5  dup
0xbc6  ldstr    aAddress2Latitu// "address2_latitude"
0xbcb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbd0  pop
0xbd1  dup
0xbd2  ldstr    aAddress2Line1// "address2_line1"
0xbd7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbdc  pop
0xbdd  dup
0xbde  ldstr    aAddress2Line2// "address2_line2"
0xbe3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbe8  pop
0xbe9  dup
0xbea  ldstr    aAddress2Line3// "address2_line3"
0xbef  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbf4  pop
0xbf5  dup
0xbf6  ldstr    aAddress2Longit// "address2_longitude"
0xbfb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc00  pop
0xc01  dup
0xc02  ldstr    aAddress2Postal// "address2_postalcode"
0xc07  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc0c  pop
0xc0d  dup
0xc0e  ldstr    aAddress2Postof// "address2_postofficebox"
0xc13  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc18  pop
0xc19  dup
0xc1a  ldstr    aAddress2Primar// "address2_primarycontactname"
0xc1f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc24  pop
0xc25  dup
0xc26  ldstr    aAddress2Stateo// "address2_stateorprovince"
0xc2b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc30  pop
0xc31  dup
0xc32  ldstr    aAddress2Teleph// "address2_telephone1"
0xc37  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc3c  pop
0xc3d  dup
0xc3e  ldstr    aAddress2Teleph_0// "address2_telephone2"
0xc43  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc48  pop
0xc49  dup
0xc4a  ldstr    aAddress2Teleph_1// "address2_telephone3"
0xc4f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc54  pop
0xc55  dup
0xc56  ldstr    aAddress3Addres// "address3_addresstypecode"
0xc5b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc60  pop
0xc61  dup
0xc62  ldstr    aAddress3City// "address3_city"
0xc67  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc6c  pop
0xc6d  dup
0xc6e  ldstr    aAddress3Compos// "address3_composite"
0xc73  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc78  pop
0xc79  dup
0xc7a  ldstr    aAddress3Countr// "address3_country"
0xc7f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc84  pop
0xc85  dup
0xc86  ldstr    aAddress3County// "address3_county"
0xc8b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc90  pop
0xc91  dup
0xc92  ldstr    aAddress3Fax// "address3_fax"
0xc97  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xc9c  pop
0xc9d  dup
0xc9e  ldstr    aAddress3Latitu// "address3_latitude"
0xca3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xca8  pop
0xca9  dup
0xcaa  ldstr    aAddress3Line1// "address3_line1"
0xcaf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xcb4  pop
0xcb5  dup
0xcb6  ldstr    aAddress3Line2// "address3_line2"
0xcbb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xcc0  pop
0xcc1  dup
0xcc2  ldstr    aAddress3Line3// "address3_line3"
0xcc7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xccc  pop
0xccd  dup
0xcce  ldstr    aAddress3Longit// "address3_longitude"
0xcd3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xcd8  pop
0xcd9  dup
0xcda  ldstr    aAddress3Postal// "address3_postalcode"
0xcdf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xce4  pop
0xce5  dup
0xce6  ldstr    aAddress3Postof// "address3_postofficebox"
0xceb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xcf0  pop
0xcf1  dup
0xcf2  ldstr    aAddress3Primar// "address3_primarycontactname"
0xcf7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xcfc  pop
0xcfd  dup
0xcfe  ldstr    aAddress3Stateo// "address3_stateorprovince"
0xd03  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd08  pop
0xd09  dup
0xd0a  ldstr    aAddress3Teleph// "address3_telephone1"
0xd0f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd14  pop
0xd15  dup
0xd16  ldstr    aAddress3Teleph_0// "address3_telephone2"
0xd1b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd20  pop
0xd21  dup
0xd22  ldstr    aAddress3Teleph_1// "address3_telephone3"
0xd27  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd2c  pop
0xd2d  stsfld   class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::VisibleAddressAttributes
0xd32  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0xd37  dup
0xd38  ldstr    aCreatedby// "createdby"
0xd3d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd42  pop
0xd43  dup
0xd44  ldstr    aCreatedon// "createdon"
0xd49  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd4e  pop
0xd4f  dup
0xd50  ldstr    aFullname// "fullname"
0xd55  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd5a  pop
0xd5b  dup
0xd5c  ldstr    aModifiedon// "modifiedon"
0xd61  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd66  pop
0xd67  dup
0xd68  ldstr    aModifiedby// "modifiedby"
0xd6d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd72  pop
0xd73  dup
0xd74  ldstr    aOwnerid// "ownerid"
0xd79  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd7e  pop
0xd7f  dup
0xd80  ldstr    aTicketnumber// "ticketnumber"
0xd85  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd8a  pop
0xd8b  stsfld   class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::ReadOnlyAttributes
0xd90  ret
```
