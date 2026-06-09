# GetTokenHandleWithAccess

- ea: `0x1800ca710`
- end: `0x1800ca7c9`
- name: `GetTokenHandleWithAccess`
- size: `185`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800051f0`

## callees

- `0x18003d884`
- `0x180044838`
- `0x1800547e0`
- `0x1800ca710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca779`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca746`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca771`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca746`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca75d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca75d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ca786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ca786`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ca797`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ca797`

## pseudocode

```c
__int64 __fastcall GetTokenHandleWithAccess(PHANDLE TokenHandle)
{
  unsigned int v2; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v4; // rax
  HANDLE CurrentProcess; // rax
  int v7; // eax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    v2 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000000u, 0, TokenHandle) && GetLastError() != 1008 )
    {
      v4 = GetCurrentThread();
      v2 = OpenThreadToken(v4, 0x2000000u, 1, TokenHandle);
    }
    if ( GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      return OpenProcessToken(CurrentProcess, 0x2000000u, TokenHandle);
    }
    return v2;
  }
  else
  {
    v7 = IsWindowsProtectedPrintSpoolerWorkerEnabled();
    return GetTokenHandleInternal(TokenHandle, 0x2000000u, v7 == 0);
  }
}

```

## disassembly

```asm
0x1800ca710  mov     [rsp+arg_0], rbx
0x1800ca715  push    rdi
0x1800ca716  sub     rsp, 20h
0x1800ca71a  mov     rdi, rcx
0x1800ca71d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800ca724  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800ca729  test    al, al
0x1800ca72b  jz      short loc_1800CA7A3
0x1800ca72d  mov     ebx, 1
0x1800ca732  call    cs:__imp_GetCurrentThread
0x1800ca738  mov     r9, rdi; TokenHandle
0x1800ca73b  xor     r8d, r8d; OpenAsSelf
0x1800ca73e  mov     rcx, rax; ThreadHandle
0x1800ca741  mov     edx, 2000000h; DesiredAccess
0x1800ca746  call    cs:__imp_OpenThreadToken
0x1800ca74c  test    eax, eax
0x1800ca74e  jnz     short loc_1800CA779
0x1800ca750  call    cs:__imp_GetLastError
0x1800ca756  cmp     eax, 3F0h
0x1800ca75b  jz      short loc_1800CA779
0x1800ca75d  call    cs:__imp_GetCurrentThread
0x1800ca763  mov     r9, rdi; TokenHandle
0x1800ca766  mov     r8d, ebx; OpenAsSelf
0x1800ca769  mov     rcx, rax; ThreadHandle
0x1800ca76c  mov     edx, 2000000h; DesiredAccess
0x1800ca771  call    cs:__imp_OpenThreadToken
0x1800ca777  mov     ebx, eax
0x1800ca779  call    cs:__imp_GetLastError
0x1800ca77f  cmp     eax, 3F0h
0x1800ca784  jnz     short loc_1800CA79F
0x1800ca786  call    cs:__imp_GetCurrentProcess
0x1800ca78c  mov     r8, rdi; TokenHandle
0x1800ca78f  mov     edx, 2000000h; DesiredAccess
0x1800ca794  mov     rcx, rax; ProcessHandle
0x1800ca797  call    cs:__imp_OpenProcessToken
0x1800ca79d  mov     ebx, eax
0x1800ca79f  mov     eax, ebx
0x1800ca7a1  jmp     short loc_1800CA7BE
0x1800ca7a3  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x1800ca7a8  xor     r8d, r8d
0x1800ca7ab  mov     edx, 2000000h; DesiredAccess
0x1800ca7b0  test    eax, eax
0x1800ca7b2  mov     rcx, rdi; TokenHandle
0x1800ca7b5  setz    r8b; int
0x1800ca7b9  call    ?GetTokenHandleInternal@@YAHPEAPEAXKH@Z; GetTokenHandleInternal(void * *,ulong,int)
0x1800ca7be  mov     rbx, [rsp+28h+arg_0]
0x1800ca7c3  add     rsp, 20h
0x1800ca7c7  pop     rdi
0x1800ca7c8  retn
```
