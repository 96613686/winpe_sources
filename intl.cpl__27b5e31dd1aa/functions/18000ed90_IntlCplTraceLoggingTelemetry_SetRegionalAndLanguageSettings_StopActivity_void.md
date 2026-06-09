# IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::StopActivity(void)

- ea: `0x18000ed90`
- end: `0x18000efbc`
- name: `?StopActivity@SetRegionalAndLanguageSettings@IntlCplTraceLoggingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001910`
- `0x180001c94`
- `0x1800093fc`
- `0x18000d524`
- `0x18000ed90`
- `0x18000f5b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef5d`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::StopActivity(
        IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings *this)
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
        (unsigned int)&unk_180032F84,
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
        (unsigned int)&unk_1800330DD,
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
0x18000ed90  push    rbp
0x18000ed92  push    rbx
0x18000ed93  push    rdi
0x18000ed94  lea     rbp, [rsp+10h]
0x18000ed99  sub     rsp, 130h
0x18000eda0  mov     rdi, [rcx+110h]
0x18000eda7  mov     rbx, rcx
0x18000edaa  mov     eax, [rdi+48h]
0x18000edad  test    eax, eax
0x18000edaf  jns     loc_18000EF49
0x18000edb5  add     rdi, 50h ; 'P'
0x18000edb9  cmp     eax, [rdi+8]
0x18000edbc  jnz     loc_18000EF49
0x18000edc2  test    rdi, rdi
0x18000edc5  jz      loc_18000EF49
0x18000edcb  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000edd0  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000edd5  mov     r9, rax
0x18000edd8  mov     ecx, [rax]
0x18000edda  cmp     ecx, 5
0x18000eddd  jbe     loc_18000EFAA
0x18000ede3  mov     rax, [rdi+70h]
0x18000ede7  lea     rdx, unk_180032F84
0x18000edee  mov     rcx, [rdi+30h]
0x18000edf2  mov     [rbp+var_60], rax
0x18000edf6  mov     eax, [rdi+68h]
0x18000edf9  mov     r8, [rbx+110h]
0x18000ee00  mov     dword ptr [rbp+arg_10], eax
0x18000ee03  add     r8, 8
0x18000ee07  mov     rax, [rdi+60h]
0x18000ee0b  mov     [rbp+var_58], rax
0x18000ee0f  mov     rax, [rdi+58h]
0x18000ee13  mov     [rbp+var_50], rax
0x18000ee17  mov     eax, [rdi+50h]
0x18000ee1a  mov     [rbp+arg_18], eax
0x18000ee1d  mov     rax, [rdi+48h]
0x18000ee21  mov     [rbp+var_48], rax
0x18000ee25  mov     eax, [rdi+20h]
0x18000ee28  mov     [rbp+var_80], eax
0x18000ee2b  mov     rax, [rdi+18h]
0x18000ee2f  mov     [rbp+var_40], rax
0x18000ee33  mov     eax, [rdi]
0x18000ee35  mov     [rbp+var_7C], eax
0x18000ee38  mov     rax, [rdi+80h]
0x18000ee3f  mov     [rbp+var_38], rax
0x18000ee43  mov     eax, [rdi+40h]
0x18000ee46  mov     [rbp+var_78], eax
0x18000ee49  mov     rax, [rdi+38h]
0x18000ee4d  mov     [rbp+var_30], rax
0x18000ee51  mov     eax, [rdi+8]
0x18000ee54  mov     [rbp+var_74], eax
0x18000ee57  lea     rax, [rbp+var_70]
0x18000ee5b  mov     [rsp+140h+var_90], rax
0x18000ee63  lea     rax, [rbp+arg_0]
0x18000ee67  mov     [rsp+140h+var_98], rax
0x18000ee6f  lea     rax, [rbp+arg_8]
0x18000ee73  mov     [rsp+140h+var_A0], rax
0x18000ee7b  lea     rax, [rbp+var_68]
0x18000ee7f  mov     [rsp+140h+var_A8], rax
0x18000ee87  lea     rax, [rbp+var_60]
0x18000ee8b  mov     [rsp+140h+var_B0], rax
0x18000ee93  lea     rax, [rbp+arg_10]
0x18000ee97  mov     [rsp+140h+var_B8], rax
0x18000ee9f  lea     rax, [rbp+var_58]
0x18000eea3  mov     [rsp+140h+var_C0], rax
0x18000eeab  lea     rax, [rbp+var_50]
0x18000eeaf  mov     [rsp+140h+var_C8], rax
0x18000eeb4  lea     rax, [rbp+arg_18]
0x18000eeb8  mov     [rsp+140h+var_D0], rax
0x18000eebd  lea     rax, [rbp+var_48]
0x18000eec1  mov     [rsp+140h+var_D8], rax
0x18000eec6  lea     rax, [rbp+var_80]
0x18000eeca  mov     [rsp+140h+var_E0], rax
0x18000eecf  lea     rax, [rbp+var_40]
0x18000eed3  mov     [rsp+140h+var_E8], rax
0x18000eed8  lea     rax, [rbp+var_7C]
0x18000eedc  mov     [rsp+140h+var_F0], rax
0x18000eee1  lea     rax, [rbp+var_38]
0x18000eee5  mov     [rsp+140h+var_F8], rax
0x18000eeea  lea     rax, [rbp+var_78]
0x18000eeee  mov     [rsp+140h+var_100], rax
0x18000eef3  lea     rax, [rbp+var_30]
0x18000eef7  mov     [rsp+140h+var_108], rax
0x18000eefc  lea     rax, [rbp+var_74]
0x18000ef00  mov     [rbp+var_70], rcx
0x18000ef04  mov     ecx, [rdi+44h]
0x18000ef07  mov     [rsp+140h+var_110], rax
0x18000ef0c  lea     rax, [rbp+var_28]
0x18000ef10  mov     [rbp+arg_0], ecx
0x18000ef13  mov     ecx, [rdi+10h]
0x18000ef16  mov     [rbp+arg_8], ecx
0x18000ef19  mov     rcx, [rdi+78h]
0x18000ef1d  mov     [rsp+140h+var_118], rax
0x18000ef22  lea     rax, [rbp+var_20]
0x18000ef26  mov     [rbp+var_68], rcx
0x18000ef2a  mov     rcx, r9
0x18000ef2d  mov     [rsp+140h+var_120], rax
0x18000ef32  mov     [rbp+var_28], 1000000h
0x18000ef3a  mov     [rbp+var_20], 0
0x18000ef42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ef47  jmp     short loc_18000EFAA
0x18000ef49  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000ef4e  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000ef53  mov     rdi, rax
0x18000ef56  mov     ecx, [rax]
0x18000ef58  cmp     ecx, 5
0x18000ef5b  jbe     short loc_18000EFAA
0x18000ef5d  call    cs:__imp_GetCurrentThreadId
0x18000ef63  mov     r8, [rbx+110h]
0x18000ef6a  lea     rdx, unk_1800330DD
0x18000ef71  mov     [rbp+arg_0], eax
0x18000ef74  lea     rax, [rbp+arg_0]
0x18000ef78  mov     [rsp+140h+var_110], rax
0x18000ef7d  lea     rax, [rbp+arg_8]
0x18000ef81  mov     [rsp+140h+var_118], rax
0x18000ef86  lea     rax, [rbp+arg_10]
0x18000ef8a  mov     ecx, [r8+48h]
0x18000ef8e  add     r8, 8
0x18000ef92  mov     [rbp+arg_8], ecx
0x18000ef95  mov     rcx, rdi
0x18000ef98  mov     [rsp+140h+var_120], rax
0x18000ef9d  mov     [rbp+arg_10], 0
0x18000efa5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000efaa  mov     rcx, rbx
0x18000efad  add     rsp, 130h
0x18000efb4  pop     rdi
0x18000efb5  pop     rbx
0x18000efb6  pop     rbp
0x18000efb7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
