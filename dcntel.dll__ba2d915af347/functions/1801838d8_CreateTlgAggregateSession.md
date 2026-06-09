# CreateTlgAggregateSession

- ea: `0x1801838d8`
- end: `0x1801839ae`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801843f8`

## callees

- `0x18018363c`
- `0x1801838d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180183920`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180183920`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180183906`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180183906`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801838f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180183985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801838f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180183985`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180183993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180183993`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180183942`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180183942`

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
    if ( !a1 || !dword_1801FFDC8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1801838d8  mov     [rsp+arg_0], rbx
0x1801838dd  mov     [rsp+arg_18], rsi
0x1801838e2  push    rdi
0x1801838e3  sub     rsp, 20h
0x1801838e7  mov     sil, cl
0x1801838ea  xor     dil, dil
0x1801838ed  mov     [rsp+28h+arg_8], dil
0x1801838f2  call    cs:__imp_GetProcessHeap
0x1801838f8  mov     rcx, rax; hHeap
0x1801838fb  mov     edx, 8; dwFlags
0x180183900  mov     r8d, 168h; dwBytes
0x180183906  call    cs:__imp_HeapAlloc
0x18018390c  mov     rbx, rax
0x18018390f  mov     [rsp+28h+arg_10], rax
0x180183914  test    rax, rax
0x180183917  jz      short loc_180183973
0x180183919  lea     rcx, [rax+108h]; SRWLock
0x180183920  call    cs:__imp_InitializeSRWLock
0x180183926  test    sil, sil
0x180183929  jz      short loc_180183970
0x18018392b  mov     ecx, cs:dword_1801FFDC8
0x180183931  test    ecx, ecx
0x180183933  jnz     short loc_180183973
0x180183935  xor     r8d, r8d; pcbe
0x180183938  mov     rdx, rbx; pv
0x18018393b  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180183942  call    cs:__imp_CreateThreadpoolTimer
0x180183948  mov     [rbx+158h], rax
0x18018394f  jmp     short loc_180183966
0x180183951  mov     eax, 1
0x180183956  xchg    eax, cs:dword_1801FFDC8
0x18018395c  mov     dil, [rsp+28h+arg_8]
0x180183961  mov     rbx, [rsp+28h+arg_10]
0x180183966  cmp     qword ptr [rbx+158h], 0
0x18018396e  jz      short loc_180183973
0x180183970  mov     dil, 1
0x180183973  test    dil, dil
0x180183976  jnz     short loc_18018399B
0x180183978  test    rbx, rbx
0x18018397b  jz      short loc_180183999
0x18018397d  mov     rcx, rbx
0x180183980  call    CancelTimerCallbacksAndDeleteTimer
0x180183985  call    cs:__imp_GetProcessHeap
0x18018398b  mov     rcx, rax; hHeap
0x18018398e  mov     r8, rbx; lpMem
0x180183991  xor     edx, edx; dwFlags
0x180183993  call    cs:__imp_HeapFree
0x180183999  xor     ebx, ebx
0x18018399b  mov     rax, rbx
0x18018399e  mov     rbx, [rsp+28h+arg_0]
0x1801839a3  mov     rsi, [rsp+28h+arg_18]
0x1801839a8  add     rsp, 20h
0x1801839ac  pop     rdi
0x1801839ad  retn
0x18018ca43  push    rbp
0x18018ca45  sub     rsp, 20h
0x18018ca49  mov     rbp, rdx
0x18018ca4c  mov     rax, [rcx]
0x18018ca4f  xor     ecx, ecx
0x18018ca51  cmp     dword ptr [rax], 0C000000Dh
0x18018ca57  setz    cl
0x18018ca5a  mov     eax, ecx
0x18018ca5c  add     rsp, 20h
0x18018ca60  pop     rbp
0x18018ca61  retn
```
