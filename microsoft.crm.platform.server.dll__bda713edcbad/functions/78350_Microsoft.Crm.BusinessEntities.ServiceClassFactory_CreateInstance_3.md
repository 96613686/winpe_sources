# Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance_3

- ea: `0x78350`
- end: `0x78454`
- name: `Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance_3`
- size: `260`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5bc40`
- `0x5bd40`
- `0x78300`
- `0x78330`
- `0x78470`

## callees

- `0x78350`
- `0x784b0`

## string_xrefs

- `0x78372`: `Service type is not defined for the Component: {0}`
- `0x783a8`: `Service type is not derived from BusinessProcessObject: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x78350  ldnull
0x78351  stloc.0
0x78352  ldarg.0
0x78353  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasServiceClass()
0x78358  brfalse  loc_78452
0x7835d  ldarg.0
0x7835e  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ServiceType()
0x78363  stloc.1
0x78364  ldloc.1
0x78365  ldnull
0x78366  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7836b  brfalse.s loc_78391
0x7836d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x78372  ldstr    aServiceTypeIsN// "Service type is not defined for the Com"...
0x78377  ldc.i4.1
0x78378  newarr   [mscorlib]System.Object
0x7837d  dup
0x7837e  ldc.i4.0
0x7837f  ldarg.0
0x78380  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x78385  stelem.ref
0x78386  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7838b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmInvalidEntityClassException::.ctor(string)
0x78390  throw
0x78391  ldloc.1
0x78392  ldtoken  Microsoft.Crm.BusinessEntities.BusinessProcessObject
0x78397  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7839c  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x783a1  brtrue.s loc_783C7
0x783a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x783a8  ldstr    aServiceTypeIsN_0// "Service type is not derived from Busine"...
0x783ad  ldc.i4.1
0x783ae  newarr   [mscorlib]System.Object
0x783b3  dup
0x783b4  ldc.i4.0
0x783b5  ldloc.1
0x783b6  callvirt instance string [mscorlib]System.Type::get_FullName()
0x783bb  stelem.ref
0x783bc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x783c1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmInvalidEntityClassException::.ctor(string)
0x783c6  throw
0x783c7  ldarg.0
0x783c8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x783cd  brtrue.s loc_783DF
0x783cf  ldarg.0
0x783d0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x783d5  brtrue.s loc_783DF
0x783d7  ldarg.0
0x783d8  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::IsGenericActivityEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x783dd  brfalse.s loc_78400
0x783df  ldloc.1
0x783e0  ldc.i4.1
0x783e1  newarr   [mscorlib]System.Type
0x783e6  dup
0x783e7  ldc.i4.0
0x783e8  ldtoken  [mscorlib]System.String
0x783ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x783f2  stelem.ref
0x783f3  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x783f8  ldnull
0x783f9  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x783fe  brtrue.s loc_78429
0x78400  ldarg.0
0x78401  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x78406  brtrue.s loc_78446
0x78408  ldloc.1
0x78409  ldc.i4.1
0x7840a  newarr   [mscorlib]System.Type
0x7840f  dup
0x78410  ldc.i4.0
0x78411  ldtoken  [mscorlib]System.String
0x78416  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7841b  stelem.ref
0x7841c  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x78421  ldnull
0x78422  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x78427  brfalse.s loc_78446
0x78429  ldloc.1
0x7842a  ldc.i4.1
0x7842b  newarr   [mscorlib]System.Object
0x78430  dup
0x78431  ldc.i4.0
0x78432  ldarg.0
0x78433  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x78438  stelem.ref
0x78439  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x7843e  castclass Microsoft.Crm.BusinessEntities.BusinessProcessObject
0x78443  stloc.0
0x78444  br.s     loc_78452
0x78446  ldloc.1
0x78447  call     object Microsoft.Crm.BusinessEntities.ObjectFactory::CreateWithLambda(class [mscorlib]System.Type serviceType)
0x7844c  castclass Microsoft.Crm.BusinessEntities.BusinessProcessObject
0x78451  stloc.0
0x78452  ldloc.0
0x78453  ret
```
