# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18002c6c0`
- end: `0x18002c6fe`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `62`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18002c6c0`
- `0x180042ac4`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c6ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c6ea`

## string_xrefs

- `0x18002c6e3`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE NtDllModuleHandle; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  result = GetProcAddress(NtDllModuleHandle, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x18002c6c0  sub     rsp, 28h
0x18002c6c4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18002c6cb  test    rax, rax
0x18002c6ce  jz      short loc_18002C6DB
0x18002c6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6d5  nop
0x18002c6d6  add     rsp, 28h
0x18002c6da  retn
0x18002c6db  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002c6e0  mov     rcx, rax; hModule
0x18002c6e3  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18002c6ea  call    cs:__imp_GetProcAddress
0x18002c6f0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18002c6f7  test    rax, rax
0x18002c6fa  jnz     short loc_18002C6D0
0x18002c6fc  jmp     short loc_18002C6D6
```
