# Microsoft.Crm.Controls.ScriptResource::LoadMailAppResources

- ea: `0xa4a0`
- end: `0xa4e9`
- name: `Microsoft.Crm.Controls.ScriptResource::LoadMailAppResources`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa3c0`

## callees

- `0xa4a0`
- `0xa560`

## string_xrefs

- `0xa4a0`: `MailAppResources.xml`

## pseudocode

```c

```

## disassembly

```asm
0xa4a0  ldstr    aMailappresourc// "MailAppResources.xml"
0xa4a5  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0xa4aa  stloc.0
0xa4ab  ldloc.0
0xa4ac  call     bool [mscorlib]System.IO.File::Exists(string)
0xa4b1  brfalse.s loc_A4C9
0xa4b3  ldloc.0
0xa4b4  ldstr    aResourceid// "ResourceId"
0xa4b9  ldstr    aResourceid// "ResourceId"
0xa4be  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::GetResources(string path, string keyAttribute, string valueAttribute)
0xa4c3  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::_mailAppResources
0xa4c8  ret
0xa4c9  ldnull
0xa4ca  ldstr    aFile0IsNotPres// "File {0} is not present on the drive"
0xa4cf  ldc.i4.1
0xa4d0  newarr   [mscorlib]System.Object
0xa4d5  dup
0xa4d6  ldc.i4.0
0xa4d7  ldloc.0
0xa4d8  stelem.ref
0xa4d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0xa4de  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xa4e3  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::_mailAppResources
0xa4e8  ret
```
