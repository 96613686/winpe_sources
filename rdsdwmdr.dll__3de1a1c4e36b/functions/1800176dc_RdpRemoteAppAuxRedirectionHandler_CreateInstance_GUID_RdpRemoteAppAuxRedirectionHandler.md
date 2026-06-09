# RdpRemoteAppAuxRedirectionHandler::CreateInstance(_GUID,RdpRemoteAppAuxRedirectionHandler * *)

- ea: `0x1800176dc`
- end: `0x18001799c`
- name: `?CreateInstance@RdpRemoteAppAuxRedirectionHandler@@SAJU_GUID@@PEAPEAV1@@Z`
- size: `704`
- prototype: `__int64 __fastcall(struct _GUID *, struct RdpRemoteAppAuxRedirectionHandler **, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180012238`

## callees

- `0x18000160c`
- `0x180001724`
- `0x1800032d4`
- `0x180005f6c`
- `0x180012924`
- `0x1800176dc`
- `0x180017c98`
- `0x18002c010`

## string_xrefs

- `0x180017719`: `CreateInstance`
- `0x180017880`: `CreateInstance`
- `0x18001791f`: `CreateInstance`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::CreateInstance(
        struct _GUID *a1,
        struct RdpRemoteAppAuxRedirectionHandler **a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // edi
  char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  RdpRemoteAppAuxRedirectionHandler *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  const char *v14; // [rsp+50h] [rbp-30h] BYREF
  const char *v15; // [rsp+58h] [rbp-28h] BYREF
  const unsigned __int16 *v16[2]; // [rsp+60h] [rbp-20h] BYREF
  struct _GUID v17; // [rsp+70h] [rbp-10h] BYREF
  int v18; // [rsp+A8h] [rbp+28h] BYREF
  int v19; // [rsp+B0h] [rbp+30h] BYREF
  RdpRemoteAppAuxRedirectionHandler *v20; // [rsp+B8h] [rbp+38h] BYREF

  v20 = 0;
  if ( a2 )
  {
    v7 = (char *)operator new(0x78u);
    v10 = (RdpRemoteAppAuxRedirectionHandler *)v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 6) = -607474739;
      *((_DWORD *)v7 + 7) = 1;
      *((_QWORD *)v7 + 2) = "RdpRemoteAppAuxRedirectionHandler";
      *((_QWORD *)v7 + 4) = v7;
      *(_QWORD *)v7 = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v7 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
      *((_DWORD *)v7 + 10) = 0;
      *(_QWORD *)v7 = &RdpRemoteAppAuxRedirectionHandler::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v7 + 1) = &RdpRemoteAppAuxRedirectionHandler::`vftable'{for `CTSObject'};
      *((_QWORD *)v7 + 6) = &RdpRemoteAppAuxRedirectionHandler::`vftable'{for `IWTSVirtualChannelCallback'};
      *((_QWORD *)v7 + 7) = &RdpRemoteAppAuxRedirectionHandler::`vftable'{for `IRdsDWMAuxRedirection'};
      *((_DWORD *)v7 + 18) = 0;
      *((_QWORD *)v7 + 8) = 0;
      *((_QWORD *)v7 + 10) = 0;
      *((_QWORD *)v7 + 11) = 0;
      *((_DWORD *)v7 + 24) = 0;
      *(_OWORD *)(v7 + 104) = 0;
      TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v20);
      v20 = v10;
      TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef(&v20);
      v17 = *a1;
      v6 = RdpRemoteAppAuxRedirectionHandler::Initialize(v10, &v17);
      if ( v6 >= 0 )
      {
        *a2 = v10;
        (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v10 + 6) + 8LL))((_QWORD *)v10 + 6);
        v6 = 0;
      }
      else if ( (unsigned int)dword_180044008 > 2 )
      {
        v18 = 61;
        v16[0] = (const unsigned __int16 *)"Initialize failed";
        v19 = v6;
        v15 = "CreateInstance";
        v14 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        *(_QWORD *)&v17.Data1 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)dword_180044008,
          (__int64)word_18003E5C2,
          v11,
          v12,
          (const unsigned __int16 **)&v17,
          (__int64)&v19,
          (const unsigned __int16 **)&v14,
          (__int64)&v18,
          (const unsigned __int16 **)&v15,
          v16);
      }
    }
    else
    {
      v6 = -2147467261;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v18 = 58;
        *(_QWORD *)&v17.Data1 = "RdpRemoteAppAuxRedirectionHandler";
        v19 = -2147467261;
        v16[0] = (const unsigned __int16 *)"CreateInstance";
        v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v14 = "Unexpected NULL object";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          2147500035LL,
          (__int64)&dword_18003E624,
          v8,
          v9,
          (const unsigned __int16 **)&v14,
          (__int64)&v19,
          (const unsigned __int16 **)&v15,
          (__int64)&v18,
          v16,
          (const unsigned __int16 **)&v17);
      }
    }
  }
  else
  {
    v6 = -2147467261;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v18 = 55;
      v14 = "CreateInstance";
      v19 = -2147467261;
      v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
      v16[0] = (const unsigned __int16 *)"Unexpected NULL object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        2147500035LL,
        (__int64)&dword_18003E684,
        a3,
        a4,
        v16,
        (__int64)&v19,
        (const unsigned __int16 **)&v15,
        (__int64)&v18,
        (const unsigned __int16 **)&v14);
    }
  }
  TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800176dc  mov     r11, rsp
