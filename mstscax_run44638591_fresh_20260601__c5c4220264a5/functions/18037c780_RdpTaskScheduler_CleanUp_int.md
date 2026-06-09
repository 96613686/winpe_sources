# RdpTaskScheduler::CleanUp(int)

- ea: `0x18037c780`
- end: `0x18037cad0`
- name: `?CleanUp@RdpTaskScheduler@@UEAAJH@Z`
- size: `848`
- prototype: `__int64 __fastcall(RdpTaskScheduler *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18037c518`

## callees

- `0x1800054f4`
- `0x180082ad8`
- `0x18012962c`
- `0x18012966c`
- `0x18037c780`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18037ca9e`
- `KERNEL32!CloseHandle` at `0x18037ca9e`
- `KERNEL32!SetThreadpoolTimer` at `0x18037c848`
- `KERNEL32!SetThreadpoolTimer` at `0x18037c848`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18037c7f4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18037c7f4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18037c7aa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18037c7aa`
- `KERNEL32!GetModuleHandleExW` at `0x18037c871`
- `KERNEL32!GetModuleHandleExW` at `0x18037c871`
- `KERNEL32!GetLastError` at `0x18037c87f`
- `KERNEL32!GetLastError` at `0x18037c9f9`
- `KERNEL32!GetLastError` at `0x18037c87f`
- `KERNEL32!GetLastError` at `0x18037c9f9`
- `KERNEL32!FreeLibrary` at `0x18037cab9`
- `KERNEL32!FreeLibrary` at `0x18037cab9`
- `KERNEL32!CreateThread` at `0x18037c9ea`
- `KERNEL32!CreateThread` at `0x18037c9ea`
- `KERNEL32!SetThreadpoolWait` at `0x18037c85b`
- `KERNEL32!SetThreadpoolWait` at `0x18037c85b`

## string_xrefs

- `0x18037c8ca`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x18037c970`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x18037ca40`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x18037ca19`: `Creation of the cleanup threadpool group thread failed.`
- `0x18037c945`: `CLEANUP_THREADPOOL_GROUP_INFO allocation failed`
- `0x18037c80e`: `Task scheduler cleanup`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::CleanUp(RTL_SRWLOCK *this, int a2)
{
  RTL_SRWLOCK *v2; // rbx
  HMODULE Ptr; // r15
  struct _TP_TIMER *v6; // r14
  struct _TP_WAIT *v7; // rsi
  int v8; // r9d
  signed int LastError; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ecx
  HMODULE *v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  HMODULE *v17; // rbx
  HANDLE Thread; // rax
  signed int v19; // eax
  int v20; // r8d
  int v21; // r9d
  unsigned int v22; // ecx
  const char *v24; // [rsp+50h] [rbp-20h] BYREF
  const char *v25; // [rsp+58h] [rbp-18h] BYREF
  const char *v26; // [rsp+60h] [rbp-10h] BYREF
  const char *v27; // [rsp+68h] [rbp-8h] BYREF
  const char *v28; // [rsp+B0h] [rbp+40h] BYREF
  int v29; // [rsp+C0h] [rbp+50h] BYREF
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
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v28 = "Task scheduler cleanup";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_1808B5850,
      (unsigned int)qword_180871218,
      0,
      v8,
      (__int64)&v28);
  }
  if ( v6 )
    SetThreadpoolTimer(v6, 0, 0, 0);
  if ( v7 )
    SetThreadpoolWait(v7, 0, 0);
  if ( !GetModuleHandleExW(4u, (LPCWSTR)RdpTaskScheduler::STATIC_CleanupThreadpoolGroup, &phModule) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      LODWORD(v28) = 267;
      v24 = "Failed to get module handle to itself.";
      v29 = v12;
      v25 = "CleanUp";
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v27 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)&byte_1808711C7,
        v10,
        v11,
        (__int64)&v27,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v28,
        (__int64)&v25,
        (__int64)&v24);
    }
    goto LABEL_25;
  }
  v13 = (HMODULE *)operator new(0x18u);
  v17 = v13;
  if ( !v13 )
  {
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      LODWORD(v28) = 270;
      v27 = "CLEANUP_THREADPOOL_GROUP_INFO allocation failed";
      v29 = -2147024882;
      v26 = "CleanUp";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v24 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)&byte_180870F5F,
        v15,
        v16,
        (__int64)&v24,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v26,
        (__int64)&v27);
    }
    goto LABEL_25;
  }
  v13[1] = Ptr;
  *((_DWORD *)v13 + 4) = a2;
  *v13 = phModule;
  Thread = CreateThread(0, 0, RdpTaskScheduler::STATIC_CleanupThreadpoolGroup, v13, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
    phModule = 0;
LABEL_24:
    HIDWORD(this[5].Ptr) |= 4u;
    goto LABEL_25;
  }
  v19 = GetLastError();
  v22 = v19;
  if ( v19 > 0 )
    v22 = (unsigned __int16)v19 | 0x80070000;
  if ( (unsigned int)dword_1808B5850 > 2 )
  {
    LODWORD(v28) = 284;
    v27 = "Creation of the cleanup threadpool group thread failed.";
    v29 = v22;
    v26 = "CleanUp";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v24 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v22,
      (unsigned int)&byte_180870FAF,
      v20,
      v21,
      (__int64)&v24,
      (__int64)&v29,
      (__int64)&v25,
      (__int64)&v28,
      (__int64)&v26,
      (__int64)&v27);
  }
  operator delete(v17);
LABEL_25:
  if ( phModule )
    FreeLibrary(phModule);
  return 0;
}

```

