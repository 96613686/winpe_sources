# AdvancedSettingsTelemetry::CommitSettings::StopActivity(void)

- ea: `0x180009190`
- end: `0x1800093b4`
- name: `?StopActivity@CommitSettings@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitSettings *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800010f8`
- `0x18000141c`
- `0x180001bac`
- `0x180007698`
- `0x18000845c`
- `0x180009190`
- `0x18000b154`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009355`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitSettings::StopActivity(
        AdvancedSettingsTelemetry::CommitSettings *this)
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
        (unsigned int)byte_180021473,
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
        (unsigned int)&dword_180021424,
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
0x180009190  push    rbp
0x180009192  push    rbx
0x180009193  push    rdi
0x180009194  lea     rbp, [rsp-47h]
0x180009199  sub     rsp, 100h
0x1800091a0  mov     rdi, [rcx+110h]
0x1800091a7  mov     rbx, rcx
0x1800091aa  mov     eax, [rdi+48h]
0x1800091ad  test    eax, eax
0x1800091af  jns     loc_18000932B
0x1800091b5  add     rdi, 50h ; 'P'
0x1800091b9  cmp     eax, [rdi+8]
0x1800091bc  jnz     loc_18000932B
0x1800091c2  test    rdi, rdi
0x1800091c5  jz      loc_18000932B
0x1800091cb  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800091d0  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x1800091d5  mov     r9, rax
0x1800091d8  mov     ecx, [rax]
0x1800091da  cmp     ecx, 5
0x1800091dd  jbe     loc_1800093A2
0x1800091e3  mov     rdx, 200000000000h
0x1800091ed  mov     rcx, rax
0x1800091f0  call    _tlgKeywordOn
0x1800091f5  test    al, al
0x1800091f7  jz      loc_1800093A2
0x1800091fd  mov     rax, [rdi+70h]
0x180009201  lea     rdx, byte_180021473
0x180009208  mov     rcx, [rdi+78h]
0x18000920c  mov     r8, [rbx+110h]
0x180009213  mov     [rbp+57h+var_60], rax
0x180009217  add     r8, 8
0x18000921b  mov     eax, [rdi+68h]
0x18000921e  mov     [rbp+57h+arg_0], eax
0x180009221  mov     rax, [rdi+60h]
0x180009225  mov     [rbp+57h+var_58], rax
0x180009229  mov     rax, [rdi+58h]
0x18000922d  mov     [rbp+57h+var_50], rax
0x180009231  mov     eax, [rdi+50h]
0x180009234  mov     [rbp+57h+arg_8], eax
0x180009237  mov     rax, [rdi+48h]
0x18000923b  mov     [rbp+57h+var_48], rax
0x18000923f  mov     eax, [rdi+20h]
0x180009242  mov     dword ptr [rbp+57h+arg_10], eax
0x180009245  mov     rax, [rdi+18h]
0x180009249  mov     [rbp+57h+var_40], rax
0x18000924d  mov     eax, [rdi]
0x18000924f  mov     [rbp+57h+arg_18], eax
0x180009252  mov     rax, [rdi+80h]
0x180009259  mov     [rbp+57h+var_38], rax
0x18000925d  mov     eax, [rdi+40h]
0x180009260  mov     [rbp+57h+var_70], eax
0x180009263  mov     rax, [rdi+38h]
0x180009267  mov     [rbp+57h+var_30], rax
0x18000926b  mov     eax, [rdi+8]
0x18000926e  mov     [rbp+57h+var_6C], eax
0x180009271  lea     rax, [rbp+57h+var_68]
0x180009275  mov     [rsp+110h+var_78], rax
0x18000927d  lea     rax, [rbp+57h+var_60]
0x180009281  mov     [rsp+110h+var_80], rax
0x180009289  lea     rax, [rbp+57h+arg_0]
0x18000928d  mov     [rsp+110h+var_88], rax
0x180009295  lea     rax, [rbp+57h+var_58]
0x180009299  mov     [rsp+110h+var_90], rax
0x1800092a1  lea     rax, [rbp+57h+var_50]
0x1800092a5  mov     [rsp+110h+var_98], rax
0x1800092aa  lea     rax, [rbp+57h+arg_8]
0x1800092ae  mov     [rsp+110h+var_A0], rax
0x1800092b3  lea     rax, [rbp+57h+var_48]
0x1800092b7  mov     [rsp+110h+var_A8], rax
0x1800092bc  lea     rax, [rbp+57h+arg_10]
0x1800092c0  mov     [rsp+110h+var_B0], rax
0x1800092c5  lea     rax, [rbp+57h+var_40]
0x1800092c9  mov     [rsp+110h+var_B8], rax
0x1800092ce  lea     rax, [rbp+57h+arg_18]
0x1800092d2  mov     [rsp+110h+var_C0], rax
0x1800092d7  lea     rax, [rbp+57h+var_38]
0x1800092db  mov     [rsp+110h+var_C8], rax
0x1800092e0  lea     rax, [rbp+57h+var_70]
0x1800092e4  mov     [rsp+110h+var_D0], rax
0x1800092e9  lea     rax, [rbp+57h+var_30]
0x1800092ed  mov     [rsp+110h+var_D8], rax
0x1800092f2  lea     rax, [rbp+57h+var_6C]
0x1800092f6  mov     [rsp+110h+var_E0], rax
0x1800092fb  lea     rax, [rbp+57h+var_28]
0x1800092ff  mov     [rsp+110h+var_E8], rax
0x180009304  lea     rax, [rbp+57h+var_20]
0x180009308  mov     [rbp+57h+var_68], rcx
0x18000930c  mov     rcx, r9
0x18000930f  mov     [rsp+110h+var_F0], rax
0x180009314  mov     [rbp+57h+var_28], 1000000h
0x18000931c  mov     [rbp+57h+var_20], 0
0x180009324  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180009329  jmp     short loc_1800093A2
0x18000932b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180009330  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180009335  mov     rdi, rax
0x180009338  mov     ecx, [rax]
0x18000933a  cmp     ecx, 5
0x18000933d  jbe     short loc_1800093A2
0x18000933f  mov     rdx, 200000000000h
0x180009349  mov     rcx, rax
0x18000934c  call    _tlgKeywordOn
0x180009351  test    al, al
0x180009353  jz      short loc_1800093A2
0x180009355  call    cs:__imp_GetCurrentThreadId
0x18000935b  mov     r8, [rbx+110h]
0x180009362  lea     rdx, dword_180021424
0x180009369  mov     [rbp+57h+arg_0], eax
0x18000936c  mov     rcx, rdi
0x18000936f  mov     eax, [r8+48h]
0x180009373  add     r8, 8
0x180009377  mov     [rbp+57h+arg_8], eax
0x18000937a  lea     rax, [rbp+57h+arg_0]
0x18000937e  mov     [rsp+110h+var_E0], rax
0x180009383  lea     rax, [rbp+57h+arg_8]
0x180009387  mov     [rsp+110h+var_E8], rax
0x18000938c  lea     rax, [rbp+57h+arg_10]
0x180009390  mov     [rsp+110h+var_F0], rax
0x180009395  mov     [rbp+57h+arg_10], 0
0x18000939d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800093a2  mov     rcx, rbx
0x1800093a5  add     rsp, 100h
0x1800093ac  pop     rdi
0x1800093ad  pop     rbx
0x1800093ae  pop     rbp
0x1800093af  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
