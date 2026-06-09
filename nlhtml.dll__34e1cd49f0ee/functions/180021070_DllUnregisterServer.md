# DllUnregisterServer

- ea: `0x180021070`
- end: `0x180021075`
- name: `DllUnregisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002122c`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllUnregisterServer()
{
  return HTMLUnregisterServer();
}

```

## disassembly

```asm
0x180021070  jmp     HTMLUnregisterServer
```
