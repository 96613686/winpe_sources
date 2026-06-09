# DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::StopActivity(void)

- ea: `0x14000c070`
- end: `0x14000c292`
- name: `?StopActivity@DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140001010`
- `0x1400018ec`
- `0x1400022ec`
- `0x1400082c0`
- `0x14000946c`
- `0x14000c070`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c232`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::StopActivity(
        DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v29[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v30; // [rsp+120h] [rbp+67h] BYREF
  int v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = DirectXDatabaseUpdaterLogging::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v9 = (__int64 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v30 = v4[26];
      v22 = (__int64 *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v32) = v4[8];
      v25 = (__int64 *)*((_QWORD *)v4 + 3);
      v33 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v18 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v19 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&byte_14001E847,
        v10 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&v30,
        &v21,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = DirectXDatabaseUpdaterLogging::Provider(v11);
    v14 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v16 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)&byte_14001E607,
        v16 + 8,
        v17,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000c070  push    rbp
0x14000c072  push    rbx
0x14000c073  push    rdi
0x14000c074  lea     rbp, [rsp-47h]
0x14000c079  sub     rsp, 100h
0x14000c080  mov     rdi, [rcx+110h]
0x14000c087  mov     rbx, rcx
0x14000c08a  mov     eax, [rdi+48h]
0x14000c08d  test    eax, eax
0x14000c08f  jns     loc_14000C208
0x14000c095  add     rdi, 50h ; 'P'
0x14000c099  cmp     eax, [rdi+8]
0x14000c09c  jnz     loc_14000C208
0x14000c0a2  test    rdi, rdi
0x14000c0a5  jz      loc_14000C208
0x14000c0ab  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000c0b0  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000c0b5  mov     r9, rax
0x14000c0b8  mov     ecx, [rax]
0x14000c0ba  cmp     ecx, 5
0x14000c0bd  jbe     loc_14000C280
0x14000c0c3  mov     rdx, 400000000000h
0x14000c0cd  mov     rcx, rax
0x14000c0d0  call    _tlgKeywordOn
0x14000c0d5  test    al, al
0x14000c0d7  jz      loc_14000C280
0x14000c0dd  mov     rax, [rdi+70h]
0x14000c0e1  lea     rdx, byte_14001E847
0x14000c0e8  mov     rcx, [rdi+78h]
0x14000c0ec  mov     r8, [rbx+110h]
0x14000c0f3  mov     [rbp+57h+var_60], rax
0x14000c0f7  add     r8, 8
0x14000c0fb  mov     eax, [rdi+68h]
0x14000c0fe  mov     [rbp+57h+arg_0], eax
0x14000c101  mov     rax, [rdi+60h]
0x14000c105  mov     [rbp+57h+var_58], rax
0x14000c109  mov     rax, [rdi+58h]
0x14000c10d  mov     [rbp+57h+var_50], rax
0x14000c111  mov     eax, [rdi+50h]
0x14000c114  mov     [rbp+57h+arg_8], eax
0x14000c117  mov     rax, [rdi+48h]
0x14000c11b  mov     [rbp+57h+var_48], rax
0x14000c11f  mov     eax, [rdi+20h]
0x14000c122  mov     dword ptr [rbp+57h+arg_10], eax
0x14000c125  mov     rax, [rdi+18h]
0x14000c129  mov     [rbp+57h+var_40], rax
0x14000c12d  mov     eax, [rdi]
0x14000c12f  mov     [rbp+57h+arg_18], eax
0x14000c132  mov     rax, [rdi+80h]
0x14000c139  mov     [rbp+57h+var_38], rax
0x14000c13d  mov     eax, [rdi+40h]
0x14000c140  mov     [rbp+57h+var_70], eax
0x14000c143  mov     rax, [rdi+38h]
0x14000c147  mov     [rbp+57h+var_30], rax
0x14000c14b  mov     eax, [rdi+8]
0x14000c14e  mov     [rbp+57h+var_6C], eax
0x14000c151  mov     eax, 1000000h
0x14000c156  mov     [rbp+57h+var_28], rax
0x14000c15a  mov     [rbp+57h+var_20], rax
0x14000c15e  lea     rax, [rbp+57h+var_68]
0x14000c162  mov     [rsp+110h+var_78], rax
0x14000c16a  lea     rax, [rbp+57h+var_60]
0x14000c16e  mov     [rsp+110h+var_80], rax
0x14000c176  lea     rax, [rbp+57h+arg_0]
0x14000c17a  mov     [rsp+110h+var_88], rax
0x14000c182  lea     rax, [rbp+57h+var_58]
0x14000c186  mov     [rsp+110h+var_90], rax
0x14000c18e  lea     rax, [rbp+57h+var_50]
0x14000c192  mov     [rsp+110h+var_98], rax
0x14000c197  lea     rax, [rbp+57h+arg_8]
0x14000c19b  mov     [rsp+110h+var_A0], rax
0x14000c1a0  lea     rax, [rbp+57h+var_48]
0x14000c1a4  mov     [rsp+110h+var_A8], rax
0x14000c1a9  lea     rax, [rbp+57h+arg_10]
0x14000c1ad  mov     [rsp+110h+var_B0], rax
0x14000c1b2  lea     rax, [rbp+57h+var_40]
0x14000c1b6  mov     [rsp+110h+var_B8], rax
0x14000c1bb  lea     rax, [rbp+57h+arg_18]
0x14000c1bf  mov     [rsp+110h+var_C0], rax
0x14000c1c4  lea     rax, [rbp+57h+var_38]
0x14000c1c8  mov     [rsp+110h+var_C8], rax
0x14000c1cd  lea     rax, [rbp+57h+var_70]
0x14000c1d1  mov     [rsp+110h+var_D0], rax
0x14000c1d6  lea     rax, [rbp+57h+var_30]
0x14000c1da  mov     [rsp+110h+var_D8], rax
0x14000c1df  lea     rax, [rbp+57h+var_6C]
0x14000c1e3  mov     [rsp+110h+var_E0], rax
0x14000c1e8  lea     rax, [rbp+57h+var_28]
0x14000c1ec  mov     [rsp+110h+var_E8], rax
0x14000c1f1  lea     rax, [rbp+57h+var_20]
0x14000c1f5  mov     [rbp+57h+var_68], rcx
0x14000c1f9  mov     rcx, r9
0x14000c1fc  mov     [rsp+110h+var_F0], rax
0x14000c201  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000c206  jmp     short loc_14000C280
0x14000c208  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000c20d  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000c212  mov     rdi, rax
0x14000c215  mov     ecx, [rax]
0x14000c217  cmp     ecx, 5
0x14000c21a  jbe     short loc_14000C280
0x14000c21c  mov     rdx, 400000000000h
0x14000c226  mov     rcx, rax
0x14000c229  call    _tlgKeywordOn
0x14000c22e  test    al, al
0x14000c230  jz      short loc_14000C280
0x14000c232  call    cs:__imp_GetCurrentThreadId
0x14000c238  mov     r8, [rbx+110h]
0x14000c23f  lea     rdx, byte_14001E607
0x14000c246  mov     [rbp+57h+arg_0], eax
0x14000c249  mov     rcx, rdi
0x14000c24c  mov     eax, [r8+48h]
0x14000c250  add     r8, 8
0x14000c254  mov     [rbp+57h+arg_8], eax
0x14000c257  mov     eax, 1000000h
0x14000c25c  mov     [rbp+57h+arg_10], rax
0x14000c260  lea     rax, [rbp+57h+arg_0]
0x14000c264  mov     [rsp+110h+var_E0], rax
0x14000c269  lea     rax, [rbp+57h+arg_8]
0x14000c26d  mov     [rsp+110h+var_E8], rax
0x14000c272  lea     rax, [rbp+57h+arg_10]
0x14000c276  mov     [rsp+110h+var_F0], rax
0x14000c27b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000c280  mov     rcx, rbx
0x14000c283  add     rsp, 100h
0x14000c28a  pop     rdi
0x14000c28b  pop     rbx
0x14000c28c  pop     rbp
0x14000c28d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
