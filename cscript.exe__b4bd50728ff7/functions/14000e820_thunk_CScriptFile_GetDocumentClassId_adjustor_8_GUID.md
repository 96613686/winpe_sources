# [thunk]:CScriptFile::GetDocumentClassId`adjustor{8}' (_GUID *)

- ea: `0x14000e820`
- end: `0x14000e829`
- name: `?GetDocumentClassId@CScriptFile@@W7EAAJPEAU_GUID@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000e800`

## pseudocode

```c
__int64 __fastcall CScriptFile::GetDocumentClassId(__int64 a1, unsigned __int16 **a2)
{
  return CScriptingEngine::GetDocVersionString((CScriptingEngine *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x14000e820  sub     rcx, 8; this
0x14000e824  jmp     ?GetDocVersionString@CScriptingEngine@@UEAAJPEAPEAG@Z; CScriptingEngine::GetDocVersionString(ushort * *)
```
