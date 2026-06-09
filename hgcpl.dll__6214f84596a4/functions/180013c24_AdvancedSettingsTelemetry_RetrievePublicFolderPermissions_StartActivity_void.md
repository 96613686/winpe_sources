# AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::StartActivity(void)

- ea: `0x180013c24`
- end: `0x180013cdb`
- name: `?StartActivity@RetrievePublicFolderPermissions@AdvancedSettingsTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::RetrievePublicFolderPermissions *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180015b98`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x180007648`
- `0x18000845c`
- `0x18000b0e4`
- `0x180013c24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c5f`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::StartActivity(
        AdvancedSettingsTelemetry::RetrievePublicFolderPermissions *this)
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
      (unsigned int)&dword_1800223BC,
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
0x180013c24  mov     [rsp+arg_10], rbx
0x180013c29  push    rdi
0x180013c2a  sub     rsp, 30h
0x180013c2e  mov     rbx, rcx
0x180013c31  call    ?zInternalStart@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180013c36  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180013c3b  mov     rdi, rax
0x180013c3e  mov     edx, [rax]
0x180013c40  cmp     edx, 5
0x180013c43  jbe     loc_180013CC9
0x180013c49  mov     rdx, 200000000000h
0x180013c53  mov     rcx, rax
0x180013c56  call    _tlgKeywordOn
0x180013c5b  test    al, al
0x180013c5d  jz      short loc_180013CC9
0x180013c5f  call    cs:__imp_GetCurrentThreadId
0x180013c65  mov     r8, [rbx+110h]
0x180013c6c  mov     [rsp+38h+arg_0], eax
0x180013c70  mov     [rsp+38h+arg_8], 0
0x180013c79  cmp     byte ptr [r8+4], 0
0x180013c7e  jz      short loc_180013C9F
0x180013c80  lea     r9, [r8+18h]
0x180013c84  cmp     dword ptr [r9], 0
0x180013c88  jnz     short loc_180013CA2
0x180013c8a  cmp     dword ptr [r9+4], 0
0x180013c8f  jnz     short loc_180013CA2
0x180013c91  cmp     dword ptr [r9+8], 0
0x180013c96  jnz     short loc_180013CA2
0x180013c98  cmp     dword ptr [r9+0Ch], 0
0x180013c9d  jnz     short loc_180013CA2
0x180013c9f  xor     r9d, r9d
0x180013ca2  lea     rax, [rsp+38h+arg_0]
0x180013ca7  add     r8, 8
0x180013cab  mov     [rsp+38h+var_10], rax
0x180013cb0  lea     rdx, dword_1800223BC
0x180013cb7  lea     rax, [rsp+38h+arg_8]
0x180013cbc  mov     rcx, rdi
0x180013cbf  mov     [rsp+38h+var_18], rax
0x180013cc4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180013cc9  mov     rcx, rbx
0x180013ccc  mov     rbx, [rsp+38h+arg_10]
0x180013cd1  add     rsp, 30h
0x180013cd5  pop     rdi
0x180013cd6  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
