# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ToAssociateResults

- ea: `0x14960`
- end: `0x1498c`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ToAssociateResults`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x23750`
- `0x23a20`
- `0x23d90`

## callees

- `0x14910`
- `0x247d0`

## pseudocode

```c

```

## disassembly

```asm
0x14960  newobj   instance void <>c__DisplayClass88_0::.ctor()
0x14965  stloc.0
0x14966  ldloc.0
0x14967  ldarg.0
0x14968  stfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <>c__DisplayClass88_0::<>4__this
0x1496d  ldloc.0
0x1496e  ldarg.2
0x1496f  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <>c__DisplayClass88_0::results
0x14974  ldarg.1
0x14975  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Messages.AssociateRequest> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ToAssociateRequests(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> links)
0x1497a  ldloc.0
0x1497b  ldftn    instance class Microsoft.Xrm.Sdk.SaveChangesResult <>c__DisplayClass88_0::<ToAssociateResults>b__0(class Microsoft.Xrm.Sdk.Messages.AssociateRequest associate)
0x14981  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.Messages.AssociateRequest, class Microsoft.Xrm.Sdk.SaveChangesResult>::.ctor(object, native int)
0x14986  call     T0x2B000055
0x1498b  ret
```
