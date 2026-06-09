# CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)

- ea: `0x180023fec`
- end: `0x1800241e0`
- name: `?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z`
- size: `500`
- prototype: `__int64 __fastcall(__int64, struct CTS_TLS_ThreadDescriptor **, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800234e0`
- `0x180027150`

## callees

- `0x18000160c`
- `0x1800032d4`
- `0x180005f9c`
- `0x18001d114`
- `0x180022860`
- `0x180023fec`
- `0x180025820`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18002401a`: `CreateInstance`
- `0x180024158`: `CreateInstance`
- `0x180024033`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180024171`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180024045`: `Thread descriptor creation NULL pointer passed`
- `0x180024183`: `OOM on thread descriptor`
- `0x18002410c`: `spThreadDescriptor init failed`

## pseudocode

```c
__int64 __fastcall CTS_TLS_ThreadDescriptor::CreateInstance(
        __int64 a1,
        struct CTS_TLS_ThreadDescriptor **a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // ebx
  int v6; // ebx
  CTS_TLS_ThreadDescriptor *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  CTS_TLS_ThreadDescriptor *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int ActivityIdPrefix; // eax
  const char *v18; // [rsp+50h] [rbp-20h] BYREF
  const char *v19; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v20[2]; // [rsp+60h] [rbp-10h] BYREF
  int v21; // [rsp+98h] [rbp+28h] BYREF
  int v22; // [rsp+A0h] [rbp+30h] BYREF
  CTS_TLS_ThreadDescriptor *v23; // [rsp+A8h] [rbp+38h] BYREF

  v23 = 0;
  v5 = a1;
  if ( a2 )
  {
    v7 = (CTS_TLS_ThreadDescriptor *)operator new(0x200u);
    if ( v7 && (v11 = CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(v7, v5)) != 0 )
    {
      TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v23);
      v12 = *((_QWORD *)v11 + 4);
      v23 = v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      v6 = CTS_TLS_ThreadDescriptor::Initialize((CTS_TLS_ThreadDescriptor *)((char *)v11 + 8));
      if ( v6 >= 0 )
      {
        v23 = 0;
        *a2 = v11;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v13, v14, v15);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          155,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"spThreadDescriptor init failed",
          v6);
      }
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v21 = 3340;
        v20[0] = (const unsigned __int16 *)"CreateInstance";
        v22 = -2147467259;
        v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v18 = "OOM on thread descriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v8,
          (__int64)byte_18003F315,
          v9,
          v10,
          (const unsigned __int16 **)&v18,
          (__int64)&v22,
          (const unsigned __int16 **)&v19,
          (__int64)&v21,
          v20);
      }
      v6 = -2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v21 = 3333;
      v18 = "CreateInstance";
      v22 = -2147467259;
      v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v20[0] = (const unsigned __int16 *)"Thread descriptor creation NULL pointer passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (__int64)word_18003F35A,
        a3,
        a4,
        v20,
        (__int64)&v22,
        (const unsigned __int16 **)&v19,
        (__int64)&v21,
        (const unsigned __int16 **)&v18);
    }
    v6 = -2147024809;
  }
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v23);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023fec  mov     r11, rsp
0x180023fef  mov     [r11+8], rbx
0x180023ff3  push    rbp
0x180023ff4  push    rsi
0x180023ff5  push    rdi
0x180023ff6  mov     rbp, rsp
0x180023ff9  sub     rsp, 70h
0x180023ffd  mov     rsi, rdx
0x180024000  mov     [rbp+arg_18], 0
0x180024008  mov     ebx, ecx
0x18002400a  test    rdx, rdx
0x18002400d  jnz     short loc_180024087
0x18002400f  mov     eax, cs:dword_180044008
0x180024015  cmp     eax, 2
0x180024018  jbe     short loc_18002407D
0x18002401a  lea     rax, aCreateinstance_1; "CreateInstance"
0x180024021  mov     [rbp+arg_8], 0D05h
0x180024028  mov     [rbp+var_20], rax
0x18002402c  lea     rdx, word_18003F35A
0x180024033  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002403a  mov     [rbp+arg_10], 80004005h
0x180024041  mov     [rbp+var_18], rax
0x180024045  lea     rax, aThreadDescript; "Thread descriptor creation NULL pointer"...
0x18002404c  mov     [rbp+var_10], rax
0x180024050  lea     rax, [rbp+var_20]
0x180024054  mov     [r11-48h], rax
0x180024058  lea     rax, [rbp+arg_8]
0x18002405c  mov     [r11-50h], rax
0x180024060  lea     rax, [rbp+var_18]
0x180024064  mov     [r11-58h], rax
0x180024068  lea     rax, [rbp+arg_10]
0x18002406c  mov     [r11-60h], rax
0x180024070  lea     rax, [rbp+var_10]
0x180024074  mov     [r11-68h], rax
0x180024078  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002407d  mov     ebx, 80070057h
0x180024082  jmp     loc_1800241C5
0x180024087  mov     ecx, 200h; Size
0x18002408c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024091  test    rax, rax
0x180024094  jz      loc_18002414D
0x18002409a  mov     edx, ebx; int
0x18002409c  mov     rcx, rax; this
0x18002409f  call    ??0CTS_TLS_ThreadDescriptor@@AEAA@H@Z; CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(int)
0x1800240a4  mov     rdi, rax
0x1800240a7  test    rax, rax
0x1800240aa  jz      loc_18002414D
0x1800240b0  lea     rcx, [rbp+arg_18]
0x1800240b4  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x1800240b9  mov     rcx, [rdi+20h]
0x1800240bd  mov     [rbp+arg_18], rdi
0x1800240c1  mov     rax, [rcx]
0x1800240c4  mov     rax, [rax+8]
0x1800240c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240cd  lea     rcx, [rdi+8]; this
0x1800240d1  call    ?Initialize@CTS_TLS_ThreadDescriptor@@EEAAJXZ; CTS_TLS_ThreadDescriptor::Initialize(void)
0x1800240d6  mov     ebx, eax
0x1800240d8  test    eax, eax
0x1800240da  jns     short loc_180024140
0x1800240dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240e3  lea     rax, WPP_GLOBAL_Control
0x1800240ea  cmp     rcx, rax
0x1800240ed  jz      loc_1800241C5
0x1800240f3  test    byte ptr [rcx+1Ch], 8
0x1800240f7  jz      loc_1800241C5
0x1800240fd  cmp     byte ptr [rcx+19h], 2
0x180024101  jb      loc_1800241C5
0x180024107  call    RdpX_GetActivityIdPrefix
0x18002410c  lea     rcx, aSpthreaddescri; "spThreadDescriptor init failed"
0x180024113  mov     dword ptr [rsp+70h+var_48], ebx
0x180024117  mov     [rsp+70h+var_50], rcx
0x18002411c  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180024123  mov     rcx, cs:WPP_GLOBAL_Control
0x18002412a  mov     edx, 9Bh
0x18002412f  mov     r9d, eax
0x180024132  mov     rcx, [rcx+10h]
0x180024136  call    WPP_SF_DsD
0x18002413b  jmp     loc_1800241C5
0x180024140  mov     [rbp+arg_18], 0
0x180024148  mov     [rsi], rdi
0x18002414b  jmp     short loc_1800241C5
0x18002414d  mov     eax, cs:dword_180044008
0x180024153  cmp     eax, 2
0x180024156  jbe     short loc_1800241C0
0x180024158  lea     rax, aCreateinstance_1; "CreateInstance"
0x18002415f  mov     [rbp+arg_8], 0D0Ch
0x180024166  mov     [rbp+var_10], rax
0x18002416a  lea     rdx, byte_18003F315
0x180024171  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180024178  mov     [rbp+arg_10], 80004005h
0x18002417f  mov     [rbp+var_18], rax
0x180024183  lea     rax, aOomOnThreadDes; "OOM on thread descriptor"
0x18002418a  mov     [rbp+var_20], rax
0x18002418e  lea     rax, [rbp+var_10]
0x180024192  mov     [rsp+70h+var_30], rax
0x180024197  lea     rax, [rbp+arg_8]
0x18002419b  mov     [rsp+70h+var_38], rax
0x1800241a0  lea     rax, [rbp+var_18]
0x1800241a4  mov     [rsp+70h+var_40], rax
0x1800241a9  lea     rax, [rbp+arg_10]
0x1800241ad  mov     [rsp+70h+var_48], rax
0x1800241b2  lea     rax, [rbp+var_20]
0x1800241b6  mov     [rsp+70h+var_50], rax
0x1800241bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800241c0  mov     ebx, 8007000Eh
0x1800241c5  lea     rcx, [rbp+arg_18]
0x1800241c9  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x1800241ce  mov     eax, ebx
0x1800241d0  mov     rbx, [rsp+70h+arg_0]
0x1800241d8  add     rsp, 70h
0x1800241dc  pop     rdi
0x1800241dd  pop     rsi
0x1800241de  pop     rbp
0x1800241df  retn
```
