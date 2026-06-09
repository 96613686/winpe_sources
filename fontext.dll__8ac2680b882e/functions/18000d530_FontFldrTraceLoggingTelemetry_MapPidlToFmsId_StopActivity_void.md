# FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::StopActivity(void)

- ea: `0x18000d530`
- end: `0x18000d75c`
- name: `?StopActivity@_MapPidlToFmsId@FontFldrTraceLoggingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontFldrTraceLoggingTelemetry::_MapPidlToFmsId *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001314`
- `0x180001698`
- `0x180009328`
- `0x180009930`
- `0x18000d530`
- `0x180010420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6fd`

## pseudocode

```c
void __fastcall FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::StopActivity(
        FontFldrTraceLoggingTelemetry::_MapPidlToFmsId *this)
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
    wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = FontFldrTraceLogging::Provider();
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
        (unsigned int)&dword_18003CC84,
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
    wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = FontFldrTraceLogging::Provider();
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
        (unsigned int)&dword_18003CC34,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x18000d530  push    rbp
0x18000d532  push    rbx
0x18000d533  push    rdi
0x18000d534  lea     rbp, [rsp+10h]
0x18000d539  sub     rsp, 130h
0x18000d540  mov     rdi, [rcx+110h]
0x18000d547  mov     rbx, rcx
0x18000d54a  mov     eax, [rdi+48h]
0x18000d54d  test    eax, eax
0x18000d54f  jns     loc_18000D6E9
0x18000d555  add     rdi, 50h ; 'P'
0x18000d559  cmp     eax, [rdi+8]
0x18000d55c  jnz     loc_18000D6E9
0x18000d562  test    rdi, rdi
0x18000d565  jz      loc_18000D6E9
0x18000d56b  call    ?zInternalStop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d570  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000d575  mov     r9, rax
0x18000d578  mov     ecx, [rax]
0x18000d57a  cmp     ecx, 5
0x18000d57d  jbe     loc_18000D74A
0x18000d583  mov     rax, [rdi+70h]
0x18000d587  lea     rdx, dword_18003CC84
0x18000d58e  mov     rcx, [rdi+30h]
0x18000d592  mov     [rbp+var_60], rax
0x18000d596  mov     eax, [rdi+68h]
0x18000d599  mov     r8, [rbx+110h]
0x18000d5a0  mov     dword ptr [rbp+arg_10], eax
0x18000d5a3  add     r8, 8
0x18000d5a7  mov     rax, [rdi+60h]
0x18000d5ab  mov     [rbp+var_58], rax
0x18000d5af  mov     rax, [rdi+58h]
0x18000d5b3  mov     [rbp+var_50], rax
0x18000d5b7  mov     eax, [rdi+50h]
0x18000d5ba  mov     [rbp+arg_18], eax
0x18000d5bd  mov     rax, [rdi+48h]
0x18000d5c1  mov     [rbp+var_48], rax
0x18000d5c5  mov     eax, [rdi+20h]
0x18000d5c8  mov     [rbp+var_80], eax
0x18000d5cb  mov     rax, [rdi+18h]
0x18000d5cf  mov     [rbp+var_40], rax
0x18000d5d3  mov     eax, [rdi]
0x18000d5d5  mov     [rbp+var_7C], eax
0x18000d5d8  mov     rax, [rdi+80h]
0x18000d5df  mov     [rbp+var_38], rax
0x18000d5e3  mov     eax, [rdi+40h]
0x18000d5e6  mov     [rbp+var_78], eax
0x18000d5e9  mov     rax, [rdi+38h]
0x18000d5ed  mov     [rbp+var_30], rax
0x18000d5f1  mov     eax, [rdi+8]
0x18000d5f4  mov     [rbp+var_74], eax
0x18000d5f7  lea     rax, [rbp+var_70]
0x18000d5fb  mov     [rsp+140h+var_90], rax
0x18000d603  lea     rax, [rbp+arg_0]
0x18000d607  mov     [rsp+140h+var_98], rax
0x18000d60f  lea     rax, [rbp+arg_8]
0x18000d613  mov     [rsp+140h+var_A0], rax
0x18000d61b  lea     rax, [rbp+var_68]
0x18000d61f  mov     [rsp+140h+var_A8], rax
0x18000d627  lea     rax, [rbp+var_60]
0x18000d62b  mov     [rsp+140h+var_B0], rax
0x18000d633  lea     rax, [rbp+arg_10]
0x18000d637  mov     [rsp+140h+var_B8], rax
0x18000d63f  lea     rax, [rbp+var_58]
0x18000d643  mov     [rsp+140h+var_C0], rax
0x18000d64b  lea     rax, [rbp+var_50]
0x18000d64f  mov     [rsp+140h+var_C8], rax
0x18000d654  lea     rax, [rbp+arg_18]
0x18000d658  mov     [rsp+140h+var_D0], rax
0x18000d65d  lea     rax, [rbp+var_48]
0x18000d661  mov     [rsp+140h+var_D8], rax
0x18000d666  lea     rax, [rbp+var_80]
0x18000d66a  mov     [rsp+140h+var_E0], rax
0x18000d66f  lea     rax, [rbp+var_40]
0x18000d673  mov     [rsp+140h+var_E8], rax
0x18000d678  lea     rax, [rbp+var_7C]
0x18000d67c  mov     [rsp+140h+var_F0], rax
0x18000d681  lea     rax, [rbp+var_38]
0x18000d685  mov     [rsp+140h+var_F8], rax
0x18000d68a  lea     rax, [rbp+var_78]
0x18000d68e  mov     [rsp+140h+var_100], rax
0x18000d693  lea     rax, [rbp+var_30]
0x18000d697  mov     [rsp+140h+var_108], rax
0x18000d69c  lea     rax, [rbp+var_74]
0x18000d6a0  mov     [rbp+var_70], rcx
0x18000d6a4  mov     ecx, [rdi+44h]
0x18000d6a7  mov     [rsp+140h+var_110], rax
0x18000d6ac  lea     rax, [rbp+var_28]
0x18000d6b0  mov     [rbp+arg_0], ecx
0x18000d6b3  mov     ecx, [rdi+10h]
0x18000d6b6  mov     [rbp+arg_8], ecx
0x18000d6b9  mov     rcx, [rdi+78h]
0x18000d6bd  mov     [rsp+140h+var_118], rax
0x18000d6c2  lea     rax, [rbp+var_20]
0x18000d6c6  mov     [rbp+var_68], rcx
0x18000d6ca  mov     rcx, r9
0x18000d6cd  mov     [rsp+140h+var_120], rax
0x18000d6d2  mov     [rbp+var_28], 1000000h
0x18000d6da  mov     [rbp+var_20], 0
0x18000d6e2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000d6e7  jmp     short loc_18000D74A
0x18000d6e9  call    ?zInternalStop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d6ee  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000d6f3  mov     rdi, rax
0x18000d6f6  mov     ecx, [rax]
0x18000d6f8  cmp     ecx, 5
0x18000d6fb  jbe     short loc_18000D74A
0x18000d6fd  call    cs:__imp_GetCurrentThreadId
0x18000d703  mov     r8, [rbx+110h]
0x18000d70a  lea     rdx, dword_18003CC34
0x18000d711  mov     [rbp+arg_0], eax
0x18000d714  lea     rax, [rbp+arg_0]
0x18000d718  mov     [rsp+140h+var_110], rax
0x18000d71d  lea     rax, [rbp+arg_8]
0x18000d721  mov     [rsp+140h+var_118], rax
0x18000d726  lea     rax, [rbp+arg_10]
0x18000d72a  mov     ecx, [r8+48h]
0x18000d72e  add     r8, 8
0x18000d732  mov     [rbp+arg_8], ecx
0x18000d735  mov     rcx, rdi
0x18000d738  mov     [rsp+140h+var_120], rax
0x18000d73d  mov     [rbp+arg_10], 0
0x18000d745  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d74a  mov     rcx, rbx
0x18000d74d  add     rsp, 130h
0x18000d754  pop     rdi
0x18000d755  pop     rbx
0x18000d756  pop     rbp
0x18000d757  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
