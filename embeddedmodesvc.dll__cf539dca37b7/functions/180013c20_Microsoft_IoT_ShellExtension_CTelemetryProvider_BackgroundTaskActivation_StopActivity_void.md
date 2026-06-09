# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::StopActivity(void)

- ea: `0x180013c20`
- end: `0x180013e44`
- name: `?StopActivity@BackgroundTaskActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180001de4`
- `0x180008898`
- `0x180008ca0`
- `0x180009618`
- `0x180013c20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013de5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013de5`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::StopActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v19; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v21; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v22; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v24; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v29; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6, v5) )
    {
      v8 = (__int64 *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v29 = v4[26];
      v21 = (__int64 *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v30 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v31) = v4[8];
      v24 = (__int64 *)*((_QWORD *)v4 + 3);
      v32 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v17 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v8;
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&word_18002045E,
        v9 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v18,
        &v26,
        (__int64)&v17,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        &v21,
        (__int64)&v29,
        &v20,
        &v19);
    }
  }
  else
  {
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
    v13 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11, v12) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v15 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)&word_18002058E,
        v15 + 8,
        v16,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180013c20  push    rbp
0x180013c22  push    rbx
0x180013c23  push    rdi
0x180013c24  lea     rbp, [rsp-47h]
0x180013c29  sub     rsp, 100h
0x180013c30  mov     rdi, [rcx+110h]
0x180013c37  mov     rbx, rcx
0x180013c3a  mov     eax, [rdi+48h]
0x180013c3d  test    eax, eax
0x180013c3f  jns     loc_180013DBB
0x180013c45  add     rdi, 50h ; 'P'
0x180013c49  cmp     eax, [rdi+8]
0x180013c4c  jnz     loc_180013DBB
0x180013c52  test    rdi, rdi
0x180013c55  jz      loc_180013DBB
0x180013c5b  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180013c60  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180013c65  mov     r9, rax
0x180013c68  mov     ecx, [rax]
0x180013c6a  cmp     ecx, 5
0x180013c6d  jbe     loc_180013E32
0x180013c73  mov     rdx, 200000000000h
0x180013c7d  mov     rcx, rax
0x180013c80  call    _tlgKeywordOn
0x180013c85  test    al, al
0x180013c87  jz      loc_180013E32
0x180013c8d  mov     rax, [rdi+70h]
0x180013c91  lea     rdx, word_18002045E
0x180013c98  mov     rcx, [rdi+78h]
0x180013c9c  mov     r8, [rbx+110h]
0x180013ca3  mov     [rbp+57h+var_60], rax
0x180013ca7  add     r8, 8
0x180013cab  mov     eax, [rdi+68h]
0x180013cae  mov     [rbp+57h+arg_0], eax
0x180013cb1  mov     rax, [rdi+60h]
0x180013cb5  mov     [rbp+57h+var_58], rax
0x180013cb9  mov     rax, [rdi+58h]
0x180013cbd  mov     [rbp+57h+var_50], rax
0x180013cc1  mov     eax, [rdi+50h]
0x180013cc4  mov     [rbp+57h+arg_8], eax
0x180013cc7  mov     rax, [rdi+48h]
0x180013ccb  mov     [rbp+57h+var_48], rax
0x180013ccf  mov     eax, [rdi+20h]
0x180013cd2  mov     dword ptr [rbp+57h+arg_10], eax
0x180013cd5  mov     rax, [rdi+18h]
0x180013cd9  mov     [rbp+57h+var_40], rax
0x180013cdd  mov     eax, [rdi]
0x180013cdf  mov     [rbp+57h+arg_18], eax
0x180013ce2  mov     rax, [rdi+80h]
0x180013ce9  mov     [rbp+57h+var_38], rax
0x180013ced  mov     eax, [rdi+40h]
0x180013cf0  mov     [rbp+57h+var_70], eax
0x180013cf3  mov     rax, [rdi+38h]
0x180013cf7  mov     [rbp+57h+var_30], rax
0x180013cfb  mov     eax, [rdi+8]
0x180013cfe  mov     [rbp+57h+var_6C], eax
0x180013d01  lea     rax, [rbp+57h+var_68]
0x180013d05  mov     [rsp+110h+var_78], rax
0x180013d0d  lea     rax, [rbp+57h+var_60]
0x180013d11  mov     [rsp+110h+var_80], rax
0x180013d19  lea     rax, [rbp+57h+arg_0]
0x180013d1d  mov     [rsp+110h+var_88], rax
0x180013d25  lea     rax, [rbp+57h+var_58]
0x180013d29  mov     [rsp+110h+var_90], rax
0x180013d31  lea     rax, [rbp+57h+var_50]
0x180013d35  mov     [rsp+110h+var_98], rax
0x180013d3a  lea     rax, [rbp+57h+arg_8]
0x180013d3e  mov     [rsp+110h+var_A0], rax
0x180013d43  lea     rax, [rbp+57h+var_48]
0x180013d47  mov     [rsp+110h+var_A8], rax
0x180013d4c  lea     rax, [rbp+57h+arg_10]
0x180013d50  mov     [rsp+110h+var_B0], rax
0x180013d55  lea     rax, [rbp+57h+var_40]
0x180013d59  mov     [rsp+110h+var_B8], rax
0x180013d5e  lea     rax, [rbp+57h+arg_18]
0x180013d62  mov     [rsp+110h+var_C0], rax
0x180013d67  lea     rax, [rbp+57h+var_38]
0x180013d6b  mov     [rsp+110h+var_C8], rax
0x180013d70  lea     rax, [rbp+57h+var_70]
0x180013d74  mov     [rsp+110h+var_D0], rax
0x180013d79  lea     rax, [rbp+57h+var_30]
0x180013d7d  mov     [rsp+110h+var_D8], rax
0x180013d82  lea     rax, [rbp+57h+var_6C]
0x180013d86  mov     [rsp+110h+var_E0], rax
0x180013d8b  lea     rax, [rbp+57h+var_28]
0x180013d8f  mov     [rsp+110h+var_E8], rax
0x180013d94  lea     rax, [rbp+57h+var_20]
0x180013d98  mov     [rbp+57h+var_68], rcx
0x180013d9c  mov     rcx, r9
0x180013d9f  mov     [rsp+110h+var_F0], rax
0x180013da4  mov     [rbp+57h+var_28], 1000000h
0x180013dac  mov     [rbp+57h+var_20], 0
0x180013db4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180013db9  jmp     short loc_180013E32
0x180013dbb  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180013dc0  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180013dc5  mov     rdi, rax
0x180013dc8  mov     ecx, [rax]
0x180013dca  cmp     ecx, 5
0x180013dcd  jbe     short loc_180013E32
0x180013dcf  mov     rdx, 200000000000h
0x180013dd9  mov     rcx, rax
0x180013ddc  call    _tlgKeywordOn
0x180013de1  test    al, al
0x180013de3  jz      short loc_180013E32
0x180013de5  call    cs:__imp_GetCurrentThreadId
0x180013deb  mov     r8, [rbx+110h]
0x180013df2  lea     rdx, word_18002058E
0x180013df9  mov     [rbp+57h+arg_0], eax
0x180013dfc  mov     rcx, rdi
0x180013dff  mov     eax, [r8+48h]
0x180013e03  add     r8, 8
0x180013e07  mov     [rbp+57h+arg_8], eax
0x180013e0a  lea     rax, [rbp+57h+arg_0]
0x180013e0e  mov     [rsp+110h+var_E0], rax
0x180013e13  lea     rax, [rbp+57h+arg_8]
0x180013e17  mov     [rsp+110h+var_E8], rax
0x180013e1c  lea     rax, [rbp+57h+arg_10]
0x180013e20  mov     [rsp+110h+var_F0], rax
0x180013e25  mov     [rbp+57h+arg_10], 0
0x180013e2d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013e32  mov     rcx, rbx
0x180013e35  add     rsp, 100h
0x180013e3c  pop     rdi
0x180013e3d  pop     rbx
0x180013e3e  pop     rbp
0x180013e3f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
