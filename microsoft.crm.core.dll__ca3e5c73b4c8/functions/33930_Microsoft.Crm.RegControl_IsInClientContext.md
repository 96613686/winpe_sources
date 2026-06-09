# Microsoft.Crm.RegControl::IsInClientContext

- ea: `0x33930`
- end: `0x33b37`
- name: `Microsoft.Crm.RegControl::IsInClientContext`
- size: `519`
- prototype: ``
- caller_count: `32`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x45b0`
- `0xe6d0`
- `0x13360`
- `0x13ba0`
- `0x140d0`
- `0x18890`
- `0x1dde0`
- `0x1ebf0`
- `0x1ed10`
- `0x22110`
- `0x242f0`
- `0x24a10`
- `0x24c10`
- `0x2fd70`
- `0x33600`
- `0x33840`
- `0x338c0`
- `0x34140`
- `0x34170`
- `0x341b0`
- `0x34250`
- `0x347a0`
- `0x350b0`
- `0x35ae0`
- `0x35bd0`
- `0x35cc0`
- `0x35d10`
- `0x35d40`
- `0x36fc0`
- `0x3e740`
- `0x3e900`
- `0x407f0`

## callees

- `0x33740`
- `0x33930`
- `0x33b40`

## string_xrefs

- `0x339e2`: `Microsoft.Crm.Application.Outlook.ConfigWizard.exe`
- `0x33a3a`: `CrmForOutlookInstaller.exe`
- `0x33a50`: `OfflineSyncAgent.exe`
- `0x33a78`: `Microsoft.Crm.Application.Host.dll`
- `0x33a8e`: `CRMABP32.dll`
- `0x33aa4`: `CrmInteropBootstrap.dll`
- `0x33aba`: `Microsoft.Crm.Application.Outlook.OfflineSync.dll`
- `0x33ad0`: `crmaddin.dll`
- `0x33ae6`: `Microsoft.Crm.Application.Outlook.Components.Platform.dll`

## pseudocode

```c

```

## disassembly

```asm
0x33930  ldsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x33935  brfalse.s loc_33942
0x33937  ldsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x3393c  unbox.any [mscorlib]System.Boolean
0x33941  ret
0x33942  ldsfld   object Microsoft.Crm.RegControl::s_syncRoot
0x33947  stloc.0
0x33948  ldc.i4.0
0x33949  stloc.1
0x3394a  ldloc.0
0x3394b  ldloca.s 1
0x3394d  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x33952  ldsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x33957  brfalse.s loc_33969
0x33959  ldsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x3395e  unbox.any [mscorlib]System.Boolean
0x33963  stloc.2
0x33964  leave    loc_33B35
0x33969  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x3396e  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x33973  ldstr    aCrmclient14b13// "CrmClient{14B13B7A-CA08-40bd-AC60-8C453"...
0x33978  ldc.i4.5
0x33979  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3397e  brtrue.s loc_33992
0x33980  ldc.i4.1
0x33981  box      [mscorlib]System.Boolean
0x33986  stsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x3398b  ldc.i4.1
0x3398c  stloc.2
0x3398d  leave    loc_33B35
0x33992  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33997  ldstr    aOutlookExe// "OUTLOOK.EXE"
0x3399c  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x339a1  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x339a6  brtrue   loc_33A61
0x339ab  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x339b0  ldstr    aExcelExe// "EXCEL.EXE"
0x339b5  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x339ba  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x339bf  brtrue   loc_33A61
0x339c4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x339c9  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Setup.Client.exe"
0x339ce  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x339d3  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x339d8  brtrue   loc_33A61
0x339dd  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x339e2  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Outlook.Confi"...
0x339e7  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x339ec  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x339f1  brtrue.s loc_33A61
0x339f3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x339f8  ldstr    aMicrosoftCrmOu// "Microsoft.Crm.Outlook.Diagnostics.exe"
0x339fd  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33a02  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33a07  brtrue.s loc_33A61
0x33a09  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33a0e  ldstr    aMicrosoftCrmAp_0// "Microsoft.Crm.Application.Hoster.exe"
0x33a13  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33a18  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33a1d  brtrue.s loc_33A61
0x33a1f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33a24  ldstr    aMicrosoftCrmAp_1// "Microsoft.Crm.Application.Outlook.WebFo"...
0x33a29  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33a2e  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33a33  brtrue.s loc_33A61
0x33a35  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33a3a  ldstr    aCrmforoutlooki// "CrmForOutlookInstaller.exe"
0x33a3f  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33a44  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33a49  brtrue.s loc_33A61
0x33a4b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33a50  ldstr    aOfflinesyncage// "OfflineSyncAgent.exe"
0x33a55  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33a5a  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33a5f  brfalse.s loc_33A73
0x33a61  ldc.i4.1
0x33a62  box      [mscorlib]System.Boolean
0x33a67  stsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x33a6c  ldc.i4.1
0x33a6d  stloc.2
0x33a6e  leave    loc_33B35
0x33a73  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33a78  ldstr    aMicrosoftCrmAp_2// "Microsoft.Crm.Application.Host.dll"
0x33a7d  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33a82  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33a87  brtrue.s loc_33AF7
0x33a89  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33a8e  ldstr    aCrmabp32Dll// "CRMABP32.dll"
0x33a93  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33a98  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33a9d  brtrue.s loc_33AF7
0x33a9f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33aa4  ldstr    aCrminteropboot// "CrmInteropBootstrap.dll"
0x33aa9  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33aae  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33ab3  brtrue.s loc_33AF7
0x33ab5  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33aba  ldstr    aMicrosoftCrmAp_3// "Microsoft.Crm.Application.Outlook.Offli"...
0x33abf  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33ac4  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33ac9  brtrue.s loc_33AF7
0x33acb  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33ad0  ldstr    aCrmaddinDll// "crmaddin.dll"
0x33ad5  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33ada  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33adf  brtrue.s loc_33AF7
0x33ae1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33ae6  ldstr    aMicrosoftCrmAp_4// "Microsoft.Crm.Application.Outlook.Compo"...
0x33aeb  call     native int Microsoft.Crm.RegControl::GetModuleHandle(string lpModuleName)
0x33af0  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x33af5  brfalse.s loc_33B06
0x33af7  ldc.i4.1
0x33af8  box      [mscorlib]System.Boolean
0x33afd  stsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x33b02  ldc.i4.1
0x33b03  stloc.2
0x33b04  leave.s  loc_33B35
0x33b06  call     bool Microsoft.Crm.RegControl::ForceClientContext()
0x33b0b  brfalse.s loc_33B1C
0x33b0d  ldc.i4.1
0x33b0e  box      [mscorlib]System.Boolean
0x33b13  stsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x33b18  ldc.i4.1
0x33b19  stloc.2
0x33b1a  leave.s  loc_33B35
0x33b1c  ldc.i4.0
0x33b1d  box      [mscorlib]System.Boolean
0x33b22  stsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x33b27  ldc.i4.0
0x33b28  stloc.2
0x33b29  leave.s  loc_33B35
0x33b2b  ldloc.1
0x33b2c  brfalse.s loc_33B34
0x33b2e  ldloc.0
0x33b2f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x33b34  endfinally
0x33b35  ldloc.2
0x33b36  ret
```
