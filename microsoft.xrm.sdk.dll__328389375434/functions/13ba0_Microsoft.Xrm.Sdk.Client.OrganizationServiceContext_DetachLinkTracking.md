# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking

- ea: `0x13ba0`
- end: `0x13bce`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking`
- size: `46`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x135a0`
- `0x13bd0`
- `0x13f80`
- `0x14110`
- `0x141d0`
- `0x14840`

## callees

- `0x3890`
- `0x3930`
- `0x3950`
- `0x3970`
- `0x13ba0`
- `0x15290`

## pseudocode

```c

```

## disassembly

```asm
0x13ba0  ldarg.1
0x13ba1  ldc.i4.1
0x13ba2  callvirt instance void Microsoft.Xrm.Sdk.Descriptor::set_State(valuetype Microsoft.Xrm.Sdk.EntityStates value)
0x13ba7  ldarg.0
0x13ba8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x13bad  ldarg.1
0x13bae  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::Remove(var<u1>)
0x13bb3  brfalse.s loc_13BCD
0x13bb5  ldarg.0
0x13bb6  ldarg.1
0x13bb7  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x13bbc  ldarg.1
0x13bbd  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x13bc2  ldarg.1
0x13bc3  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x13bc8  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnEndLinkTracking(class Microsoft.Xrm.Sdk.Entity entity, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13bcd  ret
```
