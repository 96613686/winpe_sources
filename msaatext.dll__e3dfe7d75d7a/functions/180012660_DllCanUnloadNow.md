# DllCanUnloadNow

- ea: `0x180012660`
- end: `0x18001268c`
- name: `DllCanUnloadNow`
- size: `44`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012660`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001266b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18001266b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( NdrDllCanUnloadNow(&gPFactory) )
    LODWORD(v0) = 1;
  else
    return dword_180024B28 != 0;
  return v0;
}

```

## disassembly

```asm
0x180012660  sub     rsp, 28h
0x180012664  lea     rcx, gPFactory; pPSFactoryBuffer
0x18001266b  call    cs:__imp_NdrDllCanUnloadNow
0x180012671  test    eax, eax
0x180012673  jz      short loc_18001267C
0x180012675  mov     eax, 1
0x18001267a  jmp     short loc_180012687
0x18001267c  xor     eax, eax
0x18001267e  cmp     cs:dword_180024B28, eax
0x180012684  setnz   al
0x180012687  add     rsp, 28h
0x18001268b  retn
```
