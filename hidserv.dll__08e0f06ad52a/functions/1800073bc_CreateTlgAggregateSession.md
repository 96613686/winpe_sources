# CreateTlgAggregateSession

- ea: `0x1800073bc`
- end: `0x180007492`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ed8`

## callees

- `0x180007130`
- `0x1800073bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180007404`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180007404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007469`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007477`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007477`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007426`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007426`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx
  HANDLE v6; // rax

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_18000D730 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    if ( v5 )
    {
      CancelTimerCallbacksAndDeleteTimer((__int64)v5);
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
    }
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800073bc  mov     [rsp+arg_0], rbx
0x1800073c1  mov     [rsp+arg_18], rsi
0x1800073c6  push    rdi
0x1800073c7  sub     rsp, 20h
0x1800073cb  mov     sil, cl
0x1800073ce  xor     dil, dil
0x1800073d1  mov     [rsp+28h+arg_8], dil
0x1800073d6  call    cs:__imp_GetProcessHeap
0x1800073dc  mov     rcx, rax; hHeap
0x1800073df  mov     edx, 8; dwFlags
0x1800073e4  mov     r8d, 168h; dwBytes
0x1800073ea  call    cs:__imp_HeapAlloc
0x1800073f0  mov     rbx, rax
0x1800073f3  mov     [rsp+28h+arg_10], rax
0x1800073f8  test    rax, rax
0x1800073fb  jz      short loc_180007457
0x1800073fd  lea     rcx, [rax+108h]; SRWLock
0x180007404  call    cs:__imp_InitializeSRWLock
0x18000740a  test    sil, sil
0x18000740d  jz      short loc_180007454
0x18000740f  mov     ecx, cs:dword_18000D730
0x180007415  test    ecx, ecx
0x180007417  jnz     short loc_180007457
0x180007419  xor     r8d, r8d; pcbe
0x18000741c  mov     rdx, rbx; pv
0x18000741f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180007426  call    cs:__imp_CreateThreadpoolTimer
0x18000742c  mov     [rbx+158h], rax
0x180007433  jmp     short loc_18000744A
0x180007435  mov     eax, 1
0x18000743a  xchg    eax, cs:dword_18000D730
0x180007440  mov     dil, [rsp+28h+arg_8]
0x180007445  mov     rbx, [rsp+28h+arg_10]
0x18000744a  cmp     qword ptr [rbx+158h], 0
0x180007452  jz      short loc_180007457
0x180007454  mov     dil, 1
0x180007457  test    dil, dil
0x18000745a  jnz     short loc_18000747F
0x18000745c  test    rbx, rbx
0x18000745f  jz      short loc_18000747D
0x180007461  mov     rcx, rbx
0x180007464  call    CancelTimerCallbacksAndDeleteTimer
0x180007469  call    cs:__imp_GetProcessHeap
0x18000746f  mov     rcx, rax; hHeap
0x180007472  mov     r8, rbx; lpMem
0x180007475  xor     edx, edx; dwFlags
0x180007477  call    cs:__imp_HeapFree
0x18000747d  xor     ebx, ebx
0x18000747f  mov     rax, rbx
0x180007482  mov     rbx, [rsp+28h+arg_0]
0x180007487  mov     rsi, [rsp+28h+arg_18]
0x18000748c  add     rsp, 20h
0x180007490  pop     rdi
0x180007491  retn
0x1800087b6  push    rbp
0x1800087b8  sub     rsp, 20h
0x1800087bc  mov     rbp, rdx
0x1800087bf  mov     rax, [rcx]
0x1800087c2  xor     ecx, ecx
0x1800087c4  cmp     dword ptr [rax], 0C000000Dh
0x1800087ca  setz    cl
0x1800087cd  mov     eax, ecx
0x1800087cf  add     rsp, 20h
0x1800087d3  pop     rbp
0x1800087d4  retn
```
