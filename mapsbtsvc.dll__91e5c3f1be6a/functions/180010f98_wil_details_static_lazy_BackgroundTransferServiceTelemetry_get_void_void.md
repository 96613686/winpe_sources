# wil::details::static_lazy<BackgroundTransferServiceTelemetry>::get(void (*)(void))

- ea: `0x180010f98`
- end: `0x180011044`
- name: `?get@?$static_lazy@VBackgroundTransferServiceTelemetry@@@details@wil@@QEAAPEAVBackgroundTransferServiceTelemetry@@P6AXXZ@Z`
- size: `172`
- prototype: `__int64 *__fastcall(__int64, void (__cdecl *)())`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cba4`

## callees

- `0x18000222c`
- `0x18000b468`
- `0x180010f98`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010fce`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010fce`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<BackgroundTransferServiceTelemetry>::get(
        __int64 a1,
        void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  BOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`BackgroundTransferServiceTelemetry::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8)
    && v6 )
  {
    v4 = &`BackgroundTransferServiceTelemetry::Instance'::`2'::wrapper;
    v8 = &qword_18001D8D8;
    qword_18001D8E0 = 0;
    qword_18001D8D8 = (__int64)&wil::TraceLoggingProvider::`vftable';
    byte_18001D8E8 = 0;
    dword_18001D8EC = 0;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<BackgroundTransferServiceTelemetry>::Completer::~Completer((__int64)&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x180010f98  mov     rax, rsp
0x180010f9b  mov     [rax+10h], rbx
0x180010f9f  mov     [rax+8], rcx
0x180010fa3  push    rsi
0x180010fa4  sub     rsp, 30h
0x180010fa8  mov     rbx, rdx
0x180010fab  mov     qword ptr [rax+18h], 0
0x180010fb3  lea     rsi, ?wrapper@?1??Instance@BackgroundTransferServiceTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VBackgroundTransferServiceTelemetry@@@details@wil@@A; wil::details::static_lazy<BackgroundTransferServiceTelemetry> `BackgroundTransferServiceTelemetry::Instance(void)'::`2'::wrapper
0x180010fba  mov     dword ptr [rax+8], 0
0x180010fc1  mov     rcx, rsi; lpInitOnce
0x180010fc4  lea     r9, [rax+18h]; lpContext
0x180010fc8  lea     r8, [rax+8]; fPending
0x180010fcc  xor     edx, edx; dwFlags
0x180010fce  call    cs:__imp_InitOnceBeginInitialize
0x180010fd4  test    eax, eax
0x180010fd6  jz      short loc_180011034
0x180010fd8  cmp     [rsp+38h+arg_0], 0
0x180010fdd  jz      short loc_180011034
0x180010fdf  lea     rax, qword_18001D8D8
0x180010fe6  mov     [rsp+38h+var_18], rsi
0x180010feb  mov     [rsp+38h+arg_10], rax
0x180010ff0  mov     rcx, rbx; void (__cdecl *)()
0x180010ff3  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180010ffa  mov     cs:qword_18001D8E0, 0
0x180011005  mov     cs:qword_18001D8D8, rax
0x18001100c  mov     cs:byte_18001D8E8, 0
0x180011013  mov     cs:dword_18001D8EC, 0
0x18001101d  call    atexit
0x180011022  lea     rcx, [rsp+38h+var_18]
0x180011027  mov     [rsp+38h+var_10], 0
0x18001102f  call    ??1Completer@?$static_lazy@VBackgroundTransferServiceTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<BackgroundTransferServiceTelemetry>::Completer::~Completer(void)
0x180011034  mov     rax, [rsp+38h+arg_10]
0x180011039  mov     rbx, [rsp+38h+arg_8]
0x18001103e  add     rsp, 30h
0x180011042  pop     rsi
0x180011043  retn
```
