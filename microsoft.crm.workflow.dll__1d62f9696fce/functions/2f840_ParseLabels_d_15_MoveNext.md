# <ParseLabels>d__15::MoveNext

- ea: `0x2f840`
- end: `0x2f901`
- name: `<ParseLabels>d__15::MoveNext`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x256c0`
- `0x257b0`
- `0x2f820`
- `0x2f840`
- `0x2f910`

## pseudocode

```c

```

## disassembly

```asm
0x2f840  ldarg.0
0x2f841  ldfld    int32 <ParseLabels>d__15::<>1__state
0x2f846  stloc.1
0x2f847  ldarg.0
0x2f848  ldfld    class Microsoft.Crm.Workflow.ObjectModel.FormXmlParser <ParseLabels>d__15::<>4__this
0x2f84d  stloc.2
0x2f84e  ldloc.1
0x2f84f  brfalse.s loc_2F85C
0x2f851  ldloc.1
0x2f852  ldc.i4.1
0x2f853  beq.s    loc_2F8D2
0x2f855  ldc.i4.0
0x2f856  stloc.0
0x2f857  leave    loc_2F8FF
0x2f85c  ldarg.0
0x2f85d  ldc.i4.m1
0x2f85e  stfld    int32 <ParseLabels>d__15::<>1__state
0x2f863  ldarg.0
0x2f864  ldloc.2
0x2f865  ldarg.0
0x2f866  ldfld    class [System.Xml]System.Xml.XmlNode <ParseLabels>d__15::node
0x2f86b  ldstr    aId_2// "id"
0x2f870  call     instance string Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::TryGetIdAttributeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string attributeName)
0x2f875  stfld    string <ParseLabels>d__15::<labelParentId>5__2
0x2f87a  ldarg.0
0x2f87b  ldfld    class [System.Xml]System.Xml.XmlNode <ParseLabels>d__15::node
0x2f880  ldstr    aLabelsLabel// "labels/label"
0x2f885  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2f88a  stloc.3
0x2f88b  ldarg.0
0x2f88c  ldloc.3
0x2f88d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2f892  stfld    class [mscorlib]System.Collections.IEnumerator <ParseLabels>d__15::<>7__wrap2
0x2f897  ldarg.0
0x2f898  ldc.i4.s 0xFD
0x2f89a  stfld    int32 <ParseLabels>d__15::<>1__state
0x2f89f  br.s     loc_2F8DA
0x2f8a1  ldarg.0
0x2f8a2  ldfld    class [mscorlib]System.Collections.IEnumerator <ParseLabels>d__15::<>7__wrap2
0x2f8a7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2f8ac  castclass [System.Xml]System.Xml.XmlNode
0x2f8b1  stloc.s  4
0x2f8b3  ldarg.0
0x2f8b4  ldloc.2
0x2f8b5  ldloc.s  4
0x2f8b7  ldarg.0
0x2f8b8  ldfld    string <ParseLabels>d__15::<labelParentId>5__2
0x2f8bd  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::ParseLabelStep(class [System.Xml]System.Xml.XmlNode labelXmlNode, string labelParentId)
0x2f8c2  stfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel <ParseLabels>d__15::<>2__current
0x2f8c7  ldarg.0
0x2f8c8  ldc.i4.1
0x2f8c9  stfld    int32 <ParseLabels>d__15::<>1__state
0x2f8ce  ldc.i4.1
0x2f8cf  stloc.0
0x2f8d0  leave.s  loc_2F8FF
0x2f8d2  ldarg.0
0x2f8d3  ldc.i4.s 0xFD
0x2f8d5  stfld    int32 <ParseLabels>d__15::<>1__state
0x2f8da  ldarg.0
0x2f8db  ldfld    class [mscorlib]System.Collections.IEnumerator <ParseLabels>d__15::<>7__wrap2
0x2f8e0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2f8e5  brtrue.s loc_2F8A1
0x2f8e7  ldarg.0
0x2f8e8  call     instance void <ParseLabels>d__15::<>m__Finally1()
0x2f8ed  ldarg.0
0x2f8ee  ldnull
0x2f8ef  stfld    class [mscorlib]System.Collections.IEnumerator <ParseLabels>d__15::<>7__wrap2
0x2f8f4  ldc.i4.0
0x2f8f5  stloc.0
0x2f8f6  leave.s  loc_2F8FF
0x2f8f8  ldarg.0
0x2f8f9  call     instance void <ParseLabels>d__15::System.IDisposable.Dispose()
0x2f8fe  endfinally
0x2f8ff  ldloc.0
0x2f900  ret
```
