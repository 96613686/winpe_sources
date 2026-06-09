# RdpTaskScheduler::Initialize(IThreadPoolHandle *)

- ea: `0x140087e9c`
- end: `0x14008821b`
- name: `?Initialize@RdpTaskScheduler@@IEAAJPEAUIThreadPoolHandle@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(PVOID pv, struct IThreadPoolHandle *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14008947c`

## callees

- `0x1400026b0`
- `0x140087e9c`
- `0x140112010`

## import_xrefs

- `KERNEL32!CreateThreadpoolWait` at `0x14008815d`
- `KERNEL32!CreateThreadpoolWait` at `0x14008815d`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x140087f00`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x140087f00`
- `KERNEL32!CreateThreadpoolWork` at `0x140087fef`
- `KERNEL32!CreateThreadpoolWork` at `0x140087fef`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400880a6`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400880a6`
- `KERNEL32!GetLastError` at `0x140087f16`
- `KERNEL32!GetLastError` at `0x140088005`
- `KERNEL32!GetLastError` at `0x1400880bc`
- `KERNEL32!GetLastError` at `0x140088173`
- `KERNEL32!GetLastError` at `0x140087f16`
- `KERNEL32!GetLastError` at `0x140088005`
- `KERNEL32!GetLastError` at `0x1400880bc`
- `KERNEL32!GetLastError` at `0x140088173`

## string_xrefs

