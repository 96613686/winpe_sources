# Microsoft.Crm.Controls.ScriptResource::LoadScriptResources

- ea: `0xa480`
- end: `0xa49f`
- name: `Microsoft.Crm.Controls.ScriptResource::LoadScriptResources`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa380`

## callees

- `0xa560`

## string_xrefs

- `0xa480`: `ScriptResources.xml`

## pseudocode

```c

```

## disassembly

```asm
0xa480  ldstr    aScriptresource// "ScriptResources.xml"
0xa485  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0xa48a  ldstr    aClientvariable// "ClientVariableName"
0xa48f  ldstr    aResourceid// "ResourceId"
0xa494  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::GetResources(string path, string keyAttribute, string valueAttribute)
0xa499  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::_scriptResources
0xa49e  ret
```
