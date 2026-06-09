# Locks_Initialize

- ea: `0x180019a5c`
- end: `0x180019b57`
- name: `Locks_Initialize`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007ca8`

## callees

- `0x180008030`
- `0x180019a5c`
- `0x180019b60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019aa7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019abe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019aa7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019abe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a8f`

## string_xrefs

- `0x180019a88`: `kernel32.dll`
- `0x180019a9d`: `SwitchToThread`

## pseudocode

```c
__int64 Locks_Initialize()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  unsigned int (*ProcAddress)(struct _RTL_CRITICAL_SECTION *, unsigned int); // rax

  if ( !g_fLocksInitialized )
  {
    CSimpleLock::Enter((CSimpleLock *)&g_lckInit);
    if ( !g_fLocksInitialized )
    {
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      v1 = ModuleHandleW;
      if ( ModuleHandleW )
      {
        g_pfnSwitchToThread = (int (*)(void))GetProcAddress(ModuleHandleW, "SwitchToThread");
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))GetProcAddress(v1, "TryEnterCriticalSection");
        ProcAddress = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))GetProcAddress(
                                                                                        v1,
                                                                                        "SetCriticalSectionSpinCount");
        g_pfnSetCSSpinCount = ProcAddress;
      }
      else
      {
        ProcAddress = g_pfnSetCSSpinCount;
      }
      if ( !g_pfnSwitchToThread )
        g_pfnSwitchToThread = (int (*)(void))mmcerror::SC::GetHelpID;
      if ( !g_pfnTryEnterCritSec )
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))mmcerror::SC::GetHelpID;
      if ( !ProcAddress )
        g_pfnSetCSSpinCount = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))mmcerror::SC::GetHelpID;
      g_cProcessors = NumProcessors();
      _InterlockedExchange(&g_fLocksInitialized, 1);
    }
    _InterlockedExchange((volatile __int32 *)&g_lckInit, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x180019a5c  push    rbx
0x180019a5e  sub     rsp, 20h
0x180019a62  cmp     cs:?g_fLocksInitialized@@3HA, 0; int g_fLocksInitialized
0x180019a69  jnz     loc_180019B4C
0x180019a6f  lea     rcx, ?g_lckInit@@3VCSimpleLock@@A; this
0x180019a76  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180019a7b  cmp     cs:?g_fLocksInitialized@@3HA, 0; int g_fLocksInitialized
0x180019a82  jnz     loc_180019B44
0x180019a88  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180019a8f  call    cs:__imp_GetModuleHandleW
0x180019a95  mov     rbx, rax
0x180019a98  test    rax, rax
0x180019a9b  jz      short loc_180019AE4
0x180019a9d  lea     rdx, aSwitchtothread; "SwitchToThread"
0x180019aa4  mov     rcx, rax; hModule
0x180019aa7  call    cs:__imp_GetProcAddress
0x180019aad  lea     rdx, aTryentercritic; "TryEnterCriticalSection"
0x180019ab4  mov     rcx, rbx; hModule
0x180019ab7  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rax; int (*g_pfnSwitchToThread)(void)
0x180019abe  call    cs:__imp_GetProcAddress
0x180019ac4  lea     rdx, aSetcriticalsec; "SetCriticalSectionSpinCount"
0x180019acb  mov     rcx, rbx; hModule
0x180019ace  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rax; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180019ad5  call    cs:__imp_GetProcAddress
0x180019adb  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x180019ae2  jmp     short loc_180019AEB
0x180019ae4  mov     rax, cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x180019aeb  cmp     cs:?g_pfnSwitchToThread@@3P6AHXZEA, 0; int (*g_pfnSwitchToThread)(void)
0x180019af3  jnz     short loc_180019B03
0x180019af5  lea     rcx, ?GetHelpID@SC@mmcerror@@QEAAKXZ; mmcerror::SC::GetHelpID(void)
0x180019afc  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rcx; int (*g_pfnSwitchToThread)(void)
0x180019b03  cmp     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, 0; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180019b0b  jnz     short loc_180019B1B
0x180019b0d  lea     rcx, ?GetHelpID@SC@mmcerror@@QEAAKXZ; mmcerror::SC::GetHelpID(void)
0x180019b14  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rcx; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180019b1b  test    rax, rax
0x180019b1e  jnz     short loc_180019B2E
0x180019b20  lea     rcx, ?GetHelpID@SC@mmcerror@@QEAAKXZ; mmcerror::SC::GetHelpID(void)
0x180019b27  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rcx; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x180019b2e  call    NumProcessors
0x180019b33  mov     ecx, 1
0x180019b38  mov     cs:?g_cProcessors@@3KA, eax; ulong g_cProcessors
0x180019b3e  xchg    ecx, cs:?g_fLocksInitialized@@3HA; int g_fLocksInitialized
0x180019b44  xor     ecx, ecx
0x180019b46  xchg    ecx, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x180019b4c  mov     eax, 1
0x180019b51  add     rsp, 20h
0x180019b55  pop     rbx
0x180019b56  retn
```
