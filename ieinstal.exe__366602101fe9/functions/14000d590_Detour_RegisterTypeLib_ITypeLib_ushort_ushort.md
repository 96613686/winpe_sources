# Detour_RegisterTypeLib(ITypeLib *,ushort *,ushort *)

- ea: `0x14000d590`
- end: `0x14000d597`
- name: `?Detour_RegisterTypeLib@@YAJPEAUITypeLib@@PEAG1@Z`
- size: `7`
- prototype: `HRESULT __stdcall(ITypeLib *ptlib, OLECHAR *szFullPath, OLECHAR *szHelpDir)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_RegisterTypeLibForUser` at `0x14000d590`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall Detour_RegisterTypeLib(ITypeLib *ptlib, OLECHAR *szFullPath, OLECHAR *szHelpDir)
{
  return RegisterTypeLibForUser(ptlib, szFullPath, szHelpDir);
}

```

## disassembly

```asm
0x14000d590  jmp     cs:__imp_RegisterTypeLibForUser
```
