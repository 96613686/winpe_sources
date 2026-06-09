# Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated::StopActivity(void)

- ea: `0x180014bd0`
- end: `0x180014df4`
- name: `?StopActivity@UnknownTaskInstanceActivated@CTelemetryProvider@ShellExtension@IoT@Microsoft@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated *__hidden this)`
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
- `0x180014bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d95`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated::StopActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated *this)
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
        (__int64)byte_180020F59,
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
        (__int64)byte_18002108D,
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
0x180014bd0  push    rbp
0x180014bd2  push    rbx
0x180014bd3  push    rdi
0x180014bd4  lea     rbp, [rsp-47h]
0x180014bd9  sub     rsp, 100h
0x180014be0  mov     rdi, [rcx+110h]
0x180014be7  mov     rbx, rcx
0x180014bea  mov     eax, [rdi+48h]
0x180014bed  test    eax, eax
0x180014bef  jns     loc_180014D6B
0x180014bf5  add     rdi, 50h ; 'P'
0x180014bf9  cmp     eax, [rdi+8]
0x180014bfc  jnz     loc_180014D6B
0x180014c02  test    rdi, rdi
0x180014c05  jz      loc_180014D6B
0x180014c0b  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014c10  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180014c15  mov     r9, rax
0x180014c18  mov     ecx, [rax]
0x180014c1a  cmp     ecx, 5
0x180014c1d  jbe     loc_180014DE2
0x180014c23  mov     rdx, 200000000000h
0x180014c2d  mov     rcx, rax
0x180014c30  call    _tlgKeywordOn
0x180014c35  test    al, al
0x180014c37  jz      loc_180014DE2
0x180014c3d  mov     rax, [rdi+70h]
0x180014c41  lea     rdx, byte_180020F59
0x180014c48  mov     rcx, [rdi+78h]
0x180014c4c  mov     r8, [rbx+110h]
0x180014c53  mov     [rbp+57h+var_60], rax
0x180014c57  add     r8, 8
0x180014c5b  mov     eax, [rdi+68h]
0x180014c5e  mov     [rbp+57h+arg_0], eax
0x180014c61  mov     rax, [rdi+60h]
0x180014c65  mov     [rbp+57h+var_58], rax
0x180014c69  mov     rax, [rdi+58h]
0x180014c6d  mov     [rbp+57h+var_50], rax
0x180014c71  mov     eax, [rdi+50h]
0x180014c74  mov     [rbp+57h+arg_8], eax
0x180014c77  mov     rax, [rdi+48h]
0x180014c7b  mov     [rbp+57h+var_48], rax
0x180014c7f  mov     eax, [rdi+20h]
0x180014c82  mov     dword ptr [rbp+57h+arg_10], eax
0x180014c85  mov     rax, [rdi+18h]
0x180014c89  mov     [rbp+57h+var_40], rax
0x180014c8d  mov     eax, [rdi]
0x180014c8f  mov     [rbp+57h+arg_18], eax
0x180014c92  mov     rax, [rdi+80h]
0x180014c99  mov     [rbp+57h+var_38], rax
0x180014c9d  mov     eax, [rdi+40h]
0x180014ca0  mov     [rbp+57h+var_70], eax
0x180014ca3  mov     rax, [rdi+38h]
0x180014ca7  mov     [rbp+57h+var_30], rax
0x180014cab  mov     eax, [rdi+8]
0x180014cae  mov     [rbp+57h+var_6C], eax
0x180014cb1  lea     rax, [rbp+57h+var_68]
0x180014cb5  mov     [rsp+110h+var_78], rax
0x180014cbd  lea     rax, [rbp+57h+var_60]
0x180014cc1  mov     [rsp+110h+var_80], rax
0x180014cc9  lea     rax, [rbp+57h+arg_0]
0x180014ccd  mov     [rsp+110h+var_88], rax
0x180014cd5  lea     rax, [rbp+57h+var_58]
0x180014cd9  mov     [rsp+110h+var_90], rax
0x180014ce1  lea     rax, [rbp+57h+var_50]
0x180014ce5  mov     [rsp+110h+var_98], rax
0x180014cea  lea     rax, [rbp+57h+arg_8]
0x180014cee  mov     [rsp+110h+var_A0], rax
0x180014cf3  lea     rax, [rbp+57h+var_48]
0x180014cf7  mov     [rsp+110h+var_A8], rax
0x180014cfc  lea     rax, [rbp+57h+arg_10]
0x180014d00  mov     [rsp+110h+var_B0], rax
0x180014d05  lea     rax, [rbp+57h+var_40]
0x180014d09  mov     [rsp+110h+var_B8], rax
0x180014d0e  lea     rax, [rbp+57h+arg_18]
0x180014d12  mov     [rsp+110h+var_C0], rax
0x180014d17  lea     rax, [rbp+57h+var_38]
0x180014d1b  mov     [rsp+110h+var_C8], rax
0x180014d20  lea     rax, [rbp+57h+var_70]
0x180014d24  mov     [rsp+110h+var_D0], rax
0x180014d29  lea     rax, [rbp+57h+var_30]
0x180014d2d  mov     [rsp+110h+var_D8], rax
0x180014d32  lea     rax, [rbp+57h+var_6C]
0x180014d36  mov     [rsp+110h+var_E0], rax
0x180014d3b  lea     rax, [rbp+57h+var_28]
0x180014d3f  mov     [rsp+110h+var_E8], rax
0x180014d44  lea     rax, [rbp+57h+var_20]
0x180014d48  mov     [rbp+57h+var_68], rcx
0x180014d4c  mov     rcx, r9
0x180014d4f  mov     [rsp+110h+var_F0], rax
0x180014d54  mov     [rbp+57h+var_28], 1000000h
0x180014d5c  mov     [rbp+57h+var_20], 0
0x180014d64  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180014d69  jmp     short loc_180014DE2
0x180014d6b  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014d70  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180014d75  mov     rdi, rax
0x180014d78  mov     ecx, [rax]
0x180014d7a  cmp     ecx, 5
0x180014d7d  jbe     short loc_180014DE2
0x180014d7f  mov     rdx, 200000000000h
0x180014d89  mov     rcx, rax
0x180014d8c  call    _tlgKeywordOn
0x180014d91  test    al, al
0x180014d93  jz      short loc_180014DE2
0x180014d95  call    cs:__imp_GetCurrentThreadId
0x180014d9b  mov     r8, [rbx+110h]
0x180014da2  lea     rdx, byte_18002108D
0x180014da9  mov     [rbp+57h+arg_0], eax
0x180014dac  mov     rcx, rdi
0x180014daf  mov     eax, [r8+48h]
0x180014db3  add     r8, 8
0x180014db7  mov     [rbp+57h+arg_8], eax
0x180014dba  lea     rax, [rbp+57h+arg_0]
0x180014dbe  mov     [rsp+110h+var_E0], rax
0x180014dc3  lea     rax, [rbp+57h+arg_8]
0x180014dc7  mov     [rsp+110h+var_E8], rax
0x180014dcc  lea     rax, [rbp+57h+arg_10]
0x180014dd0  mov     [rsp+110h+var_F0], rax
0x180014dd5  mov     [rbp+57h+arg_10], 0
0x180014ddd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014de2  mov     rcx, rbx
0x180014de5  add     rsp, 100h
0x180014dec  pop     rdi
0x180014ded  pop     rbx
0x180014dee  pop     rbp
0x180014def  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
