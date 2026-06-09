# AdvancedSettingsTelemetry::CommitPublicFolder::StopActivity(void)

- ea: `0x180014380`
- end: `0x1800145a4`
- name: `?StopActivity@CommitPublicFolder@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitPublicFolder *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800010f8`
- `0x18000141c`
- `0x180001bac`
- `0x180007698`
- `0x18000845c`
- `0x18000b154`
- `0x180014380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014545`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitPublicFolder::StopActivity(
        AdvancedSettingsTelemetry::CommitPublicFolder *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = AdvancedSettingsLogging::Provider();
    v8 = v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)&dword_180021E84,
        v10 + 8,
        (_DWORD)v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = AdvancedSettingsLogging::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&dword_18002293C,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180014380  push    rbp
0x180014382  push    rbx
0x180014383  push    rdi
0x180014384  lea     rbp, [rsp-47h]
0x180014389  sub     rsp, 100h
0x180014390  mov     rdi, [rcx+110h]
0x180014397  mov     rbx, rcx
0x18001439a  mov     eax, [rdi+48h]
0x18001439d  test    eax, eax
0x18001439f  jns     loc_18001451B
0x1800143a5  add     rdi, 50h ; 'P'
0x1800143a9  cmp     eax, [rdi+8]
0x1800143ac  jnz     loc_18001451B
0x1800143b2  test    rdi, rdi
0x1800143b5  jz      loc_18001451B
0x1800143bb  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800143c0  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x1800143c5  mov     r9, rax
0x1800143c8  mov     ecx, [rax]
0x1800143ca  cmp     ecx, 5
0x1800143cd  jbe     loc_180014592
0x1800143d3  mov     rdx, 200000000000h
0x1800143dd  mov     rcx, rax
0x1800143e0  call    _tlgKeywordOn
0x1800143e5  test    al, al
0x1800143e7  jz      loc_180014592
0x1800143ed  mov     rax, [rdi+70h]
0x1800143f1  lea     rdx, dword_180021E84
0x1800143f8  mov     rcx, [rdi+78h]
0x1800143fc  mov     r8, [rbx+110h]
0x180014403  mov     [rbp+57h+var_60], rax
0x180014407  add     r8, 8
0x18001440b  mov     eax, [rdi+68h]
0x18001440e  mov     [rbp+57h+arg_0], eax
0x180014411  mov     rax, [rdi+60h]
0x180014415  mov     [rbp+57h+var_58], rax
0x180014419  mov     rax, [rdi+58h]
0x18001441d  mov     [rbp+57h+var_50], rax
0x180014421  mov     eax, [rdi+50h]
0x180014424  mov     [rbp+57h+arg_8], eax
0x180014427  mov     rax, [rdi+48h]
0x18001442b  mov     [rbp+57h+var_48], rax
0x18001442f  mov     eax, [rdi+20h]
0x180014432  mov     dword ptr [rbp+57h+arg_10], eax
0x180014435  mov     rax, [rdi+18h]
0x180014439  mov     [rbp+57h+var_40], rax
0x18001443d  mov     eax, [rdi]
0x18001443f  mov     [rbp+57h+arg_18], eax
0x180014442  mov     rax, [rdi+80h]
0x180014449  mov     [rbp+57h+var_38], rax
0x18001444d  mov     eax, [rdi+40h]
0x180014450  mov     [rbp+57h+var_70], eax
0x180014453  mov     rax, [rdi+38h]
0x180014457  mov     [rbp+57h+var_30], rax
0x18001445b  mov     eax, [rdi+8]
0x18001445e  mov     [rbp+57h+var_6C], eax
0x180014461  lea     rax, [rbp+57h+var_68]
0x180014465  mov     [rsp+110h+var_78], rax
0x18001446d  lea     rax, [rbp+57h+var_60]
0x180014471  mov     [rsp+110h+var_80], rax
0x180014479  lea     rax, [rbp+57h+arg_0]
0x18001447d  mov     [rsp+110h+var_88], rax
0x180014485  lea     rax, [rbp+57h+var_58]
0x180014489  mov     [rsp+110h+var_90], rax
0x180014491  lea     rax, [rbp+57h+var_50]
0x180014495  mov     [rsp+110h+var_98], rax
0x18001449a  lea     rax, [rbp+57h+arg_8]
0x18001449e  mov     [rsp+110h+var_A0], rax
0x1800144a3  lea     rax, [rbp+57h+var_48]
0x1800144a7  mov     [rsp+110h+var_A8], rax
0x1800144ac  lea     rax, [rbp+57h+arg_10]
0x1800144b0  mov     [rsp+110h+var_B0], rax
0x1800144b5  lea     rax, [rbp+57h+var_40]
0x1800144b9  mov     [rsp+110h+var_B8], rax
0x1800144be  lea     rax, [rbp+57h+arg_18]
0x1800144c2  mov     [rsp+110h+var_C0], rax
0x1800144c7  lea     rax, [rbp+57h+var_38]
0x1800144cb  mov     [rsp+110h+var_C8], rax
0x1800144d0  lea     rax, [rbp+57h+var_70]
0x1800144d4  mov     [rsp+110h+var_D0], rax
0x1800144d9  lea     rax, [rbp+57h+var_30]
0x1800144dd  mov     [rsp+110h+var_D8], rax
0x1800144e2  lea     rax, [rbp+57h+var_6C]
0x1800144e6  mov     [rsp+110h+var_E0], rax
0x1800144eb  lea     rax, [rbp+57h+var_28]
0x1800144ef  mov     [rsp+110h+var_E8], rax
0x1800144f4  lea     rax, [rbp+57h+var_20]
0x1800144f8  mov     [rbp+57h+var_68], rcx
0x1800144fc  mov     rcx, r9
0x1800144ff  mov     [rsp+110h+var_F0], rax
0x180014504  mov     [rbp+57h+var_28], 1000000h
0x18001450c  mov     [rbp+57h+var_20], 0
0x180014514  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180014519  jmp     short loc_180014592
0x18001451b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014520  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180014525  mov     rdi, rax
0x180014528  mov     ecx, [rax]
0x18001452a  cmp     ecx, 5
0x18001452d  jbe     short loc_180014592
0x18001452f  mov     rdx, 200000000000h
0x180014539  mov     rcx, rax
0x18001453c  call    _tlgKeywordOn
0x180014541  test    al, al
0x180014543  jz      short loc_180014592
0x180014545  call    cs:__imp_GetCurrentThreadId
0x18001454b  mov     r8, [rbx+110h]
0x180014552  lea     rdx, dword_18002293C
0x180014559  mov     [rbp+57h+arg_0], eax
0x18001455c  mov     rcx, rdi
0x18001455f  mov     eax, [r8+48h]
0x180014563  add     r8, 8
0x180014567  mov     [rbp+57h+arg_8], eax
0x18001456a  lea     rax, [rbp+57h+arg_0]
0x18001456e  mov     [rsp+110h+var_E0], rax
0x180014573  lea     rax, [rbp+57h+arg_8]
0x180014577  mov     [rsp+110h+var_E8], rax
0x18001457c  lea     rax, [rbp+57h+arg_10]
0x180014580  mov     [rsp+110h+var_F0], rax
0x180014585  mov     [rbp+57h+arg_10], 0
0x18001458d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014592  mov     rcx, rbx
0x180014595  add     rsp, 100h
0x18001459c  pop     rdi
0x18001459d  pop     rbx
0x18001459e  pop     rbp
0x18001459f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
