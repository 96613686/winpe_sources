# DllCanUnloadNow

- ea: `0x180007450`
- end: `0x18000748a`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007450`
- `0x180034010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000745b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000745b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(void *))(g_AtlModule + 24LL))(&g_AtlModule) != 0;
  return result;
}

```

## disassembly

```asm
0x180007450  sub     rsp, 28h
0x180007454  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000745b  call    cs:__imp_NdrDllCanUnloadNow
0x180007461  test    eax, eax
0x180007463  jnz     short loc_180007485
0x180007465  mov     rax, cs:?g_AtlModule@@3VCEngineModule@@A; CEngineModule g_AtlModule
0x18000746c  lea     rcx, ?g_AtlModule@@3VCEngineModule@@A; CEngineModule g_AtlModule
0x180007473  mov     rax, [rax+18h]
0x180007477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000747c  xor     ecx, ecx
0x18000747e  test    eax, eax
0x180007480  setnz   cl
0x180007483  mov     eax, ecx
0x180007485  add     rsp, 28h
0x180007489  retn
```
