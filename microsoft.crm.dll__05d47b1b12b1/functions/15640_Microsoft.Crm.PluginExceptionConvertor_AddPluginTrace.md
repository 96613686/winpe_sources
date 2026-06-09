# Microsoft.Crm.PluginExceptionConvertor::AddPluginTrace

- ea: `0x15640`
- end: `0x15739`
- name: `Microsoft.Crm.PluginExceptionConvertor::AddPluginTrace`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x155a0`

## callees

- `0x15640`

## string_xrefs

- `0x1572d`: `PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x15640  ldarg.2
0x15641  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::EqualizeLineBreaks(string)
0x15646  stloc.0
0x15647  ldarg.1
0x15648  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1564d  ldc.i4.0
0x1564e  ceq
0x15650  ldarg.s  7
0x15652  and
0x15653  brfalse.s loc_1569B
0x15655  ldloc.0
0x15656  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1565b  brtrue.s loc_15669
0x1565d  ldloc.0
0x1565e  call     string [mscorlib]System.Environment::get_NewLine()
0x15663  call     string [mscorlib]System.String::Concat(string, string)
0x15668  stloc.0
0x15669  ldloc.0
0x1566a  call     string [mscorlib]System.Environment::get_NewLine()
0x1566f  call     string [mscorlib]System.String::Concat(string, string)
0x15674  stloc.0
0x15675  ldstr    asc_626E8// "\t"
0x1567a  ldarg.1
0x1567b  call     string [mscorlib]System.Environment::get_NewLine()
0x15680  call     string [mscorlib]System.Environment::get_NewLine()
0x15685  ldstr    asc_626E8// "\t"
0x1568a  call     string [mscorlib]System.String::Concat(string, string)
0x1568f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x15694  call     string [mscorlib]System.String::Concat(string, string)
0x15699  starg.s  1
0x1569b  ldarg.1
0x1569c  stloc.1
0x1569d  ldarg.s  7
0x1569f  brfalse.s loc_15709
0x156a1  ldarg.s  5
0x156a3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x156a8  brtrue.s loc_156DD
0x156aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x156af  ldsfld   string Microsoft.Crm.PluginExceptionConvertor::_fullTraceFormat
0x156b4  ldc.i4.6
0x156b5  newarr   [mscorlib]System.Object
0x156ba  dup
0x156bb  ldc.i4.0
0x156bc  ldarg.3
0x156bd  stelem.ref
0x156be  dup
0x156bf  ldc.i4.1
0x156c0  ldarg.s  4
0x156c2  stelem.ref
0x156c3  dup
0x156c4  ldc.i4.2
0x156c5  ldarg.s  5
0x156c7  stelem.ref
0x156c8  dup
0x156c9  ldc.i4.3
0x156ca  ldarg.s  6
0x156cc  stelem.ref
0x156cd  dup
0x156ce  ldc.i4.4
0x156cf  ldloc.0
0x156d0  stelem.ref
0x156d1  dup
0x156d2  ldc.i4.5
0x156d3  ldarg.1
0x156d4  stelem.ref
0x156d5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x156da  stloc.1
0x156db  br.s     loc_15709
0x156dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x156e2  ldsfld   string Microsoft.Crm.PluginExceptionConvertor::_workflowTraceFormat
0x156e7  ldc.i4.5
0x156e8  newarr   [mscorlib]System.Object
0x156ed  dup
0x156ee  ldc.i4.0
0x156ef  ldarg.3
0x156f0  stelem.ref
0x156f1  dup
0x156f2  ldc.i4.1
0x156f3  ldarg.s  4
0x156f5  stelem.ref
0x156f6  dup
0x156f7  ldc.i4.2
0x156f8  ldarg.s  6
0x156fa  stelem.ref
0x156fb  dup
0x156fc  ldc.i4.3
0x156fd  ldloc.0
0x156fe  stelem.ref
0x156ff  dup
0x15700  ldc.i4.4
0x15701  ldarg.1
0x15702  stelem.ref
0x15703  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15708  stloc.1
0x15709  ldarg.0
0x1570a  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x1570f  stloc.2
0x15710  ldloc.2
0x15711  brfalse.s loc_15727
0x15713  ldloc.2
0x15714  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x15719  brfalse.s loc_15727
0x1571b  ldloc.2
0x1571c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x15721  ldloc.1
0x15722  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_TraceText(string)
0x15727  ldarg.0
0x15728  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1572d  ldstr    aPlugintrace// "PluginTrace"
0x15732  ldloc.1
0x15733  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x15738  ret
```
