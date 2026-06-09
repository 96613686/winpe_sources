# RdpTaskScheduler::Initialize(IThreadPoolHandle *)

- ea: `0x14008a00c`
- end: `0x14008a38b`
- name: `?Initialize@RdpTaskScheduler@@IEAAJPEAUIThreadPoolHandle@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(PVOID pv, struct IThreadPoolHandle *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14008b5ec`

## callees

- `0x1400026b0`
- `0x14008a00c`
- `0x140114010`

## import_xrefs

- `KERNEL32!CreateThreadpoolWait` at `0x14008a2cd`
- `KERNEL32!CreateThreadpoolWait` at `0x14008a2cd`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x14008a070`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x14008a070`
- `KERNEL32!CreateThreadpoolWork` at `0x14008a15f`
- `KERNEL32!CreateThreadpoolWork` at `0x14008a15f`
- `KERNEL32!CreateThreadpoolTimer` at `0x14008a216`
- `KERNEL32!CreateThreadpoolTimer` at `0x14008a216`
- `KERNEL32!GetLastError` at `0x14008a086`
- `KERNEL32!GetLastError` at `0x14008a175`
- `KERNEL32!GetLastError` at `0x14008a22c`
- `KERNEL32!GetLastError` at `0x14008a2e3`
- `KERNEL32!GetLastError` at `0x14008a086`
- `KERNEL32!GetLastError` at `0x14008a175`
- `KERNEL32!GetLastError` at `0x14008a22c`
- `KERNEL32!GetLastError` at `0x14008a2e3`

## string_xrefs

