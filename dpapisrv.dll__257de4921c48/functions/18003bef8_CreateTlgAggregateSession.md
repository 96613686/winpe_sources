# CreateTlgAggregateSession

- ea: `0x18003bef8`
- end: `0x18003bfce`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003c204`

## callees

- `0x18003bef8`
- `0x18003bfd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18003bf4c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18003bf4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bf12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bf12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bf2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003bf2c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bf74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bf74`

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
    if ( !a1 || !dword_18004C828 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18003bef8  mov     [rsp+arg_0], rbx
0x18003befd  mov     [rsp+arg_18], rsi
0x18003bf02  push    rdi
0x18003bf03  sub     rsp, 20h
0x18003bf07  mov     sil, cl
0x18003bf0a  xor     dil, dil
0x18003bf0d  mov     [rsp+28h+arg_8], dil
0x18003bf12  call    cs:__imp_GetProcessHeap
0x18003bf19  nop     dword ptr [rax+rax+00h]
0x18003bf1e  mov     rcx, rax; hHeap
0x18003bf21  mov     edx, 8; dwFlags
0x18003bf26  mov     r8d, 168h; dwBytes
0x18003bf2c  call    cs:__imp_HeapAlloc
0x18003bf33  nop     dword ptr [rax+rax+00h]
0x18003bf38  mov     rbx, rax
0x18003bf3b  mov     [rsp+28h+arg_10], rax
0x18003bf40  test    rax, rax
0x18003bf43  jz      short loc_18003BFAB
0x18003bf45  lea     rcx, [rax+108h]; SRWLock
0x18003bf4c  call    cs:__imp_InitializeSRWLock
0x18003bf53  nop     dword ptr [rax+rax+00h]
0x18003bf58  test    sil, sil
0x18003bf5b  jz      short loc_18003BFA8
0x18003bf5d  mov     ecx, cs:dword_18004C828
0x18003bf63  test    ecx, ecx
0x18003bf65  jnz     short loc_18003BFAB
0x18003bf67  xor     r8d, r8d; pcbe
0x18003bf6a  mov     rdx, rbx; pv
0x18003bf6d  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18003bf74  call    cs:__imp_CreateThreadpoolTimer
0x18003bf7b  nop     dword ptr [rax+rax+00h]
0x18003bf80  mov     [rbx+158h], rax
0x18003bf87  jmp     short loc_18003BF9E
0x18003bf89  mov     eax, 1
0x18003bf8e  xchg    eax, cs:dword_18004C828
0x18003bf94  mov     dil, [rsp+28h+arg_8]
0x18003bf99  mov     rbx, [rsp+28h+arg_10]
0x18003bf9e  cmp     qword ptr [rbx+158h], 0
0x18003bfa6  jz      short loc_18003BFAB
0x18003bfa8  mov     dil, 1
0x18003bfab  test    dil, dil
0x18003bfae  jnz     short loc_18003BFBA
0x18003bfb0  mov     rcx, rbx; lpMem
0x18003bfb3  call    DestroyAggregateSession
0x18003bfb8  xor     ebx, ebx
0x18003bfba  mov     rax, rbx
0x18003bfbd  mov     rbx, [rsp+28h+arg_0]
0x18003bfc2  mov     rsi, [rsp+28h+arg_18]
0x18003bfc7  add     rsp, 20h
0x18003bfcb  pop     rdi
0x18003bfcc  retn
0x18003d298  push    rbp
0x18003d29a  sub     rsp, 20h
0x18003d29e  mov     rbp, rdx
0x18003d2a1  mov     rax, [rcx]
0x18003d2a4  xor     ecx, ecx
0x18003d2a6  cmp     dword ptr [rax], 0C000000Dh
0x18003d2ac  setz    cl
0x18003d2af  mov     eax, ecx
0x18003d2b1  add     rsp, 20h
0x18003d2b5  pop     rbp
0x18003d2b6  retn
```
