# Microsoft.Xrm.Sdk.Linq.PagingCookieHelper::Deserialize

- ea: `0xa830`
- end: `0xa9c5`
- name: `Microsoft.Xrm.Sdk.Linq.PagingCookieHelper::Deserialize`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa810`

## callees

- `0x7c80`
- `0x7cb0`
- `0xa830`
- `0xabf0`

## string_xrefs

- `0xa90d`: `Malformed XML Passed to in the Paging Cookie. We expect at most two attributes (first/firstNull and last/lastNull)`
- `0xa936`: `Malformed XML Passed to in the Paging Cookie. Value for attribute last was not specified, and it was not null either.`
- `0xa970`: `Malformed XML Passed to in the Paging Cookie. Value for attribute first was not specified, and it was not null either.`
- `0xa9a7`: `Malformed XML in the Paging Cookie`
- `0xa9b6`: `Malformed XML in the Paging Cookie`

## pseudocode

```c

```

## disassembly

```asm
0xa830  ldarg.1
0xa831  ldstr    aPagenumber// "pageNumber"
0xa836  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNegative(int32 value, string parameterName)
0xa83b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0xa840  stloc.0
0xa841  ldarg.0
0xa842  call     class [System.Xml]System.Xml.XmlReader Microsoft.Xrm.Sdk.Linq.PagingCookieHelper::CreateXmlReader(string xml)
0xa847  stloc.1
0xa848  ldloc.1
0xa849  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa84e  pop
0xa84f  ldloc.0
0xa850  ldarg.1
0xa851  box      [mscorlib]System.Int32
0xa856  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa85b  ldloc.1
0xa85c  ldstr    aParententityid// "parentEntityId"
0xa861  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa866  stloc.2
0xa867  ldloc.2
0xa868  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa86d  brtrue   loc_A98C
0xa872  ldloc.0
0xa873  ldloc.2
0xa874  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa879  box      [mscorlib]System.Guid
0xa87e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa883  ldloc.1
0xa884  ldstr    aParentattribut// "parentAttributeName"
0xa889  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa88e  stloc.3
0xa88f  ldloc.3
0xa890  ldstr    aParentattribut// "parentAttributeName"
0xa895  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNullOrEmpty(string parameter, string name)
0xa89a  ldloc.0
0xa89b  ldloc.3
0xa89c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa8a1  ldc.i4.m1
0xa8a2  stloc.s  4
0xa8a4  ldloc.1
0xa8a5  ldstr    aParententityob// "parentEntityObjectTypeCode"
0xa8aa  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa8af  ldloca.s 4
0xa8b1  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xa8b6  brfalse.s loc_A8CA
0xa8b8  ldloc.0
0xa8b9  ldloc.s  4
0xa8bb  box      [mscorlib]System.Int32
0xa8c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa8c5  br       loc_A98C
0xa8ca  ldloc.s  4
0xa8cc  ldstr    aParentotc// "parentOtc"
0xa8d1  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNegative(int32 value, string parameterName)
0xa8d6  br       loc_A98C
0xa8db  ldloc.1
0xa8dc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa8e1  ldc.i4.s 0xF
0xa8e3  beq      loc_A98C
0xa8e8  ldloc.1
0xa8e9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xa8ee  stloc.s  5
0xa8f0  ldloc.s  5
0xa8f2  ldstr    aField// "field"
0xa8f7  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNullOrEmpty(string parameter, string name)
0xa8fc  ldloc.0
0xa8fd  ldloc.s  5
0xa8ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa904  ldloc.1
0xa905  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0xa90a  ldc.i4.2
0xa90b  beq.s    loc_A918
0xa90d  ldstr    aMalformedXmlPa// "Malformed XML Passed to in the Paging C"...
0xa912  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xa917  throw
0xa918  ldloc.1
0xa919  ldstr    aLast// "last"
0xa91e  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa923  stloc.s  6
0xa925  ldloc.s  6
0xa927  brtrue.s loc_A94A
0xa929  ldloc.1
0xa92a  ldstr    aLastnull// "lastnull"
0xa92f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa934  brtrue.s loc_A941
0xa936  ldstr    aMalformedXmlPa_0// "Malformed XML Passed to in the Paging C"...
0xa93b  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xa940  throw
0xa941  ldloc.0
0xa942  ldnull
0xa943  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa948  br.s     loc_A952
0xa94a  ldloc.0
0xa94b  ldloc.s  6
0xa94d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa952  ldloc.1
0xa953  ldstr    aFirst// "first"
0xa958  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa95d  stloc.s  7
0xa95f  ldloc.s  7
0xa961  brtrue.s loc_A984
0xa963  ldloc.1
0xa964  ldstr    aFirstnull// "firstnull"
0xa969  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa96e  brtrue.s loc_A97B
0xa970  ldstr    aMalformedXmlPa_1// "Malformed XML Passed to in the Paging C"...
0xa975  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xa97a  throw
0xa97b  ldloc.0
0xa97c  ldnull
0xa97d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa982  br.s     loc_A98C
0xa984  ldloc.0
0xa985  ldloc.s  7
0xa987  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xa98c  ldloc.1
0xa98d  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa992  brtrue   loc_A8DB
0xa997  leave.s  loc_A9A3
0xa999  ldloc.1
0xa99a  brfalse.s loc_A9A2
0xa99c  ldloc.1
0xa99d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9a2  endfinally
0xa9a3  leave.s  loc_A9C3
0xa9a5  stloc.s  8
0xa9a7  ldstr    aMalformedXmlIn// "Malformed XML in the Paging Cookie"
0xa9ac  ldloc.s  8
0xa9ae  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string, class [mscorlib]System.Exception)
0xa9b3  throw
0xa9b4  stloc.s  9
0xa9b6  ldstr    aMalformedXmlIn// "Malformed XML in the Paging Cookie"
0xa9bb  ldloc.s  9
0xa9bd  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string, class [mscorlib]System.Exception)
0xa9c2  throw
0xa9c3  ldloc.0
0xa9c4  ret
```
