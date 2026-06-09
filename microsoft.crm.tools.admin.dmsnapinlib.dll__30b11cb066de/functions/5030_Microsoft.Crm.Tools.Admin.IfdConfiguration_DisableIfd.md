# Microsoft.Crm.Tools.Admin.IfdConfiguration::DisableIfd

- ea: `0x5030`
- end: `0x5114`
- name: `Microsoft.Crm.Tools.Admin.IfdConfiguration::DisableIfd`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5030`

## string_xrefs

- `0x5089`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Ifd\IfdConfigurator.cs`
- `0x50f2`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Ifd\IfdConfigurator.cs`

## pseudocode

```c

```

## disassembly

```asm
0x5030  ldc.i4.5
0x5031  newarr   [mscorlib]System.String
0x5036  dup
0x5037  ldc.i4.0
0x5038  ldstr    aIfdrootdomains// "IfdRootDomainScheme"
0x503d  stelem.ref
0x503e  dup
0x503f  ldc.i4.1
0x5040  ldstr    aIfdsdkrootdoma_0// "IfdSdkRootDomain"
0x5045  stelem.ref
0x5046  dup
0x5047  ldc.i4.2
0x5048  ldstr    aIfdwebapplicat_0// "IfdWebApplicationRootDomain"
0x504d  stelem.ref
0x504e  dup
0x504f  ldc.i4.3
0x5050  ldstr    aIfddiscoveryro_0// "IfdDiscoveryRootDomain"
0x5055  stelem.ref
0x5056  dup
0x5057  ldc.i4.4
0x5058  ldstr    aIfdenabled// "IfdEnabled"
0x505d  stelem.ref
0x505e  stloc.0
0x505f  ldnull
0x5060  stloc.1
0x5061  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x5066  stloc.2
0x5067  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x506c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentId()
0x5071  stloc.3
0x5072  ldloc.2
0x5073  ldstr    aDeployment// "Deployment"
0x5078  ldloc.3
0x5079  box      [mscorlib]System.Guid
0x507e  ldloc.0
0x507f  ldc.i4   0x94
0x5084  ldstr    aDisableifd// "DisableIfd"
0x5089  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x508e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x5093  stloc.1
0x5094  ldloc.1
0x5095  ldloc.0
0x5096  ldc.i4.0
0x5097  ldelem.ref
0x5098  ldstr    asc_1E310// ""
0x509d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x50a2  ldloc.1
0x50a3  ldloc.0
0x50a4  ldc.i4.1
0x50a5  ldelem.ref
0x50a6  ldstr    asc_1E310// ""
0x50ab  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x50b0  ldloc.1
0x50b1  ldloc.0
0x50b2  ldc.i4.2
0x50b3  ldelem.ref
0x50b4  ldstr    asc_1E310// ""
0x50b9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x50be  ldloc.1
0x50bf  ldloc.0
0x50c0  ldc.i4.3
0x50c1  ldelem.ref
0x50c2  ldstr    asc_1E310// ""
0x50c7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x50cc  ldloc.1
0x50cd  ldloc.0
0x50ce  ldc.i4.4
0x50cf  ldelem.ref
0x50d0  ldc.i4.0
0x50d1  box      [mscorlib]System.Boolean
0x50d6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x50db  ldloc.2
0x50dc  ldstr    aDeployment// "Deployment"
0x50e1  ldloc.3
0x50e2  box      [mscorlib]System.Guid
0x50e7  ldloc.1
0x50e8  ldc.i4   0xA0
0x50ed  ldstr    aDisableifd// "DisableIfd"
0x50f2  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x50f7  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x50fc  pop
0x50fd  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x5102  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x5107  leave.s  loc_5113
0x5109  ldloc.2
0x510a  brfalse.s loc_5112
0x510c  ldloc.2
0x510d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5112  endfinally
0x5113  ret
```
