# Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteInitialSolutions

- ea: `0x4cba0`
- end: `0x4cdba`
- name: `Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteInitialSolutions`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4c190`

## callees

- `0x4b350`
- `0x4b380`
- `0x4b3e0`
- `0x4cba0`
- `0x4cdc0`
- `0x4d020`
- `0x4d030`
- `0x4d040`
- `0x4d050`
- `0x4d060`
- `0x4d080`
- `0x50f30`

## string_xrefs

- `0x4cbcf`: `TryDeleteInitialSolutions for : `
- `0x4cc23`: `Starting solution delete pass : `
- `0x4cdaf`: `Completed TryDeleteInitialSolutions`

## pseudocode

```c

```

## disassembly

```asm
0x4cba0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4cba5  ldstr    aSampledatasolu// "SampleDataSolutionNames"
0x4cbaa  ldc.i4.1
0x4cbab  callvirt T0x2B000001
0x4cbb0  stloc.0
0x4cbb1  ldarg.s  4
0x4cbb3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cbb8  brtrue.s loc_4CBBD
0x4cbba  ldarg.s  4
0x4cbbc  stloc.0
0x4cbbd  ldloc.0
0x4cbbe  ldc.i4.1
0x4cbbf  newarr   [mscorlib]System.Char
0x4cbc4  dup
0x4cbc5  ldc.i4.0
0x4cbc6  ldc.i4.s 0x2C
0x4cbc8  stelem.i2
0x4cbc9  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4cbce  ldarg.3
0x4cbcf  ldstr    aTrydeleteiniti// "TryDeleteInitialSolutions for : "
0x4cbd4  ldloc.0
0x4cbd5  call     string [mscorlib]System.String::Concat(string, string)
0x4cbda  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4cbdf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.InitialSolutionInfo>::.ctor()
0x4cbe4  stloc.1
0x4cbe5  stloc.2
0x4cbe6  ldc.i4.0
0x4cbe7  stloc.3
0x4cbe8  br.s     loc_4CC14
0x4cbea  ldloc.2
0x4cbeb  ldloc.3
0x4cbec  ldelem.ref
0x4cbed  stloc.s  4
0x4cbef  ldloc.s  4
0x4cbf1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4cbf6  brtrue.s loc_4CC10
0x4cbf8  newobj   instance void Microsoft.Crm.Data.InitialSolutionInfo::.ctor()
0x4cbfd  stloc.s  5
0x4cbff  ldloc.s  5
0x4cc01  ldloc.s  4
0x4cc03  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_UniqueName(string value)
0x4cc08  ldloc.1
0x4cc09  ldloc.s  5
0x4cc0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.InitialSolutionInfo>::Add(var<u1>)
0x4cc10  ldloc.3
0x4cc11  ldc.i4.1
0x4cc12  add
0x4cc13  stloc.3
0x4cc14  ldloc.3
0x4cc15  ldloc.2
0x4cc16  ldlen
0x4cc17  conv.i4
0x4cc18  blt.s    loc_4CBEA
0x4cc1a  ldc.i4.0
0x4cc1b  stloc.s  6
0x4cc1d  br.s     loc_4CC8B
0x4cc1f  ldc.i4.0
0x4cc20  stloc.s  7
0x4cc22  ldarg.3
0x4cc23  ldstr    aStartingSoluti// "Starting solution delete pass : "
0x4cc28  ldloc.s  6
0x4cc2a  box      [mscorlib]System.Int32
0x4cc2f  call     string [mscorlib]System.String::Concat(object, object)
0x4cc34  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4cc39  ldloc.1
0x4cc3a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.InitialSolutionInfo>::GetEnumerator()
0x4cc3f  stloc.s  8
0x4cc41  br.s     loc_4CC68
0x4cc43  ldloca.s 8
0x4cc45  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Data.InitialSolutionInfo>::get_Current()
0x4cc4a  stloc.s  9
0x4cc4c  ldloc.s  9
0x4cc4e  callvirt instance bool Microsoft.Crm.Data.InitialSolutionInfo::get_DeleteSuccessful()
0x4cc53  brtrue.s loc_4CC68
0x4cc55  ldarg.0
0x4cc56  ldarg.1
0x4cc57  ldarg.2
0x4cc58  ldloc.s  9
0x4cc5a  ldarg.3
0x4cc5b  call     instance bool Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteSolution(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdk, class Microsoft.Crm.Data.InitialSolutionInfo solutionInfo, class [mscorlib]System.Action`1<string> logger)
0x4cc60  brfalse.s loc_4CC68
0x4cc62  ldloc.s  7
0x4cc64  ldc.i4.1
0x4cc65  add
0x4cc66  stloc.s  7
0x4cc68  ldloca.s 8
0x4cc6a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Data.InitialSolutionInfo>::MoveNext()
0x4cc6f  brtrue.s loc_4CC43
0x4cc71  leave.s  loc_4CC81
0x4cc73  ldloca.s 8
0x4cc75  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Data.InitialSolutionInfo>
0x4cc7b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4cc80  endfinally
0x4cc81  ldloc.s  7
0x4cc83  brfalse.s loc_4CC91
0x4cc85  ldloc.s  6
0x4cc87  ldc.i4.1
0x4cc88  add
0x4cc89  stloc.s  6
0x4cc8b  ldloc.s  6
0x4cc8d  ldc.i4.s 0xA
0x4cc8f  blt.s    loc_4CC1F
0x4cc91  ldarg.1
0x4cc92  call     class Microsoft.Crm.Data.IBasicOrganizationDataContext Microsoft.Crm.Data.BasicOrganizationDataContext::New(valuetype [mscorlib]System.Guid orgId)
0x4cc97  stloc.s  0xA
0x4cc99  ldloc.1
0x4cc9a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.InitialSolutionInfo>::GetEnumerator()
0x4cc9f  stloc.s  8
0x4cca1  br       loc_4CD7D
0x4cca6  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x4ccab  stloc.s  0xB
0x4ccad  ldloc.s  0xB
0x4ccaf  ldloca.s 8
0x4ccb1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Data.InitialSolutionInfo>::get_Current()
0x4ccb6  stfld    class Microsoft.Crm.Data.InitialSolutionInfo <>c__DisplayClass13_0::solution
0x4ccbb  ldloc.s  0xA
0x4ccbd  callvirt instance class [System.Data.Linq]System.Data.Linq.ITable`1<class Microsoft.Crm.Data.InitialSolutionInfo> Microsoft.Crm.Data.IBasicOrganizationDataContext::get_InitialSolutionInfoTable()
0x4ccc2  ldtoken  Microsoft.Crm.Data.InitialSolutionInfo
0x4ccc7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cccc  ldstr    aX// "x"
0x4ccd1  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x4ccd6  stloc.s  0xD
0x4ccd8  ldloc.s  0xD
0x4ccda  ldtoken  instance string Microsoft.Crm.Data.InitialSolutionInfo::get_UniqueName()
0x4ccdf  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x4cce4  castclass [mscorlib]System.Reflection.MethodInfo
0x4cce9  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x4ccee  ldloc.s  0xB
0x4ccf0  ldtoken  <>c__DisplayClass13_0
0x4ccf5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ccfa  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x4ccff  ldtoken  class Microsoft.Crm.Data.InitialSolutionInfo <>c__DisplayClass13_0::solution
0x4cd04  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0x4cd09  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0x4cd0e  ldtoken  instance string Microsoft.Crm.Data.InitialSolutionInfo::get_UniqueName()
0x4cd13  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x4cd18  castclass [mscorlib]System.Reflection.MethodInfo
0x4cd1d  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x4cd22  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::Equal(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0x4cd27  ldc.i4.1
0x4cd28  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x4cd2d  dup
0x4cd2e  ldc.i4.0
0x4cd2f  ldloc.s  0xD
0x4cd31  stelem.ref
0x4cd32  call     T0x2B00006B
0x4cd37  call     T0x2B00006C
0x4cd3c  stloc.s  0xC
0x4cd3e  ldloc.s  0xC
0x4cd40  brfalse.s loc_4CD6A
0x4cd42  ldloc.s  0xC
0x4cd44  ldloc.s  0xB
0x4cd46  ldfld    class Microsoft.Crm.Data.InitialSolutionInfo <>c__DisplayClass13_0::solution
0x4cd4b  callvirt instance string Microsoft.Crm.Data.InitialSolutionInfo::get_DeleteStatus()
0x4cd50  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_DeleteStatus(string value)
0x4cd55  ldloc.s  0xC
0x4cd57  ldloc.s  0xB
0x4cd59  ldfld    class Microsoft.Crm.Data.InitialSolutionInfo <>c__DisplayClass13_0::solution
0x4cd5e  callvirt instance bool Microsoft.Crm.Data.InitialSolutionInfo::get_DeleteSuccessful()
0x4cd63  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_DeleteSuccessful(bool value)
0x4cd68  br.s     loc_4CD7D
0x4cd6a  ldloc.s  0xA
0x4cd6c  callvirt instance class [System.Data.Linq]System.Data.Linq.ITable`1<class Microsoft.Crm.Data.InitialSolutionInfo> Microsoft.Crm.Data.IBasicOrganizationDataContext::get_InitialSolutionInfoTable()
0x4cd71  ldloc.s  0xB
0x4cd73  ldfld    class Microsoft.Crm.Data.InitialSolutionInfo <>c__DisplayClass13_0::solution
0x4cd78  callvirt instance void class [System.Data.Linq]System.Data.Linq.ITable`1<class Microsoft.Crm.Data.InitialSolutionInfo>::InsertOnSubmit(var<u1>)
0x4cd7d  ldloca.s 8
0x4cd7f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Data.InitialSolutionInfo>::MoveNext()
0x4cd84  brtrue   loc_4CCA6
0x4cd89  leave.s  loc_4CD99
0x4cd8b  ldloca.s 8
0x4cd8d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Data.InitialSolutionInfo>
0x4cd93  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4cd98  endfinally
0x4cd99  ldloc.s  0xA
0x4cd9b  callvirt instance void Microsoft.Crm.Data.IBasicOrganizationDataContext::SubmitChanges()
0x4cda0  leave.s  loc_4CDAE
0x4cda2  ldloc.s  0xA
0x4cda4  brfalse.s loc_4CDAD
0x4cda6  ldloc.s  0xA
0x4cda8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4cdad  endfinally
0x4cdae  ldarg.3
0x4cdaf  ldstr    aCompletedTryde// "Completed TryDeleteInitialSolutions"
0x4cdb4  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4cdb9  ret
```
