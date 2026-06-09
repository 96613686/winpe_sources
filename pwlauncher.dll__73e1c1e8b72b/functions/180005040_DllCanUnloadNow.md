# DllCanUnloadNow

- ea: `0x180005040`
- end: `0x18000507a`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005040`
- `0x180011010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000504b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000504b`

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
0x180005040  sub     rsp, 28h
0x180005044  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000504b  call    cs:__imp_NdrDllCanUnloadNow
0x180005051  test    eax, eax
0x180005053  jnz     short loc_180005075
0x180005055  mov     rax, cs:?_AtlModule@@3VCPortableWorkspaceLauncherModule@@A; CPortableWorkspaceLauncherModule _AtlModule
0x18000505c  lea     rcx, ?_AtlModule@@3VCPortableWorkspaceLauncherModule@@A; CPortableWorkspaceLauncherModule _AtlModule
0x180005063  mov     rax, [rax+18h]
0x180005067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506c  xor     ecx, ecx
0x18000506e  test    eax, eax
0x180005070  setnz   cl
0x180005073  mov     eax, ecx
0x180005075  add     rsp, 28h
0x180005079  retn
```
