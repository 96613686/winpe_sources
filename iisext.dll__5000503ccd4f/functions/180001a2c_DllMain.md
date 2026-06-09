# DllMain

- ea: `0x180001a2c`
- end: `0x180001b01`
- name: `DllMain`
- size: `213`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180001314`

## callees

- `0x180001008`
- `0x180001048`
- `0x180001a2c`
- `0x1800048f4`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x180001a99`
- `KERNEL32!OutputDebugStringA` at `0x180001a99`
- `KERNEL32!DeleteCriticalSection` at `0x180001add`
- `KERNEL32!DeleteCriticalSection` at `0x180001add`
- `IisRTL!PuDeleteDebugPrintsObject` at `0x180001ac1`
- `IisRTL!PuDeleteDebugPrintsObject` at `0x180001ac1`
- `IisRTL!PuCreateDebugPrintsObject` at `0x180001a80`
- `IisRTL!PuCreateDebugPrintsObject` at `0x180001a80`
- `IisRTL!IISInitializeCriticalSection` at `0x180001a67`
- `IisRTL!IISInitializeCriticalSection` at `0x180001a67`

## string_xrefs

- `0x180001a92`: `Unable to Create Debug Print Object \n`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  DWORD v3; // edx
  struct _RTL_CRITICAL_SECTION *v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v7; // rax
  LPCRITICAL_SECTION v8; // rbx

  if ( fdwReason )
  {
    v3 = fdwReason - 1;
    if ( v3 )
    {
      if ( v3 == 2 )
        SERVER_CACHE::FlushCurrentThread();
    }
    else
    {
      v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u);
      v5 = v4;
      if ( !v4 )
      {
        g_pGlobalLock = 0;
        return 0;
      }
      IISInitializeCriticalSection(v4);
      g_pGlobalLock = v5;
      g_pDebug = PuCreateDebugPrintsObject("iisext", 15);
      if ( !g_pDebug )
        OutputDebugStringA("Unable to Create Debug Print Object \n");
      g_dwDebugFlags = 8;
    }
  }
  else
  {
    v7 = PuDeleteDebugPrintsObject(g_pDebug, fdwReason, lpvReserved);
    v8 = g_pGlobalLock;
    g_pDebug = v7;
    if ( g_pGlobalLock )
    {
      DeleteCriticalSection(g_pGlobalLock);
      operator delete(v8);
      g_pGlobalLock = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001a2c  push    rbx
0x180001a2e  sub     rsp, 20h
0x180001a32  test    edx, edx
0x180001a34  jz      loc_180001ABA
0x180001a3a  sub     edx, 1
0x180001a3d  jz      short loc_180001A52
0x180001a3f  cmp     edx, 2
0x180001a42  jnz     loc_180001AF6
0x180001a48  call    ?FlushCurrentThread@SERVER_CACHE@@SAXXZ; SERVER_CACHE::FlushCurrentThread(void)
0x180001a4d  jmp     loc_180001AF6
0x180001a52  mov     ecx, 28h ; '('; Size
0x180001a57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a5c  mov     rbx, rax
0x180001a5f  test    rax, rax
0x180001a62  jz      short loc_180001AAB
0x180001a64  mov     rcx, rax
0x180001a67  call    cs:__imp_IISInitializeCriticalSection
0x180001a6d  mov     edx, 0Fh
0x180001a72  mov     cs:?g_pGlobalLock@@3PEAVWIN32_CRITSEC@@EA, rbx; WIN32_CRITSEC * g_pGlobalLock
0x180001a79  lea     rcx, aIisext; "iisext"
0x180001a80  call    cs:__imp_PuCreateDebugPrintsObject
0x180001a86  mov     cs:g_pDebug, rax
0x180001a8d  test    rax, rax
0x180001a90  jnz     short loc_180001A9F
0x180001a92  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180001a99  call    cs:__imp_OutputDebugStringA
0x180001a9f  mov     cs:g_dwDebugFlags, 8
0x180001aa9  jmp     short loc_180001AF6
0x180001aab  mov     cs:?g_pGlobalLock@@3PEAVWIN32_CRITSEC@@EA, 0; WIN32_CRITSEC * g_pGlobalLock
0x180001ab6  xor     eax, eax
0x180001ab8  jmp     short loc_180001AFB
0x180001aba  mov     rcx, cs:g_pDebug
0x180001ac1  call    cs:__imp_PuDeleteDebugPrintsObject
0x180001ac7  mov     rbx, cs:?g_pGlobalLock@@3PEAVWIN32_CRITSEC@@EA; WIN32_CRITSEC * g_pGlobalLock
0x180001ace  mov     cs:g_pDebug, rax
0x180001ad5  test    rbx, rbx
0x180001ad8  jz      short loc_180001AF6
0x180001ada  mov     rcx, rbx; lpCriticalSection
0x180001add  call    cs:__imp_DeleteCriticalSection
0x180001ae3  mov     rcx, rbx; Block
0x180001ae6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001aeb  mov     cs:?g_pGlobalLock@@3PEAVWIN32_CRITSEC@@EA, 0; WIN32_CRITSEC * g_pGlobalLock
0x180001af6  mov     eax, 1
0x180001afb  add     rsp, 20h
0x180001aff  pop     rbx
0x180001b00  retn
```
