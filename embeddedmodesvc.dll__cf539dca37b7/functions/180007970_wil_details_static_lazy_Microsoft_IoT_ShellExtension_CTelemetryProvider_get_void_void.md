# wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::get(void (*)(void))

- ea: `0x180007970`
- end: `0x180007a2a`
- name: `?get@?$static_lazy@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@@details@wil@@QEAAPEAVCTelemetryProvider@ShellExtension@IoT@Microsoft@@P6AXXZ@Z`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007250`
- `0x180008ca0`

## callees

- `0x180002ec0`
- `0x18000709c`
- `0x180007970`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800079a6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800079a6`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::get(
        __int64 a1,
        void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  WINBOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(
         &`Microsoft::IoT::ShellExtension::CTelemetryProvider::Instance'::`2'::wrapper,
         0,
         &v6,
         (LPVOID *)&v8)
    && v6 )
  {
    v4 = &`Microsoft::IoT::ShellExtension::CTelemetryProvider::Instance'::`2'::wrapper;
    v8 = &qword_180026588;
    qword_180026588 = (__int64)&Microsoft::IoT::ShellExtension::CTelemetryProvider::`vftable';
    qword_180026590 = 0;
    byte_180026598 = 0;
    dword_18002659C = 0;
    qword_1800265A0 = (__int64)&`Microsoft::IoT::ShellExtension::CTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::Completer::~Completer(&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x180007970  mov     rax, rsp
0x180007973  mov     [rax+10h], rbx
0x180007977  mov     [rax+8], rcx
0x18000797b  push    rsi
0x18000797c  sub     rsp, 30h
0x180007980  mov     rbx, rdx
0x180007983  mov     qword ptr [rax+18h], 0
0x18000798b  lea     rsi, ?wrapper@?1??Instance@CTelemetryProvider@ShellExtension@IoT@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@@details@wil@@A; wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider> `Microsoft::IoT::ShellExtension::CTelemetryProvider::Instance(void)'::`2'::wrapper
0x180007992  mov     dword ptr [rax+8], 0
0x180007999  mov     rcx, rsi; lpInitOnce
0x18000799c  lea     r9, [rax+18h]; lpContext
0x1800079a0  lea     r8, [rax+8]; fPending
0x1800079a4  xor     edx, edx; dwFlags
0x1800079a6  call    cs:__imp_InitOnceBeginInitialize
0x1800079ac  test    eax, eax
0x1800079ae  jz      short loc_180007A1A
0x1800079b0  cmp     [rsp+38h+arg_0], 0
0x1800079b5  jz      short loc_180007A1A
0x1800079b7  lea     rax, qword_180026588
0x1800079be  mov     [rsp+38h+var_18], rsi
0x1800079c3  mov     [rsp+38h+arg_10], rax
0x1800079c8  lea     rax, ??_7CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::`vftable'
0x1800079cf  mov     cs:qword_180026588, rax
0x1800079d6  mov     cs:qword_180026590, 0
0x1800079e1  mov     cs:byte_180026598, 0
0x1800079e8  mov     cs:dword_18002659C, 0
0x1800079f2  lea     rax, ?__hInner@?1???0StaticHandle@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Microsoft::IoT::ShellExtension::CTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800079f9  mov     rcx, rbx; void (__cdecl *)()
0x1800079fc  mov     cs:qword_1800265A0, rax
0x180007a03  call    atexit
0x180007a08  lea     rcx, [rsp+38h+var_18]
0x180007a0d  mov     [rsp+38h+var_10], 0
0x180007a15  call    ??1Completer@?$static_lazy@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@@details@wil@@QEAA@XZ; wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::Completer::~Completer(void)
0x180007a1a  mov     rax, [rsp+38h+arg_10]
0x180007a1f  mov     rbx, [rsp+38h+arg_8]
0x180007a24  add     rsp, 30h
0x180007a28  pop     rsi
0x180007a29  retn
```
