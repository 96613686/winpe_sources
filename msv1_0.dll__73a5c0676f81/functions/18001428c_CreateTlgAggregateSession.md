# CreateTlgAggregateSession

- ea: `0x18001428c`
- end: `0x18001434d`
- name: `CreateTlgAggregateSession`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001418c`

## callees

- `0x18001428c`
- `0x18002ef48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800142d4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800142d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800142f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800142f6`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_180089B10 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18001428c  mov     [rsp+arg_0], rbx
0x180014291  mov     [rsp+arg_18], rsi
0x180014296  push    rdi
0x180014297  sub     rsp, 20h
0x18001429b  mov     sil, cl
0x18001429e  xor     dil, dil
0x1800142a1  mov     [rsp+28h+arg_8], dil
0x1800142a6  call    cs:__imp_GetProcessHeap
0x1800142ac  mov     rcx, rax; hHeap
0x1800142af  mov     edx, 8; dwFlags
0x1800142b4  mov     r8d, 168h; dwBytes
0x1800142ba  call    cs:__imp_HeapAlloc
0x1800142c0  mov     rbx, rax
0x1800142c3  mov     [rsp+28h+arg_10], rax
0x1800142c8  test    rax, rax
0x1800142cb  jz      short loc_180014324
0x1800142cd  lea     rcx, [rax+108h]; SRWLock
0x1800142d4  call    cs:__imp_InitializeSRWLock
0x1800142da  test    sil, sil
0x1800142dd  jz      short loc_18001433C
0x1800142df  mov     ecx, cs:dword_180089B10
0x1800142e5  test    ecx, ecx
0x1800142e7  jnz     short loc_180014324
0x1800142e9  xor     r8d, r8d; pcbe
0x1800142ec  mov     rdx, rbx; pv
0x1800142ef  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800142f6  call    cs:__imp_CreateThreadpoolTimer
0x1800142fc  mov     [rbx+158h], rax
0x180014303  jmp     short loc_18001431A
0x180014305  mov     eax, 1
0x18001430a  xchg    eax, cs:dword_180089B10
0x180014310  mov     dil, [rsp+28h+arg_8]
0x180014315  mov     rbx, [rsp+28h+arg_10]
0x18001431a  cmp     qword ptr [rbx+158h], 0
0x180014322  jnz     short loc_18001433C
0x180014324  test    dil, dil
0x180014327  jz      short loc_180014341
0x180014329  mov     rax, rbx
0x18001432c  mov     rbx, [rsp+28h+arg_0]
0x180014331  mov     rsi, [rsp+28h+arg_18]
0x180014336  add     rsp, 20h
0x18001433a  pop     rdi
0x18001433b  retn
0x18001433c  mov     dil, 1
0x18001433f  jmp     short loc_180014324
0x180014341  mov     rcx, rbx; lpMem
0x180014344  call    DestroyAggregateSession
0x180014349  xor     ebx, ebx
0x18001434b  jmp     short loc_180014329
0x18006be6a  push    rbp
0x18006be6c  sub     rsp, 20h
0x18006be70  mov     rbp, rdx
0x18006be73  mov     rax, [rcx]
0x18006be76  xor     ecx, ecx
0x18006be78  cmp     dword ptr [rax], 0C000000Dh
0x18006be7e  setz    cl
0x18006be81  mov     eax, ecx
0x18006be83  add     rsp, 20h
0x18006be87  pop     rbp
0x18006be88  retn
```
