# DllCanUnloadNow

- ea: `0x18000dee0`
- end: `0x18000deee`
- name: `DllCanUnloadNow`
- size: `14`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000dee7`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x18000dee0  lea     rcx, gPFactory
0x18000dee7  jmp     cs:__imp_NdrDllCanUnloadNow
```
