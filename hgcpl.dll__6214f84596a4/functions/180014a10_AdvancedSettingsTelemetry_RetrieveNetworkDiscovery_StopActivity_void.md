# AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::StopActivity(void)

- ea: `0x180014a10`
- end: `0x180014c34`
- name: `?StopActivity@RetrieveNetworkDiscovery@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::RetrieveNetworkDiscovery *__hidden this)`
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
- `0x180014a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014bd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014bd5`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::StopActivity(
        AdvancedSettingsTelemetry::RetrieveNetworkDiscovery *this)
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
        (unsigned int)&word_18002205E,
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
        (unsigned int)byte_180022005,
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
0x180014a10  push    rbp
0x180014a12  push    rbx
0x180014a13  push    rdi
0x180014a14  lea     rbp, [rsp-47h]
0x180014a19  sub     rsp, 100h
0x180014a20  mov     rdi, [rcx+110h]
0x180014a27  mov     rbx, rcx
0x180014a2a  mov     eax, [rdi+48h]
0x180014a2d  test    eax, eax
0x180014a2f  jns     loc_180014BAB
0x180014a35  add     rdi, 50h ; 'P'
0x180014a39  cmp     eax, [rdi+8]
0x180014a3c  jnz     loc_180014BAB
0x180014a42  test    rdi, rdi
0x180014a45  jz      loc_180014BAB
0x180014a4b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014a50  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180014a55  mov     r9, rax
0x180014a58  mov     ecx, [rax]
0x180014a5a  cmp     ecx, 5
0x180014a5d  jbe     loc_180014C22
0x180014a63  mov     rdx, 200000000000h
0x180014a6d  mov     rcx, rax
0x180014a70  call    _tlgKeywordOn
0x180014a75  test    al, al
0x180014a77  jz      loc_180014C22
0x180014a7d  mov     rax, [rdi+70h]
0x180014a81  lea     rdx, word_18002205E
0x180014a88  mov     rcx, [rdi+78h]
0x180014a8c  mov     r8, [rbx+110h]
0x180014a93  mov     [rbp+57h+var_60], rax
0x180014a97  add     r8, 8
0x180014a9b  mov     eax, [rdi+68h]
0x180014a9e  mov     [rbp+57h+arg_0], eax
0x180014aa1  mov     rax, [rdi+60h]
0x180014aa5  mov     [rbp+57h+var_58], rax
0x180014aa9  mov     rax, [rdi+58h]
0x180014aad  mov     [rbp+57h+var_50], rax
0x180014ab1  mov     eax, [rdi+50h]
0x180014ab4  mov     [rbp+57h+arg_8], eax
0x180014ab7  mov     rax, [rdi+48h]
0x180014abb  mov     [rbp+57h+var_48], rax
0x180014abf  mov     eax, [rdi+20h]
0x180014ac2  mov     dword ptr [rbp+57h+arg_10], eax
0x180014ac5  mov     rax, [rdi+18h]
0x180014ac9  mov     [rbp+57h+var_40], rax
0x180014acd  mov     eax, [rdi]
0x180014acf  mov     [rbp+57h+arg_18], eax
0x180014ad2  mov     rax, [rdi+80h]
0x180014ad9  mov     [rbp+57h+var_38], rax
0x180014add  mov     eax, [rdi+40h]
0x180014ae0  mov     [rbp+57h+var_70], eax
0x180014ae3  mov     rax, [rdi+38h]
0x180014ae7  mov     [rbp+57h+var_30], rax
0x180014aeb  mov     eax, [rdi+8]
0x180014aee  mov     [rbp+57h+var_6C], eax
0x180014af1  lea     rax, [rbp+57h+var_68]
0x180014af5  mov     [rsp+110h+var_78], rax
0x180014afd  lea     rax, [rbp+57h+var_60]
0x180014b01  mov     [rsp+110h+var_80], rax
0x180014b09  lea     rax, [rbp+57h+arg_0]
0x180014b0d  mov     [rsp+110h+var_88], rax
0x180014b15  lea     rax, [rbp+57h+var_58]
0x180014b19  mov     [rsp+110h+var_90], rax
0x180014b21  lea     rax, [rbp+57h+var_50]
0x180014b25  mov     [rsp+110h+var_98], rax
0x180014b2a  lea     rax, [rbp+57h+arg_8]
0x180014b2e  mov     [rsp+110h+var_A0], rax
0x180014b33  lea     rax, [rbp+57h+var_48]
0x180014b37  mov     [rsp+110h+var_A8], rax
0x180014b3c  lea     rax, [rbp+57h+arg_10]
0x180014b40  mov     [rsp+110h+var_B0], rax
0x180014b45  lea     rax, [rbp+57h+var_40]
0x180014b49  mov     [rsp+110h+var_B8], rax
0x180014b4e  lea     rax, [rbp+57h+arg_18]
0x180014b52  mov     [rsp+110h+var_C0], rax
0x180014b57  lea     rax, [rbp+57h+var_38]
0x180014b5b  mov     [rsp+110h+var_C8], rax
0x180014b60  lea     rax, [rbp+57h+var_70]
0x180014b64  mov     [rsp+110h+var_D0], rax
0x180014b69  lea     rax, [rbp+57h+var_30]
0x180014b6d  mov     [rsp+110h+var_D8], rax
0x180014b72  lea     rax, [rbp+57h+var_6C]
0x180014b76  mov     [rsp+110h+var_E0], rax
0x180014b7b  lea     rax, [rbp+57h+var_28]
0x180014b7f  mov     [rsp+110h+var_E8], rax
0x180014b84  lea     rax, [rbp+57h+var_20]
0x180014b88  mov     [rbp+57h+var_68], rcx
0x180014b8c  mov     rcx, r9
0x180014b8f  mov     [rsp+110h+var_F0], rax
0x180014b94  mov     [rbp+57h+var_28], 1000000h
0x180014b9c  mov     [rbp+57h+var_20], 0
0x180014ba4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180014ba9  jmp     short loc_180014C22
0x180014bab  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014bb0  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180014bb5  mov     rdi, rax
0x180014bb8  mov     ecx, [rax]
0x180014bba  cmp     ecx, 5
0x180014bbd  jbe     short loc_180014C22
0x180014bbf  mov     rdx, 200000000000h
0x180014bc9  mov     rcx, rax
0x180014bcc  call    _tlgKeywordOn
0x180014bd1  test    al, al
0x180014bd3  jz      short loc_180014C22
0x180014bd5  call    cs:__imp_GetCurrentThreadId
0x180014bdb  mov     r8, [rbx+110h]
0x180014be2  lea     rdx, byte_180022005
0x180014be9  mov     [rbp+57h+arg_0], eax
0x180014bec  mov     rcx, rdi
0x180014bef  mov     eax, [r8+48h]
0x180014bf3  add     r8, 8
0x180014bf7  mov     [rbp+57h+arg_8], eax
0x180014bfa  lea     rax, [rbp+57h+arg_0]
0x180014bfe  mov     [rsp+110h+var_E0], rax
0x180014c03  lea     rax, [rbp+57h+arg_8]
0x180014c07  mov     [rsp+110h+var_E8], rax
0x180014c0c  lea     rax, [rbp+57h+arg_10]
0x180014c10  mov     [rsp+110h+var_F0], rax
0x180014c15  mov     [rbp+57h+arg_10], 0
0x180014c1d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014c22  mov     rcx, rbx
0x180014c25  add     rsp, 100h
0x180014c2c  pop     rdi
0x180014c2d  pop     rbx
0x180014c2e  pop     rbp
0x180014c2f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
