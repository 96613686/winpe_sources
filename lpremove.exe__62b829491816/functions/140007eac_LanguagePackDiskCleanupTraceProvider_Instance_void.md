# LanguagePackDiskCleanupTraceProvider::Instance(void)

- ea: `0x140007eac`
- end: `0x140007f5a`
- name: `?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct LanguagePackDiskCleanupTraceProvider *(void)`
- caller_count: `15`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003260`
- `0x140004e04`
- `0x1400066c4`
- `0x140006748`
- `0x140006d50`
- `0x140007104`
- `0x140008558`
- `0x140008b70`
- `0x1400093c8`
- `0x14000b358`
- `0x14000b504`
- `0x14000b8d0`
- `0x14000c2ac`
- `0x14000c36c`
- `0x14000eac8`

## callees

- `0x14000248c`
- `0x1400051d8`
- `0x140007eac`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140007ed7`
- `KERNEL32!InitOnceBeginInitialize` at `0x140007ed7`

## pseudocode

```c
struct LanguagePackDiskCleanupTraceProvider *LanguagePackDiskCleanupTraceProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`LanguagePackDiskCleanupTraceProvider::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`LanguagePackDiskCleanupTraceProvider::Instance'::`2'::wrapper;
    v4 = &qword_140018498;
    qword_140018498 = (__int64)&LanguagePackDiskCleanupTraceProvider::`vftable';
    qword_1400184A0 = 0;
    byte_1400184A8 = 0;
    dword_1400184AC = 0;
    qword_1400184B0 = (__int64)&`LanguagePackDiskCleanupTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_c05625cf4da21629ced40f0ab894117d_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<LanguagePackDiskCleanupTraceProvider>::Completer::~Completer(&v1);
  }
  return (struct LanguagePackDiskCleanupTraceProvider *)v4;
}

```

## disassembly

```asm
0x140007eac  mov     rax, rsp
0x140007eaf  push    rdi
0x140007eb0  sub     rsp, 30h
0x140007eb4  lea     rdi, ?wrapper@?1??Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV2@XZ@4V?$static_lazy@VLanguagePackDiskCleanupTraceProvider@@@details@wil@@A; wil::details::static_lazy<LanguagePackDiskCleanupTraceProvider> `LanguagePackDiskCleanupTraceProvider::Instance(void)'::`2'::wrapper
0x140007ebb  mov     qword ptr [rax+10h], 0
0x140007ec3  mov     rcx, rdi; lpInitOnce
0x140007ec6  mov     dword ptr [rax+8], 0
0x140007ecd  lea     r9, [rax+10h]; lpContext
0x140007ed1  xor     edx, edx; dwFlags
0x140007ed3  lea     r8, [rax+8]; fPending
0x140007ed7  call    cs:__imp_InitOnceBeginInitialize
0x140007edd  test    eax, eax
0x140007edf  jz      short loc_140007F4F
0x140007ee1  cmp     [rsp+38h+arg_0], 0
0x140007ee6  jz      short loc_140007F4F
0x140007ee8  lea     rax, qword_140018498
0x140007eef  mov     [rsp+38h+var_18], rdi
0x140007ef4  mov     [rsp+38h+arg_8], rax
0x140007ef9  lea     rax, ??_7LanguagePackDiskCleanupTraceProvider@@6B@; const LanguagePackDiskCleanupTraceProvider::`vftable'
0x140007f00  mov     cs:qword_140018498, rax
0x140007f07  mov     cs:qword_1400184A0, 0
0x140007f12  mov     cs:byte_1400184A8, 0
0x140007f19  mov     cs:dword_1400184AC, 0
0x140007f23  lea     rax, ?__hInner@?1???0StaticHandle@LanguagePackDiskCleanupTraceProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `LanguagePackDiskCleanupTraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140007f2a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_c05625cf4da21629ced40f0ab894117d_@@CA@XZ; void (__cdecl *)()
0x140007f31  mov     cs:qword_1400184B0, rax
0x140007f38  call    atexit
0x140007f3d  lea     rcx, [rsp+38h+var_18]
0x140007f42  mov     [rsp+38h+var_10], 0
0x140007f4a  call    ??1Completer@?$static_lazy@VLanguagePackDiskCleanupTraceProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<LanguagePackDiskCleanupTraceProvider>::Completer::~Completer(void)
0x140007f4f  mov     rax, [rsp+38h+arg_8]
0x140007f54  add     rsp, 30h
0x140007f58  pop     rdi
0x140007f59  retn
```
