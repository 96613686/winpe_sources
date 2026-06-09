# RdpTaskScheduler::CleanUp(int)

- ea: `0x140088f10`
- end: `0x14008925d`
- name: `?CleanUp@RdpTaskScheduler@@UEAAJH@Z`
- size: `845`
- prototype: `__int64 __fastcall(RdpTaskScheduler *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x140088b44`

## callees

- `0x140001010`
- `0x1400026b0`
- `0x140003b08`
- `0x140003b2c`
- `0x140088f10`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x140088fe8`
- `KERNEL32!SetThreadpoolWait` at `0x140088fe8`
- `KERNEL32!CreateThread` at `0x140089177`
- `KERNEL32!CreateThread` at `0x140089177`
- `KERNEL32!FreeLibrary` at `0x140089246`
- `KERNEL32!FreeLibrary` at `0x140089246`
- `KERNEL32!SetThreadpoolTimer` at `0x140088fd5`
- `KERNEL32!SetThreadpoolTimer` at `0x140088fd5`
- `KERNEL32!CloseHandle` at `0x14008922b`
- `KERNEL32!CloseHandle` at `0x14008922b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140088f3a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140088f3a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140088f84`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140088f84`
- `KERNEL32!GetLastError` at `0x14008900c`
- `KERNEL32!GetLastError` at `0x140089186`
- `KERNEL32!GetLastError` at `0x14008900c`
- `KERNEL32!GetLastError` at `0x140089186`
- `KERNEL32!GetModuleHandleExW` at `0x140088ffe`
- `KERNEL32!GetModuleHandleExW` at `0x140088ffe`

## string_xrefs

