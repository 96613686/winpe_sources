# AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::StopActivity(void)

- ea: `0x180014c40`
- end: `0x180014e64`
- name: `?StopActivity@RetrievePublicFolderPermissions@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::RetrievePublicFolderPermissions *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800010f8`
- `0x18000141c`
- `0x180001bac`
- `0x180007698`
- `0x18000845c`
- `0x18000b154`
- `0x180014c40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e05`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::RetrievePublicFolderPermissions::StopActivity(
        AdvancedSettingsTelemetry::RetrievePublicFolderPermissions *this)
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
        (unsigned int)byte_180022413,
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
        (unsigned int)&unk_180022230,
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
0x180014c40  push    rbp
0x180014c42  push    rbx
0x180014c43  push    rdi
0x180014c44  lea     rbp, [rsp-47h]
0x180014c49  sub     rsp, 100h
0x180014c50  mov     rdi, [rcx+110h]
0x180014c57  mov     rbx, rcx
0x180014c5a  mov     eax, [rdi+48h]
0x180014c5d  test    eax, eax
0x180014c5f  jns     loc_180014DDB
0x180014c65  add     rdi, 50h ; 'P'
0x180014c69  cmp     eax, [rdi+8]
0x180014c6c  jnz     loc_180014DDB
0x180014c72  test    rdi, rdi
0x180014c75  jz      loc_180014DDB
0x180014c7b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014c80  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180014c85  mov     r9, rax
0x180014c88  mov     ecx, [rax]
0x180014c8a  cmp     ecx, 5
0x180014c8d  jbe     loc_180014E52
0x180014c93  mov     rdx, 200000000000h
0x180014c9d  mov     rcx, rax
0x180014ca0  call    _tlgKeywordOn
0x180014ca5  test    al, al
0x180014ca7  jz      loc_180014E52
0x180014cad  mov     rax, [rdi+70h]
0x180014cb1  lea     rdx, byte_180022413
0x180014cb8  mov     rcx, [rdi+78h]
0x180014cbc  mov     r8, [rbx+110h]
0x180014cc3  mov     [rbp+57h+var_60], rax
0x180014cc7  add     r8, 8
0x180014ccb  mov     eax, [rdi+68h]
0x180014cce  mov     [rbp+57h+arg_0], eax
0x180014cd1  mov     rax, [rdi+60h]
0x180014cd5  mov     [rbp+57h+var_58], rax
0x180014cd9  mov     rax, [rdi+58h]
0x180014cdd  mov     [rbp+57h+var_50], rax
0x180014ce1  mov     eax, [rdi+50h]
0x180014ce4  mov     [rbp+57h+arg_8], eax
0x180014ce7  mov     rax, [rdi+48h]
0x180014ceb  mov     [rbp+57h+var_48], rax
0x180014cef  mov     eax, [rdi+20h]
0x180014cf2  mov     dword ptr [rbp+57h+arg_10], eax
0x180014cf5  mov     rax, [rdi+18h]
0x180014cf9  mov     [rbp+57h+var_40], rax
0x180014cfd  mov     eax, [rdi]
0x180014cff  mov     [rbp+57h+arg_18], eax
0x180014d02  mov     rax, [rdi+80h]
0x180014d09  mov     [rbp+57h+var_38], rax
0x180014d0d  mov     eax, [rdi+40h]
0x180014d10  mov     [rbp+57h+var_70], eax
0x180014d13  mov     rax, [rdi+38h]
0x180014d17  mov     [rbp+57h+var_30], rax
0x180014d1b  mov     eax, [rdi+8]
0x180014d1e  mov     [rbp+57h+var_6C], eax
0x180014d21  lea     rax, [rbp+57h+var_68]
0x180014d25  mov     [rsp+110h+var_78], rax
0x180014d2d  lea     rax, [rbp+57h+var_60]
0x180014d31  mov     [rsp+110h+var_80], rax
0x180014d39  lea     rax, [rbp+57h+arg_0]
0x180014d3d  mov     [rsp+110h+var_88], rax
0x180014d45  lea     rax, [rbp+57h+var_58]
0x180014d49  mov     [rsp+110h+var_90], rax
0x180014d51  lea     rax, [rbp+57h+var_50]
0x180014d55  mov     [rsp+110h+var_98], rax
0x180014d5a  lea     rax, [rbp+57h+arg_8]
0x180014d5e  mov     [rsp+110h+var_A0], rax
0x180014d63  lea     rax, [rbp+57h+var_48]
0x180014d67  mov     [rsp+110h+var_A8], rax
0x180014d6c  lea     rax, [rbp+57h+arg_10]
0x180014d70  mov     [rsp+110h+var_B0], rax
0x180014d75  lea     rax, [rbp+57h+var_40]
0x180014d79  mov     [rsp+110h+var_B8], rax
0x180014d7e  lea     rax, [rbp+57h+arg_18]
0x180014d82  mov     [rsp+110h+var_C0], rax
0x180014d87  lea     rax, [rbp+57h+var_38]
0x180014d8b  mov     [rsp+110h+var_C8], rax
0x180014d90  lea     rax, [rbp+57h+var_70]
0x180014d94  mov     [rsp+110h+var_D0], rax
0x180014d99  lea     rax, [rbp+57h+var_30]
0x180014d9d  mov     [rsp+110h+var_D8], rax
0x180014da2  lea     rax, [rbp+57h+var_6C]
0x180014da6  mov     [rsp+110h+var_E0], rax
0x180014dab  lea     rax, [rbp+57h+var_28]
0x180014daf  mov     [rsp+110h+var_E8], rax
0x180014db4  lea     rax, [rbp+57h+var_20]
0x180014db8  mov     [rbp+57h+var_68], rcx
0x180014dbc  mov     rcx, r9
0x180014dbf  mov     [rsp+110h+var_F0], rax
0x180014dc4  mov     [rbp+57h+var_28], 1000000h
0x180014dcc  mov     [rbp+57h+var_20], 0
0x180014dd4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180014dd9  jmp     short loc_180014E52
0x180014ddb  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014de0  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180014de5  mov     rdi, rax
0x180014de8  mov     ecx, [rax]
0x180014dea  cmp     ecx, 5
0x180014ded  jbe     short loc_180014E52
0x180014def  mov     rdx, 200000000000h
0x180014df9  mov     rcx, rax
0x180014dfc  call    _tlgKeywordOn
0x180014e01  test    al, al
0x180014e03  jz      short loc_180014E52
0x180014e05  call    cs:__imp_GetCurrentThreadId
0x180014e0b  mov     r8, [rbx+110h]
0x180014e12  lea     rdx, unk_180022230
0x180014e19  mov     [rbp+57h+arg_0], eax
0x180014e1c  mov     rcx, rdi
0x180014e1f  mov     eax, [r8+48h]
0x180014e23  add     r8, 8
0x180014e27  mov     [rbp+57h+arg_8], eax
0x180014e2a  lea     rax, [rbp+57h+arg_0]
0x180014e2e  mov     [rsp+110h+var_E0], rax
0x180014e33  lea     rax, [rbp+57h+arg_8]
0x180014e37  mov     [rsp+110h+var_E8], rax
0x180014e3c  lea     rax, [rbp+57h+arg_10]
0x180014e40  mov     [rsp+110h+var_F0], rax
0x180014e45  mov     [rbp+57h+arg_10], 0
0x180014e4d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014e52  mov     rcx, rbx
0x180014e55  add     rsp, 100h
0x180014e5c  pop     rdi
0x180014e5d  pop     rbx
0x180014e5e  pop     rbp
0x180014e5f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
