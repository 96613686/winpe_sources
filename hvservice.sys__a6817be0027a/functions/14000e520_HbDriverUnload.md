# HbDriverUnload

- ea: `0x14000e520`
- end: `0x14000e5f9`
- name: `HbDriverUnload`
- size: `217`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140001600`
- `0x14000e520`
- `0x14000e6c8`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14000e52b`
- `HAL!KeQueryPerformanceCounter` at `0x14000e52b`

## string_xrefs

- `0x14000e5ba`: `HvService teardown. Version: %s, Driver loaded in %llu ms, Driver unloaded in %llu ms`

## pseudocode

```c
__int64 HbDriverUnload()
{
  LARGE_INTEGER PerformanceCounter; // rax
  LONGLONG v1; // r9
  __int64 v2; // rax

  PerformanceCounter = KeQueryPerformanceCounter(&stru_1400092B8);
  qword_1400092B0 = PerformanceCounter.QuadPart;
  if ( qword_140009220 && PerformanceCounter.QuadPart && stru_1400092B8.QuadPart )
    v1 = 1000 * (PerformanceCounter.QuadPart - qword_140009220) / stru_1400092B8.QuadPart;
  else
    v1 = 0;
  if ( qword_1400091D8[0] && qword_140009208 && stru_140009210.QuadPart )
    v2 = 1000 * (qword_140009208 - qword_1400091D8[0]) / stru_140009210.QuadPart;
  else
    v2 = 0;
  HbpTraceEvent(
    3,
    "HbRecordPhaseTimestamp",
    163,
    "HvService teardown. Version: %s, Driver loaded in %llu ms, Driver unloaded in %llu ms",
    "10011.16384.GitEnlistment(RnDcbldB).260520-1434",
    v2,
    v1);
  HbDriverLastRecordedLifecyclePhase = 9;
  return TraceLoggingUnregister_EtwUnregister(&dword_140009088);
}

```

## disassembly

```asm
0x14000e520  sub     rsp, 48h
0x14000e524  lea     rcx, stru_1400092B8; PerformanceFrequency
0x14000e52b  call    cs:__imp_KeQueryPerformanceCounter
0x14000e532  nop     dword ptr [rax+rax+00h]
0x14000e537  mov     cs:qword_1400092B0, rax
0x14000e53e  mov     rdx, cs:qword_140009220
0x14000e545  test    rdx, rdx
0x14000e548  jz      short loc_14000E56F
0x14000e54a  test    rax, rax
0x14000e54d  jz      short loc_14000E56F
0x14000e54f  mov     rcx, qword ptr cs:stru_1400092B8
0x14000e556  test    rcx, rcx
0x14000e559  jz      short loc_14000E56F
0x14000e55b  sub     rax, rdx
0x14000e55e  imul    rax, 3E8h
0x14000e565  cqo
0x14000e567  idiv    rcx
0x14000e56a  mov     r9, rax
0x14000e56d  jmp     short loc_14000E572
0x14000e56f  xor     r9d, r9d
0x14000e572  mov     rcx, cs:qword_1400091D8
0x14000e579  test    rcx, rcx
0x14000e57c  jz      short loc_14000E5A7
0x14000e57e  mov     rax, cs:qword_140009208
0x14000e585  test    rax, rax
0x14000e588  jz      short loc_14000E5A7
0x14000e58a  mov     r8, qword ptr cs:stru_140009210
0x14000e591  test    r8, r8
0x14000e594  jz      short loc_14000E5A7
0x14000e596  sub     rax, rcx
0x14000e599  imul    rax, 3E8h
0x14000e5a0  cqo
0x14000e5a2  idiv    r8
0x14000e5a5  jmp     short loc_14000E5A9
0x14000e5a7  xor     eax, eax
0x14000e5a9  mov     [rsp+48h+var_18], r9
0x14000e5ae  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x14000e5b5  mov     [rsp+48h+var_20], rax
0x14000e5ba  lea     r9, aHvserviceTeard; "HvService teardown. Version: %s, Driver"...
0x14000e5c1  lea     rax, a1001116384Gite; "10011.16384.GitEnlistment(RnDcbldB).260"...
0x14000e5c8  mov     r8d, 0A3h
0x14000e5ce  mov     ecx, 3
0x14000e5d3  mov     [rsp+48h+var_28], rax
0x14000e5d8  call    HbpTraceEvent
0x14000e5dd  lea     rcx, dword_140009088
0x14000e5e4  mov     cs:HbDriverLastRecordedLifecyclePhase, 9
0x14000e5ee  call    TraceLoggingUnregister_EtwUnregister
0x14000e5f3  add     rsp, 48h
0x14000e5f7  retn
```
