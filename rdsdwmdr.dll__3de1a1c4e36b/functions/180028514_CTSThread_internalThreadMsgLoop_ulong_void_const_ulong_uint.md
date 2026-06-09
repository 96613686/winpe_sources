# CTSThread::internalThreadMsgLoop(ulong,void * const *,ulong,uint *)

- ea: `0x180028514`
- end: `0x18002892d`
- name: `?internalThreadMsgLoop@CTSThread@@IEAAJKPEBQEAXKPEAI@Z`
- size: `1049`
- prototype: `__int64 __fastcall(CTSThread *this, unsigned int, void *const *, int, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800277e0`
- `0x180028934`

## callees

- `0x1800010f8`
- `0x180001564`
- `0x18000160c`
- `0x180001868`
- `0x180001f98`
- `0x18001d114`
- `0x180025d90`
- `0x180026480`
- `0x180028298`
- `0x180028514`
- `0x18002a1c4`
- `0x18002b922`
- `0x18002b93a`
- `0x18002b960`
- `0x18002c010`

## string_xrefs

- `0x180028592`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800287f0`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800288a0`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180028577`: `internalThreadMsgLoop`
- `0x1800287dc`: `internalThreadMsgLoop`
- `0x180028894`: `internalThreadMsgLoop`
- `0x180028615`: `Entering thread msg loop for ID %#x`
- `0x18002865d`: `Leaving thread msg loop for ID %#x. Status: 0x%x`
- `0x1800286fb`: `Failed to run thread events`
- `0x180028783`: `Thread msg queued`
- `0x1800287fc`: `Thread: 0x%x bailing out because of defered quit`
- `0x1800288ac`: `Thread: 0x%x bailing because of error while waiting on condition`

## pseudocode

