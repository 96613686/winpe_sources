# Microsoft.Crm.Application.Controls.PageManager::isSettingsPage

- ea: `0xa9d90`
- end: `0xa9f90`
- name: `Microsoft.Crm.Application.Controls.PageManager::isSettingsPage`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xab5c0`

## callees

- `0xa9d90`
- `0xf0f70`

## string_xrefs

- `0xa9f26`: `/TOOLS/SERVICEMANAGEMENT/SERVICEMANAGEMENT.ASPX`
- `0xa9f44`: `/TOOLS/TEMPLATES/TEMPLATES.ASPX`
- `0xa9f71`: `/TOOLS/ADMINSECURITY/ADMINSECURITY_AREA.ASPX`

## pseudocode

```c

```

## disassembly

```asm
0xa9d90  ldc.i4.0
0xa9d91  stloc.0
0xa9d92  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xa9d97  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa9d9c  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0xa9da1  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xa9da6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa9dab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa9db0  dup
0xa9db1  ldc.i4.0
0xa9db2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseOrganizationName(bool)
0xa9db7  callvirt instance string [mscorlib]System.Object::ToString()
0xa9dbc  stloc.1
0xa9dbd  ldloc.1
0xa9dbe  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xa9dc3  stloc.2
0xa9dc4  ldloc.2
0xa9dc5  ldc.i4   0x76F3863F
0xa9dca  bgt.un.s loc_A9E38
0xa9dcc  ldloc.2
0xa9dcd  ldc.i4   0x23F0EBB5
0xa9dd2  bgt.un.s loc_A9DFA
0xa9dd4  ldloc.2
0xa9dd5  ldc.i4   0x35E1A6D
0xa9dda  beq      loc_A9F34
0xa9ddf  ldloc.2
0xa9de0  ldc.i4   0x9816974
0xa9de5  beq      loc_A9F7F
0xa9dea  ldloc.2
0xa9deb  ldc.i4   0x23F0EBB5
0xa9df0  beq      loc_A9E9E
0xa9df5  br       loc_A9F8E
0xa9dfa  ldloc.2
0xa9dfb  ldc.i4   0x4B7591F5
0xa9e00  bgt.un.s loc_A9E1D
0xa9e02  ldloc.2
0xa9e03  ldc.i4   0x418D7157
0xa9e08  beq      loc_A9EDD
0xa9e0d  ldloc.2
0xa9e0e  ldc.i4   0x4B7591F5
0xa9e13  beq      loc_A9F25
0xa9e18  br       loc_A9F8E
0xa9e1d  ldloc.2
0xa9e1e  ldc.i4   0x4BDF2C1F
0xa9e23  beq      loc_A9F61
0xa9e28  ldloc.2
0xa9e29  ldc.i4   0x76F3863F
0xa9e2e  beq      loc_A9F07
0xa9e33  br       loc_A9F8E
0xa9e38  ldloc.2
0xa9e39  ldc.i4   0x96111411
0xa9e3e  bgt.un.s loc_A9E66
0xa9e40  ldloc.2
0xa9e41  ldc.i4   0x81410ADB
0xa9e46  beq      loc_A9F52
0xa9e4b  ldloc.2
0xa9e4c  ldc.i4   0x9001F281
0xa9e51  beq      loc_A9EF2
0xa9e56  ldloc.2
0xa9e57  ldc.i4   0x96111411
0xa9e5c  beq      loc_A9F16
0xa9e61  br       loc_A9F8E
0xa9e66  ldloc.2
0xa9e67  ldc.i4   0xD60751D5
0xa9e6c  bgt.un.s loc_A9E89
0xa9e6e  ldloc.2
0xa9e6f  ldc.i4   0xD1F47DC7
0xa9e74  beq      loc_A9F70
0xa9e79  ldloc.2
0xa9e7a  ldc.i4   0xD60751D5
0xa9e7f  beq      loc_A9F43
0xa9e84  br       loc_A9F8E
0xa9e89  ldloc.2
0xa9e8a  ldc.i4   0xD62D1C13
0xa9e8f  beq.s    loc_A9EB3
0xa9e91  ldloc.2
0xa9e92  ldc.i4   0xD933FA25
0xa9e97  beq.s    loc_A9EC8
0xa9e99  br       loc_A9F8E
0xa9e9e  ldloc.1
0xa9e9f  ldstr    aToolsAdminAdmi// "/TOOLS/ADMIN/ADMIN.ASPX"
0xa9ea4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9ea9  brtrue   loc_A9F8C
0xa9eae  br       loc_A9F8E
0xa9eb3  ldloc.1
0xa9eb4  ldstr    aToolsBusinessB// "/TOOLS/BUSINESS/BUSINESS.ASPX"
0xa9eb9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9ebe  brtrue   loc_A9F8C
0xa9ec3  br       loc_A9F8E
0xa9ec8  ldloc.1
0xa9ec9  ldstr    aToolsDatamanag// "/TOOLS/DATAMANAGEMENT/DATAMANAGEMENT.AS"...
0xa9ece  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9ed3  brtrue   loc_A9F8C
0xa9ed8  br       loc_A9F8E
0xa9edd  ldloc.1
0xa9ede  ldstr    aToolsAuditAudi// "/TOOLS/AUDIT/AUDIT_AREA.ASPX"
0xa9ee3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9ee8  brtrue   loc_A9F8C
0xa9eed  br       loc_A9F8E
0xa9ef2  ldloc.1
0xa9ef3  ldstr    aToolsSystemcus// "/TOOLS/SYSTEMCUSTOMIZATION/SYSTEMCUSTOM"...
0xa9ef8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9efd  brtrue   loc_A9F8C
0xa9f02  br       loc_A9F8E
0xa9f07  ldloc.1
0xa9f08  ldstr    aToolsProductca_0// "/TOOLS/PRODUCTCATALOG/PRODUCTCATALOG.AS"...
0xa9f0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f12  brtrue.s loc_A9F8C
0xa9f14  br.s     loc_A9F8E
0xa9f16  ldloc.1
0xa9f17  ldstr    aToolsExternapp// "/TOOLS/EXTERNAPPMANAGEMENT/EXTERNAPPMAN"...
0xa9f1c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f21  brtrue.s loc_A9F8C
0xa9f23  br.s     loc_A9F8E
0xa9f25  ldloc.1
0xa9f26  ldstr    aToolsServicema// "/TOOLS/SERVICEMANAGEMENT/SERVICEMANAGEM"...
0xa9f2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f30  brtrue.s loc_A9F8C
0xa9f32  br.s     loc_A9F8E
0xa9f34  ldloc.1
0xa9f35  ldstr    aToolsMobileoff// "/TOOLS/MOBILEOFFLINE/MOBILEOFFLINE.ASPX"
0xa9f3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f3f  brtrue.s loc_A9F8C
0xa9f41  br.s     loc_A9F8E
0xa9f43  ldloc.1
0xa9f44  ldstr    aToolsTemplates// "/TOOLS/TEMPLATES/TEMPLATES.ASPX"
0xa9f49  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f4e  brtrue.s loc_A9F8C
0xa9f50  br.s     loc_A9F8E
0xa9f52  ldloc.1
0xa9f53  ldstr    aToolsDocumentm// "/TOOLS/DOCUMENTMANAGEMENT/DOCUMENTMANAG"...
0xa9f58  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f5d  brtrue.s loc_A9F8C
0xa9f5f  br.s     loc_A9F8E
0xa9f61  ldloc.1
0xa9f62  ldstr    aToolsSocialSoc// "/TOOLS/SOCIAL/SOCIAL_AREA.ASPX"
0xa9f67  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f6c  brtrue.s loc_A9F8C
0xa9f6e  br.s     loc_A9F8E
0xa9f70  ldloc.1
0xa9f71  ldstr    aToolsAdminsecu// "/TOOLS/ADMINSECURITY/ADMINSECURITY_AREA"...
0xa9f76  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f7b  brtrue.s loc_A9F8C
0xa9f7d  br.s     loc_A9F8E
0xa9f7f  ldloc.1
0xa9f80  ldstr    aRootWopiframeA// "/_ROOT/WOPIFRAME.ASPX"
0xa9f85  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f8a  brfalse.s loc_A9F8E
0xa9f8c  ldc.i4.1
0xa9f8d  stloc.0
0xa9f8e  ldloc.0
0xa9f8f  ret
```
