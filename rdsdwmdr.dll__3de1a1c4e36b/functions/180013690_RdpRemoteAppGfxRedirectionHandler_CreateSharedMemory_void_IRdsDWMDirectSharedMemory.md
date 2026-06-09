# RdpRemoteAppGfxRedirectionHandler::CreateSharedMemory(void *,IRdsDWMDirectSharedMemory * *)

- ea: `0x180013690`
- end: `0x180013849`
- name: `?CreateSharedMemory@RdpRemoteAppGfxRedirectionHandler@@UEAAJPEAXPEAPEAUIRdsDWMDirectSharedMemory@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *__hidden this, void *, struct IRdsDWMDirectSharedMemory **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180001724`
- `0x1800032d4`
- `0x18000f08c`
- `0x180012c34`
- `0x180013690`
- `0x18002c010`

## string_xrefs

- `0x180013743`: `CreateSharedMemory`
- `0x1800137d3`: `CreateSharedMemory`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::CreateSharedMemory(
        RdpRemoteAppGfxRedirectionHandler *this,
        void *a2,
        struct IRdsDWMDirectSharedMemory **a3)
{
  RdpRemoteAppGfxRedirectContainerSharedMemory *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  RdpRemoteAppGfxRedirectContainerSharedMemory *v9; // rcx
  unsigned __int64 v10; // rax
  __int128 v11; // rcx
  __int64 v12; // rax
  int v13; // edi
  __int16 *v14; // rdx
  const unsigned __int16 **v15; // rax
  const char **v17; // [rsp+30h] [rbp-19h]
  const char **v18; // [rsp+40h] [rbp-9h]
  const unsigned __int16 **v19; // [rsp+48h] [rbp-1h]
  int v20; // [rsp+50h] [rbp+7h] BYREF
  __int64 v21; // [rsp+58h] [rbp+Fh] BYREF
  const char *v22; // [rsp+60h] [rbp+17h] BYREF
  const char *v23; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v24; // [rsp+70h] [rbp+27h] BYREF
  _QWORD v25[5]; // [rsp+78h] [rbp+2Fh] BYREF
  int v26; // [rsp+C8h] [rbp+7Fh] BYREF

