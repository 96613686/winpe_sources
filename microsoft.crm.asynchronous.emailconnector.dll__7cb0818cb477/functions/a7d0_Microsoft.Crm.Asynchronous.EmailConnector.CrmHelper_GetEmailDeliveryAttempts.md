# Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetEmailDeliveryAttempts

- ea: `0xa7d0`
- end: `0xa7f0`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetEmailDeliveryAttempts`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4e9b0`
- `0x7ab10`

## callees

- `0xa7d0`

## string_xrefs

- `0xa7d1`: `deliveryattempts`
- `0xa7de`: `deliveryattempts`

## pseudocode

```c

```

## disassembly

```asm
0xa7d0  ldarg.0
0xa7d1  ldstr    aDeliveryattemp// "deliveryattempts"
0xa7d6  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0xa7db  brfalse.s loc_A7EE
0xa7dd  ldarg.0
0xa7de  ldstr    aDeliveryattemp// "deliveryattempts"
0xa7e3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xa7e8  unbox.any [mscorlib]System.Int32
0xa7ed  ret
0xa7ee  ldc.i4.0
0xa7ef  ret
```
