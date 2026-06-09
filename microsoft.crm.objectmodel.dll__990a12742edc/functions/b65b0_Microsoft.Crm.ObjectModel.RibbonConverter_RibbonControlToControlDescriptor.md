# Microsoft.Crm.ObjectModel.RibbonConverter::RibbonControlToControlDescriptor

- ea: `0xb65b0`
- end: `0xb7050`
- name: `Microsoft.Crm.ObjectModel.RibbonConverter::RibbonControlToControlDescriptor`
- size: `2720`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0xb6120`
- `0xb7240`

## callees

- `0xb65b0`
- `0xb7050`
- `0xb7240`
- `0xb7350`
- `0xb73f0`
- `0xb7490`
- `0xbd040`
- `0x22be40`

## string_xrefs

- `0xb65ed`: `Command`
- `0xb65ff`: `Command`
- `0xb6616`: `Command`
- `0xb6e1f`: `Command`
- `0xb6c00`: `CreateCommand`
- `0xb6cc2`: `CreateCommand`
- `0xb6d37`: `CreateCommand`
- `0xb6773`: `Mscrm.Modern.PinCommand`
- `0xb6780`: `Mscrm.Modern.EmailLinkCommand`
- `0xb683e`: `addCommand`
- `0xb6847`: `ControlCommand`
- `0xb6b5d`: `ControlCommand`
- `0xb686f`: `connection.Delete`
- `0xb6a05`: `Mscrm.CreateLetter`
- `0xb6a1a`: `Mscrm.CreateFax`
- `0xb6a2f`: `Mscrm.CreateServiceAppointment`
- `0xb6a44`: `Mscrm.CreateCampaignResponse`
- `0xb6a59`: `Mscrm.CreateRecurringAppointment`
- `0xb6bc1`: `Mscrm.CreateRecurringAppointment`
- `0xb6a6e`: `Mscrm.CreateRecurringAppointmentMaster`
- `0xb6bcd`: `Mscrm.CreateRecurringAppointmentMaster`
- `0xb6a98`: `Mscrm.Modern.WordTemplatesCommand`
- `0xb6aad`: `Mscrm.Modern.Form.WordTemplatesCommand`
- `0xb6ac2`: `Mscrm.Modern.DocumentTemplatesCommand`
- `0xb6b01`: `Mscrm.DynamicMenu.Subgrid.NewActivityMenu.serviceappointment`
- `0xb6b41`: `ruleEvaluationCommand`
- `0xb6b54`: `addExistingCommand`
- `0xb6bd4`: `Mscrm.Create`
- `0xb6f58`: `Mscrm.HomepageGrid.DeleteSplitButtonCommand`
- `0xb6f71`: `Mscrm.DeleteSelectedRecord`

## pseudocode

```c

