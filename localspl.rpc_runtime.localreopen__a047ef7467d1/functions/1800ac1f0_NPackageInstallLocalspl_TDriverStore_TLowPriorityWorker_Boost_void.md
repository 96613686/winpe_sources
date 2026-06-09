# NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost(void)

- ea: `0x1800ac1f0`
- end: `0x1800ac312`
- name: `?Boost@TLowPriorityWorker@TDriverStore@NPackageInstallLocalspl@@UEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800183d4`
- `0x1800183f4`
- `0x18003ea2c`
- `0x1800ac1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ac200`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ac200`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800ac209`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800ac260`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800ac209`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800ac260`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800ac29f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800ac29f`

## string_xrefs

- `0x1800ac234`: `GetThreadPriority`
- `0x1800ac288`: `GetThreadPriority`
- `0x1800ac242`: `NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost`
- `0x1800ac2d3`: `NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost`
- `0x1800ac2f9`: `NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost`
- `0x1800ac2c2`: `SetThreadPriority`

## pseudocode

```c
__int64 __fastcall NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost(
        NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker *this)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // edi
  signed int LastError; // eax
  void *v6; // rcx
  int v7; // ebp
  signed int v8; // eax
  const wchar_t *v9; // r8
  signed int v10; // eax

  v2 = 0;
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority == 0x7FFFFFFF )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost",
        L"%ws failed hr: 0x%x",
        L"GetThreadPriority",
        (unsigned int)v2);
  }
  NCoreLibrary::TCriticalSection::Enter((NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker *)((char *)this + 24));
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 )
  {
    v7 = GetThreadPriority(v6);
    if ( v7 == 0x7FFFFFFF )
    {
      v8 = GetLastError();
      v2 = v8;
      if ( v8 > 0 )
        v2 = (unsigned __int16)v8 | 0x80070000;
      if ( v2 < 0 )
      {
        v9 = L"GetThreadPriority";
LABEL_19:
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost",
          L"%ws failed hr: 0x%x",
          v9,
          (unsigned int)v2);
        goto LABEL_20;
      }
    }
    else if ( v2 < 0 )
    {
      goto LABEL_20;
    }
    if ( v7 < ThreadPriority && !SetThreadPriority(*((HANDLE *)this + 10), ThreadPriority) )
    {
      v10 = GetLastError();
      v2 = v10;
      if ( v10 > 0 )
        v2 = (unsigned __int16)v10 | 0x80070000;
      if ( v2 < 0 )
      {
        v9 = L"SetThreadPriority";
        goto LABEL_19;
      }
    }
  }
LABEL_20:
  *((_DWORD *)this + 22) = ThreadPriority;
  NCoreLibrary::TCriticalSection::Leave((NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker *)((char *)this + 24));
  if ( v2 < 0 )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TDriverStore::TLowPriorityWorker::Boost",
      L"Failed hr: 0x%x",
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800ac1f0  push    rbx
0x1800ac1f2  push    rbp
0x1800ac1f3  push    rsi
0x1800ac1f4  push    rdi
0x1800ac1f5  push    r14
0x1800ac1f7  sub     rsp, 20h
0x1800ac1fb  mov     rsi, rcx
0x1800ac1fe  xor     ebx, ebx
0x1800ac200  call    cs:__imp_GetCurrentThread
0x1800ac206  mov     rcx, rax; hThread
0x1800ac209  call    cs:__imp_GetThreadPriority
0x1800ac20f  mov     edi, eax
0x1800ac211  cmp     eax, 7FFFFFFFh
0x1800ac216  jnz     short loc_1800AC24E
0x1800ac218  call    cs:__imp_GetLastError
0x1800ac21e  mov     ebx, eax
0x1800ac220  test    eax, eax
0x1800ac222  jle     short loc_1800AC22D
0x1800ac224  movzx   ebx, ax
0x1800ac227  or      ebx, 80070000h
0x1800ac22d  test    ebx, ebx
0x1800ac22f  jns     short loc_1800AC24E
0x1800ac231  mov     r9d, ebx
0x1800ac234  lea     r8, aGetthreadprior; "GetThreadPriority"
0x1800ac23b  lea     rdx, aWsFailedHr0xX; "%ws failed hr: 0x%x"
0x1800ac242  lea     rcx, aNpackageinstal_14; "NPackageInstallLocalspl::TDriverStore::"...
0x1800ac249  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800ac24e  lea     rcx, [rsi+18h]; this
0x1800ac252  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x1800ac257  mov     rcx, [rsi+50h]; hThread
0x1800ac25b  test    rcx, rcx
0x1800ac25e  jz      short loc_1800AC2DF
0x1800ac260  call    cs:__imp_GetThreadPriority
0x1800ac266  mov     ebp, eax
0x1800ac268  cmp     eax, 7FFFFFFFh
0x1800ac26d  jnz     short loc_1800AC291
0x1800ac26f  call    cs:__imp_GetLastError
0x1800ac275  mov     ebx, eax
0x1800ac277  test    eax, eax
0x1800ac279  jle     short loc_1800AC284
0x1800ac27b  movzx   ebx, ax
0x1800ac27e  or      ebx, 80070000h
0x1800ac284  test    ebx, ebx
0x1800ac286  jns     short loc_1800AC295
0x1800ac288  lea     r8, aGetthreadprior; "GetThreadPriority"
0x1800ac28f  jmp     short loc_1800AC2C9
0x1800ac291  test    ebx, ebx
0x1800ac293  js      short loc_1800AC2DF
0x1800ac295  cmp     ebp, edi
0x1800ac297  jge     short loc_1800AC2DF
0x1800ac299  mov     rcx, [rsi+50h]; hThread
0x1800ac29d  mov     edx, edi; nPriority
0x1800ac29f  call    cs:__imp_SetThreadPriority
0x1800ac2a5  test    eax, eax
0x1800ac2a7  jnz     short loc_1800AC2DF
0x1800ac2a9  call    cs:__imp_GetLastError
0x1800ac2af  mov     ebx, eax
0x1800ac2b1  test    eax, eax
0x1800ac2b3  jle     short loc_1800AC2BE
0x1800ac2b5  movzx   ebx, ax
0x1800ac2b8  or      ebx, 80070000h
0x1800ac2be  test    ebx, ebx
0x1800ac2c0  jns     short loc_1800AC2DF
0x1800ac2c2  lea     r8, aSetthreadprior; "SetThreadPriority"
0x1800ac2c9  mov     r9d, ebx
0x1800ac2cc  lea     rdx, aWsFailedHr0xX; "%ws failed hr: 0x%x"
0x1800ac2d3  lea     rcx, aNpackageinstal_14; "NPackageInstallLocalspl::TDriverStore::"...
0x1800ac2da  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800ac2df  lea     rcx, [rsi+18h]; this
0x1800ac2e3  mov     [rsi+58h], edi
0x1800ac2e6  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x1800ac2eb  test    ebx, ebx
0x1800ac2ed  jns     short loc_1800AC305
0x1800ac2ef  mov     r8d, ebx
0x1800ac2f2  lea     rdx, aFailedHr0xX; "Failed hr: 0x%x"
0x1800ac2f9  lea     rcx, aNpackageinstal_14; "NPackageInstallLocalspl::TDriverStore::"...
0x1800ac300  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800ac305  mov     eax, ebx
0x1800ac307  add     rsp, 20h
0x1800ac30b  pop     r14
0x1800ac30d  pop     rdi
0x1800ac30e  pop     rsi
0x1800ac30f  pop     rbp
0x1800ac310  pop     rbx
0x1800ac311  retn
```
