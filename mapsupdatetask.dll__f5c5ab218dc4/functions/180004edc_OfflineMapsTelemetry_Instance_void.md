# OfflineMapsTelemetry::Instance(void)

- ea: `0x180004edc`
- end: `0x180004fb6`
- name: `?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ`
- size: `218`
- prototype: `struct OfflineMapsTelemetry *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800065c4`

## callees

- `0x180001fd4`
- `0x180004edc`
- `0x1800055b0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180004fa5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180004fa5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180004f04`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180004f04`

## pseudocode

```c
struct OfflineMapsTelemetry *OfflineMapsTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_18000E410 = 0;
    qword_18000E408 = (__int64)&OfflineMapsTelemetry::`vftable';
    v2 = &qword_18000E408;
    byte_18000E418 = 0;
    dword_18000E41C = 0;
    dword_18000E430 = -1;
    atexit(_lambda_76ceee9f57f0a306d53fba4fb93de71e_::_lambda_invoker_cdecl_);
    qword_18000E410 = (__int64)OfflineMapsTraceLogging::Provider();
    byte_18000E418 = 0;
    dword_18000E41C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18000E408 + 8))(&qword_18000E408);
    InitOnceComplete(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &qword_18000E408);
  }
  return (struct OfflineMapsTelemetry *)v2;
}

```

## disassembly

```asm
0x180004edc  mov     rax, rsp
0x180004edf  push    rbx
0x180004ee0  sub     rsp, 20h
0x180004ee4  lea     r9, [rax+10h]; lpContext
0x180004ee8  mov     qword ptr [rax+10h], 0
0x180004ef0  lea     r8, [rax+8]; fPending
0x180004ef4  mov     dword ptr [rax+8], 0
0x180004efb  xor     edx, edx; dwFlags
0x180004efd  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x180004f04  call    cs:__imp_InitOnceBeginInitialize
0x180004f0a  test    eax, eax
0x180004f0c  jz      loc_180004FAB
0x180004f12  cmp     [rsp+28h+arg_0], 0
0x180004f17  jz      loc_180004FAB
0x180004f1d  lea     rax, ??_7OfflineMapsTelemetry@@6B@; const OfflineMapsTelemetry::`vftable'
0x180004f24  mov     cs:qword_18000E410, 0
0x180004f2f  lea     rbx, qword_18000E408
0x180004f36  mov     cs:qword_18000E408, rax
0x180004f3d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_76ceee9f57f0a306d53fba4fb93de71e_@@CA@XZ; void (__cdecl *)()
0x180004f44  mov     [rsp+28h+arg_8], rbx
0x180004f49  mov     cs:byte_18000E418, 0
0x180004f50  mov     cs:dword_18000E41C, 0
0x180004f5a  mov     cs:dword_18000E430, 0FFFFFFFFh
0x180004f64  call    atexit
0x180004f69  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x180004f6e  mov     cs:qword_18000E410, rax
0x180004f75  mov     rcx, rbx
0x180004f78  mov     rax, cs:qword_18000E408
0x180004f7f  mov     cs:byte_18000E418, 0
0x180004f86  mov     cs:dword_18000E41C, 1
0x180004f90  mov     rax, [rax+8]
0x180004f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f99  mov     r8, rbx; lpContext
0x180004f9c  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x180004fa3  xor     edx, edx; dwFlags
0x180004fa5  call    cs:__imp_InitOnceComplete
0x180004fab  mov     rax, [rsp+28h+arg_8]
0x180004fb0  add     rsp, 20h
0x180004fb4  pop     rbx
0x180004fb5  retn
```
