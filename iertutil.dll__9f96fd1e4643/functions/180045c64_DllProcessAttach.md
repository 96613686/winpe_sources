# _DllProcessAttach

- ea: `0x180045c64`
- end: `0x180045cd7`
- name: `_DllProcessAttach`
- size: `115`
- prototype: `__int64 __fastcall(HMODULE hLibModule)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180045b04`

## callees

- `0x180045c64`
- `0x180045ce0`
- `0x180045d14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045c9d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180045c9d`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180045c8e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180045c8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180045c73`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180045c7f`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180045c73`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180045c7f`

## pseudocode

```c
__int64 __fastcall DllProcessAttach(HMODULE hLibModule)
{
  unsigned int v2; // ebx

  v2 = 0;
  g_tlsIEConfiguration = TlsAlloc();
  ThreadFreeLibrary::TLS = TlsAlloc();
  DisableThreadLibraryCalls(hLibModule);
  if ( InitializeCriticalSectionAndSpinCount(&g_csInit, 0) )
  {
    v2 = 1;
    byte_180298C88 = 1;
  }
  g_hinstMUI = hLibModule;
  McGenEventRegister_EventRegister();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180293010);
  return v2;
}

```

## disassembly

```asm
0x180045c64  mov     [rsp+arg_0], rbx
0x180045c69  push    rdi
0x180045c6a  sub     rsp, 20h
0x180045c6e  mov     rdi, rcx
0x180045c71  xor     ebx, ebx
0x180045c73  call    cs:__imp_TlsAlloc
0x180045c79  mov     cs:?g_tlsIEConfiguration@@3KA, eax; ulong g_tlsIEConfiguration
0x180045c7f  call    cs:__imp_TlsAlloc
0x180045c85  mov     rcx, rdi; hLibModule
0x180045c88  mov     cs:?TLS@ThreadFreeLibrary@@0KA, eax; ulong ThreadFreeLibrary::TLS
0x180045c8e  call    cs:__imp_DisableThreadLibraryCalls
0x180045c94  xor     edx, edx; dwSpinCount
0x180045c96  lea     rcx, ?g_csInit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045c9d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180045ca3  test    eax, eax
0x180045ca5  jz      short loc_180045CB2
0x180045ca7  mov     ebx, 1
0x180045cac  mov     cs:byte_180298C88, bl
0x180045cb2  mov     cs:g_hinstMUI, rdi
0x180045cb9  call    McGenEventRegister_EventRegister
0x180045cbe  lea     rcx, dword_180293010; CallbackContext
0x180045cc5  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180045cca  mov     eax, ebx
0x180045ccc  mov     rbx, [rsp+28h+arg_0]
0x180045cd1  add     rsp, 20h
0x180045cd5  pop     rdi
0x180045cd6  retn
```
