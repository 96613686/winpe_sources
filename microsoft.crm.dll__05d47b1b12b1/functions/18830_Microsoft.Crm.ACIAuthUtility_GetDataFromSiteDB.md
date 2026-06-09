# Microsoft.Crm.ACIAuthUtility::GetDataFromSiteDB

- ea: `0x18830`
- end: `0x188f7`
- name: `Microsoft.Crm.ACIAuthUtility::GetDataFromSiteDB`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18790`

## callees

- `0x18830`

## string_xrefs

- `0x1883a`: `GetDataFromSiteDB`

## pseudocode

```c

```

## disassembly

```asm
0x18830  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x18835  ldarg.0
0x18836  ldarg.1
0x18837  ldarg.2
0x18838  ldc.i4.s 0x64
0x1883a  ldstr    aGetdatafromsit// "GetDataFromSiteDB"
0x1883f  ldstr    aDA1SSrcSharedS// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x18844  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x18849  stloc.0
0x1884a  ldloc.0
0x1884b  brfalse.s loc_1889D
0x1884d  ldloc.0
0x1884e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Count()
0x18853  ldarg.1
0x18854  ldlen
0x18855  conv.i4
0x18856  bge.s    loc_18869
0x18858  ldstr    aQueryForProper// "Query for PropertyBagCollection for tab"...
0x1885d  ldarg.0
0x1885e  call     string [mscorlib]System.String::Format(string, object)
0x18863  newobj   instance void [mscorlib]System.NullReferenceException::.ctor(string)
0x18868  throw
0x18869  ldarg.1
0x1886a  stloc.1
0x1886b  ldc.i4.0
0x1886c  stloc.2
0x1886d  br.s     loc_18892
0x1886f  ldloc.1
0x18870  ldloc.2
0x18871  ldelem.ref
0x18872  stloc.3
0x18873  ldloc.0
0x18874  ldloc.3
0x18875  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x1887a  brtrue.s loc_1888E
0x1887c  ldstr    aPropertybagcol// "PropertyBagCollection doesn't contain t"...
0x18881  ldloc.3
0x18882  ldarg.0
0x18883  call     string [mscorlib]System.String::Format(string, object, object)
0x18888  newobj   instance void [mscorlib]System.NullReferenceException::.ctor(string)
0x1888d  throw
0x1888e  ldloc.2
0x1888f  ldc.i4.1
0x18890  add
0x18891  stloc.2
0x18892  ldloc.2
0x18893  ldloc.1
0x18894  ldlen
0x18895  conv.i4
0x18896  blt.s    loc_1886F
0x18898  ldloc.0
0x18899  stloc.s  4
0x1889b  leave.s  loc_188F4
0x1889d  leave.s  loc_188F2
0x1889f  stloc.s  5
0x188a1  ldloc.s  5
0x188a3  ldarg.3
0x188a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x188a9  ldc.i4.s 0x14
0x188ab  ldstr    aErrorHappenedF// "Error happened fetching record for tabl"...
0x188b0  ldc.i4.2
0x188b1  newarr   [mscorlib]System.Object
0x188b6  dup
0x188b7  ldc.i4.0
0x188b8  ldarg.0
0x188b9  stelem.ref
0x188ba  dup
0x188bb  ldc.i4.1
0x188bc  ldloc.s  5
0x188be  callvirt instance string [mscorlib]System.Exception::get_Message()
0x188c3  stelem.ref
0x188c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x188c9  ldc.i4   0x80044286
0x188ce  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x188d3  ldc.i4   0x80044286
0x188d8  ldc.i4.2
0x188d9  newarr   [mscorlib]System.Object
0x188de  dup
0x188df  ldc.i4.0
0x188e0  ldarg.0
0x188e1  stelem.ref
0x188e2  dup
0x188e3  ldc.i4.1
0x188e4  ldloc.s  5
0x188e6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x188eb  stelem.ref
0x188ec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32, object[])
0x188f1  throw
0x188f2  ldnull
0x188f3  ret
0x188f4  ldloc.s  4
0x188f6  ret
```