  v21 = 0;
  v6 = (RdpRemoteAppGfxRedirectContainerSharedMemory *)operator new(0x258u);
  if ( v6 )
    v9 = RdpRemoteAppGfxRedirectContainerSharedMemory::RdpRemoteAppGfxRedirectContainerSharedMemory(
           v6,
           (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48));
  else
    v9 = 0;
  v10 = (unsigned __int64)v9 + 48;
  v11 = -(__int128)(unsigned __int64)v9;
  *((_QWORD *)&v11 + 1) &= v10;
  if ( *((_QWORD *)&v11 + 1) )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v21);
    v12 = **((_QWORD **)&v11 + 1);
    v21 = *((_QWORD *)&v11 + 1);
    (*(void (__fastcall **)(_QWORD))(v12 + 8))(*((_QWORD *)&v11 + 1));
    v13 = (*(__int64 (__fastcall **)(_QWORD, void *))(**((_QWORD **)&v11 + 1) + 24LL))(*((_QWORD *)&v11 + 1), a2);
    if ( v13 >= 0 )
    {
      v21 = 0;
      *a3 = (struct IRdsDWMDirectSharedMemory *)*((_QWORD *)&v11 + 1);
    }
    else
    {
      *(_QWORD *)&v11 = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v26 = 340;
        v22 = "Initialize failed";
        v14 = (__int16 *)&dword_18003D3FC;
        v23 = "CreateSharedMemory";
        v24 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v25[0] = "Error HResult failed";
        v19 = (const unsigned __int16 **)&v22;
        v18 = &v23;
        v17 = &v24;
        v15 = (const unsigned __int16 **)v25;
LABEL_11:
        v20 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v11,
          (__int64)v14,
          v7,
          v8,
          v15,
          (__int64)&v20,
          (const unsigned __int16 **)v17,
          (__int64)&v26,
          (const unsigned __int16 **)v18,
          v19);
      }
    }
  }
  else
  {
    v13 = -2147467261;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v26 = 335;
      v25[0] = "RdpRemoteAppGfxRedirectContainerSharedMemory";
      v14 = &word_18003D45E;
      v24 = "CreateSharedMemory";
      v23 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v22 = "Unexpected NULL object";
      v19 = (const unsigned __int16 **)v25;
      v18 = &v24;
      v17 = &v23;
      v15 = (const unsigned __int16 **)&v22;
      goto LABEL_11;
    }
  }
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v21);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180013690  push    rbp
0x180013692  push    rbx
0x180013693  push    rsi
0x180013694  push    rdi
0x180013695  lea     rbp, [rsp-3Fh]
0x18001369a  sub     rsp, 88h
0x1800136a1  mov     rbx, rcx
0x1800136a4  mov     [rbp+57h+var_48], 0
0x1800136ac  mov     ecx, 258h; Size
0x1800136b1  mov     rsi, r8
0x1800136b4  mov     rdi, rdx
0x1800136b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800136bc  test    rax, rax
0x1800136bf  jz      short loc_1800136D2
0x1800136c1  lea     rdx, [rbx-30h]; struct RdpRemoteAppGfxRedirectionHandler *
0x1800136c5  mov     rcx, rax; this
0x1800136c8  call    ??0RdpRemoteAppGfxRedirectContainerSharedMemory@@AEAA@PEAVRdpRemoteAppGfxRedirectionHandler@@@Z; RdpRemoteAppGfxRedirectContainerSharedMemory::RdpRemoteAppGfxRedirectContainerSharedMemory(RdpRemoteAppGfxRedirectionHandler *)
0x1800136cd  mov     rcx, rax
0x1800136d0  jmp     short loc_1800136D4
0x1800136d2  xor     ecx, ecx
0x1800136d4  lea     rax, [rcx+30h]
0x1800136d8  neg     rcx
0x1800136db  sbb     rbx, rbx
0x1800136de  and     rbx, rax
0x1800136e1  jz      loc_1800137AA
0x1800136e7  lea     rcx, [rbp+57h+var_48]
0x1800136eb  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800136f0  mov     rax, [rbx]
0x1800136f3  mov     rcx, rbx
0x1800136f6  mov     [rbp+57h+var_48], rbx
0x1800136fa  mov     rax, [rax+8]
0x1800136fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013703  mov     rax, [rbx]
0x180013706  mov     rdx, rdi
0x180013709  mov     rcx, rbx
0x18001370c  mov     rax, [rax+18h]
0x180013710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013715  mov     edi, eax
0x180013717  test    eax, eax
0x180013719  jns     short loc_18001379A
0x18001371b  mov     ecx, cs:dword_180044008
0x180013721  cmp     ecx, 2
0x180013724  jbe     loc_180013832
0x18001372a  lea     rax, aInitializeFail; "Initialize failed"
0x180013731  mov     [rbp+57h+arg_18], 154h
0x180013738  mov     [rbp+57h+var_40], rax
0x18001373c  lea     rdx, dword_18003D3FC
0x180013743  lea     rax, aCreatesharedme; "CreateSharedMemory"
0x18001374a  mov     [rbp+57h+var_38], rax
0x18001374e  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180013755  mov     [rbp+57h+var_30], rax
0x180013759  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180013760  mov     [rbp+57h+var_28], rax
0x180013764  lea     rax, [rbp+57h+var_40]
0x180013768  mov     [rsp+0A0h+var_58], rax
0x18001376d  lea     rax, [rbp+57h+var_38]
0x180013771  mov     [rsp+0A0h+var_60], rax
0x180013776  lea     rax, [rbp+57h+arg_18]
0x18001377a  mov     [rsp+0A0h+var_68], rax
0x18001377f  lea     rax, [rbp+57h+var_30]
0x180013783  mov     [rsp+0A0h+var_70], rax
0x180013788  lea     rax, [rbp+57h+var_50]
0x18001378c  mov     [rsp+0A0h+var_78], rax
0x180013791  lea     rax, [rbp+57h+var_28]
0x180013795  jmp     loc_180013825
0x18001379a  mov     [rbp+57h+var_48], 0
0x1800137a2  mov     [rsi], rbx
0x1800137a5  jmp     loc_180013832
0x1800137aa  mov     eax, cs:dword_180044008
0x1800137b0  mov     edi, 80004003h
0x1800137b5  cmp     eax, 2
0x1800137b8  jbe     short loc_180013832
0x1800137ba  lea     rax, aRdpremoteappgf_2; "RdpRemoteAppGfxRedirectContainerSharedM"...
0x1800137c1  mov     [rbp+57h+arg_18], 14Fh
0x1800137c8  mov     [rbp+57h+var_28], rax
0x1800137cc  lea     rdx, word_18003D45E
0x1800137d3  lea     rax, aCreatesharedme; "CreateSharedMemory"
0x1800137da  mov     [rbp+57h+var_30], rax
0x1800137de  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800137e5  mov     [rbp+57h+var_38], rax
0x1800137e9  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x1800137f0  mov     [rbp+57h+var_40], rax
0x1800137f4  lea     rax, [rbp+57h+var_28]
0x1800137f8  mov     [rsp+0A0h+var_58], rax
0x1800137fd  lea     rax, [rbp+57h+var_30]
0x180013801  mov     [rsp+0A0h+var_60], rax
0x180013806  lea     rax, [rbp+57h+arg_18]
0x18001380a  mov     [rsp+0A0h+var_68], rax
0x18001380f  lea     rax, [rbp+57h+var_38]
0x180013813  mov     [rsp+0A0h+var_70], rax
0x180013818  lea     rax, [rbp+57h+var_50]
0x18001381c  mov     [rsp+0A0h+var_78], rax
0x180013821  lea     rax, [rbp+57h+var_40]
0x180013825  mov     [rsp+0A0h+var_80], rax
0x18001382a  mov     [rbp+57h+var_50], edi
0x18001382d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180013832  lea     rcx, [rbp+57h+var_48]
0x180013836  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18001383b  mov     eax, edi
0x18001383d  add     rsp, 88h
0x180013844  pop     rdi
0x180013845  pop     rsi
0x180013846  pop     rbx
0x180013847  pop     rbp
0x180013848  retn
```
