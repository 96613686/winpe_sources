# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::StopActivity(void)

- ea: `0x180014510`
- end: `0x18001473c`
- name: `?StopActivity@BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001ad0`
- `0x180001de4`
- `0x180008898`
- `0x180008ca0`
- `0x180009618`
- `0x180014510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800146dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800146dd`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::StopActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *this)
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
        (__int64)&byte_1800205E7,
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
        (__int64)&word_180020736,
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
0x180014510  push    rbp
0x180014512  push    rbx
0x180014513  push    rdi
0x180014514  lea     rbp, [rsp+10h]
0x180014519  sub     rsp, 130h
0x180014520  mov     rdi, [rcx+110h]
0x180014527  mov     rbx, rcx
0x18001452a  mov     eax, [rdi+48h]
0x18001452d  test    eax, eax
0x18001452f  jns     loc_1800146C9
0x180014535  add     rdi, 50h ; 'P'
0x180014539  cmp     eax, [rdi+8]
0x18001453c  jnz     loc_1800146C9
0x180014542  test    rdi, rdi
0x180014545  jz      loc_1800146C9
0x18001454b  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014550  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180014555  mov     r9, rax
0x180014558  mov     ecx, [rax]
0x18001455a  cmp     ecx, 5
0x18001455d  jbe     loc_18001472A
0x180014563  mov     rax, [rdi+70h]
0x180014567  lea     rdx, byte_1800205E7
0x18001456e  mov     rcx, [rdi+30h]
0x180014572  mov     [rbp+var_60], rax
0x180014576  mov     eax, [rdi+68h]
0x180014579  mov     r8, [rbx+110h]
0x180014580  mov     dword ptr [rbp+arg_10], eax
0x180014583  add     r8, 8
0x180014587  mov     rax, [rdi+60h]
0x18001458b  mov     [rbp+var_58], rax
0x18001458f  mov     rax, [rdi+58h]
0x180014593  mov     [rbp+var_50], rax
0x180014597  mov     eax, [rdi+50h]
0x18001459a  mov     [rbp+arg_18], eax
0x18001459d  mov     rax, [rdi+48h]
0x1800145a1  mov     [rbp+var_48], rax
0x1800145a5  mov     eax, [rdi+20h]
0x1800145a8  mov     [rbp+var_80], eax
0x1800145ab  mov     rax, [rdi+18h]
0x1800145af  mov     [rbp+var_40], rax
0x1800145b3  mov     eax, [rdi]
0x1800145b5  mov     [rbp+var_7C], eax
0x1800145b8  mov     rax, [rdi+80h]
0x1800145bf  mov     [rbp+var_38], rax
0x1800145c3  mov     eax, [rdi+40h]
0x1800145c6  mov     [rbp+var_78], eax
0x1800145c9  mov     rax, [rdi+38h]
0x1800145cd  mov     [rbp+var_30], rax
0x1800145d1  mov     eax, [rdi+8]
0x1800145d4  mov     [rbp+var_74], eax
0x1800145d7  lea     rax, [rbp+var_70]
0x1800145db  mov     [rsp+140h+var_90], rax
0x1800145e3  lea     rax, [rbp+arg_0]
0x1800145e7  mov     [rsp+140h+var_98], rax
0x1800145ef  lea     rax, [rbp+arg_8]
0x1800145f3  mov     [rsp+140h+var_A0], rax
0x1800145fb  lea     rax, [rbp+var_68]
0x1800145ff  mov     [rsp+140h+var_A8], rax
0x180014607  lea     rax, [rbp+var_60]
0x18001460b  mov     [rsp+140h+var_B0], rax
0x180014613  lea     rax, [rbp+arg_10]
0x180014617  mov     [rsp+140h+var_B8], rax
0x18001461f  lea     rax, [rbp+var_58]
0x180014623  mov     [rsp+140h+var_C0], rax
0x18001462b  lea     rax, [rbp+var_50]
0x18001462f  mov     [rsp+140h+var_C8], rax
0x180014634  lea     rax, [rbp+arg_18]
0x180014638  mov     [rsp+140h+var_D0], rax
0x18001463d  lea     rax, [rbp+var_48]
0x180014641  mov     [rsp+140h+var_D8], rax
0x180014646  lea     rax, [rbp+var_80]
0x18001464a  mov     [rsp+140h+var_E0], rax
0x18001464f  lea     rax, [rbp+var_40]
0x180014653  mov     [rsp+140h+var_E8], rax
0x180014658  lea     rax, [rbp+var_7C]
0x18001465c  mov     [rsp+140h+var_F0], rax
0x180014661  lea     rax, [rbp+var_38]
0x180014665  mov     [rsp+140h+var_F8], rax
0x18001466a  lea     rax, [rbp+var_78]
0x18001466e  mov     [rsp+140h+var_100], rax
0x180014673  lea     rax, [rbp+var_30]
0x180014677  mov     [rsp+140h+var_108], rax
0x18001467c  lea     rax, [rbp+var_74]
0x180014680  mov     [rbp+var_70], rcx
0x180014684  mov     ecx, [rdi+44h]
0x180014687  mov     [rsp+140h+var_110], rax
0x18001468c  lea     rax, [rbp+var_28]
0x180014690  mov     [rbp+arg_0], ecx
0x180014693  mov     ecx, [rdi+10h]
0x180014696  mov     [rbp+arg_8], ecx
0x180014699  mov     rcx, [rdi+78h]
0x18001469d  mov     [rsp+140h+var_118], rax
0x1800146a2  lea     rax, [rbp+var_20]
0x1800146a6  mov     [rbp+var_68], rcx
0x1800146aa  mov     rcx, r9
0x1800146ad  mov     [rsp+140h+var_120], rax
0x1800146b2  mov     [rbp+var_28], 1000000h
0x1800146ba  mov     [rbp+var_20], 0
0x1800146c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800146c7  jmp     short loc_18001472A
0x1800146c9  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800146ce  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x1800146d3  mov     rdi, rax
0x1800146d6  mov     ecx, [rax]
0x1800146d8  cmp     ecx, 5
0x1800146db  jbe     short loc_18001472A
0x1800146dd  call    cs:__imp_GetCurrentThreadId
0x1800146e3  mov     r8, [rbx+110h]
0x1800146ea  lea     rdx, word_180020736
0x1800146f1  mov     [rbp+arg_0], eax
0x1800146f4  lea     rax, [rbp+arg_0]
0x1800146f8  mov     [rsp+140h+var_110], rax
0x1800146fd  lea     rax, [rbp+arg_8]
0x180014701  mov     [rsp+140h+var_118], rax
0x180014706  lea     rax, [rbp+arg_10]
0x18001470a  mov     ecx, [r8+48h]
0x18001470e  add     r8, 8
0x180014712  mov     [rbp+arg_8], ecx
0x180014715  mov     rcx, rdi
0x180014718  mov     [rsp+140h+var_120], rax
0x18001471d  mov     [rbp+arg_10], 0
0x180014725  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001472a  mov     rcx, rbx
0x18001472d  add     rsp, 130h
0x180014734  pop     rdi
0x180014735  pop     rbx
0x180014736  pop     rbp
0x180014737  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
