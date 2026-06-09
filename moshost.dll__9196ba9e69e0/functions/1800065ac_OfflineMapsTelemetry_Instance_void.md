# OfflineMapsTelemetry::Instance(void)

- ea: `0x1800065ac`
- end: `0x180006686`
- name: `?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ`
- size: `218`
- prototype: `struct OfflineMapsTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006c24`
- `0x180009a80`

## callees

- `0x1800020bc`
- `0x1800065ac`
- `0x18000689c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800065d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800065d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006675`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006675`

## pseudocode

```c
struct OfflineMapsTelemetry *OfflineMapsTelemetry::Instance(void)
{
  BOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180018568 = 0;
    qword_180018560 = (__int64)&OfflineMapsTelemetry::`vftable';
    v2 = &qword_180018560;
    byte_180018570 = 0;
    dword_180018574 = 0;
    dword_180018588 = -1;
    atexit(_lambda_76ceee9f57f0a306d53fba4fb93de71e_::_lambda_invoker_cdecl_);
    qword_180018568 = (__int64)OfflineMapsTraceLogging::Provider();
    byte_180018570 = 0;
    dword_180018574 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180018560 + 8))(&qword_180018560);
    InitOnceComplete(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &qword_180018560);
  }
  return (struct OfflineMapsTelemetry *)v2;
}

```

## disassembly

```asm
0x1800065ac  mov     rax, rsp
0x1800065af  push    rbx
0x1800065b0  sub     rsp, 20h
0x1800065b4  lea     r9, [rax+10h]; lpContext
0x1800065b8  mov     qword ptr [rax+10h], 0
0x1800065c0  lea     r8, [rax+8]; fPending
0x1800065c4  mov     dword ptr [rax+8], 0
0x1800065cb  xor     edx, edx; dwFlags
0x1800065cd  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x1800065d4  call    cs:__imp_InitOnceBeginInitialize
0x1800065da  test    eax, eax
0x1800065dc  jz      loc_18000667B
0x1800065e2  cmp     [rsp+28h+arg_0], 0
0x1800065e7  jz      loc_18000667B
0x1800065ed  lea     rax, ??_7OfflineMapsTelemetry@@6B@; const OfflineMapsTelemetry::`vftable'
0x1800065f4  mov     cs:qword_180018568, 0
0x1800065ff  lea     rbx, qword_180018560
0x180006606  mov     cs:qword_180018560, rax
0x18000660d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_76ceee9f57f0a306d53fba4fb93de71e_@@CA@XZ; void (__cdecl *)()
0x180006614  mov     [rsp+28h+arg_8], rbx
0x180006619  mov     cs:byte_180018570, 0
0x180006620  mov     cs:dword_180018574, 0
0x18000662a  mov     cs:dword_180018588, 0FFFFFFFFh
0x180006634  call    atexit
0x180006639  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000663e  mov     cs:qword_180018568, rax
0x180006645  mov     rcx, rbx
0x180006648  mov     rax, cs:qword_180018560
0x18000664f  mov     cs:byte_180018570, 0
0x180006656  mov     cs:dword_180018574, 1
0x180006660  mov     rax, [rax+8]
0x180006664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006669  mov     r8, rbx; lpContext
0x18000666c  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x180006673  xor     edx, edx; dwFlags
0x180006675  call    cs:__imp_InitOnceComplete
0x18000667b  mov     rax, [rsp+28h+arg_8]
0x180006680  add     rsp, 20h
0x180006684  pop     rbx
0x180006685  retn
```