- `0x140089057`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400890fd`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400891cd`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140088f9e`: `Task scheduler cleanup`
- `0x1400890d2`: `CLEANUP_THREADPOOL_GROUP_INFO allocation failed`
- `0x1400891a6`: `Creation of the cleanup threadpool group thread failed.`

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
  if ( (unsigned int)dword_140152118 > 4 )
  {
    v29 = "Task scheduler cleanup";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_140152118,
      (unsigned int)byte_1401439DB,
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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      LODWORD(v29) = 267;
      v25 = "Failed to get module handle to itself.";
      v30 = v13;
      v26 = "CleanUp";
      v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v28 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)word_14014398A,
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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      LODWORD(v29) = 270;
      v28 = "CLEANUP_THREADPOOL_GROUP_INFO allocation failed";
      v30 = -2147024882;
      v27 = "CleanUp";
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v25 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)word_14014393A,
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
  if ( (unsigned int)dword_140152118 > 2 )
  {
    LODWORD(v29) = 284;
    v28 = "Creation of the cleanup threadpool group thread failed.";
    v30 = v23;
    v27 = "CleanUp";
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v25 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v23,
      (unsigned int)&byte_140143A47,
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
0x140088f10  push    rbp
0x140088f12  push    rbx
0x140088f13  push    rsi
0x140088f14  push    rdi
0x140088f15  push    r12
0x140088f17  push    r14
0x140088f19  push    r15
0x140088f1b  mov     rbp, rsp
0x140088f1e  sub     rsp, 70h
0x140088f22  lea     rbx, [rcx+0E8h]
0x140088f29  mov     [rbp+phModule], 0
0x140088f31  mov     rdi, rcx
0x140088f34  mov     r12d, edx
0x140088f37  mov     rcx, rbx; SRWLock
0x140088f3a  call    cs:__imp_AcquireSRWLockExclusive
0x140088f40  mov     r15, [rdi+88h]
0x140088f47  mov     rcx, rbx; SRWLock
0x140088f4a  mov     r14, [rdi+98h]
0x140088f51  mov     rsi, [rdi+0A0h]
0x140088f58  mov     qword ptr [rdi+88h], 0
0x140088f63  mov     qword ptr [rdi+90h], 0
0x140088f6e  mov     qword ptr [rdi+98h], 0
0x140088f79  mov     qword ptr [rdi+0A0h], 0
0x140088f84  call    cs:__imp_ReleaseSRWLockExclusive
0x140088f8a  test    r15, r15
0x140088f8d  jz      loc_140089239
0x140088f93  mov     eax, cs:dword_140152118
0x140088f99  cmp     eax, 4
0x140088f9c  jbe     short loc_140088FC5
0x140088f9e  lea     rax, aTaskSchedulerC; "Task scheduler cleanup"
0x140088fa5  mov     [rbp+arg_0], rax
0x140088fa9  lea     rdx, byte_1401439DB
0x140088fb0  lea     rax, [rbp+arg_0]
0x140088fb4  lea     rcx, dword_140152118
0x140088fbb  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x140088fc0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140088fc5  test    r14, r14
0x140088fc8  jz      short loc_140088FDB
0x140088fca  xor     r9d, r9d; msWindowLength
0x140088fcd  xor     r8d, r8d; msPeriod
0x140088fd0  xor     edx, edx; pftDueTime
0x140088fd2  mov     rcx, r14; pti
0x140088fd5  call    cs:__imp_SetThreadpoolTimer
0x140088fdb  test    rsi, rsi
0x140088fde  jz      short loc_140088FEE
0x140088fe0  xor     r8d, r8d; pftTimeout
0x140088fe3  xor     edx, edx; h
0x140088fe5  mov     rcx, rsi; pwa
0x140088fe8  call    cs:__imp_SetThreadpoolWait
0x140088fee  lea     r8, [rbp+phModule]; phModule
0x140088ff2  mov     ecx, 4; dwFlags
0x140088ff7  lea     rdx, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpModuleName
0x140088ffe  call    cs:__imp_GetModuleHandleExW
0x140089004  test    eax, eax
0x140089006  jnz     loc_1400890AD
0x14008900c  call    cs:__imp_GetLastError
0x140089012  mov     ecx, eax
0x140089014  test    eax, eax
0x140089016  jle     short loc_140089021
0x140089018  movzx   ecx, ax
0x14008901b  or      ecx, 80070000h
0x140089021  mov     eax, cs:dword_140152118
0x140089027  cmp     eax, 2
0x14008902a  jbe     loc_14008923D
0x140089030  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x140089037  mov     dword ptr [rbp+arg_0], 10Bh
0x14008903e  mov     [rbp+var_20], rax
0x140089042  lea     rdx, word_14014398A
0x140089049  lea     rax, aCleanup; "CleanUp"
0x140089050  mov     [rbp+arg_10], ecx
0x140089053  mov     [rbp+var_18], rax
0x140089057  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008905e  mov     [rbp+var_10], rax
0x140089062  lea     rax, aErrorCondition; "Error condition failed"
0x140089069  mov     [rbp+var_8], rax
0x14008906d  lea     rax, [rbp+var_20]
0x140089071  mov     [rsp+70h+var_28], rax
0x140089076  lea     rax, [rbp+var_18]
0x14008907a  mov     [rsp+70h+var_30], rax
0x14008907f  lea     rax, [rbp+arg_0]
0x140089083  mov     [rsp+70h+var_38], rax
0x140089088  lea     rax, [rbp+var_10]
0x14008908c  mov     [rsp+70h+var_40], rax
0x140089091  lea     rax, [rbp+arg_10]
0x140089095  mov     [rsp+70h+lpThreadId], rax
0x14008909a  lea     rax, [rbp+var_8]
0x14008909e  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x1400890a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1400890a8  jmp     loc_14008923D
0x1400890ad  mov     ecx, 18h; Size
0x1400890b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400890b7  mov     rbx, rax
0x1400890ba  test    rax, rax
0x1400890bd  jnz     loc_140089149
0x1400890c3  mov     eax, cs:dword_140152118
0x1400890c9  cmp     eax, 2
0x1400890cc  jbe     loc_14008923D
0x1400890d2  lea     rax, aCleanupThreadp; "CLEANUP_THREADPOOL_GROUP_INFO allocatio"...
0x1400890d9  mov     dword ptr [rbp+arg_0], 10Eh
0x1400890e0  mov     [rbp+var_8], rax
0x1400890e4  lea     rdx, word_14014393A
0x1400890eb  lea     rax, aCleanup; "CleanUp"
0x1400890f2  mov     [rbp+arg_10], 8007000Eh
0x1400890f9  mov     [rbp+var_10], rax
0x1400890fd  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140089104  mov     [rbp+var_18], rax
0x140089108  lea     rax, aErrorCondition; "Error condition failed"
0x14008910f  mov     [rbp+var_20], rax
0x140089113  lea     rax, [rbp+var_8]
0x140089117  mov     [rsp+70h+var_28], rax
0x14008911c  lea     rax, [rbp+var_10]
0x140089120  mov     [rsp+70h+var_30], rax
0x140089125  lea     rax, [rbp+arg_0]
0x140089129  mov     [rsp+70h+var_38], rax
0x14008912e  lea     rax, [rbp+var_18]
0x140089132  mov     [rsp+70h+var_40], rax
0x140089137  lea     rax, [rbp+arg_10]
0x14008913b  mov     [rsp+70h+lpThreadId], rax
0x140089140  lea     rax, [rbp+var_20]
0x140089144  jmp     loc_14008909E
0x140089149  mov     [rax+8], r15
0x14008914d  lea     r8, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpStartAddress
0x140089154  mov     [rax+10h], r12d
0x140089158  mov     r9, rbx; lpParameter
0x14008915b  mov     rax, [rbp+phModule]
0x14008915f  xor     edx, edx; dwStackSize
0x140089161  mov     [rsp+70h+lpThreadId], 0; lpThreadId
0x14008916a  xor     ecx, ecx; lpThreadAttributes
0x14008916c  mov     [rbx], rax
0x14008916f  mov     [rsp+70h+dwCreationFlags], 0; dwCreationFlags
0x140089177  call    cs:__imp_CreateThread
0x14008917d  test    rax, rax
0x140089180  jnz     loc_140089228
0x140089186  call    cs:__imp_GetLastError
0x14008918c  mov     ecx, eax
0x14008918e  test    eax, eax
0x140089190  jle     short loc_14008919B
0x140089192  movzx   ecx, ax
0x140089195  or      ecx, 80070000h
0x14008919b  mov     eax, cs:dword_140152118
0x1400891a1  cmp     eax, 2
0x1400891a4  jbe     short loc_14008921E
0x1400891a6  lea     rax, aCreationOfTheC; "Creation of the cleanup threadpool grou"...
0x1400891ad  mov     dword ptr [rbp+arg_0], 11Ch
0x1400891b4  mov     [rbp+var_8], rax
0x1400891b8  lea     rdx, byte_140143A47
0x1400891bf  lea     rax, aCleanup; "CleanUp"
0x1400891c6  mov     [rbp+arg_10], ecx
0x1400891c9  mov     [rbp+var_10], rax
0x1400891cd  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400891d4  mov     [rbp+var_18], rax
0x1400891d8  lea     rax, aErrorCondition; "Error condition failed"
0x1400891df  mov     [rbp+var_20], rax
0x1400891e3  lea     rax, [rbp+var_8]
0x1400891e7  mov     [rsp+70h+var_28], rax
0x1400891ec  lea     rax, [rbp+var_10]
0x1400891f0  mov     [rsp+70h+var_30], rax
0x1400891f5  lea     rax, [rbp+arg_0]
0x1400891f9  mov     [rsp+70h+var_38], rax
0x1400891fe  lea     rax, [rbp+var_18]
0x140089202  mov     [rsp+70h+var_40], rax
0x140089207  lea     rax, [rbp+arg_10]
0x14008920b  mov     [rsp+70h+lpThreadId], rax
0x140089210  lea     rax, [rbp+var_20]
0x140089214  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x140089219  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14008921e  mov     rcx, rbx; Block
0x140089221  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140089226  jmp     short loc_14008923D
0x140089228  mov     rcx, rax; hObject
0x14008922b  call    cs:__imp_CloseHandle
0x140089231  mov     [rbp+phModule], 0
0x140089239  or      dword ptr [rdi+2Ch], 4
0x14008923d  mov     rcx, [rbp+phModule]; hLibModule
0x140089241  test    rcx, rcx
0x140089244  jz      short loc_14008924C
0x140089246  call    cs:__imp_FreeLibrary
0x14008924c  xor     eax, eax
0x14008924e  add     rsp, 70h
0x140089252  pop     r15
0x140089254  pop     r14
0x140089256  pop     r12
0x140089258  pop     rdi
0x140089259  pop     rsi
0x14008925a  pop     rbx
0x14008925b  pop     rbp
0x14008925c  retn
```
