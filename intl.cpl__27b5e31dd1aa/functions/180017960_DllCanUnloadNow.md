# DllCanUnloadNow

- ea: `0x180017960`
- end: `0x18001797d`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017960`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180017976`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( dword_18003BEFC )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x180017960  cmp     cs:dword_18003BEFC, 0
0x180017967  jz      short loc_18001796F
0x180017969  mov     eax, 1
0x18001796e  retn
0x18001796f  lea     rcx, gPFactory
0x180017976  jmp     cs:__imp_NdrDllCanUnloadNow
```
