# _dynamic_initializer_for__s_disabledContext__

- ea: `0x180001010`
- end: `0x180001113`
- name: `_dynamic_initializer_for__s_disabledContext__`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001a38`
- `0x180001eb0`
- `0x180007db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001026`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001033`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001061`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001026`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001033`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800010ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800010ec`

## pseudocode

```c
int dynamic_initializer_for__s_disabledContext__()
{
  CallStackInfo *v0; // rbx
  __int64 v1; // rdi

  InitializeCriticalSection(&CriticalSection);
  InitializeCriticalSection(&stru_1800220B8);
  dword_1800220F0 = 16;
  qword_1800220E8 = (__int64)&CFreeList<CallStackContextNode,16>::`vftable';
  byte_1800220E0 = 0;
  InitializeCriticalSection(&stru_1800220F8);
  qword_180022120 = 0;
  xmmword_180022130 = 0;
  v0 = (CallStackInfo *)qword_180022150;
  qword_180022128 = 0;
  v1 = 124;
  qword_180022140 = 0;
  byte_180022148 = 0;
  do
  {
    CallStackInfo::CallStackInfo(v0);
    v0 = (CallStackInfo *)((char *)v0 + 16);
    --v1;
  }
  while ( v1 );
  dword_180022918 = 0;
  memset_0(qword_180022150, 0, sizeof(qword_180022150));
  dword_180022914 = 0;
  qword_180022930 = 0;
  xmmword_180022920 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  dword_18002291C = 0;
  dword_180022938 = 0;
  GetCurrentThreadId();
  dword_180022910 = 0;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__s_disabledContext__);
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rbx
0x180001015  mov     [rsp+arg_8], rsi
0x18000101a  push    rdi
0x18000101b  sub     rsp, 20h
0x18000101f  lea     rcx, CriticalSection; lpCriticalSection
0x180001026  call    cs:__imp_InitializeCriticalSection
0x18000102c  lea     rcx, stru_1800220B8; lpCriticalSection
0x180001033  call    cs:__imp_InitializeCriticalSection
0x180001039  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x180001040  mov     cs:dword_1800220F0, 10h
0x18000104a  xor     esi, esi
0x18000104c  mov     cs:qword_1800220E8, rax
0x180001053  lea     rcx, stru_1800220F8; lpCriticalSection
0x18000105a  mov     cs:byte_1800220E0, sil
0x180001061  call    cs:__imp_InitializeCriticalSection
0x180001067  xorps   xmm0, xmm0
0x18000106a  mov     cs:qword_180022120, rsi
0x180001071  movdqa  cs:xmmword_180022130, xmm0
0x180001079  lea     rbx, qword_180022150
0x180001080  mov     cs:qword_180022128, rsi
0x180001087  lea     edi, [rsi+7Ch]
0x18000108a  mov     cs:qword_180022140, rsi
0x180001091  mov     cs:byte_180022148, sil
0x180001098  mov     rcx, rbx; this
0x18000109b  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x1800010a0  add     rbx, 10h
0x1800010a4  sub     rdi, 1
0x1800010a8  jnz     short loc_180001098
0x1800010aa  xor     edx, edx; Val
0x1800010ac  mov     cs:dword_180022918, esi
0x1800010b2  mov     r8d, 7C0h; Size
0x1800010b8  lea     rcx, qword_180022150; void *
0x1800010bf  call    memset_0
0x1800010c4  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800010cb  mov     cs:dword_180022914, esi
0x1800010d1  mov     cs:qword_180022930, rsi
0x1800010d8  movdqu  cs:xmmword_180022920, xmm0
0x1800010e0  mov     cs:dword_18002291C, esi
0x1800010e6  mov     cs:dword_180022938, esi
0x1800010ec  call    cs:__imp_GetCurrentThreadId
0x1800010f2  lea     rcx, _dynamic_atexit_destructor_for__s_disabledContext__
0x1800010f9  mov     cs:dword_180022910, esi
0x1800010ff  mov     rbx, [rsp+28h+arg_0]
0x180001104  mov     rsi, [rsp+28h+arg_8]
0x180001109  add     rsp, 20h
0x18000110d  pop     rdi
0x18000110e  jmp     atexit
```
