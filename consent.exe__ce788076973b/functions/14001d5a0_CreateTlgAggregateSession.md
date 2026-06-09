# CreateTlgAggregateSession

- ea: `0x14001d5a0`
- end: `0x14001d65d`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000af70`
- `0x14000b820`
- `0x14000c350`

## callees

- `0x14001d5a0`
- `0x14001d664`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14001d5e8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14001d5e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001d5ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001d5ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001d5ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001d5ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001d60a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001d60a`

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
    if ( !a1 || !dword_140029BF8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x14001d5a0  mov     [rsp+arg_0], rbx
0x14001d5a5  mov     [rsp+arg_18], rsi
0x14001d5aa  push    rdi
0x14001d5ab  sub     rsp, 20h
0x14001d5af  mov     sil, cl
0x14001d5b2  xor     dil, dil
0x14001d5b5  mov     [rsp+28h+arg_8], dil
0x14001d5ba  call    cs:__imp_GetProcessHeap
0x14001d5c0  mov     rcx, rax; hHeap
0x14001d5c3  mov     edx, 8; dwFlags
0x14001d5c8  mov     r8d, 168h; dwBytes
0x14001d5ce  call    cs:__imp_HeapAlloc
0x14001d5d4  mov     rbx, rax
0x14001d5d7  mov     [rsp+28h+arg_10], rax
0x14001d5dc  test    rax, rax
0x14001d5df  jz      short loc_14001D63B
0x14001d5e1  lea     rcx, [rax+108h]; SRWLock
0x14001d5e8  call    cs:__imp_InitializeSRWLock
0x14001d5ee  test    sil, sil
0x14001d5f1  jz      short loc_14001D638
0x14001d5f3  mov     ecx, cs:dword_140029BF8
0x14001d5f9  test    ecx, ecx
0x14001d5fb  jnz     short loc_14001D63B
0x14001d5fd  xor     r8d, r8d; pcbe
0x14001d600  mov     rdx, rbx; pv
0x14001d603  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x14001d60a  call    cs:__imp_CreateThreadpoolTimer
0x14001d610  mov     [rbx+158h], rax
0x14001d617  jmp     short loc_14001D62E
0x14001d619  mov     eax, 1
0x14001d61e  xchg    eax, cs:dword_140029BF8
0x14001d624  mov     dil, [rsp+28h+arg_8]
0x14001d629  mov     rbx, [rsp+28h+arg_10]
0x14001d62e  cmp     qword ptr [rbx+158h], 0
0x14001d636  jz      short loc_14001D63B
0x14001d638  mov     dil, 1
0x14001d63b  test    dil, dil
0x14001d63e  jnz     short loc_14001D64A
0x14001d640  mov     rcx, rbx; lpMem
0x14001d643  call    DestroyAggregateSession
0x14001d648  xor     ebx, ebx
0x14001d64a  mov     rax, rbx
0x14001d64d  mov     rbx, [rsp+28h+arg_0]
0x14001d652  mov     rsi, [rsp+28h+arg_18]
0x14001d657  add     rsp, 20h
0x14001d65b  pop     rdi
0x14001d65c  retn
0x14001e8a1  push    rbp
0x14001e8a3  sub     rsp, 20h
0x14001e8a7  mov     rbp, rdx
0x14001e8aa  mov     rax, [rcx]
0x14001e8ad  xor     ecx, ecx
0x14001e8af  cmp     dword ptr [rax], 0C000000Dh
0x14001e8b5  setz    cl
0x14001e8b8  mov     eax, ecx
0x14001e8ba  add     rsp, 20h
0x14001e8be  pop     rbp
0x14001e8bf  retn
```
