# PpfTraceLoggingProvider::Provider(void)

- ea: `0x18000de98`
- end: `0x18000df5e`
- name: `?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `198`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `34`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c644`
- `0x18000cc70`
- `0x18000e008`
- `0x18000e260`
- `0x18000e3a0`
- `0x18000e680`
- `0x18000e920`
- `0x180018224`
- `0x18001838c`
- `0x1800184f4`
- `0x18001865c`
- `0x1800187c4`
- `0x18001892c`
- `0x180018aa0`
- `0x180018d3c`
- `0x180019090`
- `0x180019330`
- `0x1800195cc`
- `0x180019a60`
- `0x180019cfc`
- `0x18001a0b0`
- `0x18001a34c`
- `0x18001a6a0`
- `0x18001a93c`
- `0x18002d5ec`
- `0x18002d69c`
- `0x1800349f0`
- `0x180050c3c`
- `0x180050da4`
- `0x180050f10`
- `0x1800511b0`
- `0x18005144c`
- `0x180053970`
- `0x180053ae0`

## callees

- `0x180003620`
- `0x1800093c0`
- `0x18000de98`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dec0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dec0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000df42`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000df42`

## pseudocode

```c
const struct _tlgProvider_t *PpfTraceLoggingProvider::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`PpfTraceLoggingProvider::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_180072B00 = 0;
    v3 = &qword_180072AF8;
    qword_180072AF8 = &PpfTraceLoggingProvider::`vftable';
    byte_180072B08 = 0;
    dword_180072B0C = 0;
    qword_180072B10 = (struct _tlgProvider_t *)&`PpfTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_ce945b6397159ad6528d49b0d86357fe_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180072AF8, qword_180072B10, v0);
    InitOnceComplete(&`PpfTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_180072AF8);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18000de98  mov     rax, rsp
0x18000de9b  push    rbx
0x18000de9c  sub     rsp, 20h
0x18000dea0  lea     r9, [rax+10h]; lpContext
0x18000dea4  mov     qword ptr [rax+10h], 0
0x18000deac  lea     r8, [rax+8]; fPending
0x18000deb0  mov     dword ptr [rax+8], 0
0x18000deb7  xor     edx, edx; dwFlags
0x18000deb9  lea     rcx, ?wrapper@?1??Instance@PpfTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VPpfTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x18000dec0  call    cs:__imp_InitOnceBeginInitialize
0x18000dec7  nop     dword ptr [rax+rax+00h]
0x18000decc  test    eax, eax
0x18000dece  jz      short loc_18000DF4E
0x18000ded0  cmp     [rsp+28h+arg_0], 0
0x18000ded5  jz      short loc_18000DF4E
0x18000ded7  lea     rbx, qword_180072AF8
0x18000dede  mov     cs:qword_180072B00, 0
0x18000dee9  lea     rax, ??_7PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::`vftable'
0x18000def0  mov     [rsp+28h+arg_8], rbx
0x18000def5  mov     cs:qword_180072AF8, rax
0x18000defc  mov     cs:byte_180072B08, 0
0x18000df03  mov     cs:dword_180072B0C, 0
0x18000df0d  lea     rax, ?__hInner@?1???0StaticHandle@PpfTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PpfTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000df14  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_ce945b6397159ad6528d49b0d86357fe_@@CA@XZ; void (__cdecl *)()
0x18000df1b  mov     cs:qword_180072B10, rax
0x18000df22  call    atexit
0x18000df27  mov     rdx, cs:qword_180072B10; struct _tlgProvider_t *
0x18000df2e  mov     rcx, rbx; this
0x18000df31  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000df36  mov     r8, rbx; lpContext
0x18000df39  lea     rcx, ?wrapper@?1??Instance@PpfTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VPpfTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x18000df40  xor     edx, edx; dwFlags
0x18000df42  call    cs:__imp_InitOnceComplete
0x18000df49  nop     dword ptr [rax+rax+00h]
0x18000df4e  mov     rax, [rsp+28h+arg_8]
0x18000df53  mov     rax, [rax+8]
0x18000df57  add     rsp, 20h
0x18000df5b  pop     rbx
0x18000df5c  retn
```
