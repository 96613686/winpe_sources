# NetworkingTriageScenario::GetConnected::Provider(void)

- ea: `0x1400299fc`
- end: `0x140029ae5`
- name: `?Provider@GetConnected@NetworkingTriageScenario@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002776c`
- `0x140027a4c`
- `0x140027d1c`

## callees

- `0x140002434`
- `0x140003218`
- `0x1400299fc`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140029ad0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140029ad0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140029a24`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140029a24`

## pseudocode

```c
const struct _tlgProvider_t *NetworkingTriageScenario::GetConnected::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(
         &`NetworkingTriageScenario::GetConnected::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_140075D28 = 0;
    v2 = &qword_140075D20;
    qword_140075D20 = (__int64)&NetworkingTriageScenario::GetConnected::`vftable';
    byte_140075D30 = 0;
    dword_140075D34 = 0;
    CallbackContext = &`NetworkingTriageScenario::GetConnected::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`NetworkingTriageScenario::GetConnected::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    qword_140075D28 = (__int64)CallbackContext;
    byte_140075D30 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_140075D34 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140075D20 + 8))(&qword_140075D20);
    InitOnceComplete(&`NetworkingTriageScenario::GetConnected::Instance'::`2'::wrapper, 0, &qword_140075D20);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x1400299fc  mov     rax, rsp
0x1400299ff  push    rbx
0x140029a00  sub     rsp, 20h
0x140029a04  lea     r9, [rax+10h]; lpContext
0x140029a08  mov     qword ptr [rax+10h], 0
0x140029a10  lea     r8, [rax+8]; fPending
0x140029a14  mov     dword ptr [rax+8], 0
0x140029a1b  xor     edx, edx; dwFlags
0x140029a1d  lea     rcx, ?wrapper@?1??Instance@GetConnected@NetworkingTriageScenario@@KAPEAV23@XZ@4V?$static_lazy@VGetConnected@NetworkingTriageScenario@@@details@wil@@A; lpInitOnce
0x140029a24  call    cs:__imp___std_init_once_begin_initialize
0x140029a2a  test    eax, eax
0x140029a2c  jz      loc_140029AD6
0x140029a32  cmp     [rsp+28h+arg_0], 0
0x140029a37  jz      loc_140029AD6
0x140029a3d  lea     rbx, qword_140075D20
0x140029a44  mov     cs:qword_140075D28, 0
0x140029a4f  lea     rax, ??_7GetConnected@NetworkingTriageScenario@@6B@; const NetworkingTriageScenario::GetConnected::`vftable'
0x140029a56  mov     [rsp+28h+arg_8], rbx
0x140029a5b  mov     cs:qword_140075D20, rax
0x140029a62  mov     cs:byte_140075D30, 0
0x140029a69  mov     cs:dword_140075D34, 0
0x140029a73  lea     rax, ?__hInner@?1???0StaticHandle@GetConnected@NetworkingTriageScenario@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetworkingTriageScenario::GetConnected::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140029a7a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@GetConnected@NetworkingTriageScenario@@KAPEAV34@XZ@SA@XZ; void (__cdecl *)()
0x140029a81  mov     cs:CallbackContext, rax
0x140029a88  call    atexit
0x140029a8d  mov     rcx, cs:CallbackContext; CallbackContext
0x140029a94  mov     cs:qword_140075D28, rcx
0x140029a9b  mov     cs:byte_140075D30, 1
0x140029aa2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140029aa7  mov     rax, cs:qword_140075D20
0x140029aae  mov     rcx, rbx
0x140029ab1  mov     cs:dword_140075D34, 1
0x140029abb  mov     rax, [rax+8]
0x140029abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029ac4  mov     r8, rbx; lpContext
0x140029ac7  lea     rcx, ?wrapper@?1??Instance@GetConnected@NetworkingTriageScenario@@KAPEAV23@XZ@4V?$static_lazy@VGetConnected@NetworkingTriageScenario@@@details@wil@@A; lpInitOnce
0x140029ace  xor     edx, edx; dwFlags
0x140029ad0  call    cs:__imp_InitOnceComplete
0x140029ad6  mov     rax, [rsp+28h+arg_8]
0x140029adb  mov     rax, [rax+8]
0x140029adf  add     rsp, 20h
0x140029ae3  pop     rbx
0x140029ae4  retn
```
