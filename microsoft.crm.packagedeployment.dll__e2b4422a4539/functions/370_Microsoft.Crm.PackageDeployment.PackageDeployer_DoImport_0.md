# Microsoft.Crm.PackageDeployment.PackageDeployer::DoImport_0

- ea: `0x370`
- end: `0x3f1`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployer::DoImport_0`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x360`

## callees

- `0x340`
- `0x370`
- `0x400`
- `0x450`
- `0x520`
- `0x540`
- `0x550`
- `0x6b0`
- `0x1230`
- `0x1470`

## pseudocode

```c

```

## disassembly

```asm
0x370  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x375  dup
0x376  ldarg.0
0x377  stfld    class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase <>c__DisplayClass7_0::wrapper
0x37c  ldftn    instance class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase <>c__DisplayClass7_0::<DoImport>b__0()
0x382  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::.ctor(object, native int)
0x387  newobj   instance void class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x38c  stsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x391  call     bool Microsoft.Crm.PackageDeployment.PackageDeployer::get_OnlyUseOneInstance()
0x396  brfalse.s loc_39D
0x398  call     void Microsoft.Crm.PackageDeployment.PackageDeployer::AcquireInstance()
0x39d  nop
0x39e  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x3a3  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::get_Value()
0x3a8  callvirt instance class Microsoft.Crm.PackageDeployment.PackageDeployerImportResult Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DoImport()
0x3ad  stloc.0
0x3ae  leave.s  loc_3EF
0x3b0  stloc.1
0x3b1  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::.ctor()
0x3b6  dup
0x3b7  ldloc.1
0x3b8  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::set_Exception(class [mscorlib]System.Exception value)
0x3bd  dup
0x3be  ldc.i4.0
0x3bf  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportResult::set_Successful(bool value)
0x3c4  stloc.0
0x3c5  leave.s  loc_3EF
0x3c7  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x3cc  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::get_Value()
0x3d1  brfalse.s loc_3E2
0x3d3  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x3d8  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::get_Value()
0x3dd  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::Dispose()
0x3e2  call     bool Microsoft.Crm.PackageDeployment.PackageDeployer::get_OnlyUseOneInstance()
0x3e7  brfalse.s loc_3EE
0x3e9  call     void Microsoft.Crm.PackageDeployment.PackageDeployer::ReleaseInstance()
0x3ee  endfinally
0x3ef  ldloc.0
0x3f0  ret
```
