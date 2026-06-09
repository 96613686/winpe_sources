# LogStartDocTelemetry

- ea: `0x1800a6138`
- end: `0x1800a6257`
- name: `LogStartDocTelemetry`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800983f0`

## callees

- `0x180001008`
- `0x180001dd8`
- `0x1800a6138`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a61bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a61bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a61d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a61d3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a616b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a616b`

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
    result = dword_1800FD120;
    if ( (unsigned int)dword_1800FD120 > 5 )
    {
      result = tlgKeywordOn(&dword_1800FD120, 0x400000000000LL);
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
                 (unsigned int)&byte_1800E84DF,
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
0x1800a6138  push    rbp
0x1800a613a  push    rbx
0x1800a613b  push    rsi
0x1800a613c  push    rdi
0x1800a613d  push    r14
0x1800a613f  lea     rbp, [rsp-2Fh]
0x1800a6144  sub     rsp, 90h
0x1800a614b  mov     edi, r9d
0x1800a614e  mov     esi, r8d
0x1800a6151  mov     rbx, rdx
0x1800a6154  mov     r14, rcx
0x1800a6157  xor     r9d, r9d; Context
0x1800a615a  lea     rdx, RegisterGDI32Provider; InitFn
0x1800a6161  xor     r8d, r8d; Parameter
0x1800a6164  lea     rcx, ?g_InitGDI32TelemetryProviderOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800a616b  call    cs:__imp_InitOnceExecuteOnce
0x1800a6172  nop     dword ptr [rax+rax+00h]
0x1800a6177  test    eax, eax
0x1800a6179  jz      loc_1800A6248
0x1800a617f  lock inc dword ptr [rbx+168h]
0x1800a6186  mov     eax, cs:dword_1800FD120
0x1800a618c  cmp     eax, 5
0x1800a618f  jbe     loc_1800A6248
0x1800a6195  mov     rdx, 400000000000h
0x1800a619f  lea     rcx, dword_1800FD120
0x1800a61a6  call    _tlgKeywordOn
0x1800a61ab  test    al, al
0x1800a61ad  jz      loc_1800A6248
0x1800a61b3  mov     eax, [rbx+168h]
0x1800a61b9  mov     [rbp+4Fh+var_50], eax
0x1800a61bc  call    cs:__imp_GetCurrentThreadId
0x1800a61c3  nop     dword ptr [rax+rax+00h]
0x1800a61c8  mov     [rbp+4Fh+var_4C], eax
0x1800a61cb  mov     rax, [rbp+4Fh+arg_20]
0x1800a61cf  mov     [rbp+4Fh+var_38], rax
0x1800a61d3  call    cs:__imp_GetLastError
0x1800a61da  nop     dword ptr [rax+rax+00h]
0x1800a61df  lea     rdx, byte_1800E84DF
0x1800a61e6  mov     [rbp+4Fh+var_44], esi
0x1800a61e9  mov     [rbp+4Fh+var_48], eax
0x1800a61ec  lea     rax, [rbp+4Fh+var_50]
0x1800a61f0  mov     [rsp+0B0h+var_58], rax
0x1800a61f5  lea     rax, [rbp+4Fh+var_4C]
0x1800a61f9  mov     [rsp+0B0h+var_60], rax
0x1800a61fe  lea     rax, [rbp+4Fh+var_38]
0x1800a6202  mov     [rsp+0B0h+var_68], rax
0x1800a6207  lea     rax, [rbp+4Fh+var_48]
0x1800a620b  mov     [rsp+0B0h+var_70], rax
0x1800a6210  lea     rax, [rbp+4Fh+var_44]
0x1800a6214  mov     [rsp+0B0h+var_78], rax
0x1800a6219  lea     rax, [rbp+4Fh+var_40]
0x1800a621d  mov     [rsp+0B0h+var_80], rax
0x1800a6222  lea     rax, [rbp+4Fh+var_30]
0x1800a6226  mov     [rsp+0B0h+var_88], rax
0x1800a622b  lea     rax, [rbp+4Fh+var_28]
0x1800a622f  mov     [rsp+0B0h+var_90], rax
0x1800a6234  mov     [rbp+4Fh+var_40], edi
0x1800a6237  mov     [rbp+4Fh+var_30], r14
0x1800a623b  mov     [rbp+4Fh+var_28], 1000000h
0x1800a6243  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a6248  add     rsp, 90h
0x1800a624f  pop     r14
0x1800a6251  pop     rdi
0x1800a6252  pop     rsi
0x1800a6253  pop     rbx
0x1800a6254  pop     rbp
0x1800a6255  retn
```
