# DllRegisterServer

- ea: `0x1800044c0`
- end: `0x1800044c3`
- name: `DllRegisterServer`
- size: `3`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002148`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return 0;
}

```

## disassembly

```asm
0x1800044c0  xor     eax, eax; DllRegisterServer
0x1800044c2  retn
```