0x1800176df  mov     [r11+8], rbx
0x1800176e3  push    rbp
0x1800176e4  push    rsi
0x1800176e5  push    rdi
0x1800176e6  mov     rbp, rsp
0x1800176e9  sub     rsp, 80h
0x1800176f0  mov     [rbp+arg_18], 0
0x1800176f8  mov     rsi, rdx
0x1800176fb  mov     rdi, rcx
0x1800176fe  test    rdx, rdx
0x180017701  jnz     short loc_18001777D
0x180017703  mov     eax, cs:dword_180044008
0x180017709  mov     ecx, 80004003h
0x18001770e  mov     edi, ecx
0x180017710  cmp     eax, 2
0x180017713  jbe     loc_18001797E
0x180017719  lea     rax, aCreateinstance_1; "CreateInstance"
0x180017720  mov     [rbp+arg_8], 37h ; '7'
0x180017727  mov     [rbp+var_30], rax
0x18001772b  lea     rdx, dword_18003E684
0x180017732  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180017739  mov     [rbp+arg_10], ecx
0x18001773c  mov     [rbp+var_28], rax
0x180017740  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180017747  mov     [rbp+var_20], rax
0x18001774b  lea     rax, [rbp+var_30]
0x18001774f  mov     [r11-58h], rax
0x180017753  lea     rax, [rbp+arg_8]
0x180017757  mov     [r11-60h], rax
0x18001775b  lea     rax, [rbp+var_28]
0x18001775f  mov     [r11-68h], rax
0x180017763  lea     rax, [rbp+arg_10]
0x180017767  mov     [r11-70h], rax
0x18001776b  lea     rax, [rbp+var_20]
0x18001776f  mov     [r11-78h], rax
0x180017773  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180017778  jmp     loc_18001797E
0x18001777d  mov     ecx, 78h ; 'x'; Size
0x180017782  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017787  mov     rbx, rax
0x18001778a  test    rax, rax
0x18001778d  jz      loc_1800178F4
0x180017793  mov     dword ptr [rax+18h], 0DBCAABCDh
0x18001779a  lea     rcx, [rbp+arg_18]
0x18001779e  mov     dword ptr [rbx+1Ch], 1
0x1800177a5  lea     rax, aRdpremoteappau_1; "RdpRemoteAppAuxRedirectionHandler"
0x1800177ac  mov     [rbx+10h], rax
0x1800177b0  xorps   xmm0, xmm0
0x1800177b3  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x1800177ba  mov     [rbx+20h], rbx
0x1800177be  mov     [rbx], rax
0x1800177c1  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x1800177c8  mov     [rbx+8], rax
0x1800177cc  lea     rax, ??_7RdpRemoteAppAuxRedirectionHandler@@6BINonDelegatingUnknown@@@; const RdpRemoteAppAuxRedirectionHandler::`vftable'{for `INonDelegatingUnknown'}
0x1800177d3  mov     dword ptr [rbx+28h], 0
0x1800177da  mov     [rbx], rax
0x1800177dd  lea     rax, ??_7RdpRemoteAppAuxRedirectionHandler@@6BCTSObject@@@; const RdpRemoteAppAuxRedirectionHandler::`vftable'{for `CTSObject'}
0x1800177e4  mov     [rbx+8], rax
0x1800177e8  lea     rax, ??_7RdpRemoteAppAuxRedirectionHandler@@6BIWTSVirtualChannelCallback@@@; const RdpRemoteAppAuxRedirectionHandler::`vftable'{for `IWTSVirtualChannelCallback'}
0x1800177ef  mov     [rbx+30h], rax
0x1800177f3  lea     rax, ??_7RdpRemoteAppAuxRedirectionHandler@@6BIRdsDWMAuxRedirection@@@; const RdpRemoteAppAuxRedirectionHandler::`vftable'{for `IRdsDWMAuxRedirection'}
0x1800177fa  mov     [rbx+38h], rax
0x1800177fe  mov     dword ptr [rbx+48h], 0
0x180017805  mov     qword ptr [rbx+40h], 0
0x18001780d  mov     qword ptr [rbx+50h], 0
0x180017815  mov     qword ptr [rbx+58h], 0
0x18001781d  mov     dword ptr [rbx+60h], 0
0x180017824  movups  xmmword ptr [rbx+68h], xmm0
0x180017828  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x18001782d  lea     rcx, [rbp+arg_18]
0x180017831  mov     [rbp+arg_18], rbx
0x180017835  call    ?SafeAddRef@?$TCntPtr@VRdpRemoteAppAuxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef(void)
0x18001783a  movups  xmm0, xmmword ptr [rdi]
0x18001783d  lea     rdx, [rbp+var_10]; struct _GUID
0x180017841  mov     rcx, rbx; this
0x180017844  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180017849  call    ?Initialize@RdpRemoteAppAuxRedirectionHandler@@IEAAJU_GUID@@@Z; RdpRemoteAppAuxRedirectionHandler::Initialize(_GUID)
0x18001784e  mov     edi, eax
0x180017850  test    eax, eax
0x180017852  jns     loc_1800178DA
0x180017858  mov     ecx, cs:dword_180044008
0x18001785e  cmp     ecx, 2
0x180017861  jbe     loc_18001797E
0x180017867  lea     rax, aInitializeFail; "Initialize failed"
0x18001786e  mov     [rbp+arg_8], 3Dh ; '='
0x180017875  mov     [rbp+var_20], rax
0x180017879  lea     rdx, word_18003E5C2
0x180017880  lea     rax, aCreateinstance_1; "CreateInstance"
0x180017887  mov     [rbp+arg_10], edi
0x18001788a  mov     [rbp+var_28], rax
0x18001788e  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180017895  mov     [rbp+var_30], rax
0x180017899  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800178a0  mov     qword ptr [rbp+var_10.Data1], rax
0x1800178a4  lea     rax, [rbp+var_20]
0x1800178a8  mov     [rsp+80h+var_38], rax
0x1800178ad  lea     rax, [rbp+var_28]
0x1800178b1  mov     [rsp+80h+var_40], rax
0x1800178b6  lea     rax, [rbp+arg_8]
0x1800178ba  mov     [rsp+80h+var_48], rax
0x1800178bf  lea     rax, [rbp+var_30]
0x1800178c3  mov     [rsp+80h+var_50], rax
0x1800178c8  lea     rax, [rbp+arg_10]
0x1800178cc  mov     [rsp+80h+var_58], rax
0x1800178d1  lea     rax, [rbp+var_10]
0x1800178d5  jmp     loc_180017974
0x1800178da  lea     rcx, [rbx+30h]
0x1800178de  mov     [rsi], rbx
0x1800178e1  mov     rax, [rcx]
0x1800178e4  mov     rax, [rax+8]
0x1800178e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178ed  xor     edi, edi
0x1800178ef  jmp     loc_18001797E
0x1800178f4  mov     eax, cs:dword_180044008
0x1800178fa  mov     ecx, 80004003h
0x1800178ff  mov     edi, ecx
0x180017901  cmp     eax, 2
0x180017904  jbe     short loc_18001797E
0x180017906  lea     rax, aRdpremoteappau_1; "RdpRemoteAppAuxRedirectionHandler"
0x18001790d  mov     [rbp+arg_8], 3Ah ; ':'
0x180017914  mov     qword ptr [rbp+var_10.Data1], rax
0x180017918  lea     rdx, dword_18003E624
0x18001791f  lea     rax, aCreateinstance_1; "CreateInstance"
0x180017926  mov     [rbp+arg_10], ecx
0x180017929  mov     [rbp+var_20], rax
0x18001792d  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180017934  mov     [rbp+var_28], rax
0x180017938  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x18001793f  mov     [rbp+var_30], rax
0x180017943  lea     rax, [rbp+var_10]
0x180017947  mov     [rsp+80h+var_38], rax
0x18001794c  lea     rax, [rbp+var_20]
0x180017950  mov     [rsp+80h+var_40], rax
0x180017955  lea     rax, [rbp+arg_8]
0x180017959  mov     [rsp+80h+var_48], rax
0x18001795e  lea     rax, [rbp+var_28]
0x180017962  mov     [rsp+80h+var_50], rax
0x180017967  lea     rax, [rbp+arg_10]
0x18001796b  mov     [rsp+80h+var_58], rax
0x180017970  lea     rax, [rbp+var_30]
0x180017974  mov     [rsp+80h+var_60], rax
0x180017979  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001797e  lea     rcx, [rbp+arg_18]
0x180017982  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x180017987  mov     rbx, [rsp+80h+arg_0]
0x18001798f  mov     eax, edi
0x180017991  add     rsp, 80h
0x180017998  pop     rdi
0x180017999  pop     rsi
0x18001799a  pop     rbp
0x18001799b  retn
```
