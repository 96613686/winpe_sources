# wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18000da94`
- end: `0x18000dcd9`
- name: `?ReportStopActivity@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ced0`
- `0x18000e844`

## callees

- `0x1800017fc`
- `0x180001d24`
- `0x180001e20`
- `0x1800093fc`
- `0x18000da94`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dc64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dc64`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  __int64 v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v23; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v26; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v27; // [rsp+E0h] [rbp+27h] BYREF
  _QWORD v28[5]; // [rsp+E8h] [rbp+2Fh] BYREF
  int v29; // [rsp+120h] [rbp+67h] BYREF
  DWORD v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  __int64 v32; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = IntlCplTraceLogging::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
      {
        v9 = *(_QWORD *)(v6 + 120);
        v10 = a1[34];
        v22 = *(_QWORD *)(v6 + 112);
        v30 = *(_DWORD *)(v6 + 104);
        v23 = *(_QWORD *)(v6 + 96);
        v24 = *(_QWORD *)(v6 + 88);
        v29 = *(_DWORD *)(v6 + 80);
        v25 = *(_QWORD *)(v6 + 72);
        LODWORD(v31) = *(_DWORD *)(v6 + 32);
        v26 = *(_QWORD *)(v6 + 24);
        LODWORD(v32) = *(_DWORD *)v6;
        v27 = *(_QWORD *)(v6 + 128);
        v18 = *(_DWORD *)(v6 + 64);
        v28[0] = *(_QWORD *)(v6 + 56);
        v19 = *(_DWORD *)(v6 + 8);
        v21 = v9;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v8,
          (unsigned int)&unk_18003374A,
          v10 + 8,
          v8,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v28,
          (__int64)&v18,
          (__int64)&v27,
          (__int64)&v32,
          (__int64)&v26,
          (__int64)&v31,
          (__int64)&v25,
          (__int64)&v29,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v22,
          (__int64)&v21);
      }
    }
    else
    {
      v11 = IntlCplTraceLogging::Provider();
      v12 = (int)v11;
      if ( *(_DWORD *)v11 > 2u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
      {
        v13 = a1[34];
        v31 = *(_QWORD *)(v13 + 56);
        v32 = *(_QWORD *)(v13 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v15 = a1[34];
        v30 = CurrentThreadId;
        v29 = a2;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)&unk_180033861,
          v15 + 8,
          v16,
          (__int64)&v20,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v32,
          (__int64)&v31);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18000da94  push    rbp
0x18000da96  push    rbx
0x18000da97  push    rsi
0x18000da98  push    rdi
0x18000da99  lea     rbp, [rsp-3Fh]
0x18000da9e  sub     rsp, 0F8h
0x18000daa5  mov     esi, edx
0x18000daa7  mov     rbx, rcx
0x18000daaa  test    edx, edx
0x18000daac  jns     loc_18000DCBF
0x18000dab2  mov     rdi, [rcx+110h]
0x18000dab9  mov     eax, [rdi+48h]
0x18000dabc  test    eax, eax
0x18000dabe  jns     loc_18000DC24
0x18000dac4  add     rdi, 50h ; 'P'
0x18000dac8  cmp     eax, [rdi+8]
0x18000dacb  jnz     loc_18000DC24
0x18000dad1  test    rdi, rdi
0x18000dad4  jz      loc_18000DC24
0x18000dada  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000dadf  mov     r9, rax
0x18000dae2  mov     ecx, [rax]
0x18000dae4  cmp     ecx, 2
0x18000dae7  jbe     loc_18000DCBF
0x18000daed  mov     rdx, 200000000000h
0x18000daf7  mov     rcx, rax
0x18000dafa  call    _tlgKeywordOn
0x18000daff  test    al, al
0x18000db01  jz      loc_18000DCBF
0x18000db07  mov     rax, [rdi+70h]
0x18000db0b  lea     rdx, unk_18003374A
0x18000db12  mov     rcx, [rdi+78h]
0x18000db16  mov     r8, [rbx+110h]
0x18000db1d  mov     [rbp+57h+var_58], rax
0x18000db21  add     r8, 8
0x18000db25  mov     eax, [rdi+68h]
0x18000db28  mov     [rbp+57h+arg_8], eax
0x18000db2b  mov     rax, [rdi+60h]
0x18000db2f  mov     [rbp+57h+var_50], rax
0x18000db33  mov     rax, [rdi+58h]
0x18000db37  mov     [rbp+57h+var_48], rax
0x18000db3b  mov     eax, [rdi+50h]
0x18000db3e  mov     [rbp+57h+arg_0], eax
0x18000db41  mov     rax, [rdi+48h]
0x18000db45  mov     [rbp+57h+var_40], rax
0x18000db49  mov     eax, [rdi+20h]
0x18000db4c  mov     dword ptr [rbp+57h+arg_10], eax
0x18000db4f  mov     rax, [rdi+18h]
0x18000db53  mov     [rbp+57h+var_38], rax
0x18000db57  mov     eax, [rdi]
0x18000db59  mov     dword ptr [rbp+57h+arg_18], eax
0x18000db5c  mov     rax, [rdi+80h]
0x18000db63  mov     [rbp+57h+var_30], rax
0x18000db67  mov     eax, [rdi+40h]
0x18000db6a  mov     [rbp+57h+var_70], eax
0x18000db6d  mov     rax, [rdi+38h]
0x18000db71  mov     [rbp+57h+var_28], rax
0x18000db75  mov     eax, [rdi+8]
0x18000db78  mov     [rbp+57h+var_6C], eax
0x18000db7b  lea     rax, [rbp+57h+var_60]
0x18000db7f  mov     [rsp+110h+var_80], rax
0x18000db87  lea     rax, [rbp+57h+var_58]
0x18000db8b  mov     [rsp+110h+var_88], rax
0x18000db93  lea     rax, [rbp+57h+arg_8]
0x18000db97  mov     [rsp+110h+var_90], rax
0x18000db9f  lea     rax, [rbp+57h+var_50]
0x18000dba3  mov     [rsp+110h+var_98], rax
0x18000dba8  lea     rax, [rbp+57h+var_48]
0x18000dbac  mov     [rsp+110h+var_A0], rax
0x18000dbb1  lea     rax, [rbp+57h+arg_0]
0x18000dbb5  mov     [rsp+110h+var_A8], rax
0x18000dbba  lea     rax, [rbp+57h+var_40]
0x18000dbbe  mov     [rsp+110h+var_B0], rax
0x18000dbc3  lea     rax, [rbp+57h+arg_10]
0x18000dbc7  mov     [rsp+110h+var_B8], rax
0x18000dbcc  lea     rax, [rbp+57h+var_38]
0x18000dbd0  mov     [rsp+110h+var_C0], rax
0x18000dbd5  lea     rax, [rbp+57h+arg_18]
0x18000dbd9  mov     [rsp+110h+var_C8], rax
0x18000dbde  lea     rax, [rbp+57h+var_30]
0x18000dbe2  mov     [rsp+110h+var_D0], rax
0x18000dbe7  lea     rax, [rbp+57h+var_70]
0x18000dbeb  mov     [rsp+110h+var_D8], rax
0x18000dbf0  lea     rax, [rbp+57h+var_28]
0x18000dbf4  mov     [rsp+110h+var_E0], rax
0x18000dbf9  lea     rax, [rbp+57h+var_6C]
0x18000dbfd  mov     [rsp+110h+var_E8], rax
0x18000dc02  lea     rax, [rbp+57h+var_68]
0x18000dc06  mov     [rbp+57h+var_60], rcx
0x18000dc0a  mov     rcx, r9
0x18000dc0d  mov     [rsp+110h+var_F0], rax
0x18000dc12  mov     [rbp+57h+var_68], 1000000h
0x18000dc1a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000dc1f  jmp     loc_18000DCBF
0x18000dc24  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000dc29  mov     rdi, rax
0x18000dc2c  mov     ecx, [rax]
0x18000dc2e  cmp     ecx, 2
0x18000dc31  jbe     loc_18000DCBF
0x18000dc37  mov     rdx, 200000000000h
0x18000dc41  mov     rcx, rax
0x18000dc44  call    _tlgKeywordOn
0x18000dc49  test    al, al
0x18000dc4b  jz      short loc_18000DCBF
0x18000dc4d  mov     rcx, [rbx+110h]
0x18000dc54  mov     rax, [rcx+38h]
0x18000dc58  mov     [rbp+57h+arg_10], rax
0x18000dc5c  mov     rax, [rcx+30h]
0x18000dc60  mov     [rbp+57h+arg_18], rax
0x18000dc64  call    cs:__imp_GetCurrentThreadId
0x18000dc6a  mov     r8, [rbx+110h]
0x18000dc71  lea     rdx, unk_180033861
0x18000dc78  mov     [rbp+57h+arg_8], eax
0x18000dc7b  add     r8, 8
0x18000dc7f  lea     rax, [rbp+57h+arg_10]
0x18000dc83  mov     [rbp+57h+arg_0], esi
0x18000dc86  mov     [rsp+110h+var_D0], rax
0x18000dc8b  mov     rcx, rdi
0x18000dc8e  lea     rax, [rbp+57h+arg_18]
0x18000dc92  mov     [rbp+57h+var_68], 1000000h
0x18000dc9a  mov     [rsp+110h+var_D8], rax
0x18000dc9f  lea     rax, [rbp+57h+arg_8]
0x18000dca3  mov     [rsp+110h+var_E0], rax
0x18000dca8  lea     rax, [rbp+57h+arg_0]
0x18000dcac  mov     [rsp+110h+var_E8], rax
0x18000dcb1  lea     rax, [rbp+57h+var_68]
0x18000dcb5  mov     [rsp+110h+var_F0], rax
0x18000dcba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000dcbf  mov     rax, [rbx]
0x18000dcc2  mov     rcx, rbx
0x18000dcc5  mov     rax, [rax+8]
0x18000dcc9  add     rsp, 0F8h
0x18000dcd0  pop     rdi
0x18000dcd1  pop     rsi
0x18000dcd2  pop     rbx
0x18000dcd3  pop     rbp
0x18000dcd4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
