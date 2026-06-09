# Microsoft.Crm.ScaleGroupApi.Controllers.ImportSolutionGroupIdCreator::CreateGroupIdForOrganization

- ea: `0x46a0`
- end: `0x46f0`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.ImportSolutionGroupIdCreator::CreateGroupIdForOrganization`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3dd0`

## callees

- `0x46a0`

## pseudocode

```c

```

## disassembly

```asm
0x46a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x46a5  ldstr    aMaxconcurrenti// "MaxConcurrentImportSolutionQueueItems"
0x46aa  ldc.i4.0
0x46ab  callvirt T0x2B000025
0x46b0  stloc.0
0x46b1  ldstr    aOrganizationim// "OrganizationImportSolution"
0x46b6  stloc.1
0x46b7  ldloca.s 0
0x46b9  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x46be  brfalse.s loc_46EE
0x46c0  ldloca.s 0
0x46c2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x46c7  stloc.2
0x46c8  ldloc.2
0x46c9  ldc.i4.0
0x46ca  bgt.s    loc_46CE
0x46cc  ldc.i4.1
0x46cd  stloc.2
0x46ce  ldloc.1
0x46cf  ldstr    asc_7A3A// "_"
0x46d4  ldarga.s 0
0x46d6  constrained. [mscorlib]System.Guid
0x46dc  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x46e1  ldloc.2
0x46e2  rem.un
0x46e3  box      [mscorlib]System.UInt32
0x46e8  call     string [mscorlib]System.String::Concat(object, object, object)
0x46ed  stloc.1
0x46ee  ldloc.1
0x46ef  ret
```
