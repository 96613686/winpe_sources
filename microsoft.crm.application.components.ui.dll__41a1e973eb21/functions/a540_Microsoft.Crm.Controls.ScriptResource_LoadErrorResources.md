# Microsoft.Crm.Controls.ScriptResource::LoadErrorResources

- ea: `0xa540`
- end: `0xa55f`
- name: `Microsoft.Crm.Controls.ScriptResource::LoadErrorResources`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa440`

## callees

- `0xa560`

## string_xrefs

- `0xa540`: `ErrorResources.xml`

## pseudocode

```c

```

## disassembly

```asm
0xa540  ldstr    aErrorresources// "ErrorResources.xml"
0xa545  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0xa54a  ldstr    aResourceid// "ResourceId"
0xa54f  ldstr    aResourceid// "ResourceId"
0xa554  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::GetResources(string path, string keyAttribute, string valueAttribute)
0xa559  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::_errorResources
0xa55e  ret
```
