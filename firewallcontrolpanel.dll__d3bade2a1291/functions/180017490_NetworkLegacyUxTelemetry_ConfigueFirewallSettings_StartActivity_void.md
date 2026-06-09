# NetworkLegacyUxTelemetry::ConfigueFirewallSettings::StartActivity(void)

- ea: `0x180017490`
- end: `0x180017549`
- name: `?StartActivity@ConfigueFirewallSettings@NetworkLegacyUxTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::ConfigueFirewallSettings *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800171c8`

## callees

- `0x18000156c`
- `0x180001b8c`
- `0x18000ca00`
- `0x18000dfc0`
- `0x18000ee5c`
- `0x180017490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800174cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800174cb`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::ConfigueFirewallSettings::StartActivity(
        NetworkLegacyUxTelemetry::ConfigueFirewallSettings *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = NetworkLegacyUxLogging::Provider();
  v4 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL, v3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (__int64)&byte_1800397AF,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180017490  mov     [rsp+arg_10], rbx
0x180017495  push    rdi
0x180017496  sub     rsp, 30h
0x18001749a  mov     rbx, rcx
0x18001749d  call    ?zInternalStart@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800174a2  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x1800174a7  mov     rdi, rax
0x1800174aa  mov     edx, [rax]
0x1800174ac  cmp     edx, 5
0x1800174af  jbe     loc_180017535
0x1800174b5  mov     rdx, 400000000000h
0x1800174bf  mov     rcx, rax
0x1800174c2  call    _tlgKeywordOn
0x1800174c7  test    al, al
0x1800174c9  jz      short loc_180017535
0x1800174cb  call    cs:__imp_GetCurrentThreadId
0x1800174d1  mov     [rsp+38h+arg_0], eax
0x1800174d5  mov     [rsp+38h+arg_8], 0
0x1800174de  mov     r8, [rbx+110h]
0x1800174e5  cmp     byte ptr [r8+4], 0
0x1800174ea  jz      short loc_18001750B
0x1800174ec  lea     r9, [r8+18h]
0x1800174f0  cmp     dword ptr [r9], 0
0x1800174f4  jnz     short loc_18001750E
0x1800174f6  cmp     dword ptr [r9+4], 0
0x1800174fb  jnz     short loc_18001750E
0x1800174fd  cmp     dword ptr [r9+8], 0
0x180017502  jnz     short loc_18001750E
0x180017504  cmp     dword ptr [r9+0Ch], 0
0x180017509  jnz     short loc_18001750E
0x18001750b  xor     r9d, r9d
0x18001750e  add     r8, 8
0x180017512  lea     rax, [rsp+38h+arg_0]
0x180017517  mov     [rsp+38h+var_10], rax
0x18001751c  lea     rax, [rsp+38h+arg_8]
0x180017521  mov     [rsp+38h+var_18], rax
0x180017526  lea     rdx, byte_1800397AF
0x18001752d  mov     rcx, rdi
0x180017530  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180017535  mov     rcx, rbx
0x180017538  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001753d  nop
0x18001753e  mov     rbx, [rsp+38h+arg_10]
0x180017543  add     rsp, 30h
0x180017547  pop     rdi
0x180017548  retn
```
