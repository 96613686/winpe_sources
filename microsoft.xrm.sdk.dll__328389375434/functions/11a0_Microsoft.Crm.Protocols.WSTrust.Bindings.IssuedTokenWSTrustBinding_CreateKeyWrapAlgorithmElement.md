# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateKeyWrapAlgorithmElement

- ea: `0x11a0`
- end: `0x11d8`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateKeyWrapAlgorithmElement`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf30`

## callees

- `0x11a0`

## string_xrefs

- `0x11bf`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512`

## pseudocode

```c

```

## disassembly

```asm
0x11a0  ldarg.0
0x11a1  brtrue.s loc_11AE
0x11a3  ldstr    aKeywrapalgorit// "keyWrapAlgorithm"
0x11a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11ad  throw
0x11ae  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x11b3  stloc.0
0x11b4  ldloc.0
0x11b5  ldstr    aTrust// "trust"
0x11ba  ldstr    aKeywrapalgorit_0// "KeyWrapAlgorithm"
0x11bf  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x11c4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x11c9  dup
0x11ca  ldloc.0
0x11cb  ldarg.0
0x11cc  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x11d1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x11d6  pop
0x11d7  ret
```
