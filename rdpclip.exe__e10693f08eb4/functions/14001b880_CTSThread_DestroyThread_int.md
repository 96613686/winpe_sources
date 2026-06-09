# CTSThread::DestroyThread(int)

- ea: `0x14001b880`
- end: `0x14001bcc9`
- name: `?DestroyThread@CTSThread@@UEAAJH@Z`
- size: `1097`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1400010c0`
- `0x14000142c`
- `0x1400015ec`
- `0x140001710`
- `0x1400056c4`
- `0x140005704`
- `0x14001096c`
- `0x140010998`
- `0x14001b880`
- `0x14001d150`
- `0x14001d2b4`
- `0x14001ff80`
- `0x1400256b4`
- `0x14006b010`

## string_xrefs

- `0x14001b9ed`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001baf4`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001b8c2`: `Thread initialized but not running. Bail destroy`
- `0x14001b916`: `Destroying Bound Thread`
- `0x14001b9e2`: `DestroyThread`
- `0x14001bae6`: `DestroyThread`
- `0x14001b9f8`: `Trying to end thread ID %#x`
- `0x14001ba7c`: `Attempt to stop thread %#x`
- `0x14001baff`: `Failed to end thread ID %#x, HR = 0x%x`
- `0x14001bc8d`: `Thread id %#x exited.`

## pseudocode

```c
__int64 __fastcall CTSThread::DestroyThread(CTSThread *this)
{
  CTSReaderWriterLock *v2; // rsi
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  int v6; // eax
  unsigned int v7; // edi
  int v8; // edi
  unsigned int ActivityIdPrefix; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  const char *v23; // [rsp+60h] [rbp+7h] BYREF
  int v24; // [rsp+68h] [rbp+Fh]
  const char *v25; // [rsp+70h] [rbp+17h] BYREF
  const char *v26; // [rsp+78h] [rbp+1Fh] BYREF
  const char *v27; // [rsp+80h] [rbp+27h] BYREF
  const char *v28; // [rsp+C0h] [rbp+67h] BYREF
  const char *v29; // [rsp+D0h] [rbp+77h] BYREF
  int v30; // [rsp+D8h] [rbp+7Fh] BYREF

  v24 = 0;
  v2 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  v6 = *((_DWORD *)this + 20);
  if ( v6 == 1 )
  {
    if ( (unsigned int)dword_1400880C8 > 4 )
    {
      v28 = "Thread initialized but not running. Bail destroy";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (unsigned int)&byte_14007ECCF,
        v4,
        v5,
        (__int64)&v28);
    }
    *((_DWORD *)this + 20) = 7;
LABEL_5:
    v7 = 0;
LABEL_22:
    CTSReaderWriterLock::WriteUnlock(v2);
    return v7;
  }
  if ( *((_DWORD *)this + 46) && (v6 == 6 || v6 == 3) )
  {
    if ( (unsigned int)dword_1400880C8 > 4 )
    {
      v28 = "Destroying Bound Thread";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (unsigned int)&word_14007ECAE,
        v4,
        v5,
        (__int64)&v28);
    }
    *((_DWORD *)this + 20) = 4;
    v8 = CTSThread::InternalRundownThread(this);
    if ( v8 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix,
        v8);
    }
    CTSThread::InternalFreeThreadHandle(this);
    goto LABEL_5;
  }
  if ( v6 == 5 )
  {
    CTSReaderWriterLock::WriteUnlock(v2);
    CTSThread::InternalFreeThreadHandle(this);
    return 0;
  }
  if ( !*((_DWORD *)this + 14) )
  {
    v7 = -2147467259;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v28) = *((_DWORD *)this + 14);
      v23 = "DestroyThread";
      v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v26 = "Trying to end thread ID %#x";
      LODWORD(v29) = 529;
      v30 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v3,
        (unsigned int)byte_14007EC53,
        v4,
        v5,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v25,
        (__int64)&v29,
        (__int64)&v23,
        (__int64)&v28);
    }
    goto LABEL_22;
  }
  *((_DWORD *)this + 20) = 4;
  CTSReaderWriterLock::WriteUnlock(v2);
  if ( (unsigned int)dword_1400880C8 > 4 )
  {
    LODWORD(v28) = *((_DWORD *)this + 14);
    v29 = "Attempt to stop thread %#x";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)&dword_14007EC1C,
      v11,
      v12,
      (__int64)&v29,
      (__int64)&v28);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 92) + 56LL))(
          *((_QWORD *)this + 92),
          *((unsigned int *)this + 14),
          *((_QWORD *)this + 88));
  if ( v13 < 0 && (unsigned int)dword_1400880C8 > 2 )
  {
    LODWORD(v29) = *((_DWORD *)this + 14);
    LODWORD(v28) = v13;
    v26 = "DestroyThread";
    v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v27 = "Failed to end thread ID %#x, HR = 0x%x";
    v30 = 548;
    LODWORD(v23) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_14007EBBD,
      v14,
      v15,
      (__int64)&v27,
      (__int64)&v23,
      (__int64)&v25,
      (__int64)&v30,
      (__int64)&v26,
      (__int64)&v29,
      (__int64)&v28);
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 92) + 48LL))(
          *((_QWORD *)this + 92),
          (char *)this + 64,
          1);
  v7 = v16;
  if ( v16 == -2092629812 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        *((unsigned int *)this + 14));
    }
    return v7;
  }
  if ( v16 == -2092629813 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return v7;
    }
    v21 = 35;
    goto LABEL_38;
  }
  if ( v16 < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return v7;
    }
    v21 = 36;
LABEL_38:
    WPP_SF_Dq(
      v20[2],
      v21,
      &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      *((unsigned int *)this + 14),
      *((_QWORD *)this + 8));
    return v7;
  }
  if ( (unsigned int)dword_1400880C8 > 4 )
  {
    LODWORD(v28) = *((_DWORD *)this + 14);
    v29 = "Thread id %#x exited.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&word_14007EB86,
      v18,
      v19,
      (__int64)&v29,
      (__int64)&v28);
  }
  v7 = 0;
  CTSThread::InternalFreeThreadHandle(this);
  return v7;
}

```

