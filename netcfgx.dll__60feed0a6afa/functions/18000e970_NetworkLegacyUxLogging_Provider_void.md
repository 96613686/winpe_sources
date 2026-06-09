# NetworkLegacyUxLogging::Provider(void)

- ea: `0x18000e970`
- end: `0x18000ea22`
- name: `?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c27c`
- `0x18000e4d0`
- `0x18000f814`
- `0x18000f9bc`
- `0x18000fb90`

## callees

- `0x1800023ac`
- `0x18000c3fc`
- `0x18000e970`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e99b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e99b`

## pseudocode

```c
const struct _tlgProvider_t *NetworkLegacyUxLogging::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`NetworkLegacyUxLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`NetworkLegacyUxLogging::Instance'::`2'::wrapper;
    v4 = &qword_18001A7C8;
    qword_18001A7C8 = (__int64)&NetworkLegacyUxLogging::`vftable';
    qword_18001A7D0 = 0;
    byte_18001A7D8 = 0;
    dword_18001A7DC = 0;
    qword_18001A7E0 = (__int64)&`NetworkLegacyUxLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_0f38c6fafb7aeb3e11e6a93cf8931294_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<NetworkLegacyUxLogging>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x18000e970  mov     rax, rsp
0x18000e973  push    rdi
0x18000e974  sub     rsp, 30h
0x18000e978  lea     rdi, ?wrapper@?1??Instance@NetworkLegacyUxLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetworkLegacyUxLogging@@@details@wil@@A; wil::details::static_lazy<NetworkLegacyUxLogging> `NetworkLegacyUxLogging::Instance(void)'::`2'::wrapper
0x18000e97f  mov     qword ptr [rax+10h], 0
0x18000e987  mov     rcx, rdi; lpInitOnce
0x18000e98a  mov     dword ptr [rax+8], 0
0x18000e991  lea     r9, [rax+10h]; lpContext
0x18000e995  xor     edx, edx; dwFlags
0x18000e997  lea     r8, [rax+8]; fPending
0x18000e99b  call    cs:__imp_InitOnceBeginInitialize
0x18000e9a1  test    eax, eax
0x18000e9a3  jz      short loc_18000EA13
0x18000e9a5  cmp     [rsp+38h+arg_0], 0
0x18000e9aa  jz      short loc_18000EA13
0x18000e9ac  lea     rax, qword_18001A7C8
0x18000e9b3  mov     [rsp+38h+var_18], rdi
0x18000e9b8  mov     [rsp+38h+arg_8], rax
0x18000e9bd  lea     rax, ??_7NetworkLegacyUxLogging@@6B@; const NetworkLegacyUxLogging::`vftable'
0x18000e9c4  mov     cs:qword_18001A7C8, rax
0x18000e9cb  mov     cs:qword_18001A7D0, 0
0x18000e9d6  mov     cs:byte_18001A7D8, 0
0x18000e9dd  mov     cs:dword_18001A7DC, 0
0x18000e9e7  lea     rax, ?__hInner@?1???0StaticHandle@NetworkLegacyUxLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetworkLegacyUxLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e9ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0f38c6fafb7aeb3e11e6a93cf8931294_@@CA@XZ; void (__cdecl *)()
0x18000e9f5  mov     cs:qword_18001A7E0, rax
0x18000e9fc  call    atexit
0x18000ea01  lea     rcx, [rsp+38h+var_18]
0x18000ea06  mov     [rsp+38h+var_10], 0
0x18000ea0e  call    ??1Completer@?$static_lazy@VNetworkLegacyUxLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<NetworkLegacyUxLogging>::Completer::~Completer(void)
0x18000ea13  mov     rax, [rsp+38h+arg_8]
0x18000ea18  mov     rax, [rax+8]
0x18000ea1c  add     rsp, 30h
0x18000ea20  pop     rdi
0x18000ea21  retn
```
