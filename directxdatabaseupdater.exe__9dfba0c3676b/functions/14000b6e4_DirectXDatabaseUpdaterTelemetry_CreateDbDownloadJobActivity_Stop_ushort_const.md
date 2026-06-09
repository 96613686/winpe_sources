# DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::Stop(ushort const *)

- ea: `0x14000b6e4`
- end: `0x14000b935`
- name: `?Stop@CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXPEBG@Z`
- size: `593`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000b0cc`

## callees

- `0x140001590`
- `0x14000197c`
- `0x1400022ec`
- `0x1400082c0`
- `0x14000946c`
- `0x14000b6e4`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b8c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b8c4`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::Stop(
        DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rcx
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rcx
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+B0h] [rbp-80h] BYREF
  int v20; // [rsp+B4h] [rbp-7Ch] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-70h] BYREF
  __int64 *v23; // [rsp+C8h] [rbp-68h] BYREF
  __int64 *v24; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v26; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v28; // [rsp+F0h] [rbp-40h] BYREF
  __int64 *v29; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v31; // [rsp+108h] [rbp-28h] BYREF
  __int64 v32[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v33; // [rsp+140h] [rbp+10h] BYREF
  int v34; // [rsp+150h] [rbp+20h] BYREF
  __int64 *v35; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = DirectXDatabaseUpdaterLogging::Provider(v7);
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v9) )
    {
      v24 = (__int64 *)*((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)this + 34);
      v25 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v33 = v6[26];
      v26 = (__int64 *)*((_QWORD *)v6 + 12);
      v27 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v34 = v6[20];
      v28 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      LODWORD(v35) = v6[8];
      v29 = (__int64 *)*((_QWORD *)v6 + 3);
      v19 = *v6;
      v30 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v20 = v6[16];
      v31 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v21 = v6[2];
      v32[0] = 0x1000000;
      v22 = 0x1000000;
      v23 = (__int64 *)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v10,
        (__int64)&byte_14001E6B7,
        v11 + 8,
        v10,
        (__int64)&v22,
        (__int64)v32,
        (__int64)&v21,
        &v31,
        (__int64)&v20,
        &v30,
        (__int64)&v19,
        &v29,
        (__int64)&v35,
        &v28,
        (__int64)&v34,
        &v27,
        &v26,
        (__int64)&v33,
        &v25,
        &v24,
        &v23);
    }
  }
  else
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v13 = DirectXDatabaseUpdaterLogging::Provider(v12);
    v15 = (__int64)v13;
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL, v14) )
    {
      v35 = (__int64 *)a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v33 = CurrentThreadId;
      v34 = *(_DWORD *)(v17 + 72);
      v22 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v15,
        (__int64)byte_14001E14D,
        v17 + 8,
        v18,
        (__int64)&v22,
        (__int64)&v34,
        (__int64)&v33,
        &v35);
    }
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000b6e4  mov     [rsp-8+arg_8], rbx
0x14000b6e9  push    rbp
0x14000b6ea  push    rsi
0x14000b6eb  push    rdi
0x14000b6ec  lea     rbp, [rsp+10h]
0x14000b6f1  sub     rsp, 120h
0x14000b6f8  mov     rdi, [rcx+110h]
0x14000b6ff  mov     rsi, rdx
0x14000b702  mov     rbx, rcx
0x14000b705  mov     eax, [rdi+48h]
0x14000b708  test    eax, eax
0x14000b70a  jns     loc_14000B896
0x14000b710  add     rdi, 50h ; 'P'
0x14000b714  cmp     eax, [rdi+8]
0x14000b717  jnz     loc_14000B896
0x14000b71d  test    rdi, rdi
0x14000b720  jz      loc_14000B896
0x14000b726  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b72b  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000b730  mov     r9, rax
0x14000b733  mov     ecx, [rax]
0x14000b735  cmp     ecx, 5
0x14000b738  jbe     loc_14000B91B
0x14000b73e  mov     rdx, 400000000000h
0x14000b748  mov     rcx, rax
0x14000b74b  call    _tlgKeywordOn
0x14000b750  test    al, al
0x14000b752  jz      loc_14000B91B
0x14000b758  mov     rax, [rdi+78h]
0x14000b75c  lea     rdx, byte_14001E6B7
0x14000b763  mov     [rbp+var_60], rax
0x14000b767  mov     rcx, r9
0x14000b76a  mov     rax, [rdi+70h]
0x14000b76e  mov     r8, [rbx+110h]
0x14000b775  mov     [rbp+var_58], rax
0x14000b779  add     r8, 8
0x14000b77d  mov     eax, [rdi+68h]
0x14000b780  mov     [rbp+arg_0], eax
0x14000b783  mov     rax, [rdi+60h]
0x14000b787  mov     [rbp+var_50], rax
0x14000b78b  mov     rax, [rdi+58h]
0x14000b78f  mov     [rbp+var_48], rax
0x14000b793  mov     eax, [rdi+50h]
0x14000b796  mov     [rbp+arg_10], eax
0x14000b799  mov     rax, [rdi+48h]
0x14000b79d  mov     [rbp+var_40], rax
0x14000b7a1  mov     eax, [rdi+20h]
0x14000b7a4  mov     dword ptr [rbp+arg_18], eax
0x14000b7a7  mov     rax, [rdi+18h]
0x14000b7ab  mov     [rbp+var_38], rax
0x14000b7af  mov     eax, [rdi]
0x14000b7b1  mov     [rbp+var_80], eax
0x14000b7b4  mov     rax, [rdi+80h]
0x14000b7bb  mov     [rbp+var_30], rax
0x14000b7bf  mov     eax, [rdi+40h]
0x14000b7c2  mov     [rbp+var_7C], eax
0x14000b7c5  mov     rax, [rdi+38h]
0x14000b7c9  mov     [rbp+var_28], rax
0x14000b7cd  mov     eax, [rdi+8]
0x14000b7d0  mov     [rbp+var_78], eax
0x14000b7d3  mov     eax, 1000000h
0x14000b7d8  mov     [rbp+var_20], rax
0x14000b7dc  mov     [rbp+var_70], rax
0x14000b7e0  lea     rax, [rbp+var_68]
0x14000b7e4  mov     [rsp+130h+var_90], rax
0x14000b7ec  lea     rax, [rbp+var_60]
0x14000b7f0  mov     [rsp+130h+var_98], rax
0x14000b7f8  lea     rax, [rbp+var_58]
0x14000b7fc  mov     [rsp+130h+var_A0], rax
0x14000b804  lea     rax, [rbp+arg_0]
0x14000b808  mov     [rsp+130h+var_A8], rax
0x14000b810  lea     rax, [rbp+var_50]
0x14000b814  mov     [rsp+130h+var_B0], rax
0x14000b81c  lea     rax, [rbp+var_48]
0x14000b820  mov     [rsp+130h+var_B8], rax
0x14000b825  lea     rax, [rbp+arg_10]
0x14000b829  mov     [rsp+130h+var_C0], rax
0x14000b82e  lea     rax, [rbp+var_40]
0x14000b832  mov     [rsp+130h+var_C8], rax
0x14000b837  lea     rax, [rbp+arg_18]
0x14000b83b  mov     [rsp+130h+var_D0], rax
0x14000b840  lea     rax, [rbp+var_38]
0x14000b844  mov     [rsp+130h+var_D8], rax
0x14000b849  lea     rax, [rbp+var_80]
0x14000b84d  mov     [rsp+130h+var_E0], rax
0x14000b852  lea     rax, [rbp+var_30]
0x14000b856  mov     [rsp+130h+var_E8], rax
0x14000b85b  lea     rax, [rbp+var_7C]
0x14000b85f  mov     [rsp+130h+var_F0], rax
0x14000b864  lea     rax, [rbp+var_28]
0x14000b868  mov     [rsp+130h+var_F8], rax
0x14000b86d  lea     rax, [rbp+var_78]
0x14000b871  mov     [rsp+130h+var_100], rax
0x14000b876  lea     rax, [rbp+var_20]
0x14000b87a  mov     [rsp+130h+var_108], rax
0x14000b87f  lea     rax, [rbp+var_70]
0x14000b883  mov     [rsp+130h+var_110], rax
0x14000b888  mov     [rbp+var_68], rsi
0x14000b88c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000b891  jmp     loc_14000B91B
0x14000b896  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b89b  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000b8a0  mov     rdi, rax
0x14000b8a3  mov     ecx, [rax]
0x14000b8a5  cmp     ecx, 5
0x14000b8a8  jbe     short loc_14000B91B
0x14000b8aa  mov     rdx, 400000000000h
0x14000b8b4  mov     rcx, rax
0x14000b8b7  call    _tlgKeywordOn
0x14000b8bc  test    al, al
0x14000b8be  jz      short loc_14000B91B
0x14000b8c0  mov     [rbp+arg_18], rsi
0x14000b8c4  call    cs:__imp_GetCurrentThreadId
0x14000b8ca  mov     r8, [rbx+110h]
0x14000b8d1  lea     rdx, byte_14001E14D
0x14000b8d8  mov     [rbp+arg_0], eax
0x14000b8db  mov     rcx, rdi
0x14000b8de  mov     eax, [r8+48h]
0x14000b8e2  add     r8, 8
0x14000b8e6  mov     [rbp+arg_10], eax
0x14000b8e9  mov     eax, 1000000h
0x14000b8ee  mov     [rbp+var_70], rax
0x14000b8f2  lea     rax, [rbp+arg_18]
0x14000b8f6  mov     [rsp+130h+var_F8], rax
0x14000b8fb  lea     rax, [rbp+arg_0]
0x14000b8ff  mov     [rsp+130h+var_100], rax
0x14000b904  lea     rax, [rbp+arg_10]
0x14000b908  mov     [rsp+130h+var_108], rax
0x14000b90d  lea     rax, [rbp+var_70]
0x14000b911  mov     [rsp+130h+var_110], rax
0x14000b916  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14000b91b  mov     rcx, rbx
0x14000b91e  mov     rbx, [rsp+130h+arg_8]
0x14000b926  add     rsp, 120h
0x14000b92d  pop     rdi
0x14000b92e  pop     rsi
0x14000b92f  pop     rbp
0x14000b930  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
