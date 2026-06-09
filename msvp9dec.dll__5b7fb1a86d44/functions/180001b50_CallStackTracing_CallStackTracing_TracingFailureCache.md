# CallStackTracing::CallStackTracing(TracingFailureCache *)

- ea: `0x180001b50`
- end: `0x180001c55`
- name: `??0CallStackTracing@@QEAA@PEAVTracingFailureCache@@@Z`
- size: `261`
- prototype: `CallStackTracing *__fastcall(CallStackTracing *__hidden this, struct TracingFailureCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001b30`

## callees

- `0x180001b50`
- `0x180001ce0`
- `0x180001cf0`
- `0x18000389c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001b85`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001b92`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001bbe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001b85`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001b92`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001bbe`

## pseudocode

```c
CallStackTracing *__fastcall CallStackTracing::CallStackTracing(CallStackTracing *this, struct TracingFailureCache *a2)
{
  CallStackInfo *v2; // rdi
  __int64 v3; // rbx
  CallStackTracing *result; // rax

  byte_18000A4C8 = 0;
  qword_18000A4C0 = &CallStackTracing::`vftable';
  dword_18000A4CC = -1;
  InitializeCriticalSection(&CriticalSection);
  InitializeCriticalSection(&stru_18000A4F8);
  byte_18000A520 = 0;
  qword_18000A528 = (__int64)&CFreeList<CallStackContextNode,16>::`vftable';
  dword_18000A530 = 16;
  InitializeCriticalSection(&stru_18000A538);
  v2 = (CallStackInfo *)qword_18000A590;
  qword_18000A560 = 0;
  qword_18000A568 = 0;
  v3 = 124;
  xmmword_18000A570 = 0;
  qword_18000A580 = 0;
  byte_18000A588 = 0;
  do
  {
    CallStackInfo::CallStackInfo(v2);
    v2 = (CallStackInfo *)((char *)v2 + 16);
    --v3;
  }
  while ( v3 );
  dword_18000AD58 = 0;
  memset_0(qword_18000A590, 0, sizeof(qword_18000A590));
  CallStackContext::ClearState((GUID *)qword_18000A590);
  result = (CallStackTracing *)&qword_18000A4C0;
  dword_18000AD50 = 0;
  return result;
}

```

## disassembly

```asm
0x180001b50  mov     [rsp+arg_0], rbx
0x180001b55  mov     [rsp+arg_8], rsi
0x180001b5a  push    rdi
0x180001b5b  sub     rsp, 20h
0x180001b5f  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180001b66  mov     cs:byte_18000A4C8, 0
0x180001b6d  lea     rcx, CriticalSection; lpCriticalSection
0x180001b74  mov     cs:qword_18000A4C0, rax
0x180001b7b  mov     cs:dword_18000A4CC, 0FFFFFFFFh
0x180001b85  call    cs:__imp_InitializeCriticalSection
0x180001b8b  lea     rcx, stru_18000A4F8; lpCriticalSection
0x180001b92  call    cs:__imp_InitializeCriticalSection
0x180001b98  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x180001b9f  mov     cs:byte_18000A520, 0
0x180001ba6  lea     rcx, stru_18000A538; lpCriticalSection
0x180001bad  mov     cs:qword_18000A528, rax
0x180001bb4  mov     cs:dword_18000A530, 10h
0x180001bbe  call    cs:__imp_InitializeCriticalSection
0x180001bc4  xor     esi, esi
0x180001bc6  lea     rdi, qword_18000A590
0x180001bcd  xorps   xmm0, xmm0
0x180001bd0  mov     cs:qword_18000A560, rsi
0x180001bd7  mov     cs:qword_18000A568, rsi
0x180001bde  mov     ebx, 7Ch ; '|'
0x180001be3  movdqa  cs:xmmword_18000A570, xmm0
0x180001beb  mov     cs:qword_18000A580, rsi
0x180001bf2  mov     cs:byte_18000A588, sil
0x180001bf9  nop     dword ptr [rax+00000000h]
0x180001c00  mov     rcx, rdi; this
0x180001c03  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x180001c08  add     rdi, 10h
0x180001c0c  sub     rbx, 1
0x180001c10  jnz     short loc_180001C00
0x180001c12  xor     edx, edx; Val
0x180001c14  mov     cs:dword_18000AD58, esi
0x180001c1a  mov     r8d, 7C0h; Size
0x180001c20  lea     rcx, qword_18000A590; void *
0x180001c27  call    memset_0
0x180001c2c  lea     rcx, qword_18000A590; this
0x180001c33  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180001c38  mov     rbx, [rsp+28h+arg_0]
0x180001c3d  lea     rax, qword_18000A4C0
0x180001c44  mov     cs:dword_18000AD50, esi
0x180001c4a  mov     rsi, [rsp+28h+arg_8]
0x180001c4f  add     rsp, 20h
0x180001c53  pop     rdi
0x180001c54  retn
```
