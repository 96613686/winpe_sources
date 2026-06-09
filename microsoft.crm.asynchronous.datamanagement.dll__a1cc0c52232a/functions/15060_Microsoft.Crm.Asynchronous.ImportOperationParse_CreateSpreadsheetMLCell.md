# Microsoft.Crm.Asynchronous.ImportOperationParse::CreateSpreadsheetMLCell

- ea: `0x15060`
- end: `0x151e5`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::CreateSpreadsheetMLCell`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14cb0`

## callees

- `0x15060`
- `0x151f0`

## string_xrefs

- `0x1509c`: `urn:schemas-microsoft-com:office:spreadsheet`
- `0x150fc`: `urn:schemas-microsoft-com:office:spreadsheet`
- `0x150c2`: `CreateSpreadsheetMLCell : XmlReader reached an invalid depth and escaped out of <ss:Data> node subtree.`
- `0x1514c`: `An unexpected node type : '{0}' having node name : '{1}' was encountered while parsing XML <Data> content.`
- `0x151a0`: `Exception encountered when trying to load content from within an XMLSS <ss:Data> cell : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15060  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x15065  stloc.0
0x15066  ldc.i4.0
0x15067  stloc.1
0x15068  ldarg.s  4
0x1506a  brtrue   loc_151BC
0x1506f  ldarg.1
0x15070  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15075  ldc.i4.3
0x15076  bne.un.s loc_150AC
0x15078  ldloc.0
0x15079  ldarg.1
0x1507a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x1507f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15084  pop
0x15085  ldarg.1
0x15086  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1508b  pop
0x1508c  ldarg.1
0x1508d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15092  ldc.i4.s 0xF
0x15094  bne.un.s loc_150A8
0x15096  ldarg.1
0x15097  ldstr    aData_1// "Data"
0x1509c  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:office:spread"...
0x150a1  call     bool Microsoft.Crm.Asynchronous.ImportOperationParse::IsReaderAtNode(class [System.Xml]System.Xml.XmlReader reader, string nodeName, string namespaceUri)
0x150a6  brtrue.s loc_150AE
0x150a8  ldc.i4.1
0x150a9  stloc.1
0x150aa  br.s     loc_150AE
0x150ac  ldc.i4.1
0x150ad  stloc.1
0x150ae  ldloc.1
0x150af  brfalse  loc_151BC
0x150b4  ldc.i4.0
0x150b5  stloc.3
0x150b6  ldarg.1
0x150b7  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x150bc  ldarg.3
0x150bd  clt
0x150bf  ldc.i4.0
0x150c0  ceq
0x150c2  ldstr    aCreatespreadsh// "CreateSpreadsheetMLCell : XmlReader rea"...
0x150c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x150cc  ldarg.1
0x150cd  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x150d2  stloc.s  4
0x150d4  ldloc.s  4
0x150d6  ldc.i4.3
0x150d7  beq.s    loc_1510C
0x150d9  ldloc.s  4
0x150db  ldc.i4.4
0x150dc  beq.s    loc_1510C
0x150de  ldloc.s  4
0x150e0  ldc.i4.s 0xD
0x150e2  sub
0x150e3  switch   loc_1510C, loc_1510C, loc_150F6
0x150f4  br.s     loc_1511B
0x150f6  ldarg.1
0x150f7  ldstr    aData_1// "Data"
0x150fc  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:office:spread"...
0x15101  call     bool Microsoft.Crm.Asynchronous.ImportOperationParse::IsReaderAtNode(class [System.Xml]System.Xml.XmlReader reader, string nodeName, string namespaceUri)
0x15106  brfalse.s loc_1517F
0x15108  ldc.i4.1
0x15109  stloc.3
0x1510a  br.s     loc_1517F
0x1510c  ldloc.0
0x1510d  ldarg.1
0x1510e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x15113  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15118  pop
0x15119  br.s     loc_1517F
0x1511b  ldarg.1
0x1511c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15121  ldc.i4.1
0x15122  bne.un.s loc_15137
0x15124  ldarg.0
0x15125  ldfld    class [System]System.Collections.Generic.SortedSet`1<string> Microsoft.Crm.Asynchronous.ImportOperationParse::_htmlElementsAllowedlist
0x1512a  ldarg.1
0x1512b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15130  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<string>::Contains(var<u1>)
0x15135  brtrue.s loc_1517F
0x15137  ldarg.s  7
0x15139  ldc.i4.0
0x1513a  stind.i1
0x1513b  ldc.i4.4
0x1513c  starg.s  5
0x1513e  ldnull
0x1513f  ldarg.0
0x15140  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x15145  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1514a  ldc.i4.s 0x18
0x1514c  ldstr    aAnUnexpectedNo// "An unexpected node type : '{0}' having "...
0x15151  ldc.i4.2
0x15152  newarr   [mscorlib]System.Object
0x15157  dup
0x15158  ldc.i4.0
0x15159  ldarg.1
0x1515a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1515f  stloc.s  4
0x15161  ldloca.s 4
0x15163  constrained. [System.Xml]System.Xml.XmlNodeType
0x15169  callvirt instance string [mscorlib]System.Object::ToString()
0x1516e  stelem.ref
0x1516f  dup
0x15170  ldc.i4.1
0x15171  ldarg.1
0x15172  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15177  stelem.ref
0x15178  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1517d  ldc.i4.1
0x1517e  stloc.3
0x1517f  ldloc.3
0x15180  brtrue.s loc_1518D
0x15182  ldarg.1
0x15183  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x15188  brtrue   loc_150B6
0x1518d  leave.s  loc_151BC
0x1518f  stloc.s  5
0x15191  ldloc.s  5
0x15193  ldarg.0
0x15194  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x15199  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1519e  ldc.i4.s 0x18
0x151a0  ldstr    aExceptionEncou// "Exception encountered when trying to lo"...
0x151a5  ldc.i4.1
0x151a6  newarr   [mscorlib]System.Object
0x151ab  dup
0x151ac  ldc.i4.0
0x151ad  ldloc.s  5
0x151af  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x151b4  stelem.ref
0x151b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x151ba  rethrow
0x151bc  ldarg.2
0x151bd  ldloc.0
0x151be  callvirt instance string [mscorlib]System.Object::ToString()
0x151c3  ldarg.s  5
0x151c5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell::.ctor(int32, string, valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCellType)
0x151ca  stloc.2
0x151cb  ldarg.s  6
0x151cd  ldloc.2
0x151ce  callvirt instance void [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::AddCellToRow(class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell)
0x151d3  ldloc.2
0x151d4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell::get_CellData()
0x151d9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x151de  brtrue.s loc_151E4
0x151e0  ldarg.s  7
0x151e2  ldc.i4.0
0x151e3  stind.i1
0x151e4  ret
```
