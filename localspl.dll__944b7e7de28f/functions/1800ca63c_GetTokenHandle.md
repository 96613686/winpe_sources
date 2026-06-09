# GetTokenHandle

- ea: `0x1800ca63c`
- end: `0x1800ca70a`
- name: `GetTokenHandle`
- size: `206`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `13`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180013f98`
- `0x18001ee20`
- `0x180023484`
- `0x18002ee50`
- `0x180041ba0`
- `0x18005afa4`
- `0x1800972b4`
- `0x180097a3c`
- `0x1800982c8`
- `0x180099584`
- `0x180099788`
- `0x180099cc0`
- `0x1800a0160`

## callees

- `0x18003d884`
- `0x180044838`
- `0x1800547e0`
- `0x1800ca63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca683`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca6ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca683`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca6ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca69a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca69a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ca6c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ca6c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ca6ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ca6ce`

## pseudocode

```c
__int64 __fastcall GetTokenHandle(PHANDLE TokenHandle)
{
  unsigned int v2; // ebx
  DWORD v3; // esi
  HANDLE CurrentThread; // rax
  HANDLE v5; // rax
  HANDLE CurrentProcess; // rax
  int v8; // eax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    v2 = 1;
    v3 = (unsigned int)IsWindowsProtectedPrintSpoolerWorkerEnabled() != 0 ? 8 : 40;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, v3, 0, TokenHandle) && GetLastError() != 1008 )
    {
      v5 = GetCurrentThread();
      v2 = OpenThreadToken(v5, v3, 1, TokenHandle);
    }
    if ( GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      return OpenProcessToken(CurrentProcess, v3, TokenHandle);
    }
    return v2;
  }
  else
  {
    v8 = IsWindowsProtectedPrintSpoolerWorkerEnabled();
    return GetTokenHandleInternal(TokenHandle, v8 != 0 ? 8 : 40, v8 == 0);
  }
}

```

## disassembly

```asm
0x1800ca63c  mov     [rsp+arg_0], rbx
0x1800ca641  mov     [rsp+arg_8], rsi
0x1800ca646  push    rdi
0x1800ca647  sub     rsp, 20h
0x1800ca64b  mov     rdi, rcx
0x1800ca64e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800ca655  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800ca65a  test    al, al
0x1800ca65c  jz      short loc_1800CA6DA
0x1800ca65e  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x1800ca663  neg     eax
0x1800ca665  mov     ebx, 1
0x1800ca66a  sbb     esi, esi
0x1800ca66c  and     esi, 0FFFFFFE0h
0x1800ca66f  add     esi, 28h ; '('
0x1800ca672  call    cs:__imp_GetCurrentThread
0x1800ca678  mov     r9, rdi; TokenHandle
0x1800ca67b  xor     r8d, r8d; OpenAsSelf
0x1800ca67e  mov     rcx, rax; ThreadHandle
0x1800ca681  mov     edx, esi; DesiredAccess
0x1800ca683  call    cs:__imp_OpenThreadToken
0x1800ca689  test    eax, eax
0x1800ca68b  jnz     short loc_1800CA6B3
0x1800ca68d  call    cs:__imp_GetLastError
0x1800ca693  cmp     eax, 3F0h
0x1800ca698  jz      short loc_1800CA6B3
0x1800ca69a  call    cs:__imp_GetCurrentThread
0x1800ca6a0  mov     r9, rdi; TokenHandle
0x1800ca6a3  mov     r8d, ebx; OpenAsSelf
0x1800ca6a6  mov     rcx, rax; ThreadHandle
0x1800ca6a9  mov     edx, esi; DesiredAccess
0x1800ca6ab  call    cs:__imp_OpenThreadToken
0x1800ca6b1  mov     ebx, eax
0x1800ca6b3  call    cs:__imp_GetLastError
0x1800ca6b9  cmp     eax, 3F0h
0x1800ca6be  jnz     short loc_1800CA6D6
0x1800ca6c0  call    cs:__imp_GetCurrentProcess
0x1800ca6c6  mov     r8, rdi; TokenHandle
0x1800ca6c9  mov     edx, esi; DesiredAccess
0x1800ca6cb  mov     rcx, rax; ProcessHandle
0x1800ca6ce  call    cs:__imp_OpenProcessToken
0x1800ca6d4  mov     ebx, eax
0x1800ca6d6  mov     eax, ebx
0x1800ca6d8  jmp     short loc_1800CA6FA
0x1800ca6da  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x1800ca6df  xor     r8d, r8d
0x1800ca6e2  mov     rcx, rdi; TokenHandle
0x1800ca6e5  test    eax, eax
0x1800ca6e7  setz    r8b; int
0x1800ca6eb  neg     eax
0x1800ca6ed  sbb     edx, edx
0x1800ca6ef  and     edx, 0FFFFFFE0h
0x1800ca6f2  add     edx, 28h ; '('; DesiredAccess
0x1800ca6f5  call    ?GetTokenHandleInternal@@YAHPEAPEAXKH@Z; GetTokenHandleInternal(void * *,ulong,int)
0x1800ca6fa  mov     rbx, [rsp+28h+arg_0]
0x1800ca6ff  mov     rsi, [rsp+28h+arg_8]
0x1800ca704  add     rsp, 20h
0x1800ca708  pop     rdi
0x1800ca709  retn
```
