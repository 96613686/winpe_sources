# AdvancedSettingsTelemetry::CommitFileSharing::StopActivity(void)

- ea: `0x180013cf0`
- end: `0x180013f14`
- name: `?StopActivity@CommitFileSharing@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitFileSharing *__hidden this)`
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
- `0x180013cf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013eb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013eb5`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitFileSharing::StopActivity(
        AdvancedSettingsTelemetry::CommitFileSharing *this)
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
        (unsigned int)&byte_18002298F,
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
        (unsigned int)&word_1800221DE,
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
0x180013cf0  push    rbp
0x180013cf2  push    rbx
0x180013cf3  push    rdi
0x180013cf4  lea     rbp, [rsp-47h]
0x180013cf9  sub     rsp, 100h
0x180013d00  mov     rdi, [rcx+110h]
0x180013d07  mov     rbx, rcx
0x180013d0a  mov     eax, [rdi+48h]
0x180013d0d  test    eax, eax
0x180013d0f  jns     loc_180013E8B
0x180013d15  add     rdi, 50h ; 'P'
0x180013d19  cmp     eax, [rdi+8]
0x180013d1c  jnz     loc_180013E8B
0x180013d22  test    rdi, rdi
0x180013d25  jz      loc_180013E8B
0x180013d2b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180013d30  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180013d35  mov     r9, rax
0x180013d38  mov     ecx, [rax]
0x180013d3a  cmp     ecx, 5
0x180013d3d  jbe     loc_180013F02
0x180013d43  mov     rdx, 200000000000h
0x180013d4d  mov     rcx, rax
0x180013d50  call    _tlgKeywordOn
0x180013d55  test    al, al
0x180013d57  jz      loc_180013F02
0x180013d5d  mov     rax, [rdi+70h]
0x180013d61  lea     rdx, byte_18002298F
0x180013d68  mov     rcx, [rdi+78h]
0x180013d6c  mov     r8, [rbx+110h]
0x180013d73  mov     [rbp+57h+var_60], rax
0x180013d77  add     r8, 8
0x180013d7b  mov     eax, [rdi+68h]
0x180013d7e  mov     [rbp+57h+arg_0], eax
0x180013d81  mov     rax, [rdi+60h]
0x180013d85  mov     [rbp+57h+var_58], rax
0x180013d89  mov     rax, [rdi+58h]
0x180013d8d  mov     [rbp+57h+var_50], rax
0x180013d91  mov     eax, [rdi+50h]
0x180013d94  mov     [rbp+57h+arg_8], eax
0x180013d97  mov     rax, [rdi+48h]
0x180013d9b  mov     [rbp+57h+var_48], rax
0x180013d9f  mov     eax, [rdi+20h]
0x180013da2  mov     dword ptr [rbp+57h+arg_10], eax
0x180013da5  mov     rax, [rdi+18h]
0x180013da9  mov     [rbp+57h+var_40], rax
0x180013dad  mov     eax, [rdi]
0x180013daf  mov     [rbp+57h+arg_18], eax
0x180013db2  mov     rax, [rdi+80h]
0x180013db9  mov     [rbp+57h+var_38], rax
0x180013dbd  mov     eax, [rdi+40h]
0x180013dc0  mov     [rbp+57h+var_70], eax
0x180013dc3  mov     rax, [rdi+38h]
0x180013dc7  mov     [rbp+57h+var_30], rax
0x180013dcb  mov     eax, [rdi+8]
0x180013dce  mov     [rbp+57h+var_6C], eax
0x180013dd1  lea     rax, [rbp+57h+var_68]
0x180013dd5  mov     [rsp+110h+var_78], rax
0x180013ddd  lea     rax, [rbp+57h+var_60]
0x180013de1  mov     [rsp+110h+var_80], rax
0x180013de9  lea     rax, [rbp+57h+arg_0]
0x180013ded  mov     [rsp+110h+var_88], rax
0x180013df5  lea     rax, [rbp+57h+var_58]
0x180013df9  mov     [rsp+110h+var_90], rax
0x180013e01  lea     rax, [rbp+57h+var_50]
0x180013e05  mov     [rsp+110h+var_98], rax
0x180013e0a  lea     rax, [rbp+57h+arg_8]
0x180013e0e  mov     [rsp+110h+var_A0], rax
0x180013e13  lea     rax, [rbp+57h+var_48]
0x180013e17  mov     [rsp+110h+var_A8], rax
0x180013e1c  lea     rax, [rbp+57h+arg_10]
0x180013e20  mov     [rsp+110h+var_B0], rax
0x180013e25  lea     rax, [rbp+57h+var_40]
0x180013e29  mov     [rsp+110h+var_B8], rax
0x180013e2e  lea     rax, [rbp+57h+arg_18]
0x180013e32  mov     [rsp+110h+var_C0], rax
0x180013e37  lea     rax, [rbp+57h+var_38]
0x180013e3b  mov     [rsp+110h+var_C8], rax
0x180013e40  lea     rax, [rbp+57h+var_70]
0x180013e44  mov     [rsp+110h+var_D0], rax
0x180013e49  lea     rax, [rbp+57h+var_30]
0x180013e4d  mov     [rsp+110h+var_D8], rax
0x180013e52  lea     rax, [rbp+57h+var_6C]
0x180013e56  mov     [rsp+110h+var_E0], rax
0x180013e5b  lea     rax, [rbp+57h+var_28]
0x180013e5f  mov     [rsp+110h+var_E8], rax
0x180013e64  lea     rax, [rbp+57h+var_20]
0x180013e68  mov     [rbp+57h+var_68], rcx
0x180013e6c  mov     rcx, r9
0x180013e6f  mov     [rsp+110h+var_F0], rax
0x180013e74  mov     [rbp+57h+var_28], 1000000h
0x180013e7c  mov     [rbp+57h+var_20], 0
0x180013e84  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180013e89  jmp     short loc_180013F02
0x180013e8b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180013e90  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180013e95  mov     rdi, rax
0x180013e98  mov     ecx, [rax]
0x180013e9a  cmp     ecx, 5
0x180013e9d  jbe     short loc_180013F02
0x180013e9f  mov     rdx, 200000000000h
0x180013ea9  mov     rcx, rax
0x180013eac  call    _tlgKeywordOn
0x180013eb1  test    al, al
0x180013eb3  jz      short loc_180013F02
0x180013eb5  call    cs:__imp_GetCurrentThreadId
0x180013ebb  mov     r8, [rbx+110h]
0x180013ec2  lea     rdx, word_1800221DE
0x180013ec9  mov     [rbp+57h+arg_0], eax
0x180013ecc  mov     rcx, rdi
0x180013ecf  mov     eax, [r8+48h]
0x180013ed3  add     r8, 8
0x180013ed7  mov     [rbp+57h+arg_8], eax
0x180013eda  lea     rax, [rbp+57h+arg_0]
0x180013ede  mov     [rsp+110h+var_E0], rax
0x180013ee3  lea     rax, [rbp+57h+arg_8]
0x180013ee7  mov     [rsp+110h+var_E8], rax
0x180013eec  lea     rax, [rbp+57h+arg_10]
0x180013ef0  mov     [rsp+110h+var_F0], rax
0x180013ef5  mov     [rbp+57h+arg_10], 0
0x180013efd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013f02  mov     rcx, rbx
0x180013f05  add     rsp, 100h
0x180013f0c  pop     rdi
0x180013f0d  pop     rbx
0x180013f0e  pop     rbp
0x180013f0f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
