# Microsoft.Crm.Web.Tools.BulkDelete.DeleteImportedRecords::ConfigureForm

- ea: `0x8db00`
- end: `0x8dd0b`
- name: `Microsoft.Crm.Web.Tools.BulkDelete.DeleteImportedRecords::ConfigureForm`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8db00`
- `0x8dd10`

## string_xrefs

- `0x8db1d`: `DeleteMode`
- `0x8db39`: `BulkDelete.DeleteImporteRecords.Title`
- `0x8db52`: `BulkDelete.DeleteImporteRecordsSingleFile.Description`
- `0x8db6a`: `BulkDelete.DeleteImporteRecords.Description`
- `0x8dc4f`: `//deleteimport`
- `0x8dcac`: `//DeleteMode`

## pseudocode

```c

```

## disassembly

```asm
0x8db00  ldarg.0
0x8db01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x8db06  ldarg.0
0x8db07  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8db0c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x8db11  stloc.0
0x8db12  ldarg.0
0x8db13  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8db18  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8db1d  ldstr    aDeletemode// "DeleteMode"
0x8db22  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8db27  ldstr    aSingle// "single"
0x8db2c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8db31  stloc.1
0x8db32  ldloc.0
0x8db33  ldarg.0
0x8db34  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8db39  ldstr    aBulkdeleteDele// "BulkDelete.DeleteImporteRecords.Title"
0x8db3e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8db43  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x8db48  ldloc.1
0x8db49  brfalse.s loc_8DB63
0x8db4b  ldloc.0
0x8db4c  ldarg.0
0x8db4d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8db52  ldstr    aBulkdeleteDele_0// "BulkDelete.DeleteImporteRecordsSingleFi"...
0x8db57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8db5c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x8db61  br.s     loc_8DB79
0x8db63  ldloc.0
0x8db64  ldarg.0
0x8db65  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8db6a  ldstr    aBulkdeleteDele_1// "BulkDelete.DeleteImporteRecords.Descrip"...
0x8db6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8db74  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x8db79  ldarg.0
0x8db7a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8db7f  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x8db84  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x8db89  ldc.i4.0
0x8db8a  conv.i8
0x8db8b  ble      loc_8DD0A
0x8db90  ldarg.0
0x8db91  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8db96  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x8db9b  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x8dba0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x8dba5  stloc.2
0x8dba6  ldloc.2
0x8dba7  ldstr    aJobname// "//jobname"
0x8dbac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8dbb1  stloc.3
0x8dbb2  ldloc.3
0x8dbb3  brtrue.s loc_8DBD3
0x8dbb5  ldloc.3
0x8dbb6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dbbb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8dbc0  brfalse.s loc_8DBD3
0x8dbc2  ldc.i4   0x80048457
0x8dbc7  ldc.i4.0
0x8dbc8  newarr   [mscorlib]System.Object
0x8dbcd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8dbd2  throw
0x8dbd3  ldloc.2
0x8dbd4  ldstr    aCcrecipients// "//ccrecipients"
0x8dbd9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8dbde  stloc.s  4
0x8dbe0  ldc.i4.0
0x8dbe1  newarr   [mscorlib]System.Guid
0x8dbe6  stloc.s  5
0x8dbe8  ldloc.s  4
0x8dbea  brfalse.s loc_8DC4B
0x8dbec  ldloc.s  4
0x8dbee  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dbf3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8dbf8  brtrue.s loc_8DC4B
0x8dbfa  ldloc.s  4
0x8dbfc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dc01  ldc.i4.1
0x8dc02  newarr   [mscorlib]System.Char
0x8dc07  dup
0x8dc08  ldc.i4.0
0x8dc09  ldc.i4.s 0x2C
0x8dc0b  stelem.i2
0x8dc0c  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x8dc11  stloc.s  0xB
0x8dc13  ldloc.s  0xB
0x8dc15  ldlen
0x8dc16  conv.i4
0x8dc17  ldc.i4.0
0x8dc18  blt.s    loc_8DC4B
0x8dc1a  ldloc.s  0xB
0x8dc1c  ldlen
0x8dc1d  conv.i4
0x8dc1e  newarr   [mscorlib]System.Guid
0x8dc23  stloc.s  5
0x8dc25  ldc.i4.0
0x8dc26  stloc.s  0xC
0x8dc28  br.s     loc_8DC43
0x8dc2a  ldloc.s  5
0x8dc2c  ldloc.s  0xC
0x8dc2e  ldloc.s  0xB
0x8dc30  ldloc.s  0xC
0x8dc32  ldelem.ref
0x8dc33  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8dc38  stelem   [mscorlib]System.Guid
0x8dc3d  ldloc.s  0xC
0x8dc3f  ldc.i4.1
0x8dc40  add
0x8dc41  stloc.s  0xC
0x8dc43  ldloc.s  0xC
0x8dc45  ldloc.s  0xB
0x8dc47  ldlen
0x8dc48  conv.i4
0x8dc49  blt.s    loc_8DC2A
0x8dc4b  ldc.i4.0
0x8dc4c  stloc.s  6
0x8dc4e  ldloc.2
0x8dc4f  ldstr    aDeleteimport// "//deleteimport"
0x8dc54  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8dc59  stloc.s  7
0x8dc5b  ldloc.s  7
0x8dc5d  brfalse.s loc_8DC7B
0x8dc5f  ldloc.s  7
0x8dc61  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dc66  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8dc6b  brtrue.s loc_8DC7B
0x8dc6d  ldloc.s  7
0x8dc6f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dc74  call     bool [mscorlib]System.Boolean::Parse(string)
0x8dc79  stloc.s  6
0x8dc7b  ldc.i4.0
0x8dc7c  stloc.s  8
0x8dc7e  ldloc.2
0x8dc7f  ldstr    aSendemail// "//sendemail"
0x8dc84  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8dc89  stloc.s  9
0x8dc8b  ldloc.s  9
0x8dc8d  brfalse.s loc_8DCAB
0x8dc8f  ldloc.s  9
0x8dc91  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dc96  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8dc9b  brtrue.s loc_8DCAB
0x8dc9d  ldloc.s  9
0x8dc9f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dca4  call     bool [mscorlib]System.Boolean::Parse(string)
0x8dca9  stloc.s  8
0x8dcab  ldloc.2
0x8dcac  ldstr    aDeletemode_0// "//DeleteMode"
0x8dcb1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8dcb6  stloc.s  0xA
0x8dcb8  ldloc.s  0xA
0x8dcba  brfalse.s loc_8DCE3
0x8dcbc  ldloc.s  0xA
0x8dcbe  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dcc3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8dcc8  brtrue.s loc_8DCE3
0x8dcca  ldloc.s  0xA
0x8dccc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dcd1  ldstr    aSingle// "single"
0x8dcd6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8dcdb  brfalse.s loc_8DCE1
0x8dcdd  ldc.i4.1
0x8dcde  stloc.1
0x8dcdf  br.s     loc_8DCE3
0x8dce1  ldc.i4.0
0x8dce2  stloc.1
0x8dce3  nop
0x8dce4  ldarg.0
0x8dce5  ldloc.3
0x8dce6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8dceb  ldloc.s  5
0x8dced  ldloc.s  6
0x8dcef  ldloc.s  8
0x8dcf1  ldloc.1
0x8dcf2  call     instance void Microsoft.Crm.Web.Tools.BulkDelete.DeleteImportedRecords::SubmitBulkDeleteJob(string jobName, valuetype [mscorlib]System.Guid[] ccRecipients, bool _deleteImportHistory, bool sendEmailNotification, bool isSingleFileMode)
0x8dcf7  ldarg.0
0x8dcf8  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x8dcfd  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::RaiseXMLSuccess(class [System.Web]System.Web.UI.Page)
0x8dd02  leave.s  loc_8DD0A
0x8dd04  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x8dd09  throw
0x8dd0a  ret
```
