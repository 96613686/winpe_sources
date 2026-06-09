# WorkThreadManager::CThread::StartThread(void)

- ea: `0x180007880`
- end: `0x180007ac4`
- name: `?StartThread@CThread@WorkThreadManager@@QEAAJXZ`
- size: `580`
- prototype: `__int64 __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032b10`

## callees

- `0x180007880`
- `0x18000bbc4`
- `0x18000c548`
- `0x18000cd54`
- `0x18000ec48`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800078d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800078d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000799f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000799f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180007a8f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180007a8f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180007a98`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180007a98`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000794f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000794f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007994`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000790c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000790c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007aa1`

## string_xrefs

- `0x18000789a`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x1800079c1`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x180007a03`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CThread::StartThread(WorkThreadManager::CThread *this)
{
  int started; // eax
  unsigned int v3; // ebx
  int v5; // r14d
  wil::details *v6; // rcx
  HANDLE Event; // rsi
  wil::details *v8; // rbp
  DWORD LastError; // ebx
  void *v10; // rdx
  char *Thread; // rbx
  signed int v12; // eax
  unsigned int v13; // ebp
  HMODULE v14; // r14
  DWORD v15; // esi
  int LastErrorFailHr; // eax
  unsigned int v17; // ebx
  unsigned int v18; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  started = WorkThreadManager::CThread::StartThreadCommon(this);
  v3 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C8,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)started,
      dwCreationFlags);
    return v3;
  }
  v5 = 1;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v8 = (wil::details *)*((_QWORD *)this + 6);
    if ( v8 )
    {
      LastError = GetLastError();
      wil::details::CloseHandle(v8, v10);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 6) = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C9,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        dwCreationFlags);
      return v17;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
  (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)this + 8LL))(this);
  Thread = (char *)CreateThread(0, 0, _lambda_9844335fc14345151eefcc3593dd6895_::_lambda_invoker_cdecl_, this, 4u, 0);
  if ( ((unsigned __int64)(Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v18 = *((_DWORD *)this + 37) & 0xF000;
    if ( v18 != 20480 )
    {
      if ( v18 > 0x4000 )
      {
        switch ( v18 )
        {
          case 0x6000u:
            goto LABEL_33;
          case 0x7000u:
            v5 = 2;
            goto LABEL_33;
          case 0x8000u:
            v5 = 15;
            goto LABEL_33;
        }
      }
      else
      {
        if ( v18 == 0x4000 )
        {
          v5 = -1;
          goto LABEL_33;
        }
        if ( v18 != 4096 )
        {
          if ( v18 == 0x2000 )
          {
            v5 = -15;
            goto LABEL_33;
          }
          if ( v18 == 12288 )
          {
            v5 = -2;
LABEL_33:
            SetThreadPriority(Thread, v5);
          }
        }
      }
    }
    ResumeThread(Thread);
    CloseHandle(Thread);
    return 0;
  }
  v12 = GetLastError();
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)this + 16LL))(this);
  v14 = (HMODULE)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = GetLastError();
    FreeLibrary(v14);
    SetLastError(v15);
  }
  *((_QWORD *)this + 8) = 0;
  _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
  if ( (v13 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DD,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)v13,
      dwCreationFlagsa);
  if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(Thread);
  return v13;
}

