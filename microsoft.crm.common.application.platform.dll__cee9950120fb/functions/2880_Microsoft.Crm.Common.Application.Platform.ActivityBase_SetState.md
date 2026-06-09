# Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState

- ea: `0x2880`
- end: `0x288b`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2890`

## pseudocode

```c

```

## disassembly

```asm
0x2880  ldarg.0
0x2881  ldarg.1
0x2882  ldarg.2
0x2883  ldc.i4.m1
0x2884  ldarg.3
0x2885  call     void Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState(string entityName, valuetype [mscorlib]System.Guid entityId, string newState, int32 newStatusCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x288a  ret
```
