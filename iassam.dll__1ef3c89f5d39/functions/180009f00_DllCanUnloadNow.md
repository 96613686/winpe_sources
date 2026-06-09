# DllCanUnloadNow

- ea: `0x180009f00`
- end: `0x180009f23`
- name: `DllCanUnloadNow`
- size: `35`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009f00`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180009f0b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180009f0b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return dword_18004019C != 0;
  return result;
}

```

## disassembly

```asm
0x180009f00  sub     rsp, 28h
0x180009f04  lea     rcx, gPFactory; pPSFactoryBuffer
0x180009f0b  call    cs:__imp_NdrDllCanUnloadNow
0x180009f11  test    eax, eax
0x180009f13  jnz     short loc_180009F1E
0x180009f15  cmp     cs:dword_18004019C, eax
0x180009f1b  setnz   al
0x180009f1e  add     rsp, 28h
0x180009f22  retn
```
