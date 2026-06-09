# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks

- ea: `0x15040`
- end: `0x1506a`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks`
- size: `42`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x135a0`
- `0x13dd0`
- `0x141d0`
- `0x14760`

## callees

- `0x24bc0`

## pseudocode

```c

```

## disassembly

```asm
0x15040  newobj   instance void <>c__DisplayClass103_0::.ctor()
0x15045  stloc.0
0x15046  ldloc.0
0x15047  ldarg.1
0x15048  stfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass103_0::target
0x1504d  ldarg.0
0x1504e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x15053  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Values()
0x15058  ldloc.0
0x15059  ldftn    instance bool <>c__DisplayClass103_0::<GetTargetingLinks>b__0(class Microsoft.Xrm.Sdk.LinkDescriptor b)
0x1505f  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.LinkDescriptor, bool>::.ctor(object, native int)
0x15064  call     T0x2B00005B
0x15069  ret
```
