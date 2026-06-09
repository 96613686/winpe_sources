# RdsDWMDirectDriverIO::CreateSharedMemory(void *,IRdsDWMDirectSharedMemory * *)

- ea: `0x180008b80`
- end: `0x180008d96`
- name: `?CreateSharedMemory@RdsDWMDirectDriverIO@@UEAAJPEAXPEAPEAUIRdsDWMDirectSharedMemory@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *__hidden this, void *, struct IRdsDWMDirectSharedMemory **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001724`
- `0x1800032d4`
- `0x180005f6c`
- `0x180008b80`
- `0x18002c010`

## string_xrefs

- `0x180008c7b`: `CreateSharedMemory`
- `0x180008d14`: `CreateSharedMemory`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::CreateSharedMemory(
        RdsDWMDirectDriverIO *this,
        void *a2,
        struct IRdsDWMDirectSharedMemory **a3)
{
  _DWORD *v5; // rax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  _DWORD *v9; // rbx
  int v10; // edi
  __int16 *v11; // rdx
  const char **v12; // rax
  const char **v14; // [rsp+30h] [rbp-50h]
  const char **v15; // [rsp+40h] [rbp-40h]
  const char **v16; // [rsp+48h] [rbp-38h]
  int v17; // [rsp+50h] [rbp-30h] BYREF
  _DWORD *v18; // [rsp+58h] [rbp-28h] BYREF
  const char *v19; // [rsp+60h] [rbp-20h] BYREF
  const char *v20; // [rsp+68h] [rbp-18h] BYREF
  const char *v21; // [rsp+70h] [rbp-10h] BYREF
  const char *v22; // [rsp+78h] [rbp-8h] BYREF
  int v23; // [rsp+B8h] [rbp+38h] BYREF

