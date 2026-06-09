# DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::Stop(ushort const *)

- ea: `0x14000b93c`
- end: `0x14000bb8d`
- name: `?Stop@DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXPEBG@Z`
- size: `593`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140007ad8`

## callees

- `0x140001590`
- `0x14000197c`
- `0x1400022ec`
- `0x1400082c0`
- `0x14000946c`
- `0x14000b93c`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bb1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bb1c`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::Stop(
        DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *this,
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
        (__int64)&unk_14001DB38,
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
        (__int64)byte_14001EA6B,
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
0x14000b93c  mov     [rsp-8+arg_8], rbx
0x14000b941  push    rbp
0x14000b942  push    rsi
0x14000b943  push    rdi
0x14000b944  lea     rbp, [rsp+10h]
0x14000b949  sub     rsp, 120h
0x14000b950  mov     rdi, [rcx+110h]
0x14000b957  mov     rsi, rdx
0x14000b95a  mov     rbx, rcx
0x14000b95d  mov     eax, [rdi+48h]
0x14000b960  test    eax, eax
0x14000b962  jns     loc_14000BAEE
0x14000b968  add     rdi, 50h ; 'P'
0x14000b96c  cmp     eax, [rdi+8]
0x14000b96f  jnz     loc_14000BAEE
0x14000b975  test    rdi, rdi
0x14000b978  jz      loc_14000BAEE
0x14000b97e  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b983  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000b988  mov     r9, rax
0x14000b98b  mov     ecx, [rax]
0x14000b98d  cmp     ecx, 5
0x14000b990  jbe     loc_14000BB73
0x14000b996  mov     rdx, 400000000000h
0x14000b9a0  mov     rcx, rax
0x14000b9a3  call    _tlgKeywordOn
0x14000b9a8  test    al, al
0x14000b9aa  jz      loc_14000BB73
0x14000b9b0  mov     rax, [rdi+78h]
0x14000b9b4  lea     rdx, unk_14001DB38
0x14000b9bb  mov     [rbp+var_60], rax
0x14000b9bf  mov     rcx, r9
0x14000b9c2  mov     rax, [rdi+70h]
0x14000b9c6  mov     r8, [rbx+110h]
0x14000b9cd  mov     [rbp+var_58], rax
0x14000b9d1  add     r8, 8
0x14000b9d5  mov     eax, [rdi+68h]
0x14000b9d8  mov     [rbp+arg_0], eax
0x14000b9db  mov     rax, [rdi+60h]
0x14000b9df  mov     [rbp+var_50], rax
0x14000b9e3  mov     rax, [rdi+58h]
0x14000b9e7  mov     [rbp+var_48], rax
0x14000b9eb  mov     eax, [rdi+50h]
0x14000b9ee  mov     [rbp+arg_10], eax
0x14000b9f1  mov     rax, [rdi+48h]
0x14000b9f5  mov     [rbp+var_40], rax
0x14000b9f9  mov     eax, [rdi+20h]
0x14000b9fc  mov     dword ptr [rbp+arg_18], eax
0x14000b9ff  mov     rax, [rdi+18h]
0x14000ba03  mov     [rbp+var_38], rax
0x14000ba07  mov     eax, [rdi]
0x14000ba09  mov     [rbp+var_80], eax
0x14000ba0c  mov     rax, [rdi+80h]
0x14000ba13  mov     [rbp+var_30], rax
0x14000ba17  mov     eax, [rdi+40h]
0x14000ba1a  mov     [rbp+var_7C], eax
0x14000ba1d  mov     rax, [rdi+38h]
0x14000ba21  mov     [rbp+var_28], rax
0x14000ba25  mov     eax, [rdi+8]
0x14000ba28  mov     [rbp+var_78], eax
0x14000ba2b  mov     eax, 1000000h
0x14000ba30  mov     [rbp+var_20], rax
0x14000ba34  mov     [rbp+var_70], rax
0x14000ba38  lea     rax, [rbp+var_68]
0x14000ba3c  mov     [rsp+130h+var_90], rax
0x14000ba44  lea     rax, [rbp+var_60]
0x14000ba48  mov     [rsp+130h+var_98], rax
0x14000ba50  lea     rax, [rbp+var_58]
0x14000ba54  mov     [rsp+130h+var_A0], rax
0x14000ba5c  lea     rax, [rbp+arg_0]
0x14000ba60  mov     [rsp+130h+var_A8], rax
0x14000ba68  lea     rax, [rbp+var_50]
0x14000ba6c  mov     [rsp+130h+var_B0], rax
0x14000ba74  lea     rax, [rbp+var_48]
0x14000ba78  mov     [rsp+130h+var_B8], rax
0x14000ba7d  lea     rax, [rbp+arg_10]
0x14000ba81  mov     [rsp+130h+var_C0], rax
0x14000ba86  lea     rax, [rbp+var_40]
0x14000ba8a  mov     [rsp+130h+var_C8], rax
0x14000ba8f  lea     rax, [rbp+arg_18]
0x14000ba93  mov     [rsp+130h+var_D0], rax
0x14000ba98  lea     rax, [rbp+var_38]
0x14000ba9c  mov     [rsp+130h+var_D8], rax
0x14000baa1  lea     rax, [rbp+var_80]
0x14000baa5  mov     [rsp+130h+var_E0], rax
0x14000baaa  lea     rax, [rbp+var_30]
0x14000baae  mov     [rsp+130h+var_E8], rax
0x14000bab3  lea     rax, [rbp+var_7C]
0x14000bab7  mov     [rsp+130h+var_F0], rax
0x14000babc  lea     rax, [rbp+var_28]
0x14000bac0  mov     [rsp+130h+var_F8], rax
0x14000bac5  lea     rax, [rbp+var_78]
0x14000bac9  mov     [rsp+130h+var_100], rax
0x14000bace  lea     rax, [rbp+var_20]
0x14000bad2  mov     [rsp+130h+var_108], rax
0x14000bad7  lea     rax, [rbp+var_70]
0x14000badb  mov     [rsp+130h+var_110], rax
0x14000bae0  mov     [rbp+var_68], rsi
0x14000bae4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000bae9  jmp     loc_14000BB73
0x14000baee  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000baf3  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000baf8  mov     rdi, rax
0x14000bafb  mov     ecx, [rax]
0x14000bafd  cmp     ecx, 5
0x14000bb00  jbe     short loc_14000BB73
0x14000bb02  mov     rdx, 400000000000h
0x14000bb0c  mov     rcx, rax
0x14000bb0f  call    _tlgKeywordOn
0x14000bb14  test    al, al
0x14000bb16  jz      short loc_14000BB73
0x14000bb18  mov     [rbp+arg_18], rsi
0x14000bb1c  call    cs:__imp_GetCurrentThreadId
0x14000bb22  mov     r8, [rbx+110h]
0x14000bb29  lea     rdx, byte_14001EA6B
0x14000bb30  mov     [rbp+arg_0], eax
0x14000bb33  mov     rcx, rdi
0x14000bb36  mov     eax, [r8+48h]
0x14000bb3a  add     r8, 8
0x14000bb3e  mov     [rbp+arg_10], eax
0x14000bb41  mov     eax, 1000000h
0x14000bb46  mov     [rbp+var_70], rax
0x14000bb4a  lea     rax, [rbp+arg_18]
0x14000bb4e  mov     [rsp+130h+var_F8], rax
0x14000bb53  lea     rax, [rbp+arg_0]
0x14000bb57  mov     [rsp+130h+var_100], rax
0x14000bb5c  lea     rax, [rbp+arg_10]
0x14000bb60  mov     [rsp+130h+var_108], rax
0x14000bb65  lea     rax, [rbp+var_70]
0x14000bb69  mov     [rsp+130h+var_110], rax
0x14000bb6e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14000bb73  mov     rcx, rbx
0x14000bb76  mov     rbx, [rsp+130h+arg_8]
0x14000bb7e  add     rsp, 120h
0x14000bb85  pop     rdi
0x14000bb86  pop     rsi
0x14000bb87  pop     rbp
0x14000bb88  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
