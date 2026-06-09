# ForcedEnrollmentTelemetryProvider::Provider(void)

- ea: `0x18000c3fc`
- end: `0x18000c4f2`
- name: `?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `246`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b4ec`
- `0x18000c000`
- `0x18000c8f4`
- `0x18000ca5c`
- `0x18000cbc4`
- `0x18000cd2c`
- `0x18000ce70`
- `0x18000d110`
- `0x18000d3b0`
- `0x18000d668`

## callees

- `0x180001008`
- `0x180002a38`
- `0x18000c3fc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c424`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c424`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c4d6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c4d6`

## pseudocode

```c
const struct _tlgProvider_t *ForcedEnrollmentTelemetryProvider::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`ForcedEnrollmentTelemetryProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2)
    && v1 )
  {
    qword_18004A280 = 0;
    v2 = &qword_18004A278;
    qword_18004A278 = (__int64)&ForcedEnrollmentTelemetryProvider::`vftable';
    byte_18004A288 = 0;
    dword_18004A28C = 0;
    CallbackContext = &`ForcedEnrollmentTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_581977eed1661b97547806b796b5724b_::_lambda_invoker_cdecl_);
    qword_18004A280 = (__int64)CallbackContext;
    byte_18004A288 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18004A28C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A278 + 8))(&qword_18004A278);
    InitOnceComplete(&`ForcedEnrollmentTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_18004A278);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18000c3fc  mov     rax, rsp
0x18000c3ff  push    rbx
0x18000c400  sub     rsp, 20h
0x18000c404  lea     r9, [rax+10h]; lpContext
0x18000c408  mov     qword ptr [rax+10h], 0
0x18000c410  lea     r8, [rax+8]; fPending
0x18000c414  mov     dword ptr [rax+8], 0
0x18000c41b  xor     edx, edx; dwFlags
0x18000c41d  lea     rcx, ?wrapper@?1??Instance@ForcedEnrollmentTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VForcedEnrollmentTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000c424  call    cs:__imp_InitOnceBeginInitialize
0x18000c42b  nop     dword ptr [rax+rax+00h]
0x18000c430  test    eax, eax
0x18000c432  jz      loc_18000C4E2
0x18000c438  cmp     [rsp+28h+arg_0], 0
0x18000c43d  jz      loc_18000C4E2
0x18000c443  lea     rbx, qword_18004A278
0x18000c44a  mov     cs:qword_18004A280, 0
0x18000c455  lea     rax, ??_7ForcedEnrollmentTelemetryProvider@@6B@; const ForcedEnrollmentTelemetryProvider::`vftable'
0x18000c45c  mov     [rsp+28h+arg_8], rbx
0x18000c461  mov     cs:qword_18004A278, rax
0x18000c468  mov     cs:byte_18004A288, 0
0x18000c46f  mov     cs:dword_18004A28C, 0
0x18000c479  lea     rax, ?__hInner@?1???0StaticHandle@ForcedEnrollmentTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ForcedEnrollmentTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000c480  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_581977eed1661b97547806b796b5724b_@@CA@XZ; void (__cdecl *)()
0x18000c487  mov     cs:CallbackContext, rax
0x18000c48e  call    atexit
0x18000c493  mov     rcx, cs:CallbackContext; CallbackContext
0x18000c49a  mov     cs:qword_18004A280, rcx
0x18000c4a1  mov     cs:byte_18004A288, 1
0x18000c4a8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000c4ad  mov     rax, cs:qword_18004A278
0x18000c4b4  mov     rcx, rbx
0x18000c4b7  mov     cs:dword_18004A28C, 1
0x18000c4c1  mov     rax, [rax+8]
0x18000c4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ca  mov     r8, rbx; lpContext
0x18000c4cd  lea     rcx, ?wrapper@?1??Instance@ForcedEnrollmentTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VForcedEnrollmentTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000c4d4  xor     edx, edx; dwFlags
0x18000c4d6  call    cs:__imp_InitOnceComplete
0x18000c4dd  nop     dword ptr [rax+rax+00h]
0x18000c4e2  mov     rax, [rsp+28h+arg_8]
0x18000c4e7  mov     rax, [rax+8]
0x18000c4eb  add     rsp, 20h
0x18000c4ef  pop     rbx
0x18000c4f0  retn
```
