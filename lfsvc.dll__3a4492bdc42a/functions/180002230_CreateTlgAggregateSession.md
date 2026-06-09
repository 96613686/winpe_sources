# CreateTlgAggregateSession

- ea: `0x180002230`
- end: `0x1800022ce`
- name: `CreateTlgAggregateSession`
- size: `158`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e20`

## callees

- `0x180002230`
- `0x180002f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000226b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000226b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000223d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000223d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002251`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002251`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000228d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000228d`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v3; // rax
  RTL_SRWLOCK *v4; // rbx

  ProcessHeap = GetProcessHeap();
  v3 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v4 = v3;
  if ( !v3
    || (InitializeSRWLock(v3 + 33), a1)
    && (dword_180012668 || (v4[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v4, 0)) == 0) )
  {
    DestroyAggregateSession(v4);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180002230  mov     [rsp+arg_0], rbx
0x180002235  push    rdi
0x180002236  sub     rsp, 20h
0x18000223a  movzx   edi, cl
0x18000223d  call    cs:__imp_GetProcessHeap
0x180002243  mov     rcx, rax; hHeap
0x180002246  mov     edx, 8; dwFlags
0x18000224b  mov     r8d, 168h; dwBytes
0x180002251  call    cs:__imp_HeapAlloc
0x180002257  mov     rbx, rax
0x18000225a  mov     [rsp+28h+arg_8], rax
0x18000225f  test    rax, rax
0x180002262  jz      short loc_1800022B6
0x180002264  lea     rcx, [rax+108h]; SRWLock
0x18000226b  call    cs:__imp_InitializeSRWLock
0x180002271  test    dil, dil
0x180002274  jz      short loc_1800022C0
0x180002276  mov     ecx, cs:dword_180012668
0x18000227c  test    ecx, ecx
0x18000227e  jnz     short loc_1800022B6
0x180002280  xor     r8d, r8d; pcbe
0x180002283  mov     rdx, rbx; pv
0x180002286  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18000228d  call    cs:__imp_CreateThreadpoolTimer
0x180002293  mov     [rbx+158h], rax
0x18000229a  jmp     short loc_1800022AC
0x18000229c  mov     eax, 1
0x1800022a1  xchg    eax, cs:dword_180012668
0x1800022a7  mov     rbx, [rsp+28h+arg_8]
0x1800022ac  cmp     qword ptr [rbx+158h], 0
0x1800022b4  jnz     short loc_1800022C0
0x1800022b6  mov     rcx, rbx; lpMem
0x1800022b9  call    DestroyAggregateSession
0x1800022be  xor     ebx, ebx
0x1800022c0  mov     rax, rbx
0x1800022c3  mov     rbx, [rsp+28h+arg_0]
0x1800022c8  add     rsp, 20h
0x1800022cc  pop     rdi
0x1800022cd  retn
0x18000b450  push    rbp
0x18000b452  sub     rsp, 20h
0x18000b456  mov     rbp, rdx
0x18000b459  mov     rax, [rcx]
0x18000b45c  xor     ecx, ecx
0x18000b45e  cmp     dword ptr [rax], 0C000000Dh
0x18000b464  setz    cl
0x18000b467  mov     eax, ecx
0x18000b469  add     rsp, 20h
0x18000b46d  pop     rbp
0x18000b46e  retn
```