  v18 = 0;
  v5 = operator new(0x240u);
  v9 = v5;
  if ( v5 )
  {
    v5[6] = -607474739;
    v5[7] = 1;
    *((_QWORD *)v5 + 2) = "RdsDWMDirectSharedMemory";
    *(_QWORD *)v5 = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v5 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
    *(_QWORD *)v5 = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v5 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
    v5[10] = 0;
    *((_QWORD *)v5 + 6) = &RdsDWMDirectSharedMemory::`vftable';
    *((_WORD *)v5 + 28) = 0;
    *((_QWORD *)v5 + 4) = v5;
    TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v18);
    v18 = v9;
    (*(void (__fastcall **)(_DWORD *))(*((_QWORD *)v9 + 6) + 8LL))(v9 + 12);
    v10 = (*(__int64 (__fastcall **)(_DWORD *, void *))(*((_QWORD *)v9 + 6) + 24LL))(v9 + 12, a2);
    if ( v10 >= 0 )
    {
      v18 = 0;
      *a3 = (struct IRdsDWMDirectSharedMemory *)((unsigned __int64)(v9 + 12) & -(__int64)(v9 != 0));
    }
    else
    {
      v6 = dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v23 = 669;
        v19 = "Initialize failed";
        v11 = &word_18003849E;
        v20 = "CreateSharedMemory";
        v21 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
        v22 = "Error HResult failed";
        v16 = &v19;
        v15 = &v20;
        v14 = &v21;
        v12 = &v22;
LABEL_8:
        v17 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v6,
          (_DWORD)v11,
          v7,
          v8,
          (__int64)v12,
          (__int64)&v17,
          (__int64)v14,
          (__int64)&v23,
          (__int64)v15,
          (__int64)v16);
      }
    }
  }
  else
  {
    v10 = -2147467261;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v23 = 666;
      v22 = "RdsDWMDirectSharedMemory";
      v11 = (__int16 *)byte_1800384F3;
      v21 = "CreateSharedMemory";
      v20 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
      v19 = "Unexpected NULL object";
      v16 = &v22;
      v15 = &v21;
      v14 = &v20;
      v12 = &v19;
      goto LABEL_8;
    }
  }
  TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(&v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008b80  mov     [rsp-18h+arg_0], rbx
0x180008b85  mov     [rsp-18h+arg_8], rsi
0x180008b8a  push    rbp
0x180008b8b  push    rdi
0x180008b8c  push    r14
0x180008b8e  mov     rbp, rsp
0x180008b91  sub     rsp, 80h
0x180008b98  mov     ecx, 240h; Size
0x180008b9d  mov     [rbp+var_28], 0
0x180008ba5  mov     r14, r8
0x180008ba8  mov     rdi, rdx
0x180008bab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008bb0  mov     rbx, rax
0x180008bb3  test    rax, rax
0x180008bb6  jz      loc_180008CEB
0x180008bbc  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180008bc3  lea     rcx, [rbp+var_28]
0x180008bc7  mov     dword ptr [rbx+1Ch], 1
0x180008bce  lea     rax, aRdsdwmdirectsh; "RdsDWMDirectSharedMemory"
0x180008bd5  mov     [rbx+10h], rax
0x180008bd9  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x180008be0  mov     [rbx], rax
0x180008be3  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180008bea  mov     [rbx+8], rax
0x180008bee  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x180008bf5  mov     [rbx], rax
0x180008bf8  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180008bff  mov     [rbx+8], rax
0x180008c03  lea     rax, ??_7RdsDWMDirectSharedMemory@@6B@; const RdsDWMDirectSharedMemory::`vftable'
0x180008c0a  mov     dword ptr [rbx+28h], 0
0x180008c11  mov     [rbx+30h], rax
0x180008c15  xor     eax, eax
0x180008c17  mov     [rbx+38h], ax
0x180008c1b  mov     [rbx+20h], rbx
0x180008c1f  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x180008c24  lea     rsi, [rbx+30h]
0x180008c28  mov     [rbp+var_28], rbx
0x180008c2c  mov     rax, [rsi]
0x180008c2f  mov     rcx, rsi
0x180008c32  mov     rax, [rax+8]
0x180008c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3b  mov     rax, [rsi]
0x180008c3e  mov     rdx, rdi
0x180008c41  mov     rcx, rsi
0x180008c44  mov     rax, [rax+18h]
0x180008c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c4d  mov     edi, eax
0x180008c4f  test    eax, eax
0x180008c51  jns     short loc_180008CD2
0x180008c53  mov     ecx, cs:dword_180044008
0x180008c59  cmp     ecx, 2
0x180008c5c  jbe     loc_180008D73
0x180008c62  lea     rax, aInitializeFail; "Initialize failed"
0x180008c69  mov     [rbp+arg_18], 29Dh
0x180008c70  mov     [rbp+var_20], rax
0x180008c74  lea     rdx, word_18003849E
0x180008c7b  lea     rax, aCreatesharedme; "CreateSharedMemory"
0x180008c82  mov     [rbp+var_18], rax
0x180008c86  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180008c8d  mov     [rbp+var_10], rax
0x180008c91  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180008c98  mov     [rbp+var_8], rax
0x180008c9c  lea     rax, [rbp+var_20]
0x180008ca0  mov     [rsp+80h+var_38], rax
0x180008ca5  lea     rax, [rbp+var_18]
0x180008ca9  mov     [rsp+80h+var_40], rax
0x180008cae  lea     rax, [rbp+arg_18]
0x180008cb2  mov     [rsp+80h+var_48], rax
0x180008cb7  lea     rax, [rbp+var_10]
0x180008cbb  mov     [rsp+80h+var_50], rax
0x180008cc0  lea     rax, [rbp+var_30]
0x180008cc4  mov     [rsp+80h+var_58], rax
0x180008cc9  lea     rax, [rbp+var_8]
0x180008ccd  jmp     loc_180008D66
0x180008cd2  neg     rbx
0x180008cd5  mov     [rbp+var_28], 0
0x180008cdd  sbb     rax, rax
0x180008ce0  and     rax, rsi
0x180008ce3  mov     [r14], rax
0x180008ce6  jmp     loc_180008D73
0x180008ceb  mov     eax, cs:dword_180044008
0x180008cf1  mov     edi, 80004003h
0x180008cf6  cmp     eax, 2
0x180008cf9  jbe     short loc_180008D73
0x180008cfb  lea     rax, aRdsdwmdirectsh; "RdsDWMDirectSharedMemory"
0x180008d02  mov     [rbp+arg_18], 29Ah
0x180008d09  mov     [rbp+var_8], rax
0x180008d0d  lea     rdx, byte_1800384F3
0x180008d14  lea     rax, aCreatesharedme; "CreateSharedMemory"
0x180008d1b  mov     [rbp+var_10], rax
0x180008d1f  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180008d26  mov     [rbp+var_18], rax
0x180008d2a  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180008d31  mov     [rbp+var_20], rax
0x180008d35  lea     rax, [rbp+var_8]
0x180008d39  mov     [rsp+80h+var_38], rax
0x180008d3e  lea     rax, [rbp+var_10]
0x180008d42  mov     [rsp+80h+var_40], rax
0x180008d47  lea     rax, [rbp+arg_18]
0x180008d4b  mov     [rsp+80h+var_48], rax
0x180008d50  lea     rax, [rbp+var_18]
0x180008d54  mov     [rsp+80h+var_50], rax
0x180008d59  lea     rax, [rbp+var_30]
0x180008d5d  mov     [rsp+80h+var_58], rax
0x180008d62  lea     rax, [rbp+var_20]
0x180008d66  mov     [rsp+80h+var_60], rax
0x180008d6b  mov     [rbp+var_30], edi
0x180008d6e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180008d73  lea     rcx, [rbp+var_28]
0x180008d77  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x180008d7c  lea     r11, [rsp+80h+var_s0]
0x180008d84  mov     eax, edi
0x180008d86  mov     rbx, [r11+20h]
0x180008d8a  mov     rsi, [r11+28h]
0x180008d8e  mov     rsp, r11
0x180008d91  pop     r14
0x180008d93  pop     rdi
0x180008d94  pop     rbp
0x180008d95  retn
```
