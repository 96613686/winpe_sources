# DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::StartActivity(ushort const *)

- ea: `0x14000ad00`
- end: `0x14000adc6`
- name: `?StartActivity@DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAAXPEBG@Z`
- size: `198`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140007ad8`

## callees

- `0x140001fd8`
- `0x1400022ec`
- `0x140006df4`
- `0x14000946c`
- `0x14000ad00`
- `0x14000ef38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ad43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ad43`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::StartActivity(
        DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 *v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v5 = DirectXDatabaseUpdaterLogging::Provider(v4);
  v6 = (__int64)v5;
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7) )
  {
    v12 = (__int64 *)a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v11 = CurrentThreadId;
    v13 = 0x1000000;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v6,
      (__int64)word_14001ECE2,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v11,
      &v12);
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000ad00  push    rbx
0x14000ad02  push    rsi
0x14000ad03  push    rdi
0x14000ad04  sub     rsp, 40h
0x14000ad08  mov     rsi, rdx
0x14000ad0b  mov     rbx, rcx
0x14000ad0e  call    ?zInternalStart@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14000ad13  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000ad18  mov     rdi, rax
0x14000ad1b  mov     r8d, [rax]
0x14000ad1e  cmp     r8d, 5
0x14000ad22  jbe     loc_14000ADB7
0x14000ad28  mov     rdx, 400000000000h
0x14000ad32  mov     rcx, rax
0x14000ad35  call    _tlgKeywordOn
0x14000ad3a  test    al, al
0x14000ad3c  jz      short loc_14000ADB7
0x14000ad3e  mov     [rsp+58h+arg_10], rsi
0x14000ad43  call    cs:__imp_GetCurrentThreadId
0x14000ad49  mov     r8, [rbx+110h]
0x14000ad50  mov     [rsp+58h+arg_0], eax
0x14000ad54  mov     [rsp+58h+arg_18], 1000000h
0x14000ad5d  cmp     byte ptr [r8+4], 0
0x14000ad62  jz      short loc_14000AD83
0x14000ad64  lea     r9, [r8+18h]
0x14000ad68  cmp     dword ptr [r9], 0
0x14000ad6c  jnz     short loc_14000AD86
0x14000ad6e  cmp     dword ptr [r9+4], 0
0x14000ad73  jnz     short loc_14000AD86
0x14000ad75  cmp     dword ptr [r9+8], 0
0x14000ad7a  jnz     short loc_14000AD86
0x14000ad7c  cmp     dword ptr [r9+0Ch], 0
0x14000ad81  jnz     short loc_14000AD86
0x14000ad83  xor     r9d, r9d
0x14000ad86  lea     rax, [rsp+58h+arg_10]
0x14000ad8b  add     r8, 8
0x14000ad8f  mov     [rsp+58h+var_28], rax
0x14000ad94  lea     rdx, word_14001ECE2
0x14000ad9b  lea     rax, [rsp+58h+arg_0]
0x14000ada0  mov     rcx, rdi
0x14000ada3  mov     [rsp+58h+var_30], rax
0x14000ada8  lea     rax, [rsp+58h+arg_18]
0x14000adad  mov     [rsp+58h+var_38], rax
0x14000adb2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14000adb7  mov     rcx, rbx
0x14000adba  add     rsp, 40h
0x14000adbe  pop     rdi
0x14000adbf  pop     rsi
0x14000adc0  pop     rbx
0x14000adc1  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
