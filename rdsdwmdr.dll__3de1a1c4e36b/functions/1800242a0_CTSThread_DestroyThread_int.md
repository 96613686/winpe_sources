# CTSThread::DestroyThread(int)

- ea: `0x1800242a0`
- end: `0x1800246e4`
- name: `?DestroyThread@CTSThread@@UEAAJH@Z`
- size: `1092`
- prototype: `__int64 __fastcall(CTSThread *this)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800010f8`
- `0x180001564`
- `0x180001f98`
- `0x1800020bc`
- `0x18001a5f4`
- `0x18001d04c`
- `0x1800242a0`
- `0x180025a80`
- `0x180025be4`
- `0x180027b6c`
- `0x180027b98`
- `0x180028bec`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18002440d`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180024516`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800242e2`: `Thread initialized but not running. Bail destroy`
- `0x180024336`: `Destroying Bound Thread`
- `0x180024402`: `DestroyThread`
- `0x180024508`: `DestroyThread`
- `0x180024418`: `Trying to end thread ID %#x`
- `0x18002449e`: `Attempt to stop thread %#x`
- `0x180024521`: `Failed to end thread ID %#x, HR = 0x%x`
- `0x1800246a8`: `Thread id %#x exited.`

## pseudocode

```c
__int64 __fastcall CTSThread::DestroyThread(CTSThread *this)
{
  CTSReaderWriterLock *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx
  int v9; // edi
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int ActivityIdPrefix; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  const char *v26; // [rsp+60h] [rbp+7h] BYREF
  int v27; // [rsp+68h] [rbp+Fh]
  const char *v28; // [rsp+70h] [rbp+17h] BYREF
  const char *v29; // [rsp+78h] [rbp+1Fh] BYREF
  const char *v30; // [rsp+80h] [rbp+27h] BYREF
  const char *v31; // [rsp+C0h] [rbp+67h] BYREF
  const char *v32; // [rsp+D0h] [rbp+77h] BYREF
  int v33; // [rsp+D8h] [rbp+7Fh] BYREF

  v27 = 0;
  v2 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  v6 = *((_DWORD *)this + 20);
  if ( v6 == 1 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v31 = "Thread initialized but not running. Bail destroy";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (__int64)word_18003FDE2,
        v4,
        v5,
        (const unsigned __int16 **)&v31);
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
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v31 = "Destroying Bound Thread";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (__int64)byte_18003FDC1,
        v4,
        v5,
        (const unsigned __int16 **)&v31);
    }
    *((_DWORD *)this + 20) = 4;
    v9 = CTSThread::InternalRundownThread(this);
    if ( v9 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8, v10, v11);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix,
        v9);
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
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v31) = *((_DWORD *)this + 14);
      v26 = "DestroyThread";
      v28 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v29 = "Trying to end thread ID %#x";
      LODWORD(v32) = 529;
      v33 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v3,
        (__int64)&word_18003FD66,
        v4,
        v5,
        (const unsigned __int16 **)&v29,
        (__int64)&v33,
        (const unsigned __int16 **)&v28,
        (__int64)&v32,
        (const unsigned __int16 **)&v26,
        (__int64)&v31);
    }
    goto LABEL_22;
  }
  *((_DWORD *)this + 20) = 4;
  CTSReaderWriterLock::WriteUnlock(v2);
  if ( (unsigned int)dword_180044008 > 4 )
  {
    LODWORD(v31) = *((_DWORD *)this + 14);
    v32 = "Attempt to stop thread %#x";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v13,
      (__int64)&byte_18003FD2F,
      v14,
      v15,
      (const unsigned __int16 **)&v32,
      (__int64)&v31);
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 92) + 56LL))(
          *((_QWORD *)this + 92),
          *((unsigned int *)this + 14),
          *((_QWORD *)this + 88));
  if ( v16 < 0 && (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v32) = *((_DWORD *)this + 14);
    LODWORD(v31) = v16;
    v29 = "DestroyThread";
    v28 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v30 = "Failed to end thread ID %#x, HR = 0x%x";
    v33 = 548;
    LODWORD(v26) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)v16,
      (__int64)qword_18003FCD0,
      v17,
      v18,
      (const unsigned __int16 **)&v30,
      (__int64)&v26,
      (const unsigned __int16 **)&v28,
      (__int64)&v33,
      (const unsigned __int16 **)&v29,
      (__int64)&v32,
      (__int64)&v31);
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 92) + 48LL))(
          *((_QWORD *)this + 92),
          (char *)this + 64,
          1);
  v7 = v19;
  if ( v19 == -2092629812 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        *((unsigned int *)this + 14));
    }
    return v7;
  }
  if ( v19 == -2092629813 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return v7;
    }
    v24 = 35;
    goto LABEL_38;
  }
  if ( v19 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return v7;
    }
    v24 = 36;
LABEL_38:
    WPP_SF_Di(v23[2], v24, v21, *((unsigned int *)this + 14), *((_QWORD *)this + 8));
    return v7;
  }
  if ( (unsigned int)dword_180044008 > 4 )
  {
    LODWORD(v31) = *((_DWORD *)this + 14);
    v32 = "Thread id %#x exited.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v20,
      (__int64)byte_18003FC99,
      v21,
      v22,
      (const unsigned __int16 **)&v32,
      (__int64)&v31);
  }
  v7 = 0;
  CTSThread::InternalFreeThreadHandle(this);
  return v7;
}

```

