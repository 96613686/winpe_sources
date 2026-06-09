# Microsoft.Crm.Metadata.ViewQueryUtility::.cctor

- ea: `0x5c460`
- end: `0x5c50a`
- name: `Microsoft.Crm.Metadata.ViewQueryUtility::.cctor`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x5c471`: `componentstate`
- `0x5c481`: `fetchxml`
- `0x5c4de`: `fetchxml`
- `0x5c489`: `layoutxml`
- `0x5c4e6`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x5c460  ldc.i4.s 0xB
0x5c462  newarr   [mscorlib]System.String
0x5c467  dup
0x5c468  ldc.i4.0
0x5c469  ldstr    aReturnedtypeco// "returnedtypecode"
0x5c46e  stelem.ref
0x5c46f  dup
0x5c470  ldc.i4.1
0x5c471  ldstr    aComponentstate// "componentstate"
0x5c476  stelem.ref
0x5c477  dup
0x5c478  ldc.i4.2
0x5c479  ldstr    aDescription_0// "description"
0x5c47e  stelem.ref
0x5c47f  dup
0x5c480  ldc.i4.3
0x5c481  ldstr    aFetchxml// "fetchxml"
0x5c486  stelem.ref
0x5c487  dup
0x5c488  ldc.i4.4
0x5c489  ldstr    aLayoutxml_0// "layoutxml"
0x5c48e  stelem.ref
0x5c48f  dup
0x5c490  ldc.i4.5
0x5c491  ldstr    aIsdefault// "isdefault"
0x5c496  stelem.ref
0x5c497  dup
0x5c498  ldc.i4.6
0x5c499  ldstr    aModifiedon// "modifiedon"
0x5c49e  stelem.ref
0x5c49f  dup
0x5c4a0  ldc.i4.7
0x5c4a1  ldstr    aName// "name"
0x5c4a6  stelem.ref
0x5c4a7  dup
0x5c4a8  ldc.i4.8
0x5c4a9  ldstr    aQueryapi// "queryapi"
0x5c4ae  stelem.ref
0x5c4af  dup
0x5c4b0  ldc.i4.s 9
0x5c4b2  ldstr    aQuerytype// "querytype"
0x5c4b7  stelem.ref
0x5c4b8  dup
0x5c4b9  ldc.i4.s 0xA
0x5c4bb  ldstr    aIscustomizable// "iscustomizable"
0x5c4c0  stelem.ref
0x5c4c1  stsfld   string[] Microsoft.Crm.Metadata.ViewQueryUtility::SavedQueryColumnsToRetrieve
0x5c4c6  ldc.i4.7
0x5c4c7  newarr   [mscorlib]System.String
0x5c4cc  dup
0x5c4cd  ldc.i4.0
0x5c4ce  ldstr    aReturnedtypeco// "returnedtypecode"
0x5c4d3  stelem.ref
0x5c4d4  dup
0x5c4d5  ldc.i4.1
0x5c4d6  ldstr    aDescription_0// "description"
0x5c4db  stelem.ref
0x5c4dc  dup
0x5c4dd  ldc.i4.2
0x5c4de  ldstr    aFetchxml// "fetchxml"
0x5c4e3  stelem.ref
0x5c4e4  dup
0x5c4e5  ldc.i4.3
0x5c4e6  ldstr    aLayoutxml_0// "layoutxml"
0x5c4eb  stelem.ref
0x5c4ec  dup
0x5c4ed  ldc.i4.4
0x5c4ee  ldstr    aModifiedon// "modifiedon"
0x5c4f3  stelem.ref
0x5c4f4  dup
0x5c4f5  ldc.i4.5
0x5c4f6  ldstr    aName// "name"
0x5c4fb  stelem.ref
0x5c4fc  dup
0x5c4fd  ldc.i4.6
0x5c4fe  ldstr    aQuerytype// "querytype"
0x5c503  stelem.ref
0x5c504  stsfld   string[] Microsoft.Crm.Metadata.ViewQueryUtility::UserQueryColumnsToRetrieve
0x5c509  ret
```
