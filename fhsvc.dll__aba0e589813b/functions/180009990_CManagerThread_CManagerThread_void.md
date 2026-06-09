# CManagerThread::CManagerThread(void)

- ea: `0x180009990`
- end: `0x180009a93`
- name: `??0CManagerThread@@QEAA@XZ`
- size: `259`
- prototype: `CManagerThread *__fastcall(CManagerThread *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001170`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180009a65`
- `KERNEL32!InitializeCriticalSection` at `0x180009a72`
- `KERNEL32!InitializeCriticalSection` at `0x180009a65`
- `KERNEL32!InitializeCriticalSection` at `0x180009a72`

## pseudocode

```c
CManagerThread *__fastcall CManagerThread::CManagerThread(CManagerThread *this)
{
  CManagerThread *result; // rax

  xmmword_180019A30 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  g_ManagerThread = 0;
  xmmword_1800198F0 = 0;
  *(__m128i *)byte_180019910 = _mm_load_si128((const __m128i *)&_xmm);
  xmmword_180019A20 = 0;
  xmmword_180019A40 = 0;
  xmmword_180019A80 = 0;
  dword_1800198E8 = 0;
  xmmword_180019900 = 0;
  qword_180019948 = 0;
  qword_180019950 = 0;
  dword_180019958 = 0;
  qword_180019960 = 0;
  *(_QWORD *)&qword_1800199B8 = 0;
  pwa = 0;
  qword_1800199C8 = 0;
  hEvent = 0;
  qword_1800199E0 = 0;
  dword_1800199E8 = 0;
  qword_180019A18 = 0;
  xmmword_180019A50 = 0;
  xmmword_180019A60 = xmmword_180019A30;
  qword_180019A70 = 0;
  dword_180019A78 = 0;
  InitializeCriticalSection(&CriticalSection);
  InitializeCriticalSection(&stru_1800199F0);
  result = (CManagerThread *)&g_ManagerThread;
  qword_1800199B0 = 0;
  qword_1800199D0 = 0;
  return result;
}

```

## disassembly

```asm
0x180009990  push    rbx
0x180009992  sub     rsp, 20h
0x180009996  movdqa  xmm2, cs:__xmm@000000000000000a0000000000000000
0x18000999e  lea     rcx, CriticalSection; lpCriticalSection
0x1800099a5  xor     ebx, ebx
0x1800099a7  movdqa  cs:xmmword_180019A30, xmm2
0x1800099af  xorps   xmm0, xmm0
0x1800099b2  mov     cs:?g_ManagerThread@@3VCManagerThread@@A, rbx; CManagerThread g_ManagerThread
0x1800099b9  movdqa  cs:xmmword_1800198F0, xmm0
0x1800099c1  xorps   xmm1, xmm1
0x1800099c4  movdqa  xmm0, cs:__xmm@0000000000000000000000000000000a
0x1800099cc  movdqa  xmmword ptr cs:byte_180019910, xmm0
0x1800099d4  xorps   xmm0, xmm0
0x1800099d7  movdqa  cs:xmmword_180019A20, xmm0
0x1800099df  movdqa  cs:xmmword_180019A40, xmm0
0x1800099e7  movdqa  cs:xmmword_180019A80, xmm0
0x1800099ef  mov     cs:dword_1800198E8, ebx
0x1800099f5  movdqa  cs:xmmword_180019900, xmm1
0x1800099fd  mov     cs:qword_180019948, rbx
0x180009a04  mov     cs:qword_180019950, rbx
0x180009a0b  mov     cs:dword_180019958, ebx
0x180009a11  mov     cs:qword_180019960, rbx
0x180009a18  mov     cs:qword_1800199B8, rbx
0x180009a1f  mov     cs:pwa, rbx
0x180009a26  mov     cs:qword_1800199C8, rbx
0x180009a2d  mov     cs:hEvent, rbx
0x180009a34  mov     cs:qword_1800199E0, rbx
0x180009a3b  mov     cs:dword_1800199E8, ebx
0x180009a41  mov     cs:qword_180019A18, rbx
0x180009a48  movdqa  cs:xmmword_180019A50, xmm1
0x180009a50  movdqa  cs:xmmword_180019A60, xmm2
0x180009a58  mov     cs:qword_180019A70, rbx
0x180009a5f  mov     cs:dword_180019A78, ebx
0x180009a65  call    cs:__imp_InitializeCriticalSection
0x180009a6b  lea     rcx, stru_1800199F0; lpCriticalSection
0x180009a72  call    cs:__imp_InitializeCriticalSection
0x180009a78  lea     rax, ?g_ManagerThread@@3VCManagerThread@@A; CManagerThread g_ManagerThread
0x180009a7f  mov     cs:qword_1800199B0, rbx
0x180009a86  mov     cs:qword_1800199D0, rbx
0x180009a8d  add     rsp, 20h
0x180009a91  pop     rbx
0x180009a92  retn
```