## disassembly

```asm
0x14001b880  push    rbp
0x14001b882  push    rbx
0x14001b883  push    rsi
0x14001b884  push    rdi
0x14001b885  push    r14
0x14001b887  lea     rbp, [rsp-37h]
0x14001b88c  sub     rsp, 90h
0x14001b893  mov     r14d, edx
0x14001b896  mov     [rbp+57h+var_48], 0
0x14001b89d  mov     rbx, rcx
0x14001b8a0  lea     rsi, [rcx+94h]
0x14001b8a7  mov     rcx, rsi; this
0x14001b8aa  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x14001b8af  mov     eax, [rbx+50h]
0x14001b8b2  cmp     eax, 1
0x14001b8b5  jnz     short loc_14001B8F0
0x14001b8b7  mov     eax, cs:dword_1400880C8
0x14001b8bd  cmp     eax, 4
0x14001b8c0  jbe     short loc_14001B8E2
0x14001b8c2  lea     rax, aThreadInitiali; "Thread initialized but not running. Bai"...
0x14001b8c9  mov     [rbp+57h+arg_0], rax
0x14001b8cd  lea     rdx, byte_14007ECCF
0x14001b8d4  lea     rax, [rbp+57h+arg_0]
0x14001b8d8  mov     [rsp+0B0h+var_90], rax
0x14001b8dd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14001b8e2  mov     dword ptr [rbx+50h], 7
0x14001b8e9  xor     edi, edi
0x14001b8eb  jmp     loc_14001BA48
0x14001b8f0  cmp     dword ptr [rbx+0B8h], 0
0x14001b8f7  jz      loc_14001B99F
0x14001b8fd  cmp     eax, 6
0x14001b900  jz      short loc_14001B90B
0x14001b902  cmp     eax, 3
0x14001b905  jnz     loc_14001B99F
0x14001b90b  mov     eax, cs:dword_1400880C8
0x14001b911  cmp     eax, 4
0x14001b914  jbe     short loc_14001B936
0x14001b916  lea     rax, aDestroyingBoun; "Destroying Bound Thread"
0x14001b91d  mov     [rbp+57h+arg_0], rax
0x14001b921  lea     rdx, word_14007ECAE
0x14001b928  lea     rax, [rbp+57h+arg_0]
0x14001b92c  mov     [rsp+0B0h+var_90], rax
0x14001b931  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14001b936  mov     rcx, rbx; this
0x14001b939  mov     dword ptr [rbx+50h], 4
0x14001b940  call    ?InternalRundownThread@CTSThread@@AEAAJXZ; CTSThread::InternalRundownThread(void)
0x14001b945  mov     edi, eax
0x14001b947  test    eax, eax
0x14001b949  jns     short loc_14001B992
0x14001b94b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b952  lea     rax, WPP_GLOBAL_Control
0x14001b959  cmp     rcx, rax
0x14001b95c  jz      short loc_14001B992
0x14001b95e  test    byte ptr [rcx+1Ch], 8
0x14001b962  jz      short loc_14001B992
0x14001b964  cmp     byte ptr [rcx+19h], 2
0x14001b968  jb      short loc_14001B992
0x14001b96a  call    RdpX_GetActivityIdPrefix
0x14001b96f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b976  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001b97d  mov     edx, 21h ; '!'
0x14001b982  mov     dword ptr [rsp+0B0h+var_90], edi
0x14001b986  mov     r9d, eax
0x14001b989  mov     rcx, [rcx+10h]
0x14001b98d  call    WPP_SF_Dd
0x14001b992  mov     rcx, rbx; this
0x14001b995  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x14001b99a  jmp     loc_14001B8E9
0x14001b99f  cmp     eax, 5
0x14001b9a2  jnz     short loc_14001B9BB
0x14001b9a4  mov     rcx, rsi; this
0x14001b9a7  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x14001b9ac  mov     rcx, rbx; this
0x14001b9af  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x14001b9b4  xor     edi, edi
0x14001b9b6  jmp     loc_14001BCB9
0x14001b9bb  cmp     dword ptr [rbx+38h], 0
0x14001b9bf  jnz     loc_14001BA55
0x14001b9c5  mov     eax, cs:dword_1400880C8
0x14001b9cb  mov     edi, 80004005h
0x14001b9d0  cmp     eax, 2
0x14001b9d3  jbe     short loc_14001BA48
0x14001b9d5  mov     eax, [rbx+38h]
0x14001b9d8  lea     rdx, byte_14007EC53
0x14001b9df  mov     dword ptr [rbp+57h+arg_0], eax
0x14001b9e2  lea     rax, aDestroythread; "DestroyThread"
0x14001b9e9  mov     [rbp+57h+var_50], rax
0x14001b9ed  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001b9f4  mov     [rbp+57h+var_40], rax
0x14001b9f8  lea     rax, aTryingToEndThr; "Trying to end thread ID %#x"
0x14001b9ff  mov     [rbp+57h+var_38], rax
0x14001ba03  lea     rax, [rbp+57h+arg_0]
0x14001ba07  mov     [rsp+0B0h+var_68], rax
0x14001ba0c  lea     rax, [rbp+57h+var_50]
0x14001ba10  mov     [rsp+0B0h+var_70], rax
0x14001ba15  lea     rax, [rbp+57h+arg_10]
0x14001ba19  mov     [rsp+0B0h+var_78], rax
0x14001ba1e  lea     rax, [rbp+57h+var_40]
0x14001ba22  mov     [rsp+0B0h+var_80], rax
0x14001ba27  lea     rax, [rbp+57h+arg_18]
0x14001ba2b  mov     [rsp+0B0h+var_88], rax
0x14001ba30  lea     rax, [rbp+57h+var_38]
0x14001ba34  mov     [rsp+0B0h+var_90], rax
0x14001ba39  mov     dword ptr [rbp+57h+arg_10], 211h
0x14001ba40  mov     [rbp+57h+arg_18], edi
0x14001ba43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001ba48  mov     rcx, rsi; this
0x14001ba4b  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x14001ba50  jmp     loc_14001BCB9
0x14001ba55  mov     rcx, rsi; this
0x14001ba58  mov     dword ptr [rbx+50h], 4
0x14001ba5f  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x14001ba64  mov     eax, cs:dword_1400880C8
0x14001ba6a  cmp     eax, 4
0x14001ba6d  jbe     short loc_14001BA9E
0x14001ba6f  mov     eax, [rbx+38h]
0x14001ba72  lea     rdx, dword_14007EC1C
0x14001ba79  mov     dword ptr [rbp+57h+arg_0], eax
0x14001ba7c  lea     rax, aAttemptToStopT; "Attempt to stop thread %#x"
0x14001ba83  mov     [rbp+57h+arg_10], rax
0x14001ba87  lea     rax, [rbp+57h+arg_0]
0x14001ba8b  mov     [rsp+0B0h+var_88], rax
0x14001ba90  lea     rax, [rbp+57h+arg_10]
0x14001ba94  mov     [rsp+0B0h+var_90], rax
0x14001ba99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001ba9e  mov     rcx, [rbx+2E0h]
0x14001baa5  mov     r8, [rbx+2C0h]
0x14001baac  mov     edx, [rbx+38h]
0x14001baaf  mov     rax, [rcx]
0x14001bab2  mov     rax, [rax+38h]
0x14001bab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001babb  mov     ecx, eax
0x14001babd  test    eax, eax
0x14001babf  jns     loc_14001BB58
0x14001bac5  mov     eax, cs:dword_1400880C8
0x14001bacb  cmp     eax, 2
0x14001bace  jbe     loc_14001BB58
0x14001bad4  mov     eax, [rbx+38h]
0x14001bad7  lea     rdx, byte_14007EBBD
0x14001bade  mov     dword ptr [rbp+57h+arg_10], eax
0x14001bae1  mov     edi, 80004005h
0x14001bae6  lea     rax, aDestroythread; "DestroyThread"
0x14001baed  mov     dword ptr [rbp+57h+arg_0], ecx
0x14001baf0  mov     [rbp+57h+var_38], rax
0x14001baf4  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001bafb  mov     [rbp+57h+var_40], rax
0x14001baff  lea     rax, aFailedToEndThr; "Failed to end thread ID %#x, HR = 0x%x"
0x14001bb06  mov     [rbp+57h+var_30], rax
0x14001bb0a  lea     rax, [rbp+57h+arg_0]
0x14001bb0e  mov     [rsp+0B0h+var_60], rax
0x14001bb13  lea     rax, [rbp+57h+arg_10]
0x14001bb17  mov     [rsp+0B0h+var_68], rax
0x14001bb1c  lea     rax, [rbp+57h+var_38]
0x14001bb20  mov     [rsp+0B0h+var_70], rax
0x14001bb25  lea     rax, [rbp+57h+arg_18]
0x14001bb29  mov     [rsp+0B0h+var_78], rax
0x14001bb2e  lea     rax, [rbp+57h+var_40]
0x14001bb32  mov     [rsp+0B0h+var_80], rax
0x14001bb37  lea     rax, [rbp+57h+var_50]
0x14001bb3b  mov     [rsp+0B0h+var_88], rax
0x14001bb40  lea     rax, [rbp+57h+var_30]
0x14001bb44  mov     [rsp+0B0h+var_90], rax
0x14001bb49  mov     [rbp+57h+arg_18], 224h
0x14001bb50  mov     dword ptr [rbp+57h+var_50], edi
0x14001bb53  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001bb58  mov     rcx, [rbx+2E0h]
0x14001bb5f  lea     rdx, [rbx+40h]
0x14001bb63  xor     r8d, r8d
0x14001bb66  test    r14d, r14d
0x14001bb69  mov     rax, [rcx]
0x14001bb6c  setz    r8b
0x14001bb70  xor     r9d, r9d
0x14001bb73  mov     r10, [rax+30h]
0x14001bb77  lea     rax, [rbp+57h+var_48]
0x14001bb7b  mov     [rsp+0B0h+var_78], rax
0x14001bb80  mov     eax, [rbx+90h]
0x14001bb86  mov     dword ptr [rsp+0B0h+var_80], r8d
0x14001bb8b  lea     r8d, [r9+1]
0x14001bb8f  mov     dword ptr [rsp+0B0h+var_88], 1
0x14001bb97  mov     dword ptr [rsp+0B0h+var_90], eax
0x14001bb9b  mov     rax, r10
0x14001bb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bba3  mov     edi, eax
0x14001bba5  cmp     eax, 834500CCh
0x14001bbaa  jnz     short loc_14001BBF5
0x14001bbac  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bbb3  lea     rax, WPP_GLOBAL_Control
0x14001bbba  cmp     rcx, rax
0x14001bbbd  jz      loc_14001BCB9
0x14001bbc3  test    byte ptr [rcx+1Ch], 1
0x14001bbc7  jz      loc_14001BCB9
0x14001bbcd  cmp     byte ptr [rcx+19h], 1
0x14001bbd1  jb      loc_14001BCB9
0x14001bbd7  mov     r9d, [rbx+38h]
0x14001bbdb  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001bbe2  mov     rcx, [rcx+10h]
0x14001bbe6  mov     edx, 22h ; '"'
0x14001bbeb  call    WPP_SF_d
0x14001bbf0  jmp     loc_14001BCB9
0x14001bbf5  cmp     eax, 834500CBh
0x14001bbfa  jnz     short loc_14001BC4B
0x14001bbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc03  lea     rax, WPP_GLOBAL_Control
0x14001bc0a  cmp     rcx, rax
0x14001bc0d  jz      loc_14001BCB9
0x14001bc13  test    byte ptr [rcx+1Ch], 1
0x14001bc17  jz      loc_14001BCB9
0x14001bc1d  cmp     byte ptr [rcx+19h], 1
0x14001bc21  jb      loc_14001BCB9
0x14001bc27  mov     edx, 23h ; '#'
0x14001bc2c  mov     rax, [rbx+40h]
0x14001bc30  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001bc37  mov     r9d, [rbx+38h]
0x14001bc3b  mov     rcx, [rcx+10h]
0x14001bc3f  mov     [rsp+0B0h+var_90], rax
0x14001bc44  call    WPP_SF_Dq
0x14001bc49  jmp     short loc_14001BCB9
0x14001bc4b  test    eax, eax
0x14001bc4d  jns     short loc_14001BC75
0x14001bc4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc56  lea     rax, WPP_GLOBAL_Control
0x14001bc5d  cmp     rcx, rax
0x14001bc60  jz      short loc_14001BCB9
0x14001bc62  test    byte ptr [rcx+1Ch], 1
0x14001bc66  jz      short loc_14001BCB9
0x14001bc68  cmp     byte ptr [rcx+19h], 1
0x14001bc6c  jb      short loc_14001BCB9
0x14001bc6e  mov     edx, 24h ; '$'
0x14001bc73  jmp     short loc_14001BC2C
0x14001bc75  mov     eax, cs:dword_1400880C8
0x14001bc7b  cmp     eax, 4
0x14001bc7e  jbe     short loc_14001BCAF
0x14001bc80  mov     eax, [rbx+38h]
0x14001bc83  lea     rdx, word_14007EB86
0x14001bc8a  mov     dword ptr [rbp+57h+arg_0], eax
0x14001bc8d  lea     rax, aThreadIdXExite; "Thread id %#x exited."
0x14001bc94  mov     [rbp+57h+arg_10], rax
0x14001bc98  lea     rax, [rbp+57h+arg_0]
0x14001bc9c  mov     [rsp+0B0h+var_88], rax
0x14001bca1  lea     rax, [rbp+57h+arg_10]
0x14001bca5  mov     [rsp+0B0h+var_90], rax
0x14001bcaa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001bcaf  xor     edi, edi
0x14001bcb1  mov     rcx, rbx; this
0x14001bcb4  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x14001bcb9  mov     eax, edi
0x14001bcbb  add     rsp, 90h
0x14001bcc2  pop     r14
0x14001bcc4  pop     rdi
0x14001bcc5  pop     rsi
0x14001bcc6  pop     rbx
0x14001bcc7  pop     rbp
0x14001bcc8  retn
```
