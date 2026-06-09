# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached

- ea: `0x137e0`
- end: `0x137fb`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached`
- size: `27`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x13970`
- `0x14760`
- `0x152a0`
- `0x23220`

## callees

- `0x137e0`

## pseudocode

```c

```

## disassembly

```asm
0x137e0  ldarg.1
0x137e1  brtrue.s loc_137EE
0x137e3  ldstr    aEntity// "entity"
0x137e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x137ed  throw
0x137ee  ldarg.0
0x137ef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x137f4  ldarg.1
0x137f5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::ContainsKey(var<u1>)
0x137fa  ret
```