```

## disassembly

```asm
0xb65b0  ldnull
0xb65b1  stloc.0
0xb65b2  ldnull
0xb65b3  stloc.1
0xb65b4  ldnull
0xb65b5  stloc.2
0xb65b6  ldnull
0xb65b7  stloc.3
0xb65b8  ldnull
0xb65b9  stloc.s  4
0xb65bb  ldarg.0
0xb65bc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb65c1  ldstr    aId_0// "Id"
0xb65c6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb65cb  brtrue.s loc_B65D0
0xb65cd  ldnull
0xb65ce  br.s     loc_B65E5
0xb65d0  ldarg.0
0xb65d1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb65d6  ldstr    aId_0// "Id"
0xb65db  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb65e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb65e5  stloc.s  5
0xb65e7  ldarg.0
0xb65e8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb65ed  ldstr    aCommand_0// "Command"
0xb65f2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb65f7  brfalse.s loc_B6668
0xb65f9  ldarg.0
0xb65fa  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb65ff  ldstr    aCommand_0// "Command"
0xb6604  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb6609  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb660e  brfalse.s loc_B6668
0xb6610  ldarg.0
0xb6611  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb6616  ldstr    aCommand_0// "Command"
0xb661b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb6620  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb6625  stloc.1
0xb6626  ldloc.1
0xb6627  ldc.i4.1
0xb6628  newarr   [mscorlib]System.Char
0xb662d  dup
0xb662e  ldc.i4.0
0xb662f  ldc.i4.s 0x2E
0xb6631  stelem.i2
0xb6632  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb6637  dup
0xb6638  ldlen
0xb6639  conv.i4
0xb663a  ldc.i4.1
0xb663b  sub
0xb663c  ldelem.ref
0xb663d  stloc.2
0xb663e  ldloc.1
0xb663f  ldc.i4.1
0xb6640  newarr   [mscorlib]System.Char
0xb6645  dup
0xb6646  ldc.i4.0
0xb6647  ldc.i4.s 0x7C
0xb6649  stelem.i2
0xb664a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb664f  stloc.s  0xC
0xb6651  ldloc.s  0xC
0xb6653  ldlen
0xb6654  conv.i4
0xb6655  ldc.i4.1
0xb6656  blt.s    loc_B6668
0xb6658  ldloc.s  0xC
0xb665a  ldloc.s  0xC
0xb665c  ldlen
0xb665d  conv.i4
0xb665e  ldc.i4.1
0xb665f  sub
0xb6660  ldelem.ref
0xb6661  stloc.3
0xb6662  ldloc.s  0xC
0xb6664  ldc.i4.0
0xb6665  ldelem.ref
0xb6666  stloc.s  4
0xb6668  ldnull
0xb6669  stloc.s  6
0xb666b  ldstr    aSymbol// "Symbol"
0xb6670  stloc.s  7
0xb6672  ldarg.0
0xb6673  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb6678  ldstr    aModernimage// "ModernImage"
0xb667d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb6682  brfalse.s loc_B66B4
0xb6684  ldarg.0
0xb6685  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb668a  ldstr    aModernimage// "ModernImage"
0xb668f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb6694  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb6699  brfalse.s loc_B66B4
0xb669b  ldarg.0
0xb669c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb66a1  ldstr    aModernimage// "ModernImage"
0xb66a6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb66ab  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb66b0  stloc.s  6
0xb66b2  br.s     loc_B66BB
0xb66b4  ldstr    aDefault// "Default"
0xb66b9  stloc.s  6
0xb66bb  ldarg.0
0xb66bc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb66c1  ldstr    aLabeltext// "LabelText"
0xb66c6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb66cb  brtrue.s loc_B66D0
0xb66cd  ldnull
0xb66ce  br.s     loc_B66E5
0xb66d0  ldarg.0
0xb66d1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb66d6  ldstr    aLabeltext// "LabelText"
0xb66db  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb66e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb66e5  stloc.s  8
0xb66e7  ldloc.s  8
0xb66e9  brtrue.s loc_B6717
0xb66eb  ldarg.0
0xb66ec  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb66f1  ldstr    aTitle// "Title"
0xb66f6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb66fb  brtrue.s loc_B6700
0xb66fd  ldnull
0xb66fe  br.s     loc_B6715
0xb6700  ldarg.0
0xb6701  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb6706  ldstr    aTitle// "Title"
0xb670b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb6710  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb6715  stloc.s  8
0xb6717  ldloc.s  5
0xb6719  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb671e  brtrue.s loc_B6740
0xb6720  ldloc.s  5
0xb6722  ldstr    aActivitypointe_1// "activitypointer"
0xb6727  ldc.i4.5
0xb6728  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xb672d  brfalse.s loc_B6740
0xb672f  ldloc.s  5
0xb6731  ldstr    aActivitypointe_3// "activitypointer.NewRecord"
0xb6736  ldc.i4.5
0xb6737  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xb673c  brfalse.s loc_B6740
0xb673e  ldnull
0xb673f  ret
0xb6740  ldarg.1
0xb6741  ldc.i4.1
0xb6742  bne.un.s loc_B674F
0xb6744  ldarg.2
0xb6745  ldloc.3
0xb6746  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Contains(var<u1>)
0xb674b  brfalse.s loc_B674F
0xb674d  ldnull
0xb674e  ret
0xb674f  ldarg.s  4
0xb6751  brtrue.s loc_B678E
0xb6753  ldarg.1
0xb6754  ldc.i4.2
0xb6755  bne.un.s loc_B678E
0xb6757  ldarg.2
0xb6758  ldloc.3
0xb6759  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Contains(var<u1>)
0xb675e  brtrue.s loc_B678E
0xb6760  ldarg.0
0xb6761  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb6766  ldstr    aButton// "Button"
0xb676b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb6770  brfalse.s loc_B678E
0xb6772  ldloc.3
0xb6773  ldstr    aMscrmModernPin// "Mscrm.Modern.PinCommand"
0xb6778  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xb677d  brfalse.s loc_B678E
0xb677f  ldloc.3
0xb6780  ldstr    aMscrmModernEma// "Mscrm.Modern.EmailLinkCommand"
0xb6785  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xb678a  brfalse.s loc_B678E
0xb678c  ldnull
0xb678d  ret
0xb678e  ldloc.s  8
0xb6790  brfalse.s loc_B67B3
0xb6792  ldloc.s  8
0xb6794  ldstr    asc_2A5726// " "
0xb6799  callvirt instance bool [mscorlib]System.String::Contains(string)
0xb679e  brfalse.s loc_B67B3
0xb67a0  ldloc.s  8
0xb67a2  ldstr    asc_2A5726// " "
0xb67a7  ldstr    asc_279D7A// " "
0xb67ac  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb67b1  stloc.s  8
0xb67b3  ldc.i4.m1
0xb67b4  stloc.s  9
0xb67b6  ldarg.0
0xb67b7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb67bc  ldstr    aSequence_0// "Sequence"
0xb67c1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb67c6  brfalse.s loc_B67E6
0xb67c8  ldarg.0
0xb67c9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb67ce  ldstr    aSequence_0// "Sequence"
0xb67d3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb67d8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb67dd  ldloca.s 9
0xb67df  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xb67e4  brtrue.s loc_B67ED
0xb67e6  ldc.i4   0x3E7
0xb67eb  stloc.s  9
0xb67ed  ldsfld   string [mscorlib]System.String::Empty
0xb67f2  stloc.s  0xA
0xb67f4  ldc.i4.0
0xb67f5  newarr   [mscorlib]System.Object
0xb67fa  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xb67ff  stloc.s  0xB
0xb6801  ldloc.s  0xB
0xb6803  ldstr    aEntitylogicaln_3// "entityLogicalName"
0xb6808  ldloc.s  4
0xb680a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb680f  ldloc.s  5
0xb6811  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb6816  brtrue.s loc_B687E
0xb6818  ldloc.s  5
0xb681a  ldstr    aConnection// "connection"
0xb681f  ldc.i4.5
0xb6820  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xb6825  brfalse.s loc_B687E
0xb6827  ldloc.s  5
0xb6829  ldstr    aConnectionNewr// "connection.NewRecord"
0xb682e  ldc.i4.5
0xb682f  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xb6834  brfalse.s loc_B685E
0xb6836  ldloc.s  5
0xb6838  ldarg.0
0xb6839  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb683e  ldstr    aAddcommand// "addCommand"
0xb6843  ldloc.s  8
0xb6845  ldloc.s  9
0xb6847  ldstr    aControlcommand// "ControlCommand"
0xb684c  ldstr    aAdd// "Add"
0xb6851  ldstr    aSymbol// "Symbol"
0xb6856  ldloc.s  0xB
0xb6858  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0xb685d  ret
0xb685e  ldloc.s  5
0xb6860  ldstr    aMscrmSubgridCo// "Mscrm.SubGrid.connection.RefreshButton"
0xb6865  ldc.i4.5
0xb6866  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xb686b  brtrue.s loc_B687E
0xb686d  ldloc.s  5
0xb686f  ldstr    aConnectionDele// "connection.Delete"
0xb6874  ldc.i4.5
0xb6875  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xb687a  brtrue.s loc_B687E
0xb687c  ldnull
0xb687d  ret
0xb687e  ldloc.3
0xb687f  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xb6884  stloc.s  0xD
0xb6886  ldloc.s  0xD
0xb6888  ldc.i4   0x64DD5BBE
0xb688d  bgt.un   loc_B692D
0xb6892  ldloc.s  0xD
0xb6894  ldc.i4   0x407BE5C9
0xb6899  bgt.un.s loc_B68DE
0xb689b  ldloc.s  0xD
0xb689d  ldc.i4   0x1FB391C5
0xb68a2  bgt.un.s loc_B68C1
0xb68a4  ldloc.s  0xD
0xb68a6  ldc.i4   0x1944EA2E
0xb68ab  beq      loc_B69DA
0xb68b0  ldloc.s  0xD
0xb68b2  ldc.i4   0x1FB391C5
0xb68b7  beq      loc_B6B00
0xb68bc  br       loc_B6CE7
0xb68c1  ldloc.s  0xD
0xb68c3  ldc.i4   0x2FAC0B8B
0xb68c8  beq      loc_B6A04
0xb68cd  ldloc.s  0xD
0xb68cf  ldc.i4   0x407BE5C9
0xb68d4  beq      loc_B69C5
0xb68d9  br       loc_B6CE7
0xb68de  ldloc.s  0xD
0xb68e0  ldc.i4   0x4A1F97CB
0xb68e5  bgt.un.s loc_B6904
0xb68e7  ldloc.s  0xD
0xb68e9  ldc.i4   0x43F20F2C
0xb68ee  beq      loc_B6B15
0xb68f3  ldloc.s  0xD
0xb68f5  ldc.i4   0x4A1F97CB
0xb68fa  beq      loc_B6AC1
0xb68ff  br       loc_B6CE7
0xb6904  ldloc.s  0xD
0xb6906  ldc.i4   0x4E748C72
0xb690b  beq      loc_B6A19
0xb6910  ldloc.s  0xD
0xb6912  ldc.i4   0x4F580DC9
0xb6917  beq      loc_B6AD6
0xb691c  ldloc.s  0xD
0xb691e  ldc.i4   0x64DD5BBE
  ... truncated ...
```
