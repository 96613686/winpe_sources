# AdvancedSettingsTelemetry::RetrieveSettings::StartActivity(void)

- ea: `0x180008e9c`
- end: `0x180008f53`
- name: `?StartActivity@RetrieveSettings@AdvancedSettingsTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::RetrieveSettings *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000abc8`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x180007648`
- `0x18000845c`
- `0x180008e9c`
- `0x18000b0e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ed7`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::RetrieveSettings::StartActivity(
        AdvancedSettingsTelemetry::RetrieveSettings *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = AdvancedSettingsLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 0;
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)byte_18002121D,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180008e9c  mov     [rsp+arg_10], rbx
0x180008ea1  push    rdi
0x180008ea2  sub     rsp, 30h
0x180008ea6  mov     rbx, rcx
0x180008ea9  call    ?zInternalStart@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180008eae  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180008eb3  mov     rdi, rax
0x180008eb6  mov     edx, [rax]
0x180008eb8  cmp     edx, 5
0x180008ebb  jbe     loc_180008F41
0x180008ec1  mov     rdx, 200000000000h
0x180008ecb  mov     rcx, rax
0x180008ece  call    _tlgKeywordOn
0x180008ed3  test    al, al
0x180008ed5  jz      short loc_180008F41
0x180008ed7  call    cs:__imp_GetCurrentThreadId
0x180008edd  mov     r8, [rbx+110h]
0x180008ee4  mov     [rsp+38h+arg_0], eax
0x180008ee8  mov     [rsp+38h+arg_8], 0
0x180008ef1  cmp     byte ptr [r8+4], 0
0x180008ef6  jz      short loc_180008F17
0x180008ef8  lea     r9, [r8+18h]
0x180008efc  cmp     dword ptr [r9], 0
0x180008f00  jnz     short loc_180008F1A
0x180008f02  cmp     dword ptr [r9+4], 0
0x180008f07  jnz     short loc_180008F1A
0x180008f09  cmp     dword ptr [r9+8], 0
0x180008f0e  jnz     short loc_180008F1A
0x180008f10  cmp     dword ptr [r9+0Ch], 0
0x180008f15  jnz     short loc_180008F1A
0x180008f17  xor     r9d, r9d
0x180008f1a  lea     rax, [rsp+38h+arg_0]
0x180008f1f  add     r8, 8
0x180008f23  mov     [rsp+38h+var_10], rax
0x180008f28  lea     rdx, byte_18002121D
0x180008f2f  lea     rax, [rsp+38h+arg_8]
0x180008f34  mov     rcx, rdi
0x180008f37  mov     [rsp+38h+var_18], rax
0x180008f3c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180008f41  mov     rcx, rbx
0x180008f44  mov     rbx, [rsp+38h+arg_10]
0x180008f49  add     rsp, 30h
0x180008f4d  pop     rdi
0x180008f4e  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
