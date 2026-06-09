# DllCanUnloadNow

- ea: `0x180001920`
- end: `0x18000194a`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001920`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000192b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000192b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory) || dword_180006640 > 0;
}

```

## disassembly

```asm
0x180001920  sub     rsp, 28h
0x180001924  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000192b  call    cs:__imp_NdrDllCanUnloadNow
0x180001931  test    eax, eax
0x180001933  jnz     short loc_180001940
0x180001935  cmp     cs:dword_180006640, eax
0x18000193b  setnle  al
0x18000193e  jmp     short loc_180001945
0x180001940  mov     eax, 1
0x180001945  add     rsp, 28h
0x180001949  retn
```
