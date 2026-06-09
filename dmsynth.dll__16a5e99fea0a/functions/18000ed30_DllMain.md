# DllMain

- ea: `0x18000ed30`
- end: `0x18000edd2`
- name: `DllMain`
- size: `162`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001364`

## callees

- `0x1800040e0`
- `0x18000ed30`
- `0x18000ff10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eda6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000edbb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eda6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000edbb`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ed50`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ed50`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  CDSLinkList *v4; // rcx

  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
    {
      if ( !--dword_180020108 && dword_18001E5C8 )
      {
        dword_18001E5C8 = 0;
        DeleteCriticalSection(&CriticalSection);
      }
      if ( CControlLogic::s_fCSInitialized )
      {
        DeleteCriticalSection(&CControlLogic::s_CriticalSection);
        CControlLogic::s_fCSInitialized = 0;
      }
    }
    return 1;
  }
  if ( ++dword_180020108 != 1 )
    return 1;
  DisableThreadLibraryCalls(hinstDLL);
  g_hModule = hinstDLL;
  return (unsigned int)CDSLinkList::OpenUp(v4) && CControlLogic::InitCriticalSection() != 0;
}

```

## disassembly

```asm
0x18000ed30  push    rbx
0x18000ed32  sub     rsp, 20h
0x18000ed36  mov     rbx, rcx
0x18000ed39  cmp     edx, 1
0x18000ed3c  jnz     short loc_18000ED82
0x18000ed3e  mov     eax, cs:dword_180020108
0x18000ed44  inc     eax
0x18000ed46  mov     cs:dword_180020108, eax
0x18000ed4c  cmp     eax, edx
0x18000ed4e  jnz     short loc_18000EDC7
0x18000ed50  call    cs:__imp_DisableThreadLibraryCalls
0x18000ed56  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hModule
0x18000ed5d  call    ?OpenUp@CDSLinkList@@QEAAHXZ; CDSLinkList::OpenUp(void)
0x18000ed62  test    eax, eax
0x18000ed64  jz      short loc_18000ED7A
0x18000ed66  call    ?InitCriticalSection@CControlLogic@@SAHXZ; CControlLogic::InitCriticalSection(void)
0x18000ed6b  xor     ebx, ebx
0x18000ed6d  test    eax, eax
0x18000ed6f  setnz   bl
0x18000ed72  mov     eax, ebx
0x18000ed74  add     rsp, 20h
0x18000ed78  pop     rbx
0x18000ed79  retn
0x18000ed7a  xor     eax, eax
0x18000ed7c  add     rsp, 20h
0x18000ed80  pop     rbx
0x18000ed81  retn
0x18000ed82  test    edx, edx
0x18000ed84  jnz     short loc_18000EDC7
0x18000ed86  xor     ebx, ebx
0x18000ed88  sub     cs:dword_180020108, 1
0x18000ed8f  jnz     short loc_18000EDAC
0x18000ed91  cmp     cs:dword_18001E5C8, ebx
0x18000ed97  jz      short loc_18000EDAC
0x18000ed99  lea     rcx, CriticalSection; lpCriticalSection
0x18000eda0  mov     cs:dword_18001E5C8, ebx
0x18000eda6  call    cs:__imp_DeleteCriticalSection
0x18000edac  cmp     cs:?s_fCSInitialized@CControlLogic@@2HA, ebx; int CControlLogic::s_fCSInitialized
0x18000edb2  jz      short loc_18000EDC7
0x18000edb4  lea     rcx, ?s_CriticalSection@CControlLogic@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000edbb  call    cs:__imp_DeleteCriticalSection
0x18000edc1  mov     cs:?s_fCSInitialized@CControlLogic@@2HA, ebx; int CControlLogic::s_fCSInitialized
0x18000edc7  mov     eax, 1
0x18000edcc  add     rsp, 20h
0x18000edd0  pop     rbx
0x18000edd1  retn
```
