# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::StopActivity(void)

- ea: `0x180014990`
- end: `0x180014bbc`
- name: `?StopActivity@BackgroundTaskRelaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001ad0`
- `0x180001de4`
- `0x180008898`
- `0x180008ca0`
- `0x180009618`
- `0x180014990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b5d`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::StopActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *this)
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
        (__int64)&word_18002098E,
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
        (__int64)&byte_180020ADF,
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
0x180014990  push    rbp
0x180014992  push    rbx
0x180014993  push    rdi
0x180014994  lea     rbp, [rsp+10h]
0x180014999  sub     rsp, 130h
0x1800149a0  mov     rdi, [rcx+110h]
0x1800149a7  mov     rbx, rcx
0x1800149aa  mov     eax, [rdi+48h]
0x1800149ad  test    eax, eax
0x1800149af  jns     loc_180014B49
0x1800149b5  add     rdi, 50h ; 'P'
0x1800149b9  cmp     eax, [rdi+8]
0x1800149bc  jnz     loc_180014B49
0x1800149c2  test    rdi, rdi
0x1800149c5  jz      loc_180014B49
0x1800149cb  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800149d0  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x1800149d5  mov     r9, rax
0x1800149d8  mov     ecx, [rax]
0x1800149da  cmp     ecx, 5
0x1800149dd  jbe     loc_180014BAA
0x1800149e3  mov     rax, [rdi+70h]
0x1800149e7  lea     rdx, word_18002098E
0x1800149ee  mov     rcx, [rdi+30h]
0x1800149f2  mov     [rbp+var_60], rax
0x1800149f6  mov     eax, [rdi+68h]
0x1800149f9  mov     r8, [rbx+110h]
0x180014a00  mov     dword ptr [rbp+arg_10], eax
0x180014a03  add     r8, 8
0x180014a07  mov     rax, [rdi+60h]
0x180014a0b  mov     [rbp+var_58], rax
0x180014a0f  mov     rax, [rdi+58h]
0x180014a13  mov     [rbp+var_50], rax
0x180014a17  mov     eax, [rdi+50h]
0x180014a1a  mov     [rbp+arg_18], eax
0x180014a1d  mov     rax, [rdi+48h]
0x180014a21  mov     [rbp+var_48], rax
0x180014a25  mov     eax, [rdi+20h]
0x180014a28  mov     [rbp+var_80], eax
0x180014a2b  mov     rax, [rdi+18h]
0x180014a2f  mov     [rbp+var_40], rax
0x180014a33  mov     eax, [rdi]
0x180014a35  mov     [rbp+var_7C], eax
0x180014a38  mov     rax, [rdi+80h]
0x180014a3f  mov     [rbp+var_38], rax
0x180014a43  mov     eax, [rdi+40h]
0x180014a46  mov     [rbp+var_78], eax
0x180014a49  mov     rax, [rdi+38h]
0x180014a4d  mov     [rbp+var_30], rax
0x180014a51  mov     eax, [rdi+8]
0x180014a54  mov     [rbp+var_74], eax
0x180014a57  lea     rax, [rbp+var_70]
0x180014a5b  mov     [rsp+140h+var_90], rax
0x180014a63  lea     rax, [rbp+arg_0]
0x180014a67  mov     [rsp+140h+var_98], rax
0x180014a6f  lea     rax, [rbp+arg_8]
0x180014a73  mov     [rsp+140h+var_A0], rax
0x180014a7b  lea     rax, [rbp+var_68]
0x180014a7f  mov     [rsp+140h+var_A8], rax
0x180014a87  lea     rax, [rbp+var_60]
0x180014a8b  mov     [rsp+140h+var_B0], rax
0x180014a93  lea     rax, [rbp+arg_10]
0x180014a97  mov     [rsp+140h+var_B8], rax
0x180014a9f  lea     rax, [rbp+var_58]
0x180014aa3  mov     [rsp+140h+var_C0], rax
0x180014aab  lea     rax, [rbp+var_50]
0x180014aaf  mov     [rsp+140h+var_C8], rax
0x180014ab4  lea     rax, [rbp+arg_18]
0x180014ab8  mov     [rsp+140h+var_D0], rax
0x180014abd  lea     rax, [rbp+var_48]
0x180014ac1  mov     [rsp+140h+var_D8], rax
0x180014ac6  lea     rax, [rbp+var_80]
0x180014aca  mov     [rsp+140h+var_E0], rax
0x180014acf  lea     rax, [rbp+var_40]
0x180014ad3  mov     [rsp+140h+var_E8], rax
0x180014ad8  lea     rax, [rbp+var_7C]
0x180014adc  mov     [rsp+140h+var_F0], rax
0x180014ae1  lea     rax, [rbp+var_38]
0x180014ae5  mov     [rsp+140h+var_F8], rax
0x180014aea  lea     rax, [rbp+var_78]
0x180014aee  mov     [rsp+140h+var_100], rax
0x180014af3  lea     rax, [rbp+var_30]
0x180014af7  mov     [rsp+140h+var_108], rax
0x180014afc  lea     rax, [rbp+var_74]
0x180014b00  mov     [rbp+var_70], rcx
0x180014b04  mov     ecx, [rdi+44h]
0x180014b07  mov     [rsp+140h+var_110], rax
0x180014b0c  lea     rax, [rbp+var_28]
0x180014b10  mov     [rbp+arg_0], ecx
0x180014b13  mov     ecx, [rdi+10h]
0x180014b16  mov     [rbp+arg_8], ecx
0x180014b19  mov     rcx, [rdi+78h]
0x180014b1d  mov     [rsp+140h+var_118], rax
0x180014b22  lea     rax, [rbp+var_20]
0x180014b26  mov     [rbp+var_68], rcx
0x180014b2a  mov     rcx, r9
0x180014b2d  mov     [rsp+140h+var_120], rax
0x180014b32  mov     [rbp+var_28], 1000000h
0x180014b3a  mov     [rbp+var_20], 0
0x180014b42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180014b47  jmp     short loc_180014BAA
0x180014b49  call    ?zInternalStop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180014b4e  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180014b53  mov     rdi, rax
0x180014b56  mov     ecx, [rax]
0x180014b58  cmp     ecx, 5
0x180014b5b  jbe     short loc_180014BAA
0x180014b5d  call    cs:__imp_GetCurrentThreadId
0x180014b63  mov     r8, [rbx+110h]
0x180014b6a  lea     rdx, byte_180020ADF
0x180014b71  mov     [rbp+arg_0], eax
0x180014b74  lea     rax, [rbp+arg_0]
0x180014b78  mov     [rsp+140h+var_110], rax
0x180014b7d  lea     rax, [rbp+arg_8]
0x180014b81  mov     [rsp+140h+var_118], rax
0x180014b86  lea     rax, [rbp+arg_10]
0x180014b8a  mov     ecx, [r8+48h]
0x180014b8e  add     r8, 8
0x180014b92  mov     [rbp+arg_8], ecx
0x180014b95  mov     rcx, rdi
0x180014b98  mov     [rsp+140h+var_120], rax
0x180014b9d  mov     [rbp+arg_10], 0
0x180014ba5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014baa  mov     rcx, rbx
0x180014bad  add     rsp, 130h
0x180014bb4  pop     rdi
0x180014bb5  pop     rbx
0x180014bb6  pop     rbp
0x180014bb7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