- `0x140087f3a`: `CreateThreadpoolWork failed`
- `0x140088029`: `CreateThreadpoolWork failed`
- `0x140087f5e`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008804d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140088104`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400881b7`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400880e0`: `CreateThreadpoolTimer failed`
- `0x140088193`: `CreateThreadpoolWait failed`

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
        if ( (unsigned int)dword_140150118 > 2 )
        {
          v24 = 206;
          v26 = "CreateThreadpoolWait failed";
          v11 = &byte_1401419AF;
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
        if ( (unsigned int)dword_140150118 > 2 )
        {
          v24 = 200;
          v26 = "CreateThreadpoolTimer failed";
          v11 = &byte_1401419FF;
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        v24 = 194;
        v26 = "CreateThreadpoolWork failed";
        v11 = &byte_14014195F;
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
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v24 = 179;
      v26 = "CreateThreadpoolWork failed";
      v11 = &byte_140141A4F;
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
0x140087e9c  mov     [rsp-18h+arg_8], rbx
0x140087ea1  push    rbp
0x140087ea2  push    rsi
0x140087ea3  push    rdi
0x140087ea4  mov     rbp, rsp
0x140087ea7  sub     rsp, 70h
0x140087eab  lea     rdi, [rcx+40h]
0x140087eaf  mov     rsi, rdx
0x140087eb2  mov     dword ptr [rdi], 3
0x140087eb8  mov     rbx, rcx
0x140087ebb  mov     qword ptr [rdi+8], 0
0x140087ec3  mov     qword ptr [rdi+10h], 0
0x140087ecb  mov     qword ptr [rdi+18h], 0
0x140087ed3  mov     qword ptr [rdi+20h], 0
0x140087edb  mov     qword ptr [rdi+28h], 0
0x140087ee3  mov     qword ptr [rdi+30h], 0
0x140087eeb  mov     dword ptr [rdi+38h], 0
0x140087ef2  mov     dword ptr [rdi+3Ch], 1
0x140087ef9  mov     dword ptr [rdi+40h], 48h ; 'H'
0x140087f00  call    cs:__imp_CreateThreadpoolCleanupGroup
0x140087f06  mov     [rbx+88h], rax
0x140087f0d  test    rax, rax
0x140087f10  jnz     loc_140087FB7
0x140087f16  call    cs:__imp_GetLastError
0x140087f1c  mov     ebx, eax
0x140087f1e  test    eax, eax
0x140087f20  jle     short loc_140087F2B
0x140087f22  movzx   ebx, ax
0x140087f25  or      ebx, 80070000h
0x140087f2b  mov     eax, cs:dword_140150118
0x140087f31  cmp     eax, 2
0x140087f34  jbe     loc_140088209
0x140087f3a  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x140087f41  mov     [rbp+arg_0], 0B3h
0x140087f48  mov     [rbp+arg_18], rax
0x140087f4c  lea     rdx, byte_140141A4F
0x140087f53  lea     rax, aInitialize; "Initialize"
0x140087f5a  mov     [rbp+var_20], rax
0x140087f5e  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140087f65  mov     [rbp+var_18], rax
0x140087f69  lea     rax, aErrorCondition; "Error condition failed"
0x140087f70  mov     [rbp+var_10], rax
0x140087f74  lea     rax, [rbp+arg_18]
0x140087f78  mov     [rsp+70h+var_28], rax
0x140087f7d  lea     rax, [rbp+var_20]
0x140087f81  mov     [rsp+70h+var_30], rax
0x140087f86  lea     rax, [rbp+arg_0]
0x140087f8a  mov     [rsp+70h+var_38], rax
0x140087f8f  lea     rax, [rbp+var_18]
0x140087f93  mov     [rsp+70h+var_40], rax
0x140087f98  lea     rax, [rbp+arg_10]
0x140087f9c  mov     [rsp+70h+var_48], rax
0x140087fa1  lea     rax, [rbp+var_10]
0x140087fa5  mov     [rsp+70h+var_50], rax
0x140087faa  mov     [rbp+arg_10], ebx
0x140087fad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x140087fb2  jmp     loc_140088209
0x140087fb7  test    rsi, rsi
0x140087fba  jz      short loc_140087FCF
0x140087fbc  mov     rax, [rsi]
0x140087fbf  mov     rcx, rsi
0x140087fc2  mov     rax, [rax+18h]
0x140087fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087fcb  mov     [rbx+48h], rax
0x140087fcf  mov     rax, [rbx+88h]
0x140087fd6  lea     rcx, ?STATIC_WorkThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140087fdd  mov     r8, rdi; pcbe
0x140087fe0  mov     [rbx+50h], rax
0x140087fe4  mov     rdx, rbx; pv
0x140087fe7  mov     qword ptr [rbx+58h], 0
0x140087fef  call    cs:__imp_CreateThreadpoolWork
0x140087ff5  mov     [rbx+90h], rax
0x140087ffc  test    rax, rax
0x140087fff  jnz     loc_140088099
0x140088005  call    cs:__imp_GetLastError
0x14008800b  mov     ebx, eax
0x14008800d  test    eax, eax
0x14008800f  jle     short loc_14008801A
0x140088011  movzx   ebx, ax
0x140088014  or      ebx, 80070000h
0x14008801a  mov     eax, cs:dword_140150118
0x140088020  cmp     eax, 2
0x140088023  jbe     loc_140088209
0x140088029  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x140088030  mov     [rbp+arg_0], 0C2h
0x140088037  mov     [rbp+arg_18], rax
0x14008803b  lea     rdx, byte_14014195F
0x140088042  lea     rax, aInitialize; "Initialize"
0x140088049  mov     [rbp+var_10], rax
0x14008804d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140088054  mov     [rbp+var_18], rax
0x140088058  lea     rax, aErrorCondition; "Error condition failed"
0x14008805f  mov     [rbp+var_20], rax
0x140088063  lea     rax, [rbp+arg_18]
0x140088067  mov     [rsp+70h+var_28], rax
0x14008806c  lea     rax, [rbp+var_10]
0x140088070  mov     [rsp+70h+var_30], rax
0x140088075  lea     rax, [rbp+arg_0]
0x140088079  mov     [rsp+70h+var_38], rax
0x14008807e  lea     rax, [rbp+var_18]
0x140088082  mov     [rsp+70h+var_40], rax
0x140088087  lea     rax, [rbp+arg_10]
0x14008808b  mov     [rsp+70h+var_48], rax
0x140088090  lea     rax, [rbp+var_20]
0x140088094  jmp     loc_140087FA5
0x140088099  mov     r8, rdi; pcbe
0x14008809c  lea     rcx, ?STATIC_TimerThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400880a3  mov     rdx, rbx; pv
0x1400880a6  call    cs:__imp_CreateThreadpoolTimer
0x1400880ac  mov     [rbx+98h], rax
0x1400880b3  test    rax, rax
0x1400880b6  jnz     loc_140088150
0x1400880bc  call    cs:__imp_GetLastError
0x1400880c2  mov     ebx, eax
0x1400880c4  test    eax, eax
0x1400880c6  jle     short loc_1400880D1
0x1400880c8  movzx   ebx, ax
0x1400880cb  or      ebx, 80070000h
0x1400880d1  mov     eax, cs:dword_140150118
0x1400880d7  cmp     eax, 2
0x1400880da  jbe     loc_140088209
0x1400880e0  lea     rax, aCreatethreadpo_2; "CreateThreadpoolTimer failed"
0x1400880e7  mov     [rbp+arg_0], 0C8h
0x1400880ee  mov     [rbp+arg_18], rax
0x1400880f2  lea     rdx, byte_1401419FF
0x1400880f9  lea     rax, aInitialize; "Initialize"
0x140088100  mov     [rbp+var_10], rax
0x140088104  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008810b  mov     [rbp+var_18], rax
0x14008810f  lea     rax, aErrorCondition; "Error condition failed"
0x140088116  mov     [rbp+var_20], rax
0x14008811a  lea     rax, [rbp+arg_18]
0x14008811e  mov     [rsp+70h+var_28], rax
0x140088123  lea     rax, [rbp+var_10]
0x140088127  mov     [rsp+70h+var_30], rax
0x14008812c  lea     rax, [rbp+arg_0]
0x140088130  mov     [rsp+70h+var_38], rax
0x140088135  lea     rax, [rbp+var_18]
0x140088139  mov     [rsp+70h+var_40], rax
0x14008813e  lea     rax, [rbp+arg_10]
0x140088142  mov     [rsp+70h+var_48], rax
0x140088147  lea     rax, [rbp+var_20]
0x14008814b  jmp     loc_140087FA5
0x140088150  mov     r8, rdi; pcbe
0x140088153  lea     rcx, ?STATIC_WaitThreadPoolCallback@RdpTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x14008815a  mov     rdx, rbx; pv
0x14008815d  call    cs:__imp_CreateThreadpoolWait
0x140088163  mov     [rbx+0A0h], rax
0x14008816a  test    rax, rax
0x14008816d  jnz     loc_140088203
0x140088173  call    cs:__imp_GetLastError
0x140088179  mov     ebx, eax
0x14008817b  test    eax, eax
0x14008817d  jle     short loc_140088188
0x14008817f  movzx   ebx, ax
0x140088182  or      ebx, 80070000h
0x140088188  mov     eax, cs:dword_140150118
0x14008818e  cmp     eax, 2
0x140088191  jbe     short loc_140088209
0x140088193  lea     rax, aCreatethreadpo_0; "CreateThreadpoolWait failed"
0x14008819a  mov     [rbp+arg_0], 0CEh
0x1400881a1  mov     [rbp+arg_18], rax
0x1400881a5  lea     rdx, byte_1401419AF
0x1400881ac  lea     rax, aInitialize; "Initialize"
0x1400881b3  mov     [rbp+var_10], rax
0x1400881b7  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400881be  mov     [rbp+var_18], rax
0x1400881c2  lea     rax, aErrorCondition; "Error condition failed"
0x1400881c9  mov     [rbp+var_20], rax
0x1400881cd  lea     rax, [rbp+arg_18]
0x1400881d1  mov     [rsp+70h+var_28], rax
0x1400881d6  lea     rax, [rbp+var_10]
0x1400881da  mov     [rsp+70h+var_30], rax
0x1400881df  lea     rax, [rbp+arg_0]
0x1400881e3  mov     [rsp+70h+var_38], rax
0x1400881e8  lea     rax, [rbp+var_18]
0x1400881ec  mov     [rsp+70h+var_40], rax
0x1400881f1  lea     rax, [rbp+arg_10]
0x1400881f5  mov     [rsp+70h+var_48], rax
0x1400881fa  lea     rax, [rbp+var_20]
0x1400881fe  jmp     loc_140087FA5
0x140088203  or      dword ptr [rbx+2Ch], 2
0x140088207  xor     ebx, ebx
0x140088209  mov     eax, ebx
0x14008820b  mov     rbx, [rsp+70h+arg_8]
0x140088213  add     rsp, 70h
0x140088217  pop     rdi
0x140088218  pop     rsi
0x140088219  pop     rbp
0x14008821a  retn
```
