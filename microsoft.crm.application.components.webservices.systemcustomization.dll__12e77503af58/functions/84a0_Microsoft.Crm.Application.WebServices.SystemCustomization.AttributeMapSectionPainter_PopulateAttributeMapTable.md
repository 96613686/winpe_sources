# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::PopulateAttributeMapTable

- ea: `0x84a0`
- end: `0x879a`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::PopulateAttributeMapTable`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x7e60`

## callees

- `0x8460`
- `0x84a0`
- `0x87a0`
- `0x8a00`
- `0x9060`

## pseudocode

```c

```

## disassembly

```asm
0x84a0  ldarg.0
0x84a1  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_mandatoryAttributesPlatformNames
0x84a6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x84ab  stloc.0
0x84ac  ldc.i4.0
0x84ad  stloc.1
0x84ae  ldarg.0
0x84af  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetMap
0x84b4  ldstr    aAttributemapsA_1// "AttributeMaps/AttributeMap[not(@Unused)"...
0x84b9  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x84be  stloc.2
0x84bf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x84c4  stloc.3
0x84c5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x84ca  newobj   instance void [mscorlib]System.Collections.Comparer::.ctor(class [mscorlib]System.Globalization.CultureInfo)
0x84cf  newobj   instance void [mscorlib]System.Collections.SortedList::.ctor(class [mscorlib]System.Collections.IComparer)
0x84d4  stloc.s  5
0x84d6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x84db  newobj   instance void [mscorlib]System.Collections.Comparer::.ctor(class [mscorlib]System.Globalization.CultureInfo)
0x84e0  newobj   instance void [mscorlib]System.Collections.SortedList::.ctor(class [mscorlib]System.Collections.IComparer)
0x84e5  stloc.s  6
0x84e7  ldloc.2
0x84e8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x84ed  stloc.s  7
0x84ef  br       loc_861E
0x84f4  ldloc.s  7
0x84f6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x84fb  castclass [System.Xml]System.Xml.XmlNode
0x8500  ldarg.0
0x8501  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8506  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::.ctor(class [System.Xml]System.Xml.XmlNode, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity)
0x850b  stloc.s  8
0x850d  ldloc.s  8
0x850f  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x8514  stloc.s  9
0x8516  ldloc.s  8
0x8518  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsInternalMapping()
0x851d  brfalse.s loc_8522
0x851f  ldc.i4.4
0x8520  stloc.s  9
0x8522  ldloc.3
0x8523  ldloc.s  8
0x8525  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_SourceColumn()
0x852a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x852f  brfalse.s loc_8542
0x8531  ldloc.s  8
0x8533  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsMandatoryAttributeMapping()
0x8538  brfalse  loc_861E
0x853d  ldc.i4.0
0x853e  stloc.s  4
0x8540  br.s     loc_8552
0x8542  ldloc.3
0x8543  ldloc.s  8
0x8545  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_SourceColumn()
0x854a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x854f  ldc.i4.1
0x8550  stloc.s  4
0x8552  ldloc.s  8
0x8554  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsMandatoryAttributeMapping()
0x8559  brfalse.s loc_8569
0x855b  ldloc.0
0x855c  ldloc.s  8
0x855e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x8563  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Remove(var<u1>)
0x8568  pop
0x8569  ldarg.0
0x856a  ldloc.s  9
0x856c  call     instance bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::IsVisibleInCurrentView(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode processCode)
0x8571  brfalse  loc_861E
0x8576  ldloc.s  8
0x8578  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsMandatoryAttributeMapping()
0x857d  brfalse  loc_860A
0x8582  ldnull
0x8583  stloc.s  0xA
0x8585  ldloc.s  8
0x8587  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x858c  brfalse.s loc_8597
0x858e  ldloc.s  8
0x8590  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_Id()
0x8595  stloc.s  0xA
0x8597  ldloc.s  8
0x8599  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsInternalMapping()
0x859e  brfalse.s loc_85A7
0x85a0  ldstr    a4Internal// "4-Internal"
0x85a5  stloc.s  0xA
0x85a7  ldarg.0
0x85a8  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x85ad  ldloc.s  8
0x85af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x85b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName(string)
0x85b9  stloc.s  0xB
0x85bb  ldloc.s  6
0x85bd  ldloc.s  0xB
0x85bf  callvirt instance bool [mscorlib]System.Collections.SortedList::ContainsKey(object)
0x85c4  brfalse.s loc_85E4
0x85c6  ldloc.s  6
0x85c8  ldloc.s  0xB
0x85ca  callvirt instance object [mscorlib]System.Collections.SortedList::get_Item(object)
0x85cf  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>
0x85d4  ldloc.s  8
0x85d6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x85db  ldloc.s  0xA
0x85dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x85e2  br.s     loc_8606
0x85e4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x85e9  stloc.s  0xC
0x85eb  ldloc.s  0xC
0x85ed  ldloc.s  8
0x85ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x85f4  ldloc.s  0xA
0x85f6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x85fb  ldloc.s  6
0x85fd  ldloc.s  0xB
0x85ff  ldloc.s  0xC
0x8601  callvirt instance void [mscorlib]System.Collections.SortedList::Add(object, object)
0x8606  ldloc.1
0x8607  ldc.i4.1
0x8608  add
0x8609  stloc.1
0x860a  ldloc.s  4
0x860c  brfalse.s loc_861E
0x860e  ldloc.s  5
0x8610  ldloc.s  8
0x8612  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_SourceColumn()
0x8617  ldloc.s  8
0x8619  callvirt instance void [mscorlib]System.Collections.SortedList::Add(object, object)
0x861e  ldloc.s  7
0x8620  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8625  brtrue   loc_84F4
0x862a  leave.s  loc_8641
0x862c  ldloc.s  7
0x862e  isinst   [mscorlib]System.IDisposable
0x8633  stloc.s  0xD
0x8635  ldloc.s  0xD
0x8637  brfalse.s loc_8640
0x8639  ldloc.s  0xD
0x863b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8640  endfinally
0x8641  ldloc.0
0x8642  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x8647  stloc.s  0xE
0x8649  br       loc_86D9
0x864e  ldloca.s 0xE
0x8650  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x8655  stloc.s  0xF
0x8657  ldnull
0x8658  stloc.s  0x10
0x865a  ldc.i4.1
0x865b  stloc.s  0x11
0x865d  ldarg.0
0x865e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8663  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_FunctoidMappedAttributes()
0x8668  ldloc.s  0xF
0x866a  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x866f  brfalse.s loc_867B
0x8671  ldc.i4.4
0x8672  stloc.s  0x11
0x8674  ldstr    a4Internal// "4-Internal"
0x8679  stloc.s  0x10
0x867b  ldarg.0
0x867c  ldloc.s  0x11
0x867e  call     instance bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::IsVisibleInCurrentView(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode processCode)
0x8683  brfalse.s loc_86D9
0x8685  ldloc.1
0x8686  ldc.i4.1
0x8687  add
0x8688  stloc.1
0x8689  ldarg.0
0x868a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x868f  ldloc.s  0xF
0x8691  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName(string)
0x8696  stloc.s  0x12
0x8698  ldloc.s  6
0x869a  ldloc.s  0x12
0x869c  callvirt instance bool [mscorlib]System.Collections.SortedList::ContainsKey(object)
0x86a1  brfalse.s loc_86BC
0x86a3  ldloc.s  6
0x86a5  ldloc.s  0x12
0x86a7  callvirt instance object [mscorlib]System.Collections.SortedList::get_Item(object)
0x86ac  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>
0x86b1  ldloc.s  0xF
0x86b3  ldloc.s  0x10
0x86b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x86ba  br.s     loc_86D9
0x86bc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x86c1  stloc.s  0x13
0x86c3  ldloc.s  0x13
0x86c5  ldloc.s  0xF
0x86c7  ldloc.s  0x10
0x86c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x86ce  ldloc.s  6
0x86d0  ldloc.s  0x12
0x86d2  ldloc.s  0x13
0x86d4  callvirt instance void [mscorlib]System.Collections.SortedList::Add(object, object)
0x86d9  ldloca.s 0xE
0x86db  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x86e0  brtrue   loc_864E
0x86e5  leave.s  loc_86F5
0x86e7  ldloca.s 0xE
0x86e9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x86ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86f4  endfinally
0x86f5  ldc.i4.0
0x86f6  stloc.s  0x14
0x86f8  br.s     loc_8714
0x86fa  ldarg.0
0x86fb  ldloc.s  5
0x86fd  ldloc.s  0x14
0x86ff  callvirt instance object [mscorlib]System.Collections.SortedList::GetByIndex(int32)
0x8704  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap
0x8709  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddAttributeToNonMandatorySection(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap attribute)
0x870e  ldloc.s  0x14
0x8710  ldc.i4.1
0x8711  add
0x8712  stloc.s  0x14
0x8714  ldloc.s  0x14
0x8716  ldloc.s  5
0x8718  callvirt instance int32 [mscorlib]System.Collections.SortedList::get_Count()
0x871d  blt.s    loc_86FA
0x871f  ldloc.s  6
0x8721  callvirt instance int32 [mscorlib]System.Collections.SortedList::get_Count()
0x8726  ldc.i4.1
0x8727  sub
0x8728  stloc.s  0x15
0x872a  br.s     loc_877F
0x872c  ldloc.s  6
0x872e  ldloc.s  0x15
0x8730  callvirt instance object [mscorlib]System.Collections.SortedList::GetByIndex(int32)
0x8735  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>
0x873a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x873f  stloc.s  0x16
0x8741  br.s     loc_8760
0x8743  ldloca.s 0x16
0x8745  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x874a  stloc.s  0x17
0x874c  ldarg.0
0x874d  ldloca.s 0x17
0x874f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x8754  ldloca.s 0x17
0x8756  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x875b  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddAttributeMapToMandatorySection(string crmAttributeName, string selectedValue)
0x8760  ldloca.s 0x16
0x8762  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x8767  brtrue.s loc_8743
0x8769  leave.s  loc_8779
0x876b  ldloca.s 0x16
0x876d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x8773  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8778  endfinally
0x8779  ldloc.s  0x15
0x877b  ldc.i4.1
0x877c  sub
0x877d  stloc.s  0x15
0x877f  ldloc.s  0x15
0x8781  ldc.i4.0
0x8782  bge.s    loc_872C
0x8784  ldloc.1
0x8785  brtrue.s loc_878D
0x8787  ldarg.0
0x8788  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InsertFillerRow()
0x878d  leave.s  loc_8799
0x878f  ldloc.2
0x8790  brfalse.s loc_8798
0x8792  ldloc.2
0x8793  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8798  endfinally
0x8799  ret
```
