# Microsoft.Crm.Common.Application.Platform.Email::ResetDirectionAndStateStatus

- ea: `0x3410`
- end: `0x344d`
- name: `Microsoft.Crm.Common.Application.Platform.Email::ResetDirectionAndStateStatus`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3320`

## pseudocode

```c

```

## disassembly

```asm
0x3410  ldarg.0
0x3411  ldstr    aDirectioncode// "directioncode"
0x3416  ldc.i4.1
0x3417  box      [mscorlib]System.Boolean
0x341c  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3421  ldarg.0
0x3422  ldstr    aStatecode// "statecode"
0x3427  ldc.i4.0
0x3428  stloc.0
0x3429  ldloca.s 0
0x342b  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.EmailState
0x3431  callvirt instance string [mscorlib]System.Object::ToString()
0x3436  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x343b  ldarg.0
0x343c  ldstr    aStatuscode// "statuscode"
0x3441  ldc.i4.1
0x3442  box      [mscorlib]System.Int32
0x3447  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x344c  ret
```
