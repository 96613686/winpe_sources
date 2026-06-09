# Microsoft.Crm.ObjectModel.SharePointColumnMappingHelper::.cctor

- ea: `0x189e90`
- end: `0x18a18c`
- name: `Microsoft.Crm.ObjectModel.SharePointColumnMappingHelper::.cctor`
- size: `764`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x18a171`: `servicetype`
- `0x18a13a`: `readurl`
- `0x189f26`: `sharepointcreatedon`
- `0x18a080`: `sharepointcreatedon`
- `0x189ee6`: `checkincomment`
- `0x18a040`: `checkincomment`
- `0x189eeb`: `_CheckinComment`
- `0x189f16`: `copysource`
- `0x18a070`: `copysource`
- `0x189f1b`: `_CopySource`
- `0x189f2b`: `Created_x0020_Date`
- `0x189fb6`: `appcreatedby`
- `0x18a100`: `appcreatedby`

## pseudocode

```c

```

## disassembly

```asm
0x189e90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x189e95  dup
0x189e96  ldstr    aDocumentid// "documentid"
0x189e9b  ldstr    aId_3// "ID"
0x189ea0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189ea5  dup
0x189ea6  ldstr    aFullname_0// "fullname"
0x189eab  ldstr    aFileleafref// "FileLeafRef"
0x189eb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189eb5  dup
0x189eb6  ldstr    aAbsoluteurl// "absoluteurl"
0x189ebb  ldstr    aFileref// "FileRef"
0x189ec0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189ec5  dup
0x189ec6  ldstr    aModified// "modified"
0x189ecb  ldstr    aLastX0020Modif// "Last_x0020_Modified"
0x189ed0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189ed5  dup
0x189ed6  ldstr    aSharepointmodi// "sharepointmodifiedby"
0x189edb  ldstr    aEditor// "Editor"
0x189ee0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189ee5  dup
0x189ee6  ldstr    aCheckincomment// "checkincomment"
0x189eeb  ldstr    aCheckincomment_0// "_CheckinComment"
0x189ef0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189ef5  dup
0x189ef6  ldstr    aCheckedoutto// "checkedoutto"
0x189efb  ldstr    aCheckedouttitl// "CheckedOutTitle"
0x189f00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f05  dup
0x189f06  ldstr    aContenttype// "contenttype"
0x189f0b  ldstr    aContenttype_0// "ContentType"
0x189f10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f15  dup
0x189f16  ldstr    aCopysource// "copysource"
0x189f1b  ldstr    aCopysource_0// "_CopySource"
0x189f20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f25  dup
0x189f26  ldstr    aSharepointcrea// "sharepointcreatedon"
0x189f2b  ldstr    aCreatedX0020Da// "Created_x0020_Date"
0x189f30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f35  dup
0x189f36  ldstr    aEditurl// "editurl"
0x189f3b  ldstr    aEdit_1// "Edit"
0x189f40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f45  dup
0x189f46  ldstr    aFilesize// "filesize"
0x189f4b  ldstr    aFileX0020Size// "File_x0020_Size"
0x189f50  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f55  dup
0x189f56  ldstr    aChildfoldercou// "childfoldercount"
0x189f5b  ldstr    aFolderchildcou// "FolderChildCount"
0x189f60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f65  dup
0x189f66  ldstr    aChilditemcount// "childitemcount"
0x189f6b  ldstr    aItemchildcount// "ItemChildCount"
0x189f70  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f75  dup
0x189f76  ldstr    aTitle_0// "title"
0x189f7b  ldstr    aTitle// "Title"
0x189f80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f85  dup
0x189f86  ldstr    aAuthor// "author"
0x189f8b  ldstr    aAuthor_1// "Author"
0x189f90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189f95  dup
0x189f96  ldstr    aFiletype// "filetype"
0x189f9b  ldstr    aFileX0020Type// "File_x0020_Type"
0x189fa0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189fa5  dup
0x189fa6  ldstr    aRelativelocati// "relativelocation"
0x189fab  ldstr    aFileref// "FileRef"
0x189fb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189fb5  dup
0x189fb6  ldstr    aAppcreatedby// "appcreatedby"
0x189fbb  ldstr    aAppauthor// "AppAuthor"
0x189fc0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189fc5  dup
0x189fc6  ldstr    aAppmodifiedby// "appmodifiedby"
0x189fcb  ldstr    aAppeditor// "AppEditor"
0x189fd0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189fd5  dup
0x189fd6  ldstr    aIscheckedout// "ischeckedout"
0x189fdb  ldstr    aCheckedouttitl// "CheckedOutTitle"
0x189fe0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189fe5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.SharePointColumnMappingHelper::_sharepointInternalName
0x189fea  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x189fef  dup
0x189ff0  ldstr    aDocumentid// "documentid"
0x189ff5  ldstr    aInt_0// "Int"
0x189ffa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x189fff  dup
0x18a000  ldstr    aFullname_0// "fullname"
0x18a005  ldstr    aLookup// "Lookup"
0x18a00a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a00f  dup
0x18a010  ldstr    aAbsoluteurl// "absoluteurl"
0x18a015  ldstr    aText_0// "Text"
0x18a01a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a01f  dup
0x18a020  ldstr    aModified// "modified"
0x18a025  ldstr    aDatetime// "DateTime"
0x18a02a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a02f  dup
0x18a030  ldstr    aSharepointmodi// "sharepointmodifiedby"
0x18a035  ldstr    aLookup// "Lookup"
0x18a03a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a03f  dup
0x18a040  ldstr    aCheckincomment// "checkincomment"
0x18a045  ldstr    aText_0// "Text"
0x18a04a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a04f  dup
0x18a050  ldstr    aCheckedoutto// "checkedoutto"
0x18a055  ldstr    aText_0// "Text"
0x18a05a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a05f  dup
0x18a060  ldstr    aContenttype// "contenttype"
0x18a065  ldstr    aText_0// "Text"
0x18a06a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a06f  dup
0x18a070  ldstr    aCopysource// "copysource"
0x18a075  ldstr    aText_0// "Text"
0x18a07a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a07f  dup
0x18a080  ldstr    aSharepointcrea// "sharepointcreatedon"
0x18a085  ldstr    aDatetime// "DateTime"
0x18a08a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a08f  dup
0x18a090  ldstr    aEditurl// "editurl"
0x18a095  ldstr    aText_0// "Text"
0x18a09a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a09f  dup
0x18a0a0  ldstr    aFilesize// "filesize"
0x18a0a5  ldstr    aInt_0// "Int"
0x18a0aa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a0af  dup
0x18a0b0  ldstr    aChildfoldercou// "childfoldercount"
0x18a0b5  ldstr    aInt_0// "Int"
0x18a0ba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a0bf  dup
0x18a0c0  ldstr    aChilditemcount// "childitemcount"
0x18a0c5  ldstr    aInt_0// "Int"
0x18a0ca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a0cf  dup
0x18a0d0  ldstr    aTitle_0// "title"
0x18a0d5  ldstr    aText_0// "Text"
0x18a0da  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a0df  dup
0x18a0e0  ldstr    aAuthor// "author"
0x18a0e5  ldstr    aText_0// "Text"
0x18a0ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a0ef  dup
0x18a0f0  ldstr    aFiletype// "filetype"
0x18a0f5  ldstr    aText_0// "Text"
0x18a0fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a0ff  dup
0x18a100  ldstr    aAppcreatedby// "appcreatedby"
0x18a105  ldstr    aText_0// "Text"
0x18a10a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a10f  dup
0x18a110  ldstr    aAppmodifiedby// "appmodifiedby"
0x18a115  ldstr    aText_0// "Text"
0x18a11a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a11f  dup
0x18a120  ldstr    aRelativelocati// "relativelocation"
0x18a125  ldstr    aText_0// "Text"
0x18a12a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x18a12f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.SharePointColumnMappingHelper::_sharepointColumnType
0x18a134  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x18a139  dup
0x18a13a  ldstr    aReadurl// "readurl"
0x18a13f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18a144  dup
0x18a145  ldstr    aEditurl// "editurl"
0x18a14a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18a14f  dup
0x18a150  ldstr    aSharepointdocu// "sharepointdocumentid"
0x18a155  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18a15a  dup
0x18a15b  ldstr    aIconclassname// "iconclassname"
0x18a160  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18a165  dup
0x18a166  ldstr    aLocationid// "locationid"
0x18a16b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18a170  dup
0x18a171  ldstr    aServicetype// "servicetype"
0x18a176  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18a17b  dup
0x18a17c  ldstr    aLocationname// "locationname"
0x18a181  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x18a186  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.ObjectModel.SharePointColumnMappingHelper::_ignoredColumns
0x18a18b  ret
```
