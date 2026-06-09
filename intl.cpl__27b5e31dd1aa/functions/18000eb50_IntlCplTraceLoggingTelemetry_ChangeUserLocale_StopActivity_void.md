# IntlCplTraceLoggingTelemetry::ChangeUserLocale::StopActivity(void)

- ea: `0x18000eb50`
- end: `0x18000ed7c`
- name: `?StopActivity@ChangeUserLocale@IntlCplTraceLoggingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::ChangeUserLocale *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001910`
- `0x180001c94`
- `0x1800093fc`
- `0x18000d524`
- `0x18000eb50`
- `0x18000f5b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed1d`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::ChangeUserLocale::StopActivity(
        IntlCplTraceLoggingTelemetry::ChangeUserLocale *this)
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
        (unsigned int)&unk_180033582,
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
        (unsigned int)&unk_1800336CD,
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
0x18000eb50  push    rbp
0x18000eb52  push    rbx
0x18000eb53  push    rdi
0x18000eb54  lea     rbp, [rsp+10h]
0x18000eb59  sub     rsp, 130h
0x18000eb60  mov     rdi, [rcx+110h]
0x18000eb67  mov     rbx, rcx
0x18000eb6a  mov     eax, [rdi+48h]
0x18000eb6d  test    eax, eax
0x18000eb6f  jns     loc_18000ED09
0x18000eb75  add     rdi, 50h ; 'P'
0x18000eb79  cmp     eax, [rdi+8]
0x18000eb7c  jnz     loc_18000ED09
0x18000eb82  test    rdi, rdi
0x18000eb85  jz      loc_18000ED09
0x18000eb8b  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000eb90  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000eb95  mov     r9, rax
0x18000eb98  mov     ecx, [rax]
0x18000eb9a  cmp     ecx, 5
0x18000eb9d  jbe     loc_18000ED6A
0x18000eba3  mov     rax, [rdi+70h]
0x18000eba7  lea     rdx, unk_180033582
0x18000ebae  mov     rcx, [rdi+30h]
0x18000ebb2  mov     [rbp+var_60], rax
0x18000ebb6  mov     eax, [rdi+68h]
0x18000ebb9  mov     r8, [rbx+110h]
0x18000ebc0  mov     dword ptr [rbp+arg_10], eax
0x18000ebc3  add     r8, 8
0x18000ebc7  mov     rax, [rdi+60h]
0x18000ebcb  mov     [rbp+var_58], rax
0x18000ebcf  mov     rax, [rdi+58h]
0x18000ebd3  mov     [rbp+var_50], rax
0x18000ebd7  mov     eax, [rdi+50h]
0x18000ebda  mov     [rbp+arg_18], eax
0x18000ebdd  mov     rax, [rdi+48h]
0x18000ebe1  mov     [rbp+var_48], rax
0x18000ebe5  mov     eax, [rdi+20h]
0x18000ebe8  mov     [rbp+var_80], eax
0x18000ebeb  mov     rax, [rdi+18h]
0x18000ebef  mov     [rbp+var_40], rax
0x18000ebf3  mov     eax, [rdi]
0x18000ebf5  mov     [rbp+var_7C], eax
0x18000ebf8  mov     rax, [rdi+80h]
0x18000ebff  mov     [rbp+var_38], rax
0x18000ec03  mov     eax, [rdi+40h]
0x18000ec06  mov     [rbp+var_78], eax
0x18000ec09  mov     rax, [rdi+38h]
0x18000ec0d  mov     [rbp+var_30], rax
0x18000ec11  mov     eax, [rdi+8]
0x18000ec14  mov     [rbp+var_74], eax
0x18000ec17  lea     rax, [rbp+var_70]
0x18000ec1b  mov     [rsp+140h+var_90], rax
0x18000ec23  lea     rax, [rbp+arg_0]
0x18000ec27  mov     [rsp+140h+var_98], rax
0x18000ec2f  lea     rax, [rbp+arg_8]
0x18000ec33  mov     [rsp+140h+var_A0], rax
0x18000ec3b  lea     rax, [rbp+var_68]
0x18000ec3f  mov     [rsp+140h+var_A8], rax
0x18000ec47  lea     rax, [rbp+var_60]
0x18000ec4b  mov     [rsp+140h+var_B0], rax
0x18000ec53  lea     rax, [rbp+arg_10]
0x18000ec57  mov     [rsp+140h+var_B8], rax
0x18000ec5f  lea     rax, [rbp+var_58]
0x18000ec63  mov     [rsp+140h+var_C0], rax
0x18000ec6b  lea     rax, [rbp+var_50]
0x18000ec6f  mov     [rsp+140h+var_C8], rax
0x18000ec74  lea     rax, [rbp+arg_18]
0x18000ec78  mov     [rsp+140h+var_D0], rax
0x18000ec7d  lea     rax, [rbp+var_48]
0x18000ec81  mov     [rsp+140h+var_D8], rax
0x18000ec86  lea     rax, [rbp+var_80]
0x18000ec8a  mov     [rsp+140h+var_E0], rax
0x18000ec8f  lea     rax, [rbp+var_40]
0x18000ec93  mov     [rsp+140h+var_E8], rax
0x18000ec98  lea     rax, [rbp+var_7C]
0x18000ec9c  mov     [rsp+140h+var_F0], rax
0x18000eca1  lea     rax, [rbp+var_38]
0x18000eca5  mov     [rsp+140h+var_F8], rax
0x18000ecaa  lea     rax, [rbp+var_78]
0x18000ecae  mov     [rsp+140h+var_100], rax
0x18000ecb3  lea     rax, [rbp+var_30]
0x18000ecb7  mov     [rsp+140h+var_108], rax
0x18000ecbc  lea     rax, [rbp+var_74]
0x18000ecc0  mov     [rbp+var_70], rcx
0x18000ecc4  mov     ecx, [rdi+44h]
0x18000ecc7  mov     [rsp+140h+var_110], rax
0x18000eccc  lea     rax, [rbp+var_28]
0x18000ecd0  mov     [rbp+arg_0], ecx
0x18000ecd3  mov     ecx, [rdi+10h]
0x18000ecd6  mov     [rbp+arg_8], ecx
0x18000ecd9  mov     rcx, [rdi+78h]
0x18000ecdd  mov     [rsp+140h+var_118], rax
0x18000ece2  lea     rax, [rbp+var_20]
0x18000ece6  mov     [rbp+var_68], rcx
0x18000ecea  mov     rcx, r9
0x18000eced  mov     [rsp+140h+var_120], rax
0x18000ecf2  mov     [rbp+var_28], 1000000h
0x18000ecfa  mov     [rbp+var_20], 0
0x18000ed02  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ed07  jmp     short loc_18000ED6A
0x18000ed09  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000ed0e  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000ed13  mov     rdi, rax
0x18000ed16  mov     ecx, [rax]
0x18000ed18  cmp     ecx, 5
0x18000ed1b  jbe     short loc_18000ED6A
0x18000ed1d  call    cs:__imp_GetCurrentThreadId
0x18000ed23  mov     r8, [rbx+110h]
0x18000ed2a  lea     rdx, unk_1800336CD
0x18000ed31  mov     [rbp+arg_0], eax
0x18000ed34  lea     rax, [rbp+arg_0]
0x18000ed38  mov     [rsp+140h+var_110], rax
0x18000ed3d  lea     rax, [rbp+arg_8]
0x18000ed41  mov     [rsp+140h+var_118], rax
0x18000ed46  lea     rax, [rbp+arg_10]
0x18000ed4a  mov     ecx, [r8+48h]
0x18000ed4e  add     r8, 8
0x18000ed52  mov     [rbp+arg_8], ecx
0x18000ed55  mov     rcx, rdi
0x18000ed58  mov     [rsp+140h+var_120], rax
0x18000ed5d  mov     [rbp+arg_10], 0
0x18000ed65  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ed6a  mov     rcx, rbx
0x18000ed6d  add     rsp, 130h
0x18000ed74  pop     rdi
0x18000ed75  pop     rbx
0x18000ed76  pop     rbp
0x18000ed77  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
