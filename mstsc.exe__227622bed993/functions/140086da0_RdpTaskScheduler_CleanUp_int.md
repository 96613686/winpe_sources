# RdpTaskScheduler::CleanUp(int)

- ea: `0x140086da0`
- end: `0x1400870ed`
- name: `?CleanUp@RdpTaskScheduler@@UEAAJH@Z`
- size: `845`
- prototype: `__int64 __fastcall(RdpTaskScheduler *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1400869d4`

## callees

- `0x140001010`
- `0x1400026b0`
- `0x140003b08`
- `0x140003b2c`
- `0x140086da0`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x140086e78`
- `KERNEL32!SetThreadpoolWait` at `0x140086e78`
- `KERNEL32!CreateThread` at `0x140087007`
- `KERNEL32!CreateThread` at `0x140087007`
- `KERNEL32!FreeLibrary` at `0x1400870d6`
- `KERNEL32!FreeLibrary` at `0x1400870d6`
- `KERNEL32!SetThreadpoolTimer` at `0x140086e65`
- `KERNEL32!SetThreadpoolTimer` at `0x140086e65`
- `KERNEL32!CloseHandle` at `0x1400870bb`
- `KERNEL32!CloseHandle` at `0x1400870bb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140086dca`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140086dca`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140086e14`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140086e14`
- `KERNEL32!GetLastError` at `0x140086e9c`
- `KERNEL32!GetLastError` at `0x140087016`
- `KERNEL32!GetLastError` at `0x140086e9c`
- `KERNEL32!GetLastError` at `0x140087016`
- `KERNEL32!GetModuleHandleExW` at `0x140086e8e`
- `KERNEL32!GetModuleHandleExW` at `0x140086e8e`

## string_xrefs

- `0x140086ee7`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140086f8d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008705d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140086e2e`: `Task scheduler cleanup`
- `0x140086f62`: `CLEANUP_THREADPOOL_GROUP_INFO allocation failed`
- `0x140087036`: `Creation of the cleanup threadpool group thread failed.`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::CleanUp(RTL_SRWLOCK *this, int a2)
{
  RTL_SRWLOCK *v2; // rbx
  HMODULE Ptr; // r15
  struct _TP_TIMER *v6; // r14
  struct _TP_WAIT *v7; // rsi
  int v8; // r8d
  int v9; // r9d
  signed int LastError; // eax
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ecx
  HMODULE *v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  HMODULE *v18; // rbx
  HANDLE Thread; // rax
  signed int v20; // eax
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // ecx
  const char *v25; // [rsp+50h] [rbp-20h] BYREF
  const char *v26; // [rsp+58h] [rbp-18h] BYREF
  const char *v27; // [rsp+60h] [rbp-10h] BYREF
  const char *v28; // [rsp+68h] [rbp-8h] BYREF
  const char *v29; // [rsp+B0h] [rbp+40h] BYREF
  int v30; // [rsp+C0h] [rbp+50h] BYREF
  HMODULE phModule; // [rsp+C8h] [rbp+58h] BYREF

  v2 = this + 29;
  phModule = 0;
  AcquireSRWLockExclusive(this + 29);
  Ptr = (HMODULE)this[17].Ptr;
  v6 = (struct _TP_TIMER *)this[19].Ptr;
  v7 = (struct _TP_WAIT *)this[20].Ptr;
  this[17].Ptr = 0;
  this[18].Ptr = 0;
  this[19].Ptr = 0;
  this[20].Ptr = 0;
  ReleaseSRWLockExclusive(v2);
  if ( !Ptr )
    goto LABEL_24;
  if ( (unsigned int)dword_140150118 > 4 )
  {
    v29 = "Task scheduler cleanup";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_140150118,
      (unsigned int)byte_1401418A3,
      v8,
      v9,
      (__int64)&v29);
  }
  if ( v6 )
    SetThreadpoolTimer(v6, 0, 0, 0);
  if ( v7 )
    SetThreadpoolWait(v7, 0, 0);
  if ( !GetModuleHandleExW(4u, (LPCWSTR)RdpTaskScheduler::STATIC_CleanupThreadpoolGroup, &phModule) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_140150118 > 2 )
    {
      LODWORD(v29) = 267;
      v25 = "Failed to get module handle to itself.";
      v30 = v13;
      v26 = "CleanUp";
      v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v28 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)word_140141852,
        v11,
        v12,
        (__int64)&v28,
        (__int64)&v30,
        (__int64)&v27,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v25);
    }
    goto LABEL_25;
  }
  v14 = (HMODULE *)operator new(0x18u);
  v18 = v14;
  if ( !v14 )
  {
    if ( (unsigned int)dword_140150118 > 2 )
    {
      LODWORD(v29) = 270;
      v28 = "CLEANUP_THREADPOOL_GROUP_INFO allocation failed";
      v30 = -2147024882;
      v27 = "CleanUp";
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v25 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)word_140141802,
        v16,
        v17,
        (__int64)&v25,
        (__int64)&v30,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v27,
        (__int64)&v28);
    }
    goto LABEL_25;
  }
  v14[1] = Ptr;
  *((_DWORD *)v14 + 4) = a2;
  *v14 = phModule;
  Thread = CreateThread(0, 0, RdpTaskScheduler::STATIC_CleanupThreadpoolGroup, v14, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
    phModule = 0;
LABEL_24:
    HIDWORD(this[5].Ptr) |= 4u;
    goto LABEL_25;
  }
  v20 = GetLastError();
  v23 = v20;
  if ( v20 > 0 )
    v23 = (unsigned __int16)v20 | 0x80070000;
  if ( (unsigned int)dword_140150118 > 2 )
  {
    LODWORD(v29) = 284;
    v28 = "Creation of the cleanup threadpool group thread failed.";
    v30 = v23;
    v27 = "CleanUp";
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v25 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v23,
      (unsigned int)&byte_14014190F,
      v21,
      v22,
      (__int64)&v25,
      (__int64)&v30,
      (__int64)&v26,
      (__int64)&v29,
      (__int64)&v27,
      (__int64)&v28);
  }
  operator delete(v18);
LABEL_25:
  if ( phModule )
    FreeLibrary(phModule);
  return 0;
}

```