## disassembly

```asm
0x18037c780  push    rbp
0x18037c782  push    rbx
0x18037c783  push    rsi
0x18037c784  push    rdi
0x18037c785  push    r12
0x18037c787  push    r14
0x18037c789  push    r15
0x18037c78b  mov     rbp, rsp
0x18037c78e  sub     rsp, 70h
0x18037c792  lea     rbx, [rcx+0E8h]
0x18037c799  mov     [rbp+phModule], 0
0x18037c7a1  mov     rdi, rcx
0x18037c7a4  mov     r12d, edx
0x18037c7a7  mov     rcx, rbx; SRWLock
0x18037c7aa  call    cs:__imp_AcquireSRWLockExclusive
0x18037c7b0  mov     r15, [rdi+88h]
0x18037c7b7  mov     rcx, rbx; SRWLock
0x18037c7ba  mov     r14, [rdi+98h]
0x18037c7c1  mov     rsi, [rdi+0A0h]
0x18037c7c8  mov     qword ptr [rdi+88h], 0
0x18037c7d3  mov     qword ptr [rdi+90h], 0
0x18037c7de  mov     qword ptr [rdi+98h], 0
0x18037c7e9  mov     qword ptr [rdi+0A0h], 0
0x18037c7f4  call    cs:__imp_ReleaseSRWLockExclusive
0x18037c7fa  test    r15, r15
0x18037c7fd  jz      loc_18037CAAC
0x18037c803  mov     eax, cs:dword_1808B5850
0x18037c809  cmp     eax, 4
0x18037c80c  jbe     short loc_18037C838
0x18037c80e  lea     rax, aTaskSchedulerC; "Task scheduler cleanup"
0x18037c815  xor     r8d, r8d
0x18037c818  mov     [rbp+arg_0], rax
0x18037c81c  lea     rdx, qword_180871218
0x18037c823  lea     rax, [rbp+arg_0]
0x18037c827  lea     rcx, dword_1808B5850
0x18037c82e  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x18037c833  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18037c838  test    r14, r14
0x18037c83b  jz      short loc_18037C84E
0x18037c83d  xor     r9d, r9d; msWindowLength
0x18037c840  xor     r8d, r8d; msPeriod
0x18037c843  xor     edx, edx; pftDueTime
0x18037c845  mov     rcx, r14; pti
0x18037c848  call    cs:__imp_SetThreadpoolTimer
0x18037c84e  test    rsi, rsi
0x18037c851  jz      short loc_18037C861
0x18037c853  xor     r8d, r8d; pftTimeout
0x18037c856  xor     edx, edx; h
0x18037c858  mov     rcx, rsi; pwa
0x18037c85b  call    cs:__imp_SetThreadpoolWait
0x18037c861  lea     r8, [rbp+phModule]; phModule
0x18037c865  mov     ecx, 4; dwFlags
0x18037c86a  lea     rdx, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpModuleName
0x18037c871  call    cs:__imp_GetModuleHandleExW
0x18037c877  test    eax, eax
0x18037c879  jnz     loc_18037C920
0x18037c87f  call    cs:__imp_GetLastError
0x18037c885  mov     ecx, eax
0x18037c887  test    eax, eax
0x18037c889  jle     short loc_18037C894
0x18037c88b  movzx   ecx, ax
0x18037c88e  or      ecx, 80070000h
0x18037c894  mov     eax, cs:dword_1808B5850
0x18037c89a  cmp     eax, 2
0x18037c89d  jbe     loc_18037CAB0
0x18037c8a3  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x18037c8aa  mov     dword ptr [rbp+arg_0], 10Bh
0x18037c8b1  mov     [rbp+var_20], rax
0x18037c8b5  lea     rdx, byte_1808711C7
0x18037c8bc  lea     rax, aCleanup; "CleanUp"
0x18037c8c3  mov     [rbp+arg_10], ecx
0x18037c8c6  mov     [rbp+var_18], rax
0x18037c8ca  lea     rax, aOnecoreTermsrv_49; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18037c8d1  mov     [rbp+var_10], rax
0x18037c8d5  lea     rax, aErrorCondition; "Error condition failed"
0x18037c8dc  mov     [rbp+var_8], rax
0x18037c8e0  lea     rax, [rbp+var_20]
0x18037c8e4  mov     [rsp+70h+var_28], rax
0x18037c8e9  lea     rax, [rbp+var_18]
0x18037c8ed  mov     [rsp+70h+var_30], rax
0x18037c8f2  lea     rax, [rbp+arg_0]
0x18037c8f6  mov     [rsp+70h+var_38], rax
0x18037c8fb  lea     rax, [rbp+var_10]
0x18037c8ff  mov     [rsp+70h+var_40], rax
0x18037c904  lea     rax, [rbp+arg_10]
0x18037c908  mov     [rsp+70h+lpThreadId], rax
0x18037c90d  lea     rax, [rbp+var_8]
0x18037c911  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x18037c916  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18037c91b  jmp     loc_18037CAB0
0x18037c920  mov     ecx, 18h; Size
0x18037c925  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18037c92a  mov     rbx, rax
0x18037c92d  test    rax, rax
0x18037c930  jnz     loc_18037C9BC
0x18037c936  mov     eax, cs:dword_1808B5850
0x18037c93c  cmp     eax, 2
0x18037c93f  jbe     loc_18037CAB0
0x18037c945  lea     rax, aCleanupThreadp; "CLEANUP_THREADPOOL_GROUP_INFO allocatio"...
0x18037c94c  mov     dword ptr [rbp+arg_0], 10Eh
0x18037c953  mov     [rbp+var_8], rax
0x18037c957  lea     rdx, byte_180870F5F
0x18037c95e  lea     rax, aCleanup; "CleanUp"
0x18037c965  mov     [rbp+arg_10], 8007000Eh
0x18037c96c  mov     [rbp+var_10], rax
0x18037c970  lea     rax, aOnecoreTermsrv_49; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18037c977  mov     [rbp+var_18], rax
0x18037c97b  lea     rax, aErrorCondition; "Error condition failed"
0x18037c982  mov     [rbp+var_20], rax
0x18037c986  lea     rax, [rbp+var_8]
0x18037c98a  mov     [rsp+70h+var_28], rax
0x18037c98f  lea     rax, [rbp+var_10]
0x18037c993  mov     [rsp+70h+var_30], rax
0x18037c998  lea     rax, [rbp+arg_0]
0x18037c99c  mov     [rsp+70h+var_38], rax
0x18037c9a1  lea     rax, [rbp+var_18]
0x18037c9a5  mov     [rsp+70h+var_40], rax
0x18037c9aa  lea     rax, [rbp+arg_10]
0x18037c9ae  mov     [rsp+70h+lpThreadId], rax
0x18037c9b3  lea     rax, [rbp+var_20]
0x18037c9b7  jmp     loc_18037C911
0x18037c9bc  mov     [rax+8], r15
0x18037c9c0  lea     r8, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpStartAddress
0x18037c9c7  mov     [rax+10h], r12d
0x18037c9cb  mov     r9, rbx; lpParameter
0x18037c9ce  mov     rax, [rbp+phModule]
0x18037c9d2  xor     edx, edx; dwStackSize
0x18037c9d4  mov     [rsp+70h+lpThreadId], 0; lpThreadId
0x18037c9dd  xor     ecx, ecx; lpThreadAttributes
0x18037c9df  mov     [rbx], rax
0x18037c9e2  mov     [rsp+70h+dwCreationFlags], 0; dwCreationFlags
0x18037c9ea  call    cs:__imp_CreateThread
0x18037c9f0  test    rax, rax
0x18037c9f3  jnz     loc_18037CA9B
0x18037c9f9  call    cs:__imp_GetLastError
0x18037c9ff  mov     ecx, eax
0x18037ca01  test    eax, eax
0x18037ca03  jle     short loc_18037CA0E
0x18037ca05  movzx   ecx, ax
0x18037ca08  or      ecx, 80070000h
0x18037ca0e  mov     eax, cs:dword_1808B5850
0x18037ca14  cmp     eax, 2
0x18037ca17  jbe     short loc_18037CA91
0x18037ca19  lea     rax, aCreationOfTheC; "Creation of the cleanup threadpool grou"...
0x18037ca20  mov     dword ptr [rbp+arg_0], 11Ch
0x18037ca27  mov     [rbp+var_8], rax
0x18037ca2b  lea     rdx, byte_180870FAF
0x18037ca32  lea     rax, aCleanup; "CleanUp"
0x18037ca39  mov     [rbp+arg_10], ecx
0x18037ca3c  mov     [rbp+var_10], rax
0x18037ca40  lea     rax, aOnecoreTermsrv_49; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18037ca47  mov     [rbp+var_18], rax
0x18037ca4b  lea     rax, aErrorCondition; "Error condition failed"
0x18037ca52  mov     [rbp+var_20], rax
0x18037ca56  lea     rax, [rbp+var_8]
0x18037ca5a  mov     [rsp+70h+var_28], rax
0x18037ca5f  lea     rax, [rbp+var_10]
0x18037ca63  mov     [rsp+70h+var_30], rax
0x18037ca68  lea     rax, [rbp+arg_0]
0x18037ca6c  mov     [rsp+70h+var_38], rax
0x18037ca71  lea     rax, [rbp+var_18]
0x18037ca75  mov     [rsp+70h+var_40], rax
0x18037ca7a  lea     rax, [rbp+arg_10]
0x18037ca7e  mov     [rsp+70h+lpThreadId], rax
0x18037ca83  lea     rax, [rbp+var_20]
0x18037ca87  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x18037ca8c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18037ca91  mov     rcx, rbx; Block
0x18037ca94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18037ca99  jmp     short loc_18037CAB0
0x18037ca9b  mov     rcx, rax; hObject
0x18037ca9e  call    cs:__imp_CloseHandle
0x18037caa4  mov     [rbp+phModule], 0
0x18037caac  or      dword ptr [rdi+2Ch], 4
0x18037cab0  mov     rcx, [rbp+phModule]; hLibModule
0x18037cab4  test    rcx, rcx
0x18037cab7  jz      short loc_18037CABF
0x18037cab9  call    cs:__imp_FreeLibrary
0x18037cabf  xor     eax, eax
0x18037cac1  add     rsp, 70h
0x18037cac5  pop     r15
0x18037cac7  pop     r14
0x18037cac9  pop     r12
0x18037cacb  pop     rdi
0x18037cacc  pop     rsi
0x18037cacd  pop     rbx
0x18037cace  pop     rbp
0x18037cacf  retn
```
