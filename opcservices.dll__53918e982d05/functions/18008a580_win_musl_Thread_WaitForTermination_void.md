# win_musl::Thread::WaitForTermination(void)

- ea: `0x18008a580`
- end: `0x18008a633`
- name: `?WaitForTermination@Thread@win_musl@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(win_musl::Thread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18008a50c`

## callees

- `0x18002db70`
- `0x18008a580`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008a5b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008a5b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008a5c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008a5c6`

## string_xrefs

- `0x18008a5ed`: `Do not try to wait on the completion of the current thread, it just won't happen.`

## pseudocode

```c
void __fastcall win_musl::Thread::WaitForTermination(win_musl::Thread *this)
{
  int v2; // ebx
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  if ( *((_QWORD *)this + 1) && dword_1801C4F30 != -1 )
  {
    v2 = *((_DWORD *)this + 4);
    if ( v2 == GetCurrentThreadId() )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x71u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"Do not try to wait on the completion of the current thread, it just won't happen.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF);
  }
}

```

## disassembly

```asm
0x18008a580  mov     [rsp+arg_8], rbx
0x18008a585  push    rdi
0x18008a586  sub     rsp, 0F0h
0x18008a58d  mov     rax, cs:__security_cookie
0x18008a594  xor     rax, rsp
0x18008a597  mov     [rsp+0F8h+var_18], rax
0x18008a59f  cmp     qword ptr [rcx+8], 0
0x18008a5a4  mov     rdi, rcx
0x18008a5a7  jz      short loc_18008A5CC
0x18008a5a9  cmp     cs:dword_1801C4F30, 0FFFFFFFFh
0x18008a5b0  jz      short loc_18008A5CC
0x18008a5b2  mov     ebx, [rcx+10h]
0x18008a5b5  call    cs:__imp_GetCurrentThreadId
0x18008a5bb  cmp     ebx, eax
0x18008a5bd  jz      short loc_18008A5ED
0x18008a5bf  mov     rcx, [rdi+8]; hHandle
0x18008a5c3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18008a5c6  call    cs:__imp_WaitForSingleObject
0x18008a5cc  mov     rcx, [rsp+0F8h+var_18]
0x18008a5d4  xor     rcx, rsp; StackCookie
0x18008a5d7  call    __security_check_cookie
0x18008a5dc  mov     rbx, [rsp+0F8h+arg_8]
0x18008a5e4  add     rsp, 0F0h
0x18008a5eb  pop     rdi
0x18008a5ec  retn
0x18008a5ed  lea     rax, aDoNotTryToWait; "Do not try to wait on the completion of"...
0x18008a5f4  mov     [rsp+0F8h+var_C8], rax; struct win_musl::TStringEllipseBase *
0x18008a5f9  lea     r9, word_180139126
0x18008a600  mov     [rsp+0F8h+var_D0], 8000FFFFh; unsigned int
0x18008a608  lea     r8, aNoFilename; "(no filename)"
0x18008a60f  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18008a614  mov     [rsp+0F8h+var_D8], 71h ; 'q'; unsigned int
0x18008a61c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008a621  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008a628  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18008a62d  call    _CxxThrowException_0
```
