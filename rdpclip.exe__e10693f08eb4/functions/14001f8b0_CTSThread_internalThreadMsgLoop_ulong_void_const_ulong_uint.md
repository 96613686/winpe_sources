# CTSThread::internalThreadMsgLoop(ulong,void * const *,ulong,uint *)

- ea: `0x14001f8b0`
- end: `0x14001fcc9`
- name: `?internalThreadMsgLoop@CTSThread@@IEAAJKPEBQEAXKPEAI@Z`
- size: `1049`
- prototype: `__int64 __usercall@<rax>(CTSThread *__hidden this@<rcx>, unsigned int@<edx>, void *const *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14001ee20`
- `0x14001fcd0`

## callees

- `0x1400010c0`
- `0x14000142c`
- `0x1400014d4`
- `0x1400015ec`
- `0x140001968`
- `0x1400030d3`
- `0x140005750`
- `0x14001d470`
- `0x14001dad0`
- `0x14001f634`
- `0x14001f8b0`
- `0x1400256b4`
- `0x14006a0e2`
- `0x14006a120`
- `0x14006b010`

## string_xrefs

- `0x14001f92e`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001fb8c`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001fc3c`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001f913`: `internalThreadMsgLoop`
- `0x14001fb78`: `internalThreadMsgLoop`
- `0x14001fc30`: `internalThreadMsgLoop`
- `0x14001f9b1`: `Entering thread msg loop for ID %#x`
- `0x14001f9f9`: `Leaving thread msg loop for ID %#x. Status: 0x%x`
- `0x14001fa97`: `Failed to run thread events`
- `0x14001fb1f`: `Thread msg queued`
- `0x14001fb98`: `Thread: 0x%x bailing out because of defered quit`
- `0x14001fc48`: `Thread: 0x%x bailing because of error while waiting on condition`

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
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ebx
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int ActivityIdPrefix; // eax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  const char *v25; // [rsp+58h] [rbp-A8h] BYREF
  const char *v26; // [rsp+60h] [rbp-A0h] BYREF
  const char *v27; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v29[64]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a2;
  memset_0(v29, 0, sizeof(v29));
  if ( (unsigned int)v6 >= 0x40 )
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v24 = 1854;
      v26 = "internalThreadMsgLoop";
      v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v25 = "Too many wait objects";
      v23 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)byte_14007E755,
        v10,
        v11,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v27,
        (__int64)&v24,
        (__int64)&v26);
    }
    return (unsigned int)-2147024809;
  }
  if ( !(_DWORD)v6 )
  {
    if ( (unsigned int)dword_1400880C8 > 5 )
    {
      v23 = *((_DWORD *)this + 14);
      v25 = "Entering thread msg loop for ID %#x";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&word_14007E71E,
        v10,
        v11,
        (__int64)&v25,
        (__int64)&v23);
    }
    v13 = CTSThread::internalMsgPump(this);
    v12 = v13;
    if ( (unsigned int)dword_1400880C8 > 5 )
    {
      v16 = *((_DWORD *)this + 14);
      v23 = v13;
      v25 = "Leaving thread msg loop for ID %#x. Status: 0x%x";
      v24 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)byte_14007E6E3,
        v14,
        v15,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23);
    }
    goto LABEL_10;
  }
  memcpy_0(v29, a3, 8 * v6);
  v29[v6] = *((_QWORD *)this + 86);
  v12 = CTSThread::RunAllQueueEvents(this, 0);
  if ( v12 >= 0 )
  {
    while ( 1 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD, int, _DWORD, _DWORD, unsigned int *))(**((_QWORD **)this + 92) + 48LL))(
              *((_QWORD *)this + 92),
              v29,
              (unsigned int)(v6 + 1),
              *((_QWORD *)this + 88),
              a4,
              0,
              0,
              a5);
      if ( v18 < 0 )
        break;
      if ( *a5 != (_DWORD)v6 )
        return 0;
      if ( (unsigned int)dword_1400880C8 > 5 )
      {
        v25 = "Thread msg queued";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)word_14007E6C2,
          v20,
          v21,
          (__int64)&v25);
      }
      CTSThread::OnNotifyThreadEventQueue(this);
    }
    if ( v18 == -2092629812 )
    {
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        v23 = *((_DWORD *)this + 14);
        v24 = 1928;
        v25 = "internalThreadMsgLoop";
        v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v28[0] = "Thread: 0x%x bailing out because of defered quit";
        LODWORD(v26) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)&byte_14007E667,
          v20,
          v21,
          (__int64)v28,
          (__int64)&v26,
          (__int64)&v27,
          (__int64)&v24,
          (__int64)&v25,
          (__int64)&v23);
      }
      *((_DWORD *)this + 45) = 1;
      *a5 = 0;
      return 0;
    }
    if ( v18 == -2092629813 )
    {
      v12 = -2092630012;
LABEL_10:
      *a5 = 0;
      return (unsigned int)v12;
    }
    v12 = -2147467259;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v26) = *((_DWORD *)this + 14);
      v28[0] = "internalThreadMsgLoop";
      v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v27 = "Thread: 0x%x bailing because of error while waiting on condition";
      v23 = 1944;
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&dword_14007E60C,
        v20,
        v21,
        (__int64)&v27,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)v28,
        (__int64)&v26);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
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
0x14001f8b0  mov     [rsp-8+arg_10], rbx
0x14001f8b5  push    rbp
0x14001f8b6  push    rsi
0x14001f8b7  push    rdi
0x14001f8b8  push    r14
0x14001f8ba  push    r15
0x14001f8bc  lea     rbp, [rsp-190h]
0x14001f8c4  sub     rsp, 290h
0x14001f8cb  mov     rax, cs:__security_cookie
0x14001f8d2  xor     rax, rsp
0x14001f8d5  mov     [rbp+1B0h+var_30], rax
0x14001f8dc  mov     r14, [rbp+1B0h+arg_20]
0x14001f8e3  mov     rbx, r8
0x14001f8e6  mov     esi, edx
0x14001f8e8  mov     rdi, rcx
0x14001f8eb  xor     edx, edx; Val
0x14001f8ed  lea     rcx, [rbp+1B0h+var_230]; void *
0x14001f8f1  mov     r8d, 200h; Size
0x14001f8f7  mov     r15d, r9d
0x14001f8fa  call    memset_0
0x14001f8ff  cmp     esi, 40h ; '@'
0x14001f902  jb      loc_14001F990
0x14001f908  mov     eax, cs:dword_1400880C8
0x14001f90e  cmp     eax, 2
0x14001f911  jbe     short loc_14001F986
0x14001f913  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x14001f91a  mov     [rsp+2B0h+var_25C], 73Eh
0x14001f922  mov     [rsp+2B0h+var_250], rax
0x14001f927  lea     rdx, byte_14007E755
0x14001f92e  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001f935  mov     ebx, 80004005h
0x14001f93a  mov     [rsp+2B0h+var_248], rax
0x14001f93f  lea     rax, aTooManyWaitObj; "Too many wait objects"
0x14001f946  mov     [rsp+2B0h+var_258], rax
0x14001f94b  lea     rax, [rsp+2B0h+var_250]
0x14001f950  mov     [rsp+2B0h+var_270], rax
0x14001f955  lea     rax, [rsp+2B0h+var_25C]
0x14001f95a  mov     [rsp+2B0h+var_278], rax
0x14001f95f  lea     rax, [rsp+2B0h+var_248]
0x14001f964  mov     [rsp+2B0h+var_280], rax
0x14001f969  lea     rax, [rsp+2B0h+var_260]
0x14001f96e  mov     [rsp+2B0h+var_288], rax
0x14001f973  lea     rax, [rsp+2B0h+var_258]
0x14001f978  mov     [rsp+2B0h+var_290], rax
0x14001f97d  mov     [rsp+2B0h+var_260], ebx
0x14001f981  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001f986  mov     ebx, 80070057h
0x14001f98b  jmp     loc_14001FCA1
0x14001f990  test    esi, esi
0x14001f992  jnz     loc_14001FA38
0x14001f998  mov     eax, cs:dword_1400880C8
0x14001f99e  cmp     eax, 5
0x14001f9a1  jbe     short loc_14001F9D6
0x14001f9a3  mov     eax, [rdi+38h]
0x14001f9a6  lea     rdx, word_14007E71E
0x14001f9ad  mov     [rsp+2B0h+var_260], eax
0x14001f9b1  lea     rax, aEnteringThread; "Entering thread msg loop for ID %#x"
0x14001f9b8  mov     [rsp+2B0h+var_258], rax
0x14001f9bd  lea     rax, [rsp+2B0h+var_260]
0x14001f9c2  mov     [rsp+2B0h+var_288], rax
0x14001f9c7  lea     rax, [rsp+2B0h+var_258]
0x14001f9cc  mov     [rsp+2B0h+var_290], rax
0x14001f9d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001f9d6  mov     rcx, rdi; this
0x14001f9d9  call    ?internalMsgPump@CTSThread@@IEAAJXZ; CTSThread::internalMsgPump(void)
0x14001f9de  mov     ecx, cs:dword_1400880C8
0x14001f9e4  mov     ebx, eax
0x14001f9e6  cmp     ecx, 5
0x14001f9e9  jbe     short loc_14001FA2C
0x14001f9eb  mov     ecx, [rdi+38h]
0x14001f9ee  lea     rdx, byte_14007E6E3
0x14001f9f5  mov     [rsp+2B0h+var_260], eax
0x14001f9f9  lea     rax, aLeavingThreadM; "Leaving thread msg loop for ID %#x. Sta"...
0x14001fa00  mov     [rsp+2B0h+var_258], rax
0x14001fa05  lea     rax, [rsp+2B0h+var_260]
0x14001fa0a  mov     [rsp+2B0h+var_280], rax
0x14001fa0f  lea     rax, [rsp+2B0h+var_25C]
0x14001fa14  mov     [rsp+2B0h+var_288], rax
0x14001fa19  lea     rax, [rsp+2B0h+var_258]
0x14001fa1e  mov     [rsp+2B0h+var_290], rax
0x14001fa23  mov     [rsp+2B0h+var_25C], ecx
0x14001fa27  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001fa2c  mov     dword ptr [r14], 0
0x14001fa33  jmp     loc_14001FCA1
0x14001fa38  mov     r8, rsi
0x14001fa3b  lea     rcx, [rbp+1B0h+var_230]; void *
0x14001fa3f  shl     r8, 3; Size
0x14001fa43  mov     rdx, rbx; Src
0x14001fa46  call    memcpy_0
0x14001fa4b  mov     rax, [rdi+2B0h]
0x14001fa52  xor     edx, edx; struct ITSEventFilter *
0x14001fa54  mov     rcx, rdi; this
0x14001fa57  mov     [rbp+rsi*8+1B0h+var_230], rax
0x14001fa5c  call    ?RunAllQueueEvents@CTSThread@@MEAAJPEAVITSEventFilter@@@Z; CTSThread::RunAllQueueEvents(ITSEventFilter *)
0x14001fa61  mov     ebx, eax
0x14001fa63  test    eax, eax
0x14001fa65  jns     short loc_14001FACB
0x14001fa67  mov     rax, cs:WPP_GLOBAL_Control
0x14001fa6e  lea     rcx, WPP_GLOBAL_Control
0x14001fa75  cmp     rax, rcx
0x14001fa78  jz      loc_14001FCA1
0x14001fa7e  test    byte ptr [rax+1Ch], 8
0x14001fa82  jz      loc_14001FCA1
0x14001fa88  cmp     byte ptr [rax+19h], 2
0x14001fa8c  jb      loc_14001FCA1
0x14001fa92  call    RdpX_GetActivityIdPrefix
0x14001fa97  lea     rcx, aFailedToRunThr; "Failed to run thread events"
0x14001fa9e  mov     dword ptr [rsp+2B0h+var_288], ebx
0x14001faa2  mov     [rsp+2B0h+var_290], rcx
0x14001faa7  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001faae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fab5  mov     edx, 5Fh ; '_'
0x14001faba  mov     r9d, eax
0x14001fabd  mov     rcx, [rcx+10h]
0x14001fac1  call    WPP_SF_DsD
0x14001fac6  jmp     loc_14001FCA1
0x14001facb  mov     rcx, [rdi+2E0h]
0x14001fad2  lea     r8d, [rsi+1]
0x14001fad6  mov     r9, [rdi+2C0h]
0x14001fadd  lea     rdx, [rbp+1B0h+var_230]
0x14001fae1  mov     [rsp+2B0h+var_278], r14
0x14001fae6  mov     dword ptr [rsp+2B0h+var_280], 0
0x14001faee  mov     rax, [rcx]
0x14001faf1  mov     dword ptr [rsp+2B0h+var_288], 0
0x14001faf9  mov     dword ptr [rsp+2B0h+var_290], r15d
0x14001fafe  mov     rax, [rax+30h]
0x14001fb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fb07  test    eax, eax
0x14001fb09  js      short loc_14001FB4B
0x14001fb0b  cmp     [r14], esi
0x14001fb0e  jnz     loc_14001FBFA
0x14001fb14  mov     eax, cs:dword_1400880C8
0x14001fb1a  cmp     eax, 5
0x14001fb1d  jbe     short loc_14001FB41
0x14001fb1f  lea     rax, aThreadMsgQueue; "Thread msg queued"
0x14001fb26  mov     [rsp+2B0h+var_258], rax
0x14001fb2b  lea     rdx, word_14007E6C2
0x14001fb32  lea     rax, [rsp+2B0h+var_258]
0x14001fb37  mov     [rsp+2B0h+var_290], rax
0x14001fb3c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14001fb41  mov     rcx, rdi; this
0x14001fb44  call    ?OnNotifyThreadEventQueue@CTSThread@@UEAAJXZ; CTSThread::OnNotifyThreadEventQueue(void)
0x14001fb49  jmp     short loc_14001FACB
0x14001fb4b  cmp     eax, 834500CCh
0x14001fb50  jnz     loc_14001FC01
0x14001fb56  mov     eax, cs:dword_1400880C8
0x14001fb5c  cmp     eax, 2
0x14001fb5f  jbe     loc_14001FBE9
0x14001fb65  mov     eax, [rdi+38h]
0x14001fb68  lea     rdx, byte_14007E667
0x14001fb6f  mov     [rsp+2B0h+var_260], eax
0x14001fb73  mov     ebx, 80004005h
0x14001fb78  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x14001fb7f  mov     [rsp+2B0h+var_25C], 788h
0x14001fb87  mov     [rsp+2B0h+var_258], rax
0x14001fb8c  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001fb93  mov     [rsp+2B0h+var_248], rax
0x14001fb98  lea     rax, aThread0xXBaili; "Thread: 0x%x bailing out because of def"...
0x14001fb9f  mov     [rsp+2B0h+var_240], rax
0x14001fba4  lea     rax, [rsp+2B0h+var_260]
0x14001fba9  mov     [rsp+2B0h+var_268], rax
0x14001fbae  lea     rax, [rsp+2B0h+var_258]
0x14001fbb3  mov     [rsp+2B0h+var_270], rax
0x14001fbb8  lea     rax, [rsp+2B0h+var_25C]
0x14001fbbd  mov     [rsp+2B0h+var_278], rax
0x14001fbc2  lea     rax, [rsp+2B0h+var_248]
0x14001fbc7  mov     [rsp+2B0h+var_280], rax
0x14001fbcc  lea     rax, [rsp+2B0h+var_250]
0x14001fbd1  mov     [rsp+2B0h+var_288], rax
0x14001fbd6  lea     rax, [rsp+2B0h+var_240]
0x14001fbdb  mov     [rsp+2B0h+var_290], rax
0x14001fbe0  mov     dword ptr [rsp+2B0h+var_250], ebx
0x14001fbe4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001fbe9  mov     dword ptr [rdi+0B4h], 1
0x14001fbf3  mov     dword ptr [r14], 0
0x14001fbfa  xor     ebx, ebx
0x14001fbfc  jmp     loc_14001FCA1
0x14001fc01  cmp     eax, 834500CBh
0x14001fc06  jnz     short loc_14001FC12
0x14001fc08  mov     ebx, 83450004h
0x14001fc0d  jmp     loc_14001FA2C
0x14001fc12  mov     eax, cs:dword_1400880C8
0x14001fc18  mov     ebx, 80004005h
0x14001fc1d  cmp     eax, 2
0x14001fc20  jbe     short loc_14001FCA1
0x14001fc22  mov     eax, [rdi+38h]
0x14001fc25  lea     rdx, dword_14007E60C
0x14001fc2c  mov     dword ptr [rsp+2B0h+var_250], eax
0x14001fc30  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x14001fc37  mov     [rsp+2B0h+var_240], rax
0x14001fc3c  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001fc43  mov     [rsp+2B0h+var_258], rax
0x14001fc48  lea     rax, aThread0xXBaili_0; "Thread: 0x%x bailing because of error w"...
0x14001fc4f  mov     [rsp+2B0h+var_248], rax
0x14001fc54  lea     rax, [rsp+2B0h+var_250]
0x14001fc59  mov     [rsp+2B0h+var_268], rax
0x14001fc5e  lea     rax, [rsp+2B0h+var_240]
0x14001fc63  mov     [rsp+2B0h+var_270], rax
0x14001fc68  lea     rax, [rsp+2B0h+var_260]
0x14001fc6d  mov     [rsp+2B0h+var_278], rax
0x14001fc72  lea     rax, [rsp+2B0h+var_258]
0x14001fc77  mov     [rsp+2B0h+var_280], rax
0x14001fc7c  lea     rax, [rsp+2B0h+var_25C]
0x14001fc81  mov     [rsp+2B0h+var_288], rax
0x14001fc86  lea     rax, [rsp+2B0h+var_248]
0x14001fc8b  mov     [rsp+2B0h+var_290], rax
0x14001fc90  mov     [rsp+2B0h+var_260], 798h
0x14001fc98  mov     [rsp+2B0h+var_25C], ebx
0x14001fc9c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001fca1  mov     eax, ebx
0x14001fca3  mov     rcx, [rbp+1B0h+var_30]
0x14001fcaa  xor     rcx, rsp; StackCookie
0x14001fcad  call    __security_check_cookie
0x14001fcb2  mov     rbx, [rsp+2B0h+arg_10]
0x14001fcba  add     rsp, 290h
0x14001fcc1  pop     r15
0x14001fcc3  pop     r14
0x14001fcc5  pop     rdi
0x14001fcc6  pop     rsi
0x14001fcc7  pop     rbp
0x14001fcc8  retn
```
