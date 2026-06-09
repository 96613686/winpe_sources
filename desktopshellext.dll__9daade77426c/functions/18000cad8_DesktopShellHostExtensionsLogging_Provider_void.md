# DesktopShellHostExtensionsLogging::Provider(void)

- ea: `0x18000cad8`
- end: `0x18000cbc1`
- name: `?Provider@DesktopShellHostExtensionsLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `16`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b80`
- `0x180008f30`
- `0x180009150`
- `0x180009f20`
- `0x18000a060`
- `0x18000a1c4`
- `0x180013080`
- `0x180018348`
- `0x18003600c`
- `0x1800384c0`
- `0x180038820`
- `0x180039420`
- `0x1800394e0`
- `0x180039610`
- `0x180039840`
- `0x18006d5b0`

## callees

- `0x18000cad8`
- `0x18000cbd0`
- `0x18002a85c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cbac`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cbac`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cb00`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cb00`

## pseudocode

```c
const struct _tlgProvider_t *DesktopShellHostExtensionsLogging::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`DesktopShellHostExtensionsLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2)
    && v1 )
  {
    qword_1800AD140 = 0;
    v2 = &qword_1800AD138;
    qword_1800AD138 = (__int64)&DesktopShellHostExtensionsLogging::`vftable';
    byte_1800AD148 = 0;
    dword_1800AD14C = 0;
    qword_1800AD150 = &`DesktopShellHostExtensionsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_9fb9bd43d52e730c3396f42695231301_::_lambda_invoker_cdecl_);
    qword_1800AD140 = (__int64)qword_1800AD150;
    byte_1800AD148 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800AD150);
    dword_1800AD14C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800AD138 + 8))(&qword_1800AD138);
    InitOnceComplete(&`DesktopShellHostExtensionsLogging::Instance'::`2'::wrapper, 0, &qword_1800AD138);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18000cad8  mov     rax, rsp
0x18000cadb  push    rbx
0x18000cadc  sub     rsp, 20h
0x18000cae0  lea     r9, [rax+10h]; lpContext
0x18000cae4  mov     qword ptr [rax+10h], 0
0x18000caec  lea     r8, [rax+8]; fPending
0x18000caf0  mov     dword ptr [rax+8], 0
0x18000caf7  xor     edx, edx; dwFlags
0x18000caf9  lea     rcx, ?wrapper@?1??Instance@DesktopShellHostExtensionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VDesktopShellHostExtensionsLogging@@@details@wil@@A; lpInitOnce
0x18000cb00  call    cs:__imp_InitOnceBeginInitialize
0x18000cb06  test    eax, eax
0x18000cb08  jz      loc_18000CBB2
0x18000cb0e  cmp     [rsp+28h+arg_0], 0
0x18000cb13  jz      loc_18000CBB2
0x18000cb19  lea     rbx, qword_1800AD138
0x18000cb20  mov     cs:qword_1800AD140, 0
0x18000cb2b  lea     rax, ??_7DesktopShellHostExtensionsLogging@@6B@; const DesktopShellHostExtensionsLogging::`vftable'
0x18000cb32  mov     [rsp+28h+arg_8], rbx
0x18000cb37  mov     cs:qword_1800AD138, rax
0x18000cb3e  mov     cs:byte_1800AD148, 0
0x18000cb45  mov     cs:dword_1800AD14C, 0
0x18000cb4f  lea     rax, ?__hInner@?1???0StaticHandle@DesktopShellHostExtensionsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DesktopShellHostExtensionsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000cb56  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_9fb9bd43d52e730c3396f42695231301_@@CA@XZ; void (__cdecl *)()
0x18000cb5d  mov     cs:qword_1800AD150, rax
0x18000cb64  call    atexit
0x18000cb69  mov     rcx, cs:qword_1800AD150; CallbackContext
0x18000cb70  mov     cs:qword_1800AD140, rcx
0x18000cb77  mov     cs:byte_1800AD148, 1
0x18000cb7e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000cb83  mov     rax, cs:qword_1800AD138
0x18000cb8a  mov     rcx, rbx
0x18000cb8d  mov     cs:dword_1800AD14C, 1
0x18000cb97  mov     rax, [rax+8]
0x18000cb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cba0  mov     r8, rbx; lpContext
0x18000cba3  lea     rcx, ?wrapper@?1??Instance@DesktopShellHostExtensionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VDesktopShellHostExtensionsLogging@@@details@wil@@A; lpInitOnce
0x18000cbaa  xor     edx, edx; dwFlags
0x18000cbac  call    cs:__imp_InitOnceComplete
0x18000cbb2  mov     rax, [rsp+28h+arg_8]
0x18000cbb7  mov     rax, [rax+8]
0x18000cbbb  add     rsp, 20h
0x18000cbbf  pop     rbx
0x18000cbc0  retn
```
