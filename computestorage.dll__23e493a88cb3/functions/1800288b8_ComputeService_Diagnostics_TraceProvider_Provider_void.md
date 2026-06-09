# ComputeService::Diagnostics::TraceProvider::Provider(void)

- ea: `0x1800288b8`
- end: `0x1800289cc`
- name: `?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ`
- size: `276`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029118`
- `0x18002a118`
- `0x18002a608`

## callees

- `0x180001d8c`
- `0x180002690`
- `0x180002b54`
- `0x1800288b8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800288f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800288f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800289a3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800289a3`

## pseudocode

```c
const struct _tlgProvider_t *ComputeService::Diagnostics::TraceProvider::Provider(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`ComputeService::Diagnostics::TraceProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_18005FF30 = 0;
    Context = &qword_18005FF28;
    qword_18005FF28 = (__int64)&ComputeLib::Diagnostics::TraceProvider::`vftable';
    byte_18005FF38 = 0;
    dword_18005FF3C = 0;
    qword_18005FF40 = &`ComputeService::Diagnostics::TraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_c79bbec46348da9366b3cfee12cf15ba_::_lambda_invoker_cdecl_);
    qword_18005FF30 = (__int64)qword_18005FF40;
    byte_18005FF38 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_18005FF40);
    dword_18005FF3C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18005FF28 + 8))(&qword_18005FF28);
    InitOnceComplete(&`ComputeService::Diagnostics::TraceProvider::Instance'::`2'::wrapper, 0, &qword_18005FF28);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x1800288b8  push    rbx
0x1800288ba  sub     rsp, 40h
0x1800288be  mov     rax, cs:__security_cookie
0x1800288c5  xor     rax, rsp
0x1800288c8  mov     [rsp+48h+var_18], rax
0x1800288cd  lea     r9, [rsp+48h+Context]; lpContext
0x1800288d2  mov     [rsp+48h+Context], 0
0x1800288db  lea     r8, [rsp+48h+fPending]; fPending
0x1800288e0  mov     [rsp+48h+fPending], 0
0x1800288e8  xor     edx, edx; dwFlags
0x1800288ea  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@ComputeService@@@details@wil@@A; lpInitOnce
0x1800288f1  call    cs:__imp___std_init_once_begin_initialize
0x1800288f8  nop     dword ptr [rax+rax+00h]
0x1800288fd  test    eax, eax
0x1800288ff  jz      loc_1800289AF
0x180028905  cmp     [rsp+48h+fPending], 0
0x18002890a  jz      loc_1800289AF
0x180028910  lea     rbx, qword_18005FF28
0x180028917  mov     cs:qword_18005FF30, 0
0x180028922  lea     rax, ??_7TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::`vftable'
0x180028929  mov     [rsp+48h+Context], rbx
0x18002892e  mov     cs:qword_18005FF28, rax
0x180028935  mov     cs:byte_18005FF38, 0
0x18002893c  mov     cs:dword_18005FF3C, 0
0x180028946  lea     rax, ?__hInner@?1???0StaticHandle@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ComputeService::Diagnostics::TraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002894d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_c79bbec46348da9366b3cfee12cf15ba_@@CA@XZ; void (__cdecl *)()
0x180028954  mov     cs:qword_18005FF40, rax
0x18002895b  call    atexit
0x180028960  mov     rcx, cs:qword_18005FF40; CallbackContext
0x180028967  mov     cs:qword_18005FF30, rcx
0x18002896e  mov     cs:byte_18005FF38, 1
0x180028975  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002897a  mov     rax, cs:qword_18005FF28
0x180028981  mov     rcx, rbx
0x180028984  mov     cs:dword_18005FF3C, 1
0x18002898e  mov     rax, [rax+8]
0x180028992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028997  mov     r8, rbx; lpContext
0x18002899a  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@ComputeService@@@details@wil@@A; lpInitOnce
0x1800289a1  xor     edx, edx; dwFlags
0x1800289a3  call    cs:__imp_InitOnceComplete
0x1800289aa  nop     dword ptr [rax+rax+00h]
0x1800289af  mov     rax, [rsp+48h+Context]
0x1800289b4  mov     rax, [rax+8]
0x1800289b8  mov     rcx, [rsp+48h+var_18]
0x1800289bd  xor     rcx, rsp; StackCookie
0x1800289c0  call    __security_check_cookie
0x1800289c5  add     rsp, 40h
0x1800289c9  pop     rbx
0x1800289ca  retn
```
