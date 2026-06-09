# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking_0

- ea: `0x13ab0`
- end: `0x13af1`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachLinkTracking_0`
- size: `65`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x136e0`
- `0x13a40`
- `0x13be0`
- `0x13c70`

## callees

- `0x3930`
- `0x3950`
- `0x3970`
- `0x13830`
- `0x13ab0`
- `0x15280`

## pseudocode

```c

```

## disassembly

```asm
0x13ab0  ldarg.0
0x13ab1  ldarg.1
0x13ab2  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x13ab7  ldarg.1
0x13ab8  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x13abd  ldarg.1
0x13abe  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x13ac3  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13ac8  brfalse.s loc_13ACB
0x13aca  ret
0x13acb  ldarg.0
0x13acc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x13ad1  ldarg.1
0x13ad2  ldarg.1
0x13ad3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::Add(var<u1>, !!T0)
0x13ad8  ldarg.0
0x13ad9  ldarg.1
0x13ada  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x13adf  ldarg.1
0x13ae0  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x13ae5  ldarg.1
0x13ae6  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x13aeb  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnBeginLinkTracking(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13af0  ret
```