## disassembly

```asm
0x140086da0  push    rbp
0x140086da2  push    rbx
0x140086da3  push    rsi
0x140086da4  push    rdi
0x140086da5  push    r12
0x140086da7  push    r14
0x140086da9  push    r15
0x140086dab  mov     rbp, rsp
0x140086dae  sub     rsp, 70h
0x140086db2  lea     rbx, [rcx+0E8h]
0x140086db9  mov     [rbp+phModule], 0
0x140086dc1  mov     rdi, rcx
0x140086dc4  mov     r12d, edx
0x140086dc7  mov     rcx, rbx; SRWLock
0x140086dca  call    cs:__imp_AcquireSRWLockExclusive
0x140086dd0  mov     r15, [rdi+88h]
0x140086dd7  mov     rcx, rbx; SRWLock
0x140086dda  mov     r14, [rdi+98h]
0x140086de1  mov     rsi, [rdi+0A0h]
0x140086de8  mov     qword ptr [rdi+88h], 0
0x140086df3  mov     qword ptr [rdi+90h], 0
0x140086dfe  mov     qword ptr [rdi+98h], 0
0x140086e09  mov     qword ptr [rdi+0A0h], 0
0x140086e14  call    cs:__imp_ReleaseSRWLockExclusive
0x140086e1a  test    r15, r15
0x140086e1d  jz      loc_1400870C9
0x140086e23  mov     eax, cs:dword_140150118
0x140086e29  cmp     eax, 4
0x140086e2c  jbe     short loc_140086E55
0x140086e2e  lea     rax, aTaskSchedulerC; "Task scheduler cleanup"
0x140086e35  mov     [rbp+arg_0], rax
0x140086e39  lea     rdx, byte_1401418A3
0x140086e40  lea     rax, [rbp+arg_0]
0x140086e44  lea     rcx, dword_140150118
0x140086e4b  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x140086e50  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140086e55  test    r14, r14
0x140086e58  jz      short loc_140086E6B
0x140086e5a  xor     r9d, r9d; msWindowLength
0x140086e5d  xor     r8d, r8d; msPeriod
0x140086e60  xor     edx, edx; pftDueTime
0x140086e62  mov     rcx, r14; pti
0x140086e65  call    cs:__imp_SetThreadpoolTimer
0x140086e6b  test    rsi, rsi
0x140086e6e  jz      short loc_140086E7E
0x140086e70  xor     r8d, r8d; pftTimeout
0x140086e73  xor     edx, edx; h
0x140086e75  mov     rcx, rsi; pwa
0x140086e78  call    cs:__imp_SetThreadpoolWait
0x140086e7e  lea     r8, [rbp+phModule]; phModule
0x140086e82  mov     ecx, 4; dwFlags
0x140086e87  lea     rdx, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpModuleName
0x140086e8e  call    cs:__imp_GetModuleHandleExW
0x140086e94  test    eax, eax
0x140086e96  jnz     loc_140086F3D
0x140086e9c  call    cs:__imp_GetLastError
0x140086ea2  mov     ecx, eax
0x140086ea4  test    eax, eax
0x140086ea6  jle     short loc_140086EB1
0x140086ea8  movzx   ecx, ax
0x140086eab  or      ecx, 80070000h
0x140086eb1  mov     eax, cs:dword_140150118
0x140086eb7  cmp     eax, 2
0x140086eba  jbe     loc_1400870CD
0x140086ec0  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x140086ec7  mov     dword ptr [rbp+arg_0], 10Bh
0x140086ece  mov     [rbp+var_20], rax
0x140086ed2  lea     rdx, word_140141852
0x140086ed9  lea     rax, aCleanup; "CleanUp"
0x140086ee0  mov     [rbp+arg_10], ecx
0x140086ee3  mov     [rbp+var_18], rax
0x140086ee7  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140086eee  mov     [rbp+var_10], rax
0x140086ef2  lea     rax, aErrorCondition; "Error condition failed"
0x140086ef9  mov     [rbp+var_8], rax
0x140086efd  lea     rax, [rbp+var_20]
0x140086f01  mov     [rsp+70h+var_28], rax
0x140086f06  lea     rax, [rbp+var_18]
0x140086f0a  mov     [rsp+70h+var_30], rax
0x140086f0f  lea     rax, [rbp+arg_0]
0x140086f13  mov     [rsp+70h+var_38], rax
0x140086f18  lea     rax, [rbp+var_10]
0x140086f1c  mov     [rsp+70h+var_40], rax
0x140086f21  lea     rax, [rbp+arg_10]
0x140086f25  mov     [rsp+70h+lpThreadId], rax
0x140086f2a  lea     rax, [rbp+var_8]
0x140086f2e  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x140086f33  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x140086f38  jmp     loc_1400870CD
0x140086f3d  mov     ecx, 18h; Size
0x140086f42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086f47  mov     rbx, rax
0x140086f4a  test    rax, rax
0x140086f4d  jnz     loc_140086FD9
0x140086f53  mov     eax, cs:dword_140150118
0x140086f59  cmp     eax, 2
0x140086f5c  jbe     loc_1400870CD
0x140086f62  lea     rax, aCleanupThreadp; "CLEANUP_THREADPOOL_GROUP_INFO allocatio"...
0x140086f69  mov     dword ptr [rbp+arg_0], 10Eh
0x140086f70  mov     [rbp+var_8], rax
0x140086f74  lea     rdx, word_140141802
0x140086f7b  lea     rax, aCleanup; "CleanUp"
0x140086f82  mov     [rbp+arg_10], 8007000Eh
0x140086f89  mov     [rbp+var_10], rax
0x140086f8d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140086f94  mov     [rbp+var_18], rax
0x140086f98  lea     rax, aErrorCondition; "Error condition failed"
0x140086f9f  mov     [rbp+var_20], rax
0x140086fa3  lea     rax, [rbp+var_8]
0x140086fa7  mov     [rsp+70h+var_28], rax
0x140086fac  lea     rax, [rbp+var_10]
0x140086fb0  mov     [rsp+70h+var_30], rax
0x140086fb5  lea     rax, [rbp+arg_0]
0x140086fb9  mov     [rsp+70h+var_38], rax
0x140086fbe  lea     rax, [rbp+var_18]
0x140086fc2  mov     [rsp+70h+var_40], rax
0x140086fc7  lea     rax, [rbp+arg_10]
0x140086fcb  mov     [rsp+70h+lpThreadId], rax
0x140086fd0  lea     rax, [rbp+var_20]
0x140086fd4  jmp     loc_140086F2E
0x140086fd9  mov     [rax+8], r15
0x140086fdd  lea     r8, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpStartAddress
0x140086fe4  mov     [rax+10h], r12d
0x140086fe8  mov     r9, rbx; lpParameter
0x140086feb  mov     rax, [rbp+phModule]
0x140086fef  xor     edx, edx; dwStackSize
0x140086ff1  mov     [rsp+70h+lpThreadId], 0; lpThreadId
0x140086ffa  xor     ecx, ecx; lpThreadAttributes
0x140086ffc  mov     [rbx], rax
0x140086fff  mov     [rsp+70h+dwCreationFlags], 0; dwCreationFlags
0x140087007  call    cs:__imp_CreateThread
0x14008700d  test    rax, rax
0x140087010  jnz     loc_1400870B8
0x140087016  call    cs:__imp_GetLastError
0x14008701c  mov     ecx, eax
0x14008701e  test    eax, eax
0x140087020  jle     short loc_14008702B
0x140087022  movzx   ecx, ax
0x140087025  or      ecx, 80070000h
0x14008702b  mov     eax, cs:dword_140150118
0x140087031  cmp     eax, 2
0x140087034  jbe     short loc_1400870AE
0x140087036  lea     rax, aCreationOfTheC; "Creation of the cleanup threadpool grou"...
0x14008703d  mov     dword ptr [rbp+arg_0], 11Ch
0x140087044  mov     [rbp+var_8], rax
0x140087048  lea     rdx, byte_14014190F
0x14008704f  lea     rax, aCleanup; "CleanUp"
0x140087056  mov     [rbp+arg_10], ecx
0x140087059  mov     [rbp+var_10], rax
0x14008705d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140087064  mov     [rbp+var_18], rax
0x140087068  lea     rax, aErrorCondition; "Error condition failed"
0x14008706f  mov     [rbp+var_20], rax
0x140087073  lea     rax, [rbp+var_8]
0x140087077  mov     [rsp+70h+var_28], rax
0x14008707c  lea     rax, [rbp+var_10]
0x140087080  mov     [rsp+70h+var_30], rax
0x140087085  lea     rax, [rbp+arg_0]
0x140087089  mov     [rsp+70h+var_38], rax
0x14008708e  lea     rax, [rbp+var_18]
0x140087092  mov     [rsp+70h+var_40], rax
0x140087097  lea     rax, [rbp+arg_10]
0x14008709b  mov     [rsp+70h+lpThreadId], rax
0x1400870a0  lea     rax, [rbp+var_20]
0x1400870a4  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x1400870a9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1400870ae  mov     rcx, rbx; Block
0x1400870b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400870b6  jmp     short loc_1400870CD
0x1400870b8  mov     rcx, rax; hObject
0x1400870bb  call    cs:__imp_CloseHandle
0x1400870c1  mov     [rbp+phModule], 0
0x1400870c9  or      dword ptr [rdi+2Ch], 4
0x1400870cd  mov     rcx, [rbp+phModule]; hLibModule
0x1400870d1  test    rcx, rcx
0x1400870d4  jz      short loc_1400870DC
0x1400870d6  call    cs:__imp_FreeLibrary
0x1400870dc  xor     eax, eax
0x1400870de  add     rsp, 70h
0x1400870e2  pop     r15
0x1400870e4  pop     r14
0x1400870e6  pop     r12
0x1400870e8  pop     rdi
0x1400870e9  pop     rsi
0x1400870ea  pop     rbx
0x1400870eb  pop     rbp
0x1400870ec  retn
```
