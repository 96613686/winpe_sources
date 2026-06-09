# Microsoft.Crm.ExceptionUtility::CreateCrmExceptionFromServiceFault

- ea: `0x157d0`
- end: `0x15898`
- name: `Microsoft.Crm.ExceptionUtility::CreateCrmExceptionFromServiceFault`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x157d0`

## string_xrefs

- `0x15804`: `PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x157d0  ldarg.0
0x157d1  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x157d6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x157db  ldarg.0
0x157dc  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x157e1  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x157e6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x157eb  stloc.0
0x157ec  ldarg.0
0x157ed  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x157f2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x157f7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x157fc  brtrue.s loc_15819
0x157fe  ldloc.0
0x157ff  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x15804  ldstr    aPlugintrace// "PluginTrace"
0x15809  ldarg.0
0x1580a  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1580f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x15814  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x15819  ldloc.0
0x1581a  ldarg.0
0x1581b  callvirt instance string [mscorlib]System.Exception::get_Source()
0x15820  callvirt instance void [mscorlib]System.Exception::set_Source(string)
0x15825  ldarg.0
0x15826  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1582b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x15830  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x15835  stloc.1
0x15836  br.s     loc_15882
0x15838  ldloc.1
0x15839  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x1583e  stloc.2
0x1583f  ldloca.s 2
0x15841  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x15846  ldloca.s 3
0x15848  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x1584d  brfalse.s loc_15869
0x1584f  ldloc.0
0x15850  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x15855  ldloc.3
0x15856  box      [mscorlib]System.Int32
0x1585b  ldloca.s 2
0x1585d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x15862  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::set_Item(var<u1>, !!T0)
0x15867  br.s     loc_15882
0x15869  ldloc.0
0x1586a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x1586f  ldloca.s 2
0x15871  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x15876  ldloca.s 2
0x15878  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1587d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::set_Item(var<u1>, !!T0)
0x15882  ldloc.1
0x15883  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15888  brtrue.s loc_15838
0x1588a  leave.s  loc_15896
0x1588c  ldloc.1
0x1588d  brfalse.s loc_15895
0x1588f  ldloc.1
0x15890  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15895  endfinally
0x15896  ldloc.0
0x15897  ret
```