```c
__int64 __fastcall CTSThread::internalThreadMsgLoop(
        CTSThread *this,
        unsigned int a2,
        void *const *a3,
        int a4,
        unsigned int *a5)
{
  __int64 v6; // rsi
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // ebx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int ActivityIdPrefix; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  const char *v28; // [rsp+58h] [rbp-A8h] BYREF
  const char *v29; // [rsp+60h] [rbp-A0h] BYREF
  const char *v30; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v31[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v32[64]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a2;
  memset_0(v32, 0, sizeof(v32));
  if ( (unsigned int)v6 >= 0x40 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v27 = 1854;
      v29 = "internalThreadMsgLoop";
      v30 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v28 = "Too many wait objects";
      v26 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (__int64)qword_18003F868,
        v10,
        v11,
        (const unsigned __int16 **)&v28,
        (__int64)&v26,
        (const unsigned __int16 **)&v30,
        (__int64)&v27,
        (const unsigned __int16 **)&v29);
    }
    return (unsigned int)-2147024809;
  }
  if ( !(_DWORD)v6 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v26 = *((_DWORD *)this + 14);
      v28 = "Entering thread msg loop for ID %#x";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)byte_18003F831,
        v10,
        v11,
        (const unsigned __int16 **)&v28,
        (__int64)&v26);
    }
    v13 = CTSThread::internalMsgPump(this);
    v12 = v13;
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v16 = *((unsigned int *)this + 14);
      v26 = v13;
      v28 = "Leaving thread msg loop for ID %#x. Status: 0x%x";
      v27 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v16,
        (__int64)&word_18003F7F6,
        v14,
        v15,
        (const unsigned __int16 **)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
    goto LABEL_10;
  }
  memcpy_0(v32, a3, 8 * v6);
  v32[v6] = *((_QWORD *)this + 86);
  v12 = CTSThread::RunAllQueueEvents(this, 0);
  if ( v12 >= 0 )
  {
    while ( 1 )
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD, int, _DWORD, _DWORD, unsigned int *))(**((_QWORD **)this + 92) + 48LL))(
              *((_QWORD *)this + 92),
              v32,
              (unsigned int)(v6 + 1),
              *((_QWORD *)this + 88),
              a4,
              0,
              0,
              a5);
      if ( v21 < 0 )
        break;
      if ( *a5 != (_DWORD)v6 )
        return 0;
      if ( (unsigned int)dword_180044008 > 5 )
      {
        v28 = "Thread msg queued";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v22,
          (__int64)byte_18003F7D5,
          v23,
          v24,
          (const unsigned __int16 **)&v28);
      }
      CTSThread::OnNotifyThreadEventQueue(this);
    }
    if ( v21 == -2092629812 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v26 = *((_DWORD *)this + 14);
        v27 = 1928;
        v28 = "internalThreadMsgLoop";
        v30 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v31[0] = (const unsigned __int16 *)"Thread: 0x%x bailing out because of defered quit";
        LODWORD(v29) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v22,
          (__int64)word_18003F77A,
          v23,
          v24,
          v31,
          (__int64)&v29,
          (const unsigned __int16 **)&v30,
          (__int64)&v27,
          (const unsigned __int16 **)&v28,
          (__int64)&v26);
      }
      *((_DWORD *)this + 45) = 1;
      *a5 = 0;
      return 0;
    }
    if ( v21 == -2092629813 )
    {
      v12 = -2092630012;
LABEL_10:
      *a5 = 0;
      return (unsigned int)v12;
    }
    v12 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v29) = *((_DWORD *)this + 14);
      v31[0] = (const unsigned __int16 *)"internalThreadMsgLoop";
      v28 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v30 = "Thread: 0x%x bailing because of error while waiting on condition";
      v26 = 1944;
      v27 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v22,
        (__int64)&byte_18003F71F,
        v23,
        v24,
        (const unsigned __int16 **)&v30,
        (__int64)&v27,
        (const unsigned __int16 **)&v28,
        (__int64)&v26,
        v31,
        (__int64)&v29);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v17, v18, v19);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)"Failed to run thread events",
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180028514  mov     [rsp-8+arg_10], rbx
0x180028519  push    rbp
0x18002851a  push    rsi
0x18002851b  push    rdi
0x18002851c  push    r14
0x18002851e  push    r15
0x180028520  lea     rbp, [rsp-190h]
0x180028528  sub     rsp, 290h
0x18002852f  mov     rax, cs:__security_cookie
0x180028536  xor     rax, rsp
0x180028539  mov     [rbp+1B0h+var_30], rax
0x180028540  mov     r14, [rbp+1B0h+arg_20]
0x180028547  mov     rbx, r8
0x18002854a  mov     esi, edx
0x18002854c  mov     rdi, rcx
0x18002854f  xor     edx, edx; Val
0x180028551  lea     rcx, [rbp+1B0h+var_230]; void *
0x180028555  mov     r8d, 200h; Size
0x18002855b  mov     r15d, r9d
0x18002855e  call    memset_0
0x180028563  cmp     esi, 40h ; '@'
0x180028566  jb      loc_1800285F4
0x18002856c  mov     eax, cs:dword_180044008
0x180028572  cmp     eax, 2
0x180028575  jbe     short loc_1800285EA
0x180028577  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x18002857e  mov     [rsp+2B0h+var_25C], 73Eh
0x180028586  mov     [rsp+2B0h+var_250], rax
0x18002858b  lea     rdx, qword_18003F868
0x180028592  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180028599  mov     ebx, 80004005h
0x18002859e  mov     [rsp+2B0h+var_248], rax
0x1800285a3  lea     rax, aTooManyWaitObj; "Too many wait objects"
0x1800285aa  mov     [rsp+2B0h+var_258], rax
0x1800285af  lea     rax, [rsp+2B0h+var_250]
0x1800285b4  mov     [rsp+2B0h+var_270], rax
0x1800285b9  lea     rax, [rsp+2B0h+var_25C]
0x1800285be  mov     [rsp+2B0h+var_278], rax
0x1800285c3  lea     rax, [rsp+2B0h+var_248]
0x1800285c8  mov     [rsp+2B0h+var_280], rax
0x1800285cd  lea     rax, [rsp+2B0h+var_260]
0x1800285d2  mov     [rsp+2B0h+var_288], rax
0x1800285d7  lea     rax, [rsp+2B0h+var_258]
0x1800285dc  mov     [rsp+2B0h+var_290], rax
0x1800285e1  mov     [rsp+2B0h+var_260], ebx
0x1800285e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800285ea  mov     ebx, 80070057h
0x1800285ef  jmp     loc_180028905
0x1800285f4  test    esi, esi
0x1800285f6  jnz     loc_18002869C
0x1800285fc  mov     eax, cs:dword_180044008
0x180028602  cmp     eax, 5
0x180028605  jbe     short loc_18002863A
0x180028607  mov     eax, [rdi+38h]
0x18002860a  lea     rdx, byte_18003F831
0x180028611  mov     [rsp+2B0h+var_260], eax
0x180028615  lea     rax, aEnteringThread; "Entering thread msg loop for ID %#x"
0x18002861c  mov     [rsp+2B0h+var_258], rax
0x180028621  lea     rax, [rsp+2B0h+var_260]
0x180028626  mov     [rsp+2B0h+var_288], rax
0x18002862b  lea     rax, [rsp+2B0h+var_258]
0x180028630  mov     [rsp+2B0h+var_290], rax
0x180028635  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002863a  mov     rcx, rdi; this
0x18002863d  call    ?internalMsgPump@CTSThread@@IEAAJXZ; CTSThread::internalMsgPump(void)
0x180028642  mov     ecx, cs:dword_180044008
0x180028648  mov     ebx, eax
0x18002864a  cmp     ecx, 5
0x18002864d  jbe     short loc_180028690
0x18002864f  mov     ecx, [rdi+38h]
0x180028652  lea     rdx, word_18003F7F6
0x180028659  mov     [rsp+2B0h+var_260], eax
0x18002865d  lea     rax, aLeavingThreadM; "Leaving thread msg loop for ID %#x. Sta"...
0x180028664  mov     [rsp+2B0h+var_258], rax
0x180028669  lea     rax, [rsp+2B0h+var_260]
0x18002866e  mov     [rsp+2B0h+var_280], rax
0x180028673  lea     rax, [rsp+2B0h+var_25C]
0x180028678  mov     [rsp+2B0h+var_288], rax
0x18002867d  lea     rax, [rsp+2B0h+var_258]
0x180028682  mov     [rsp+2B0h+var_290], rax
0x180028687  mov     [rsp+2B0h+var_25C], ecx
0x18002868b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180028690  mov     dword ptr [r14], 0
0x180028697  jmp     loc_180028905
0x18002869c  mov     r8, rsi
0x18002869f  lea     rcx, [rbp+1B0h+var_230]; void *
0x1800286a3  shl     r8, 3; Size
0x1800286a7  mov     rdx, rbx; Src
0x1800286aa  call    memcpy_0
0x1800286af  mov     rax, [rdi+2B0h]
0x1800286b6  xor     edx, edx; struct ITSEventFilter *
0x1800286b8  mov     rcx, rdi; this
0x1800286bb  mov     [rbp+rsi*8+1B0h+var_230], rax
0x1800286c0  call    ?RunAllQueueEvents@CTSThread@@MEAAJPEAVITSEventFilter@@@Z; CTSThread::RunAllQueueEvents(ITSEventFilter *)
0x1800286c5  mov     ebx, eax
0x1800286c7  test    eax, eax
0x1800286c9  jns     short loc_18002872F
0x1800286cb  mov     rax, cs:WPP_GLOBAL_Control
0x1800286d2  lea     rcx, WPP_GLOBAL_Control
0x1800286d9  cmp     rax, rcx
0x1800286dc  jz      loc_180028905
0x1800286e2  test    byte ptr [rax+1Ch], 8
0x1800286e6  jz      loc_180028905
0x1800286ec  cmp     byte ptr [rax+19h], 2
0x1800286f0  jb      loc_180028905
0x1800286f6  call    RdpX_GetActivityIdPrefix
0x1800286fb  lea     rcx, aFailedToRunThr; "Failed to run thread events"
0x180028702  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180028706  mov     [rsp+2B0h+var_290], rcx
0x18002870b  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180028712  mov     rcx, cs:WPP_GLOBAL_Control
0x180028719  mov     edx, 5Fh ; '_'
0x18002871e  mov     r9d, eax
0x180028721  mov     rcx, [rcx+10h]
0x180028725  call    WPP_SF_DsD
0x18002872a  jmp     loc_180028905
0x18002872f  mov     rcx, [rdi+2E0h]
0x180028736  lea     r8d, [rsi+1]
0x18002873a  mov     r9, [rdi+2C0h]
0x180028741  lea     rdx, [rbp+1B0h+var_230]
0x180028745  mov     [rsp+2B0h+var_278], r14
0x18002874a  mov     dword ptr [rsp+2B0h+var_280], 0
0x180028752  mov     rax, [rcx]
0x180028755  mov     dword ptr [rsp+2B0h+var_288], 0
0x18002875d  mov     dword ptr [rsp+2B0h+var_290], r15d
0x180028762  mov     rax, [rax+30h]
0x180028766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002876b  test    eax, eax
0x18002876d  js      short loc_1800287AF
0x18002876f  cmp     [r14], esi
0x180028772  jnz     loc_18002885E
0x180028778  mov     eax, cs:dword_180044008
0x18002877e  cmp     eax, 5
0x180028781  jbe     short loc_1800287A5
0x180028783  lea     rax, aThreadMsgQueue; "Thread msg queued"
0x18002878a  mov     [rsp+2B0h+var_258], rax
0x18002878f  lea     rdx, byte_18003F7D5
0x180028796  lea     rax, [rsp+2B0h+var_258]
0x18002879b  mov     [rsp+2B0h+var_290], rax
0x1800287a0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800287a5  mov     rcx, rdi; this
0x1800287a8  call    ?OnNotifyThreadEventQueue@CTSThread@@UEAAJXZ; CTSThread::OnNotifyThreadEventQueue(void)
0x1800287ad  jmp     short loc_18002872F
0x1800287af  cmp     eax, 834500CCh
0x1800287b4  jnz     loc_180028865
0x1800287ba  mov     eax, cs:dword_180044008
0x1800287c0  cmp     eax, 2
0x1800287c3  jbe     loc_18002884D
0x1800287c9  mov     eax, [rdi+38h]
0x1800287cc  lea     rdx, word_18003F77A
0x1800287d3  mov     [rsp+2B0h+var_260], eax
0x1800287d7  mov     ebx, 80004005h
0x1800287dc  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x1800287e3  mov     [rsp+2B0h+var_25C], 788h
0x1800287eb  mov     [rsp+2B0h+var_258], rax
0x1800287f0  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800287f7  mov     [rsp+2B0h+var_248], rax
0x1800287fc  lea     rax, aThread0xXBaili; "Thread: 0x%x bailing out because of def"...
0x180028803  mov     [rsp+2B0h+var_240], rax
0x180028808  lea     rax, [rsp+2B0h+var_260]
0x18002880d  mov     [rsp+2B0h+var_268], rax
0x180028812  lea     rax, [rsp+2B0h+var_258]
0x180028817  mov     [rsp+2B0h+var_270], rax
0x18002881c  lea     rax, [rsp+2B0h+var_25C]
0x180028821  mov     [rsp+2B0h+var_278], rax
0x180028826  lea     rax, [rsp+2B0h+var_248]
0x18002882b  mov     [rsp+2B0h+var_280], rax
0x180028830  lea     rax, [rsp+2B0h+var_250]
0x180028835  mov     [rsp+2B0h+var_288], rax
0x18002883a  lea     rax, [rsp+2B0h+var_240]
0x18002883f  mov     [rsp+2B0h+var_290], rax
0x180028844  mov     dword ptr [rsp+2B0h+var_250], ebx
0x180028848  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002884d  mov     dword ptr [rdi+0B4h], 1
0x180028857  mov     dword ptr [r14], 0
0x18002885e  xor     ebx, ebx
0x180028860  jmp     loc_180028905
0x180028865  cmp     eax, 834500CBh
0x18002886a  jnz     short loc_180028876
0x18002886c  mov     ebx, 83450004h
0x180028871  jmp     loc_180028690
0x180028876  mov     eax, cs:dword_180044008
0x18002887c  mov     ebx, 80004005h
0x180028881  cmp     eax, 2
0x180028884  jbe     short loc_180028905
0x180028886  mov     eax, [rdi+38h]
0x180028889  lea     rdx, byte_18003F71F
0x180028890  mov     dword ptr [rsp+2B0h+var_250], eax
0x180028894  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x18002889b  mov     [rsp+2B0h+var_240], rax
0x1800288a0  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800288a7  mov     [rsp+2B0h+var_258], rax
0x1800288ac  lea     rax, aThread0xXBaili_0; "Thread: 0x%x bailing because of error w"...
0x1800288b3  mov     [rsp+2B0h+var_248], rax
0x1800288b8  lea     rax, [rsp+2B0h+var_250]
0x1800288bd  mov     [rsp+2B0h+var_268], rax
0x1800288c2  lea     rax, [rsp+2B0h+var_240]
0x1800288c7  mov     [rsp+2B0h+var_270], rax
0x1800288cc  lea     rax, [rsp+2B0h+var_260]
0x1800288d1  mov     [rsp+2B0h+var_278], rax
0x1800288d6  lea     rax, [rsp+2B0h+var_258]
0x1800288db  mov     [rsp+2B0h+var_280], rax
0x1800288e0  lea     rax, [rsp+2B0h+var_25C]
0x1800288e5  mov     [rsp+2B0h+var_288], rax
0x1800288ea  lea     rax, [rsp+2B0h+var_248]
0x1800288ef  mov     [rsp+2B0h+var_290], rax
0x1800288f4  mov     [rsp+2B0h+var_260], 798h
0x1800288fc  mov     [rsp+2B0h+var_25C], ebx
0x180028900  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180028905  mov     eax, ebx
0x180028907  mov     rcx, [rbp+1B0h+var_30]
0x18002890e  xor     rcx, rsp; StackCookie
0x180028911  call    __security_check_cookie
0x180028916  mov     rbx, [rsp+2B0h+arg_10]
0x18002891e  add     rsp, 290h
0x180028925  pop     r15
0x180028927  pop     r14
0x180028929  pop     rdi
0x18002892a  pop     rsi
0x18002892b  pop     rbp
0x18002892c  retn
```
