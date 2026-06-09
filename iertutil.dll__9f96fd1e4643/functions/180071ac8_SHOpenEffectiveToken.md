# SHOpenEffectiveToken

- ea: `0x180071ac8`
- end: `0x180071b5d`
- name: `SHOpenEffectiveToken`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800719b4`
- `0x18007793c`

## callees

- `0x180053f78`
- `0x180071ac8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180071b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180071b2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180071b40`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180071b40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071b06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071b06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180071b19`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180071b19`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180071ae5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180071ae5`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, void **a2)
{
  __int64 result; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax

  InitOnceExecuteOnce(&stru_180299FB8, InitOnceDeviceFamily, 0, 0);
  if ( byte_180298C9C )
    return 2147500033LL;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a2) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, a2) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180071ac8  push    rbx
0x180071aca  sub     rsp, 20h
0x180071ace  mov     rbx, rdx
0x180071ad1  lea     rcx, stru_180299FB8; InitOnce
0x180071ad8  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180071adf  xor     r9d, r9d; Context
0x180071ae2  xor     r8d, r8d; Parameter
0x180071ae5  call    cs:__imp_InitOnceExecuteOnce
0x180071aeb  cmp     cs:byte_180298C9C, 0
0x180071af2  jz      short loc_180071AFF
0x180071af4  mov     eax, 80004001h
0x180071af9  add     rsp, 20h
0x180071afd  pop     rbx
0x180071afe  retn
0x180071aff  mov     qword ptr [rbx], 0
0x180071b06  call    cs:__imp_GetCurrentThread
0x180071b0c  xor     r8d, r8d; OpenAsSelf
0x180071b0f  mov     r9, rbx; TokenHandle
0x180071b12  mov     rcx, rax; ThreadHandle
0x180071b15  lea     edx, [r8+8]; DesiredAccess
0x180071b19  call    cs:__imp_OpenThreadToken
0x180071b1f  test    eax, eax
0x180071b21  jnz     short loc_180071B4A
0x180071b23  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180071b28  cmp     eax, 800703F0h
0x180071b2d  jnz     short loc_180071B57
0x180071b2f  call    cs:__imp_GetCurrentProcess
0x180071b35  mov     r8, rbx; TokenHandle
0x180071b38  mov     edx, 8; DesiredAccess
0x180071b3d  mov     rcx, rax; ProcessHandle
0x180071b40  call    cs:__imp_OpenProcessToken
0x180071b46  test    eax, eax
0x180071b48  jz      short loc_180071B52
0x180071b4a  xor     eax, eax
0x180071b4c  add     rsp, 20h
0x180071b50  pop     rbx
0x180071b51  retn
0x180071b52  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180071b57  add     rsp, 20h
0x180071b5b  pop     rbx
0x180071b5c  retn
```
