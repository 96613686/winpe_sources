# Microsoft.Xrm.Sdk.Linq.QueryProvider::CreateQuery

- ea: `0xade0`
- end: `0xae0a`
- name: `Microsoft.Xrm.Sdk.Linq.QueryProvider::CreateQuery`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xd870`

## callees

- `0x4e40`
- `0x4e80`
- `0xaee0`
- `0xaf20`

## pseudocode

```c

```

## disassembly

```asm
0xade0  ldarg.0
0xade1  ldarg.1
0xade2  call     instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::CheckEntitySubclass(class [mscorlib]System.Type entityType)
0xade7  ldc.i4.1
0xade8  call     class Microsoft.Xrm.Sdk.KnownProxyTypesProvider Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetInstance(bool supportIndividualAssemblies)
0xaded  ldarg.1
0xadee  callvirt instance string Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetNameForType(class [mscorlib]System.Type type)
0xadf3  stloc.0
0xadf4  ldarg.0
0xadf5  ldarg.1
0xadf6  ldc.i4.2
0xadf7  newarr   [mscorlib]System.Object
0xadfc  dup
0xadfd  ldc.i4.0
0xadfe  ldarg.0
0xadff  stelem.ref
0xae00  dup
0xae01  ldc.i4.1
0xae02  ldloc.0
0xae03  stelem.ref
0xae04  call     instance class [System.Core]System.Linq.IQueryable Microsoft.Xrm.Sdk.Linq.QueryProvider::CreateQueryInstance(class [mscorlib]System.Type elementType, object[] args)
0xae09  ret
```
