# DllCanUnloadNow

- ea: `0x180005950`
- end: `0x18000598a`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005950`
- `0x18004a010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000595b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000595b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
  return result;
}

```

## disassembly

```asm
0x180005950  sub     rsp, 28h
0x180005954  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000595b  call    cs:__imp_NdrDllCanUnloadNow
0x180005961  test    eax, eax
0x180005963  jnz     short loc_180005985
0x180005965  mov     rax, cs:?_AtlModule@@3VCImapi2Module@@A; CImapi2Module _AtlModule
0x18000596c  lea     rcx, ?_AtlModule@@3VCImapi2Module@@A; CImapi2Module _AtlModule
0x180005973  mov     rax, [rax+18h]
0x180005977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597c  xor     ecx, ecx
0x18000597e  test    eax, eax
0x180005980  setnz   cl
0x180005983  mov     eax, ecx
0x180005985  add     rsp, 28h
0x180005989  retn
```
