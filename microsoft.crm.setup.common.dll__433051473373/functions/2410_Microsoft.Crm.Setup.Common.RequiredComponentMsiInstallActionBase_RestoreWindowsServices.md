# Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::RestoreWindowsServices

- ea: `0x2410`
- end: `0x245c`
- name: `Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::RestoreWindowsServices`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2410`
- `0x2500`

## string_xrefs

- `0x2425`: `Restarting service {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2410  ldarg.1
0x2411  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x2416  stloc.0
0x2417  br.s     loc_2440
0x2419  ldloc.0
0x241a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x241f  castclass [mscorlib]System.String
0x2424  stloc.1
0x2425  ldstr    aRestartingServ// "Restarting service {0}"
0x242a  ldc.i4.1
0x242b  newarr   [mscorlib]System.Object
0x2430  dup
0x2431  ldc.i4.0
0x2432  ldloc.1
0x2433  stelem.ref
0x2434  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x2439  ldarg.0
0x243a  ldloc.1
0x243b  call     instance void Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::StartWindowsService(string serviceName)
0x2440  ldloc.0
0x2441  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2446  brtrue.s loc_2419
0x2448  leave.s  loc_245B
0x244a  ldloc.0
0x244b  isinst   [mscorlib]System.IDisposable
0x2450  stloc.2
0x2451  ldloc.2
0x2452  brfalse.s loc_245A
0x2454  ldloc.2
0x2455  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x245a  endfinally
0x245b  ret
```
