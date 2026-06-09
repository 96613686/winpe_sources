# IntlCplTraceLoggingTelemetry::OpeningIntlCpl::StopActivity(void)

- ea: `0x180016ee0`
- end: `0x180017104`
- name: `?StopActivity@OpeningIntlCpl@IntlCplTraceLoggingTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::OpeningIntlCpl *__hidden this)`
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
- `0x180016ee0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170a5`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::OpeningIntlCpl::StopActivity(
        IntlCplTraceLoggingTelemetry::OpeningIntlCpl *this)
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
        (unsigned int)&unk_180033BC8,
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
        (unsigned int)&unk_180033CEE,
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
0x180016ee0  push    rbp
0x180016ee2  push    rbx
0x180016ee3  push    rdi
0x180016ee4  lea     rbp, [rsp-47h]
0x180016ee9  sub     rsp, 100h
0x180016ef0  mov     rdi, [rcx+110h]
0x180016ef7  mov     rbx, rcx
0x180016efa  mov     eax, [rdi+48h]
0x180016efd  test    eax, eax
0x180016eff  jns     loc_18001707B
0x180016f05  add     rdi, 50h ; 'P'
0x180016f09  cmp     eax, [rdi+8]
0x180016f0c  jnz     loc_18001707B
0x180016f12  test    rdi, rdi
0x180016f15  jz      loc_18001707B
0x180016f1b  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180016f20  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x180016f25  mov     r9, rax
0x180016f28  mov     ecx, [rax]
0x180016f2a  cmp     ecx, 5
0x180016f2d  jbe     loc_1800170F2
0x180016f33  mov     rdx, 200000000000h
0x180016f3d  mov     rcx, rax
0x180016f40  call    _tlgKeywordOn
0x180016f45  test    al, al
0x180016f47  jz      loc_1800170F2
0x180016f4d  mov     rax, [rdi+70h]
0x180016f51  lea     rdx, unk_180033BC8
0x180016f58  mov     rcx, [rdi+78h]
0x180016f5c  mov     r8, [rbx+110h]
0x180016f63  mov     [rbp+57h+var_60], rax
0x180016f67  add     r8, 8
0x180016f6b  mov     eax, [rdi+68h]
0x180016f6e  mov     [rbp+57h+arg_0], eax
0x180016f71  mov     rax, [rdi+60h]
0x180016f75  mov     [rbp+57h+var_58], rax
0x180016f79  mov     rax, [rdi+58h]
0x180016f7d  mov     [rbp+57h+var_50], rax
0x180016f81  mov     eax, [rdi+50h]
0x180016f84  mov     [rbp+57h+arg_8], eax
0x180016f87  mov     rax, [rdi+48h]
0x180016f8b  mov     [rbp+57h+var_48], rax
0x180016f8f  mov     eax, [rdi+20h]
0x180016f92  mov     dword ptr [rbp+57h+arg_10], eax
0x180016f95  mov     rax, [rdi+18h]
0x180016f99  mov     [rbp+57h+var_40], rax
0x180016f9d  mov     eax, [rdi]
0x180016f9f  mov     [rbp+57h+arg_18], eax
0x180016fa2  mov     rax, [rdi+80h]
0x180016fa9  mov     [rbp+57h+var_38], rax
0x180016fad  mov     eax, [rdi+40h]
0x180016fb0  mov     [rbp+57h+var_70], eax
0x180016fb3  mov     rax, [rdi+38h]
0x180016fb7  mov     [rbp+57h+var_30], rax
0x180016fbb  mov     eax, [rdi+8]
0x180016fbe  mov     [rbp+57h+var_6C], eax
0x180016fc1  lea     rax, [rbp+57h+var_68]
0x180016fc5  mov     [rsp+110h+var_78], rax
0x180016fcd  lea     rax, [rbp+57h+var_60]
0x180016fd1  mov     [rsp+110h+var_80], rax
0x180016fd9  lea     rax, [rbp+57h+arg_0]
0x180016fdd  mov     [rsp+110h+var_88], rax
0x180016fe5  lea     rax, [rbp+57h+var_58]
0x180016fe9  mov     [rsp+110h+var_90], rax
0x180016ff1  lea     rax, [rbp+57h+var_50]
0x180016ff5  mov     [rsp+110h+var_98], rax
0x180016ffa  lea     rax, [rbp+57h+arg_8]
0x180016ffe  mov     [rsp+110h+var_A0], rax
0x180017003  lea     rax, [rbp+57h+var_48]
0x180017007  mov     [rsp+110h+var_A8], rax
0x18001700c  lea     rax, [rbp+57h+arg_10]
0x180017010  mov     [rsp+110h+var_B0], rax
0x180017015  lea     rax, [rbp+57h+var_40]
0x180017019  mov     [rsp+110h+var_B8], rax
0x18001701e  lea     rax, [rbp+57h+arg_18]
0x180017022  mov     [rsp+110h+var_C0], rax
0x180017027  lea     rax, [rbp+57h+var_38]
0x18001702b  mov     [rsp+110h+var_C8], rax
0x180017030  lea     rax, [rbp+57h+var_70]
0x180017034  mov     [rsp+110h+var_D0], rax
0x180017039  lea     rax, [rbp+57h+var_30]
0x18001703d  mov     [rsp+110h+var_D8], rax
0x180017042  lea     rax, [rbp+57h+var_6C]
0x180017046  mov     [rsp+110h+var_E0], rax
0x18001704b  lea     rax, [rbp+57h+var_28]
0x18001704f  mov     [rsp+110h+var_E8], rax
0x180017054  lea     rax, [rbp+57h+var_20]
0x180017058  mov     [rbp+57h+var_68], rcx
0x18001705c  mov     rcx, r9
0x18001705f  mov     [rsp+110h+var_F0], rax
0x180017064  mov     [rbp+57h+var_28], 1000000h
0x18001706c  mov     [rbp+57h+var_20], 0
0x180017074  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180017079  jmp     short loc_1800170F2
0x18001707b  call    ?zInternalStop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180017080  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x180017085  mov     rdi, rax
0x180017088  mov     ecx, [rax]
0x18001708a  cmp     ecx, 5
0x18001708d  jbe     short loc_1800170F2
0x18001708f  mov     rdx, 200000000000h
0x180017099  mov     rcx, rax
0x18001709c  call    _tlgKeywordOn
0x1800170a1  test    al, al
0x1800170a3  jz      short loc_1800170F2
0x1800170a5  call    cs:__imp_GetCurrentThreadId
0x1800170ab  mov     r8, [rbx+110h]
0x1800170b2  lea     rdx, unk_180033CEE
0x1800170b9  mov     [rbp+57h+arg_0], eax
0x1800170bc  mov     rcx, rdi
0x1800170bf  mov     eax, [r8+48h]
0x1800170c3  add     r8, 8
0x1800170c7  mov     [rbp+57h+arg_8], eax
0x1800170ca  lea     rax, [rbp+57h+arg_0]
0x1800170ce  mov     [rsp+110h+var_E0], rax
0x1800170d3  lea     rax, [rbp+57h+arg_8]
0x1800170d7  mov     [rsp+110h+var_E8], rax
0x1800170dc  lea     rax, [rbp+57h+arg_10]
0x1800170e0  mov     [rsp+110h+var_F0], rax
0x1800170e5  mov     [rbp+57h+arg_10], 0
0x1800170ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800170f2  mov     rcx, rbx
0x1800170f5  add     rsp, 100h
0x1800170fc  pop     rdi
0x1800170fd  pop     rbx
0x1800170fe  pop     rbp
0x1800170ff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
