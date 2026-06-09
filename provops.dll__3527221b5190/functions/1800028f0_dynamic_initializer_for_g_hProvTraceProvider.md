# _dynamic_initializer_for__g_hProvTraceProvider__

- ea: `0x1800028f0`
- end: `0x1800029cb`
- name: `_dynamic_initializer_for__g_hProvTraceProvider__`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800028f0`
- `0x1800034f4`
- `0x180006f50`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002918`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180002918`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800029af`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800029af`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_hProvTraceProvider__()
{
  __int64 *result; // rax
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(
         &`Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_18004AC90 = 0;
    qword_18004AC88 = (__int64)&Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::`vftable';
    v2 = &qword_18004AC88;
    byte_18004AC98 = 0;
    dword_18004AC9C = 0;
    atexit(_lambda_9bfd91b5e90169f203b4e9496af63b9b_::_lambda_invoker_cdecl_);
    qword_18004AC90 = (__int64)Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    byte_18004AC98 = 0;
    dword_18004AC9C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004AC88 + 8))(&qword_18004AC88);
    InitOnceComplete(
      &`Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::Instance'::`2'::wrapper,
      0,
      &qword_18004AC88);
  }
  result = v2;
  g_hProvTraceProvider = v2[1];
  return result;
}

```

## disassembly

```asm
0x1800028f0  mov     rax, rsp
0x1800028f3  push    rbx
0x1800028f4  sub     rsp, 20h
0x1800028f8  lea     r9, [rax+10h]; lpContext
0x1800028fc  mov     qword ptr [rax+10h], 0
0x180002904  lea     r8, [rax+8]; fPending
0x180002908  mov     dword ptr [rax+8], 0
0x18000290f  xor     edx, edx; dwFlags
0x180002911  lea     rcx, ?wrapper@?1??Instance@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@KAPEAV234567@XZ@4V?$static_lazy@VProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@@details@wil@@A; lpInitOnce
0x180002918  call    cs:__imp_InitOnceBeginInitialize
0x18000291e  test    eax, eax
0x180002920  jz      loc_1800029B5
0x180002926  cmp     [rsp+28h+arg_0], 0
0x18000292b  jz      loc_1800029B5
0x180002931  lea     rax, ??_7ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::`vftable'
0x180002938  mov     cs:qword_18004AC90, 0
0x180002943  lea     rbx, qword_18004AC88
0x18000294a  mov     cs:qword_18004AC88, rax
0x180002951  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_9bfd91b5e90169f203b4e9496af63b9b_@@CA@XZ; void (__cdecl *)()
0x180002958  mov     [rsp+28h+arg_8], rbx
0x18000295d  mov     cs:byte_18004AC98, 0
0x180002964  mov     cs:dword_18004AC9C, 0
0x18000296e  call    atexit
0x180002973  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180002978  mov     cs:qword_18004AC90, rax
0x18000297f  mov     rcx, rbx
0x180002982  mov     rax, cs:qword_18004AC88
0x180002989  mov     cs:byte_18004AC98, 0
0x180002990  mov     cs:dword_18004AC9C, 1
0x18000299a  mov     rax, [rax+8]
0x18000299e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a3  mov     r8, rbx; lpContext
0x1800029a6  lea     rcx, ?wrapper@?1??Instance@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@KAPEAV234567@XZ@4V?$static_lazy@VProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@@details@wil@@A; lpInitOnce
0x1800029ad  xor     edx, edx; dwFlags
0x1800029af  call    cs:__imp_InitOnceComplete
0x1800029b5  mov     rax, [rsp+28h+arg_8]
0x1800029ba  mov     rcx, [rax+8]
0x1800029be  mov     cs:g_hProvTraceProvider, rcx
0x1800029c5  add     rsp, 20h
0x1800029c9  pop     rbx
0x1800029ca  retn
```