- `0x14008a0aa`: `CreateThreadpoolWork failed`
- `0x14008a199`: `CreateThreadpoolWork failed`
- `0x14008a0ce`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008a1bd`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008a274`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008a327`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008a250`: `CreateThreadpoolTimer failed`
- `0x14008a303`: `CreateThreadpoolWait failed`

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
  char *v11; // rdx
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
        if ( (unsigned int)dword_140152118 > 2 )
        {
          v24 = 206;
          v26 = "CreateThreadpoolWait failed";
          v11 = &byte_140143AE7;
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
        if ( (unsigned int)dword_140152118 > 2 )
        {
          v24 = 200;
          v26 = "CreateThreadpoolTimer failed";
          v11 = &byte_140143B37;
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
      if ( (unsigned int)dword_140152118 > 2 )
      {
        v24 = 194;
        v26 = "CreateThreadpoolWork failed";
        v11 = &byte_140143A97;
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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v24 = 179;
      v26 = "CreateThreadpoolWork failed";
      v11 = &byte_140143B87;
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
0x14008a00c  mov     [rsp-18h+arg_8], rbx
0x14008a011  push    rbp
0x14008a012  push    rsi
0x14008a013  push    rdi
0x14008a014  mov     rbp, rsp
0x14008a017  sub     rsp, 70h
0x14008a01b  lea     rdi, [rcx+40h]
0x14008a01f  mov     rsi, rdx
0x14008a022  mov     dword ptr [rdi], 3
0x14008a028  mov     rbx, rcx
0x14008a02b  mov     qword ptr [rdi+8], 0
0x14008a033  mov     qword ptr [rdi+10h], 0
0x14008a03b  mov     qword ptr [rdi+18h], 0
0x14008a043  mov     qword ptr [rdi+20h], 0
0x14008a04b  mov     qword ptr [rdi+28h], 0
0x14008a053  mov     qword ptr [rdi+30h], 0
0x14008a05b  mov     dword ptr [rdi+38h], 0
0x14008a062  mov     dword ptr [rdi+3Ch], 1
0x14008a069  mov     dword ptr [rdi+40h], 48h ; 'H'
0x14008a070  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14008a076  mov     [rbx+88h], rax
0x14008a07d  test    rax, rax
0x14008a080  jnz     loc_14008A127
0x14008a086  call    cs:__imp_GetLastError
0x14008a08c  mov     ebx, eax
0x14008a08e  test    eax, eax
0x14008a090  jle     short loc_14008A09B
0x14008a092  movzx   ebx, ax
0x14008a095  or      ebx, 80070000h
0x14008a09b  mov     eax, cs:dword_140152118
0x14008a0a1  cmp     eax, 2
0x14008a0a4  jbe     loc_14008A379
0x14008a0aa  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x14008a0b1  mov     [rbp+arg_0], 0B3h
0x14008a0b8  mov     [rbp+arg_18], rax
0x14008a0bc  lea     rdx, byte_140143B87
0x14008a0c3  lea     rax, aInitialize; "Initialize"
0x14008a0ca  mov     [rbp+var_20], rax
0x14008a0ce  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008a0d5  mov     [rbp+var_18], rax
0x14008a0d9  lea     rax, aErrorCondition; "Error condition failed"
0x14008a0e0  mov     [rbp+var_10], rax
0x14008a0e4  lea     rax, [rbp+arg_18]
0x14008a0e8  mov     [rsp+70h+var_28], rax
0x14008a0ed  lea     rax, [rbp+var_20]
0x14008a0f1  mov     [rsp+70h+var_30], rax
0x14008a0f6  lea     rax, [rbp+arg_0]
0x14008a0fa  mov     [rsp+70h+var_38], rax
0x14008a0ff  lea     rax, [rbp+var_18]
0x14008a103  mov     [rsp+70h+var_40], rax
0x14008a108  lea     rax, [rbp+arg_10]
0x14008a10c  mov     [rsp+70h+var_48], rax
0x14008a111  lea     rax, [rbp+var_10]
0x14008a115  mov     [rsp+70h+var_50], rax
0x14008a11a  mov     [rbp+arg_10], ebx
0x14008a11d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14008a122  jmp     loc_14008A379
0x14008a127  test    rsi, rsi
0x14008a12a  jz      short loc_14008A13F
0x14008a12c  mov     rax, [rsi]
0x14008a12f  mov     rcx, rsi
0x14008a132  mov     rax, [rax+18h]
0x14008a136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008a13b  mov     [rbx+48h], rax
0x14008a13f  mov     rax, [rbx+88h]
0x14008a146  lea     rcx, ?STATIC_WorkThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14008a14d  mov     r8, rdi; pcbe
0x14008a150  mov     [rbx+50h], rax
0x14008a154  mov     rdx, rbx; pv
0x14008a157  mov     qword ptr [rbx+58h], 0
0x14008a15f  call    cs:__imp_CreateThreadpoolWork
0x14008a165  mov     [rbx+90h], rax
0x14008a16c  test    rax, rax
0x14008a16f  jnz     loc_14008A209
0x14008a175  call    cs:__imp_GetLastError
0x14008a17b  mov     ebx, eax
0x14008a17d  test    eax, eax
0x14008a17f  jle     short loc_14008A18A
0x14008a181  movzx   ebx, ax
0x14008a184  or      ebx, 80070000h
0x14008a18a  mov     eax, cs:dword_140152118
0x14008a190  cmp     eax, 2
0x14008a193  jbe     loc_14008A379
0x14008a199  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x14008a1a0  mov     [rbp+arg_0], 0C2h
0x14008a1a7  mov     [rbp+arg_18], rax
0x14008a1ab  lea     rdx, byte_140143A97
0x14008a1b2  lea     rax, aInitialize; "Initialize"
0x14008a1b9  mov     [rbp+var_10], rax
0x14008a1bd  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008a1c4  mov     [rbp+var_18], rax
0x14008a1c8  lea     rax, aErrorCondition; "Error condition failed"
0x14008a1cf  mov     [rbp+var_20], rax
0x14008a1d3  lea     rax, [rbp+arg_18]
0x14008a1d7  mov     [rsp+70h+var_28], rax
0x14008a1dc  lea     rax, [rbp+var_10]
0x14008a1e0  mov     [rsp+70h+var_30], rax
0x14008a1e5  lea     rax, [rbp+arg_0]
0x14008a1e9  mov     [rsp+70h+var_38], rax
0x14008a1ee  lea     rax, [rbp+var_18]
0x14008a1f2  mov     [rsp+70h+var_40], rax
0x14008a1f7  lea     rax, [rbp+arg_10]
0x14008a1fb  mov     [rsp+70h+var_48], rax
0x14008a200  lea     rax, [rbp+var_20]
0x14008a204  jmp     loc_14008A115
0x14008a209  mov     r8, rdi; pcbe
0x14008a20c  lea     rcx, ?STATIC_TimerThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14008a213  mov     rdx, rbx; pv
0x14008a216  call    cs:__imp_CreateThreadpoolTimer
0x14008a21c  mov     [rbx+98h], rax
0x14008a223  test    rax, rax
0x14008a226  jnz     loc_14008A2C0
0x14008a22c  call    cs:__imp_GetLastError
0x14008a232  mov     ebx, eax
0x14008a234  test    eax, eax
0x14008a236  jle     short loc_14008A241
0x14008a238  movzx   ebx, ax
0x14008a23b  or      ebx, 80070000h
0x14008a241  mov     eax, cs:dword_140152118
0x14008a247  cmp     eax, 2
0x14008a24a  jbe     loc_14008A379
0x14008a250  lea     rax, aCreatethreadpo_2; "CreateThreadpoolTimer failed"
0x14008a257  mov     [rbp+arg_0], 0C8h
0x14008a25e  mov     [rbp+arg_18], rax
0x14008a262  lea     rdx, byte_140143B37
0x14008a269  lea     rax, aInitialize; "Initialize"
0x14008a270  mov     [rbp+var_10], rax
0x14008a274  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008a27b  mov     [rbp+var_18], rax
0x14008a27f  lea     rax, aErrorCondition; "Error condition failed"
0x14008a286  mov     [rbp+var_20], rax
0x14008a28a  lea     rax, [rbp+arg_18]
0x14008a28e  mov     [rsp+70h+var_28], rax
0x14008a293  lea     rax, [rbp+var_10]
0x14008a297  mov     [rsp+70h+var_30], rax
0x14008a29c  lea     rax, [rbp+arg_0]
0x14008a2a0  mov     [rsp+70h+var_38], rax
0x14008a2a5  lea     rax, [rbp+var_18]
0x14008a2a9  mov     [rsp+70h+var_40], rax
0x14008a2ae  lea     rax, [rbp+arg_10]
0x14008a2b2  mov     [rsp+70h+var_48], rax
0x14008a2b7  lea     rax, [rbp+var_20]
0x14008a2bb  jmp     loc_14008A115
0x14008a2c0  mov     r8, rdi; pcbe
0x14008a2c3  lea     rcx, ?STATIC_WaitThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x14008a2ca  mov     rdx, rbx; pv
0x14008a2cd  call    cs:__imp_CreateThreadpoolWait
0x14008a2d3  mov     [rbx+0A0h], rax
0x14008a2da  test    rax, rax
0x14008a2dd  jnz     loc_14008A373
0x14008a2e3  call    cs:__imp_GetLastError
0x14008a2e9  mov     ebx, eax
0x14008a2eb  test    eax, eax
0x14008a2ed  jle     short loc_14008A2F8
0x14008a2ef  movzx   ebx, ax
0x14008a2f2  or      ebx, 80070000h
0x14008a2f8  mov     eax, cs:dword_140152118
0x14008a2fe  cmp     eax, 2
0x14008a301  jbe     short loc_14008A379
0x14008a303  lea     rax, aCreatethreadpo_0; "CreateThreadpoolWait failed"
0x14008a30a  mov     [rbp+arg_0], 0CEh
0x14008a311  mov     [rbp+arg_18], rax
0x14008a315  lea     rdx, byte_140143AE7
0x14008a31c  lea     rax, aInitialize; "Initialize"
0x14008a323  mov     [rbp+var_10], rax
0x14008a327  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008a32e  mov     [rbp+var_18], rax
0x14008a332  lea     rax, aErrorCondition; "Error condition failed"
0x14008a339  mov     [rbp+var_20], rax
0x14008a33d  lea     rax, [rbp+arg_18]
0x14008a341  mov     [rsp+70h+var_28], rax
0x14008a346  lea     rax, [rbp+var_10]
0x14008a34a  mov     [rsp+70h+var_30], rax
0x14008a34f  lea     rax, [rbp+arg_0]
0x14008a353  mov     [rsp+70h+var_38], rax
0x14008a358  lea     rax, [rbp+var_18]
0x14008a35c  mov     [rsp+70h+var_40], rax
0x14008a361  lea     rax, [rbp+arg_10]
0x14008a365  mov     [rsp+70h+var_48], rax
0x14008a36a  lea     rax, [rbp+var_20]
0x14008a36e  jmp     loc_14008A115
0x14008a373  or      dword ptr [rbx+2Ch], 2
0x14008a377  xor     ebx, ebx
0x14008a379  mov     eax, ebx
0x14008a37b  mov     rbx, [rsp+70h+arg_8]
0x14008a383  add     rsp, 70h
0x14008a387  pop     rdi
0x14008a388  pop     rsi
0x14008a389  pop     rbp
0x14008a38a  retn
```
