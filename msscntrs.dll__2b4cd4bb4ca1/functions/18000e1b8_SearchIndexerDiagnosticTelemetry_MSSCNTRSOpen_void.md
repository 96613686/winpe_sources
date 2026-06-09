# SearchIndexerDiagnosticTelemetry::MSSCNTRSOpen(void)

- ea: `0x18000e1b8`
- end: `0x18000e334`
- name: `?MSSCNTRSOpen@SearchIndexerDiagnosticTelemetry@@SAXXZ`
- size: `380`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011500`

## callees

- `0x1800016ac`
- `0x1800017dc`
- `0x1800024a0`
- `0x180002964`
- `0x18000e1b8`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e2a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e2a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e1f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e1f6`

## pseudocode

```c
void SearchIndexerDiagnosticTelemetry::MSSCNTRSOpen(void)
{
  __int64 v0; // rcx
  WINBOOL fPending; // [rsp+30h] [rbp-50h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v3[32]; // [rsp+40h] [rbp-40h] BYREF
  LPVOID *p_Context; // [rsp+60h] [rbp-20h]
  __int64 v5; // [rsp+68h] [rbp-18h]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`SearchIndexerDiagnosticsLogging::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_180022410 = 0;
    Context = &qword_180022408;
    qword_180022408 = (__int64)&SearchIndexerDiagnosticsLogging::`vftable';
    byte_180022418 = 0;
    dword_18002241C = 0;
    qword_180022420 = &`SearchIndexerDiagnosticsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_f5a7b2c01e17025c4bccdc40fa72449f_::_lambda_invoker_cdecl_);
    qword_180022410 = (__int64)qword_180022420;
    byte_180022418 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_180022420);
    dword_18002241C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180022408 + 8))(&qword_180022408);
    InitOnceComplete(&`SearchIndexerDiagnosticsLogging::Instance'::`2'::wrapper, 0, &qword_180022408);
  }
  v0 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v0 > 5u
    && (*(_QWORD *)(v0 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v0 + 24) & 0x400000000000LL) == *(_QWORD *)(v0 + 24) )
  {
    Context = (LPVOID)0x1000000;
    p_Context = &Context;
    v5 = 8;
    tlgWriteTransfer_EventWriteTransfer(v0, &byte_18001C76F, 0, 0, 3, v3);
  }
}

```

## disassembly

```asm
0x18000e1b8  mov     [rsp-8+arg_0], rbx
0x18000e1bd  push    rbp
0x18000e1be  mov     rbp, rsp
0x18000e1c1  sub     rsp, 80h
0x18000e1c8  mov     rax, cs:__security_cookie
0x18000e1cf  xor     rax, rsp
0x18000e1d2  mov     [rbp+var_10], rax
0x18000e1d6  lea     r9, [rbp+Context]; lpContext
0x18000e1da  mov     [rbp+Context], 0
0x18000e1e2  lea     r8, [rbp+fPending]; fPending
0x18000e1e6  mov     [rbp+fPending], 0
0x18000e1ed  xor     edx, edx; dwFlags
0x18000e1ef  lea     rcx, ?wrapper@?1??Instance@SearchIndexerDiagnosticsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerDiagnosticsLogging@@@details@wil@@A; lpInitOnce
0x18000e1f6  call    cs:__imp_InitOnceBeginInitialize
0x18000e1fc  test    eax, eax
0x18000e1fe  jz      loc_18000E2AB
0x18000e204  cmp     [rbp+fPending], 0
0x18000e208  jz      loc_18000E2AB
0x18000e20e  lea     rbx, qword_180022408
0x18000e215  mov     cs:qword_180022410, 0
0x18000e220  lea     rax, ??_7SearchIndexerDiagnosticsLogging@@6B@; const SearchIndexerDiagnosticsLogging::`vftable'
0x18000e227  mov     [rbp+Context], rbx
0x18000e22b  mov     cs:qword_180022408, rax
0x18000e232  mov     cs:byte_180022418, 0
0x18000e239  mov     cs:dword_18002241C, 0
0x18000e243  lea     rax, ?__hInner@?1???0StaticHandle@SearchIndexerDiagnosticsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SearchIndexerDiagnosticsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e24a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_f5a7b2c01e17025c4bccdc40fa72449f_@@CA@XZ; void (__cdecl *)()
0x18000e251  mov     cs:qword_180022420, rax
0x18000e258  call    atexit
0x18000e25d  mov     rcx, cs:qword_180022420; CallbackContext
0x18000e264  xor     r8d, r8d
0x18000e267  xor     edx, edx
0x18000e269  mov     cs:qword_180022410, rcx
0x18000e270  mov     cs:byte_180022418, 1
0x18000e277  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000e27c  mov     rax, cs:qword_180022408
0x18000e283  mov     rcx, rbx
0x18000e286  mov     cs:dword_18002241C, 1
0x18000e290  mov     rax, [rax+8]
0x18000e294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e299  mov     r8, rbx; lpContext
0x18000e29c  lea     rcx, ?wrapper@?1??Instance@SearchIndexerDiagnosticsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerDiagnosticsLogging@@@details@wil@@A; lpInitOnce
0x18000e2a3  xor     edx, edx; dwFlags
0x18000e2a5  call    cs:__imp_InitOnceComplete
0x18000e2ab  mov     rax, [rbp+Context]
0x18000e2af  mov     rcx, [rax+8]
0x18000e2b3  mov     eax, [rcx]
0x18000e2b5  cmp     eax, 5
0x18000e2b8  jbe     short loc_18000E317
0x18000e2ba  mov     rdx, [rcx+18h]
0x18000e2be  mov     r8, 400000000000h
0x18000e2c8  mov     rax, [rcx+10h]
0x18000e2cc  test    r8, rax
0x18000e2cf  jz      short loc_18000E317
0x18000e2d1  mov     rax, rdx
0x18000e2d4  and     rax, r8
0x18000e2d7  cmp     rax, rdx
0x18000e2da  jnz     short loc_18000E317
0x18000e2dc  lea     rax, [rbp+Context]
0x18000e2e0  mov     [rbp+Context], 1000000h
0x18000e2e8  mov     [rbp+var_20], rax
0x18000e2ec  lea     rdx, byte_18001C76F
0x18000e2f3  lea     rax, [rbp+var_40]
0x18000e2f7  mov     [rbp+var_18], 8
0x18000e2ff  mov     [rsp+80h+var_58], rax
0x18000e304  xor     r9d, r9d
0x18000e307  xor     r8d, r8d
0x18000e30a  mov     [rsp+80h+var_60], 3
0x18000e312  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e317  mov     rcx, [rbp+var_10]
0x18000e31b  xor     rcx, rsp; StackCookie
0x18000e31e  call    __security_check_cookie
0x18000e323  mov     rbx, [rsp+80h+arg_0]
0x18000e32b  add     rsp, 80h
0x18000e332  pop     rbp
0x18000e333  retn
```
