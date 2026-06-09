# RdpRemoteAppGfxRedirectionHandler::CreateInstance(_GUID,RdpRemoteAppGfxRedirectionHandler * *)

- ea: `0x180013444`
- end: `0x180013684`
- name: `?CreateInstance@RdpRemoteAppGfxRedirectionHandler@@SAJU_GUID@@PEAPEAV1@@Z`
- size: `576`
- prototype: `__int64 __fastcall(struct _GUID *, struct RdpRemoteAppGfxRedirectionHandler **, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180012238`

## callees

- `0x18000160c`
- `0x180001724`
- `0x1800032d4`
- `0x180005f6c`
- `0x180012924`
- `0x180012ce8`
- `0x180013444`
- `0x1800141d0`
- `0x18002c010`

## string_xrefs

- `0x180013481`: `CreateInstance`
- `0x180013568`: `CreateInstance`
- `0x180013607`: `CreateInstance`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::CreateInstance(
        struct _GUID *a1,
        struct RdpRemoteAppGfxRedirectionHandler **a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // ebx
  RdpRemoteAppGfxRedirectionHandler *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  RdpRemoteAppGfxRedirectionHandler *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  const char *v14; // [rsp+50h] [rbp-30h] BYREF
  const char *v15; // [rsp+58h] [rbp-28h] BYREF
  const unsigned __int16 *v16[2]; // [rsp+60h] [rbp-20h] BYREF
  struct _GUID v17; // [rsp+70h] [rbp-10h] BYREF
  int v18; // [rsp+A8h] [rbp+28h] BYREF
  int v19; // [rsp+B0h] [rbp+30h] BYREF
  RdpRemoteAppGfxRedirectionHandler *v20; // [rsp+B8h] [rbp+38h] BYREF

  v20 = 0;
  if ( a2 )
  {
    v7 = (RdpRemoteAppGfxRedirectionHandler *)operator new(0x138u);
    if ( v7 && (v10 = RdpRemoteAppGfxRedirectionHandler::RdpRemoteAppGfxRedirectionHandler(v7)) != 0 )
    {
      TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v20);
      v20 = v10;
      TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef(&v20);
      v17 = *a1;
      v6 = RdpRemoteAppGfxRedirectionHandler::Initialize(v10, &v17);
      if ( v6 >= 0 )
      {
        *a2 = v10;
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v10 + 6) + 8LL))((__int64)v10 + 48);
        v6 = 0;
      }
      else if ( (unsigned int)dword_180044008 > 2 )
      {
        v18 = 172;
        v16[0] = (const unsigned __int16 *)"Initialize failed";
        v19 = v6;
        v15 = "CreateInstance";
        v14 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        *(_QWORD *)&v17.Data1 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)dword_180044008,
          (__int64)&word_18003D6C6,
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
        v18 = 169;
        *(_QWORD *)&v17.Data1 = "RdpRemoteAppGfxRedirectionHandler";
        v19 = -2147467261;
        v16[0] = (const unsigned __int16 *)"CreateInstance";
        v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v14 = "Unexpected NULL object";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          2147500035LL,
          (__int64)&unk_18003D728,
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
      v18 = 166;
      v14 = "CreateInstance";
      v19 = -2147467261;
      v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v16[0] = (const unsigned __int16 *)"Unexpected NULL object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        2147500035LL,
        (__int64)&unk_18003D788,
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
0x180013444  mov     r11, rsp
0x180013447  mov     [r11+8], rbx
0x18001344b  push    rbp
0x18001344c  push    rsi
0x18001344d  push    rdi
0x18001344e  mov     rbp, rsp
0x180013451  sub     rsp, 80h
0x180013458  mov     [rbp+arg_18], 0
0x180013460  mov     rsi, rdx
0x180013463  mov     rbx, rcx
0x180013466  test    rdx, rdx
0x180013469  jnz     short loc_1800134E5
0x18001346b  mov     eax, cs:dword_180044008
0x180013471  mov     ecx, 80004003h
0x180013476  mov     ebx, ecx
0x180013478  cmp     eax, 2
0x18001347b  jbe     loc_180013666
0x180013481  lea     rax, aCreateinstance_1; "CreateInstance"
0x180013488  mov     [rbp+arg_8], 0A6h
0x18001348f  mov     [rbp+var_30], rax
0x180013493  lea     rdx, unk_18003D788
0x18001349a  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800134a1  mov     [rbp+arg_10], ecx
0x1800134a4  mov     [rbp+var_28], rax
0x1800134a8  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x1800134af  mov     [rbp+var_20], rax
0x1800134b3  lea     rax, [rbp+var_30]
0x1800134b7  mov     [r11-58h], rax
0x1800134bb  lea     rax, [rbp+arg_8]
0x1800134bf  mov     [r11-60h], rax
0x1800134c3  lea     rax, [rbp+var_28]
0x1800134c7  mov     [r11-68h], rax
0x1800134cb  lea     rax, [rbp+arg_10]
0x1800134cf  mov     [r11-70h], rax
0x1800134d3  lea     rax, [rbp+var_20]
0x1800134d7  mov     [r11-78h], rax
0x1800134db  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800134e0  jmp     loc_180013666
0x1800134e5  mov     ecx, 138h; Size
0x1800134ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800134ef  test    rax, rax
0x1800134f2  jz      loc_1800135DC
0x1800134f8  mov     rcx, rax; this
0x1800134fb  call    ??0RdpRemoteAppGfxRedirectionHandler@@IEAA@XZ; RdpRemoteAppGfxRedirectionHandler::RdpRemoteAppGfxRedirectionHandler(void)
0x180013500  mov     rdi, rax
0x180013503  test    rax, rax
0x180013506  jz      loc_1800135DC
0x18001350c  lea     rcx, [rbp+arg_18]
0x180013510  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x180013515  lea     rcx, [rbp+arg_18]
0x180013519  mov     [rbp+arg_18], rdi
0x18001351d  call    ?SafeAddRef@?$TCntPtr@VRdpRemoteAppAuxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppAuxRedirectionHandler>::SafeAddRef(void)
0x180013522  movups  xmm0, xmmword ptr [rbx]
0x180013525  lea     rdx, [rbp+var_10]; struct _GUID
0x180013529  mov     rcx, rdi; this
0x18001352c  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180013531  call    ?Initialize@RdpRemoteAppGfxRedirectionHandler@@IEAAJU_GUID@@@Z; RdpRemoteAppGfxRedirectionHandler::Initialize(_GUID)
0x180013536  mov     ebx, eax
0x180013538  test    eax, eax
0x18001353a  jns     loc_1800135C2
0x180013540  mov     ecx, cs:dword_180044008
0x180013546  cmp     ecx, 2
0x180013549  jbe     loc_180013666
0x18001354f  lea     rax, aInitializeFail; "Initialize failed"
0x180013556  mov     [rbp+arg_8], 0ACh
0x18001355d  mov     [rbp+var_20], rax
0x180013561  lea     rdx, word_18003D6C6
0x180013568  lea     rax, aCreateinstance_1; "CreateInstance"
0x18001356f  mov     [rbp+arg_10], ebx
0x180013572  mov     [rbp+var_28], rax
0x180013576  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001357d  mov     [rbp+var_30], rax
0x180013581  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180013588  mov     qword ptr [rbp+var_10.Data1], rax
0x18001358c  lea     rax, [rbp+var_20]
0x180013590  mov     [rsp+80h+var_38], rax
0x180013595  lea     rax, [rbp+var_28]
0x180013599  mov     [rsp+80h+var_40], rax
0x18001359e  lea     rax, [rbp+arg_8]
0x1800135a2  mov     [rsp+80h+var_48], rax
0x1800135a7  lea     rax, [rbp+var_30]
0x1800135ab  mov     [rsp+80h+var_50], rax
0x1800135b0  lea     rax, [rbp+arg_10]
0x1800135b4  mov     [rsp+80h+var_58], rax
0x1800135b9  lea     rax, [rbp+var_10]
0x1800135bd  jmp     loc_18001365C
0x1800135c2  lea     rcx, [rdi+30h]
0x1800135c6  mov     [rsi], rdi
0x1800135c9  mov     rax, [rcx]
0x1800135cc  mov     rax, [rax+8]
0x1800135d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135d5  xor     ebx, ebx
0x1800135d7  jmp     loc_180013666
0x1800135dc  mov     eax, cs:dword_180044008
0x1800135e2  mov     ecx, 80004003h
0x1800135e7  mov     ebx, ecx
0x1800135e9  cmp     eax, 2
0x1800135ec  jbe     short loc_180013666
0x1800135ee  lea     rax, aRdpremoteappgf; "RdpRemoteAppGfxRedirectionHandler"
0x1800135f5  mov     [rbp+arg_8], 0A9h
0x1800135fc  mov     qword ptr [rbp+var_10.Data1], rax
0x180013600  lea     rdx, unk_18003D728
0x180013607  lea     rax, aCreateinstance_1; "CreateInstance"
0x18001360e  mov     [rbp+arg_10], ecx
0x180013611  mov     [rbp+var_20], rax
0x180013615  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001361c  mov     [rbp+var_28], rax
0x180013620  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180013627  mov     [rbp+var_30], rax
0x18001362b  lea     rax, [rbp+var_10]
0x18001362f  mov     [rsp+80h+var_38], rax
0x180013634  lea     rax, [rbp+var_20]
0x180013638  mov     [rsp+80h+var_40], rax
0x18001363d  lea     rax, [rbp+arg_8]
0x180013641  mov     [rsp+80h+var_48], rax
0x180013646  lea     rax, [rbp+var_28]
0x18001364a  mov     [rsp+80h+var_50], rax
0x18001364f  lea     rax, [rbp+arg_10]
0x180013653  mov     [rsp+80h+var_58], rax
0x180013658  lea     rax, [rbp+var_30]
0x18001365c  mov     [rsp+80h+var_60], rax
0x180013661  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180013666  lea     rcx, [rbp+arg_18]
0x18001366a  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x18001366f  mov     eax, ebx
0x180013671  mov     rbx, [rsp+80h+arg_0]
0x180013679  add     rsp, 80h
0x180013680  pop     rdi
0x180013681  pop     rsi
0x180013682  pop     rbp
0x180013683  retn
```
