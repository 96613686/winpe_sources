# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectChartPoints

- ea: `0x7cf0`
- end: `0x7d59`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectChartPoints`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xefb0`
- `0xefd0`

## callees

- `0x7cf0`
- `0x7d60`
- `0x8070`

## pseudocode

```c

```

## disassembly

```asm
0x7cf0  ldarg.2
0x7cf1  ldc.i4.2
0x7cf2  ldelem.ref
0x7cf3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7cf8  beq.s    loc_7D15
0x7cfa  ldarg.1
0x7cfb  dup
0x7cfc  ldc.i4   0x201
0x7d01  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7d06  stloc.0
0x7d07  ldc.i4   0x201
0x7d0c  ldloc.0
0x7d0d  ldc.i4.1
0x7d0e  add
0x7d0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7d14  ret
0x7d15  ldarg.2
0x7d16  ldc.i4.0
0x7d17  ldelem.ref
0x7d18  castclass [mscorlib]System.String
0x7d1d  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x7d22  ldstr    aDatadefinition// "datadefinition/fetchcollection/fetch//a"...
0x7d27  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7d2c  stloc.1
0x7d2d  ldarg.2
0x7d2e  ldc.i4.1
0x7d2f  ldelem.ref
0x7d30  castclass [mscorlib]System.String
0x7d35  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x7d3a  stloc.2
0x7d3b  ldarg.0
0x7d3c  ldarg.1
0x7d3d  ldloc.2
0x7d3e  ldloc.1
0x7d3f  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSqmForSeriesandChartType(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> sqmDataPoints, class [System.Xml]System.Xml.XmlDocument presentationXml, class [System.Xml]System.Xml.XmlNodeList groupByNodes)
0x7d44  ldarg.0
0x7d45  ldarg.1
0x7d46  ldloc.1
0x7d47  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSqmForGrouping(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> sqmDataPoints, class [System.Xml]System.Xml.XmlNodeList groupByNodes)
0x7d4c  leave.s  loc_7D58
0x7d4e  ldloc.1
0x7d4f  brfalse.s loc_7D57
0x7d51  ldloc.1
0x7d52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d57  endfinally
0x7d58  ret
```
