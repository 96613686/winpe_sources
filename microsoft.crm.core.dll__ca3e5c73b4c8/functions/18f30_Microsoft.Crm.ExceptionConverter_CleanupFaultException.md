# Microsoft.Crm.ExceptionConverter::CleanupFaultException

- ea: `0x18f30`
- end: `0x18f81`
- name: `Microsoft.Crm.ExceptionConverter::CleanupFaultException`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18cc0`
- `0x18e20`

## string_xrefs

- `0x18f36`: `PluginTrace`
- `0x18f56`: `ExceptionFromPluginConstructor`
- `0x18f66`: `ExceptionFromPluginExecute`

## pseudocode

```c

```

## disassembly

```asm
0x18f30  ldarg.0
0x18f31  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x18f36  ldstr    aPlugintrace// "PluginTrace"
0x18f3b  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x18f40  ldarg.0
0x18f41  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x18f46  ldstr    aCrmexceptionfa// "CrmExceptionFaults"
0x18f4b  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x18f50  ldarg.0
0x18f51  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x18f56  ldstr    aExceptionfromp// "ExceptionFromPluginConstructor"
0x18f5b  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x18f60  ldarg.0
0x18f61  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x18f66  ldstr    aExceptionfromp_0// "ExceptionFromPluginExecute"
0x18f6b  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x18f70  ldarg.0
0x18f71  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x18f76  ldstr    aSandbox// "Sandbox"
0x18f7b  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x18f80  ret
```
