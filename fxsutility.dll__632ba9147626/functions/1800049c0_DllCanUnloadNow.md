# DllCanUnloadNow

- ea: `0x1800049c0`
- end: `0x1800049dd`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800049c0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800049d6`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( dword_18001EB58 )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x1800049c0  cmp     cs:dword_18001EB58, 0
0x1800049c7  jz      short loc_1800049CF
0x1800049c9  mov     eax, 1
0x1800049ce  retn
0x1800049cf  lea     rcx, gPFactory
0x1800049d6  jmp     cs:__imp_NdrDllCanUnloadNow
```
