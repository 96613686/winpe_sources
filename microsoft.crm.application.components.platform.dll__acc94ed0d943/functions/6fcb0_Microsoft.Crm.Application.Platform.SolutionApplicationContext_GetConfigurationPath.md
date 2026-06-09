# Microsoft.Crm.Application.Platform.SolutionApplicationContext::GetConfigurationPath

- ea: `0x6fcb0`
- end: `0x6fd16`
- name: `Microsoft.Crm.Application.Platform.SolutionApplicationContext::GetConfigurationPath`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2fb90`
- `0x30e70`
- `0x59710`
- `0x5be20`
- `0x5be50`
- `0x6fcb0`
- `0x6fd20`

## string_xrefs

- `0x6fcd6`: `configurationpageid`
- `0x6fce8`: `configurationpageid`
- `0x6fcf5`: `configurationpageid`

## pseudocode

```c

```

## disassembly

```asm
0x6fcb0  ldarg.0
0x6fcb1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6fcb6  brfalse.s loc_6FCC0
0x6fcb8  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x6fcbd  stloc.0
0x6fcbe  br.s     loc_6FCC8
0x6fcc0  ldloca.s 0
0x6fcc2  ldarg.0
0x6fcc3  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6fcc8  ldstr    aSolution_0// "solution"
0x6fccd  ldloc.0
0x6fcce  ldc.i4.1
0x6fccf  newarr   [mscorlib]System.String
0x6fcd4  dup
0x6fcd5  ldc.i4.0
0x6fcd6  ldstr    aConfigurationp// "configurationpageid"
0x6fcdb  stelem.ref
0x6fcdc  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6fce1  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6fce6  stloc.1
0x6fce7  ldloc.1
0x6fce8  ldstr    aConfigurationp// "configurationpageid"
0x6fced  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string name)
0x6fcf2  brfalse.s loc_6FD14
0x6fcf4  ldloc.1
0x6fcf5  ldstr    aConfigurationp// "configurationpageid"
0x6fcfa  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6fcff  castclass Microsoft.Crm.Application.Types.LookupValue
0x6fd04  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x6fd09  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6fd0e  call     string Microsoft.Crm.Application.Platform.SolutionApplicationContext::GetConfigurationPathById(valuetype [mscorlib]System.Guid configurationPageId)
0x6fd13  ret
0x6fd14  ldnull
0x6fd15  ret
```
