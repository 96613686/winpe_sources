# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::StopActivity(void)

- ea: `0x18000bf70`
- end: `0x18000c19c`
- name: `?StopActivity@BackgroundTaskSettingsChanged@CTelemetryProvider@ShellExtension@IoT@Microsoft@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001ad0`
- `0x180001de4`
- `0x180008898`
- `0x180008ca0`
- `0x180009618`
- `0x18000bf70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c13d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c13d`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::StopActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged *this)
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
        (__int64)&unk_18001FA58,
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
        (__int64)&unk_18001FBB0,
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
0x18000bf70  push    rbp
0x18000bf72  push    rbx
0x18000bf73  push    rdi
0x18000bf74  lea     rbp, [rsp+10h]
0x18000bf79  sub     rsp, 130h
0x18000bf80  mov     rdi, [rcx+110h]
0x18000bf87  mov     rbx, rcx
0x18000bf8a  mov     eax, [rdi+48h]
0x18000bf8d  test    eax, eax
0x18000bf8f  jns     loc_18000C129
0x18000bf95  add     rdi, 50h ; 'P'
0x18000bf99  cmp     eax, [rdi+8]
0x18000bf9c  jnz     loc_18000C129
0x18000bfa2  test    rdi, rdi
0x18000bfa5  jz      loc_18000C129
0x18000bfab  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000bfb0  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18000bfb5  mov     r9, rax
0x18000bfb8  mov     ecx, [rax]
0x18000bfba  cmp     ecx, 5
0x18000bfbd  jbe     loc_18000C18A
0x18000bfc3  mov     rax, [rdi+70h]
0x18000bfc7  lea     rdx, unk_18001FA58
0x18000bfce  mov     rcx, [rdi+30h]
0x18000bfd2  mov     [rbp+var_60], rax
0x18000bfd6  mov     eax, [rdi+68h]
0x18000bfd9  mov     r8, [rbx+110h]
0x18000bfe0  mov     dword ptr [rbp+arg_10], eax
0x18000bfe3  add     r8, 8
0x18000bfe7  mov     rax, [rdi+60h]
0x18000bfeb  mov     [rbp+var_58], rax
0x18000bfef  mov     rax, [rdi+58h]
0x18000bff3  mov     [rbp+var_50], rax
0x18000bff7  mov     eax, [rdi+50h]
0x18000bffa  mov     [rbp+arg_18], eax
0x18000bffd  mov     rax, [rdi+48h]
0x18000c001  mov     [rbp+var_48], rax
0x18000c005  mov     eax, [rdi+20h]
0x18000c008  mov     [rbp+var_80], eax
0x18000c00b  mov     rax, [rdi+18h]
0x18000c00f  mov     [rbp+var_40], rax
0x18000c013  mov     eax, [rdi]
0x18000c015  mov     [rbp+var_7C], eax
0x18000c018  mov     rax, [rdi+80h]
0x18000c01f  mov     [rbp+var_38], rax
0x18000c023  mov     eax, [rdi+40h]
0x18000c026  mov     [rbp+var_78], eax
0x18000c029  mov     rax, [rdi+38h]
0x18000c02d  mov     [rbp+var_30], rax
0x18000c031  mov     eax, [rdi+8]
0x18000c034  mov     [rbp+var_74], eax
0x18000c037  lea     rax, [rbp+var_70]
0x18000c03b  mov     [rsp+140h+var_90], rax
0x18000c043  lea     rax, [rbp+arg_0]
0x18000c047  mov     [rsp+140h+var_98], rax
0x18000c04f  lea     rax, [rbp+arg_8]
0x18000c053  mov     [rsp+140h+var_A0], rax
0x18000c05b  lea     rax, [rbp+var_68]
0x18000c05f  mov     [rsp+140h+var_A8], rax
0x18000c067  lea     rax, [rbp+var_60]
0x18000c06b  mov     [rsp+140h+var_B0], rax
0x18000c073  lea     rax, [rbp+arg_10]
0x18000c077  mov     [rsp+140h+var_B8], rax
0x18000c07f  lea     rax, [rbp+var_58]
0x18000c083  mov     [rsp+140h+var_C0], rax
0x18000c08b  lea     rax, [rbp+var_50]
0x18000c08f  mov     [rsp+140h+var_C8], rax
0x18000c094  lea     rax, [rbp+arg_18]
0x18000c098  mov     [rsp+140h+var_D0], rax
0x18000c09d  lea     rax, [rbp+var_48]
0x18000c0a1  mov     [rsp+140h+var_D8], rax
0x18000c0a6  lea     rax, [rbp+var_80]
0x18000c0aa  mov     [rsp+140h+var_E0], rax
0x18000c0af  lea     rax, [rbp+var_40]
0x18000c0b3  mov     [rsp+140h+var_E8], rax
0x18000c0b8  lea     rax, [rbp+var_7C]
0x18000c0bc  mov     [rsp+140h+var_F0], rax
0x18000c0c1  lea     rax, [rbp+var_38]
0x18000c0c5  mov     [rsp+140h+var_F8], rax
0x18000c0ca  lea     rax, [rbp+var_78]
0x18000c0ce  mov     [rsp+140h+var_100], rax
0x18000c0d3  lea     rax, [rbp+var_30]
0x18000c0d7  mov     [rsp+140h+var_108], rax
0x18000c0dc  lea     rax, [rbp+var_74]
0x18000c0e0  mov     [rbp+var_70], rcx
0x18000c0e4  mov     ecx, [rdi+44h]
0x18000c0e7  mov     [rsp+140h+var_110], rax
0x18000c0ec  lea     rax, [rbp+var_28]
0x18000c0f0  mov     [rbp+arg_0], ecx
0x18000c0f3  mov     ecx, [rdi+10h]
0x18000c0f6  mov     [rbp+arg_8], ecx
0x18000c0f9  mov     rcx, [rdi+78h]
0x18000c0fd  mov     [rsp+140h+var_118], rax
0x18000c102  lea     rax, [rbp+var_20]
0x18000c106  mov     [rbp+var_68], rcx
0x18000c10a  mov     rcx, r9
0x18000c10d  mov     [rsp+140h+var_120], rax
0x18000c112  mov     [rbp+var_28], 1000000h
0x18000c11a  mov     [rbp+var_20], 0
0x18000c122  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c127  jmp     short loc_18000C18A
0x18000c129  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000c12e  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18000c133  mov     rdi, rax
0x18000c136  mov     ecx, [rax]
0x18000c138  cmp     ecx, 5
0x18000c13b  jbe     short loc_18000C18A
0x18000c13d  call    cs:__imp_GetCurrentThreadId
0x18000c143  mov     r8, [rbx+110h]
0x18000c14a  lea     rdx, unk_18001FBB0
0x18000c151  mov     [rbp+arg_0], eax
0x18000c154  lea     rax, [rbp+arg_0]
0x18000c158  mov     [rsp+140h+var_110], rax
0x18000c15d  lea     rax, [rbp+arg_8]
0x18000c161  mov     [rsp+140h+var_118], rax
0x18000c166  lea     rax, [rbp+arg_10]
0x18000c16a  mov     ecx, [r8+48h]
0x18000c16e  add     r8, 8
0x18000c172  mov     [rbp+arg_8], ecx
0x18000c175  mov     rcx, rdi
0x18000c178  mov     [rsp+140h+var_120], rax
0x18000c17d  mov     [rbp+arg_10], 0
0x18000c185  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c18a  mov     rcx, rbx
0x18000c18d  add     rsp, 130h
0x18000c194  pop     rdi
0x18000c195  pop     rbx
0x18000c196  pop     rbp
0x18000c197  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
