# CTelemetryFrames::FrameEnded(bool,bool,unsigned __int64)

- ea: `0x18010c860`
- end: `0x18010c9b0`
- name: `?FrameEnded@CTelemetryFrames@@SAX_N0_K@Z`
- size: `336`
- prototype: `void __fastcall(bool, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010b7d0`

## callees

- `0x18010c860`
- `0x18010c9c0`
- `0x18010ceb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010c8af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010c8af`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010c8bd`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010c8bd`

## pseudocode

```c
void __fastcall CTelemetryFrames::FrameEnded(__int64 a1, char a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rbx
  HANDLE CurrentThread; // rax
  BOOL v6; // eax
  unsigned __int64 v7; // r9
  unsigned __int64 CycleTime; // [rsp+40h] [rbp+18h] BYREF

  CycleTime = a3;
  if ( a2 )
    dword_1803BAD70 |= 0x80u;
  ++dword_1803BAD7C;
  v3 = 0;
  v4 = ::CycleTime;
  byte_1803BB350 = dword_1803BADF8 != dword_1803BB388;
  CycleTime = 0;
  if ( qword_1803BB2F8 )
  {
    CurrentThread = GetCurrentThread();
    v6 = QueryThreadCycleTime(CurrentThread, &CycleTime);
    v3 = CycleTime;
    if ( v6 )
      qword_1803BAD98 += CycleTime - qword_1803BB2F8;
  }
  *((_QWORD *)&xmmword_1803BAEC0 + 1) = 0;
  qword_1803BADD0 = v3 - v4;
  if ( 1000000 * ((unsigned __int64)-qword_1803BB348 % g_qpcFrequency.QuadPart) / g_qpcFrequency.QuadPart
     + 1000000 * ((unsigned __int64)-qword_1803BB348 / g_qpcFrequency.QuadPart) > (unsigned int)dword_1803BAD94 )
    dword_1803BAD94 = 1000000 * ((unsigned __int64)-qword_1803BB348 % g_qpcFrequency.QuadPart) / g_qpcFrequency.QuadPart
                    + 1000000 * ((unsigned __int64)-qword_1803BB348 / g_qpcFrequency.QuadPart);
  dword_1803BA16C = 3;
  anonymous_namespace_::OutputCurrentFrameToEtw();
  v7 = (unsigned __int64)(qword_1803BB348 - xmmword_1803BAEC0) % g_qpcFrequency.QuadPart;
  if ( 1000 * ((unsigned __int64)(qword_1803BB348 - xmmword_1803BAEC0) / g_qpcFrequency.QuadPart)
     + 1000 * v7 / g_qpcFrequency.QuadPart >= (unsigned int)CCommonRegistryData::TelemetryFramesSequenceMaximumPeriodMilliseconds )
    anonymous_namespace_::SealCurrentFrameSequence(
      (unsigned int)CCommonRegistryData::TelemetryFramesSequenceMaximumPeriodMilliseconds,
      1000 * v7 % g_qpcFrequency.QuadPart);
}

```

## disassembly

```asm
0x18010c860  mov     [rsp+CycleTime], r8
0x18010c865  push    rbx
0x18010c866  sub     rsp, 20h
0x18010c86a  test    dl, dl
0x18010c86c  jz      short loc_18010C878
0x18010c86e  or      cs:dword_1803BAD70, 80h
0x18010c878  mov     eax, cs:dword_1803BB388
0x18010c87e  cmp     cs:dword_1803BADF8, eax
0x18010c884  jnz     loc_18010C9A9
0x18010c88a  xor     al, al
0x18010c88c  inc     cs:dword_1803BAD7C
0x18010c892  xor     ecx, ecx
0x18010c894  cmp     cs:qword_1803BB2F8, rcx
0x18010c89b  mov     rbx, cs:CycleTime
0x18010c8a2  mov     cs:byte_1803BB350, al
0x18010c8a8  mov     [rsp+28h+CycleTime], rcx
0x18010c8ad  jz      short loc_18010C8DD
0x18010c8af  call    cs:__imp_GetCurrentThread
0x18010c8b5  mov     rcx, rax; ThreadHandle
0x18010c8b8  lea     rdx, [rsp+28h+CycleTime]; CycleTime
0x18010c8bd  call    cs:__imp_QueryThreadCycleTime
0x18010c8c3  mov     rcx, [rsp+28h+CycleTime]
0x18010c8c8  test    eax, eax
0x18010c8ca  jz      short loc_18010C8DD
0x18010c8cc  mov     rax, rcx
0x18010c8cf  sub     rax, cs:qword_1803BB2F8
0x18010c8d6  add     cs:qword_1803BAD98, rax
0x18010c8dd  mov     r9, cs:qword_1803BB348
0x18010c8e4  xor     edx, edx
0x18010c8e6  sub     rcx, rbx
0x18010c8e9  mov     qword ptr cs:xmmword_1803BAEC0+8, 0
0x18010c8f4  neg     r9
0x18010c8f7  mov     cs:qword_1803BADD0, rcx
0x18010c8fe  mov     rcx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x18010c905  mov     rax, r9
0x18010c908  div     rcx
0x18010c90b  mov     rdx, rax
0x18010c90e  mov     r8, rax
0x18010c911  imul    rdx, rcx
0x18010c915  sub     r9, rdx
0x18010c918  xor     edx, edx
0x18010c91a  imul    rax, r9, 0F4240h
0x18010c921  div     rcx
0x18010c924  imul    rdx, r8, 0F4240h
0x18010c92b  add     rdx, rax
0x18010c92e  mov     eax, cs:dword_1803BAD94
0x18010c934  cmp     rdx, rax
0x18010c937  jbe     short loc_18010C93F
0x18010c939  mov     cs:dword_1803BAD94, edx
0x18010c93f  mov     cs:dword_1803BA16C, 3
0x18010c949  call    _anonymous_namespace___OutputCurrentFrameToEtw
0x18010c94e  mov     rcx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x18010c955  xor     edx, edx
0x18010c957  mov     r9, cs:qword_1803BB348
0x18010c95e  sub     r9, qword ptr cs:xmmword_1803BAEC0
0x18010c965  mov     rax, r9
0x18010c968  div     rcx
0x18010c96b  mov     rdx, rax
0x18010c96e  mov     r8, rax
0x18010c971  imul    rdx, rcx
0x18010c975  sub     r9, rdx
0x18010c978  xor     edx, edx
0x18010c97a  imul    rax, r9, 3E8h
0x18010c981  div     rcx
0x18010c984  imul    rcx, r8, 3E8h
0x18010c98b  add     rax, rcx
0x18010c98e  mov     ecx, cs:?TelemetryFramesSequenceMaximumPeriodMilliseconds@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::TelemetryFramesSequenceMaximumPeriodMilliseconds
0x18010c994  cmp     rax, rcx
0x18010c997  jb      short loc_18010C9A3
0x18010c999  add     rsp, 20h
0x18010c99d  pop     rbx
0x18010c99e  jmp     _anonymous_namespace___SealCurrentFrameSequence
0x18010c9a3  add     rsp, 20h
0x18010c9a7  pop     rbx
0x18010c9a8  retn
0x18010c9a9  mov     al, 1
0x18010c9ab  jmp     loc_18010C88C
```
