# Microsoft.Crm.Dependency.ComponentCollector::DeleteComponentDependencies

- ea: `0x57d0`
- end: `0x5827`
- name: `Microsoft.Crm.Dependency.ComponentCollector::DeleteComponentDependencies`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5180`

## callees

- `0x57d0`
- `0x6ca0`
- `0x73a0`

## string_xrefs

- `0x57de`: `Dependency_BEGIN_{0}.ProcessRecord: IDependencyHelper.BatchDeleteDependencies`
- `0x580d`: `Dependency_END_{0}.ProcessRecord: IDependencyHelper.BatchDeleteDependencies`

## pseudocode

```c

```

## disassembly

```asm
0x57d0  ldarg.1
0x57d1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x57d6  ldc.i4.0
0x57d7  ble.s    loc_5826
0x57d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57de  ldstr    aDependencyBegi_4// "Dependency_BEGIN_{0}.ProcessRecord: IDe"...
0x57e3  ldc.i4.1
0x57e4  newarr   [mscorlib]System.Object
0x57e9  dup
0x57ea  ldc.i4.0
0x57eb  ldarg.0
0x57ec  stelem.ref
0x57ed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x57f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x57f7  call     class Microsoft.Crm.Dependency.IDependencyHelper Microsoft.Crm.Dependency.DependencyCalculatorFactory::CreateHelper()
0x57fc  ldarg.1
0x57fd  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x5802  ldarg.2
0x5803  callvirt instance void Microsoft.Crm.Dependency.IDependencyHelper::BatchDeleteDependencies(valuetype [mscorlib]System.Guid[] nodeIds, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5808  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x580d  ldstr    aDependencyEnd0_3// "Dependency_END_{0}.ProcessRecord: IDepe"...
0x5812  ldc.i4.1
0x5813  newarr   [mscorlib]System.Object
0x5818  dup
0x5819  ldc.i4.0
0x581a  ldarg.0
0x581b  stelem.ref
0x581c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5821  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x5826  ret
```
