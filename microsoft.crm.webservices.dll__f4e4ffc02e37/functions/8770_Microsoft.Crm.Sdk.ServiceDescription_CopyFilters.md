# Microsoft.Crm.Sdk.ServiceDescription::CopyFilters

- ea: `0x8770`
- end: `0x87b5`
- name: `Microsoft.Crm.Sdk.ServiceDescription::CopyFilters`
- size: `69`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5dd0`
- `0x6090`
- `0x65e0`
- `0x8fd0`

## callees

- `0x8770`
- `0x87f0`

## pseudocode

```c

```

## disassembly

```asm
0x8770  newobj   instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::.ctor()
0x8775  stloc.0
0x8776  ldarg.0
0x8777  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::GetEnumerator()
0x877c  stloc.1
0x877d  br.s     loc_8798
0x877f  ldloc.1
0x8780  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8785  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType
0x878a  call     class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType Microsoft.Crm.Sdk.ServiceDescription::CreateFilter(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType filter)
0x878f  stloc.2
0x8790  ldloc.0
0x8791  ldloc.2
0x8792  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::Add(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType)
0x8797  pop
0x8798  ldloc.1
0x8799  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x879e  brtrue.s loc_877F
0x87a0  leave.s  loc_87B3
0x87a2  ldloc.1
0x87a3  isinst   [mscorlib]System.IDisposable
0x87a8  stloc.3
0x87a9  ldloc.3
0x87aa  brfalse.s loc_87B2
0x87ac  ldloc.3
0x87ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x87b2  endfinally
0x87b3  ldloc.0
0x87b4  ret
```
