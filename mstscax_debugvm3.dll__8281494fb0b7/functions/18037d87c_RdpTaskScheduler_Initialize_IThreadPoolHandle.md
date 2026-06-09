# RdpTaskScheduler::Initialize(IThreadPoolHandle *)

- ea: `0x18037d87c`
- end: `0x18037dbfb`
- name: `?Initialize@RdpTaskScheduler@@IEAAJPEAUIThreadPoolHandle@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(PVOID pv, struct IThreadPoolHandle *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18037e8e8`

## callees

- `0x1800054f4`
- `0x18037d87c`
- `0x18068c010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18037da86`
- `KERNEL32!CreateThreadpoolTimer` at `0x18037da86`
- `KERNEL32!GetLastError` at `0x18037d8f6`
- `KERNEL32!GetLastError` at `0x18037d9e5`
- `KERNEL32!GetLastError` at `0x18037da9c`
- `KERNEL32!GetLastError` at `0x18037db53`
- `KERNEL32!GetLastError` at `0x18037d8f6`
- `KERNEL32!GetLastError` at `0x18037d9e5`
- `KERNEL32!GetLastError` at `0x18037da9c`
- `KERNEL32!GetLastError` at `0x18037db53`
- `KERNEL32!CreateThreadpoolWait` at `0x18037db3d`
- `KERNEL32!CreateThreadpoolWait` at `0x18037db3d`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18037d8e0`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18037d8e0`
- `KERNEL32!CreateThreadpoolWork` at `0x18037d9cf`
- `KERNEL32!CreateThreadpoolWork` at `0x18037d9cf`

## string_xrefs

