# DllMain

- ea: `0x18000a58c`
- end: `0x18000a61a`
- name: `DllMain`
- size: `142`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004174`

## callees

- `0x180001e20`
- `0x18000a58c`
- `0x18000b104`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a5e3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a5e3`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      TlgRegisterAggregateProviderEx(&dword_180012038);
      TlgRegisterAggregateProviderEx(&qword_180012000);
      TlgRegisterAggregateProviderEx(&dword_180012070);
      wil::g_fResultOutputDebugString = 0;
      g_pfnResultLoggingCallback = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))LocationFailureReport::Report;
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    TlgUnregisterAggregateProvider(&dword_180012038, 0, lpvReserved);
    TlgUnregisterAggregateProvider(&qword_180012000, v4, v5);
    TlgUnregisterAggregateProvider(&dword_180012070, v6, v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a58c  push    rbx
0x18000a58e  sub     rsp, 20h
0x18000a592  mov     rbx, rcx
0x18000a595  mov     eax, edx
0x18000a597  test    edx, edx
0x18000a599  jz      short loc_18000A5EB
0x18000a59b  cmp     eax, 1
0x18000a59e  jz      short loc_18000A5A7
0x18000a5a0  cmp     edx, 1
0x18000a5a3  jnz     short loc_18000A60F
0x18000a5a5  jmp     short loc_18000A5E0
0x18000a5a7  lea     rcx, dword_180012038; CallbackContext
0x18000a5ae  call    TlgRegisterAggregateProviderEx
0x18000a5b3  lea     rcx, qword_180012000; CallbackContext
0x18000a5ba  call    TlgRegisterAggregateProviderEx
0x18000a5bf  lea     rcx, dword_180012070; CallbackContext
0x18000a5c6  call    TlgRegisterAggregateProviderEx
0x18000a5cb  lea     rax, ?Report@LocationFailureReport@@SAXPEAUFailureInfo@wil@@PEAG_K@Z; LocationFailureReport::Report(wil::FailureInfo *,ushort *,unsigned __int64)
0x18000a5d2  mov     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x18000a5d9  mov     cs:g_pfnResultLoggingCallback, rax
0x18000a5e0  mov     rcx, rbx; hLibModule
0x18000a5e3  call    cs:__imp_DisableThreadLibraryCalls
0x18000a5e9  jmp     short loc_18000A60F
0x18000a5eb  lea     rcx, dword_180012038
0x18000a5f2  call    TlgUnregisterAggregateProvider
0x18000a5f7  lea     rcx, qword_180012000
0x18000a5fe  call    TlgUnregisterAggregateProvider
0x18000a603  lea     rcx, dword_180012070
0x18000a60a  call    TlgUnregisterAggregateProvider
0x18000a60f  mov     eax, 1
0x18000a614  add     rsp, 20h
0x18000a618  pop     rbx
0x18000a619  retn
```
