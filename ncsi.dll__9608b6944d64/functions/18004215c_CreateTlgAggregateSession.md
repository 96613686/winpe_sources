# CreateTlgAggregateSession

- ea: `0x18004215c`
- end: `0x180042219`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e504`

## callees

- `0x18004215c`
- `0x180043614`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004218a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004218a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042176`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042176`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800421c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800421c6`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800421a4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800421a4`

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
    if ( !a1 || !dword_18009B298 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18004215c  mov     [rsp+arg_0], rbx
0x180042161  mov     [rsp+arg_18], rsi
0x180042166  push    rdi
0x180042167  sub     rsp, 20h
0x18004216b  mov     sil, cl
0x18004216e  xor     dil, dil
0x180042171  mov     [rsp+28h+arg_8], dil
0x180042176  call    cs:__imp_GetProcessHeap
0x18004217c  mov     rcx, rax; hHeap
0x18004217f  mov     edx, 8; dwFlags
0x180042184  mov     r8d, 168h; dwBytes
0x18004218a  call    cs:__imp_HeapAlloc
0x180042190  mov     rbx, rax
0x180042193  mov     [rsp+28h+arg_10], rax
0x180042198  test    rax, rax
0x18004219b  jz      short loc_1800421F7
0x18004219d  lea     rcx, [rax+108h]; SRWLock
0x1800421a4  call    cs:__imp_InitializeSRWLock
0x1800421aa  test    sil, sil
0x1800421ad  jz      short loc_1800421F4
0x1800421af  mov     ecx, cs:dword_18009B298
0x1800421b5  test    ecx, ecx
0x1800421b7  jnz     short loc_1800421F7
0x1800421b9  xor     r8d, r8d; pcbe
0x1800421bc  mov     rdx, rbx; pv
0x1800421bf  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800421c6  call    cs:__imp_CreateThreadpoolTimer
0x1800421cc  mov     [rbx+158h], rax
0x1800421d3  jmp     short loc_1800421EA
0x1800421d5  mov     eax, 1
0x1800421da  xchg    eax, cs:dword_18009B298
0x1800421e0  mov     dil, [rsp+28h+arg_8]
0x1800421e5  mov     rbx, [rsp+28h+arg_10]
0x1800421ea  cmp     qword ptr [rbx+158h], 0
0x1800421f2  jz      short loc_1800421F7
0x1800421f4  mov     dil, 1
0x1800421f7  test    dil, dil
0x1800421fa  jnz     short loc_180042206
0x1800421fc  mov     rcx, rbx; lpMem
0x1800421ff  call    DestroyAggregateSession
0x180042204  xor     ebx, ebx
0x180042206  mov     rax, rbx
0x180042209  mov     rbx, [rsp+28h+arg_0]
0x18004220e  mov     rsi, [rsp+28h+arg_18]
0x180042213  add     rsp, 20h
0x180042217  pop     rdi
0x180042218  retn
0x180078f8b  push    rbp
0x180078f8d  sub     rsp, 20h
0x180078f91  mov     rbp, rdx
0x180078f94  mov     rax, [rcx]
0x180078f97  xor     ecx, ecx
0x180078f99  cmp     dword ptr [rax], 0C000000Dh
0x180078f9f  setz    cl
0x180078fa2  mov     eax, ecx
0x180078fa4  add     rsp, 20h
0x180078fa8  pop     rbp
0x180078fa9  retn
```
