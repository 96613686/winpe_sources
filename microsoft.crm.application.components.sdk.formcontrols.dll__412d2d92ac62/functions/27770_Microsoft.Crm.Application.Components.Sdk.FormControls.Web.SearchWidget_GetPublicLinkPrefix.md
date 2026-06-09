# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetPublicLinkPrefix

- ea: `0x27770`
- end: `0x2785a`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetPublicLinkPrefix`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x25890`

## callees

- `0x27770`

## string_xrefs

- `0x277fd`: `{0}/link/portal/{1}/{2}/Article/`

## pseudocode

```c

```

## disassembly

```asm
0x27770  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x27775  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2777a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2777f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27784  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x27789  stloc.0
0x2778a  ldloc.0
0x2778b  brfalse  loc_27854
0x27790  ldloc.0
0x27791  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x27796  brfalse  loc_27854
0x2779b  ldloc.0
0x2779c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x277a1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_IsParature()
0x277a6  brfalse  loc_2782E
0x277ab  ldloc.0
0x277ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x277b1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_SupportURL()
0x277b6  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x277bb  brtrue.s loc_2782E
0x277bd  ldloc.0
0x277be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x277c3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_AccountId()
0x277c8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x277cd  brtrue.s loc_2782E
0x277cf  ldloc.0
0x277d0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x277d5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_DepartmentId()
0x277da  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x277df  brtrue.s loc_2782E
0x277e1  ldloc.0
0x277e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x277e7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_SupportURL()
0x277ec  newobj   instance void [System]System.Uri::.ctor(string)
0x277f1  ldc.i4.1
0x277f2  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x277f7  stloc.1
0x277f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x277fd  ldstr    a0LinkPortal12A// "{0}/link/portal/{1}/{2}/Article/"
0x27802  ldc.i4.3
0x27803  newarr   [mscorlib]System.Object
0x27808  dup
0x27809  ldc.i4.0
0x2780a  ldloc.1
0x2780b  stelem.ref
0x2780c  dup
0x2780d  ldc.i4.1
0x2780e  ldloc.0
0x2780f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x27814  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_AccountId()
0x27819  stelem.ref
0x2781a  dup
0x2781b  ldc.i4.2
0x2781c  ldloc.0
0x2781d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x27822  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_DepartmentId()
0x27827  stelem.ref
0x27828  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2782d  ret
0x2782e  ldloc.0
0x2782f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x27834  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_IsParature()
0x27839  brtrue.s loc_27854
0x2783b  ldloc.0
0x2783c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x27841  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_UseExternalPortal()
0x27846  brfalse.s loc_27854
0x27848  ldloc.0
0x27849  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x2784e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_NativeCrmUrl()
0x27853  ret
0x27854  ldsfld   string [mscorlib]System.String::Empty
0x27859  ret
```
