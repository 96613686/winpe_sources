# Microsoft.Crm.Extensibility.ExecuteTransactionProcessor::ThrowIfAnyRequestUnsupported

- ea: `0x5660`
- end: `0x5693`
- name: `Microsoft.Crm.Extensibility.ExecuteTransactionProcessor::ThrowIfAnyRequestUnsupported`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5430`

## callees

- `0x5660`

## string_xrefs

- `0x5687`: `ExecuteMultiple or ExecuteTransaction Requests cannot be executed inside another ExecuteTransaction request!`

## pseudocode

```c

```

## disassembly

```asm
0x5660  ldarg.0
0x5661  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest, bool> <>c::<>9__3_0
0x5666  dup
0x5667  brtrue.s loc_5680
0x5669  pop
0x566a  ldsfld   class <>c <>c::<>9
0x566f  ldftn    instance bool <>c::<ThrowIfAnyRequestUnsupported>b__3_0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest r)
0x5675  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest, bool>::.ctor(object, native int)
0x567a  dup
0x567b  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest, bool> <>c::<>9__3_0
0x5680  call     T0x2B00002C
0x5685  brfalse.s loc_5692
0x5687  ldstr    aExecutemultipl_2// "ExecuteMultiple or ExecuteTransaction R"...
0x568c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x5691  throw
0x5692  ret
```
