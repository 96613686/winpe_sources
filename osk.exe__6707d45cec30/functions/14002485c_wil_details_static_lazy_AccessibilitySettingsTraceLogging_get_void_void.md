# wil::details::static_lazy<AccessibilitySettingsTraceLogging>::get(void (*)(void))

- ea: `0x14002485c`
- end: `0x140024916`
- name: `?get@?$static_lazy@VAccessibilitySettingsTraceLogging@@@details@wil@@QEAAPEAVAccessibilitySettingsTraceLogging@@P6AXXZ@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002219c`

## callees

- `0x1400027f4`
- `0x14001d7d4`
- `0x14002485c`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140024892`
- `KERNEL32!InitOnceBeginInitialize` at `0x140024892`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<AccessibilitySettingsTraceLogging>::get(__int64 a1, void (__cdecl *a2)())
{
  __int64 v3; // rdx
  void (*v4)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  union _RTL_RUN_ONCE *v6; // [rsp+20h] [rbp-18h] BYREF
  int v7; // [rsp+28h] [rbp-10h]
  WINBOOL v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]
  __int64 *v10; // [rsp+50h] [rbp+18h] BYREF

  v9 = HIDWORD(a1);
  v10 = 0;
  v8 = 0;
  if ( InitOnceBeginInitialize(&`AccessibilitySettingsTraceLogging::Instance'::`2'::wrapper, 0, &v8, (LPVOID *)&v10)
    && v8 )
  {
    v6 = &`AccessibilitySettingsTraceLogging::Instance'::`2'::wrapper;
    v10 = &qword_140037890;
    qword_140037890 = (__int64)&wil::details::FeatureLogging::`vftable';
    qword_140037898 = 0;
    byte_1400378A0 = 0;
    dword_1400378A4 = 0;
    qword_1400378A8 = (__int64)&`AccessibilitySettingsTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v7 = 0;
    wil::details::static_lazy<AccessibilitySettingsTraceLogging>::Completer::~Completer(&v6, v3, v4);
  }
  return v10;
}

```

## disassembly

```asm
0x14002485c  mov     rax, rsp
0x14002485f  mov     [rax+10h], rbx
0x140024863  mov     [rax+8], rcx
0x140024867  push    rsi
0x140024868  sub     rsp, 30h
0x14002486c  mov     rbx, rdx
0x14002486f  mov     qword ptr [rax+18h], 0
0x140024877  lea     rsi, ?wrapper@?1??Instance@AccessibilitySettingsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VAccessibilitySettingsTraceLogging@@@details@wil@@A; wil::details::static_lazy<AccessibilitySettingsTraceLogging> `AccessibilitySettingsTraceLogging::Instance(void)'::`2'::wrapper
0x14002487e  mov     dword ptr [rax+8], 0
0x140024885  mov     rcx, rsi; lpInitOnce
0x140024888  lea     r9, [rax+18h]; lpContext
0x14002488c  lea     r8, [rax+8]; fPending
0x140024890  xor     edx, edx; dwFlags
0x140024892  call    cs:__imp_InitOnceBeginInitialize
0x140024898  test    eax, eax
0x14002489a  jz      short loc_140024906
0x14002489c  cmp     [rsp+38h+arg_0], 0
0x1400248a1  jz      short loc_140024906
0x1400248a3  lea     rax, qword_140037890
0x1400248aa  mov     [rsp+38h+var_18], rsi
0x1400248af  mov     [rsp+38h+arg_10], rax
0x1400248b4  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1400248bb  mov     cs:qword_140037890, rax
0x1400248c2  mov     cs:qword_140037898, 0
0x1400248cd  mov     cs:byte_1400378A0, 0
0x1400248d4  mov     cs:dword_1400378A4, 0
0x1400248de  lea     rax, ?__hInner@?1???0StaticHandle@AccessibilitySettingsTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AccessibilitySettingsTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1400248e5  mov     rcx, rbx; void (__cdecl *)()
0x1400248e8  mov     cs:qword_1400378A8, rax
0x1400248ef  call    atexit
0x1400248f4  lea     rcx, [rsp+38h+var_18]
0x1400248f9  mov     [rsp+38h+var_10], 0
0x140024901  call    ??1Completer@?$static_lazy@VAccessibilitySettingsTraceLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<AccessibilitySettingsTraceLogging>::Completer::~Completer(void)
0x140024906  mov     rax, [rsp+38h+arg_10]
0x14002490b  mov     rbx, [rsp+38h+arg_8]
0x140024910  add     rsp, 30h
0x140024914  pop     rsi
0x140024915  retn
```
