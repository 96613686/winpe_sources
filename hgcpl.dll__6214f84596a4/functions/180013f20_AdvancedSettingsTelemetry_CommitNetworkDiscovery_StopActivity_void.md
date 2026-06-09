# AdvancedSettingsTelemetry::CommitNetworkDiscovery::StopActivity(void)

- ea: `0x180013f20`
- end: `0x180014144`
- name: `?StopActivity@CommitNetworkDiscovery@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitNetworkDiscovery *__hidden this)`
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
- `0x180013f20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800140e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800140e5`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitNetworkDiscovery::StopActivity(
        AdvancedSettingsTelemetry::CommitNetworkDiscovery *this)
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
        (unsigned int)&byte_180022B4F,
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
        (unsigned int)&word_180021FAE,
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
0x180013f20  push    rbp
0x180013f22  push    rbx
0x180013f23  push    rdi
0x180013f24  lea     rbp, [rsp-47h]
0x180013f29  sub     rsp, 100h
0x180013f30  mov     rdi, [rcx+110h]
0x180013f37  mov     rbx, rcx
0x180013f3a  mov     eax, [rdi+48h]
0x180013f3d  test    eax, eax
0x180013f3f  jns     loc_1800140BB
0x180013f45  add     rdi, 50h ; 'P'
0x180013f49  cmp     eax, [rdi+8]
0x180013f4c  jnz     loc_1800140BB
0x180013f52  test    rdi, rdi
0x180013f55  jz      loc_1800140BB
0x180013f5b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180013f60  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180013f65  mov     r9, rax
0x180013f68  mov     ecx, [rax]
0x180013f6a  cmp     ecx, 5
0x180013f6d  jbe     loc_180014132
0x180013f73  mov     rdx, 200000000000h
0x180013f7d  mov     rcx, rax
0x180013f80  call    _tlgKeywordOn
0x180013f85  test    al, al
0x180013f87  jz      loc_180014132
0x180013f8d  mov     rax, [rdi+70h]
0x180013f91  lea     rdx, byte_180022B4F
0x180013f98  mov     rcx, [rdi+78h]
0x180013f9c  mov     r8, [rbx+110h]
0x180013fa3  mov     [rbp+57h+var_60], rax
0x180013fa7  add     r8, 8
0x180013fab  mov     eax, [rdi+68h]
0x180013fae  mov     [rbp+57h+arg_0], eax
0x180013fb1  mov     rax, [rdi+60h]
0x180013fb5  mov     [rbp+57h+var_58], rax
0x180013fb9  mov     rax, [rdi+58h]
0x180013fbd  mov     [rbp+57h+var_50], rax
0x180013fc1  mov     eax, [rdi+50h]
0x180013fc4  mov     [rbp+57h+arg_8], eax
0x180013fc7  mov     rax, [rdi+48h]
0x180013fcb  mov     [rbp+57h+var_48], rax
0x180013fcf  mov     eax, [rdi+20h]
0x180013fd2  mov     dword ptr [rbp+57h+arg_10], eax
0x180013fd5  mov     rax, [rdi+18h]
0x180013fd9  mov     [rbp+57h+var_40], rax
0x180013fdd  mov     eax, [rdi]
0x180013fdf  mov     [rbp+57h+arg_18], eax
0x180013fe2  mov     rax, [rdi+80h]
0x180013fe9  mov     [rbp+57h+var_38], rax
0x180013fed  mov     eax, [rdi+40h]
0x180013ff0  mov     [rbp+57h+var_70], eax
0x180013ff3  mov     rax, [rdi+38h]
0x180013ff7  mov     [rbp+57h+var_30], rax
0x180013ffb  mov     eax, [rdi+8]
0x180013ffe  mov     [rbp+57h+var_6C], eax
0x180014001  lea     rax, [rbp+57h+var_68]
0x180014005  mov     [rsp+110h+var_78], rax
0x18001400d  lea     rax, [rbp+57h+var_60]
0x180014011  mov     [rsp+110h+var_80], rax
0x180014019  lea     rax, [rbp+57h+arg_0]
0x18001401d  mov     [rsp+110h+var_88], rax
0x180014025  lea     rax, [rbp+57h+var_58]
0x180014029  mov     [rsp+110h+var_90], rax
0x180014031  lea     rax, [rbp+57h+var_50]
0x180014035  mov     [rsp+110h+var_98], rax
0x18001403a  lea     rax, [rbp+57h+arg_8]
0x18001403e  mov     [rsp+110h+var_A0], rax
0x180014043  lea     rax, [rbp+57h+var_48]
0x180014047  mov     [rsp+110h+var_A8], rax
0x18001404c  lea     rax, [rbp+57h+arg_10]
0x180014050  mov     [rsp+110h+var_B0], rax
0x180014055  lea     rax, [rbp+57h+var_40]
0x180014059  mov     [rsp+110h+var_B8], rax
0x18001405e  lea     rax, [rbp+57h+arg_18]
0x180014062  mov     [rsp+110h+var_C0], rax
0x180014067  lea     rax, [rbp+57h+var_38]
0x18001406b  mov     [rsp+110h+var_C8], rax
0x180014070  lea     rax, [rbp+57h+var_70]
0x180014074  mov     [rsp+110h+var_D0], rax
0x180014079  lea     rax, [rbp+57h+var_30]
0x18001407d  mov     [rsp+110h+var_D8], rax
0x180014082  lea     rax, [rbp+57h+var_6C]
0x180014086  mov     [rsp+110h+var_E0], rax
0x18001408b  lea     rax, [rbp+57h+var_28]
0x18001408f  mov     [rsp+110h+var_E8], rax
0x180014094  lea     rax, [rbp+57h+var_20]
0x180014098  mov     [rbp+57h+var_68], rcx
0x18001409c  mov     rcx, r9
0x18001409f  mov     [rsp+110h+var_F0], rax
0x1800140a4  mov     [rbp+57h+var_28], 1000000h
0x1800140ac  mov     [rbp+57h+var_20], 0
0x1800140b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800140b9  jmp     short loc_180014132
0x1800140bb  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800140c0  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x1800140c5  mov     rdi, rax
0x1800140c8  mov     ecx, [rax]
0x1800140ca  cmp     ecx, 5
0x1800140cd  jbe     short loc_180014132
0x1800140cf  mov     rdx, 200000000000h
0x1800140d9  mov     rcx, rax
0x1800140dc  call    _tlgKeywordOn
0x1800140e1  test    al, al
0x1800140e3  jz      short loc_180014132
0x1800140e5  call    cs:__imp_GetCurrentThreadId
0x1800140eb  mov     r8, [rbx+110h]
0x1800140f2  lea     rdx, word_180021FAE
0x1800140f9  mov     [rbp+57h+arg_0], eax
0x1800140fc  mov     rcx, rdi
0x1800140ff  mov     eax, [r8+48h]
0x180014103  add     r8, 8
0x180014107  mov     [rbp+57h+arg_8], eax
0x18001410a  lea     rax, [rbp+57h+arg_0]
0x18001410e  mov     [rsp+110h+var_E0], rax
0x180014113  lea     rax, [rbp+57h+arg_8]
0x180014117  mov     [rsp+110h+var_E8], rax
0x18001411c  lea     rax, [rbp+57h+arg_10]
0x180014120  mov     [rsp+110h+var_F0], rax
0x180014125  mov     [rbp+57h+arg_10], 0
0x18001412d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014132  mov     rcx, rbx
0x180014135  add     rsp, 100h
0x18001413c  pop     rdi
0x18001413d  pop     rbx
0x18001413e  pop     rbp
0x18001413f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
