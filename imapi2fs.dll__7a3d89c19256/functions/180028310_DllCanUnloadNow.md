# DllCanUnloadNow

- ea: `0x180028310`
- end: `0x18002834a`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180028310`
- `0x180088010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18002831b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18002831b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(__int64 *))(_AtlModule + 24))(&_AtlModule) != 0;
  return result;
}

```

## disassembly

```asm
0x180028310  sub     rsp, 28h
0x180028314  lea     rcx, gPFactory; pPSFactoryBuffer
0x18002831b  call    cs:__imp_NdrDllCanUnloadNow
0x180028321  test    eax, eax
0x180028323  jnz     short loc_180028345
0x180028325  mov     rax, cs:?_AtlModule@@3VCFileSystemImagingModule@@A; CFileSystemImagingModule _AtlModule
0x18002832c  lea     rcx, ?_AtlModule@@3VCFileSystemImagingModule@@A; CFileSystemImagingModule _AtlModule
0x180028333  mov     rax, [rax+18h]
0x180028337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002833c  xor     ecx, ecx
0x18002833e  test    eax, eax
0x180028340  setnz   cl
0x180028343  mov     eax, ecx
0x180028345  add     rsp, 28h
0x180028349  retn
```
