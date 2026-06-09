# DirectXDatabaseUpdaterLogging::Provider(void)

- ea: `0x14000aa74`
- end: `0x14000ab2d`
- name: `?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008214`
- `0x140009d6c`

## callees

- `0x140002558`
- `0x14000aa74`
- `0x14000c0e4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000aa9c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000aa9c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000ab18`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000ab18`

## pseudocode

```c
const struct _tlgProvider_t *DirectXDatabaseUpdaterLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`DirectXDatabaseUpdaterLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_14001A690 = 0;
    v3 = &qword_14001A688;
    qword_14001A688 = &DXGIAdapterCacheLogging::`vftable';
    byte_14001A698 = 0;
    dword_14001A69C = 0;
    qword_14001A6A0 = (struct _tlgProvider_t *)&`DirectXDatabaseUpdaterLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_4584331c7c235ab1bc19f4fa446ba6ef_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_14001A688, qword_14001A6A0, v0);
    InitOnceComplete(&`DirectXDatabaseUpdaterLogging::Instance'::`2'::wrapper, 0, &qword_14001A688);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x14000aa74  mov     rax, rsp
0x14000aa77  push    rbx
0x14000aa78  sub     rsp, 20h
0x14000aa7c  lea     r9, [rax+10h]; lpContext
0x14000aa80  mov     qword ptr [rax+10h], 0
0x14000aa88  lea     r8, [rax+8]; fPending
0x14000aa8c  mov     dword ptr [rax+8], 0
0x14000aa93  xor     edx, edx; dwFlags
0x14000aa95  lea     rcx, ?wrapper@?1??Instance@DirectXDatabaseUpdaterLogging@@KAPEAV2@XZ@4V?$static_lazy@VDirectXDatabaseUpdaterLogging@@@details@wil@@A; lpInitOnce
0x14000aa9c  call    cs:__imp_InitOnceBeginInitialize
0x14000aaa2  test    eax, eax
0x14000aaa4  jz      short loc_14000AB1E
0x14000aaa6  cmp     [rsp+28h+arg_0], 0
0x14000aaab  jz      short loc_14000AB1E
0x14000aaad  lea     rbx, qword_14001A688
0x14000aab4  mov     cs:qword_14001A690, 0
0x14000aabf  lea     rax, ??_7DXGIAdapterCacheLogging@@6B@; const DXGIAdapterCacheLogging::`vftable'
0x14000aac6  mov     [rsp+28h+arg_8], rbx
0x14000aacb  mov     cs:qword_14001A688, rax
0x14000aad2  mov     cs:byte_14001A698, 0
0x14000aad9  mov     cs:dword_14001A69C, 0
0x14000aae3  lea     rax, ?__hInner@?1???0StaticHandle@DirectXDatabaseUpdaterLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DirectXDatabaseUpdaterLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000aaea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_4584331c7c235ab1bc19f4fa446ba6ef_@@CA@XZ; void (__cdecl *)()
0x14000aaf1  mov     cs:qword_14001A6A0, rax
0x14000aaf8  call    atexit
0x14000aafd  mov     rdx, cs:qword_14001A6A0; struct _tlgProvider_t *
0x14000ab04  mov     rcx, rbx; this
0x14000ab07  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x14000ab0c  mov     r8, rbx; lpContext
0x14000ab0f  lea     rcx, ?wrapper@?1??Instance@DirectXDatabaseUpdaterLogging@@KAPEAV2@XZ@4V?$static_lazy@VDirectXDatabaseUpdaterLogging@@@details@wil@@A; lpInitOnce
0x14000ab16  xor     edx, edx; dwFlags
0x14000ab18  call    cs:__imp_InitOnceComplete
0x14000ab1e  mov     rax, [rsp+28h+arg_8]
0x14000ab23  mov     rax, [rax+8]
0x14000ab27  add     rsp, 20h
0x14000ab2b  pop     rbx
0x14000ab2c  retn
```
