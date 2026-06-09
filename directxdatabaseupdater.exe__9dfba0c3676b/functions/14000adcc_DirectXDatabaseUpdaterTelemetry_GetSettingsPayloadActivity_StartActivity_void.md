# DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::StartActivity(void)

- ea: `0x14000adcc`
- end: `0x14000ae85`
- name: `?StartActivity@GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x14000b0cc`

## callees

- `0x14000187c`
- `0x1400022ec`
- `0x140006df4`
- `0x14000946c`
- `0x14000adcc`
- `0x14000ef38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ae07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ae07`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::StartActivity(
        DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *this)
{
  __int64 v2; // rcx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v3 = DirectXDatabaseUpdaterLogging::Provider(v2);
  v5 = (__int64)v3;
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)&unk_14001EC90,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000adcc  mov     [rsp+arg_10], rbx
0x14000add1  push    rdi
0x14000add2  sub     rsp, 30h
0x14000add6  mov     rbx, rcx
0x14000add9  call    ?zInternalStart@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14000adde  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000ade3  mov     rdi, rax
0x14000ade6  mov     edx, [rax]
0x14000ade8  cmp     edx, 5
0x14000adeb  jbe     loc_14000AE71
0x14000adf1  mov     rdx, 400000000000h
0x14000adfb  mov     rcx, rax
0x14000adfe  call    _tlgKeywordOn
0x14000ae03  test    al, al
0x14000ae05  jz      short loc_14000AE71
0x14000ae07  call    cs:__imp_GetCurrentThreadId
0x14000ae0d  mov     [rsp+38h+arg_0], eax
0x14000ae11  mov     [rsp+38h+arg_8], 1000000h
0x14000ae1a  mov     r8, [rbx+110h]
0x14000ae21  cmp     byte ptr [r8+4], 0
0x14000ae26  jz      short loc_14000AE47
0x14000ae28  lea     r9, [r8+18h]
0x14000ae2c  cmp     dword ptr [r9], 0
0x14000ae30  jnz     short loc_14000AE4A
0x14000ae32  cmp     dword ptr [r9+4], 0
0x14000ae37  jnz     short loc_14000AE4A
0x14000ae39  cmp     dword ptr [r9+8], 0
0x14000ae3e  jnz     short loc_14000AE4A
0x14000ae40  cmp     dword ptr [r9+0Ch], 0
0x14000ae45  jnz     short loc_14000AE4A
0x14000ae47  xor     r9d, r9d
0x14000ae4a  add     r8, 8
0x14000ae4e  lea     rax, [rsp+38h+arg_0]
0x14000ae53  mov     [rsp+38h+var_10], rax
0x14000ae58  lea     rax, [rsp+38h+arg_8]
0x14000ae5d  mov     [rsp+38h+var_18], rax
0x14000ae62  lea     rdx, unk_14001EC90
0x14000ae69  mov     rcx, rdi
0x14000ae6c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14000ae71  mov     rcx, rbx
0x14000ae74  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14000ae79  nop
0x14000ae7a  mov     rbx, [rsp+38h+arg_10]
0x14000ae7f  add     rsp, 30h
0x14000ae83  pop     rdi
0x14000ae84  retn
```
