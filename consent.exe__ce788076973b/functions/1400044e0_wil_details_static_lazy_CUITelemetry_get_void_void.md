# wil::details::static_lazy<CUITelemetry>::get(void (*)(void))

- ea: `0x1400044e0`
- end: `0x140004650`
- name: `?get@?$static_lazy@VCUITelemetry@@@details@wil@@QEAAPEAVCUITelemetry@@P6AXXZ@Z`
- size: `368`
- prototype: `LPVOID __fastcall(__int64, void (__cdecl *)())`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007ce0`
- `0x14000dd88`
- `0x14001bc94`

## callees

- `0x1400044e0`
- `0x140004660`
- `0x140010514`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400045c5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140004645`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400045c5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140004645`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000450c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000457b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000450c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000457b`

## pseudocode

```c
LPVOID __fastcall wil::details::static_lazy<CUITelemetry>::get(__int64 a1, void (__cdecl *a2)())
{
  void (*v4)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID v5; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+54h] [rbp+Ch]
  WINBOOL v8; // [rsp+60h] [rbp+18h] BYREF
  LPVOID Context; // [rsp+68h] [rbp+20h] BYREF

  v7 = HIDWORD(a1);
  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`CUITelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_140029E78 = 0;
    Context = &qword_140029E70;
    byte_140029E80 = 0;
    dword_140029E84 = 0;
    qword_140029E70 = (__int64)&CUILogging::`vftable';
    atexit(a2);
    v5 = 0;
    v8 = 0;
    if ( InitOnceBeginInitialize(&`CUILogging::Instance'::`2'::wrapper, 0, &v8, &v5) && v8 )
    {
      qword_140029E50 = 0;
      v5 = &qword_140029E48;
      qword_140029E48 = &CUILogging::`vftable';
      byte_140029E58 = 0;
      dword_140029E5C = 0;
      qword_140029E60 = (struct _tlgProvider_t *)&`CUILogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_61db26cb2c3b1cdde0a84bc9ea249318_::_lambda_invoker_cdecl_);
      wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140029E48, qword_140029E60, v4);
      InitOnceComplete(&`CUILogging::Instance'::`2'::wrapper, 0, &qword_140029E48);
    }
    qword_140029E78 = *((_QWORD *)v5 + 1);
    byte_140029E80 = 0;
    dword_140029E84 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140029E70 + 8))(&qword_140029E70);
    InitOnceComplete(&`CUITelemetry::Instance'::`2'::wrapper, 0, &qword_140029E70);
  }
  return Context;
}

```

## disassembly

```asm
0x1400044e0  mov     qword ptr [rsp+fPending], rcx
0x1400044e5  push    rbx
0x1400044e6  push    rdi
0x1400044e7  sub     rsp, 38h
0x1400044eb  mov     rbx, rdx
0x1400044ee  lea     r9, [rsp+48h+Context]; lpContext
0x1400044f3  xor     edi, edi
0x1400044f5  lea     r8, [rsp+48h+fPending]; fPending
0x1400044fa  xor     edx, edx; dwFlags
0x1400044fc  mov     [rsp+48h+Context], rdi
0x140004501  lea     rcx, ?wrapper@?1??Instance@CUITelemetry@@KAPEAV2@XZ@4V?$static_lazy@VCUITelemetry@@@details@wil@@A; lpInitOnce
0x140004508  mov     [rsp+48h+fPending], edi
0x14000450c  call    cs:__imp_InitOnceBeginInitialize
0x140004512  test    eax, eax
0x140004514  jz      loc_1400045D0
0x14000451a  cmp     [rsp+48h+fPending], edi
0x14000451e  jz      loc_1400045D0
0x140004524  lea     rax, ??_7CUILogging@@6B@; const CUILogging::`vftable'
0x14000452b  mov     [rsp+48h+var_18], rsi
0x140004530  lea     rsi, qword_140029E70
0x140004537  mov     cs:qword_140029E78, rdi
0x14000453e  mov     rcx, rbx; void (__cdecl *)()
0x140004541  mov     [rsp+48h+Context], rsi
0x140004546  mov     cs:byte_140029E80, dil
0x14000454d  mov     cs:dword_140029E84, edi
0x140004553  mov     cs:qword_140029E70, rax
0x14000455a  call    atexit
0x14000455f  lea     r9, [rsp+48h+var_28]; lpContext
0x140004564  mov     [rsp+48h+var_28], rdi
0x140004569  lea     r8, [rsp+48h+arg_10]; fPending
0x14000456e  mov     [rsp+48h+arg_10], edi
0x140004572  xor     edx, edx; dwFlags
0x140004574  lea     rcx, ?wrapper@?1??Instance@CUILogging@@KAPEAV2@XZ@4V?$static_lazy@VCUILogging@@@details@wil@@A; lpInitOnce
0x14000457b  call    cs:__imp_InitOnceBeginInitialize
0x140004581  test    eax, eax
0x140004583  jnz     short loc_1400045DC
0x140004585  mov     rax, [rsp+48h+var_28]
0x14000458a  mov     rcx, rsi
0x14000458d  mov     rdx, [rax+8]
0x140004591  mov     rax, cs:qword_140029E70
0x140004598  mov     cs:qword_140029E78, rdx
0x14000459f  mov     cs:byte_140029E80, dil
0x1400045a6  mov     cs:dword_140029E84, 1
0x1400045b0  mov     rax, [rax+8]
0x1400045b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045b9  mov     r8, rsi; lpContext
0x1400045bc  lea     rcx, ?wrapper@?1??Instance@CUITelemetry@@KAPEAV2@XZ@4V?$static_lazy@VCUITelemetry@@@details@wil@@A; lpInitOnce
0x1400045c3  xor     edx, edx; dwFlags
0x1400045c5  call    cs:__imp_InitOnceComplete
0x1400045cb  mov     rsi, [rsp+48h+var_18]
0x1400045d0  mov     rax, [rsp+48h+Context]
0x1400045d5  add     rsp, 38h
0x1400045d9  pop     rdi
0x1400045da  pop     rbx
0x1400045db  retn
0x1400045dc  cmp     [rsp+48h+arg_10], edi
0x1400045e0  jz      short loc_140004585
0x1400045e2  lea     rbx, qword_140029E48
0x1400045e9  mov     cs:qword_140029E50, rdi
0x1400045f0  lea     rax, ??_7CUILogging@@6B@; const CUILogging::`vftable'
0x1400045f7  mov     [rsp+48h+var_28], rbx
0x1400045fc  mov     cs:qword_140029E48, rax
0x140004603  mov     cs:byte_140029E58, dil
0x14000460a  mov     cs:dword_140029E5C, edi
0x140004610  lea     rax, ?__hInner@?1???0StaticHandle@CUILogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CUILogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140004617  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_61db26cb2c3b1cdde0a84bc9ea249318_@@CA@XZ; void (__cdecl *)()
0x14000461e  mov     cs:qword_140029E60, rax
0x140004625  call    atexit
0x14000462a  mov     rdx, cs:qword_140029E60; struct _tlgProvider_t *
0x140004631  mov     rcx, rbx; this
0x140004634  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140004639  mov     r8, rbx; lpContext
0x14000463c  lea     rcx, ?wrapper@?1??Instance@CUILogging@@KAPEAV2@XZ@4V?$static_lazy@VCUILogging@@@details@wil@@A; lpInitOnce
0x140004643  xor     edx, edx; dwFlags
0x140004645  call    cs:__imp_InitOnceComplete
0x14000464b  jmp     loc_140004585
```
