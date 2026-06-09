# ComputeStorage::Diagnostics::TraceProvider::Instance(void)

- ea: `0x18000b9b4`
- end: `0x18000bac4`
- name: `?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ`
- size: `272`
- prototype: `struct ComputeStorage::Diagnostics::TraceProvider *(void)`
- caller_count: `32`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008d68`
- `0x18000c260`
- `0x18000f118`
- `0x18000f248`
- `0x18000f378`
- `0x18000f4a8`
- `0x18000f5d8`
- `0x18000f708`
- `0x18000f838`
- `0x18000f968`
- `0x18000fa98`
- `0x18000fbc8`
- `0x18000fcf8`
- `0x18000fe28`
- `0x18000ffd4`
- `0x180010120`
- `0x180010420`
- `0x180010720`
- `0x180010a20`
- `0x180010d20`
- `0x180011020`
- `0x180011320`
- `0x180011620`
- `0x180011920`
- `0x180011c20`
- `0x180011f20`
- `0x180012220`
- `0x180013e8c`
- `0x180013f30`
- `0x180014130`
- `0x180016aec`
- `0x180016e20`

## callees

- `0x180001d8c`
- `0x180002690`
- `0x180002b54`
- `0x18000b9b4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b9ed`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b9ed`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ba9f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000ba9f`

## pseudocode

```c
struct ComputeStorage::Diagnostics::TraceProvider *ComputeStorage::Diagnostics::TraceProvider::Instance(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`ComputeStorage::Diagnostics::TraceProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_18005FBA0 = 0;
    Context = &qword_18005FB98;
    qword_18005FB98 = (__int64)&ComputeLib::Diagnostics::TraceProvider::`vftable';
    byte_18005FBA8 = 0;
    dword_18005FBAC = 0;
    CallbackContext = &`ComputeStorage::Diagnostics::TraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_6ea46401583d520fc54c77e7d6ec4592_::_lambda_invoker_cdecl_);
    qword_18005FBA0 = (__int64)CallbackContext;
    byte_18005FBA8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18005FBAC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18005FB98 + 8))(&qword_18005FB98);
    InitOnceComplete(&`ComputeStorage::Diagnostics::TraceProvider::Instance'::`2'::wrapper, 0, &qword_18005FB98);
  }
  return (struct ComputeStorage::Diagnostics::TraceProvider *)Context;
}

```

## disassembly

```asm
0x18000b9b4  push    rbx
0x18000b9b6  sub     rsp, 40h
0x18000b9ba  mov     rax, cs:__security_cookie
0x18000b9c1  xor     rax, rsp
0x18000b9c4  mov     [rsp+48h+var_18], rax
0x18000b9c9  lea     r9, [rsp+48h+Context]; lpContext
0x18000b9ce  mov     [rsp+48h+Context], 0
0x18000b9d7  lea     r8, [rsp+48h+fPending]; fPending
0x18000b9dc  mov     [rsp+48h+fPending], 0
0x18000b9e4  xor     edx, edx; dwFlags
0x18000b9e6  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@ComputeStorage@@@details@wil@@A; lpInitOnce
0x18000b9ed  call    cs:__imp___std_init_once_begin_initialize
0x18000b9f4  nop     dword ptr [rax+rax+00h]
0x18000b9f9  test    eax, eax
0x18000b9fb  jz      loc_18000BAAB
0x18000ba01  cmp     [rsp+48h+fPending], 0
0x18000ba06  jz      loc_18000BAAB
0x18000ba0c  lea     rbx, qword_18005FB98
0x18000ba13  mov     cs:qword_18005FBA0, 0
0x18000ba1e  lea     rax, ??_7TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::`vftable'
0x18000ba25  mov     [rsp+48h+Context], rbx
0x18000ba2a  mov     cs:qword_18005FB98, rax
0x18000ba31  mov     cs:byte_18005FBA8, 0
0x18000ba38  mov     cs:dword_18005FBAC, 0
0x18000ba42  lea     rax, ?__hInner@?1???0StaticHandle@TraceProvider@Diagnostics@ComputeStorage@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ComputeStorage::Diagnostics::TraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000ba49  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_6ea46401583d520fc54c77e7d6ec4592_@@CA@XZ; void (__cdecl *)()
0x18000ba50  mov     cs:CallbackContext, rax
0x18000ba57  call    atexit
0x18000ba5c  mov     rcx, cs:CallbackContext; CallbackContext
0x18000ba63  mov     cs:qword_18005FBA0, rcx
0x18000ba6a  mov     cs:byte_18005FBA8, 1
0x18000ba71  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000ba76  mov     rax, cs:qword_18005FB98
0x18000ba7d  mov     rcx, rbx
0x18000ba80  mov     cs:dword_18005FBAC, 1
0x18000ba8a  mov     rax, [rax+8]
0x18000ba8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba93  mov     r8, rbx; lpContext
0x18000ba96  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@ComputeStorage@@@details@wil@@A; lpInitOnce
0x18000ba9d  xor     edx, edx; dwFlags
0x18000ba9f  call    cs:__imp_InitOnceComplete
0x18000baa6  nop     dword ptr [rax+rax+00h]
0x18000baab  mov     rax, [rsp+48h+Context]
0x18000bab0  mov     rcx, [rsp+48h+var_18]
0x18000bab5  xor     rcx, rsp; StackCookie
0x18000bab8  call    __security_check_cookie
0x18000babd  add     rsp, 40h
0x18000bac1  pop     rbx
0x18000bac2  retn
```
