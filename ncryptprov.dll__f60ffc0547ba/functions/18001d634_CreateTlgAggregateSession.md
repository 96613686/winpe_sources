# CreateTlgAggregateSession

- ea: `0x18001d634`
- end: `0x18001d70c`
- name: `CreateTlgAggregateSession`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d44c`

## callees

- `0x18001d634`
- `0x18001d7b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d668`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d668`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d64e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d64e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001d688`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001d688`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d6b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d6b0`

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
    if ( !a1 || !dword_18007A220 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18001d634  mov     [rsp+arg_0], rbx
0x18001d639  mov     [rsp+arg_18], rsi
0x18001d63e  push    rdi
0x18001d63f  sub     rsp, 20h
0x18001d643  mov     sil, cl
0x18001d646  xor     dil, dil
0x18001d649  mov     [rsp+28h+arg_8], dil
0x18001d64e  call    cs:__imp_GetProcessHeap
0x18001d655  nop     dword ptr [rax+rax+00h]
0x18001d65a  mov     rcx, rax; hHeap
0x18001d65d  mov     edx, 8; dwFlags
0x18001d662  mov     r8d, 168h; dwBytes
0x18001d668  call    cs:__imp_HeapAlloc
0x18001d66f  nop     dword ptr [rax+rax+00h]
0x18001d674  mov     rbx, rax
0x18001d677  mov     [rsp+28h+arg_10], rax
0x18001d67c  test    rax, rax
0x18001d67f  jz      short loc_18001D6E7
0x18001d681  lea     rcx, [rax+108h]; SRWLock
0x18001d688  call    cs:__imp_InitializeSRWLock
0x18001d68f  nop     dword ptr [rax+rax+00h]
0x18001d694  test    sil, sil
0x18001d697  jz      short loc_18001D6E4
0x18001d699  mov     ecx, cs:dword_18007A220
0x18001d69f  test    ecx, ecx
0x18001d6a1  jnz     short loc_18001D6E7
0x18001d6a3  xor     r8d, r8d; pcbe
0x18001d6a6  mov     rdx, rbx; pv
0x18001d6a9  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18001d6b0  call    cs:__imp_CreateThreadpoolTimer
0x18001d6b7  nop     dword ptr [rax+rax+00h]
0x18001d6bc  mov     [rbx+158h], rax
0x18001d6c3  jmp     short loc_18001D6DA
0x18001d6c5  mov     eax, 1
0x18001d6ca  xchg    eax, cs:dword_18007A220
0x18001d6d0  mov     dil, [rsp+28h+arg_8]
0x18001d6d5  mov     rbx, [rsp+28h+arg_10]
0x18001d6da  cmp     qword ptr [rbx+158h], 0
0x18001d6e2  jz      short loc_18001D6E7
0x18001d6e4  mov     dil, 1
0x18001d6e7  test    dil, dil
0x18001d6ea  jz      short loc_18001D700
0x18001d6ec  mov     rax, rbx
0x18001d6ef  mov     rbx, [rsp+28h+arg_0]
0x18001d6f4  mov     rsi, [rsp+28h+arg_18]
0x18001d6f9  add     rsp, 20h
0x18001d6fd  pop     rdi
0x18001d6fe  retn
0x18001d700  mov     rcx, rbx; lpMem
0x18001d703  call    DestroyAggregateSession
0x18001d708  xor     ebx, ebx
0x18001d70a  jmp     short loc_18001D6EC
0x18006275c  push    rbp
0x18006275e  sub     rsp, 20h
0x180062762  mov     rbp, rdx
0x180062765  mov     rax, [rcx]
0x180062768  xor     ecx, ecx
0x18006276a  cmp     dword ptr [rax], 0C000000Dh
0x180062770  setz    cl
0x180062773  mov     eax, ecx
0x180062775  add     rsp, 20h
0x180062779  pop     rbp
0x18006277a  retn
```
