# CreateTlgAggregateSession

- ea: `0x180111104`
- end: `0x1801111c1`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180111950`

## callees

- `0x180111104`
- `0x1801111c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18011114c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18011114c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011111e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011111e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180111132`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180111132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011116e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011116e`

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
    if ( !a1 || !dword_180174DB8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180111104  mov     [rsp+arg_0], rbx
0x180111109  mov     [rsp+arg_18], rsi
0x18011110e  push    rdi
0x18011110f  sub     rsp, 20h
0x180111113  mov     sil, cl
0x180111116  xor     dil, dil
0x180111119  mov     [rsp+28h+arg_8], dil
0x18011111e  call    cs:__imp_GetProcessHeap
0x180111124  mov     rcx, rax; hHeap
0x180111127  mov     edx, 8; dwFlags
0x18011112c  mov     r8d, 168h; dwBytes
0x180111132  call    cs:__imp_HeapAlloc
0x180111138  mov     rbx, rax
0x18011113b  mov     [rsp+28h+arg_10], rax
0x180111140  test    rax, rax
0x180111143  jz      short loc_18011119F
0x180111145  lea     rcx, [rax+108h]; SRWLock
0x18011114c  call    cs:__imp_InitializeSRWLock
0x180111152  test    sil, sil
0x180111155  jz      short loc_18011119C
0x180111157  mov     ecx, cs:dword_180174DB8
0x18011115d  test    ecx, ecx
0x18011115f  jnz     short loc_18011119F
0x180111161  xor     r8d, r8d; pcbe
0x180111164  mov     rdx, rbx; pv
0x180111167  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18011116e  call    cs:__imp_CreateThreadpoolTimer
0x180111174  mov     [rbx+158h], rax
0x18011117b  jmp     short loc_180111192
0x18011117d  mov     eax, 1
0x180111182  xchg    eax, cs:dword_180174DB8
0x180111188  mov     dil, [rsp+28h+arg_8]
0x18011118d  mov     rbx, [rsp+28h+arg_10]
0x180111192  cmp     qword ptr [rbx+158h], 0
0x18011119a  jz      short loc_18011119F
0x18011119c  mov     dil, 1
0x18011119f  test    dil, dil
0x1801111a2  jnz     short loc_1801111AE
0x1801111a4  mov     rcx, rbx; lpMem
0x1801111a7  call    DestroyAggregateSession
0x1801111ac  xor     ebx, ebx
0x1801111ae  mov     rax, rbx
0x1801111b1  mov     rbx, [rsp+28h+arg_0]
0x1801111b6  mov     rsi, [rsp+28h+arg_18]
0x1801111bb  add     rsp, 20h
0x1801111bf  pop     rdi
0x1801111c0  retn
0x18011811c  push    rbp
0x18011811e  sub     rsp, 20h
0x180118122  mov     rbp, rdx
0x180118125  mov     rax, [rcx]
0x180118128  xor     ecx, ecx
0x18011812a  cmp     dword ptr [rax], 0C000000Dh
0x180118130  setz    cl
0x180118133  mov     eax, ecx
0x180118135  add     rsp, 20h
0x180118139  pop     rbp
0x18011813a  retn
```
