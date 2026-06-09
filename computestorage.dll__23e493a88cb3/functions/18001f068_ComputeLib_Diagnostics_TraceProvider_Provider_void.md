# ComputeLib::Diagnostics::TraceProvider::Provider(void)

- ea: `0x18001f068`
- end: `0x18001f17c`
- name: `?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ`
- size: `276`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001a9c8`
- `0x18001bb08`
- `0x18001e200`
- `0x18001f95c`
- `0x1800203a8`
- `0x180020500`

## callees

- `0x180001d8c`
- `0x180002690`
- `0x180002b54`
- `0x18001f068`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001f0a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001f0a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001f153`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001f153`

## pseudocode

```c
const struct _tlgProvider_t *ComputeLib::Diagnostics::TraceProvider::Provider(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`ComputeLib::Diagnostics::TraceProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_180060020 = 0;
    Context = &qword_180060018;
    qword_180060018 = (__int64)&ComputeLib::Diagnostics::TraceProvider::`vftable';
    byte_180060028 = 0;
    dword_18006002C = 0;
    qword_180060030 = &`ComputeLib::Diagnostics::TraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_4611ceecc108e945812a9bf634c4bbda_::_lambda_invoker_cdecl_);
    qword_180060020 = (__int64)qword_180060030;
    byte_180060028 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_180060030);
    dword_18006002C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180060018 + 8))(&qword_180060018);
    InitOnceComplete(&`ComputeLib::Diagnostics::TraceProvider::Instance'::`2'::wrapper, 0, &qword_180060018);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x18001f068  push    rbx
0x18001f06a  sub     rsp, 40h
0x18001f06e  mov     rax, cs:__security_cookie
0x18001f075  xor     rax, rsp
0x18001f078  mov     [rsp+48h+var_18], rax
0x18001f07d  lea     r9, [rsp+48h+Context]; lpContext
0x18001f082  mov     [rsp+48h+Context], 0
0x18001f08b  lea     r8, [rsp+48h+fPending]; fPending
0x18001f090  mov     [rsp+48h+fPending], 0
0x18001f098  xor     edx, edx; dwFlags
0x18001f09a  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@ComputeLib@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@ComputeLib@@@details@wil@@A; lpInitOnce
0x18001f0a1  call    cs:__imp___std_init_once_begin_initialize
0x18001f0a8  nop     dword ptr [rax+rax+00h]
0x18001f0ad  test    eax, eax
0x18001f0af  jz      loc_18001F15F
0x18001f0b5  cmp     [rsp+48h+fPending], 0
0x18001f0ba  jz      loc_18001F15F
0x18001f0c0  lea     rbx, qword_180060018
0x18001f0c7  mov     cs:qword_180060020, 0
0x18001f0d2  lea     rax, ??_7TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::`vftable'
0x18001f0d9  mov     [rsp+48h+Context], rbx
0x18001f0de  mov     cs:qword_180060018, rax
0x18001f0e5  mov     cs:byte_180060028, 0
0x18001f0ec  mov     cs:dword_18006002C, 0
0x18001f0f6  lea     rax, ?__hInner@?1???0StaticHandle@TraceProvider@Diagnostics@ComputeLib@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ComputeLib::Diagnostics::TraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001f0fd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_4611ceecc108e945812a9bf634c4bbda_@@CA@XZ; void (__cdecl *)()
0x18001f104  mov     cs:qword_180060030, rax
0x18001f10b  call    atexit
0x18001f110  mov     rcx, cs:qword_180060030; CallbackContext
0x18001f117  mov     cs:qword_180060020, rcx
0x18001f11e  mov     cs:byte_180060028, 1
0x18001f125  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001f12a  mov     rax, cs:qword_180060018
0x18001f131  mov     rcx, rbx
0x18001f134  mov     cs:dword_18006002C, 1
0x18001f13e  mov     rax, [rax+8]
0x18001f142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f147  mov     r8, rbx; lpContext
0x18001f14a  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@ComputeLib@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@ComputeLib@@@details@wil@@A; lpInitOnce
0x18001f151  xor     edx, edx; dwFlags
0x18001f153  call    cs:__imp_InitOnceComplete
0x18001f15a  nop     dword ptr [rax+rax+00h]
0x18001f15f  mov     rax, [rsp+48h+Context]
0x18001f164  mov     rax, [rax+8]
0x18001f168  mov     rcx, [rsp+48h+var_18]
0x18001f16d  xor     rcx, rsp; StackCookie
0x18001f170  call    __security_check_cookie
0x18001f175  add     rsp, 40h
0x18001f179  pop     rbx
0x18001f17a  retn
```
