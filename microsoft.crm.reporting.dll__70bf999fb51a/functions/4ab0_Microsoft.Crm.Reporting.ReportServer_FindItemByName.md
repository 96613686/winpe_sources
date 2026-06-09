# Microsoft.Crm.Reporting.ReportServer::FindItemByName

- ea: `0x4ab0`
- end: `0x4bd3`
- name: `Microsoft.Crm.Reporting.ReportServer::FindItemByName`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4aa0`
- `0x7fa0`

## callees

- `0x270`
- `0x4860`
- `0x4970`
- `0x4ab0`

## string_xrefs

- `0x4b18`: `Calling ReportingService.FindItems to find {0}: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x4ab0  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition::.ctor()
0x4ab5  stloc.0
0x4ab6  ldloc.0
0x4ab7  ldc.i4.1
0x4ab8  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition::set_Condition(valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ConditionEnum)
0x4abd  ldloc.0
0x4abe  ldc.i4.1
0x4abf  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition::set_ConditionSpecified(bool)
0x4ac4  ldloc.0
0x4ac5  ldstr    aName// "Name"
0x4aca  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition::set_Name(string)
0x4acf  ldc.i4.1
0x4ad0  newarr   [mscorlib]System.String
0x4ad5  dup
0x4ad6  ldc.i4.0
0x4ad7  ldarg.2
0x4ad8  stelem.ref
0x4ad9  stloc.1
0x4ada  ldloc.0
0x4adb  ldloc.1
0x4adc  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition::set_Values(string[])
0x4ae1  ldc.i4.1
0x4ae2  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition
0x4ae7  dup
0x4ae8  ldc.i4.0
0x4ae9  ldloc.0
0x4aea  stelem.ref
0x4aeb  stloc.2
0x4aec  ldc.i4.1
0x4aed  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property
0x4af2  dup
0x4af3  ldc.i4.0
0x4af4  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::.ctor()
0x4af9  dup
0x4afa  ldstr    aRecursive// "Recursive"
0x4aff  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Name(string)
0x4b04  dup
0x4b05  ldstr    aTrue_0// "True"
0x4b0a  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Value(string)
0x4b0f  stelem.ref
0x4b10  stloc.3
0x4b11  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4b16  ldc.i4.s 0x20
0x4b18  ldstr    aCallingReporti_0// "Calling ReportingService.FindItems to f"...
0x4b1d  ldc.i4.2
0x4b1e  newarr   [mscorlib]System.Object
0x4b23  dup
0x4b24  ldc.i4.0
0x4b25  ldarg.3
0x4b26  stelem.ref
0x4b27  dup
0x4b28  ldc.i4.1
0x4b29  ldarg.2
0x4b2a  stelem.ref
0x4b2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4b30  ldarg.0
0x4b31  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x4b36  ldarg.1
0x4b37  ldc.i4.0
0x4b38  ldloc.3
0x4b39  ldloc.2
0x4b3a  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem[] Microsoft.Crm.Reporting.IReportingService::FindItems(string Folder, valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.BooleanOperatorEnum BooleanOperator, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] SearchOptions, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition[] SearchConditions)
0x4b3f  stloc.s  4
0x4b41  leave.s  loc_4B58
0x4b43  stloc.s  6
0x4b45  ldarg.0
0x4b46  ldloc.s  6
0x4b48  ldstr    aFinditems// "FindItems"
0x4b4d  ldc.i4   0x80048318
0x4b52  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x4b57  throw
0x4b58  ldarg.1
0x4b59  ldarg.1
0x4b5a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b5f  ldc.i4.1
0x4b60  sub
0x4b61  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4b66  ldc.i4.s 0x2F
0x4b68  beq.s    loc_4B74
0x4b6a  ldarg.1
0x4b6b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b70  ldc.i4.1
0x4b71  add
0x4b72  br.s     loc_4B7A
0x4b74  ldarg.1
0x4b75  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b7a  stloc.s  5
0x4b7c  ldloc.s  4
0x4b7e  brfalse.s loc_4BD1
0x4b80  ldloc.s  4
0x4b82  stloc.s  7
0x4b84  ldc.i4.0
0x4b85  stloc.s  8
0x4b87  br.s     loc_4BC9
0x4b89  ldloc.s  7
0x4b8b  ldloc.s  8
0x4b8d  ldelem.ref
0x4b8e  stloc.s  9
0x4b90  ldloc.s  9
0x4b92  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem::get_Path()
0x4b97  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b9c  ldloc.s  9
0x4b9e  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem::get_Name()
0x4ba3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ba8  sub
0x4ba9  stloc.s  0xA
0x4bab  ldloc.s  9
0x4bad  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem::get_TypeName()
0x4bb2  ldarg.3
0x4bb3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bb8  brfalse.s loc_4BC3
0x4bba  ldloc.s  0xA
0x4bbc  ldloc.s  5
0x4bbe  bne.un.s loc_4BC3
0x4bc0  ldloc.s  9
0x4bc2  ret
0x4bc3  ldloc.s  8
0x4bc5  ldc.i4.1
0x4bc6  add
0x4bc7  stloc.s  8
0x4bc9  ldloc.s  8
0x4bcb  ldloc.s  7
0x4bcd  ldlen
0x4bce  conv.i4
0x4bcf  blt.s    loc_4B89
0x4bd1  ldnull
0x4bd2  ret
```
