# Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap

- ea: `0x116e0`
- end: `0x116e7`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap`
- size: `7`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11350`
- `0x11380`
- `0x113e0`
- `0x115f0`
- `0x11640`
- `0x119d0`
- `0x11b10`

## pseudocode

```c

```

## disassembly

```asm
0x116e0  ldarg.0
0x116e1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::_systemComponentMap
0x116e6  ret
```
