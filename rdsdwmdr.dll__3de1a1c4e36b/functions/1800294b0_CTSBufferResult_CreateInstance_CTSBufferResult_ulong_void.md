# CTSBufferResult::CreateInstance(CTSBufferResult * *,ulong,void *)

- ea: `0x1800294b0`
- end: `0x18002967f`
- name: `?CreateInstance@CTSBufferResult@@SAJPEAPEAV1@KPEAX@Z`
- size: `463`
- prototype: `__int64 __fastcall(struct CTSBufferResult **, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029688`

## callees

- `0x18000160c`
- `0x1800032d4`
- `0x180005f9c`
- `0x18001d114`
- `0x180021830`
- `0x1800294b0`
- `0x180029978`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x1800295f2`: `CreateInstance`
- `0x18002960b`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`

## pseudocode

```c
__int64 __fastcall CTSBufferResult::CreateInstance(struct CTSBufferResult **a1, unsigned int a2, void *a3)
{
  CTSPooledUnknown *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  CTSPooledUnknown *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // r8
  __int64 v15; // r9
  int ActivityIdPrefix; // eax
  CTSPooledUnknown *v18; // [rsp+50h] [rbp-20h] BYREF
  const char *v19; // [rsp+58h] [rbp-18h] BYREF
  const char *v20; // [rsp+60h] [rbp-10h] BYREF
  const char *v21; // [rsp+68h] [rbp-8h] BYREF
  int v22; // [rsp+90h] [rbp+20h] BYREF
  int v23; // [rsp+A8h] [rbp+38h] BYREF

  v18 = 0;
  *a1 = 0;
  v6 = (CTSPooledUnknown *)operator new(0x70u);
  v10 = v6;
  if ( v6 )
  {
    CTSPooledUnknown::CTSPooledUnknown(v6, "CTSBufferResult", 0);
    *((_DWORD *)v10 + 22) = 0;
    *(_QWORD *)v10 = &CTSPooledUnknown::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v10 + 1) = &CTSBufferResult::`vftable'{for `CTSObject'};
    *((_QWORD *)v10 + 10) = &CTSBufferResult::`vftable';
    *((_QWORD *)v10 + 12) = 0;
    *((_DWORD *)v10 + 26) = 0;
    TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v18);
    v11 = *((_QWORD *)v10 + 4);
    v18 = v10;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v13 = CTSBufferResult::Initialize(v10, a2, a3);
    if ( v13 >= 0 )
    {
      *a1 = v10;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 4) + 8LL))(*((_QWORD *)v10 + 4));
      v13 = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v12, v14, v15);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)WPP_45c8207700f83d40fa4666bbba92ada0_Traceguids,
        ActivityIdPrefix,
        (__int64)"Failed to initialize buffer result!",
        v13);
    }
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v22 = 397;
      v19 = "CreateInstance";
      v23 = -2147467259;
      v20 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v21 = "OOM on CTSBufferResult!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (__int64)byte_18003FEF3,
        v8,
        v9,
        (const unsigned __int16 **)&v21,
        (__int64)&v23,
        (const unsigned __int16 **)&v20,
        (__int64)&v22,
        (const unsigned __int16 **)&v19);
    }
    v13 = -2147024882;
  }
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v18);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800294b0  mov     [rsp-18h+arg_8], rbx
0x1800294b5  mov     [rsp-18h+arg_10], rsi
0x1800294ba  push    rbp
0x1800294bb  push    rdi
0x1800294bc  push    r14
0x1800294be  mov     rbp, rsp
0x1800294c1  sub     rsp, 70h
0x1800294c5  mov     rdi, r8
0x1800294c8  mov     [rbp+var_20], 0
0x1800294d0  mov     r14d, edx
0x1800294d3  mov     rsi, rcx
0x1800294d6  mov     qword ptr [rcx], 0
0x1800294dd  mov     ecx, 70h ; 'p'; Size
0x1800294e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800294e7  mov     rbx, rax
0x1800294ea  test    rax, rax
0x1800294ed  jz      loc_1800295E7
0x1800294f3  xor     r8d, r8d; struct ITSObjectPool *
0x1800294f6  lea     rdx, aCtsbufferresul; "CTSBufferResult"
0x1800294fd  mov     rcx, rax; this
0x180029500  call    ??0CTSPooledUnknown@@QEAA@PEBDPEAVITSObjectPool@@@Z; CTSPooledUnknown::CTSPooledUnknown(char const *,ITSObjectPool *)
0x180029505  lea     rax, ??_7CTSPooledUnknown@@6BINonDelegatingUnknown@@@; const CTSPooledUnknown::`vftable'{for `INonDelegatingUnknown'}
0x18002950c  mov     dword ptr [rbx+58h], 0
0x180029513  mov     [rbx], rax
0x180029516  lea     rax, ??_7CTSBufferResult@@6BCTSObject@@@; const CTSBufferResult::`vftable'{for `CTSObject'}
0x18002951d  mov     [rbx+8], rax
0x180029521  lea     rax, ??_7CTSBufferResult@@6B@; const CTSBufferResult::`vftable'
0x180029528  mov     [rbx+50h], rax
0x18002952c  mov     qword ptr [rbx+60h], 0
0x180029534  mov     dword ptr [rbx+68h], 0
0x18002953b  lea     rcx, [rbp+var_20]
0x18002953f  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180029544  mov     rcx, [rbx+20h]
0x180029548  mov     [rbp+var_20], rbx
0x18002954c  mov     rax, [rcx]
0x18002954f  mov     rax, [rax+8]
0x180029553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029558  mov     r8, rdi; void *
0x18002955b  mov     edx, r14d; unsigned int
0x18002955e  mov     rcx, rbx; this
0x180029561  call    ?Initialize@CTSBufferResult@@IEAAJKPEAX@Z; CTSBufferResult::Initialize(ulong,void *)
0x180029566  mov     edi, eax
0x180029568  test    eax, eax
0x18002956a  jns     short loc_1800295D0
0x18002956c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029573  lea     rax, WPP_GLOBAL_Control
0x18002957a  cmp     rcx, rax
0x18002957d  jz      loc_18002965F
0x180029583  test    byte ptr [rcx+1Ch], 8
0x180029587  jz      loc_18002965F
0x18002958d  cmp     byte ptr [rcx+19h], 2
0x180029591  jb      loc_18002965F
0x180029597  call    RdpX_GetActivityIdPrefix
0x18002959c  lea     rcx, aFailedToInitia_2; "Failed to initialize buffer result!"
0x1800295a3  mov     dword ptr [rsp+70h+var_48], edi
0x1800295a7  mov     [rsp+70h+var_50], rcx
0x1800295ac  lea     r8, WPP_45c8207700f83d40fa4666bbba92ada0_Traceguids
0x1800295b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295ba  mov     edx, 1Ch
0x1800295bf  mov     r9d, eax
0x1800295c2  mov     rcx, [rcx+10h]
0x1800295c6  call    WPP_SF_DsD
0x1800295cb  jmp     loc_18002965F
0x1800295d0  mov     [rsi], rbx
0x1800295d3  mov     rcx, [rbx+20h]
0x1800295d7  mov     rax, [rcx]
0x1800295da  mov     rax, [rax+8]
0x1800295de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295e3  xor     edi, edi
0x1800295e5  jmp     short loc_18002965F
0x1800295e7  mov     eax, cs:dword_180044008
0x1800295ed  cmp     eax, 2
0x1800295f0  jbe     short loc_18002965A
0x1800295f2  lea     rax, aCreateinstance_1; "CreateInstance"
0x1800295f9  mov     [rbp+arg_0], 18Dh
0x180029600  mov     [rbp+var_18], rax
0x180029604  lea     rdx, byte_18003FEF3
0x18002960b  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180029612  mov     [rbp+arg_18], 80004005h
0x180029619  mov     [rbp+var_10], rax
0x18002961d  lea     rax, aOomOnCtsbuffer; "OOM on CTSBufferResult!"
0x180029624  mov     [rbp+var_8], rax
0x180029628  lea     rax, [rbp+var_18]
0x18002962c  mov     [rsp+70h+var_30], rax
0x180029631  lea     rax, [rbp+arg_0]
0x180029635  mov     [rsp+70h+var_38], rax
0x18002963a  lea     rax, [rbp+var_10]
0x18002963e  mov     [rsp+70h+var_40], rax
0x180029643  lea     rax, [rbp+arg_18]
0x180029647  mov     [rsp+70h+var_48], rax
0x18002964c  lea     rax, [rbp+var_8]
0x180029650  mov     [rsp+70h+var_50], rax
0x180029655  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002965a  mov     edi, 8007000Eh
0x18002965f  lea     rcx, [rbp+var_20]
0x180029663  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180029668  lea     r11, [rsp+70h+var_s0]
0x18002966d  mov     eax, edi
0x18002966f  mov     rbx, [r11+28h]
0x180029673  mov     rsi, [r11+30h]
0x180029677  mov     rsp, r11
0x18002967a  pop     r14
0x18002967c  pop     rdi
0x18002967d  pop     rbp
0x18002967e  retn
```
