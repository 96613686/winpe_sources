# Microsoft.Crm.Controls.ScriptResource::LoadMocaResources

- ea: `0xa4f0`
- end: `0xa539`
- name: `Microsoft.Crm.Controls.ScriptResource::LoadMocaResources`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa400`

## callees

- `0xa4f0`
- `0xa560`

## string_xrefs

- `0xa4f0`: `MobileClientResources.xml`

## pseudocode

```c

```

## disassembly

```asm
0xa4f0  ldstr    aMobileclientre// "MobileClientResources.xml"
0xa4f5  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0xa4fa  stloc.0
0xa4fb  ldloc.0
0xa4fc  call     bool [mscorlib]System.IO.File::Exists(string)
0xa501  brfalse.s loc_A519
0xa503  ldloc.0
0xa504  ldstr    aResourceid// "ResourceId"
0xa509  ldstr    aResourceid// "ResourceId"
0xa50e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::GetResources(string path, string keyAttribute, string valueAttribute)
0xa513  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::_mobileClientResources
0xa518  ret
0xa519  ldnull
0xa51a  ldstr    aFile0IsNotPres// "File {0} is not present on the drive"
0xa51f  ldc.i4.1
0xa520  newarr   [mscorlib]System.Object
0xa525  dup
0xa526  ldc.i4.0
0xa527  ldloc.0
0xa528  stelem.ref
0xa529  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0xa52e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xa533  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.ScriptResource::_mobileClientResources
0xa538  ret
```
