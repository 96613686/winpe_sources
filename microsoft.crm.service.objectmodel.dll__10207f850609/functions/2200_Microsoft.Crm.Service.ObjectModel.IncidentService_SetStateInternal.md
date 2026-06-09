# Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateInternal

- ea: `0x2200`
- end: `0x2274`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateInternal`
- size: `116`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x2000`
- `0x2160`
- `0x2bc0`
- `0x2c00`

## callees

- `0x11d0`
- `0x1460`
- `0x18b0`
- `0x18f0`
- `0x1930`
- `0x2200`

## pseudocode

```c

```

## disassembly

```asm
0x2200  ldarg.0
0x2201  ldarg.s  4
0x2203  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::IsServiceRefreshEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context)
0x2208  brfalse.s loc_2268
0x220a  ldarg.0
0x220b  ldarg.s  4
0x220d  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::HasServiceStage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2212  brfalse.s loc_2268
0x2214  ldarg.2
0x2215  switch   loc_2228, loc_2233, loc_2233
0x2226  br.s     loc_223E
0x2228  ldarg.0
0x2229  ldarg.s  4
0x222b  call     instance int32 Microsoft.Crm.Service.ObjectModel.IncidentService::GetFirstServiceStage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2230  stloc.0
0x2231  br.s     loc_2259
0x2233  ldarg.0
0x2234  ldarg.s  4
0x2236  call     instance int32 Microsoft.Crm.Service.ObjectModel.IncidentService::GetLastServiceStage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x223b  stloc.0
0x223c  br.s     loc_2259
0x223e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2243  ldstr    aTheTargetState// "The target state is invalid.  The targe"...
0x2248  ldc.i4.0
0x2249  newarr   [mscorlib]System.Object
0x224e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2253  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x2258  throw
0x2259  ldarg.0
0x225a  ldarg.1
0x225b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x2260  ldloc.0
0x2261  ldarg.s  4
0x2263  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::UpdateIncidentStage(valuetype [mscorlib]System.Guid incidentId, int32 serviceStage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2268  ldarg.0
0x2269  ldarg.1
0x226a  ldarg.2
0x226b  ldarg.3
0x226c  ldarg.s  4
0x226e  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2273  ret
```
