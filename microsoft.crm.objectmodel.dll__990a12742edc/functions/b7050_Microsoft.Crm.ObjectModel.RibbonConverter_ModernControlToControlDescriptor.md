# Microsoft.Crm.ObjectModel.RibbonConverter::ModernControlToControlDescriptor

- ea: `0xb7050`
- end: `0xb7235`
- name: `Microsoft.Crm.ObjectModel.RibbonConverter::ModernControlToControlDescriptor`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb65b0`

## callees

- `0xb7050`
- `0xbd080`

## string_xrefs

- `0xb7211`: `ruleEvaluationCommand`
- `0xb7056`: `ModernCommandType`
- `0xb7068`: `ModernCommandType`
- `0xb7086`: `ModernCommandType`
- `0xb70d4`: `PinCommand`
- `0xb7102`: `PinCommand`
- `0xb70e1`: `ChangeControlCommand`
- `0xb7187`: `ChangeControlCommand`
- `0xb70ee`: `resizeHandlesCommand`
- `0xb7203`: `resizeHandlesCommand`
- `0xb7142`: `ChangeViewCommand`
- `0xb7177`: `CommandId`
- `0xb71b3`: `CommandId`
- `0xb71a7`: `RetrieveControlConfigurations`
- `0xb71c3`: `CreateEmailReplyDraftCommand`

## pseudocode

```c

