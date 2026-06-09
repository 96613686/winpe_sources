# CreateTlgAggregateSession

- ea: `0x1800531c0`
- end: `0x18005327d`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180053004`

## callees

- `0x1800531c0`
- `0x180053328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180053208`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180053208`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800531da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800531da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800531ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800531ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005322a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005322a`

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
    if ( !a1 || !dword_1800F1938 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800531c0  mov     [rsp+arg_0], rbx
0x1800531c5  mov     [rsp+arg_18], rsi
0x1800531ca  push    rdi
0x1800531cb  sub     rsp, 20h
0x1800531cf  mov     sil, cl
0x1800531d2  xor     dil, dil
0x1800531d5  mov     [rsp+28h+arg_8], dil
0x1800531da  call    cs:__imp_GetProcessHeap
0x1800531e0  mov     rcx, rax; hHeap
0x1800531e3  mov     edx, 8; dwFlags
0x1800531e8  mov     r8d, 168h; dwBytes
0x1800531ee  call    cs:__imp_HeapAlloc
0x1800531f4  mov     rbx, rax
0x1800531f7  mov     [rsp+28h+arg_10], rax
0x1800531fc  test    rax, rax
0x1800531ff  jz      short loc_18005325B
0x180053201  lea     rcx, [rax+108h]; SRWLock
0x180053208  call    cs:__imp_InitializeSRWLock
0x18005320e  test    sil, sil
0x180053211  jz      short loc_180053258
0x180053213  mov     ecx, cs:dword_1800F1938
0x180053219  test    ecx, ecx
0x18005321b  jnz     short loc_18005325B
0x18005321d  xor     r8d, r8d; pcbe
0x180053220  mov     rdx, rbx; pv
0x180053223  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18005322a  call    cs:__imp_CreateThreadpoolTimer
0x180053230  mov     [rbx+158h], rax
0x180053237  jmp     short loc_18005324E
0x180053239  mov     eax, 1
0x18005323e  xchg    eax, cs:dword_1800F1938
0x180053244  mov     dil, [rsp+28h+arg_8]
0x180053249  mov     rbx, [rsp+28h+arg_10]
0x18005324e  cmp     qword ptr [rbx+158h], 0
0x180053256  jz      short loc_18005325B
0x180053258  mov     dil, 1
0x18005325b  test    dil, dil
0x18005325e  jnz     short loc_18005326A
0x180053260  mov     rcx, rbx; lpMem
0x180053263  call    DestroyAggregateSession
0x180053268  xor     ebx, ebx
0x18005326a  mov     rax, rbx
0x18005326d  mov     rbx, [rsp+28h+arg_0]
0x180053272  mov     rsi, [rsp+28h+arg_18]
0x180053277  add     rsp, 20h
0x18005327b  pop     rdi
0x18005327c  retn
0x1800a909c  push    rbp
0x1800a909e  sub     rsp, 20h
0x1800a90a2  mov     rbp, rdx
0x1800a90a5  mov     rax, [rcx]
0x1800a90a8  xor     ecx, ecx
0x1800a90aa  cmp     dword ptr [rax], 0C000000Dh
0x1800a90b0  setz    cl
0x1800a90b3  mov     eax, ecx
0x1800a90b5  add     rsp, 20h
0x1800a90b9  pop     rbp
0x1800a90ba  retn
```
