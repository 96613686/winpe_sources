# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::Clone

- ea: `0x18640`
- end: `0x18669`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::Clone`
- size: `41`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1a840`
- `0x1a9c0`
- `0x1ad90`
- `0x1f610`
- `0x23200`
- `0x23a40`

## callees

- `0x17dc0`
- `0x185d0`
- `0x185e0`
- `0x18640`

## pseudocode

```c

```

## disassembly

```asm
0x18640  ldarg.0
0x18641  call     instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::Clone()
0x18646  isinst   Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper
0x1864b  stloc.0
0x1864c  ldarg.0
0x1864d  callvirt instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x18652  isinst   [mscorlib]System.ICloneable
0x18657  stloc.1
0x18658  ldloc.1
0x18659  brfalse.s loc_18667
0x1865b  ldloc.0
0x1865c  ldloc.1
0x1865d  callvirt instance object [mscorlib]System.ICloneable::Clone()
0x18662  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object value)
0x18667  ldloc.0
0x18668  ret
```
