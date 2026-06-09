# Microsoft.Crm.Extensibility.RequestValidator::ValidateRequiredMembers

- ea: `0xbec0`
- end: `0xc03a`
- name: `Microsoft.Crm.Extensibility.RequestValidator::ValidateRequiredMembers`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xbe50`

## callees

- `0x4230`
- `0x48d0`
- `0x48f0`
- `0x4920`
- `0xbec0`

## string_xrefs

- `0xbff3`: `AddAppComponents`
- `0xc000`: `RemoveAppComponents`

## pseudocode

```c

```

## disassembly

```asm
0xbec0  ldarg.3
0xbec1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0xbec6  ldarg.3
0xbec7  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0xbecc  stloc.0
0xbecd  ldarg.3
0xbece  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0xbed3  stloc.1
0xbed4  ldarg.3
0xbed5  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>
0xbeda  stloc.2
0xbedb  brtrue.s loc_BEE0
0xbedd  ldloc.0
0xbede  brfalse.s loc_BF06
0xbee0  ldarg.0
0xbee1  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.RequestValidator::_entityKeyProcessor
0xbee6  brfalse.s loc_BEF5
0xbee8  ldarg.0
0xbee9  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.RequestValidator::_entityKeyProcessor
0xbeee  newobj   instance void Microsoft.Crm.Extensibility.EntityValidator::.ctor(class Microsoft.Crm.Extensibility.EntityKeyProcessor entityKeyProcessor)
0xbef3  br.s     loc_BEFA
0xbef5  newobj   instance void Microsoft.Crm.Extensibility.EntityValidator::.ctor()
0xbefa  ldarg.2
0xbefb  ldarg.3
0xbefc  ldarg.s  4
0xbefe  ldarg.s  5
0xbf00  callvirt instance void Microsoft.Crm.Extensibility.EntityValidator::ValidateRequiredMembers(string fieldName, object fieldValue, class Microsoft.Crm.Extensibility.EntityActionResolver entityActionResolver, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xbf05  ret
0xbf06  ldloc.1
0xbf07  brfalse.s loc_BF6A
0xbf09  ldloc.1
0xbf0a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0xbf0f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbf14  brfalse.s loc_BF2C
0xbf16  ldstr    aRequiredMember_0// "Required member 'LogicalName' missing f"...
0xbf1b  ldarg.2
0xbf1c  ldstr    asc_372BC// "'"
0xbf21  call     string [mscorlib]System.String::Concat(string, string, string)
0xbf26  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xbf2b  throw
0xbf2c  ldarg.0
0xbf2d  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.RequestValidator::_entityKeyProcessor
0xbf32  brfalse  loc_C039
0xbf37  ldloc.1
0xbf38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xbf3d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbf42  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbf47  brfalse  loc_C039
0xbf4c  ldloc.1
0xbf4d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.KeyAttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_KeyAttributes()
0xbf52  callvirt instance int32 class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Count()
0xbf57  ldc.i4.0
0xbf58  ble      loc_C039
0xbf5d  ldarg.0
0xbf5e  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.RequestValidator::_entityKeyProcessor
0xbf63  ldloc.1
0xbf64  callvirt instance void Microsoft.Crm.Extensibility.EntityKeyProcessor::ResolveAlternateKey(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference)
0xbf69  ret
0xbf6a  ldloc.2
0xbf6b  brfalse  loc_C039
0xbf70  ldloc.2
0xbf71  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::GetEnumerator()
0xbf76  stloc.3
0xbf77  br       loc_C022
0xbf7c  ldloc.3
0xbf7d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Current()
0xbf82  stloc.s  4
0xbf84  ldloc.s  4
0xbf86  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0xbf8b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbf90  brfalse.s loc_BFA8
0xbf92  ldstr    aRequiredMember_0// "Required member 'LogicalName' missing f"...
0xbf97  ldarg.2
0xbf98  ldstr    asc_372BC// "'"
0xbf9d  call     string [mscorlib]System.String::Concat(string, string, string)
0xbfa2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xbfa7  throw
0xbfa8  ldarg.0
0xbfa9  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.RequestValidator::_entityKeyProcessor
0xbfae  brfalse.s loc_BFDF
0xbfb0  ldloc.s  4
0xbfb2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xbfb7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbfbc  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbfc1  brfalse.s loc_BFDF
0xbfc3  ldloc.s  4
0xbfc5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.KeyAttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_KeyAttributes()
0xbfca  callvirt instance int32 class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Count()
0xbfcf  ldc.i4.0
0xbfd0  ble.s    loc_BFDF
0xbfd2  ldarg.0
0xbfd3  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.RequestValidator::_entityKeyProcessor
0xbfd8  ldloc.s  4
0xbfda  callvirt instance void Microsoft.Crm.Extensibility.EntityKeyProcessor::ResolveAlternateKey(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference)
0xbfdf  ldloc.s  4
0xbfe1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xbfe6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbfeb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbff0  brfalse.s loc_C022
0xbff2  ldarg.1
0xbff3  ldstr    aAddappcomponen// "AddAppComponents"
0xbff8  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbffd  brfalse.s loc_C022
0xbfff  ldarg.1
0xc000  ldstr    aRemoveappcompo// "RemoveAppComponents"
0xc005  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xc00a  brfalse.s loc_C022
0xc00c  ldstr    aRequiredMember_1// "Required member 'Id' missing for field "...
0xc011  ldarg.2
0xc012  ldstr    asc_372BC// "'"
0xc017  call     string [mscorlib]System.String::Concat(string, string, string)
0xc01c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xc021  throw
0xc022  ldloc.3
0xc023  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc028  brtrue   loc_BF7C
0xc02d  leave.s  loc_C039
0xc02f  ldloc.3
0xc030  brfalse.s loc_C038
0xc032  ldloc.3
0xc033  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc038  endfinally
0xc039  ret
```
