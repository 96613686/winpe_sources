# CreateTlgAggregateSession

- ea: `0x180078dec`
- end: `0x180078ea9`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800791bc`

## callees

- `0x180078dec`
- `0x180078eb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078e06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078e06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078e1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078e1a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180078e34`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180078e34`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180078e56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180078e56`

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
    if ( !a1 || !dword_1800ABDA8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180078dec  mov     [rsp+arg_0], rbx
0x180078df1  mov     [rsp+arg_18], rsi
0x180078df6  push    rdi
0x180078df7  sub     rsp, 20h
0x180078dfb  mov     sil, cl
0x180078dfe  xor     dil, dil
0x180078e01  mov     [rsp+28h+arg_8], dil
0x180078e06  call    cs:__imp_GetProcessHeap
0x180078e0c  mov     rcx, rax; hHeap
0x180078e0f  mov     edx, 8; dwFlags
0x180078e14  mov     r8d, 168h; dwBytes
0x180078e1a  call    cs:__imp_HeapAlloc
0x180078e20  mov     rbx, rax
0x180078e23  mov     [rsp+28h+arg_10], rax
0x180078e28  test    rax, rax
0x180078e2b  jz      short loc_180078E87
0x180078e2d  lea     rcx, [rax+108h]; SRWLock
0x180078e34  call    cs:__imp_InitializeSRWLock
0x180078e3a  test    sil, sil
0x180078e3d  jz      short loc_180078E84
0x180078e3f  mov     ecx, cs:dword_1800ABDA8
0x180078e45  test    ecx, ecx
0x180078e47  jnz     short loc_180078E87
0x180078e49  xor     r8d, r8d; pcbe
0x180078e4c  mov     rdx, rbx; pv
0x180078e4f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180078e56  call    cs:__imp_CreateThreadpoolTimer
0x180078e5c  mov     [rbx+158h], rax
0x180078e63  jmp     short loc_180078E7A
0x180078e65  mov     eax, 1
0x180078e6a  xchg    eax, cs:dword_1800ABDA8
0x180078e70  mov     dil, [rsp+28h+arg_8]
0x180078e75  mov     rbx, [rsp+28h+arg_10]
0x180078e7a  cmp     qword ptr [rbx+158h], 0
0x180078e82  jz      short loc_180078E87
0x180078e84  mov     dil, 1
0x180078e87  test    dil, dil
0x180078e8a  jnz     short loc_180078E96
0x180078e8c  mov     rcx, rbx; lpMem
0x180078e8f  call    DestroyAggregateSession
0x180078e94  xor     ebx, ebx
0x180078e96  mov     rax, rbx
0x180078e99  mov     rbx, [rsp+28h+arg_0]
0x180078e9e  mov     rsi, [rsp+28h+arg_18]
0x180078ea3  add     rsp, 20h
0x180078ea7  pop     rdi
0x180078ea8  retn
0x18007961e  push    rbp
0x180079620  sub     rsp, 20h
0x180079624  mov     rbp, rdx
0x180079627  mov     rax, [rcx]
0x18007962a  xor     ecx, ecx
0x18007962c  cmp     dword ptr [rax], 0C000000Dh
0x180079632  setz    cl
0x180079635  mov     eax, ecx
0x180079637  add     rsp, 20h
0x18007963b  pop     rbp
0x18007963c  retn
```
