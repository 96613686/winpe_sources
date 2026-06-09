# AdvancedSettingsTelemetry::RetrieveSettings::StopActivity(void)

- ea: `0x180009820`
- end: `0x180009a44`
- name: `?StopActivity@RetrieveSettings@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::RetrieveSettings *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800010f8`
- `0x18000141c`
- `0x180001bac`
- `0x180007698`
- `0x18000845c`
- `0x180009820`
- `0x18000b154`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800099e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800099e5`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::RetrieveSettings::StopActivity(
        AdvancedSettingsTelemetry::RetrieveSettings *this)
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
        (unsigned int)&word_1800212B6,
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
        (unsigned int)byte_180021265,
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
0x180009820  push    rbp
0x180009822  push    rbx
0x180009823  push    rdi
0x180009824  lea     rbp, [rsp-47h]
0x180009829  sub     rsp, 100h
0x180009830  mov     rdi, [rcx+110h]
0x180009837  mov     rbx, rcx
0x18000983a  mov     eax, [rdi+48h]
0x18000983d  test    eax, eax
0x18000983f  jns     loc_1800099BB
0x180009845  add     rdi, 50h ; 'P'
0x180009849  cmp     eax, [rdi+8]
0x18000984c  jnz     loc_1800099BB
0x180009852  test    rdi, rdi
0x180009855  jz      loc_1800099BB
0x18000985b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180009860  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180009865  mov     r9, rax
0x180009868  mov     ecx, [rax]
0x18000986a  cmp     ecx, 5
0x18000986d  jbe     loc_180009A32
0x180009873  mov     rdx, 200000000000h
0x18000987d  mov     rcx, rax
0x180009880  call    _tlgKeywordOn
0x180009885  test    al, al
0x180009887  jz      loc_180009A32
0x18000988d  mov     rax, [rdi+70h]
0x180009891  lea     rdx, word_1800212B6
0x180009898  mov     rcx, [rdi+78h]
0x18000989c  mov     r8, [rbx+110h]
0x1800098a3  mov     [rbp+57h+var_60], rax
0x1800098a7  add     r8, 8
0x1800098ab  mov     eax, [rdi+68h]
0x1800098ae  mov     [rbp+57h+arg_0], eax
0x1800098b1  mov     rax, [rdi+60h]
0x1800098b5  mov     [rbp+57h+var_58], rax
0x1800098b9  mov     rax, [rdi+58h]
0x1800098bd  mov     [rbp+57h+var_50], rax
0x1800098c1  mov     eax, [rdi+50h]
0x1800098c4  mov     [rbp+57h+arg_8], eax
0x1800098c7  mov     rax, [rdi+48h]
0x1800098cb  mov     [rbp+57h+var_48], rax
0x1800098cf  mov     eax, [rdi+20h]
0x1800098d2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800098d5  mov     rax, [rdi+18h]
0x1800098d9  mov     [rbp+57h+var_40], rax
0x1800098dd  mov     eax, [rdi]
0x1800098df  mov     [rbp+57h+arg_18], eax
0x1800098e2  mov     rax, [rdi+80h]
0x1800098e9  mov     [rbp+57h+var_38], rax
0x1800098ed  mov     eax, [rdi+40h]
0x1800098f0  mov     [rbp+57h+var_70], eax
0x1800098f3  mov     rax, [rdi+38h]
0x1800098f7  mov     [rbp+57h+var_30], rax
0x1800098fb  mov     eax, [rdi+8]
0x1800098fe  mov     [rbp+57h+var_6C], eax
0x180009901  lea     rax, [rbp+57h+var_68]
0x180009905  mov     [rsp+110h+var_78], rax
0x18000990d  lea     rax, [rbp+57h+var_60]
0x180009911  mov     [rsp+110h+var_80], rax
0x180009919  lea     rax, [rbp+57h+arg_0]
0x18000991d  mov     [rsp+110h+var_88], rax
0x180009925  lea     rax, [rbp+57h+var_58]
0x180009929  mov     [rsp+110h+var_90], rax
0x180009931  lea     rax, [rbp+57h+var_50]
0x180009935  mov     [rsp+110h+var_98], rax
0x18000993a  lea     rax, [rbp+57h+arg_8]
0x18000993e  mov     [rsp+110h+var_A0], rax
0x180009943  lea     rax, [rbp+57h+var_48]
0x180009947  mov     [rsp+110h+var_A8], rax
0x18000994c  lea     rax, [rbp+57h+arg_10]
0x180009950  mov     [rsp+110h+var_B0], rax
0x180009955  lea     rax, [rbp+57h+var_40]
0x180009959  mov     [rsp+110h+var_B8], rax
0x18000995e  lea     rax, [rbp+57h+arg_18]
0x180009962  mov     [rsp+110h+var_C0], rax
0x180009967  lea     rax, [rbp+57h+var_38]
0x18000996b  mov     [rsp+110h+var_C8], rax
0x180009970  lea     rax, [rbp+57h+var_70]
0x180009974  mov     [rsp+110h+var_D0], rax
0x180009979  lea     rax, [rbp+57h+var_30]
0x18000997d  mov     [rsp+110h+var_D8], rax
0x180009982  lea     rax, [rbp+57h+var_6C]
0x180009986  mov     [rsp+110h+var_E0], rax
0x18000998b  lea     rax, [rbp+57h+var_28]
0x18000998f  mov     [rsp+110h+var_E8], rax
0x180009994  lea     rax, [rbp+57h+var_20]
0x180009998  mov     [rbp+57h+var_68], rcx
0x18000999c  mov     rcx, r9
0x18000999f  mov     [rsp+110h+var_F0], rax
0x1800099a4  mov     [rbp+57h+var_28], 1000000h
0x1800099ac  mov     [rbp+57h+var_20], 0
0x1800099b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800099b9  jmp     short loc_180009A32
0x1800099bb  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800099c0  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x1800099c5  mov     rdi, rax
0x1800099c8  mov     ecx, [rax]
0x1800099ca  cmp     ecx, 5
0x1800099cd  jbe     short loc_180009A32
0x1800099cf  mov     rdx, 200000000000h
0x1800099d9  mov     rcx, rax
0x1800099dc  call    _tlgKeywordOn
0x1800099e1  test    al, al
0x1800099e3  jz      short loc_180009A32
0x1800099e5  call    cs:__imp_GetCurrentThreadId
0x1800099eb  mov     r8, [rbx+110h]
0x1800099f2  lea     rdx, byte_180021265
0x1800099f9  mov     [rbp+57h+arg_0], eax
0x1800099fc  mov     rcx, rdi
0x1800099ff  mov     eax, [r8+48h]
0x180009a03  add     r8, 8
0x180009a07  mov     [rbp+57h+arg_8], eax
0x180009a0a  lea     rax, [rbp+57h+arg_0]
0x180009a0e  mov     [rsp+110h+var_E0], rax
0x180009a13  lea     rax, [rbp+57h+arg_8]
0x180009a17  mov     [rsp+110h+var_E8], rax
0x180009a1c  lea     rax, [rbp+57h+arg_10]
0x180009a20  mov     [rsp+110h+var_F0], rax
0x180009a25  mov     [rbp+57h+arg_10], 0
0x180009a2d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009a32  mov     rcx, rbx
0x180009a35  add     rsp, 100h
0x180009a3c  pop     rdi
0x180009a3d  pop     rbx
0x180009a3e  pop     rbp
0x180009a3f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
