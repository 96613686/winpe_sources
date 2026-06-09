# CUILogging::Provider(void)

- ea: `0x140004418`
- end: `0x1400044d1`
- name: `?Provider@CUILogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bdf0`
- `0x14001c528`

## callees

- `0x140004418`
- `0x140004660`
- `0x140010514`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400044bc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400044bc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140004440`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140004440`

## pseudocode

```c
const struct _tlgProvider_t *CUILogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`CUILogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_140029E50 = 0;
    v3 = &qword_140029E48;
    qword_140029E48 = &CUILogging::`vftable';
    byte_140029E58 = 0;
    dword_140029E5C = 0;
    qword_140029E60 = (struct _tlgProvider_t *)&`CUILogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_61db26cb2c3b1cdde0a84bc9ea249318_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140029E48, qword_140029E60, v0);
    InitOnceComplete(&`CUILogging::Instance'::`2'::wrapper, 0, &qword_140029E48);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x140004418  mov     rax, rsp
0x14000441b  push    rbx
0x14000441c  sub     rsp, 20h
0x140004420  lea     r9, [rax+10h]; lpContext
0x140004424  mov     qword ptr [rax+10h], 0
0x14000442c  lea     r8, [rax+8]; fPending
0x140004430  mov     dword ptr [rax+8], 0
0x140004437  xor     edx, edx; dwFlags
0x140004439  lea     rcx, ?wrapper@?1??Instance@CUILogging@@KAPEAV2@XZ@4V?$static_lazy@VCUILogging@@@details@wil@@A; lpInitOnce
0x140004440  call    cs:__imp_InitOnceBeginInitialize
0x140004446  test    eax, eax
0x140004448  jz      short loc_1400044C2
0x14000444a  cmp     [rsp+28h+arg_0], 0
0x14000444f  jz      short loc_1400044C2
0x140004451  lea     rbx, qword_140029E48
0x140004458  mov     cs:qword_140029E50, 0
0x140004463  lea     rax, ??_7CUILogging@@6B@; const CUILogging::`vftable'
0x14000446a  mov     [rsp+28h+arg_8], rbx
0x14000446f  mov     cs:qword_140029E48, rax
0x140004476  mov     cs:byte_140029E58, 0
0x14000447d  mov     cs:dword_140029E5C, 0
0x140004487  lea     rax, ?__hInner@?1???0StaticHandle@CUILogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CUILogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000448e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_61db26cb2c3b1cdde0a84bc9ea249318_@@CA@XZ; void (__cdecl *)()
0x140004495  mov     cs:qword_140029E60, rax
0x14000449c  call    atexit
0x1400044a1  mov     rdx, cs:qword_140029E60; struct _tlgProvider_t *
0x1400044a8  mov     rcx, rbx; this
0x1400044ab  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1400044b0  mov     r8, rbx; lpContext
0x1400044b3  lea     rcx, ?wrapper@?1??Instance@CUILogging@@KAPEAV2@XZ@4V?$static_lazy@VCUILogging@@@details@wil@@A; lpInitOnce
0x1400044ba  xor     edx, edx; dwFlags
0x1400044bc  call    cs:__imp_InitOnceComplete
0x1400044c2  mov     rax, [rsp+28h+arg_8]
0x1400044c7  mov     rax, [rax+8]
0x1400044cb  add     rsp, 20h
0x1400044cf  pop     rbx
0x1400044d0  retn
```
