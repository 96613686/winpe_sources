# FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::StopActivity(void)

- ea: `0x18000d0b0`
- end: `0x18000d2dc`
- name: `?StopActivity@_MakeFacePidlFromFmsId@FontFldrTraceLoggingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001314`
- `0x180001698`
- `0x180009328`
- `0x180009930`
- `0x18000d0b0`
- `0x180010420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d27d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d27d`

## pseudocode

```c
void __fastcall FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::StopActivity(
        FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId *this)
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
        (unsigned int)&word_18003BD06,
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
        (unsigned int)&byte_18003BCAF,
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
0x18000d0b0  push    rbp
0x18000d0b2  push    rbx
0x18000d0b3  push    rdi
0x18000d0b4  lea     rbp, [rsp+10h]
0x18000d0b9  sub     rsp, 130h
0x18000d0c0  mov     rdi, [rcx+110h]
0x18000d0c7  mov     rbx, rcx
0x18000d0ca  mov     eax, [rdi+48h]
0x18000d0cd  test    eax, eax
0x18000d0cf  jns     loc_18000D269
0x18000d0d5  add     rdi, 50h ; 'P'
0x18000d0d9  cmp     eax, [rdi+8]
0x18000d0dc  jnz     loc_18000D269
0x18000d0e2  test    rdi, rdi
0x18000d0e5  jz      loc_18000D269
0x18000d0eb  call    ?zInternalStop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d0f0  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000d0f5  mov     r9, rax
0x18000d0f8  mov     ecx, [rax]
0x18000d0fa  cmp     ecx, 5
0x18000d0fd  jbe     loc_18000D2CA
0x18000d103  mov     rax, [rdi+70h]
0x18000d107  lea     rdx, word_18003BD06
0x18000d10e  mov     rcx, [rdi+30h]
0x18000d112  mov     [rbp+var_60], rax
0x18000d116  mov     eax, [rdi+68h]
0x18000d119  mov     r8, [rbx+110h]
0x18000d120  mov     dword ptr [rbp+arg_10], eax
0x18000d123  add     r8, 8
0x18000d127  mov     rax, [rdi+60h]
0x18000d12b  mov     [rbp+var_58], rax
0x18000d12f  mov     rax, [rdi+58h]
0x18000d133  mov     [rbp+var_50], rax
0x18000d137  mov     eax, [rdi+50h]
0x18000d13a  mov     [rbp+arg_18], eax
0x18000d13d  mov     rax, [rdi+48h]
0x18000d141  mov     [rbp+var_48], rax
0x18000d145  mov     eax, [rdi+20h]
0x18000d148  mov     [rbp+var_80], eax
0x18000d14b  mov     rax, [rdi+18h]
0x18000d14f  mov     [rbp+var_40], rax
0x18000d153  mov     eax, [rdi]
0x18000d155  mov     [rbp+var_7C], eax
0x18000d158  mov     rax, [rdi+80h]
0x18000d15f  mov     [rbp+var_38], rax
0x18000d163  mov     eax, [rdi+40h]
0x18000d166  mov     [rbp+var_78], eax
0x18000d169  mov     rax, [rdi+38h]
0x18000d16d  mov     [rbp+var_30], rax
0x18000d171  mov     eax, [rdi+8]
0x18000d174  mov     [rbp+var_74], eax
0x18000d177  lea     rax, [rbp+var_70]
0x18000d17b  mov     [rsp+140h+var_90], rax
0x18000d183  lea     rax, [rbp+arg_0]
0x18000d187  mov     [rsp+140h+var_98], rax
0x18000d18f  lea     rax, [rbp+arg_8]
0x18000d193  mov     [rsp+140h+var_A0], rax
0x18000d19b  lea     rax, [rbp+var_68]
0x18000d19f  mov     [rsp+140h+var_A8], rax
0x18000d1a7  lea     rax, [rbp+var_60]
0x18000d1ab  mov     [rsp+140h+var_B0], rax
0x18000d1b3  lea     rax, [rbp+arg_10]
0x18000d1b7  mov     [rsp+140h+var_B8], rax
0x18000d1bf  lea     rax, [rbp+var_58]
0x18000d1c3  mov     [rsp+140h+var_C0], rax
0x18000d1cb  lea     rax, [rbp+var_50]
0x18000d1cf  mov     [rsp+140h+var_C8], rax
0x18000d1d4  lea     rax, [rbp+arg_18]
0x18000d1d8  mov     [rsp+140h+var_D0], rax
0x18000d1dd  lea     rax, [rbp+var_48]
0x18000d1e1  mov     [rsp+140h+var_D8], rax
0x18000d1e6  lea     rax, [rbp+var_80]
0x18000d1ea  mov     [rsp+140h+var_E0], rax
0x18000d1ef  lea     rax, [rbp+var_40]
0x18000d1f3  mov     [rsp+140h+var_E8], rax
0x18000d1f8  lea     rax, [rbp+var_7C]
0x18000d1fc  mov     [rsp+140h+var_F0], rax
0x18000d201  lea     rax, [rbp+var_38]
0x18000d205  mov     [rsp+140h+var_F8], rax
0x18000d20a  lea     rax, [rbp+var_78]
0x18000d20e  mov     [rsp+140h+var_100], rax
0x18000d213  lea     rax, [rbp+var_30]
0x18000d217  mov     [rsp+140h+var_108], rax
0x18000d21c  lea     rax, [rbp+var_74]
0x18000d220  mov     [rbp+var_70], rcx
0x18000d224  mov     ecx, [rdi+44h]
0x18000d227  mov     [rsp+140h+var_110], rax
0x18000d22c  lea     rax, [rbp+var_28]
0x18000d230  mov     [rbp+arg_0], ecx
0x18000d233  mov     ecx, [rdi+10h]
0x18000d236  mov     [rbp+arg_8], ecx
0x18000d239  mov     rcx, [rdi+78h]
0x18000d23d  mov     [rsp+140h+var_118], rax
0x18000d242  lea     rax, [rbp+var_20]
0x18000d246  mov     [rbp+var_68], rcx
0x18000d24a  mov     rcx, r9
0x18000d24d  mov     [rsp+140h+var_120], rax
0x18000d252  mov     [rbp+var_28], 1000000h
0x18000d25a  mov     [rbp+var_20], 0
0x18000d262  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000d267  jmp     short loc_18000D2CA
0x18000d269  call    ?zInternalStop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d26e  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000d273  mov     rdi, rax
0x18000d276  mov     ecx, [rax]
0x18000d278  cmp     ecx, 5
0x18000d27b  jbe     short loc_18000D2CA
0x18000d27d  call    cs:__imp_GetCurrentThreadId
0x18000d283  mov     r8, [rbx+110h]
0x18000d28a  lea     rdx, byte_18003BCAF
0x18000d291  mov     [rbp+arg_0], eax
0x18000d294  lea     rax, [rbp+arg_0]
0x18000d298  mov     [rsp+140h+var_110], rax
0x18000d29d  lea     rax, [rbp+arg_8]
0x18000d2a1  mov     [rsp+140h+var_118], rax
0x18000d2a6  lea     rax, [rbp+arg_10]
0x18000d2aa  mov     ecx, [r8+48h]
0x18000d2ae  add     r8, 8
0x18000d2b2  mov     [rbp+arg_8], ecx
0x18000d2b5  mov     rcx, rdi
0x18000d2b8  mov     [rsp+140h+var_120], rax
0x18000d2bd  mov     [rbp+arg_10], 0
0x18000d2c5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d2ca  mov     rcx, rbx
0x18000d2cd  add     rsp, 130h
0x18000d2d4  pop     rdi
0x18000d2d5  pop     rbx
0x18000d2d6  pop     rbp
0x18000d2d7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
