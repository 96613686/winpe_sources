# IntlCplTraceLoggingTelemetry::ChangeSystemLocale::StopActivity(void)

- ea: `0x18000e910`
- end: `0x18000eb3c`
- name: `?StopActivity@ChangeSystemLocale@IntlCplTraceLoggingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::ChangeSystemLocale *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001910`
- `0x180001c94`
- `0x1800093fc`
- `0x18000d524`
- `0x18000e910`
- `0x18000f5b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eadd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eadd`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::ChangeSystemLocale::StopActivity(
        IntlCplTraceLoggingTelemetry::ChangeSystemLocale *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v29[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v30; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = IntlCplTraceLogging::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v21 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v8;
      v30 = v4[17];
      v31 = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)&unk_18003313C,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = IntlCplTraceLogging::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&unk_180033289,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x18000e910  push    rbp
0x18000e912  push    rbx
0x18000e913  push    rdi
0x18000e914  lea     rbp, [rsp+10h]
0x18000e919  sub     rsp, 130h
0x18000e920  mov     rdi, [rcx+110h]
0x18000e927  mov     rbx, rcx
0x18000e92a  mov     eax, [rdi+48h]
0x18000e92d  test    eax, eax
0x18000e92f  jns     loc_18000EAC9
0x18000e935  add     rdi, 50h ; 'P'
0x18000e939  cmp     eax, [rdi+8]
0x18000e93c  jnz     loc_18000EAC9
0x18000e942  test    rdi, rdi
0x18000e945  jz      loc_18000EAC9
0x18000e94b  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000e950  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000e955  mov     r9, rax
0x18000e958  mov     ecx, [rax]
0x18000e95a  cmp     ecx, 5
0x18000e95d  jbe     loc_18000EB2A
0x18000e963  mov     rax, [rdi+70h]
0x18000e967  lea     rdx, unk_18003313C
0x18000e96e  mov     rcx, [rdi+30h]
0x18000e972  mov     [rbp+var_60], rax
0x18000e976  mov     eax, [rdi+68h]
0x18000e979  mov     r8, [rbx+110h]
0x18000e980  mov     dword ptr [rbp+arg_10], eax
0x18000e983  add     r8, 8
0x18000e987  mov     rax, [rdi+60h]
0x18000e98b  mov     [rbp+var_58], rax
0x18000e98f  mov     rax, [rdi+58h]
0x18000e993  mov     [rbp+var_50], rax
0x18000e997  mov     eax, [rdi+50h]
0x18000e99a  mov     [rbp+arg_18], eax
0x18000e99d  mov     rax, [rdi+48h]
0x18000e9a1  mov     [rbp+var_48], rax
0x18000e9a5  mov     eax, [rdi+20h]
0x18000e9a8  mov     [rbp+var_80], eax
0x18000e9ab  mov     rax, [rdi+18h]
0x18000e9af  mov     [rbp+var_40], rax
0x18000e9b3  mov     eax, [rdi]
0x18000e9b5  mov     [rbp+var_7C], eax
0x18000e9b8  mov     rax, [rdi+80h]
0x18000e9bf  mov     [rbp+var_38], rax
0x18000e9c3  mov     eax, [rdi+40h]
0x18000e9c6  mov     [rbp+var_78], eax
0x18000e9c9  mov     rax, [rdi+38h]
0x18000e9cd  mov     [rbp+var_30], rax
0x18000e9d1  mov     eax, [rdi+8]
0x18000e9d4  mov     [rbp+var_74], eax
0x18000e9d7  lea     rax, [rbp+var_70]
0x18000e9db  mov     [rsp+140h+var_90], rax
0x18000e9e3  lea     rax, [rbp+arg_0]
0x18000e9e7  mov     [rsp+140h+var_98], rax
0x18000e9ef  lea     rax, [rbp+arg_8]
0x18000e9f3  mov     [rsp+140h+var_A0], rax
0x18000e9fb  lea     rax, [rbp+var_68]
0x18000e9ff  mov     [rsp+140h+var_A8], rax
0x18000ea07  lea     rax, [rbp+var_60]
0x18000ea0b  mov     [rsp+140h+var_B0], rax
0x18000ea13  lea     rax, [rbp+arg_10]
0x18000ea17  mov     [rsp+140h+var_B8], rax
0x18000ea1f  lea     rax, [rbp+var_58]
0x18000ea23  mov     [rsp+140h+var_C0], rax
0x18000ea2b  lea     rax, [rbp+var_50]
0x18000ea2f  mov     [rsp+140h+var_C8], rax
0x18000ea34  lea     rax, [rbp+arg_18]
0x18000ea38  mov     [rsp+140h+var_D0], rax
0x18000ea3d  lea     rax, [rbp+var_48]
0x18000ea41  mov     [rsp+140h+var_D8], rax
0x18000ea46  lea     rax, [rbp+var_80]
0x18000ea4a  mov     [rsp+140h+var_E0], rax
0x18000ea4f  lea     rax, [rbp+var_40]
0x18000ea53  mov     [rsp+140h+var_E8], rax
0x18000ea58  lea     rax, [rbp+var_7C]
0x18000ea5c  mov     [rsp+140h+var_F0], rax
0x18000ea61  lea     rax, [rbp+var_38]
0x18000ea65  mov     [rsp+140h+var_F8], rax
0x18000ea6a  lea     rax, [rbp+var_78]
0x18000ea6e  mov     [rsp+140h+var_100], rax
0x18000ea73  lea     rax, [rbp+var_30]
0x18000ea77  mov     [rsp+140h+var_108], rax
0x18000ea7c  lea     rax, [rbp+var_74]
0x18000ea80  mov     [rbp+var_70], rcx
0x18000ea84  mov     ecx, [rdi+44h]
0x18000ea87  mov     [rsp+140h+var_110], rax
0x18000ea8c  lea     rax, [rbp+var_28]
0x18000ea90  mov     [rbp+arg_0], ecx
0x18000ea93  mov     ecx, [rdi+10h]
0x18000ea96  mov     [rbp+arg_8], ecx
0x18000ea99  mov     rcx, [rdi+78h]
0x18000ea9d  mov     [rsp+140h+var_118], rax
0x18000eaa2  lea     rax, [rbp+var_20]
0x18000eaa6  mov     [rbp+var_68], rcx
0x18000eaaa  mov     rcx, r9
0x18000eaad  mov     [rsp+140h+var_120], rax
0x18000eab2  mov     [rbp+var_28], 1000000h
0x18000eaba  mov     [rbp+var_20], 0
0x18000eac2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000eac7  jmp     short loc_18000EB2A
0x18000eac9  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000eace  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000ead3  mov     rdi, rax
0x18000ead6  mov     ecx, [rax]
0x18000ead8  cmp     ecx, 5
0x18000eadb  jbe     short loc_18000EB2A
0x18000eadd  call    cs:__imp_GetCurrentThreadId
0x18000eae3  mov     r8, [rbx+110h]
0x18000eaea  lea     rdx, unk_180033289
0x18000eaf1  mov     [rbp+arg_0], eax
0x18000eaf4  lea     rax, [rbp+arg_0]
0x18000eaf8  mov     [rsp+140h+var_110], rax
0x18000eafd  lea     rax, [rbp+arg_8]
0x18000eb01  mov     [rsp+140h+var_118], rax
0x18000eb06  lea     rax, [rbp+arg_10]
0x18000eb0a  mov     ecx, [r8+48h]
0x18000eb0e  add     r8, 8
0x18000eb12  mov     [rbp+arg_8], ecx
0x18000eb15  mov     rcx, rdi
0x18000eb18  mov     [rsp+140h+var_120], rax
0x18000eb1d  mov     [rbp+arg_10], 0
0x18000eb25  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000eb2a  mov     rcx, rbx
0x18000eb2d  add     rsp, 130h
0x18000eb34  pop     rdi
0x18000eb35  pop     rbx
0x18000eb36  pop     rbp
0x18000eb37  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
