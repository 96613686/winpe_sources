# DllCanUnloadNow

- ea: `0x180013cf0`
- end: `0x180013d4c`
- name: `DllCanUnloadNow`
- size: `92`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180013cf0`
- `0x180014410`
- `0x18005c010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180013cfd`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180013cfd`

## string_xrefs

- `0x180013d31`: `DllCanUnloadNow`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax
  int v1; // eax
  __int64 v2; // rcx
  _BOOL8 v3; // rbx

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
  {
    v1 = (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule);
    v3 = v1 != 0;
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
      McTemplateU0sd_EventWriteTransfer(v2, mbaeapi_cpp115, "DllCanUnloadNow", v1 != 0);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180013cf0  push    rbx
0x180013cf2  sub     rsp, 20h
0x180013cf6  lea     rcx, gPFactory; pPSFactoryBuffer
0x180013cfd  call    cs:__imp_NdrDllCanUnloadNow
0x180013d03  test    eax, eax
0x180013d05  jnz     short loc_180013D46
0x180013d07  mov     rax, cs:?_AtlModule@@3VCMbaeApiModule@@A; CMbaeApiModule _AtlModule
0x180013d0e  lea     rcx, ?_AtlModule@@3VCMbaeApiModule@@A; CMbaeApiModule _AtlModule
0x180013d15  mov     rax, [rax+18h]
0x180013d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d1e  xor     ebx, ebx
0x180013d20  test    eax, eax
0x180013d22  setnz   bl
0x180013d25  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180013d2c  jz      short loc_180013D44
0x180013d2e  mov     r9d, ebx
0x180013d31  lea     r8, aDllcanunloadno_0; "DllCanUnloadNow"
0x180013d38  lea     rdx, mbaeapi_cpp115
0x180013d3f  call    McTemplateU0sd_EventWriteTransfer
0x180013d44  mov     eax, ebx
0x180013d46  add     rsp, 20h
0x180013d4a  pop     rbx
0x180013d4b  retn
```
