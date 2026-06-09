# DXGIAdapterCacheDxDbTelemetry::Instance(void)

- ea: `0x140009d6c`
- end: `0x140009e3c`
- name: `?Instance@DXGIAdapterCacheDxDbTelemetry@@KAPEAV1@XZ`
- size: `208`
- prototype: `struct DXGIAdapterCacheDxDbTelemetry *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000eafc`

## callees

- `0x140002558`
- `0x140009d6c`
- `0x14000aa74`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140009d94`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140009d94`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140009e2b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140009e2b`

## pseudocode

```c
struct DXGIAdapterCacheDxDbTelemetry *DXGIAdapterCacheDxDbTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`DXGIAdapterCacheDxDbTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_14001A6B8 = 0;
    qword_14001A6B0 = (__int64)&wil::TraceLoggingProvider::`vftable';
    v2 = &qword_14001A6B0;
    byte_14001A6C0 = 0;
    dword_14001A6C4 = 0;
    atexit(_lambda_bf08096c73fa689545ec45806f7715aa_::_lambda_invoker_cdecl_);
    qword_14001A6B8 = (__int64)DirectXDatabaseUpdaterLogging::Provider();
    byte_14001A6C0 = 0;
    dword_14001A6C4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14001A6B0 + 8))(&qword_14001A6B0);
    InitOnceComplete(&`DXGIAdapterCacheDxDbTelemetry::Instance'::`2'::wrapper, 0, &qword_14001A6B0);
  }
  return (struct DXGIAdapterCacheDxDbTelemetry *)v2;
}

```

## disassembly

```asm
0x140009d6c  mov     rax, rsp
0x140009d6f  push    rbx
0x140009d70  sub     rsp, 20h
0x140009d74  lea     r9, [rax+10h]; lpContext
0x140009d78  mov     qword ptr [rax+10h], 0
0x140009d80  lea     r8, [rax+8]; fPending
0x140009d84  mov     dword ptr [rax+8], 0
0x140009d8b  xor     edx, edx; dwFlags
0x140009d8d  lea     rcx, ?wrapper@?1??Instance@DXGIAdapterCacheDxDbTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VDXGIAdapterCacheDxDbTelemetry@@@details@wil@@A; lpInitOnce
0x140009d94  call    cs:__imp_InitOnceBeginInitialize
0x140009d9a  test    eax, eax
0x140009d9c  jz      loc_140009E31
0x140009da2  cmp     [rsp+28h+arg_0], 0
0x140009da7  jz      loc_140009E31
0x140009dad  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x140009db4  mov     cs:qword_14001A6B8, 0
0x140009dbf  lea     rbx, qword_14001A6B0
0x140009dc6  mov     cs:qword_14001A6B0, rax
0x140009dcd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_bf08096c73fa689545ec45806f7715aa_@@CA@XZ; void (__cdecl *)()
0x140009dd4  mov     [rsp+28h+arg_8], rbx
0x140009dd9  mov     cs:byte_14001A6C0, 0
0x140009de0  mov     cs:dword_14001A6C4, 0
0x140009dea  call    atexit
0x140009def  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x140009df4  mov     cs:qword_14001A6B8, rax
0x140009dfb  mov     rcx, rbx
0x140009dfe  mov     rax, cs:qword_14001A6B0
0x140009e05  mov     cs:byte_14001A6C0, 0
0x140009e0c  mov     cs:dword_14001A6C4, 1
0x140009e16  mov     rax, [rax+8]
0x140009e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e1f  mov     r8, rbx; lpContext
0x140009e22  lea     rcx, ?wrapper@?1??Instance@DXGIAdapterCacheDxDbTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VDXGIAdapterCacheDxDbTelemetry@@@details@wil@@A; lpInitOnce
0x140009e29  xor     edx, edx; dwFlags
0x140009e2b  call    cs:__imp_InitOnceComplete
0x140009e31  mov     rax, [rsp+28h+arg_8]
0x140009e36  add     rsp, 20h
0x140009e3a  pop     rbx
0x140009e3b  retn
```