- `0x18037d91a`: `CreateThreadpoolWork failed`
- `0x18037da09`: `CreateThreadpoolWork failed`
- `0x18037d93e`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x18037da2d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x18037dae4`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x18037db97`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x18037db73`: `CreateThreadpoolWait failed`
- `0x18037dac0`: `CreateThreadpoolTimer failed`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::Initialize(_DWORD *pv, struct IThreadPoolHandle *a2)
{
  struct _TP_CALLBACK_ENVIRON_V3 *v2; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int v6; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  int *v11; // rdx
  const char **v12; // rax
  PTP_WORK ThreadpoolWork; // rax
  signed int v14; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  signed int v16; // eax
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  const char **v20; // [rsp+40h] [rbp-30h]
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+30h] BYREF
  const char *v26; // [rsp+A8h] [rbp+38h] BYREF

  v2 = (struct _TP_CALLBACK_ENVIRON_V3 *)(pv + 16);
  pv[16] = 3;
  *((_QWORD *)pv + 9) = 0;
  *((_QWORD *)pv + 10) = 0;
  *((_QWORD *)pv + 11) = 0;
  *((_QWORD *)pv + 12) = 0;
  *((_QWORD *)pv + 13) = 0;
  *((_QWORD *)pv + 14) = 0;
  pv[30] = 0;
  pv[31] = 1;
  pv[32] = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)pv + 17) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    if ( a2 )
      *((_QWORD *)pv + 9) = (*(__int64 (__fastcall **)(struct IThreadPoolHandle *))(*(_QWORD *)a2 + 24LL))(a2);
    *((_QWORD *)pv + 10) = *((_QWORD *)pv + 17);
    *((_QWORD *)pv + 11) = 0;
    ThreadpoolWork = CreateThreadpoolWork(RdpTaskScheduler::STATIC_WorkThreadPoolCallback, pv, v2);
    *((_QWORD *)pv + 18) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(RdpTaskScheduler::STATIC_TimerThreadPoolCallback, pv, v2);
      *((_QWORD *)pv + 19) = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        ThreadpoolWait = CreateThreadpoolWait(RdpTaskScheduler::STATIC_WaitThreadPoolCallback, pv, v2);
        *((_QWORD *)pv + 20) = ThreadpoolWait;
        if ( ThreadpoolWait )
        {
          pv[11] |= 2u;
          return 0;
        }
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v24 = 206;
          v26 = "CreateThreadpoolWait failed";
          v11 = (int *)byte_180871113;
          v23[0] = "Initialize";
          v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
          v21 = "Error condition failed";
          v20 = (const char **)v23;
          v12 = &v21;
          goto LABEL_6;
        }
      }
      else
      {
        v16 = GetLastError();
        v10 = v16;
        if ( v16 > 0 )
          v10 = (unsigned __int16)v16 | 0x80070000;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v24 = 200;
          v26 = "CreateThreadpoolTimer failed";
          v11 = &dword_18087129C;
          v23[0] = "Initialize";
          v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
          v21 = "Error condition failed";
          v20 = (const char **)v23;
          v12 = &v21;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v14 = GetLastError();
      v10 = v14;
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v24 = 194;
        v26 = "CreateThreadpoolWork failed";
        v11 = &dword_18087133C;
        v23[0] = "Initialize";
        v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
        v21 = "Error condition failed";
        v20 = (const char **)v23;
        v12 = &v21;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v6 = GetLastError();
    v10 = v6;
    if ( v6 > 0 )
      v10 = (unsigned __int16)v6 | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v24 = 179;
      v26 = "CreateThreadpoolWork failed";
      v11 = &dword_1808712EC;
      v21 = "Initialize";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v23[0] = "Error condition failed";
      v20 = &v21;
      v12 = (const char **)v23;
LABEL_6:
      v25 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (_DWORD)v11,
        v8,
        v9,
        (__int64)v12,
        (__int64)&v25,
        (__int64)&v22,
        (__int64)&v24,
        (__int64)v20,
        (__int64)&v26);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18037d87c  mov     [rsp-18h+arg_8], rbx
0x18037d881  push    rbp
0x18037d882  push    rsi
0x18037d883  push    rdi
0x18037d884  mov     rbp, rsp
0x18037d887  sub     rsp, 70h
0x18037d88b  lea     rdi, [rcx+40h]
0x18037d88f  mov     rsi, rdx
0x18037d892  mov     dword ptr [rdi], 3
0x18037d898  mov     rbx, rcx
0x18037d89b  mov     qword ptr [rdi+8], 0
0x18037d8a3  mov     qword ptr [rdi+10h], 0
0x18037d8ab  mov     qword ptr [rdi+18h], 0
0x18037d8b3  mov     qword ptr [rdi+20h], 0
0x18037d8bb  mov     qword ptr [rdi+28h], 0
0x18037d8c3  mov     qword ptr [rdi+30h], 0
0x18037d8cb  mov     dword ptr [rdi+38h], 0
0x18037d8d2  mov     dword ptr [rdi+3Ch], 1
0x18037d8d9  mov     dword ptr [rdi+40h], 48h ; 'H'
0x18037d8e0  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18037d8e6  mov     [rbx+88h], rax
0x18037d8ed  test    rax, rax
0x18037d8f0  jnz     loc_18037D997
0x18037d8f6  call    cs:__imp_GetLastError
0x18037d8fc  mov     ebx, eax
0x18037d8fe  test    eax, eax
0x18037d900  jle     short loc_18037D90B
0x18037d902  movzx   ebx, ax
0x18037d905  or      ebx, 80070000h
0x18037d90b  mov     eax, cs:dword_1808B5850
0x18037d911  cmp     eax, 2
0x18037d914  jbe     loc_18037DBE9
0x18037d91a  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x18037d921  mov     [rbp+arg_0], 0B3h
0x18037d928  mov     [rbp+arg_18], rax
0x18037d92c  lea     rdx, dword_1808712EC
0x18037d933  lea     rax, aInitialize_0; "Initialize"
0x18037d93a  mov     [rbp+var_20], rax
0x18037d93e  lea     rax, aOnecoreTermsrv_49; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18037d945  mov     [rbp+var_18], rax
0x18037d949  lea     rax, aErrorCondition; "Error condition failed"
0x18037d950  mov     [rbp+var_10], rax
0x18037d954  lea     rax, [rbp+arg_18]
0x18037d958  mov     [rsp+70h+var_28], rax
0x18037d95d  lea     rax, [rbp+var_20]
0x18037d961  mov     [rsp+70h+var_30], rax
0x18037d966  lea     rax, [rbp+arg_0]
0x18037d96a  mov     [rsp+70h+var_38], rax
0x18037d96f  lea     rax, [rbp+var_18]
0x18037d973  mov     [rsp+70h+var_40], rax
0x18037d978  lea     rax, [rbp+arg_10]
0x18037d97c  mov     [rsp+70h+var_48], rax
0x18037d981  lea     rax, [rbp+var_10]
0x18037d985  mov     [rsp+70h+var_50], rax
0x18037d98a  mov     [rbp+arg_10], ebx
0x18037d98d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18037d992  jmp     loc_18037DBE9
0x18037d997  test    rsi, rsi
0x18037d99a  jz      short loc_18037D9AF
0x18037d99c  mov     rax, [rsi]
0x18037d99f  mov     rcx, rsi
0x18037d9a2  mov     rax, [rax+18h]
0x18037d9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037d9ab  mov     [rbx+48h], rax
0x18037d9af  mov     rax, [rbx+88h]
0x18037d9b6  lea     rcx, ?STATIC_WorkThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18037d9bd  mov     r8, rdi; pcbe
0x18037d9c0  mov     [rbx+50h], rax
0x18037d9c4  mov     rdx, rbx; pv
0x18037d9c7  mov     qword ptr [rbx+58h], 0
0x18037d9cf  call    cs:__imp_CreateThreadpoolWork
0x18037d9d5  mov     [rbx+90h], rax
0x18037d9dc  test    rax, rax
0x18037d9df  jnz     loc_18037DA79
0x18037d9e5  call    cs:__imp_GetLastError
0x18037d9eb  mov     ebx, eax
0x18037d9ed  test    eax, eax
0x18037d9ef  jle     short loc_18037D9FA
0x18037d9f1  movzx   ebx, ax
0x18037d9f4  or      ebx, 80070000h
0x18037d9fa  mov     eax, cs:dword_1808B5850
0x18037da00  cmp     eax, 2
0x18037da03  jbe     loc_18037DBE9
0x18037da09  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x18037da10  mov     [rbp+arg_0], 0C2h
0x18037da17  mov     [rbp+arg_18], rax
0x18037da1b  lea     rdx, dword_18087133C
0x18037da22  lea     rax, aInitialize_0; "Initialize"
0x18037da29  mov     [rbp+var_10], rax
0x18037da2d  lea     rax, aOnecoreTermsrv_49; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18037da34  mov     [rbp+var_18], rax
0x18037da38  lea     rax, aErrorCondition; "Error condition failed"
0x18037da3f  mov     [rbp+var_20], rax
0x18037da43  lea     rax, [rbp+arg_18]
0x18037da47  mov     [rsp+70h+var_28], rax
0x18037da4c  lea     rax, [rbp+var_10]
0x18037da50  mov     [rsp+70h+var_30], rax
0x18037da55  lea     rax, [rbp+arg_0]
0x18037da59  mov     [rsp+70h+var_38], rax
0x18037da5e  lea     rax, [rbp+var_18]
0x18037da62  mov     [rsp+70h+var_40], rax
0x18037da67  lea     rax, [rbp+arg_10]
0x18037da6b  mov     [rsp+70h+var_48], rax
0x18037da70  lea     rax, [rbp+var_20]
0x18037da74  jmp     loc_18037D985
0x18037da79  mov     r8, rdi; pcbe
0x18037da7c  lea     rcx, ?STATIC_TimerThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18037da83  mov     rdx, rbx; pv
0x18037da86  call    cs:__imp_CreateThreadpoolTimer
0x18037da8c  mov     [rbx+98h], rax
0x18037da93  test    rax, rax
0x18037da96  jnz     loc_18037DB30
0x18037da9c  call    cs:__imp_GetLastError
0x18037daa2  mov     ebx, eax
0x18037daa4  test    eax, eax
0x18037daa6  jle     short loc_18037DAB1
0x18037daa8  movzx   ebx, ax
0x18037daab  or      ebx, 80070000h
0x18037dab1  mov     eax, cs:dword_1808B5850
0x18037dab7  cmp     eax, 2
0x18037daba  jbe     loc_18037DBE9
0x18037dac0  lea     rax, aCreatethreadpo_3; "CreateThreadpoolTimer failed"
0x18037dac7  mov     [rbp+arg_0], 0C8h
0x18037dace  mov     [rbp+arg_18], rax
0x18037dad2  lea     rdx, dword_18087129C
0x18037dad9  lea     rax, aInitialize_0; "Initialize"
0x18037dae0  mov     [rbp+var_10], rax
0x18037dae4  lea     rax, aOnecoreTermsrv_49; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18037daeb  mov     [rbp+var_18], rax
0x18037daef  lea     rax, aErrorCondition; "Error condition failed"
0x18037daf6  mov     [rbp+var_20], rax
0x18037dafa  lea     rax, [rbp+arg_18]
0x18037dafe  mov     [rsp+70h+var_28], rax
0x18037db03  lea     rax, [rbp+var_10]
0x18037db07  mov     [rsp+70h+var_30], rax
0x18037db0c  lea     rax, [rbp+arg_0]
0x18037db10  mov     [rsp+70h+var_38], rax
0x18037db15  lea     rax, [rbp+var_18]
0x18037db19  mov     [rsp+70h+var_40], rax
0x18037db1e  lea     rax, [rbp+arg_10]
0x18037db22  mov     [rsp+70h+var_48], rax
0x18037db27  lea     rax, [rbp+var_20]
0x18037db2b  jmp     loc_18037D985
0x18037db30  mov     r8, rdi; pcbe
0x18037db33  lea     rcx, ?STATIC_WaitThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18037db3a  mov     rdx, rbx; pv
0x18037db3d  call    cs:__imp_CreateThreadpoolWait
0x18037db43  mov     [rbx+0A0h], rax
0x18037db4a  test    rax, rax
0x18037db4d  jnz     loc_18037DBE3
0x18037db53  call    cs:__imp_GetLastError
0x18037db59  mov     ebx, eax
0x18037db5b  test    eax, eax
0x18037db5d  jle     short loc_18037DB68
0x18037db5f  movzx   ebx, ax
0x18037db62  or      ebx, 80070000h
0x18037db68  mov     eax, cs:dword_1808B5850
0x18037db6e  cmp     eax, 2
0x18037db71  jbe     short loc_18037DBE9
0x18037db73  lea     rax, aCreatethreadpo_0; "CreateThreadpoolWait failed"
0x18037db7a  mov     [rbp+arg_0], 0CEh
0x18037db81  mov     [rbp+arg_18], rax
0x18037db85  lea     rdx, byte_180871113
0x18037db8c  lea     rax, aInitialize_0; "Initialize"
0x18037db93  mov     [rbp+var_10], rax
0x18037db97  lea     rax, aOnecoreTermsrv_49; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18037db9e  mov     [rbp+var_18], rax
0x18037dba2  lea     rax, aErrorCondition; "Error condition failed"
0x18037dba9  mov     [rbp+var_20], rax
0x18037dbad  lea     rax, [rbp+arg_18]
0x18037dbb1  mov     [rsp+70h+var_28], rax
0x18037dbb6  lea     rax, [rbp+var_10]
0x18037dbba  mov     [rsp+70h+var_30], rax
0x18037dbbf  lea     rax, [rbp+arg_0]
0x18037dbc3  mov     [rsp+70h+var_38], rax
0x18037dbc8  lea     rax, [rbp+var_18]
0x18037dbcc  mov     [rsp+70h+var_40], rax
0x18037dbd1  lea     rax, [rbp+arg_10]
0x18037dbd5  mov     [rsp+70h+var_48], rax
0x18037dbda  lea     rax, [rbp+var_20]
0x18037dbde  jmp     loc_18037D985
0x18037dbe3  or      dword ptr [rbx+2Ch], 2
0x18037dbe7  xor     ebx, ebx
0x18037dbe9  mov     eax, ebx
0x18037dbeb  mov     rbx, [rsp+70h+arg_8]
0x18037dbf3  add     rsp, 70h
0x18037dbf7  pop     rdi
0x18037dbf8  pop     rsi
0x18037dbf9  pop     rbp
0x18037dbfa  retn
```
