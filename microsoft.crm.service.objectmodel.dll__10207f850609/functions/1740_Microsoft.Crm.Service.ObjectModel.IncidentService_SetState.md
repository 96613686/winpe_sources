# Microsoft.Crm.Service.ObjectModel.IncidentService::SetState

- ea: `0x1740`
- end: `0x1803`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::SetState`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1740`
- `0x1e90`
- `0x2000`
- `0x2160`

## pseudocode

```c

```

## disassembly

```asm
0x1740  ldarg.2
0x1741  switch   loc_1754, loc_176E, loc_1761
0x1752  br.s     loc_1789
0x1754  ldarg.0
0x1755  ldarg.1
0x1756  ldarg.3
0x1757  ldarg.s  4
0x1759  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::Open(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x175e  pop
0x175f  br.s     loc_17A4
0x1761  ldarg.0
0x1762  ldarg.1
0x1763  ldarg.3
0x1764  ldarg.s  4
0x1766  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::Cancel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x176b  pop
0x176c  br.s     loc_17A4
0x176e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1773  ldstr    aThisMessageCan// "This message can not be used to set the"...
0x1778  ldc.i4.0
0x1779  newarr   [mscorlib]System.Object
0x177e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1783  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x1788  throw
0x1789  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x178e  ldstr    aTheTargetState// "The target state is invalid.  The targe"...
0x1793  ldc.i4.0
0x1794  newarr   [mscorlib]System.Object
0x1799  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x179e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x17a3  throw
0x17a4  ldarg.0
0x17a5  ldarg.1
0x17a6  ldnull
0x17a7  ldarg.2
0x17a8  ldarg.3
0x17a9  ldarg.s  4
0x17ab  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::PerformCascadeUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x17b0  ldc.i4.1
0x17b1  stloc.0
0x17b2  leave.s  loc_1801
0x17b4  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17b9  ldc.i4   0x8004F00E
0x17be  bne.un.s loc_17FF
0x17c0  ldarg.s  4
0x17c2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x17c7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::get_Request()
0x17cc  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x17d1  ldstr    aMerge// "Merge"
0x17d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17db  brfalse.s loc_17EE
0x17dd  ldc.i4   0x8004F457
0x17e2  ldc.i4.0
0x17e3  newarr   [mscorlib]System.Object
0x17e8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x17ed  throw
0x17ee  ldc.i4   0x8006074
0x17f3  ldc.i4.0
0x17f4  newarr   [mscorlib]System.Object
0x17f9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x17fe  throw
0x17ff  rethrow
0x1801  ldloc.0
0x1802  ret
```
