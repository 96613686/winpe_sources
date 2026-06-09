# Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetErrorMessage_0

- ea: `0x302f0`
- end: `0x305ef`
- name: `Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetErrorMessage_0`
- size: `767`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x302b0`
- `0x302e0`

## callees

- `0xe1c0`
- `0x10040`
- `0x10080`
- `0x100d0`
- `0x16b80`
- `0x16b90`
- `0x30240`
- `0x302f0`
- `0x305f0`
- `0x30870`
- `0x308a0`
- `0x30b40`

## string_xrefs

- `0x30306`: `CRM_Dynamics_Community`
- `0x3033c`: `CRM_Dynamics_Community`
- `0x30319`: `<A target="_blank" href="{0}" class="ms-crm-Link">{1}</A>`
- `0x3036b`: `<A target="_blank" href="{0}" class="ms-crm-Link">{1}</A>`
- `0x30327`: `CRM_Dynamics_Community_Address`

## pseudocode

```c

```

## disassembly

```asm
0x302f0  ldsfld   string [mscorlib]System.String::Empty
0x302f5  stloc.0
0x302f6  ldarg.0
0x302f7  ldarg.1
0x302f8  call     instance bool Microsoft.Crm.Application.ResourceManager.BasicResourceManager::DoesErrorContainSpecialPlaceholder(string errorCode)
0x302fd  brfalse  loc_30410
0x30302  ldarg.2
0x30303  brtrue.s loc_30314
0x30305  ldarg.0
0x30306  ldstr    aCrmDynamicsCom// "CRM_Dynamics_Community"
0x3030b  ldarg.s  4
0x3030d  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30312  br.s     loc_30353
0x30314  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30319  ldstr    aATargetBlankHr// "<A target=\"_blank\" href=\"{0}\" class"...
0x3031e  ldc.i4.2
0x3031f  newarr   [mscorlib]System.Object
0x30324  dup
0x30325  ldc.i4.0
0x30326  ldarg.0
0x30327  ldstr    aCrmDynamicsCom_0// "CRM_Dynamics_Community_Address"
0x3032c  ldarg.s  4
0x3032e  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30333  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x30338  stelem.ref
0x30339  dup
0x3033a  ldc.i4.1
0x3033b  ldarg.0
0x3033c  ldstr    aCrmDynamicsCom// "CRM_Dynamics_Community"
0x30341  ldarg.s  4
0x30343  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30348  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3034d  stelem.ref
0x3034e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30353  stloc.1
0x30354  ldarg.2
0x30355  brtrue.s loc_30366
0x30357  ldarg.0
0x30358  ldstr    aMicrosoftSuppo// "Microsoft_Support"
0x3035d  ldarg.s  4
0x3035f  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30364  br.s     loc_303A5
0x30366  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3036b  ldstr    aATargetBlankHr// "<A target=\"_blank\" href=\"{0}\" class"...
0x30370  ldc.i4.2
0x30371  newarr   [mscorlib]System.Object
0x30376  dup
0x30377  ldc.i4.0
0x30378  ldarg.0
0x30379  ldstr    aMicrosoftSuppo_0// "Microsoft_Support_Address"
0x3037e  ldarg.s  4
0x30380  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30385  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x3038a  stelem.ref
0x3038b  dup
0x3038c  ldc.i4.1
0x3038d  ldarg.0
0x3038e  ldstr    aMicrosoftSuppo// "Microsoft_Support"
0x30393  ldarg.s  4
0x30395  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3039a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3039f  stelem.ref
0x303a0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x303a5  stloc.2
0x303a6  ldarg.0
0x303a7  ldstr    aErrorMessageGe// "Error_Message_Generic_Instruction"
0x303ac  ldarg.s  4
0x303ae  ldc.i4.2
0x303af  newarr   [mscorlib]System.Object
0x303b4  dup
0x303b5  ldc.i4.0
0x303b6  ldloc.1
0x303b7  stelem.ref
0x303b8  dup
0x303b9  ldc.i4.1
0x303ba  ldloc.2
0x303bb  stelem.ref
0x303bc  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, object[] arguments)
0x303c1  stloc.3
0x303c2  ldarg.1
0x303c3  ldstr    aGeneric// "Generic"
0x303c8  ldc.i4.5
0x303c9  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x303ce  brtrue.s loc_303FF
0x303d0  ldarg.0
0x303d1  ldstr    aErrorMessageGe_0// "Error_Message_Generic"
0x303d6  ldarg.s  4
0x303d8  ldc.i4.2
0x303d9  newarr   [mscorlib]System.Object
0x303de  dup
0x303df  ldc.i4.0
0x303e0  ldloc.3
0x303e1  stelem.ref
0x303e2  dup
0x303e3  ldc.i4.1
0x303e4  ldarg.2
0x303e5  brtrue.s loc_303EE
0x303e7  ldsfld   string [mscorlib]System.String::Empty
0x303ec  br.s     loc_303F3
0x303ee  ldstr    aBrBr// "<br><br>"
0x303f3  stelem.ref
0x303f4  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, object[] arguments)
0x303f9  stloc.0
0x303fa  br       loc_305ED
0x303ff  ldarg.0
0x30400  ldarg.1
0x30401  ldarg.2
0x30402  ldarg.s  4
0x30404  ldloc.3
0x30405  call     instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetUserErrorMessage(string errorCode, bool htmlVersion, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, string errorInstruction)
0x3040a  stloc.0
0x3040b  br       loc_305ED
0x30410  ldarg.0
0x30411  ldstr    aErrorMessage0x_0// "Error_Message_0x"
0x30416  ldarg.1
0x30417  call     string [mscorlib]System.String::Concat(string, string)
0x3041c  ldarg.s  4
0x3041e  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30423  stloc.0
0x30424  newobj   instance void Microsoft.Crm.Errors.ErrorLookup::.ctor()
0x30429  ldarg.1
0x3042a  ldarg.s  4
0x3042c  call     instance class Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Errors.ErrorLookup::GetError(string errorCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30431  stloc.s  4
0x30433  ldc.i4   0x8004B042
0x30438  ldloc.s  4
0x3043a  callvirt instance int32 Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x3043f  bne.un.s loc_304AA
0x30441  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x30446  ldarg.s  4
0x30448  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3044d  ldc.i4.4
0x3044e  ldc.i4   0xC0
0x30453  ldstr    aGeterrormessag// "GetErrorMessage"
0x30458  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x3045d  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationResourceLimit(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ResourceType, int32, string, string)
0x30462  stloc.s  8
0x30464  ldloca.s 8
0x30466  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x3046b  brtrue.s loc_30478
0x3046d  ldstr    aLimitForCustom// "Limit for custom entities cannot be nul"...
0x30472  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x30477  throw
0x30478  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x3047d  ldarg.s  4
0x3047f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30484  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserCulture()
0x30489  ldloc.0
0x3048a  ldc.i4.1
0x3048b  newarr   [mscorlib]System.Object
0x30490  dup
0x30491  ldc.i4.0
0x30492  ldloca.s 8
0x30494  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x30499  box      [mscorlib]System.Int32
0x3049e  stelem.ref
0x3049f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x304a4  stloc.0
0x304a5  br       loc_3055C
0x304aa  ldc.i4   0x8003F454
0x304af  ldloc.s  4
0x304b1  callvirt instance int32 Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x304b6  bne.un.s loc_30516
0x304b8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x304bd  ldarg.s  4
0x304bf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x304c4  ldstr    aMaxchildincide// "MaxChildIncidentNumber"
0x304c9  ldc.i4   0xCE
0x304ce  ldstr    aGeterrormessag// "GetErrorMessage"
0x304d3  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x304d8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x304dd  stloc.s  9
0x304df  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x304e4  ldarg.s  4
0x304e6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x304eb  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserCulture()
0x304f0  ldloc.0
0x304f1  ldc.i4.1
0x304f2  newarr   [mscorlib]System.Object
0x304f7  dup
0x304f8  ldc.i4.0
0x304f9  ldloc.s  9
0x304fb  brfalse.s loc_30506
0x304fd  ldloc.s  9
0x304ff  unbox.any [mscorlib]System.Int32
0x30504  br.s     loc_30508
0x30506  ldc.i4.s 0xA
0x30508  box      [mscorlib]System.Int32
0x3050d  stelem.ref
0x3050e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30513  stloc.0
0x30514  br.s     loc_3055C
0x30516  ldc.i4   0x80043E08
0x3051b  ldloc.s  4
0x3051d  callvirt instance int32 Microsoft.Crm.Errors.ErrorData::get_ErrorCode()
0x30522  bne.un.s loc_3055C
0x30524  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x30529  ldarg.s  4
0x3052b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30530  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserCulture()
0x30535  ldloc.0
0x30536  ldc.i4.1
0x30537  newarr   [mscorlib]System.Object
0x3053c  dup
0x3053d  ldc.i4.0
0x3053e  ldarg.s  4
0x30540  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30545  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxUploadFileSize()
0x3054a  ldc.i4   0x400
0x3054f  div
0x30550  box      [mscorlib]System.Int32
0x30555  stelem.ref
0x30556  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3055b  stloc.0
0x3055c  ldarg.3
0x3055d  brfalse.s loc_30566
0x3055f  ldloc.0
0x30560  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x30565  stloc.0
0x30566  ldloc.0
0x30567  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x3056c  stloc.s  5
0x3056e  ldstr    aErrorMessage00// "Error_Message_{0}_0x"
0x30573  ldarg.1
0x30574  call     string [mscorlib]System.String::Concat(string, string)
0x30579  stloc.s  6
0x3057b  ldnull
0x3057c  stloc.s  7
0x3057e  ldc.i4.2
0x3057f  stloc.s  0xA
0x30581  ldarg.0
0x30582  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x30587  ldarg.s  4
0x30589  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3058e  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserCulture()
0x30593  ldloc.s  6
0x30595  ldc.i4.1
0x30596  newarr   [mscorlib]System.Object
0x3059b  dup
0x3059c  ldc.i4.0
0x3059d  ldloc.s  0xA
0x3059f  box      [mscorlib]System.Int32
0x305a4  stelem.ref
0x305a5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x305aa  ldarg.s  4
0x305ac  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x305b1  stloc.s  7
0x305b3  ldloc.s  7
0x305b5  brfalse.s loc_305E5
0x305b7  ldarg.2
0x305b8  brfalse.s loc_305C7
0x305ba  ldloc.s  5
0x305bc  ldstr    aBr_0// "<br/>"
0x305c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x305c6  pop
0x305c7  ldarg.3
0x305c8  brfalse.s loc_305D3
0x305ca  ldloc.s  7
0x305cc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x305d1  stloc.s  7
0x305d3  ldloc.s  5
0x305d5  ldloc.s  7
0x305d7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x305dc  pop
0x305dd  ldloc.s  0xA
0x305df  ldc.i4.1
0x305e0  add
0x305e1  stloc.s  0xA
0x305e3  br.s     loc_30581
0x305e5  ldloc.s  5
0x305e7  callvirt instance string [mscorlib]System.Object::ToString()
0x305ec  stloc.0
0x305ed  ldloc.0
0x305ee  ret
```
