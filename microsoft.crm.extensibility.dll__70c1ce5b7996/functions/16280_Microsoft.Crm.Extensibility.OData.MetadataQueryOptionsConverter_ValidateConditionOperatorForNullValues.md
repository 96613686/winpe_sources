# Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateConditionOperatorForNullValues

- ea: `0x16280`
- end: `0x162a7`
- name: `Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateConditionOperatorForNullValues`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x161a0`

## callees

- `0x16280`

## string_xrefs

- `0x1628c`: `The right side of the "{0}" operator can't be NULL.`

## pseudocode

```c

```

## disassembly

```asm
0x16280  ldarg.1
0x16281  brfalse.s loc_162A6
0x16283  ldarg.1
0x16284  ldc.i4.1
0x16285  beq.s    loc_162A6
0x16287  ldc.i4   0x190
0x1628c  ldstr    aTheRightSideOf_0// "The right side of the \"{0}\" operator "...
0x16291  ldc.i4.1
0x16292  newarr   [mscorlib]System.Object
0x16297  dup
0x16298  ldc.i4.0
0x16299  ldarg.2
0x1629a  box      [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind
0x1629f  stelem.ref
0x162a0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x162a5  throw
0x162a6  ret
```
