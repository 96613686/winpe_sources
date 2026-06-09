# CPrivateNotificationWindow::CreateInstance(CPrivateNotificationWindowSink *,CPrivateNotificationWindow * *)

- ea: `0x1800ae8f4`
- end: `0x1800ae9d3`
- name: `?CreateInstance@CPrivateNotificationWindow@@SAJPEAVCPrivateNotificationWindowSink@@PEAPEAV1@@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct CPrivateNotificationWindowSink *, struct CPrivateNotificationWindow **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180054a30`

## callees

- `0x180003968`
- `0x18000ac48`
- `0x1800ae8f4`
- `0x1800c4010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x1800ae984`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x1800ae984`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800ae95b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800ae95b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ae946`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ae946`

## pseudocode

```c
__int64 __fastcall CPrivateNotificationWindow::CreateInstance(
        struct CPrivateNotificationWindowSink *a1,
        struct _RTL_CRITICAL_SECTION **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rax
  int Error; // ebx

  *a2 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    return (unsigned int)-2147024882;
  v4->LockCount = 1;
  v4->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CPrivateNotificationWindow::`vftable';
  v4->OwningThread = 0;
  CurrentThreadId = GetCurrentThreadId();
  v4->SpinCount = 0;
  LODWORD(v4->LockSemaphore) = CurrentThreadId;
  InitializeCriticalSection(v4 + 1);
  v4->SpinCount = (ULONG_PTR)a1;
  v6 = SHCreateWorkerWindowW(CPrivateNotificationWindow::s_NotifierWndProc, -3, 0);
  v4->OwningThread = (HANDLE)v6;
  if ( v6 )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v4->DebugInfo->Type)(v4, 1);
      return (unsigned int)Error;
    }
  }
  *a2 = v4;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800ae8f4  mov     [rsp+arg_0], rbx
0x1800ae8f9  mov     [rsp+arg_8], rsi
0x1800ae8fe  push    rdi
0x1800ae8ff  sub     rsp, 30h
0x1800ae903  mov     rsi, rdx
0x1800ae906  mov     qword ptr [rdx], 0
0x1800ae90d  mov     rbx, rcx
0x1800ae910  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ae917  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800ae91c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ae921  mov     rdi, rax
0x1800ae924  test    rax, rax
0x1800ae927  jz      loc_1800AE9BC
0x1800ae92d  lea     rax, ??_7CPrivateNotificationWindow@@6B@; const CPrivateNotificationWindow::`vftable'
0x1800ae934  mov     dword ptr [rdi+8], 1
0x1800ae93b  mov     [rdi], rax
0x1800ae93e  mov     qword ptr [rdi+10h], 0
0x1800ae946  call    cs:__imp_GetCurrentThreadId
0x1800ae94c  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800ae950  mov     qword ptr [rdi+20h], 0
0x1800ae958  mov     [rdi+18h], eax
0x1800ae95b  call    cs:__imp_InitializeCriticalSection
0x1800ae961  xor     r9d, r9d
0x1800ae964  mov     [rsp+38h+var_10], rdi
0x1800ae969  xor     r8d, r8d
0x1800ae96c  mov     [rdi+20h], rbx
0x1800ae970  lea     rcx, ?s_NotifierWndProc@CPrivateNotificationWindow@@KA_JPEAUHWND__@@I_K_J@Z; CPrivateNotificationWindow::s_NotifierWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800ae977  mov     [rsp+38h+var_18], 0
0x1800ae980  lea     rdx, [r9-3]
0x1800ae984  call    cs:__imp_SHCreateWorkerWindowW
0x1800ae98a  mov     [rdi+10h], rax
0x1800ae98e  test    rax, rax
0x1800ae991  jz      short loc_1800AE997
0x1800ae993  xor     ebx, ebx
0x1800ae995  jmp     short loc_1800AE9A2
0x1800ae997  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ae99c  mov     ebx, eax
0x1800ae99e  test    eax, eax
0x1800ae9a0  js      short loc_1800AE9A7
0x1800ae9a2  mov     [rsi], rdi
0x1800ae9a5  jmp     short loc_1800AE9C1
0x1800ae9a7  mov     rax, [rdi]
0x1800ae9aa  mov     edx, 1
0x1800ae9af  mov     rcx, rdi
0x1800ae9b2  mov     rax, [rax]
0x1800ae9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae9ba  jmp     short loc_1800AE9C1
0x1800ae9bc  mov     ebx, 8007000Eh
0x1800ae9c1  mov     rsi, [rsp+38h+arg_8]
0x1800ae9c6  mov     eax, ebx
0x1800ae9c8  mov     rbx, [rsp+38h+arg_0]
0x1800ae9cd  add     rsp, 30h
0x1800ae9d1  pop     rdi
0x1800ae9d2  retn
```
