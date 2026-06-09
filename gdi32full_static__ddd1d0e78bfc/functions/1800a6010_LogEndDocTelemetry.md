# LogEndDocTelemetry

- ea: `0x1800a6010`
- end: `0x1800a6132`
- name: `LogEndDocTelemetry`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180097d10`

## callees

- `0x180001110`
- `0x180001dd8`
- `0x1800a6010`
- `0x1800a68b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a608d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a608d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a60a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a60a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a6043`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a6043`

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
    if ( (unsigned int)dword_1800FD120 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800FD120, 0x400000000000LL) )
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
        (unsigned int)&dword_1800E8554,
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
0x1800a6010  push    rbp
0x1800a6012  push    rbx
0x1800a6013  push    rsi
0x1800a6014  push    rdi
0x1800a6015  push    r14
0x1800a6017  lea     rbp, [rsp-37h]
0x1800a601c  sub     rsp, 90h
0x1800a6023  mov     rdi, r9
0x1800a6026  mov     esi, r8d
0x1800a6029  mov     rbx, rdx
0x1800a602c  mov     r14, rcx
0x1800a602f  xor     r9d, r9d; Context
0x1800a6032  lea     rdx, RegisterGDI32Provider; InitFn
0x1800a6039  xor     r8d, r8d; Parameter
0x1800a603c  lea     rcx, ?g_InitGDI32TelemetryProviderOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800a6043  call    cs:__imp_InitOnceExecuteOnce
0x1800a604a  nop     dword ptr [rax+rax+00h]
0x1800a604f  test    eax, eax
0x1800a6051  jz      loc_1800A6123
0x1800a6057  mov     eax, cs:dword_1800FD120
0x1800a605d  cmp     eax, 5
0x1800a6060  jbe     loc_1800A6109
0x1800a6066  mov     rdx, 400000000000h
0x1800a6070  lea     rcx, dword_1800FD120
0x1800a6077  call    _tlgKeywordOn
0x1800a607c  test    al, al
0x1800a607e  jz      loc_1800A6109
0x1800a6084  mov     eax, [rbx+168h]
0x1800a608a  mov     [rbp+57h+var_50], eax
0x1800a608d  call    cs:__imp_GetCurrentThreadId
0x1800a6094  nop     dword ptr [rax+rax+00h]
0x1800a6099  mov     [rbp+57h+var_4C], eax
0x1800a609c  mov     [rbp+57h+var_40], rdi
0x1800a60a0  call    cs:__imp_GetLastError
0x1800a60a7  nop     dword ptr [rax+rax+00h]
0x1800a60ac  lea     rdx, dword_1800E8554
0x1800a60b3  mov     [rbp+57h+var_44], esi
0x1800a60b6  mov     [rbp+57h+var_48], eax
0x1800a60b9  lea     rax, [rbp+57h+var_50]
0x1800a60bd  mov     [rsp+0B0h+var_60], rax
0x1800a60c2  lea     rax, [rbp+57h+var_4C]
0x1800a60c6  mov     [rsp+0B0h+var_68], rax
0x1800a60cb  lea     rax, [rbp+57h+var_40]
0x1800a60cf  mov     [rsp+0B0h+var_70], rax
0x1800a60d4  lea     rax, [rbp+57h+var_48]
0x1800a60d8  mov     [rsp+0B0h+var_78], rax
0x1800a60dd  lea     rax, [rbp+57h+var_44]
0x1800a60e1  mov     [rsp+0B0h+var_80], rax
0x1800a60e6  lea     rax, [rbp+57h+var_38]
0x1800a60ea  mov     [rsp+0B0h+var_88], rax
0x1800a60ef  lea     rax, [rbp+57h+var_30]
0x1800a60f3  mov     [rsp+0B0h+var_90], rax
0x1800a60f8  mov     [rbp+57h+var_38], r14
0x1800a60fc  mov     [rbp+57h+var_30], 1000000h
0x1800a6104  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a6109  lea     rdx, aMetaPrint; "Meta Print"
0x1800a6110  mov     rcx, rdi; String1
0x1800a6113  call    wcscmp_0
0x1800a6118  test    eax, eax
0x1800a611a  jz      short loc_1800A6123
0x1800a611c  lock dec dword ptr [rbx+168h]
0x1800a6123  add     rsp, 90h
0x1800a612a  pop     r14
0x1800a612c  pop     rdi
0x1800a612d  pop     rsi
0x1800a612e  pop     rbx
0x1800a612f  pop     rbp
0x1800a6130  retn
```
