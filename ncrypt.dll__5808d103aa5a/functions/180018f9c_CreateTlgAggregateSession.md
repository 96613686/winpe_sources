# CreateTlgAggregateSession

- ea: `0x180018f9c`
- end: `0x180019059`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018e90`

## callees

- `0x180018d80`
- `0x180018f9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180018fe4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180018fe4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018fca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018fca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018fb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018fb6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019006`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019006`

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
    if ( !a1 || !dword_18002AFD8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180018f9c  mov     [rsp+arg_0], rbx
0x180018fa1  mov     [rsp+arg_18], rsi
0x180018fa6  push    rdi
0x180018fa7  sub     rsp, 20h
0x180018fab  mov     sil, cl
0x180018fae  xor     dil, dil
0x180018fb1  mov     [rsp+28h+arg_8], dil
0x180018fb6  call    cs:__imp_GetProcessHeap
0x180018fbc  mov     rcx, rax; hHeap
0x180018fbf  mov     edx, 8; dwFlags
0x180018fc4  mov     r8d, 168h; dwBytes
0x180018fca  call    cs:__imp_HeapAlloc
0x180018fd0  mov     rbx, rax
0x180018fd3  mov     [rsp+28h+arg_10], rax
0x180018fd8  test    rax, rax
0x180018fdb  jz      short loc_180019037
0x180018fdd  lea     rcx, [rax+108h]; SRWLock
0x180018fe4  call    cs:__imp_InitializeSRWLock
0x180018fea  test    sil, sil
0x180018fed  jz      short loc_180019034
0x180018fef  mov     ecx, cs:dword_18002AFD8
0x180018ff5  test    ecx, ecx
0x180018ff7  jnz     short loc_180019037
0x180018ff9  xor     r8d, r8d; pcbe
0x180018ffc  mov     rdx, rbx; pv
0x180018fff  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180019006  call    cs:__imp_CreateThreadpoolTimer
0x18001900c  mov     [rbx+158h], rax
0x180019013  jmp     short loc_18001902A
0x180019015  mov     eax, 1
0x18001901a  xchg    eax, cs:dword_18002AFD8
0x180019020  mov     dil, [rsp+28h+arg_8]
0x180019025  mov     rbx, [rsp+28h+arg_10]
0x18001902a  cmp     qword ptr [rbx+158h], 0
0x180019032  jz      short loc_180019037
0x180019034  mov     dil, 1
0x180019037  test    dil, dil
0x18001903a  jnz     short loc_180019046
0x18001903c  mov     rcx, rbx; lpMem
0x18001903f  call    DestroyAggregateSession
0x180019044  xor     ebx, ebx
0x180019046  mov     rax, rbx
0x180019049  mov     rbx, [rsp+28h+arg_0]
0x18001904e  mov     rsi, [rsp+28h+arg_18]
0x180019053  add     rsp, 20h
0x180019057  pop     rdi
0x180019058  retn
0x18001f282  push    rbp
0x18001f284  sub     rsp, 20h
0x18001f288  mov     rbp, rdx
0x18001f28b  mov     rax, [rcx]
0x18001f28e  xor     ecx, ecx
0x18001f290  cmp     dword ptr [rax], 0C000000Dh
0x18001f296  setz    cl
0x18001f299  mov     eax, ecx
0x18001f29b  add     rsp, 20h
0x18001f29f  pop     rbp
0x18001f2a0  retn
```
