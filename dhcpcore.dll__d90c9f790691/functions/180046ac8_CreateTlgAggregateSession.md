# CreateTlgAggregateSession

- ea: `0x180046ac8`
- end: `0x180046b85`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180047680`

## callees

- `0x180046ac8`
- `0x180046b8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046af6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046af6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046ae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046ae2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180046b10`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180046b10`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180046b32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180046b32`

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
    if ( !a1 || !dword_180061938 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180046ac8  mov     [rsp+arg_0], rbx
0x180046acd  mov     [rsp+arg_18], rsi
0x180046ad2  push    rdi
0x180046ad3  sub     rsp, 20h
0x180046ad7  mov     sil, cl
0x180046ada  xor     dil, dil
0x180046add  mov     [rsp+28h+arg_8], dil
0x180046ae2  call    cs:__imp_GetProcessHeap
0x180046ae8  mov     rcx, rax; hHeap
0x180046aeb  mov     edx, 8; dwFlags
0x180046af0  mov     r8d, 168h; dwBytes
0x180046af6  call    cs:__imp_HeapAlloc
0x180046afc  mov     rbx, rax
0x180046aff  mov     [rsp+28h+arg_10], rax
0x180046b04  test    rax, rax
0x180046b07  jz      short loc_180046B63
0x180046b09  lea     rcx, [rax+108h]; SRWLock
0x180046b10  call    cs:__imp_InitializeSRWLock
0x180046b16  test    sil, sil
0x180046b19  jz      short loc_180046B60
0x180046b1b  mov     ecx, cs:dword_180061938
0x180046b21  test    ecx, ecx
0x180046b23  jnz     short loc_180046B63
0x180046b25  xor     r8d, r8d; pcbe
0x180046b28  mov     rdx, rbx; pv
0x180046b2b  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180046b32  call    cs:__imp_CreateThreadpoolTimer
0x180046b38  mov     [rbx+158h], rax
0x180046b3f  jmp     short loc_180046B56
0x180046b41  mov     eax, 1
0x180046b46  xchg    eax, cs:dword_180061938
0x180046b4c  mov     dil, [rsp+28h+arg_8]
0x180046b51  mov     rbx, [rsp+28h+arg_10]
0x180046b56  cmp     qword ptr [rbx+158h], 0
0x180046b5e  jz      short loc_180046B63
0x180046b60  mov     dil, 1
0x180046b63  test    dil, dil
0x180046b66  jnz     short loc_180046B72
0x180046b68  mov     rcx, rbx; lpMem
0x180046b6b  call    DestroyAggregateSession
0x180046b70  xor     ebx, ebx
0x180046b72  mov     rax, rbx
0x180046b75  mov     rbx, [rsp+28h+arg_0]
0x180046b7a  mov     rsi, [rsp+28h+arg_18]
0x180046b7f  add     rsp, 20h
0x180046b83  pop     rdi
0x180046b84  retn
0x180048015  push    rbp
0x180048017  sub     rsp, 20h
0x18004801b  mov     rbp, rdx
0x18004801e  mov     rax, [rcx]
0x180048021  xor     ecx, ecx
0x180048023  cmp     dword ptr [rax], 0C000000Dh
0x180048029  setz    cl
0x18004802c  mov     eax, ecx
0x18004802e  add     rsp, 20h
0x180048032  pop     rbp
0x180048033  retn
```
