# DXGIAdapterCacheLogging::Provider(void)

- ea: `0x14000a9b4`
- end: `0x14000aa6d`
- name: `?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400035b8`
- `0x140005fc4`
- `0x14000a400`
- `0x14000d358`
- `0x14000d500`
- `0x14000d6e0`

## callees

- `0x140002558`
- `0x14000a9b4`
- `0x14000c0e4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000a9dc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000a9dc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000aa58`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000aa58`

## pseudocode

```c
const struct _tlgProvider_t *DXGIAdapterCacheLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`DXGIAdapterCacheLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_14001A668 = 0;
    v3 = &qword_14001A660;
    qword_14001A660 = &DXGIAdapterCacheLogging::`vftable';
    byte_14001A670 = 0;
    dword_14001A674 = 0;
    qword_14001A678 = (struct _tlgProvider_t *)&`DXGIAdapterCacheLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_a1d5ba74ad4b20b2a37f31f56b96ffea_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_14001A660, qword_14001A678, v0);
    InitOnceComplete(&`DXGIAdapterCacheLogging::Instance'::`2'::wrapper, 0, &qword_14001A660);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x14000a9b4  mov     rax, rsp
0x14000a9b7  push    rbx
0x14000a9b8  sub     rsp, 20h
0x14000a9bc  lea     r9, [rax+10h]; lpContext
0x14000a9c0  mov     qword ptr [rax+10h], 0
0x14000a9c8  lea     r8, [rax+8]; fPending
0x14000a9cc  mov     dword ptr [rax+8], 0
0x14000a9d3  xor     edx, edx; dwFlags
0x14000a9d5  lea     rcx, ?wrapper@?1??Instance@DXGIAdapterCacheLogging@@KAPEAV2@XZ@4V?$static_lazy@VDXGIAdapterCacheLogging@@@details@wil@@A; lpInitOnce
0x14000a9dc  call    cs:__imp_InitOnceBeginInitialize
0x14000a9e2  test    eax, eax
0x14000a9e4  jz      short loc_14000AA5E
0x14000a9e6  cmp     [rsp+28h+arg_0], 0
0x14000a9eb  jz      short loc_14000AA5E
0x14000a9ed  lea     rbx, qword_14001A660
0x14000a9f4  mov     cs:qword_14001A668, 0
0x14000a9ff  lea     rax, ??_7DXGIAdapterCacheLogging@@6B@; const DXGIAdapterCacheLogging::`vftable'
0x14000aa06  mov     [rsp+28h+arg_8], rbx
0x14000aa0b  mov     cs:qword_14001A660, rax
0x14000aa12  mov     cs:byte_14001A670, 0
0x14000aa19  mov     cs:dword_14001A674, 0
0x14000aa23  lea     rax, ?__hInner@?1???0StaticHandle@DXGIAdapterCacheLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DXGIAdapterCacheLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000aa2a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a1d5ba74ad4b20b2a37f31f56b96ffea_@@CA@XZ; void (__cdecl *)()
0x14000aa31  mov     cs:qword_14001A678, rax
0x14000aa38  call    atexit
0x14000aa3d  mov     rdx, cs:qword_14001A678; struct _tlgProvider_t *
0x14000aa44  mov     rcx, rbx; this
0x14000aa47  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x14000aa4c  mov     r8, rbx; lpContext
0x14000aa4f  lea     rcx, ?wrapper@?1??Instance@DXGIAdapterCacheLogging@@KAPEAV2@XZ@4V?$static_lazy@VDXGIAdapterCacheLogging@@@details@wil@@A; lpInitOnce
0x14000aa56  xor     edx, edx; dwFlags
0x14000aa58  call    cs:__imp_InitOnceComplete
0x14000aa5e  mov     rax, [rsp+28h+arg_8]
0x14000aa63  mov     rax, [rax+8]
0x14000aa67  add     rsp, 20h
0x14000aa6b  pop     rbx
0x14000aa6c  retn
```
