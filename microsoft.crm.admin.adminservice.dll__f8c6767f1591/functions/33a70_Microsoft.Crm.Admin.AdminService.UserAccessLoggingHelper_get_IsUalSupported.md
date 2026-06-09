# Microsoft.Crm.Admin.AdminService.UserAccessLoggingHelper::get_IsUalSupported

- ea: `0x33a70`
- end: `0x33aff`
- name: `Microsoft.Crm.Admin.AdminService.UserAccessLoggingHelper::get_IsUalSupported`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x33b00`
- `0x33b50`

## callees

- `0x339f0`
- `0x33a70`
- `0x38be0`
- `0x38bf0`
- `0x38c00`

## string_xrefs

- `0x33a77`: `ualapi.dll`
- `0x33a9c`: `ualapi.dll cannot be loaded with error code {0}`

## pseudocode

```c

```

## disassembly

```asm
0x33a70  call     bool Microsoft.Crm.Admin.AdminService.UserAccessLoggingHelper::get_IsServer2012OrHigher()
0x33a75  brfalse.s loc_33AD9
0x33a77  ldstr    aUalapiDll// "ualapi.dll"
0x33a7c  call     native int Microsoft.Crm.Admin.AdminService.UserAccessLogging.UalNativeMethods::LoadLibrary(string lpFileName)
0x33a81  stloc.0
0x33a82  ldloc.0
0x33a83  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33a88  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x33a8d  brfalse.s loc_33AB7
0x33a8f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x33a94  stloc.2
0x33a95  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x33a9a  ldc.i4.s 0x30
0x33a9c  ldstr    aUalapiDllCanno// "ualapi.dll cannot be loaded with error "...
0x33aa1  ldc.i4.1
0x33aa2  newarr   [mscorlib]System.Object
0x33aa7  dup
0x33aa8  ldc.i4.0
0x33aa9  ldloc.2
0x33aaa  box      [mscorlib]System.Int32
0x33aaf  stelem.ref
0x33ab0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33ab5  ldc.i4.0
0x33ab6  ret
0x33ab7  ldloc.0
0x33ab8  ldstr    aUalstart// "UalStart"
0x33abd  call     native unsigned int Microsoft.Crm.Admin.AdminService.UserAccessLogging.UalNativeMethods::GetProcAddress(native int module, string procName)
0x33ac2  stloc.1
0x33ac3  ldloc.0
0x33ac4  call     bool Microsoft.Crm.Admin.AdminService.UserAccessLogging.UalNativeMethods::FreeLibrary([hasfieldmarshal] native int)
0x33ac9  pop
0x33aca  ldloc.1
0x33acb  ldsfld   native unsigned int [mscorlib]System.UIntPtr::Zero
0x33ad0  call     bool [mscorlib]System.UIntPtr::op_Inequality(native unsigned int, native unsigned int)
0x33ad5  brfalse.s loc_33AFD
0x33ad7  ldc.i4.1
0x33ad8  ret
0x33ad9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x33ade  ldc.i4.s 0x30
0x33ae0  ldstr    aUalIsNotSuppor// "UAL is not supported on OS Version {0}."
0x33ae5  ldc.i4.1
0x33ae6  newarr   [mscorlib]System.Object
0x33aeb  dup
0x33aec  ldc.i4.0
0x33aed  call     class [mscorlib]System.OperatingSystem [mscorlib]System.Environment::get_OSVersion()
0x33af2  callvirt instance class [mscorlib]System.Version [mscorlib]System.OperatingSystem::get_Version()
0x33af7  stelem.ref
0x33af8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33afd  ldc.i4.0
0x33afe  ret
```
