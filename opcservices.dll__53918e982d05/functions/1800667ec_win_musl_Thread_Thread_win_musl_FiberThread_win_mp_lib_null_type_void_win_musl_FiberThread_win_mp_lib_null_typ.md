# win_musl::Thread::Thread(win_musl::FiberThread *,win_mp_lib::null_type,void (win_musl::FiberThread::*)(win_mp_lib::null_type))

- ea: `0x1800667ec`
- end: `0x180066921`
- name: `??$?0PEAVFiberThread@win_musl@@Vnull_type@win_mp_lib@@P801@EAAXV23@@Z@Thread@win_musl@@QEAA@PEAVFiberThread@1@Vnull_type@win_mp_lib@@P821@EAAX1@Z@Z`
- size: `309`
- prototype: `__int64 __fastcall(__int64, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180065694`

## callees

- `0x180015660`
- `0x18002db70`
- `0x18006554c`
- `0x1800667ec`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180066879`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180066879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006688c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006688c`

## pseudocode

```c
__int64 __fastcall win_musl::Thread::Thread(__int64 a1, const char *a2, unsigned int a3)
{
  DWORD *v5; // rdi
  const char **v6; // rax
  const char **v7; // r9
  HANDLE Thread; // rax
  void *v9; // rcx
  unsigned int lpThreadId; // [rsp+28h] [rbp-F0h]
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)a1 = &win_musl::Thread::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  v5 = (DWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 16) = 0;
  v6 = (const char **)operator new(0x18u, a2, a3);
  v7 = 0;
  if ( v6 )
  {
    *v6 = a2;
    v6[2] = (const char *)&win_musl::FiberThread::ThreadProc;
    v7 = v6;
  }
  Thread = CreateThread(
             0,
             0,
             win_musl::Thread::ThreadProc<win_musl::Thread::ThreadThunkData<win_musl::FiberThread *,win_mp_lib::null_type,void (win_musl::FiberThread::*)(win_mp_lib::null_type)>>,
             v7,
             0,
             v5);
  v9 = *(void **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = Thread;
  if ( v9 )
    CloseHandle(v9);
  if ( !*(_QWORD *)(a1 + 8) )
  {
    lpThreadId = win_musl::detail::GetLastErrorAsFailHR((win_musl::detail *)v9);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x59u,
      lpThreadId,
      (struct win_musl::TStringEllipseBase *)L"Unspecified error");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x1800667ec  mov     rax, rsp
0x1800667ef  push    rdi
0x1800667f0  sub     rsp, 110h
0x1800667f7  mov     [rsp+118h+var_D0], 0FFFFFFFFFFFFFFFEh
0x180066800  mov     [rax+10h], rbx
0x180066804  mov     [rax+18h], rsi
0x180066808  mov     rax, cs:__security_cookie
0x18006680f  xor     rax, rsp
0x180066812  mov     [rsp+118h+var_18], rax
0x18006681a  mov     rsi, rdx
0x18006681d  mov     rbx, rcx
0x180066820  mov     [rsp+118h+var_C8], rcx
0x180066825  lea     rax, ??_7Thread@win_musl@@6B@; const win_musl::Thread::`vftable'
0x18006682c  mov     [rcx], rax
0x18006682f  mov     qword ptr [rcx+8], 0
0x180066837  lea     rdi, [rcx+10h]
0x18006683b  mov     dword ptr [rdi], 0
0x180066841  mov     ecx, 18h; unsigned __int64
0x180066846  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18006684b  mov     [rsp+118h+var_D8], rax
0x180066850  xor     r9d, r9d; lpParameter
0x180066853  test    rax, rax
0x180066856  jnz     loc_180066909
0x18006685c  mov     [rsp+118h+var_D8], r9
0x180066861  mov     [rsp+118h+lpThreadId], rdi; lpThreadId
0x180066866  mov     [rsp+118h+dwCreationFlags], 0; dwCreationFlags
0x18006686e  lea     r8, ??$ThreadProc@U?$ThreadThunkData@PEAVFiberThread@win_musl@@Vnull_type@win_mp_lib@@P812@EAAXV34@@Z@Thread@win_musl@@@Thread@win_musl@@CAKPEAX@Z; lpStartAddress
0x180066875  xor     edx, edx; dwStackSize
0x180066877  xor     ecx, ecx; lpThreadAttributes
0x180066879  call    cs:__imp_CreateThread
0x18006687f  mov     rcx, [rbx+8]; hObject
0x180066883  mov     [rbx+8], rax
0x180066887  test    rcx, rcx
0x18006688a  jz      short loc_180066892
0x18006688c  call    cs:__imp_CloseHandle
0x180066892  cmp     qword ptr [rbx+8], 0
0x180066897  jz      short loc_1800668C1
0x180066899  mov     rax, rbx
0x18006689c  mov     rcx, [rsp+118h+var_18]
0x1800668a4  xor     rcx, rsp; StackCookie
0x1800668a7  call    __security_check_cookie
0x1800668ac  lea     r11, [rsp+118h+var_8]
0x1800668b4  mov     rbx, [r11+18h]
0x1800668b8  mov     rsi, [r11+20h]
0x1800668bc  mov     rsp, r11
0x1800668bf  pop     rdi
0x1800668c0  retn
0x1800668c1  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800668c6  nop
0x1800668c7  lea     rcx, aUnspecifiedErr; "Unspecified error"
0x1800668ce  mov     [rsp+118h+var_E8], rcx; struct win_musl::TStringEllipseBase *
0x1800668d3  mov     dword ptr [rsp+118h+lpThreadId], eax; unsigned int
0x1800668d7  mov     [rsp+118h+dwCreationFlags], 59h ; 'Y'; unsigned int
0x1800668df  lea     r9, word_180139126
0x1800668e6  lea     r8, aNoFilename; "(no filename)"
0x1800668ed  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800668f2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800668f7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800668fe  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180066903  call    _CxxThrowException_0
0x180066909  mov     [rax], rsi
0x18006690c  lea     rcx, ?ThreadProc@FiberThread@win_musl@@AEAAXVnull_type@win_mp_lib@@@Z; win_musl::FiberThread::ThreadProc(win_mp_lib::null_type)
0x180066913  mov     [rax+10h], rcx
0x180066917  cmovnz  r9, rax
0x18006691b  jmp     loc_18006685C
```
