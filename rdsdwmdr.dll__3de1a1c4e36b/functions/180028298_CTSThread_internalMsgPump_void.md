# CTSThread::internalMsgPump(void)

- ea: `0x180028298`
- end: `0x18002850d`
- name: `?internalMsgPump@CTSThread@@IEAAJXZ`
- size: `629`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180028514`

## callees

- `0x1800010f8`
- `0x18000160c`
- `0x18001a5f4`
- `0x18001d114`
- `0x180026480`
- `0x180028298`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18002839f`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180028478`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800284d4`: `Bailing from msg pump due to _fThreadReceivedQuit`
- `0x1800283b1`: `Bailing from msg pump since _fThreadReceivedQuit was set while running events`

## pseudocode

```c
__int64 __fastcall CTSThread::internalMsgPump(CTSThread *this)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // ebx
  unsigned int ActivityIdPrefix; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  __int64 v15; // [rsp+28h] [rbp-38h]
  const char *v16; // [rsp+50h] [rbp-10h] BYREF
  const char *v17; // [rsp+58h] [rbp-8h] BYREF
  int v18; // [rsp+90h] [rbp+30h] BYREF
  const char *v19; // [rsp+98h] [rbp+38h] BYREF
  int v20; // [rsp+A0h] [rbp+40h] BYREF
  const char *v21; // [rsp+A8h] [rbp+48h] BYREF

  v18 = 0;
  while ( 1 )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD, int, int, _DWORD, int *))(**((_QWORD **)this + 92)
                                                                                             + 48LL))(
           *((_QWORD *)this + 92),
           (char *)this + 688,
           1,
           *((_QWORD *)this + 88),
           -1,
           1,
           0,
           &v18);
    v7 = v2;
    if ( v2 == -2092629812 )
    {
      if ( (unsigned int)dword_180044008 > 5 )
      {
        v19 = "Bailing from msg pump due to _fThreadReceivedQuit";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v4,
          (__int64)&word_18003F6FE,
          v5,
          v6,
          (const unsigned __int16 **)&v19);
      }
      *((_DWORD *)this + 45) = 1;
      return 0;
    }
    if ( v2 < 0 )
      break;
    if ( !v18
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v4, v3, v5, v6);
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        &WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix);
    }
    v7 = CTSThread::RunAllQueueEvents(this, 0);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpX_GetActivityIdPrefix(v10, v9, v11, v12);
        LODWORD(v15) = v7;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          99,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          v13,
          (__int64)"Fail to run queue events",
          v15);
      }
      return (unsigned int)v7;
    }
    if ( *((_DWORD *)this + 45) )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v19) = 2006;
        v21 = "internalMsgPump";
        v20 = -2147467259;
        v16 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v17 = "Bailing from msg pump since _fThreadReceivedQuit was set while running events";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (__int64)&dword_18003F674,
          v11,
          v12,
          (const unsigned __int16 **)&v17,
          (__int64)&v20,
          (const unsigned __int16 **)&v16,
          (__int64)&v19,
          (const unsigned __int16 **)&v21);
      }
      return 0;
    }
  }
  if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v19) = 1986;
    v21 = "internalMsgPump";
    v20 = -2147467259;
    v17 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v16 = "Failed while waiting on enqueue condition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v4,
      (__int64)byte_18003F6B9,
      v5,
      v6,
      (const unsigned __int16 **)&v16,
      (__int64)&v20,
      (const unsigned __int16 **)&v17,
      (__int64)&v19,
      (const unsigned __int16 **)&v21);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028298  push    rbp
0x18002829a  push    rbx
0x18002829b  push    rsi
0x18002829c  push    rdi
0x18002829d  push    r12
0x18002829f  mov     rbp, rsp
0x1800282a2  sub     rsp, 60h
0x1800282a6  mov     rdi, rcx
0x1800282a9  mov     [rbp+arg_0], 0
0x1800282b0  lea     r12, WPP_GLOBAL_Control
0x1800282b7  mov     rcx, [rdi+2E0h]
0x1800282be  lea     rdx, [rbp+arg_0]
0x1800282c2  mov     r9, [rdi+2C0h]
0x1800282c9  mov     r8d, 1
0x1800282cf  mov     [rsp+60h+var_28], rdx
0x1800282d4  lea     rdx, [rdi+2B0h]
0x1800282db  mov     dword ptr [rsp+60h+var_30], 0
0x1800282e3  mov     rax, [rcx]
0x1800282e6  mov     dword ptr [rsp+60h+var_38], 1
0x1800282ee  mov     dword ptr [rsp+60h+var_40], 0FFFFFFFFh
0x1800282f6  mov     rax, [rax+30h]
0x1800282fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282ff  mov     ebx, eax
0x180028301  cmp     eax, 834500CCh
0x180028306  jz      loc_1800284C9
0x18002830c  test    eax, eax
0x18002830e  js      loc_180028450
0x180028314  cmp     [rbp+arg_0], 0
0x180028318  jnz     short loc_180028356
0x18002831a  mov     rax, cs:WPP_GLOBAL_Control
0x180028321  cmp     rax, r12
0x180028324  jz      short loc_180028356
0x180028326  test    byte ptr [rax+1Ch], 1
0x18002832a  jz      short loc_180028356
0x18002832c  cmp     byte ptr [rax+19h], 5
0x180028330  jb      short loc_180028356
0x180028332  call    RdpX_GetActivityIdPrefix
0x180028337  mov     rcx, cs:WPP_GLOBAL_Control
0x18002833e  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180028345  mov     edx, 62h ; 'b'
0x18002834a  mov     r9d, eax
0x18002834d  mov     rcx, [rcx+10h]
0x180028351  call    WPP_SF_D
0x180028356  xor     edx, edx; struct ITSEventFilter *
0x180028358  mov     rcx, rdi; this
0x18002835b  call    ?RunAllQueueEvents@CTSThread@@MEAAJPEAVITSEventFilter@@@Z; CTSThread::RunAllQueueEvents(ITSEventFilter *)
0x180028360  mov     ebx, eax
0x180028362  test    eax, eax
0x180028364  js      loc_1800283F3
0x18002836a  cmp     dword ptr [rdi+0B4h], 0
0x180028371  jz      loc_1800282B7
0x180028377  mov     eax, cs:dword_180044008
0x18002837d  cmp     eax, 2
0x180028380  jbe     loc_1800284FE
0x180028386  lea     rax, aInternalmsgpum; "internalMsgPump"
0x18002838d  mov     dword ptr [rbp+arg_8], 7D6h
0x180028394  mov     [rbp+arg_18], rax
0x180028398  lea     rdx, dword_18003F674
0x18002839f  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800283a6  mov     [rbp+arg_10], 80004005h
0x1800283ad  mov     [rbp+var_10], rax
0x1800283b1  lea     rax, aBailingFromMsg; "Bailing from msg pump since _fThreadRec"...
0x1800283b8  mov     [rbp+var_8], rax
0x1800283bc  lea     rax, [rbp+arg_18]
0x1800283c0  mov     [rsp+60h+var_20], rax
0x1800283c5  lea     rax, [rbp+arg_8]
0x1800283c9  mov     [rsp+60h+var_28], rax
0x1800283ce  lea     rax, [rbp+var_10]
0x1800283d2  mov     [rsp+60h+var_30], rax
0x1800283d7  lea     rax, [rbp+arg_10]
0x1800283db  mov     [rsp+60h+var_38], rax
0x1800283e0  lea     rax, [rbp+var_8]
0x1800283e4  mov     [rsp+60h+var_40], rax
0x1800283e9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800283ee  jmp     loc_1800284FE
0x1800283f3  mov     rax, cs:WPP_GLOBAL_Control
0x1800283fa  cmp     rax, r12
0x1800283fd  jz      loc_180028500
0x180028403  test    byte ptr [rax+1Ch], 8
0x180028407  jz      loc_180028500
0x18002840d  cmp     byte ptr [rax+19h], 2
0x180028411  jb      loc_180028500
0x180028417  call    RdpX_GetActivityIdPrefix
0x18002841c  lea     rcx, aFailToRunQueue; "Fail to run queue events"
0x180028423  mov     dword ptr [rsp+60h+var_38], ebx
0x180028427  mov     [rsp+60h+var_40], rcx
0x18002842c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180028433  mov     rcx, cs:WPP_GLOBAL_Control
0x18002843a  mov     edx, 63h ; 'c'
0x18002843f  mov     r9d, eax
0x180028442  mov     rcx, [rcx+10h]
0x180028446  call    WPP_SF_DsD
0x18002844b  jmp     loc_180028500
0x180028450  mov     eax, cs:dword_180044008
0x180028456  cmp     eax, 2
0x180028459  jbe     loc_180028500
0x18002845f  lea     rax, aInternalmsgpum; "internalMsgPump"
0x180028466  mov     dword ptr [rbp+arg_8], 7C2h
0x18002846d  mov     [rbp+arg_18], rax
0x180028471  lea     rdx, byte_18003F6B9
0x180028478  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002847f  mov     [rbp+arg_10], 80004005h
0x180028486  mov     [rbp+var_8], rax
0x18002848a  lea     rax, aFailedWhileWai; "Failed while waiting on enqueue conditi"...
0x180028491  mov     [rbp+var_10], rax
0x180028495  lea     rax, [rbp+arg_18]
0x180028499  mov     [rsp+60h+var_20], rax
0x18002849e  lea     rax, [rbp+arg_8]
0x1800284a2  mov     [rsp+60h+var_28], rax
0x1800284a7  lea     rax, [rbp+var_8]
0x1800284ab  mov     [rsp+60h+var_30], rax
0x1800284b0  lea     rax, [rbp+arg_10]
0x1800284b4  mov     [rsp+60h+var_38], rax
0x1800284b9  lea     rax, [rbp+var_10]
0x1800284bd  mov     [rsp+60h+var_40], rax
0x1800284c2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800284c7  jmp     short loc_180028500
0x1800284c9  mov     eax, cs:dword_180044008
0x1800284cf  cmp     eax, 5
0x1800284d2  jbe     short loc_1800284F4
0x1800284d4  lea     rax, aBailingFromMsg_0; "Bailing from msg pump due to _fThreadRe"...
0x1800284db  mov     [rbp+arg_8], rax
0x1800284df  lea     rdx, word_18003F6FE
0x1800284e6  lea     rax, [rbp+arg_8]
0x1800284ea  mov     [rsp+60h+var_40], rax
0x1800284ef  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800284f4  mov     dword ptr [rdi+0B4h], 1
0x1800284fe  xor     ebx, ebx
0x180028500  mov     eax, ebx
0x180028502  add     rsp, 60h
0x180028506  pop     r12
0x180028508  pop     rdi
0x180028509  pop     rsi
0x18002850a  pop     rbx
0x18002850b  pop     rbp
0x18002850c  retn
```
