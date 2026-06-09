# LogStartDocTelemetry

- ea: `0x1800a2df0`
- end: `0x1800a2efc`
- name: `LogStartDocTelemetry`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800927b0`

## callees

- `0x180001008`
- `0x180001dc8`
- `0x1800a2df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2e6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2e6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e7f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a2e23`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a2e23`

## pseudocode

```c
int __fastcall LogStartDocTelemetry(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  int result; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // [rsp+60h] [rbp-1h] BYREF
  DWORD CurrentThreadId; // [rsp+64h] [rbp+3h] BYREF
  DWORD LastError; // [rsp+68h] [rbp+7h] BYREF
  int v16; // [rsp+6Ch] [rbp+Bh] BYREF
  int v17; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+78h] [rbp+17h] BYREF
  __int64 v19; // [rsp+80h] [rbp+1Fh] BYREF
  __int64 v20[5]; // [rsp+88h] [rbp+27h] BYREF

  result = InitOnceExecuteOnce(&g_InitGDI32TelemetryProviderOnce, RegisterGDI32Provider, 0, 0);
  if ( result )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 360));
    result = dword_1800FA120;
    if ( (unsigned int)dword_1800FA120 > 5 )
    {
      result = tlgKeywordOn(&dword_1800FA120, 0x400000000000LL);
      if ( (_BYTE)result )
      {
        v13 = *(_DWORD *)(a2 + 360);
        CurrentThreadId = GetCurrentThreadId();
        v18 = a5;
        v16 = a3;
        LastError = GetLastError();
        v17 = a4;
        v19 = a1;
        v20[0] = 0x1000000;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                 v10,
                 (unsigned int)qword_1800E5600,
                 v11,
                 v12,
                 (__int64)v20,
                 (__int64)&v19,
                 (__int64)&v17,
                 (__int64)&v16,
                 (__int64)&LastError,
                 (__int64)&v18,
                 (__int64)&CurrentThreadId,
                 (__int64)&v13);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800a2df0  push    rbp
0x1800a2df2  push    rbx
0x1800a2df3  push    rsi
0x1800a2df4  push    rdi
0x1800a2df5  push    r14
0x1800a2df7  lea     rbp, [rsp-2Fh]
0x1800a2dfc  sub     rsp, 90h
0x1800a2e03  mov     edi, r9d
0x1800a2e06  mov     esi, r8d
0x1800a2e09  mov     rbx, rdx
0x1800a2e0c  mov     r14, rcx
0x1800a2e0f  xor     r9d, r9d; Context
0x1800a2e12  lea     rdx, RegisterGDI32Provider; InitFn
0x1800a2e19  xor     r8d, r8d; Parameter
0x1800a2e1c  lea     rcx, ?g_InitGDI32TelemetryProviderOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800a2e23  call    cs:__imp_InitOnceExecuteOnce
0x1800a2e29  test    eax, eax
0x1800a2e2b  jz      loc_1800A2EEE
0x1800a2e31  lock inc dword ptr [rbx+168h]
0x1800a2e38  mov     eax, cs:dword_1800FA120
0x1800a2e3e  cmp     eax, 5
0x1800a2e41  jbe     loc_1800A2EEE
0x1800a2e47  mov     rdx, 400000000000h
0x1800a2e51  lea     rcx, dword_1800FA120
0x1800a2e58  call    _tlgKeywordOn
0x1800a2e5d  test    al, al
0x1800a2e5f  jz      loc_1800A2EEE
0x1800a2e65  mov     eax, [rbx+168h]
0x1800a2e6b  mov     [rbp+4Fh+var_50], eax
0x1800a2e6e  call    cs:__imp_GetCurrentThreadId
0x1800a2e74  mov     [rbp+4Fh+var_4C], eax
0x1800a2e77  mov     rax, [rbp+4Fh+arg_20]
0x1800a2e7b  mov     [rbp+4Fh+var_38], rax
0x1800a2e7f  call    cs:__imp_GetLastError
0x1800a2e85  lea     rdx, qword_1800E5600
0x1800a2e8c  mov     [rbp+4Fh+var_44], esi
0x1800a2e8f  mov     [rbp+4Fh+var_48], eax
0x1800a2e92  lea     rax, [rbp+4Fh+var_50]
0x1800a2e96  mov     [rsp+0B0h+var_58], rax
0x1800a2e9b  lea     rax, [rbp+4Fh+var_4C]
0x1800a2e9f  mov     [rsp+0B0h+var_60], rax
0x1800a2ea4  lea     rax, [rbp+4Fh+var_38]
0x1800a2ea8  mov     [rsp+0B0h+var_68], rax
0x1800a2ead  lea     rax, [rbp+4Fh+var_48]
0x1800a2eb1  mov     [rsp+0B0h+var_70], rax
0x1800a2eb6  lea     rax, [rbp+4Fh+var_44]
0x1800a2eba  mov     [rsp+0B0h+var_78], rax
0x1800a2ebf  lea     rax, [rbp+4Fh+var_40]
0x1800a2ec3  mov     [rsp+0B0h+var_80], rax
0x1800a2ec8  lea     rax, [rbp+4Fh+var_30]
0x1800a2ecc  mov     [rsp+0B0h+var_88], rax
0x1800a2ed1  lea     rax, [rbp+4Fh+var_28]
0x1800a2ed5  mov     [rsp+0B0h+var_90], rax
0x1800a2eda  mov     [rbp+4Fh+var_40], edi
0x1800a2edd  mov     [rbp+4Fh+var_30], r14
0x1800a2ee1  mov     [rbp+4Fh+var_28], 1000000h
0x1800a2ee9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a2eee  add     rsp, 90h
0x1800a2ef5  pop     r14
0x1800a2ef7  pop     rdi
0x1800a2ef8  pop     rsi
0x1800a2ef9  pop     rbx
0x1800a2efa  pop     rbp
0x1800a2efb  retn
```
