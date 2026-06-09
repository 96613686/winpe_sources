# DllCanUnloadNow

- ea: `0x18000b780`
- end: `0x18000b7a6`
- name: `DllCanUnloadNow`
- size: `38`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b780`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000b79f`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( dword_180021C0C || g_PropPageCount )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x18000b780  cmp     cs:dword_180021C0C, 0
0x18000b787  jnz     short loc_18000B792
0x18000b789  cmp     cs:?g_PropPageCount@@3IA, 0; uint g_PropPageCount
0x18000b790  jz      short loc_18000B798
0x18000b792  mov     eax, 1
0x18000b797  retn
0x18000b798  lea     rcx, gPFactory
0x18000b79f  jmp     cs:__imp_NdrDllCanUnloadNow
```
