# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::CreateOrganizationFeatures

- ea: `0x27fe0`
- end: `0x280da`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::CreateOrganizationFeatures`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x25c00`

## callees

- `0x27fe0`

## string_xrefs

- `0x28005`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x28090`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x27fe3`: `CreateOrganizationFeatures`
- `0x28000`: `CreateOrganizationFeatures`
- `0x2808b`: `CreateOrganizationFeatures`
- `0x280bd`: `Exception in CreateOrganizationFeatures {0}`

## pseudocode

```c

```

## disassembly

```asm
0x27fe0  ldarg.0
0x27fe1  ldc.i4.s 0x14
0x27fe3  ldstr    aCreateorganiza_1// "CreateOrganizationFeatures"
0x27fe8  ldc.i4.0
0x27fe9  newarr   [mscorlib]System.Object
0x27fee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27ff3  ldarg.1
0x27ff4  ldstr    aFeature_0// "Feature"
0x27ff9  ldnull
0x27ffa  ldnull
0x27ffb  ldc.i4   0x68A
0x28000  ldstr    aCreateorganiza_1// "CreateOrganizationFeatures"
0x28005  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2800a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2800f  stloc.0
0x28010  ldloc.0
0x28011  brfalse  loc_280B4
0x28016  ldloc.0
0x28017  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x2801c  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x28021  stloc.1
0x28022  br.s     loc_2809B
0x28024  ldloca.s 1
0x28026  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x2802b  stloc.2
0x2802c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x28031  stloc.3
0x28032  ldloc.3
0x28033  ldstr    aId// "Id"
0x28038  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x2803d  box      [mscorlib]System.Guid
0x28042  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x28047  ldloc.3
0x28048  ldstr    aFeatureid// "FeatureId"
0x2804d  ldloc.2
0x2804e  ldstr    aId// "Id"
0x28053  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x28058  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x2805d  ldloc.3
0x2805e  ldstr    aOrganizationid_0// "OrganizationId"
0x28063  ldarg.0
0x28064  box      [mscorlib]System.Guid
0x28069  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x2806e  ldloc.3
0x2806f  ldstr    aEnabled// "Enabled"
0x28074  ldc.i4.1
0x28075  box      [mscorlib]System.Boolean
0x2807a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x2807f  ldarg.1
0x28080  ldstr    aOrganizationfe_0// "OrganizationFeatureMap"
0x28085  ldloc.3
0x28086  ldc.i4   0x695
0x2808b  ldstr    aCreateorganiza_1// "CreateOrganizationFeatures"
0x28090  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x28095  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2809a  pop
0x2809b  ldloca.s 1
0x2809d  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x280a2  brtrue.s loc_28024
0x280a4  leave.s  loc_280B4
0x280a6  ldloca.s 1
0x280a8  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x280ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x280b3  endfinally
0x280b4  leave.s  loc_280D9
0x280b6  stloc.s  4
0x280b8  ldloc.s  4
0x280ba  ldarg.0
0x280bb  ldc.i4.s 0x14
0x280bd  ldstr    aExceptionInCre// "Exception in CreateOrganizationFeatures"...
0x280c2  ldc.i4.1
0x280c3  newarr   [mscorlib]System.Object
0x280c8  dup
0x280c9  ldc.i4.0
0x280ca  ldloc.s  4
0x280cc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x280d1  stelem.ref
0x280d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x280d7  rethrow
0x280d9  ret
```
