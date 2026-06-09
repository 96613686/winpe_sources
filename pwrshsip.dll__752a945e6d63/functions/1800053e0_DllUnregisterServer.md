# DllUnregisterServer

- ea: `0x1800053e0`
- end: `0x1800053f8`
- name: `DllUnregisterServer`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `CRYPT32!CryptSIPRemoveProvider` at `0x1800053eb`
- `CRYPT32!CryptSIPRemoveProvider` at `0x1800053eb`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  CryptSIPRemoveProvider((GUID *)&guidPsSip);
  return 0;
}

```

## disassembly

```asm
0x1800053e0  sub     rsp, 28h
0x1800053e4  lea     rcx, guidPsSip; pgProv
0x1800053eb  call    cs:__imp_CryptSIPRemoveProvider
0x1800053f1  xor     eax, eax
0x1800053f3  add     rsp, 28h
0x1800053f7  retn
```