```

## disassembly

```asm
0x180007880  push    rbx
0x180007882  push    rdi
0x180007883  sub     rsp, 38h
0x180007887  mov     rdi, rcx
0x18000788a  call    ?StartThreadCommon@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::StartThreadCommon(void)
0x18000788f  mov     ebx, eax
0x180007891  test    eax, eax
0x180007893  jns     short loc_1800078B7
0x180007895  mov     rcx, [rsp+48h]; this
0x18000789a  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x1800078a1  mov     r9d, eax; char *
0x1800078a4  mov     edx, 2C8h; void *
0x1800078a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078ae  mov     eax, ebx
0x1800078b0  add     rsp, 38h
0x1800078b4  pop     rdi
0x1800078b5  pop     rbx
0x1800078b6  retn
0x1800078b7  mov     [rsp+48h+arg_0], rbp
0x1800078bc  mov     r9d, 1F0003h; dwDesiredAccess
0x1800078c2  mov     [rsp+48h+arg_8], rsi
0x1800078c7  xor     edx, edx; lpName
0x1800078c9  mov     [rsp+48h+arg_10], r14
0x1800078ce  xor     ecx, ecx; lpEventAttributes
0x1800078d0  mov     r14d, 1
0x1800078d6  mov     r8d, r14d; dwFlags
0x1800078d9  call    cs:__imp_CreateEventExW
0x1800078df  mov     rsi, rax
0x1800078e2  test    rax, rax
0x1800078e5  jz      loc_1800079EF
0x1800078eb  call    cs:__imp_GetLastError
0x1800078f1  mov     rbp, [rdi+30h]
0x1800078f5  test    rbp, rbp
0x1800078f8  jz      short loc_180007912
0x1800078fa  call    cs:__imp_GetLastError
0x180007900  mov     rcx, rbp; this
0x180007903  mov     ebx, eax
0x180007905  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000790a  mov     ecx, ebx; dwErrCode
0x18000790c  call    cs:__imp_SetLastError
0x180007912  mov     [rdi+30h], rsi
0x180007916  mov     [rsp+48h+var_18], r15
0x18000791b  lock inc cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x180007922  mov     rax, [rdi]
0x180007925  mov     rcx, rdi
0x180007928  mov     rax, [rax+8]
0x18000792c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007931  xor     r15d, r15d
0x180007934  lea     r8, ?_lambda_invoker_cdecl_@_lambda_9844335fc14345151eefcc3593dd6895_@@CAKPEAX@Z; lpStartAddress
0x18000793b  mov     [rsp+48h+lpThreadId], r15; lpThreadId
0x180007940  mov     r9, rdi; lpParameter
0x180007943  xor     edx, edx; dwStackSize
0x180007945  mov     [rsp+48h+dwCreationFlags], 4; int
0x18000794d  xor     ecx, ecx; lpThreadAttributes
0x18000794f  call    cs:__imp_CreateThread
0x180007955  mov     rbx, rax
0x180007958  inc     rax
0x18000795b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180007961  jnz     loc_180007A1E
0x180007967  call    cs:__imp_GetLastError
0x18000796d  mov     ebp, eax
0x18000796f  test    eax, eax
0x180007971  jle     short loc_18000797C
0x180007973  movzx   ebp, ax
0x180007976  or      ebp, 80070000h
0x18000797c  mov     rax, [rdi]
0x18000797f  mov     rcx, rdi
0x180007982  mov     rax, [rax+10h]
0x180007986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000798b  mov     r14, [rdi+40h]
0x18000798f  test    r14, r14
0x180007992  jz      short loc_1800079AD
0x180007994  call    cs:__imp_GetLastError
0x18000799a  mov     rcx, r14; hLibModule
0x18000799d  mov     esi, eax
0x18000799f  call    cs:__imp_FreeLibrary
0x1800079a5  mov     ecx, esi; dwErrCode
0x1800079a7  call    cs:__imp_SetLastError
0x1800079ad  mov     [rdi+40h], r15
0x1800079b1  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x1800079b8  test    ebp, ebp
0x1800079ba  jns     short loc_1800079D5
0x1800079bc  mov     rcx, [rsp+48h]; this
0x1800079c1  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x1800079c8  mov     r9d, ebp; char *
0x1800079cb  mov     edx, 2DDh; void *
0x1800079d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079d5  lea     rcx, [rbx-1]
0x1800079d9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800079dd  ja      short loc_1800079E8
0x1800079df  mov     rcx, rbx; hObject
0x1800079e2  call    cs:__imp_CloseHandle
0x1800079e8  mov     eax, ebp
0x1800079ea  jmp     loc_180007AA9
0x1800079ef  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800079f4  mov     ebx, eax
0x1800079f6  test    eax, eax
0x1800079f8  jns     loc_180007916
0x1800079fe  mov     rcx, [rsp+48h]; this
0x180007a03  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180007a0a  mov     r9d, eax; char *
0x180007a0d  mov     edx, 2C9h; void *
0x180007a12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a17  mov     eax, ebx
0x180007a19  jmp     loc_180007AAE
0x180007a1e  mov     eax, [rdi+94h]
0x180007a24  and     eax, 0F000h
0x180007a29  cmp     eax, 5000h
0x180007a2e  jz      short loc_180007A95
0x180007a30  cmp     eax, 4000h
0x180007a35  ja      short loc_180007A66
0x180007a37  jz      short loc_180007A5E
0x180007a39  cmp     eax, 1000h
0x180007a3e  jz      short loc_180007A95
0x180007a40  cmp     eax, 2000h
0x180007a45  jz      short loc_180007A56
0x180007a47  cmp     eax, 3000h
0x180007a4c  jnz     short loc_180007A95
0x180007a4e  mov     r14d, 0FFFFFFFEh
0x180007a54  jmp     short loc_180007A89
0x180007a56  mov     r14d, 0FFFFFFF1h
0x180007a5c  jmp     short loc_180007A89
0x180007a5e  mov     r14d, 0FFFFFFFFh
0x180007a64  jmp     short loc_180007A89
0x180007a66  cmp     eax, 6000h
0x180007a6b  jz      short loc_180007A89
0x180007a6d  cmp     eax, 7000h
0x180007a72  jz      short loc_180007A83
0x180007a74  cmp     eax, 8000h
0x180007a79  jnz     short loc_180007A95
0x180007a7b  mov     r14d, 0Fh
0x180007a81  jmp     short loc_180007A89
0x180007a83  mov     r14d, 2
0x180007a89  mov     edx, r14d; nPriority
0x180007a8c  mov     rcx, rbx; hThread
0x180007a8f  call    cs:__imp_SetThreadPriority
0x180007a95  mov     rcx, rbx; hThread
0x180007a98  call    cs:__imp_ResumeThread
0x180007a9e  mov     rcx, rbx; hObject
0x180007aa1  call    cs:__imp_CloseHandle
0x180007aa7  xor     eax, eax
0x180007aa9  mov     r15, [rsp+48h+var_18]
0x180007aae  mov     rsi, [rsp+48h+arg_8]
0x180007ab3  mov     rbp, [rsp+48h+arg_0]
0x180007ab8  mov     r14, [rsp+48h+arg_10]
0x180007abd  add     rsp, 38h
0x180007ac1  pop     rdi
0x180007ac2  pop     rbx
0x180007ac3  retn
```
