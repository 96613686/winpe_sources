# Microsoft.Crm.Sandbox.SandboxWcfConfiguration::GetQuotas

- ea: `0x7aa0`
- end: `0x7b48`
- name: `Microsoft.Crm.Sandbox.SandboxWcfConfiguration::GetQuotas`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7bf0`
- `0x7d40`

## callees

- `0x7aa0`

## pseudocode

```c

```

## disassembly

```asm
0x7aa0  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_Max()
0x7aa5  stloc.0
0x7aa6  ldarg.0
0x7aa7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7aac  ldc.i4.0
0x7aad  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7ab2  brfalse.s loc_7AC6
0x7ab4  ldloc.0
0x7ab5  ldarg.0
0x7ab6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7abb  ldc.i4.0
0x7abc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7ac1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxArrayLength(int32)
0x7ac6  ldarg.0
0x7ac7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7acc  ldc.i4.1
0x7acd  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7ad2  brfalse.s loc_7AE6
0x7ad4  ldloc.0
0x7ad5  ldarg.0
0x7ad6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7adb  ldc.i4.1
0x7adc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7ae1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxBytesPerRead(int32)
0x7ae6  ldarg.0
0x7ae7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7aec  ldc.i4.2
0x7aed  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7af2  brfalse.s loc_7B06
0x7af4  ldloc.0
0x7af5  ldarg.0
0x7af6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7afb  ldc.i4.2
0x7afc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7b01  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxDepth(int32)
0x7b06  ldarg.0
0x7b07  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b0c  ldc.i4.3
0x7b0d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7b12  brfalse.s loc_7B26
0x7b14  ldloc.0
0x7b15  ldarg.0
0x7b16  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b1b  ldc.i4.3
0x7b1c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7b21  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxNameTableCharCount(int32)
0x7b26  ldarg.0
0x7b27  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b2c  ldc.i4.4
0x7b2d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7b32  brfalse.s loc_7B46
0x7b34  ldloc.0
0x7b35  ldarg.0
0x7b36  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b3b  ldc.i4.4
0x7b3c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7b41  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxStringContentLength(int32)
0x7b46  ldloc.0
0x7b47  ret
```
