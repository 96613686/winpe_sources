# CreateTlgAggregateSession

- ea: `0x180016ea4`
- end: `0x180016f7a`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016bc0`

## callees

- `0x180016ea4`
- `0x180016f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016ef8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180016ef8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ed8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ed8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ebe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ebe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016f20`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016f20`

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
    if ( !a1 || !dword_18009C078 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180016ea4  mov     [rsp+arg_0], rbx
0x180016ea9  mov     [rsp+arg_18], rsi
0x180016eae  push    rdi
0x180016eaf  sub     rsp, 20h
0x180016eb3  mov     sil, cl
0x180016eb6  xor     dil, dil
0x180016eb9  mov     [rsp+28h+arg_8], dil
0x180016ebe  call    cs:__imp_GetProcessHeap
0x180016ec5  nop     dword ptr [rax+rax+00h]
0x180016eca  mov     rcx, rax; hHeap
0x180016ecd  mov     edx, 8; dwFlags
0x180016ed2  mov     r8d, 168h; dwBytes
0x180016ed8  call    cs:__imp_HeapAlloc
0x180016edf  nop     dword ptr [rax+rax+00h]
0x180016ee4  mov     rbx, rax
0x180016ee7  mov     [rsp+28h+arg_10], rax
0x180016eec  test    rax, rax
0x180016eef  jz      short loc_180016F57
0x180016ef1  lea     rcx, [rax+108h]; SRWLock
0x180016ef8  call    cs:__imp_InitializeSRWLock
0x180016eff  nop     dword ptr [rax+rax+00h]
0x180016f04  test    sil, sil
0x180016f07  jz      short loc_180016F54
0x180016f09  mov     ecx, cs:dword_18009C078
0x180016f0f  test    ecx, ecx
0x180016f11  jnz     short loc_180016F57
0x180016f13  xor     r8d, r8d; pcbe
0x180016f16  mov     rdx, rbx; pv
0x180016f19  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180016f20  call    cs:__imp_CreateThreadpoolTimer
0x180016f27  nop     dword ptr [rax+rax+00h]
0x180016f2c  mov     [rbx+158h], rax
0x180016f33  jmp     short loc_180016F4A
0x180016f35  mov     eax, 1
0x180016f3a  xchg    eax, cs:dword_18009C078
0x180016f40  mov     dil, [rsp+28h+arg_8]
0x180016f45  mov     rbx, [rsp+28h+arg_10]
0x180016f4a  cmp     qword ptr [rbx+158h], 0
0x180016f52  jz      short loc_180016F57
0x180016f54  mov     dil, 1
0x180016f57  test    dil, dil
0x180016f5a  jnz     short loc_180016F66
0x180016f5c  mov     rcx, rbx; lpMem
0x180016f5f  call    DestroyAggregateSession
0x180016f64  xor     ebx, ebx
0x180016f66  mov     rax, rbx
0x180016f69  mov     rbx, [rsp+28h+arg_0]
0x180016f6e  mov     rsi, [rsp+28h+arg_18]
0x180016f73  add     rsp, 20h
0x180016f77  pop     rdi
0x180016f78  retn
0x18005fb68  push    rbp
0x18005fb6a  sub     rsp, 20h
0x18005fb6e  mov     rbp, rdx
0x18005fb71  mov     rax, [rcx]
0x18005fb74  xor     ecx, ecx
0x18005fb76  cmp     dword ptr [rax], 0C000000Dh
0x18005fb7c  setz    cl
0x18005fb7f  mov     eax, ecx
0x18005fb81  add     rsp, 20h
0x18005fb85  pop     rbp
0x18005fb86  retn
```
