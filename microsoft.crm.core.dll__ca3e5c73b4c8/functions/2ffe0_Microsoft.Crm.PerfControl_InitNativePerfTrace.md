# Microsoft.Crm.PerfControl::InitNativePerfTrace

- ea: `0x2ffe0`
- end: `0x300c0`
- name: `Microsoft.Crm.PerfControl::InitNativePerfTrace`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2fd70`

## callees

- `0x2e370`
- `0x2e390`
- `0x2ffe0`

## string_xrefs

- `0x2fffc`: `crmcore.dll`
- `0x3008d`: `CrmEtwWritePerfMarker`

## pseudocode

```c

```

## disassembly

```asm
0x2ffe0  ldsflda  int32 Microsoft.Crm.PerfControl::_initialized
0x2ffe5  ldc.i4.1
0x2ffe6  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0x2ffeb  brtrue   loc_300BF
0x2fff0  ldnull
0x2fff1  stsfld   class LogPerfTraceDelegate Microsoft.Crm.PerfControl::_logPerfTraceFn
0x2fff6  ldnull
0x2fff7  stsfld   class CodeMarkerDelegate Microsoft.Crm.PerfControl::_codeMarkerFn
0x2fffc  ldstr    aCrmcoreDll// "crmcore.dll"
0x30001  call     class Microsoft.Crm.SafeLibraryHandle Microsoft.Crm.NativeMethods::LoadLibrary(string fileName)
0x30006  stsfld   class Microsoft.Crm.SafeLibraryHandle Microsoft.Crm.PerfControl::_hModCrmCore
0x3000b  ldsfld   class Microsoft.Crm.SafeLibraryHandle Microsoft.Crm.PerfControl::_hModCrmCore
0x30010  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x30015  brtrue   loc_300BF
0x3001a  ldsfld   class Microsoft.Crm.SafeLibraryHandle Microsoft.Crm.PerfControl::_hModCrmCore
0x3001f  ldstr    aCrmlogpertrace// "CrmLogPerTrace"
0x30024  call     native int Microsoft.Crm.NativeMethods::GetProcAddress(class Microsoft.Crm.SafeLibraryHandle hModule, [in] [hasfieldmarshal] string procName)
0x30029  stloc.0
0x3002a  ldloc.0
0x3002b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x30030  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x30035  brfalse.s loc_30051
0x30037  ldloc.0
0x30038  ldtoken  LogPerfTraceDelegate
0x3003d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30042  call     class [mscorlib]System.Delegate [mscorlib]System.Runtime.InteropServices.Marshal::GetDelegateForFunctionPointer(native int, class [mscorlib]System.Type)
0x30047  castclass LogPerfTraceDelegate
0x3004c  stsfld   class LogPerfTraceDelegate Microsoft.Crm.PerfControl::_logPerfTraceFn
0x30051  ldsfld   class Microsoft.Crm.SafeLibraryHandle Microsoft.Crm.PerfControl::_hModCrmCore
0x30056  ldstr    aCrmlogcodemark// "CrmLogCodeMarker"
0x3005b  call     native int Microsoft.Crm.NativeMethods::GetProcAddress(class Microsoft.Crm.SafeLibraryHandle hModule, [in] [hasfieldmarshal] string procName)
0x30060  stloc.0
0x30061  ldloc.0
0x30062  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x30067  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3006c  brfalse.s loc_30088
0x3006e  ldloc.0
0x3006f  ldtoken  CodeMarkerDelegate
0x30074  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30079  call     class [mscorlib]System.Delegate [mscorlib]System.Runtime.InteropServices.Marshal::GetDelegateForFunctionPointer(native int, class [mscorlib]System.Type)
0x3007e  castclass CodeMarkerDelegate
0x30083  stsfld   class CodeMarkerDelegate Microsoft.Crm.PerfControl::_codeMarkerFn
0x30088  ldsfld   class Microsoft.Crm.SafeLibraryHandle Microsoft.Crm.PerfControl::_hModCrmCore
0x3008d  ldstr    aCrmetwwriteper// "CrmEtwWritePerfMarker"
0x30092  call     native int Microsoft.Crm.NativeMethods::GetProcAddress(class Microsoft.Crm.SafeLibraryHandle hModule, [in] [hasfieldmarshal] string procName)
0x30097  stloc.0
0x30098  ldloc.0
0x30099  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3009e  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x300a3  brfalse.s loc_300BF
0x300a5  ldloc.0
0x300a6  ldtoken  EventWritePerfMarkerDelegate
0x300ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x300b0  call     class [mscorlib]System.Delegate [mscorlib]System.Runtime.InteropServices.Marshal::GetDelegateForFunctionPointer(native int, class [mscorlib]System.Type)
0x300b5  castclass EventWritePerfMarkerDelegate
0x300ba  stsfld   class EventWritePerfMarkerDelegate Microsoft.Crm.PerfControl::_writePerfMarkerFn
0x300bf  ret
```
