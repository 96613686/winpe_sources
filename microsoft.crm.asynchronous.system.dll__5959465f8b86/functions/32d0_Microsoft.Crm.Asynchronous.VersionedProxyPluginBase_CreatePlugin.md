# Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::CreatePlugin

- ea: `0x32d0`
- end: `0x33b5`
- name: `Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::CreatePlugin`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2b40`
- `0x2bd0`
- `0x32d0`

## pseudocode

```c

```

## disassembly

```asm
0x32d0  ldarg.1
0x32d1  callvirt instance bool [mscorlib]System.Type::get_IsAbstract()
0x32d6  brfalse.s loc_32E9
0x32d8  ldc.i4   0x8004A201
0x32dd  ldc.i4.0
0x32de  newarr   [mscorlib]System.Object
0x32e3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x32e8  throw
0x32e9  ldnull
0x32ea  stloc.0
0x32eb  ldarg.1
0x32ec  ldc.i4.2
0x32ed  newarr   [mscorlib]System.Type
0x32f2  dup
0x32f3  ldc.i4.0
0x32f4  ldtoken  [mscorlib]System.String
0x32f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32fe  stelem.ref
0x32ff  dup
0x3300  ldc.i4.1
0x3301  ldtoken  [mscorlib]System.String
0x3306  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x330b  stelem.ref
0x330c  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x3311  dup
0x3312  stloc.0
0x3313  ldnull
0x3314  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x3319  brfalse.s loc_3343
0x331b  ldarg.2
0x331c  call     string Microsoft.Crm.Asynchronous.EventOperation::GetStepSecureConfiguration(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x3321  stloc.1
0x3322  ldarg.2
0x3323  call     string Microsoft.Crm.Asynchronous.EventOperation::GetStepConfiguration(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x3328  stloc.2
0x3329  ldloc.0
0x332a  ldc.i4.2
0x332b  newarr   [mscorlib]System.Object
0x3330  dup
0x3331  ldc.i4.0
0x3332  ldloc.2
0x3333  stelem.ref
0x3334  dup
0x3335  ldc.i4.1
0x3336  ldloc.1
0x3337  stelem.ref
0x3338  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x333d  unbox.any mvar<u1>
0x3342  ret
0x3343  ldarg.1
0x3344  ldc.i4.1
0x3345  newarr   [mscorlib]System.Type
0x334a  dup
0x334b  ldc.i4.0
0x334c  ldtoken  [mscorlib]System.String
0x3351  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3356  stelem.ref
0x3357  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x335c  dup
0x335d  stloc.0
0x335e  ldnull
0x335f  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x3364  brfalse.s loc_3383
0x3366  ldarg.2
0x3367  call     string Microsoft.Crm.Asynchronous.EventOperation::GetStepConfiguration(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x336c  stloc.3
0x336d  ldloc.0
0x336e  ldc.i4.1
0x336f  newarr   [mscorlib]System.Object
0x3374  dup
0x3375  ldc.i4.0
0x3376  ldloc.3
0x3377  stelem.ref
0x3378  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x337d  unbox.any mvar<u1>
0x3382  ret
0x3383  ldarg.1
0x3384  ldsfld   class [mscorlib]System.Type[] [mscorlib]System.Type::EmptyTypes
0x3389  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x338e  stloc.0
0x338f  ldloc.0
0x3390  ldnull
0x3391  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Equality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x3396  brfalse.s loc_33A9
0x3398  ldc.i4   0x8004A201
0x339d  ldc.i4.0
0x339e  newarr   [mscorlib]System.Object
0x33a3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x33a8  throw
0x33a9  ldarg.1
0x33aa  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x33af  unbox.any mvar<u1>
0x33b4  ret
```
