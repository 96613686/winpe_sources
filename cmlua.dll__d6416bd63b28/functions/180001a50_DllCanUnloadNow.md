# DllCanUnloadNow

- ea: `0x180001a50`
- end: `0x180001a7a`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001a50`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180001a5b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180001a5b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory) || dword_18000C6C0 > 0;
}

```

## disassembly

```asm
0x180001a50  sub     rsp, 28h
0x180001a54  lea     rcx, gPFactory; pPSFactoryBuffer
0x180001a5b  call    cs:__imp_NdrDllCanUnloadNow
0x180001a61  test    eax, eax
0x180001a63  jnz     short loc_180001A70
0x180001a65  cmp     cs:dword_18000C6C0, eax
0x180001a6b  setnle  al
0x180001a6e  jmp     short loc_180001A75
0x180001a70  mov     eax, 1
0x180001a75  add     rsp, 28h
0x180001a79  retn
```
