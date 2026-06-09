# Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::VerifyStrongName

- ea: `0x157d0`
- end: `0x15857`
- name: `Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::VerifyStrongName`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x153e0`

## callees

- `0x157d0`

## string_xrefs

- `0x15805`: `' as the CrmScalegroupProvisioningService is strongly signed but the executable is not.`
- `0x15846`: `' as the CrmScalegroupProvisioningService and the executable have different public keys`

## pseudocode

```c

```

## disassembly

```asm
0x157d0  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x157d5  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x157da  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKey()
0x157df  stloc.0
0x157e0  ldloc.0
0x157e1  brfalse.s loc_15856
0x157e3  ldloc.0
0x157e4  ldlen
0x157e5  brfalse.s loc_15856
0x157e7  ldarg.0
0x157e8  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::ReflectionOnlyLoadFrom(string)
0x157ed  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x157f2  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKey()
0x157f7  stloc.1
0x157f8  ldloc.1
0x157f9  brfalse.s loc_157FF
0x157fb  ldloc.1
0x157fc  ldlen
0x157fd  brtrue.s loc_15815
0x157ff  ldstr    aCouldNotExecut// "Could not execute '"
0x15804  ldarg.0
0x15805  ldstr    aAsTheCrmscaleg// "' as the CrmScalegroupProvisioningServi"...
0x1580a  call     string [mscorlib]System.String::Concat(string, string, string)
0x1580f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x15814  throw
0x15815  ldc.i4.1
0x15816  stloc.2
0x15817  ldloc.0
0x15818  ldlen
0x15819  conv.i4
0x1581a  ldloc.1
0x1581b  ldlen
0x1581c  conv.i4
0x1581d  beq.s    loc_15823
0x1581f  ldc.i4.0
0x15820  stloc.2
0x15821  br.s     loc_1583D
0x15823  ldc.i4.0
0x15824  stloc.3
0x15825  br.s     loc_15837
0x15827  ldloc.0
0x15828  ldloc.3
0x15829  ldelem.u1
0x1582a  ldloc.1
0x1582b  ldloc.3
0x1582c  ldelem.u1
0x1582d  beq.s    loc_15833
0x1582f  ldc.i4.0
0x15830  stloc.2
0x15831  br.s     loc_1583D
0x15833  ldloc.3
0x15834  ldc.i4.1
0x15835  add
0x15836  stloc.3
0x15837  ldloc.3
0x15838  ldloc.0
0x15839  ldlen
0x1583a  conv.i4
0x1583b  blt.s    loc_15827
0x1583d  ldloc.2
0x1583e  brtrue.s loc_15856
0x15840  ldstr    aCouldNotExecut// "Could not execute '"
0x15845  ldarg.0
0x15846  ldstr    aAsTheCrmscaleg_0// "' as the CrmScalegroupProvisioningServi"...
0x1584b  call     string [mscorlib]System.String::Concat(string, string, string)
0x15850  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x15855  throw
0x15856  ret
```
