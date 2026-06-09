# Microsoft.Crm.Admin.AdminService.PidGenUtility::ValidateProductKeyInternal

- ea: `0x32850`
- end: `0x3292b`
- name: `Microsoft.Crm.Admin.AdminService.PidGenUtility::ValidateProductKeyInternal`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x32950`

## callees

- `0x32850`
- `0x32a00`
- `0x32a10`
- `0x32a20`
- `0x32a30`
- `0x33220`
- `0x33250`
- `0x3f1a0`

## string_xrefs

- `0x32888`: `Could not load from license cache, attempting to calculate values.`
- `0x328a2`: `License Cache is null`
- `0x328c9`: `License Cache does not contain latest value`
- `0x328e3`: `License Cache is in an inconsistent state.`

## pseudocode

```c

```

## disassembly

```asm
0x32850  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x32855  ldc.i4.s 0x30
0x32857  ldstr    aEnteringValida// "Entering ValidateProductKeyInternal"
0x3285c  ldc.i4.0
0x3285d  newarr   [mscorlib]System.Object
0x32862  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x32867  call     class Microsoft.Crm.Admin.AdminService.PidGenCache Microsoft.Crm.Admin.AdminService.PidGenUtility::get_PidGenLicenseCache()
0x3286c  stloc.0
0x3286d  ldloc.0
0x3286e  brfalse.s loc_32881
0x32870  ldloc.0
0x32871  callvirt instance string Microsoft.Crm.Admin.AdminService.PidGenCache::get_LicenseKey()
0x32876  ldarg.0
0x32877  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3287c  brfalse  loc_32912
0x32881  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x32886  ldc.i4.s 0x30
0x32888  ldstr    aCouldNotLoadFr// "Could not load from license cache, atte"...
0x3288d  ldc.i4.0
0x3288e  newarr   [mscorlib]System.Object
0x32893  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x32898  ldloc.0
0x32899  brtrue.s loc_328B4
0x3289b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x328a0  ldc.i4.s 0x30
0x328a2  ldstr    aLicenseCacheIs// "License Cache is null"
0x328a7  ldc.i4.0
0x328a8  newarr   [mscorlib]System.Object
0x328ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x328b2  br.s     loc_328F3
0x328b4  ldloc.0
0x328b5  callvirt instance string Microsoft.Crm.Admin.AdminService.PidGenCache::get_LicenseKey()
0x328ba  ldarg.0
0x328bb  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x328c0  brfalse.s loc_328DB
0x328c2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x328c7  ldc.i4.s 0x30
0x328c9  ldstr    aLicenseCacheDo// "License Cache does not contain latest v"...
0x328ce  ldc.i4.0
0x328cf  newarr   [mscorlib]System.Object
0x328d4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x328d9  br.s     loc_328F3
0x328db  ldnull
0x328dc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x328e1  ldc.i4.s 0x30
0x328e3  ldstr    aLicenseCacheIs_0// "License Cache is in an inconsistent sta"...
0x328e8  ldc.i4.0
0x328e9  newarr   [mscorlib]System.Object
0x328ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x328f3  ldnull
0x328f4  stloc.0
0x328f5  ldarg.1
0x328f6  ldarg.0
0x328f7  call     string LicenseFilesLocationCache::get_Directory()
0x328fc  call     string Microsoft.Crm.Admin.AdminService.PidGenUtility::get_Mpc()
0x32901  call     string Microsoft.Crm.Admin.AdminService.PidGenUtility::get_OemId()
0x32906  callvirt instance class Microsoft.Crm.Admin.AdminService.PidGenCache Microsoft.Crm.Admin.AdminService.PidGenXValidator::ValidateLicenseKey(string licenseKey, string directory, string mpc, string oemId)
0x3290b  stloc.0
0x3290c  ldloc.0
0x3290d  call     void Microsoft.Crm.Admin.AdminService.PidGenUtility::set_PidGenLicenseCache(class Microsoft.Crm.Admin.AdminService.PidGenCache value)
0x32912  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x32917  ldc.i4.s 0x30
0x32919  ldstr    aExitingValidat// "Exiting ValidateProductKeyV5Internal"
0x3291e  ldc.i4.0
0x3291f  newarr   [mscorlib]System.Object
0x32924  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x32929  ldloc.0
0x3292a  ret
```
