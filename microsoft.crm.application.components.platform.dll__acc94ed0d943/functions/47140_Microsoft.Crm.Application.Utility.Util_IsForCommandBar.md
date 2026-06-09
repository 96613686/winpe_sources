# Microsoft.Crm.Application.Utility.Util::IsForCommandBar

- ea: `0x47140`
- end: `0x4724d`
- name: `Microsoft.Crm.Application.Utility.Util::IsForCommandBar`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4d210`

## callees

- `0x2fb90`
- `0x427d0`
- `0x47140`
- `0x47280`
- `0x48970`

## string_xrefs

- `0x47189`: `/_forms/read/layout.aspx`
- `0x4722c`: `DisableCommandUI`

## pseudocode

```c

```

## disassembly

```asm
0x47140  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x47145  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x4714a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MultiThreadMetadataGeneration()
0x4714f  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x47154  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47159  ldnull
0x4715a  stloc.0
0x4715b  brfalse.s loc_47178
0x4715d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x47162  brfalse.s loc_47170
0x47164  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x47169  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4716e  brtrue.s loc_47178
0x47170  call     class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Utility.Util::get_HttpRequest()
0x47175  stloc.0
0x47176  br.s     loc_47183
0x47178  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4717d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x47182  stloc.0
0x47183  ldloc.0
0x47184  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x47189  ldstr    aFormsReadLayou// "/_forms/read/layout.aspx"
0x4718e  ldc.i4.5
0x4718f  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x47194  brfalse.s loc_47198
0x47196  ldc.i4.1
0x47197  ret
0x47198  ldloc.0
0x47199  brfalse.s loc_471FA
0x4719b  ldloc.0
0x4719c  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x471a1  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x471a6  ldc.i4.5
0x471a7  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x471ac  brtrue.s loc_471FA
0x471ae  ldloc.0
0x471af  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x471b4  ldstr    aToolsFormedito// "/tools/formEditor/formeditor.aspx"
0x471b9  ldc.i4.5
0x471ba  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x471bf  brtrue.s loc_471FA
0x471c1  ldloc.0
0x471c2  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x471c7  ldstr    aAdvancedfindAd// "/advancedfind/advfind.aspx"
0x471cc  ldc.i4.5
0x471cd  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x471d2  brtrue.s loc_471FA
0x471d4  ldloc.0
0x471d5  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x471da  ldstr    aAdvancedfindFe// "/advancedfind/fetchData.aspx"
0x471df  ldc.i4.5
0x471e0  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x471e5  brtrue.s loc_471FA
0x471e7  ldloc.0
0x471e8  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x471ed  ldstr    aToolsVisualiza// "/tools/visualizationdesigner/visualizat"...
0x471f2  ldc.i4.5
0x471f3  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x471f8  br.s     loc_471FB
0x471fa  ldc.i4.1
0x471fb  stloc.1
0x471fc  ldc.i4.1
0x471fd  stloc.2
0x471fe  ldarg.0
0x471ff  brfalse.s loc_47223
0x47201  ldarg.1
0x47202  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47207  ldarg.0
0x47208  ldc.i4.1
0x47209  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x4720e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x47213  ldarg.1
0x47214  call     bool Microsoft.Crm.Application.Utility.Util::IsRefreshEnabledForEntity(int32 objectTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x47219  brfalse.s loc_4721F
0x4721b  ldc.i4.1
0x4721c  stloc.2
0x4721d  br.s     loc_4722C
0x4721f  ldc.i4.0
0x47220  stloc.2
0x47221  br.s     loc_4722C
0x47223  call     bool Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x47228  brfalse.s loc_4722C
0x4722a  ldc.i4.0
0x4722b  stloc.2
0x4722c  ldstr    aDisablecommand// "DisableCommandUI"
0x47231  ldc.i4.0
0x47232  box      [mscorlib]System.Int32
0x47237  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x4723c  unbox.any [mscorlib]System.Int32
0x47241  brtrue.s loc_47249
0x47243  ldloc.1
0x47244  ldc.i4.0
0x47245  ceq
0x47247  br.s     loc_4724A
0x47249  ldc.i4.0
0x4724a  ldloc.2
0x4724b  and
0x4724c  ret
```