## disassembly

```asm
0x1800242a0  push    rbp
0x1800242a2  push    rbx
0x1800242a3  push    rsi
0x1800242a4  push    rdi
0x1800242a5  push    r14
0x1800242a7  lea     rbp, [rsp-37h]
0x1800242ac  sub     rsp, 90h
0x1800242b3  mov     r14d, edx
0x1800242b6  mov     [rbp+57h+var_48], 0
0x1800242bd  mov     rbx, rcx
0x1800242c0  lea     rsi, [rcx+94h]
0x1800242c7  mov     rcx, rsi; this
0x1800242ca  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x1800242cf  mov     eax, [rbx+50h]
0x1800242d2  cmp     eax, 1
0x1800242d5  jnz     short loc_180024310
0x1800242d7  mov     eax, cs:dword_180044008
0x1800242dd  cmp     eax, 4
0x1800242e0  jbe     short loc_180024302
0x1800242e2  lea     rax, aThreadInitiali; "Thread initialized but not running. Bai"...
0x1800242e9  mov     [rbp+57h+arg_0], rax
0x1800242ed  lea     rdx, word_18003FDE2
0x1800242f4  lea     rax, [rbp+57h+arg_0]
0x1800242f8  mov     [rsp+0B0h+var_90], rax
0x1800242fd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180024302  mov     dword ptr [rbx+50h], 7
0x180024309  xor     edi, edi
0x18002430b  jmp     loc_180024468
0x180024310  cmp     dword ptr [rbx+0B8h], 0
0x180024317  jz      loc_1800243BF
0x18002431d  cmp     eax, 6
0x180024320  jz      short loc_18002432B
0x180024322  cmp     eax, 3
0x180024325  jnz     loc_1800243BF
0x18002432b  mov     eax, cs:dword_180044008
0x180024331  cmp     eax, 4
0x180024334  jbe     short loc_180024356
0x180024336  lea     rax, aDestroyingBoun; "Destroying Bound Thread"
0x18002433d  mov     [rbp+57h+arg_0], rax
0x180024341  lea     rdx, byte_18003FDC1
0x180024348  lea     rax, [rbp+57h+arg_0]
0x18002434c  mov     [rsp+0B0h+var_90], rax
0x180024351  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180024356  mov     rcx, rbx; this
0x180024359  mov     dword ptr [rbx+50h], 4
0x180024360  call    ?InternalRundownThread@CTSThread@@AEAAJXZ; CTSThread::InternalRundownThread(void)
0x180024365  mov     edi, eax
0x180024367  test    eax, eax
0x180024369  jns     short loc_1800243B2
0x18002436b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024372  lea     rax, WPP_GLOBAL_Control
0x180024379  cmp     rcx, rax
0x18002437c  jz      short loc_1800243B2
0x18002437e  test    byte ptr [rcx+1Ch], 8
0x180024382  jz      short loc_1800243B2
0x180024384  cmp     byte ptr [rcx+19h], 2
0x180024388  jb      short loc_1800243B2
0x18002438a  call    RdpX_GetActivityIdPrefix
0x18002438f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024396  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18002439d  mov     edx, 21h ; '!'
0x1800243a2  mov     dword ptr [rsp+0B0h+var_90], edi
0x1800243a6  mov     r9d, eax
0x1800243a9  mov     rcx, [rcx+10h]
0x1800243ad  call    WPP_SF_Dd
0x1800243b2  mov     rcx, rbx; this
0x1800243b5  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x1800243ba  jmp     loc_180024309
0x1800243bf  cmp     eax, 5
0x1800243c2  jnz     short loc_1800243DB
0x1800243c4  mov     rcx, rsi; this
0x1800243c7  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x1800243cc  mov     rcx, rbx; this
0x1800243cf  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x1800243d4  xor     edi, edi
0x1800243d6  jmp     loc_1800246D4
0x1800243db  cmp     dword ptr [rbx+38h], 0
0x1800243df  jnz     loc_180024475
0x1800243e5  mov     eax, cs:dword_180044008
0x1800243eb  mov     edi, 80004005h
0x1800243f0  cmp     eax, 2
0x1800243f3  jbe     short loc_180024468
0x1800243f5  mov     eax, [rbx+38h]
0x1800243f8  lea     rdx, word_18003FD66
0x1800243ff  mov     dword ptr [rbp+57h+arg_0], eax
0x180024402  lea     rax, aDestroythread; "DestroyThread"
0x180024409  mov     [rbp+57h+var_50], rax
0x18002440d  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180024414  mov     [rbp+57h+var_40], rax
0x180024418  lea     rax, aTryingToEndThr; "Trying to end thread ID %#x"
0x18002441f  mov     [rbp+57h+var_38], rax
0x180024423  lea     rax, [rbp+57h+arg_0]
0x180024427  mov     [rsp+0B0h+var_68], rax
0x18002442c  lea     rax, [rbp+57h+var_50]
0x180024430  mov     [rsp+0B0h+var_70], rax
0x180024435  lea     rax, [rbp+57h+arg_10]
0x180024439  mov     [rsp+0B0h+var_78], rax
0x18002443e  lea     rax, [rbp+57h+var_40]
0x180024442  mov     [rsp+0B0h+var_80], rax
0x180024447  lea     rax, [rbp+57h+arg_18]
0x18002444b  mov     [rsp+0B0h+var_88], rax
0x180024450  lea     rax, [rbp+57h+var_38]
0x180024454  mov     [rsp+0B0h+var_90], rax
0x180024459  mov     dword ptr [rbp+57h+arg_10], 211h
0x180024460  mov     [rbp+57h+arg_18], edi
0x180024463  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180024468  mov     rcx, rsi; this
0x18002446b  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180024470  jmp     loc_1800246D4
0x180024475  mov     rcx, rsi; this
0x180024478  mov     dword ptr [rbx+50h], 4
0x18002447f  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180024484  mov     r11d, cs:dword_180044008
0x18002448b  cmp     r11d, 4
0x18002448f  jbe     short loc_1800244C0
0x180024491  mov     eax, [rbx+38h]
0x180024494  lea     rdx, byte_18003FD2F
0x18002449b  mov     dword ptr [rbp+57h+arg_0], eax
0x18002449e  lea     rax, aAttemptToStopT; "Attempt to stop thread %#x"
0x1800244a5  mov     [rbp+57h+arg_10], rax
0x1800244a9  lea     rax, [rbp+57h+arg_0]
0x1800244ad  mov     [rsp+0B0h+var_88], rax
0x1800244b2  lea     rax, [rbp+57h+arg_10]
0x1800244b6  mov     [rsp+0B0h+var_90], rax
0x1800244bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800244c0  mov     rcx, [rbx+2E0h]
0x1800244c7  mov     r8, [rbx+2C0h]
0x1800244ce  mov     edx, [rbx+38h]
0x1800244d1  mov     rax, [rcx]
0x1800244d4  mov     rax, [rax+38h]
0x1800244d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244dd  mov     ecx, eax
0x1800244df  test    eax, eax
0x1800244e1  jns     loc_18002457A
0x1800244e7  mov     eax, cs:dword_180044008
0x1800244ed  cmp     eax, 2
0x1800244f0  jbe     loc_18002457A
0x1800244f6  mov     eax, [rbx+38h]
0x1800244f9  lea     rdx, qword_18003FCD0
0x180024500  mov     dword ptr [rbp+57h+arg_10], eax
0x180024503  mov     edi, 80004005h
0x180024508  lea     rax, aDestroythread; "DestroyThread"
0x18002450f  mov     dword ptr [rbp+57h+arg_0], ecx
0x180024512  mov     [rbp+57h+var_38], rax
0x180024516  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002451d  mov     [rbp+57h+var_40], rax
0x180024521  lea     rax, aFailedToEndThr; "Failed to end thread ID %#x, HR = 0x%x"
0x180024528  mov     [rbp+57h+var_30], rax
0x18002452c  lea     rax, [rbp+57h+arg_0]
0x180024530  mov     [rsp+0B0h+var_60], rax
0x180024535  lea     rax, [rbp+57h+arg_10]
0x180024539  mov     [rsp+0B0h+var_68], rax
0x18002453e  lea     rax, [rbp+57h+var_38]
0x180024542  mov     [rsp+0B0h+var_70], rax
0x180024547  lea     rax, [rbp+57h+arg_18]
0x18002454b  mov     [rsp+0B0h+var_78], rax
0x180024550  lea     rax, [rbp+57h+var_40]
0x180024554  mov     [rsp+0B0h+var_80], rax
0x180024559  lea     rax, [rbp+57h+var_50]
0x18002455d  mov     [rsp+0B0h+var_88], rax
0x180024562  lea     rax, [rbp+57h+var_30]
0x180024566  mov     [rsp+0B0h+var_90], rax
0x18002456b  mov     [rbp+57h+arg_18], 224h
0x180024572  mov     dword ptr [rbp+57h+var_50], edi
0x180024575  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002457a  mov     rcx, [rbx+2E0h]
0x180024581  lea     rdx, [rbx+40h]
0x180024585  xor     r8d, r8d
0x180024588  test    r14d, r14d
0x18002458b  mov     rax, [rcx]
0x18002458e  setz    r8b
0x180024592  xor     r9d, r9d
0x180024595  mov     r10, [rax+30h]
0x180024599  lea     rax, [rbp+57h+var_48]
0x18002459d  mov     [rsp+0B0h+var_78], rax
0x1800245a2  mov     eax, [rbx+90h]
0x1800245a8  mov     dword ptr [rsp+0B0h+var_80], r8d
0x1800245ad  lea     r8d, [r9+1]
0x1800245b1  mov     dword ptr [rsp+0B0h+var_88], 1
0x1800245b9  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800245bd  mov     rax, r10
0x1800245c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245c5  mov     edi, eax
0x1800245c7  cmp     eax, 834500CCh
0x1800245cc  jnz     short loc_180024617
0x1800245ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245d5  lea     rax, WPP_GLOBAL_Control
0x1800245dc  cmp     rcx, rax
0x1800245df  jz      loc_1800246D4
0x1800245e5  test    byte ptr [rcx+1Ch], 1
0x1800245e9  jz      loc_1800246D4
0x1800245ef  cmp     byte ptr [rcx+19h], 1
0x1800245f3  jb      loc_1800246D4
0x1800245f9  mov     r9d, [rbx+38h]
0x1800245fd  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180024604  mov     rcx, [rcx+10h]
0x180024608  mov     edx, 22h ; '"'
0x18002460d  call    WPP_SF_D
0x180024612  jmp     loc_1800246D4
0x180024617  cmp     eax, 834500CBh
0x18002461c  jnz     short loc_180024666
0x18002461e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024625  lea     rax, WPP_GLOBAL_Control
0x18002462c  cmp     rcx, rax
0x18002462f  jz      loc_1800246D4
0x180024635  test    byte ptr [rcx+1Ch], 1
0x180024639  jz      loc_1800246D4
0x18002463f  cmp     byte ptr [rcx+19h], 1
0x180024643  jb      loc_1800246D4
0x180024649  mov     edx, 23h ; '#'
0x18002464e  mov     rax, [rbx+40h]
0x180024652  mov     r9d, [rbx+38h]
0x180024656  mov     rcx, [rcx+10h]
0x18002465a  mov     [rsp+0B0h+var_90], rax
0x18002465f  call    WPP_SF_Di
0x180024664  jmp     short loc_1800246D4
0x180024666  test    eax, eax
0x180024668  jns     short loc_180024690
0x18002466a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024671  lea     rax, WPP_GLOBAL_Control
0x180024678  cmp     rcx, rax
0x18002467b  jz      short loc_1800246D4
0x18002467d  test    byte ptr [rcx+1Ch], 1
0x180024681  jz      short loc_1800246D4
0x180024683  cmp     byte ptr [rcx+19h], 1
0x180024687  jb      short loc_1800246D4
0x180024689  mov     edx, 24h ; '$'
0x18002468e  jmp     short loc_18002464E
0x180024690  mov     eax, cs:dword_180044008
0x180024696  cmp     eax, 4
0x180024699  jbe     short loc_1800246CA
0x18002469b  mov     eax, [rbx+38h]
0x18002469e  lea     rdx, byte_18003FC99
0x1800246a5  mov     dword ptr [rbp+57h+arg_0], eax
0x1800246a8  lea     rax, aThreadIdXExite; "Thread id %#x exited."
0x1800246af  mov     [rbp+57h+arg_10], rax
0x1800246b3  lea     rax, [rbp+57h+arg_0]
0x1800246b7  mov     [rsp+0B0h+var_88], rax
0x1800246bc  lea     rax, [rbp+57h+arg_10]
0x1800246c0  mov     [rsp+0B0h+var_90], rax
0x1800246c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800246ca  xor     edi, edi
0x1800246cc  mov     rcx, rbx; this
0x1800246cf  call    ?InternalFreeThreadHandle@CTSThread@@AEAAJXZ; CTSThread::InternalFreeThreadHandle(void)
0x1800246d4  mov     eax, edi
0x1800246d6  add     rsp, 90h
0x1800246dd  pop     r14
0x1800246df  pop     rdi
0x1800246e0  pop     rsi
0x1800246e1  pop     rbx
0x1800246e2  pop     rbp
0x1800246e3  retn
```