```

## disassembly

```asm
0xb7050  ldarg.0
0xb7051  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb7056  ldstr    aModerncommandt// "ModernCommandType"
0xb705b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb7060  brfalse.s loc_B707E
0xb7062  ldarg.0
0xb7063  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb7068  ldstr    aModerncommandt// "ModernCommandType"
0xb706d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb7072  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb7077  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb707c  brfalse.s loc_B7080
0xb707e  ldnull
0xb707f  ret
0xb7080  ldarg.0
0xb7081  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb7086  ldstr    aModerncommandt// "ModernCommandType"
0xb708b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb7090  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb7095  stloc.0
0xb7096  ldarg.0
0xb7097  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb709c  ldstr    aId_0// "Id"
0xb70a1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb70a6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb70ab  ldc.i4.1
0xb70ac  newarr   [mscorlib]System.Char
0xb70b1  dup
0xb70b2  ldc.i4.0
0xb70b3  ldc.i4.s 0x2E
0xb70b5  stelem.i2
0xb70b6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb70bb  dup
0xb70bc  ldlen
0xb70bd  conv.i4
0xb70be  ldc.i4.1
0xb70bf  sub
0xb70c0  ldelem.ref
0xb70c1  stloc.1
0xb70c2  ldarg.3
0xb70c3  ldstr    aMscrmModern// "Mscrm.Modern."
0xb70c8  ldstr    asc_24F76C// ""
0xb70cd  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xb70d2  stloc.2
0xb70d3  ldloc.2
0xb70d4  ldstr    aPincommand// "PinCommand"
0xb70d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb70de  brtrue.s loc_B70FA
0xb70e0  ldloc.2
0xb70e1  ldstr    aChangecontrolc// "ChangeControlCommand"
0xb70e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb70eb  brtrue.s loc_B70FA
0xb70ed  ldloc.2
0xb70ee  ldstr    aResizehandlesc// "resizeHandlesCommand"
0xb70f3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb70f8  brfalse.s loc_B7101
0xb70fa  ldarg.s  9
0xb70fc  ldc.i4.3
0xb70fd  bne.un.s loc_B7101
0xb70ff  ldnull
0xb7100  ret
0xb7101  ldloc.2
0xb7102  ldstr    aPincommand// "PinCommand"
0xb7107  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb710c  brfalse.s loc_B7141
0xb710e  ldarg.s  8
0xb7110  ldstr    aStartscreen// "StartScreen"
0xb7115  ldloc.1
0xb7116  ldstr    aWin8pinbutton// "Win8PinButton"
0xb711b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb7120  box      [mscorlib]System.Boolean
0xb7125  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb712a  ldarg.s  8
0xb712c  ldstr    aIsboundtoscree// "IsBoundToScreen"
0xb7131  ldc.i4.0
0xb7132  box      [mscorlib]System.Boolean
0xb7137  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb713c  br       loc_B7202
0xb7141  ldloc.2
0xb7142  ldstr    aChangeviewcomm// "ChangeViewCommand"
0xb7147  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb714c  brfalse.s loc_B7186
0xb714e  ldarg.1
0xb714f  ldc.i4.2
0xb7150  bne.un.s loc_B7154
0xb7152  ldnull
0xb7153  ret
0xb7154  ldarg.2
0xb7155  brtrue.s loc_B715E
0xb7157  ldstr    aChangegridview// "ChangeGridViewButton"
0xb715c  br.s     loc_B7163
0xb715e  ldstr    aChangelistview// "ChangeListViewButton"
0xb7163  stloc.1
0xb7164  ldarg.s  8
0xb7166  ldstr    aRetrievalactio// "RetrievalAction"
0xb716b  ldstr    aRetrieveviewse// "RetrieveViewSelector"
0xb7170  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb7175  ldarg.s  8
0xb7177  ldstr    aCommandid// "CommandId"
0xb717c  ldarg.3
0xb717d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb7182  ldnull
0xb7183  stloc.0
0xb7184  br.s     loc_B7202
0xb7186  ldloc.2
0xb7187  ldstr    aChangecontrolc// "ChangeControlCommand"
0xb718c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb7191  brfalse.s loc_B71C2
0xb7193  ldarg.1
0xb7194  ldc.i4.2
0xb7195  beq.s    loc_B719E
0xb7197  call     bool Microsoft.Crm.ObjectModel.ConverterUtilities::IsMocaCustomControlFeatureAvailable()
0xb719c  brtrue.s loc_B71A0
0xb719e  ldnull
0xb719f  ret
0xb71a0  ldarg.s  8
0xb71a2  ldstr    aRetrievalactio// "RetrievalAction"
0xb71a7  ldstr    aRetrievecontro// "RetrieveControlConfigurations"
0xb71ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb71b1  ldarg.s  8
0xb71b3  ldstr    aCommandid// "CommandId"
0xb71b8  ldarg.3
0xb71b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb71be  ldnull
0xb71bf  stloc.0
0xb71c0  br.s     loc_B7202
0xb71c2  ldloc.2
0xb71c3  ldstr    aCreateemailrep// "CreateEmailReplyDraftCommand"
0xb71c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb71cd  brfalse.s loc_B7202
0xb71cf  ldloc.1
0xb71d0  ldstr    aYes// "Yes"
0xb71d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb71da  brfalse.s loc_B71F0
0xb71dc  ldarg.s  8
0xb71de  ldstr    aIsreplyaffirma// "IsReplyAffirmative"
0xb71e3  ldc.i4.1
0xb71e4  box      [mscorlib]System.Boolean
0xb71e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb71ee  br.s     loc_B7202
0xb71f0  ldarg.s  8
0xb71f2  ldstr    aIsreplyaffirma// "IsReplyAffirmative"
0xb71f7  ldc.i4.0
0xb71f8  box      [mscorlib]System.Boolean
0xb71fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb7202  ldloc.2
0xb7203  ldstr    aResizehandlesc// "resizeHandlesCommand"
0xb7208  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xb720d  brfalse.s loc_B721C
0xb720f  ldarg.s  8
0xb7211  ldstr    aRuleevaluation// "ruleEvaluationCommand"
0xb7216  ldarg.3
0xb7217  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb721c  ldloc.1
0xb721d  ldarg.0
0xb721e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xb7223  ldloc.2
0xb7224  ldarg.s  4
0xb7226  ldarg.s  5
0xb7228  ldloc.0
0xb7229  ldarg.s  6
0xb722b  ldarg.s  7
0xb722d  ldarg.s  8
0xb722f  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0xb7234  ret
```
