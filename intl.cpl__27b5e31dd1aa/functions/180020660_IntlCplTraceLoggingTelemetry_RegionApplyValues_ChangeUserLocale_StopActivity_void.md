# IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::StopActivity(void)

- ea: `0x180020660`
- end: `0x180020884`
- name: `?StopActivity@RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800010f4`
- `0x1800017fc`
- `0x180001c94`
- `0x1800093fc`
- `0x18000d524`
- `0x18000f5b4`
- `0x180020660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020825`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::StopActivity(
        IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *this)
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
    wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = IntlCplTraceLogging::Provider();
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
        (unsigned int)&unk_1800343BD,
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
    wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = IntlCplTraceLogging::Provider();
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
        (unsigned int)&unk_1800344F7,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180020660  push    rbp
0x180020662  push    rbx
0x180020663  push    rdi
0x180020664  lea     rbp, [rsp-47h]
0x180020669  sub     rsp, 100h
0x180020670  mov     rdi, [rcx+110h]
0x180020677  mov     rbx, rcx
0x18002067a  mov     eax, [rdi+48h]
0x18002067d  test    eax, eax
0x18002067f  jns     loc_1800207FB
0x180020685  add     rdi, 50h ; 'P'
0x180020689  cmp     eax, [rdi+8]
0x18002068c  jnz     loc_1800207FB
0x180020692  test    rdi, rdi
0x180020695  jz      loc_1800207FB
0x18002069b  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800206a0  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x1800206a5  mov     r9, rax
0x1800206a8  mov     ecx, [rax]
0x1800206aa  cmp     ecx, 5
0x1800206ad  jbe     loc_180020872
0x1800206b3  mov     rdx, 200000000000h
0x1800206bd  mov     rcx, rax
0x1800206c0  call    _tlgKeywordOn
0x1800206c5  test    al, al
0x1800206c7  jz      loc_180020872
0x1800206cd  mov     rax, [rdi+70h]
0x1800206d1  lea     rdx, unk_1800343BD
0x1800206d8  mov     rcx, [rdi+78h]
0x1800206dc  mov     r8, [rbx+110h]
0x1800206e3  mov     [rbp+57h+var_60], rax
0x1800206e7  add     r8, 8
0x1800206eb  mov     eax, [rdi+68h]
0x1800206ee  mov     [rbp+57h+arg_0], eax
0x1800206f1  mov     rax, [rdi+60h]
0x1800206f5  mov     [rbp+57h+var_58], rax
0x1800206f9  mov     rax, [rdi+58h]
0x1800206fd  mov     [rbp+57h+var_50], rax
0x180020701  mov     eax, [rdi+50h]
0x180020704  mov     [rbp+57h+arg_8], eax
0x180020707  mov     rax, [rdi+48h]
0x18002070b  mov     [rbp+57h+var_48], rax
0x18002070f  mov     eax, [rdi+20h]
0x180020712  mov     dword ptr [rbp+57h+arg_10], eax
0x180020715  mov     rax, [rdi+18h]
0x180020719  mov     [rbp+57h+var_40], rax
0x18002071d  mov     eax, [rdi]
0x18002071f  mov     [rbp+57h+arg_18], eax
0x180020722  mov     rax, [rdi+80h]
0x180020729  mov     [rbp+57h+var_38], rax
0x18002072d  mov     eax, [rdi+40h]
0x180020730  mov     [rbp+57h+var_70], eax
0x180020733  mov     rax, [rdi+38h]
0x180020737  mov     [rbp+57h+var_30], rax
0x18002073b  mov     eax, [rdi+8]
0x18002073e  mov     [rbp+57h+var_6C], eax
0x180020741  lea     rax, [rbp+57h+var_68]
0x180020745  mov     [rsp+110h+var_78], rax
0x18002074d  lea     rax, [rbp+57h+var_60]
0x180020751  mov     [rsp+110h+var_80], rax
0x180020759  lea     rax, [rbp+57h+arg_0]
0x18002075d  mov     [rsp+110h+var_88], rax
0x180020765  lea     rax, [rbp+57h+var_58]
0x180020769  mov     [rsp+110h+var_90], rax
0x180020771  lea     rax, [rbp+57h+var_50]
0x180020775  mov     [rsp+110h+var_98], rax
0x18002077a  lea     rax, [rbp+57h+arg_8]
0x18002077e  mov     [rsp+110h+var_A0], rax
0x180020783  lea     rax, [rbp+57h+var_48]
0x180020787  mov     [rsp+110h+var_A8], rax
0x18002078c  lea     rax, [rbp+57h+arg_10]
0x180020790  mov     [rsp+110h+var_B0], rax
0x180020795  lea     rax, [rbp+57h+var_40]
0x180020799  mov     [rsp+110h+var_B8], rax
0x18002079e  lea     rax, [rbp+57h+arg_18]
0x1800207a2  mov     [rsp+110h+var_C0], rax
0x1800207a7  lea     rax, [rbp+57h+var_38]
0x1800207ab  mov     [rsp+110h+var_C8], rax
0x1800207b0  lea     rax, [rbp+57h+var_70]
0x1800207b4  mov     [rsp+110h+var_D0], rax
0x1800207b9  lea     rax, [rbp+57h+var_30]
0x1800207bd  mov     [rsp+110h+var_D8], rax
0x1800207c2  lea     rax, [rbp+57h+var_6C]
0x1800207c6  mov     [rsp+110h+var_E0], rax
0x1800207cb  lea     rax, [rbp+57h+var_28]
0x1800207cf  mov     [rsp+110h+var_E8], rax
0x1800207d4  lea     rax, [rbp+57h+var_20]
0x1800207d8  mov     [rbp+57h+var_68], rcx
0x1800207dc  mov     rcx, r9
0x1800207df  mov     [rsp+110h+var_F0], rax
0x1800207e4  mov     [rbp+57h+var_28], 1000000h
0x1800207ec  mov     [rbp+57h+var_20], 0
0x1800207f4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800207f9  jmp     short loc_180020872
0x1800207fb  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020800  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x180020805  mov     rdi, rax
0x180020808  mov     ecx, [rax]
0x18002080a  cmp     ecx, 5
0x18002080d  jbe     short loc_180020872
0x18002080f  mov     rdx, 200000000000h
0x180020819  mov     rcx, rax
0x18002081c  call    _tlgKeywordOn
0x180020821  test    al, al
0x180020823  jz      short loc_180020872
0x180020825  call    cs:__imp_GetCurrentThreadId
0x18002082b  mov     r8, [rbx+110h]
0x180020832  lea     rdx, unk_1800344F7
0x180020839  mov     [rbp+57h+arg_0], eax
0x18002083c  mov     rcx, rdi
0x18002083f  mov     eax, [r8+48h]
0x180020843  add     r8, 8
0x180020847  mov     [rbp+57h+arg_8], eax
0x18002084a  lea     rax, [rbp+57h+arg_0]
0x18002084e  mov     [rsp+110h+var_E0], rax
0x180020853  lea     rax, [rbp+57h+arg_8]
0x180020857  mov     [rsp+110h+var_E8], rax
0x18002085c  lea     rax, [rbp+57h+arg_10]
0x180020860  mov     [rsp+110h+var_F0], rax
0x180020865  mov     [rbp+57h+arg_10], 0
0x18002086d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020872  mov     rcx, rbx
0x180020875  add     rsp, 100h
0x18002087c  pop     rdi
0x18002087d  pop     rbx
0x18002087e  pop     rbp
0x18002087f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
