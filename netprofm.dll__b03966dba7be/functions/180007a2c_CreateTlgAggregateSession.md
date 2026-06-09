# CreateTlgAggregateSession

- ea: `0x180007a2c`
- end: `0x180007ae9`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007810`

## callees

- `0x180007a2c`
- `0x180007b94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180007a74`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180007a74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007a5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007a5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007a96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007a96`

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
    if ( !a1 || !dword_180060180 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180007a2c  mov     [rsp+arg_0], rbx
0x180007a31  mov     [rsp+arg_18], rsi
0x180007a36  push    rdi
0x180007a37  sub     rsp, 20h
0x180007a3b  mov     sil, cl
0x180007a3e  xor     dil, dil
0x180007a41  mov     [rsp+28h+arg_8], dil
0x180007a46  call    cs:__imp_GetProcessHeap
0x180007a4c  mov     rcx, rax; hHeap
0x180007a4f  mov     edx, 8; dwFlags
0x180007a54  mov     r8d, 168h; dwBytes
0x180007a5a  call    cs:__imp_HeapAlloc
0x180007a60  mov     rbx, rax
0x180007a63  mov     [rsp+28h+arg_10], rax
0x180007a68  test    rax, rax
0x180007a6b  jz      short loc_180007AC7
0x180007a6d  lea     rcx, [rax+108h]; SRWLock
0x180007a74  call    cs:__imp_InitializeSRWLock
0x180007a7a  test    sil, sil
0x180007a7d  jz      short loc_180007AC4
0x180007a7f  mov     ecx, cs:dword_180060180
0x180007a85  test    ecx, ecx
0x180007a87  jnz     short loc_180007AC7
0x180007a89  xor     r8d, r8d; pcbe
0x180007a8c  mov     rdx, rbx; pv
0x180007a8f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180007a96  call    cs:__imp_CreateThreadpoolTimer
0x180007a9c  mov     [rbx+158h], rax
0x180007aa3  jmp     short loc_180007ABA
0x180007aa5  mov     eax, 1
0x180007aaa  xchg    eax, cs:dword_180060180
0x180007ab0  mov     dil, [rsp+28h+arg_8]
0x180007ab5  mov     rbx, [rsp+28h+arg_10]
0x180007aba  cmp     qword ptr [rbx+158h], 0
0x180007ac2  jz      short loc_180007AC7
0x180007ac4  mov     dil, 1
0x180007ac7  test    dil, dil
0x180007aca  jnz     short loc_180007AD6
0x180007acc  mov     rcx, rbx; lpMem
0x180007acf  call    DestroyAggregateSession
0x180007ad4  xor     ebx, ebx
0x180007ad6  mov     rax, rbx
0x180007ad9  mov     rbx, [rsp+28h+arg_0]
0x180007ade  mov     rsi, [rsp+28h+arg_18]
0x180007ae3  add     rsp, 20h
0x180007ae7  pop     rdi
0x180007ae8  retn
0x18003f8e6  push    rbp
0x18003f8e8  sub     rsp, 20h
0x18003f8ec  mov     rbp, rdx
0x18003f8ef  mov     rax, [rcx]
0x18003f8f2  xor     ecx, ecx
0x18003f8f4  cmp     dword ptr [rax], 0C000000Dh
0x18003f8fa  setz    cl
0x18003f8fd  mov     eax, ecx
0x18003f8ff  add     rsp, 20h
0x18003f903  pop     rbp
0x18003f904  retn
```
