# DllCanUnloadNow

- ea: `0x180001a40`
- end: `0x180001a6f`
- name: `DllCanUnloadNow`
- size: `47`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001a40`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180001a4b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180001a4b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( NdrDllCanUnloadNow(&gPFactory) == 1 )
    LODWORD(v0) = 1;
  else
    return g_dwRefCount != 0;
  return v0;
}

```

## disassembly

```asm
0x180001a40  sub     rsp, 28h
0x180001a44  lea     rcx, gPFactory; pPSFactoryBuffer
0x180001a4b  call    cs:__imp_NdrDllCanUnloadNow
0x180001a51  cmp     eax, 1
0x180001a54  jz      short loc_180001A65
0x180001a56  mov     ecx, cs:?g_dwRefCount@@3JC; long volatile g_dwRefCount
0x180001a5c  xor     eax, eax
0x180001a5e  test    ecx, ecx
0x180001a60  setnz   al
0x180001a63  jmp     short loc_180001A6A
0x180001a65  mov     eax, 1
0x180001a6a  add     rsp, 28h
0x180001a6e  retn
```
