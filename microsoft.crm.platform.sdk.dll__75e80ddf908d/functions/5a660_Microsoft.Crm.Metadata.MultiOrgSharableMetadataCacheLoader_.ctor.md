# Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::.ctor

- ea: `0x5a660`
- end: `0x5a7a5`
- name: `Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::.ctor`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x50db0`

## callees

- `0x50d70`

## string_xrefs

- `0x5a666`: `where (SolutionId = '{0}' and ComponentState = 0) or (SolutionId <> '{0}' and OverwriteTime = {1} and ComponentState in ({2}, {3}))`
- `0x5a6a9`: `where SolutionId <> '{0}' and OverwriteTime = {1} and ComponentState in ({2}, {3})`
- `0x5a6ec`: `where (SolutionId = '{0}' and ComponentState = 0)`
- `0x5a72f`: `where SolutionId <> '{0}' and OverwriteTime = {1} and ComponentState = {2}`
- `0x5a769`: `where SolutionId <> '{0}' and OverwriteTime = {1} and ComponentState = {2}`

## pseudocode

```c

```

## disassembly

```asm
0x5a660  ldarg.0
0x5a661  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a666  ldstr    aWhereSolutioni// "where (SolutionId = '{0}' and Component"...
0x5a66b  ldc.i4.4
0x5a66c  newarr   [mscorlib]System.Object
0x5a671  dup
0x5a672  ldc.i4.0
0x5a673  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5a678  box      [mscorlib]System.Guid
0x5a67d  stelem.ref
0x5a67e  dup
0x5a67f  ldc.i4.1
0x5a680  ldc.i4.0
0x5a681  box      [mscorlib]System.Int32
0x5a686  stelem.ref
0x5a687  dup
0x5a688  ldc.i4.2
0x5a689  ldc.i4.0
0x5a68a  box      [mscorlib]System.Int32
0x5a68f  stelem.ref
0x5a690  dup
0x5a691  ldc.i4.3
0x5a692  ldc.i4.2
0x5a693  box      [mscorlib]System.Int32
0x5a698  stelem.ref
0x5a699  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a69e  stfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionWithSystemRows
0x5a6a3  ldarg.0
0x5a6a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a6a9  ldstr    aWhereSolutioni_0// "where SolutionId <> '{0}' and Overwrite"...
0x5a6ae  ldc.i4.4
0x5a6af  newarr   [mscorlib]System.Object
0x5a6b4  dup
0x5a6b5  ldc.i4.0
0x5a6b6  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5a6bb  box      [mscorlib]System.Guid
0x5a6c0  stelem.ref
0x5a6c1  dup
0x5a6c2  ldc.i4.1
0x5a6c3  ldc.i4.0
0x5a6c4  box      [mscorlib]System.Int32
0x5a6c9  stelem.ref
0x5a6ca  dup
0x5a6cb  ldc.i4.2
0x5a6cc  ldc.i4.0
0x5a6cd  box      [mscorlib]System.Int32
0x5a6d2  stelem.ref
0x5a6d3  dup
0x5a6d4  ldc.i4.3
0x5a6d5  ldc.i4.2
0x5a6d6  box      [mscorlib]System.Int32
0x5a6db  stelem.ref
0x5a6dc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a6e1  stfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionNoSystemRows
0x5a6e6  ldarg.0
0x5a6e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a6ec  ldstr    aWhereSolutioni_1// "where (SolutionId = '{0}' and Component"...
0x5a6f1  ldc.i4.4
0x5a6f2  newarr   [mscorlib]System.Object
0x5a6f7  dup
0x5a6f8  ldc.i4.0
0x5a6f9  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5a6fe  box      [mscorlib]System.Guid
0x5a703  stelem.ref
0x5a704  dup
0x5a705  ldc.i4.1
0x5a706  ldc.i4.0
0x5a707  box      [mscorlib]System.Int32
0x5a70c  stelem.ref
0x5a70d  dup
0x5a70e  ldc.i4.2
0x5a70f  ldc.i4.0
0x5a710  box      [mscorlib]System.Int32
0x5a715  stelem.ref
0x5a716  dup
0x5a717  ldc.i4.3
0x5a718  ldc.i4.2
0x5a719  box      [mscorlib]System.Int32
0x5a71e  stelem.ref
0x5a71f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a724  stfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionOnlySystemRows
0x5a729  ldarg.0
0x5a72a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a72f  ldstr    aWhereSolutioni_2// "where SolutionId <> '{0}' and Overwrite"...
0x5a734  ldc.i4.3
0x5a735  newarr   [mscorlib]System.Object
0x5a73a  dup
0x5a73b  ldc.i4.0
0x5a73c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5a741  box      [mscorlib]System.Guid
0x5a746  stelem.ref
0x5a747  dup
0x5a748  ldc.i4.1
0x5a749  ldc.i4.0
0x5a74a  box      [mscorlib]System.Int32
0x5a74f  stelem.ref
0x5a750  dup
0x5a751  ldc.i4.2
0x5a752  ldc.i4.0
0x5a753  box      [mscorlib]System.Int32
0x5a758  stelem.ref
0x5a759  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a75e  stfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionOnlyPublishedNoSystemRows
0x5a763  ldarg.0
0x5a764  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a769  ldstr    aWhereSolutioni_2// "where SolutionId <> '{0}' and Overwrite"...
0x5a76e  ldc.i4.3
0x5a76f  newarr   [mscorlib]System.Object
0x5a774  dup
0x5a775  ldc.i4.0
0x5a776  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5a77b  box      [mscorlib]System.Guid
0x5a780  stelem.ref
0x5a781  dup
0x5a782  ldc.i4.1
0x5a783  ldc.i4.0
0x5a784  box      [mscorlib]System.Int32
0x5a789  stelem.ref
0x5a78a  dup
0x5a78b  ldc.i4.2
0x5a78c  ldc.i4.2
0x5a78d  box      [mscorlib]System.Int32
0x5a792  stelem.ref
0x5a793  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a798  stfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionOnlyDeletedNoSystemRows
0x5a79d  ldarg.0
0x5a79e  ldarg.1
0x5a79f  call     instance void Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x5a7a4  ret
```
