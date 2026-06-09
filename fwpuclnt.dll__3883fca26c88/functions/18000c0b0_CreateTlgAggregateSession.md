# CreateTlgAggregateSession

- ea: `0x18000c0b0`
- end: `0x18000c186`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be70`

## callees

- `0x18000c0b0`
- `0x18000c230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000c104`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000c104`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c12c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c12c`

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
    if ( !a1 || !dword_18007C3C0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18000c0b0  mov     [rsp+arg_0], rbx
0x18000c0b5  mov     [rsp+arg_18], rsi
0x18000c0ba  push    rdi
0x18000c0bb  sub     rsp, 20h
0x18000c0bf  mov     sil, cl
0x18000c0c2  xor     dil, dil
0x18000c0c5  mov     [rsp+28h+arg_8], dil
0x18000c0ca  call    cs:__imp_GetProcessHeap
0x18000c0d1  nop     dword ptr [rax+rax+00h]
0x18000c0d6  mov     rcx, rax; hHeap
0x18000c0d9  mov     edx, 8; dwFlags
0x18000c0de  mov     r8d, 168h; dwBytes
0x18000c0e4  call    cs:__imp_HeapAlloc
0x18000c0eb  nop     dword ptr [rax+rax+00h]
0x18000c0f0  mov     rbx, rax
0x18000c0f3  mov     [rsp+28h+arg_10], rax
0x18000c0f8  test    rax, rax
0x18000c0fb  jz      short loc_18000C163
0x18000c0fd  lea     rcx, [rax+108h]; SRWLock
0x18000c104  call    cs:__imp_InitializeSRWLock
0x18000c10b  nop     dword ptr [rax+rax+00h]
0x18000c110  test    sil, sil
0x18000c113  jz      short loc_18000C160
0x18000c115  mov     ecx, cs:dword_18007C3C0
0x18000c11b  test    ecx, ecx
0x18000c11d  jnz     short loc_18000C163
0x18000c11f  xor     r8d, r8d; pcbe
0x18000c122  mov     rdx, rbx; pv
0x18000c125  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18000c12c  call    cs:__imp_CreateThreadpoolTimer
0x18000c133  nop     dword ptr [rax+rax+00h]
0x18000c138  mov     [rbx+158h], rax
0x18000c13f  jmp     short loc_18000C156
0x18000c141  mov     eax, 1
0x18000c146  xchg    eax, cs:dword_18007C3C0
0x18000c14c  mov     dil, [rsp+28h+arg_8]
0x18000c151  mov     rbx, [rsp+28h+arg_10]
0x18000c156  cmp     qword ptr [rbx+158h], 0
0x18000c15e  jz      short loc_18000C163
0x18000c160  mov     dil, 1
0x18000c163  test    dil, dil
0x18000c166  jnz     short loc_18000C172
0x18000c168  mov     rcx, rbx; lpMem
0x18000c16b  call    DestroyAggregateSession
0x18000c170  xor     ebx, ebx
0x18000c172  mov     rax, rbx
0x18000c175  mov     rbx, [rsp+28h+arg_0]
0x18000c17a  mov     rsi, [rsp+28h+arg_18]
0x18000c17f  add     rsp, 20h
0x18000c183  pop     rdi
0x18000c184  retn
0x18004a14c  push    rbp
0x18004a14e  sub     rsp, 20h
0x18004a152  mov     rbp, rdx
0x18004a155  mov     rax, [rcx]
0x18004a158  xor     ecx, ecx
0x18004a15a  cmp     dword ptr [rax], 0C000000Dh
0x18004a160  setz    cl
0x18004a163  mov     eax, ecx
0x18004a165  add     rsp, 20h
0x18004a169  pop     rbp
0x18004a16a  retn
```
