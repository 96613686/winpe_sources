# AdvancedSettingsTelemetry::PageInitialization::StopActivity(void)

- ea: `0x1800095f0`
- end: `0x180009814`
- name: `?StopActivity@PageInitialization@AdvancedSettingsTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::PageInitialization *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800010f8`
- `0x18000141c`
- `0x180001bac`
- `0x180007698`
- `0x18000845c`
- `0x1800095f0`
- `0x18000b154`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097b5`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::PageInitialization::StopActivity(
        AdvancedSettingsTelemetry::PageInitialization *this)
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
        (unsigned int)&word_180021636,
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
        (unsigned int)byte_1800215E3,
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
0x1800095f0  push    rbp
0x1800095f2  push    rbx
0x1800095f3  push    rdi
0x1800095f4  lea     rbp, [rsp-47h]
0x1800095f9  sub     rsp, 100h
0x180009600  mov     rdi, [rcx+110h]
0x180009607  mov     rbx, rcx
0x18000960a  mov     eax, [rdi+48h]
0x18000960d  test    eax, eax
0x18000960f  jns     loc_18000978B
0x180009615  add     rdi, 50h ; 'P'
0x180009619  cmp     eax, [rdi+8]
0x18000961c  jnz     loc_18000978B
0x180009622  test    rdi, rdi
0x180009625  jz      loc_18000978B
0x18000962b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180009630  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180009635  mov     r9, rax
0x180009638  mov     ecx, [rax]
0x18000963a  cmp     ecx, 5
0x18000963d  jbe     loc_180009802
0x180009643  mov     rdx, 200000000000h
0x18000964d  mov     rcx, rax
0x180009650  call    _tlgKeywordOn
0x180009655  test    al, al
0x180009657  jz      loc_180009802
0x18000965d  mov     rax, [rdi+70h]
0x180009661  lea     rdx, word_180021636
0x180009668  mov     rcx, [rdi+78h]
0x18000966c  mov     r8, [rbx+110h]
0x180009673  mov     [rbp+57h+var_60], rax
0x180009677  add     r8, 8
0x18000967b  mov     eax, [rdi+68h]
0x18000967e  mov     [rbp+57h+arg_0], eax
0x180009681  mov     rax, [rdi+60h]
0x180009685  mov     [rbp+57h+var_58], rax
0x180009689  mov     rax, [rdi+58h]
0x18000968d  mov     [rbp+57h+var_50], rax
0x180009691  mov     eax, [rdi+50h]
0x180009694  mov     [rbp+57h+arg_8], eax
0x180009697  mov     rax, [rdi+48h]
0x18000969b  mov     [rbp+57h+var_48], rax
0x18000969f  mov     eax, [rdi+20h]
0x1800096a2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800096a5  mov     rax, [rdi+18h]
0x1800096a9  mov     [rbp+57h+var_40], rax
0x1800096ad  mov     eax, [rdi]
0x1800096af  mov     [rbp+57h+arg_18], eax
0x1800096b2  mov     rax, [rdi+80h]
0x1800096b9  mov     [rbp+57h+var_38], rax
0x1800096bd  mov     eax, [rdi+40h]
0x1800096c0  mov     [rbp+57h+var_70], eax
0x1800096c3  mov     rax, [rdi+38h]
0x1800096c7  mov     [rbp+57h+var_30], rax
0x1800096cb  mov     eax, [rdi+8]
0x1800096ce  mov     [rbp+57h+var_6C], eax
0x1800096d1  lea     rax, [rbp+57h+var_68]
0x1800096d5  mov     [rsp+110h+var_78], rax
0x1800096dd  lea     rax, [rbp+57h+var_60]
0x1800096e1  mov     [rsp+110h+var_80], rax
0x1800096e9  lea     rax, [rbp+57h+arg_0]
0x1800096ed  mov     [rsp+110h+var_88], rax
0x1800096f5  lea     rax, [rbp+57h+var_58]
0x1800096f9  mov     [rsp+110h+var_90], rax
0x180009701  lea     rax, [rbp+57h+var_50]
0x180009705  mov     [rsp+110h+var_98], rax
0x18000970a  lea     rax, [rbp+57h+arg_8]
0x18000970e  mov     [rsp+110h+var_A0], rax
0x180009713  lea     rax, [rbp+57h+var_48]
0x180009717  mov     [rsp+110h+var_A8], rax
0x18000971c  lea     rax, [rbp+57h+arg_10]
0x180009720  mov     [rsp+110h+var_B0], rax
0x180009725  lea     rax, [rbp+57h+var_40]
0x180009729  mov     [rsp+110h+var_B8], rax
0x18000972e  lea     rax, [rbp+57h+arg_18]
0x180009732  mov     [rsp+110h+var_C0], rax
0x180009737  lea     rax, [rbp+57h+var_38]
0x18000973b  mov     [rsp+110h+var_C8], rax
0x180009740  lea     rax, [rbp+57h+var_70]
0x180009744  mov     [rsp+110h+var_D0], rax
0x180009749  lea     rax, [rbp+57h+var_30]
0x18000974d  mov     [rsp+110h+var_D8], rax
0x180009752  lea     rax, [rbp+57h+var_6C]
0x180009756  mov     [rsp+110h+var_E0], rax
0x18000975b  lea     rax, [rbp+57h+var_28]
0x18000975f  mov     [rsp+110h+var_E8], rax
0x180009764  lea     rax, [rbp+57h+var_20]
0x180009768  mov     [rbp+57h+var_68], rcx
0x18000976c  mov     rcx, r9
0x18000976f  mov     [rsp+110h+var_F0], rax
0x180009774  mov     [rbp+57h+var_28], 1000000h
0x18000977c  mov     [rbp+57h+var_20], 0
0x180009784  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180009789  jmp     short loc_180009802
0x18000978b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180009790  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180009795  mov     rdi, rax
0x180009798  mov     ecx, [rax]
0x18000979a  cmp     ecx, 5
0x18000979d  jbe     short loc_180009802
0x18000979f  mov     rdx, 200000000000h
0x1800097a9  mov     rcx, rax
0x1800097ac  call    _tlgKeywordOn
0x1800097b1  test    al, al
0x1800097b3  jz      short loc_180009802
0x1800097b5  call    cs:__imp_GetCurrentThreadId
0x1800097bb  mov     r8, [rbx+110h]
0x1800097c2  lea     rdx, byte_1800215E3
0x1800097c9  mov     [rbp+57h+arg_0], eax
0x1800097cc  mov     rcx, rdi
0x1800097cf  mov     eax, [r8+48h]
0x1800097d3  add     r8, 8
0x1800097d7  mov     [rbp+57h+arg_8], eax
0x1800097da  lea     rax, [rbp+57h+arg_0]
0x1800097de  mov     [rsp+110h+var_E0], rax
0x1800097e3  lea     rax, [rbp+57h+arg_8]
0x1800097e7  mov     [rsp+110h+var_E8], rax
0x1800097ec  lea     rax, [rbp+57h+arg_10]
0x1800097f0  mov     [rsp+110h+var_F0], rax
0x1800097f5  mov     [rbp+57h+arg_10], 0
0x1800097fd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009802  mov     rcx, rbx
0x180009805  add     rsp, 100h
0x18000980c  pop     rdi
0x18000980d  pop     rbx
0x18000980e  pop     rbp
0x18000980f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
