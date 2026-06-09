# CTelemetryFrames::FrameEnded(bool,bool,unsigned __int64)

- ea: `0x180017bd0`
- end: `0x180017d20`
- name: `?FrameEnded@CTelemetryFrames@@SAX_N0_K@Z`
- size: `336`
- prototype: `void __fastcall(bool, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016b10`

## callees

- `0x180017bd0`
- `0x180017d30`
- `0x180018224`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017c1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017c1f`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180017c2d`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180017c2d`

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
  byte_1803BB2E0 = dword_1803BADF8 != dword_1803BB378;
  CycleTime = 0;
  if ( qword_1803BB360 )
  {
    CurrentThread = GetCurrentThread();
    v6 = QueryThreadCycleTime(CurrentThread, &CycleTime);
    v3 = CycleTime;
    if ( v6 )
      qword_1803BAD98 += CycleTime - qword_1803BB360;
  }
  *((_QWORD *)&xmmword_1803BAEC0 + 1) = 0;
  qword_1803BADD0 = v3 - v4;
  if ( 1000000 * ((unsigned __int64)-qword_1803BB338 % g_qpcFrequency.QuadPart) / g_qpcFrequency.QuadPart
     + 1000000 * ((unsigned __int64)-qword_1803BB338 / g_qpcFrequency.QuadPart) > (unsigned int)dword_1803BAD94 )
    dword_1803BAD94 = 1000000 * ((unsigned __int64)-qword_1803BB338 % g_qpcFrequency.QuadPart) / g_qpcFrequency.QuadPart
                    + 1000000 * ((unsigned __int64)-qword_1803BB338 / g_qpcFrequency.QuadPart);
  dword_1803BA16C = 3;
  anonymous_namespace_::OutputCurrentFrameToEtw();
  v7 = (unsigned __int64)(qword_1803BB338 - xmmword_1803BAEC0) % g_qpcFrequency.QuadPart;
  if ( 1000 * ((unsigned __int64)(qword_1803BB338 - xmmword_1803BAEC0) / g_qpcFrequency.QuadPart)
     + 1000 * v7 / g_qpcFrequency.QuadPart >= (unsigned int)CCommonRegistryData::TelemetryFramesSequenceMaximumPeriodMilliseconds )
    anonymous_namespace_::SealCurrentFrameSequence(
      (unsigned int)CCommonRegistryData::TelemetryFramesSequenceMaximumPeriodMilliseconds,
      1000 * v7 % g_qpcFrequency.QuadPart);
}

```

## disassembly

```asm
0x180017bd0  mov     [rsp+CycleTime], r8
0x180017bd5  push    rbx
0x180017bd6  sub     rsp, 20h
0x180017bda  test    dl, dl
0x180017bdc  jz      short loc_180017BE8
0x180017bde  or      cs:dword_1803BAD70, 80h
0x180017be8  mov     eax, cs:dword_1803BB378
0x180017bee  cmp     cs:dword_1803BADF8, eax
0x180017bf4  jnz     loc_180017D19
0x180017bfa  xor     al, al
0x180017bfc  inc     cs:dword_1803BAD7C
0x180017c02  xor     ecx, ecx
0x180017c04  cmp     cs:qword_1803BB360, rcx
0x180017c0b  mov     rbx, cs:CycleTime
0x180017c12  mov     cs:byte_1803BB2E0, al
0x180017c18  mov     [rsp+28h+CycleTime], rcx
0x180017c1d  jz      short loc_180017C4D
0x180017c1f  call    cs:__imp_GetCurrentThread
0x180017c25  mov     rcx, rax; ThreadHandle
0x180017c28  lea     rdx, [rsp+28h+CycleTime]; CycleTime
0x180017c2d  call    cs:__imp_QueryThreadCycleTime
0x180017c33  mov     rcx, [rsp+28h+CycleTime]
0x180017c38  test    eax, eax
0x180017c3a  jz      short loc_180017C4D
0x180017c3c  mov     rax, rcx
0x180017c3f  sub     rax, cs:qword_1803BB360
0x180017c46  add     cs:qword_1803BAD98, rax
0x180017c4d  mov     r9, cs:qword_1803BB338
0x180017c54  xor     edx, edx
0x180017c56  sub     rcx, rbx
0x180017c59  mov     qword ptr cs:xmmword_1803BAEC0+8, 0
0x180017c64  neg     r9
0x180017c67  mov     cs:qword_1803BADD0, rcx
0x180017c6e  mov     rcx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x180017c75  mov     rax, r9
0x180017c78  div     rcx
0x180017c7b  mov     rdx, rax
0x180017c7e  mov     r8, rax
0x180017c81  imul    rdx, rcx
0x180017c85  sub     r9, rdx
0x180017c88  xor     edx, edx
0x180017c8a  imul    rax, r9, 0F4240h
0x180017c91  div     rcx
0x180017c94  imul    rdx, r8, 0F4240h
0x180017c9b  add     rdx, rax
0x180017c9e  mov     eax, cs:dword_1803BAD94
0x180017ca4  cmp     rdx, rax
0x180017ca7  jbe     short loc_180017CAF
0x180017ca9  mov     cs:dword_1803BAD94, edx
0x180017caf  mov     cs:dword_1803BA16C, 3
0x180017cb9  call    _anonymous_namespace___OutputCurrentFrameToEtw
0x180017cbe  mov     rcx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x180017cc5  xor     edx, edx
0x180017cc7  mov     r9, cs:qword_1803BB338
0x180017cce  sub     r9, qword ptr cs:xmmword_1803BAEC0
0x180017cd5  mov     rax, r9
0x180017cd8  div     rcx
0x180017cdb  mov     rdx, rax
0x180017cde  mov     r8, rax
0x180017ce1  imul    rdx, rcx
0x180017ce5  sub     r9, rdx
0x180017ce8  xor     edx, edx
0x180017cea  imul    rax, r9, 3E8h
0x180017cf1  div     rcx
0x180017cf4  imul    rcx, r8, 3E8h
0x180017cfb  add     rax, rcx
0x180017cfe  mov     ecx, cs:?TelemetryFramesSequenceMaximumPeriodMilliseconds@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::TelemetryFramesSequenceMaximumPeriodMilliseconds
0x180017d04  cmp     rax, rcx
0x180017d07  jb      short loc_180017D13
0x180017d09  add     rsp, 20h
0x180017d0d  pop     rbx
0x180017d0e  jmp     _anonymous_namespace___SealCurrentFrameSequence
0x180017d13  add     rsp, 20h
0x180017d17  pop     rbx
0x180017d18  retn
0x180017d19  mov     al, 1
0x180017d1b  jmp     loc_180017BFC
```
