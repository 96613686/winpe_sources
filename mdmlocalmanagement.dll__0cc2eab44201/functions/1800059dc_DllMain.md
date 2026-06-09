# DllMain

- ea: `0x1800059dc`
- end: `0x180005a78`
- name: `DllMain`
- size: `156`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800014c4`

## callees

- `0x180001008`
- `0x1800059dc`
- `0x180005b88`
- `0x180005bc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800059ed`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800059ed`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180005a39`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180005a61`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180005a39`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180005a61`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  REGHANDLE v3; // rcx
  REGHANDLE v4; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18000B000);
      TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18000B088);
      McGenEventRegister_EventRegister();
    }
  }
  else
  {
    McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
    v3 = RegHandle;
    dword_18000B088 = 0;
    RegHandle = 0;
    EventUnregister(v3);
    v4 = qword_18000B020;
    dword_18000B000 = 0;
    qword_18000B020 = 0;
    EventUnregister(v4);
  }
  return 1;
}

```

## disassembly

```asm
0x1800059dc  sub     rsp, 28h
0x1800059e0  test    edx, edx
0x1800059e2  jz      short loc_180005A18
0x1800059e4  cmp     edx, 1
0x1800059e7  jnz     loc_180005A6D
0x1800059ed  call    cs:__imp_DisableThreadLibraryCalls
0x1800059f4  nop     dword ptr [rax+rax+00h]
0x1800059f9  lea     rcx, dword_18000B000; CallbackContext
0x180005a00  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180005a05  lea     rcx, dword_18000B088; CallbackContext
0x180005a0c  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180005a11  call    McGenEventRegister_EventRegister
0x180005a16  jmp     short loc_180005A6D
0x180005a18  call    McGenEventUnregister_EventUnregister
0x180005a1d  mov     rcx, cs:RegHandle; RegHandle
0x180005a24  mov     cs:dword_18000B088, 0
0x180005a2e  mov     cs:RegHandle, 0
0x180005a39  call    cs:__imp_EventUnregister
0x180005a40  nop     dword ptr [rax+rax+00h]
0x180005a45  mov     rcx, cs:qword_18000B020; RegHandle
0x180005a4c  mov     cs:dword_18000B000, 0
0x180005a56  mov     cs:qword_18000B020, 0
0x180005a61  call    cs:__imp_EventUnregister
0x180005a68  nop     dword ptr [rax+rax+00h]
0x180005a6d  mov     eax, 1
0x180005a72  add     rsp, 28h
0x180005a76  retn
```
