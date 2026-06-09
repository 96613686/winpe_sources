# Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::StopActivity(void)

- ea: `0x1800092a0`
- end: `0x1800094cc`
- name: `?StopActivity@BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001ad0`
- `0x180001de4`
- `0x180008898`
- `0x180008ca0`
- `0x1800092a0`
- `0x180009618`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000946d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000946d`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::StopActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C4h] [rbp-7Ch] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v16; // [rsp+D0h] [rbp-70h] BYREF
  __int64 *v17; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp-60h] BYREF
  __int64 *v19; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v20; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v21; // [rsp+F8h] [rbp-48h] BYREF
  __int64 *v22; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v23; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v24; // [rsp+110h] [rbp-30h] BYREF
  __int64 v25; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v26[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v27; // [rsp+150h] [rbp+10h] BYREF
  int v28; // [rsp+158h] [rbp+18h] BYREF
  __int64 v29; // [rsp+160h] [rbp+20h] BYREF
  int v30; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v29) = v4[26];
      v19 = (__int64 *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v30 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v12 = v4[8];
      v22 = (__int64 *)*((_QWORD *)v4 + 3);
      v13 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v16 = v6;
      v27 = v4[17];
      v28 = v4[4];
      v17 = (__int64 *)*((_QWORD *)v4 + 15);
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&unk_18001F650,
        v7 + 8,
        (__int64)v5,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v30,
        &v20,
        &v19,
        (__int64)&v29,
        &v18,
        &v17,
        (__int64)&v28,
        (__int64)&v27,
        &v16);
    }
  }
  else
  {
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v10 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)byte_18001F79B,
        v10 + 8,
        v11,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800092a0  push    rbp
0x1800092a2  push    rbx
0x1800092a3  push    rdi
0x1800092a4  lea     rbp, [rsp+10h]
0x1800092a9  sub     rsp, 130h
0x1800092b0  mov     rdi, [rcx+110h]
0x1800092b7  mov     rbx, rcx
0x1800092ba  mov     eax, [rdi+48h]
0x1800092bd  test    eax, eax
0x1800092bf  jns     loc_180009459
0x1800092c5  add     rdi, 50h ; 'P'
0x1800092c9  cmp     eax, [rdi+8]
0x1800092cc  jnz     loc_180009459
0x1800092d2  test    rdi, rdi
0x1800092d5  jz      loc_180009459
0x1800092db  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800092e0  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x1800092e5  mov     r9, rax
0x1800092e8  mov     ecx, [rax]
0x1800092ea  cmp     ecx, 5
0x1800092ed  jbe     loc_1800094BA
0x1800092f3  mov     rax, [rdi+70h]
0x1800092f7  lea     rdx, unk_18001F650
0x1800092fe  mov     rcx, [rdi+30h]
0x180009302  mov     [rbp+var_60], rax
0x180009306  mov     eax, [rdi+68h]
0x180009309  mov     r8, [rbx+110h]
0x180009310  mov     dword ptr [rbp+arg_10], eax
0x180009313  add     r8, 8
0x180009317  mov     rax, [rdi+60h]
0x18000931b  mov     [rbp+var_58], rax
0x18000931f  mov     rax, [rdi+58h]
0x180009323  mov     [rbp+var_50], rax
0x180009327  mov     eax, [rdi+50h]
0x18000932a  mov     [rbp+arg_18], eax
0x18000932d  mov     rax, [rdi+48h]
0x180009331  mov     [rbp+var_48], rax
0x180009335  mov     eax, [rdi+20h]
0x180009338  mov     [rbp+var_80], eax
0x18000933b  mov     rax, [rdi+18h]
0x18000933f  mov     [rbp+var_40], rax
0x180009343  mov     eax, [rdi]
0x180009345  mov     [rbp+var_7C], eax
0x180009348  mov     rax, [rdi+80h]
0x18000934f  mov     [rbp+var_38], rax
0x180009353  mov     eax, [rdi+40h]
0x180009356  mov     [rbp+var_78], eax
0x180009359  mov     rax, [rdi+38h]
0x18000935d  mov     [rbp+var_30], rax
0x180009361  mov     eax, [rdi+8]
0x180009364  mov     [rbp+var_74], eax
0x180009367  lea     rax, [rbp+var_70]
0x18000936b  mov     [rsp+140h+var_90], rax
0x180009373  lea     rax, [rbp+arg_0]
0x180009377  mov     [rsp+140h+var_98], rax
0x18000937f  lea     rax, [rbp+arg_8]
0x180009383  mov     [rsp+140h+var_A0], rax
0x18000938b  lea     rax, [rbp+var_68]
0x18000938f  mov     [rsp+140h+var_A8], rax
0x180009397  lea     rax, [rbp+var_60]
0x18000939b  mov     [rsp+140h+var_B0], rax
0x1800093a3  lea     rax, [rbp+arg_10]
0x1800093a7  mov     [rsp+140h+var_B8], rax
0x1800093af  lea     rax, [rbp+var_58]
0x1800093b3  mov     [rsp+140h+var_C0], rax
0x1800093bb  lea     rax, [rbp+var_50]
0x1800093bf  mov     [rsp+140h+var_C8], rax
0x1800093c4  lea     rax, [rbp+arg_18]
0x1800093c8  mov     [rsp+140h+var_D0], rax
0x1800093cd  lea     rax, [rbp+var_48]
0x1800093d1  mov     [rsp+140h+var_D8], rax
0x1800093d6  lea     rax, [rbp+var_80]
0x1800093da  mov     [rsp+140h+var_E0], rax
0x1800093df  lea     rax, [rbp+var_40]
0x1800093e3  mov     [rsp+140h+var_E8], rax
0x1800093e8  lea     rax, [rbp+var_7C]
0x1800093ec  mov     [rsp+140h+var_F0], rax
0x1800093f1  lea     rax, [rbp+var_38]
0x1800093f5  mov     [rsp+140h+var_F8], rax
0x1800093fa  lea     rax, [rbp+var_78]
0x1800093fe  mov     [rsp+140h+var_100], rax
0x180009403  lea     rax, [rbp+var_30]
0x180009407  mov     [rsp+140h+var_108], rax
0x18000940c  lea     rax, [rbp+var_74]
0x180009410  mov     [rbp+var_70], rcx
0x180009414  mov     ecx, [rdi+44h]
0x180009417  mov     [rsp+140h+var_110], rax
0x18000941c  lea     rax, [rbp+var_28]
0x180009420  mov     [rbp+arg_0], ecx
0x180009423  mov     ecx, [rdi+10h]
0x180009426  mov     [rbp+arg_8], ecx
0x180009429  mov     rcx, [rdi+78h]
0x18000942d  mov     [rsp+140h+var_118], rax
0x180009432  lea     rax, [rbp+var_20]
0x180009436  mov     [rbp+var_68], rcx
0x18000943a  mov     rcx, r9
0x18000943d  mov     [rsp+140h+var_120], rax
0x180009442  mov     [rbp+var_28], 1000000h
0x18000944a  mov     [rbp+var_20], 0
0x180009452  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180009457  jmp     short loc_1800094BA
0x180009459  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000945e  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180009463  mov     rdi, rax
0x180009466  mov     ecx, [rax]
0x180009468  cmp     ecx, 5
0x18000946b  jbe     short loc_1800094BA
0x18000946d  call    cs:__imp_GetCurrentThreadId
0x180009473  mov     r8, [rbx+110h]
0x18000947a  lea     rdx, byte_18001F79B
0x180009481  mov     [rbp+arg_0], eax
0x180009484  lea     rax, [rbp+arg_0]
0x180009488  mov     [rsp+140h+var_110], rax
0x18000948d  lea     rax, [rbp+arg_8]
0x180009491  mov     [rsp+140h+var_118], rax
0x180009496  lea     rax, [rbp+arg_10]
0x18000949a  mov     ecx, [r8+48h]
0x18000949e  add     r8, 8
0x1800094a2  mov     [rbp+arg_8], ecx
0x1800094a5  mov     rcx, rdi
0x1800094a8  mov     [rsp+140h+var_120], rax
0x1800094ad  mov     [rbp+arg_10], 0
0x1800094b5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800094ba  mov     rcx, rbx
0x1800094bd  add     rsp, 130h
0x1800094c4  pop     rdi
0x1800094c5  pop     rbx
0x1800094c6  pop     rbp
0x1800094c7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
