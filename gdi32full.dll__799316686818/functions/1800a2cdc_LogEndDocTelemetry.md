# LogEndDocTelemetry

- ea: `0x1800a2cdc`
- end: `0x1800a2de7`
- name: `LogEndDocTelemetry`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180092130`

## callees

- `0x180001110`
- `0x180001dc8`
- `0x1800a2cdc`
- `0x1800a34f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d5c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a2d0f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a2d0f`

## pseudocode

```c
int __fastcall LogEndDocTelemetry(__int64 a1, __int64 a2, int a3, const wchar_t *a4)
{
  int result; // eax
  DWORD LastError; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // [rsp+60h] [rbp+7h] BYREF
  DWORD CurrentThreadId; // [rsp+64h] [rbp+Bh] BYREF
  DWORD v15; // [rsp+68h] [rbp+Fh] BYREF
  int v16; // [rsp+6Ch] [rbp+13h] BYREF
  const wchar_t *v17; // [rsp+70h] [rbp+17h] BYREF
  __int64 v18; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v19[6]; // [rsp+80h] [rbp+27h] BYREF

  result = InitOnceExecuteOnce(&g_InitGDI32TelemetryProviderOnce, RegisterGDI32Provider, 0, 0);
  if ( result )
  {
    if ( (unsigned int)dword_1800FA120 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800FA120, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(a2 + 360);
      CurrentThreadId = GetCurrentThreadId();
      v17 = a4;
      LastError = GetLastError();
      v16 = a3;
      v15 = LastError;
      v18 = a1;
      v19[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&dword_1800E56B4,
        v11,
        v12,
        (__int64)v19,
        (__int64)&v18,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v17,
        (__int64)&CurrentThreadId,
        (__int64)&v13);
    }
    result = wcscmp_0(a4, L"Meta Print");
    if ( result )
      _InterlockedDecrement((volatile signed __int32 *)(a2 + 360));
  }
  return result;
}

```

## disassembly

```asm
0x1800a2cdc  push    rbp
0x1800a2cde  push    rbx
0x1800a2cdf  push    rsi
0x1800a2ce0  push    rdi
0x1800a2ce1  push    r14
0x1800a2ce3  lea     rbp, [rsp-37h]
0x1800a2ce8  sub     rsp, 90h
0x1800a2cef  mov     rdi, r9
0x1800a2cf2  mov     esi, r8d
0x1800a2cf5  mov     rbx, rdx
0x1800a2cf8  mov     r14, rcx
0x1800a2cfb  xor     r9d, r9d; Context
0x1800a2cfe  lea     rdx, RegisterGDI32Provider; InitFn
0x1800a2d05  xor     r8d, r8d; Parameter
0x1800a2d08  lea     rcx, ?g_InitGDI32TelemetryProviderOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800a2d0f  call    cs:__imp_InitOnceExecuteOnce
0x1800a2d15  test    eax, eax
0x1800a2d17  jz      loc_1800A2DD9
0x1800a2d1d  mov     eax, cs:dword_1800FA120
0x1800a2d23  cmp     eax, 5
0x1800a2d26  jbe     loc_1800A2DBF
0x1800a2d2c  mov     rdx, 400000000000h
0x1800a2d36  lea     rcx, dword_1800FA120
0x1800a2d3d  call    _tlgKeywordOn
0x1800a2d42  test    al, al
0x1800a2d44  jz      short loc_1800A2DBF
0x1800a2d46  mov     eax, [rbx+168h]
0x1800a2d4c  mov     [rbp+57h+var_50], eax
0x1800a2d4f  call    cs:__imp_GetCurrentThreadId
0x1800a2d55  mov     [rbp+57h+var_4C], eax
0x1800a2d58  mov     [rbp+57h+var_40], rdi
0x1800a2d5c  call    cs:__imp_GetLastError
0x1800a2d62  lea     rdx, dword_1800E56B4
0x1800a2d69  mov     [rbp+57h+var_44], esi
0x1800a2d6c  mov     [rbp+57h+var_48], eax
0x1800a2d6f  lea     rax, [rbp+57h+var_50]
0x1800a2d73  mov     [rsp+0B0h+var_60], rax
0x1800a2d78  lea     rax, [rbp+57h+var_4C]
0x1800a2d7c  mov     [rsp+0B0h+var_68], rax
0x1800a2d81  lea     rax, [rbp+57h+var_40]
0x1800a2d85  mov     [rsp+0B0h+var_70], rax
0x1800a2d8a  lea     rax, [rbp+57h+var_48]
0x1800a2d8e  mov     [rsp+0B0h+var_78], rax
0x1800a2d93  lea     rax, [rbp+57h+var_44]
0x1800a2d97  mov     [rsp+0B0h+var_80], rax
0x1800a2d9c  lea     rax, [rbp+57h+var_38]
0x1800a2da0  mov     [rsp+0B0h+var_88], rax
0x1800a2da5  lea     rax, [rbp+57h+var_30]
0x1800a2da9  mov     [rsp+0B0h+var_90], rax
0x1800a2dae  mov     [rbp+57h+var_38], r14
0x1800a2db2  mov     [rbp+57h+var_30], 1000000h
0x1800a2dba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a2dbf  lea     rdx, aMetaPrint; "Meta Print"
0x1800a2dc6  mov     rcx, rdi; String1
0x1800a2dc9  call    wcscmp_0
0x1800a2dce  test    eax, eax
0x1800a2dd0  jz      short loc_1800A2DD9
0x1800a2dd2  lock dec dword ptr [rbx+168h]
0x1800a2dd9  add     rsp, 90h
0x1800a2de0  pop     r14
0x1800a2de2  pop     rdi
0x1800a2de3  pop     rsi
0x1800a2de4  pop     rbx
0x1800a2de5  pop     rbp
0x1800a2de6  retn
```
