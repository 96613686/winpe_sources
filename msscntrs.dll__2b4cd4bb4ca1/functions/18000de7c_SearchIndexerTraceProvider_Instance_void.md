# SearchIndexerTraceProvider::Instance(void)

- ea: `0x18000de7c`
- end: `0x18000df66`
- name: `?Instance@SearchIndexerTraceProvider@@KAPEAU1@XZ`
- size: `234`
- prototype: `struct SearchIndexerTraceProvider *(void)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c84c`
- `0x18000c8e8`
- `0x18000dd2c`
- `0x18000ddc8`
- `0x18001067c`
- `0x180010718`

## callees

- `0x1800016ac`
- `0x180002964`
- `0x18000de7c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000df55`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000df55`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dea4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dea4`

## pseudocode

```c
struct SearchIndexerTraceProvider *SearchIndexerTraceProvider::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`SearchIndexerTraceProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180022128 = 0;
    v2 = &qword_180022120;
    qword_180022120 = (__int64)&SearchIndexerDiagnosticsLogging::`vftable';
    byte_180022130 = 0;
    dword_180022134 = 0;
    CallbackContext = &`SearchIndexerTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8d28b2098336314bba74a672c814e573_::_lambda_invoker_cdecl_);
    qword_180022128 = (__int64)CallbackContext;
    byte_180022130 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180022134 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180022120 + 8))(&qword_180022120);
    InitOnceComplete(&`SearchIndexerTraceProvider::Instance'::`2'::wrapper, 0, &qword_180022120);
  }
  return (struct SearchIndexerTraceProvider *)v2;
}

```

## disassembly

```asm
0x18000de7c  mov     rax, rsp
0x18000de7f  push    rbx
0x18000de80  sub     rsp, 20h
0x18000de84  lea     r9, [rax+10h]; lpContext
0x18000de88  mov     qword ptr [rax+10h], 0
0x18000de90  lea     r8, [rax+8]; fPending
0x18000de94  mov     dword ptr [rax+8], 0
0x18000de9b  xor     edx, edx; dwFlags
0x18000de9d  lea     rcx, ?wrapper@?1??Instance@SearchIndexerTraceProvider@@KAPEAU2@XZ@4V?$static_lazy@USearchIndexerTraceProvider@@@details@wil@@A; lpInitOnce
0x18000dea4  call    cs:__imp_InitOnceBeginInitialize
0x18000deaa  test    eax, eax
0x18000deac  jz      loc_18000DF5B
0x18000deb2  cmp     [rsp+28h+arg_0], 0
0x18000deb7  jz      loc_18000DF5B
0x18000debd  lea     rbx, qword_180022120
0x18000dec4  mov     cs:qword_180022128, 0
0x18000decf  lea     rax, ??_7SearchIndexerDiagnosticsLogging@@6B@; const SearchIndexerDiagnosticsLogging::`vftable'
0x18000ded6  mov     [rsp+28h+arg_8], rbx
0x18000dedb  mov     cs:qword_180022120, rax
0x18000dee2  mov     cs:byte_180022130, 0
0x18000dee9  mov     cs:dword_180022134, 0
0x18000def3  lea     rax, ?__hInner@?1???0StaticHandle@SearchIndexerTraceProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SearchIndexerTraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000defa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8d28b2098336314bba74a672c814e573_@@CA@XZ; void (__cdecl *)()
0x18000df01  mov     cs:CallbackContext, rax
0x18000df08  call    atexit
0x18000df0d  mov     rcx, cs:CallbackContext; CallbackContext
0x18000df14  xor     r8d, r8d
0x18000df17  xor     edx, edx
0x18000df19  mov     cs:qword_180022128, rcx
0x18000df20  mov     cs:byte_180022130, 1
0x18000df27  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000df2c  mov     rax, cs:qword_180022120
0x18000df33  mov     rcx, rbx
0x18000df36  mov     cs:dword_180022134, 1
0x18000df40  mov     rax, [rax+8]
0x18000df44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df49  mov     r8, rbx; lpContext
0x18000df4c  lea     rcx, ?wrapper@?1??Instance@SearchIndexerTraceProvider@@KAPEAU2@XZ@4V?$static_lazy@USearchIndexerTraceProvider@@@details@wil@@A; lpInitOnce
0x18000df53  xor     edx, edx; dwFlags
0x18000df55  call    cs:__imp_InitOnceComplete
0x18000df5b  mov     rax, [rsp+28h+arg_8]
0x18000df60  add     rsp, 20h
0x18000df64  pop     rbx
0x18000df65  retn
```
