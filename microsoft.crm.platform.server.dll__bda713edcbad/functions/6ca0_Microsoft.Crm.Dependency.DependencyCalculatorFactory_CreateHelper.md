# Microsoft.Crm.Dependency.DependencyCalculatorFactory::CreateHelper

- ea: `0x6ca0`
- end: `0x6d0f`
- name: `Microsoft.Crm.Dependency.DependencyCalculatorFactory::CreateHelper`
- size: `111`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5580`
- `0x57d0`
- `0x5830`
- `0x5970`
- `0x6e70`
- `0x71c0`

## callees

- `0x6ca0`

## string_xrefs

- `0x6ccd`: `Microsoft.Crm.ObjectModel.CombinedDependencyHelper`
- `0x6cf0`: `Microsoft.Crm.ObjectModel.CombinedDependencyHelper`

## pseudocode

```c

```

## disassembly

```asm
0x6ca0  ldsfld   class Microsoft.Crm.Dependency.IDependencyHelper Microsoft.Crm.Dependency.DependencyCalculatorFactory::CombinedDependencyHelperReference
0x6ca5  brtrue.s loc_6D09
0x6ca7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6cac  ldc.i4.s 0x14
0x6cae  ldstr    a0// "{0}"
0x6cb3  ldc.i4.1
0x6cb4  newarr   [mscorlib]System.Object
0x6cb9  dup
0x6cba  ldc.i4.0
0x6cbb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cc0  ldstr    aCreatingIdepen_0// "Creating IDependencyHelper({0}) from {1"...
0x6cc5  ldc.i4.2
0x6cc6  newarr   [mscorlib]System.Object
0x6ccb  dup
0x6ccc  ldc.i4.0
0x6ccd  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel.CombinedDepen"...
0x6cd2  stelem.ref
0x6cd3  dup
0x6cd4  ldc.i4.1
0x6cd5  ldstr    aMicrosoftCrmOb_0// "Microsoft.Crm.ObjectModel"
0x6cda  stelem.ref
0x6cdb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6ce0  stelem.ref
0x6ce1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ce6  ldstr    aMicrosoftCrmOb_0// "Microsoft.Crm.ObjectModel"
0x6ceb  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x6cf0  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel.CombinedDepen"...
0x6cf5  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x6cfa  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x6cff  castclass Microsoft.Crm.Dependency.IDependencyHelper
0x6d04  stsfld   class Microsoft.Crm.Dependency.IDependencyHelper Microsoft.Crm.Dependency.DependencyCalculatorFactory::CombinedDependencyHelperReference
0x6d09  ldsfld   class Microsoft.Crm.Dependency.IDependencyHelper Microsoft.Crm.Dependency.DependencyCalculatorFactory::CombinedDependencyHelperReference
0x6d0e  ret
```
