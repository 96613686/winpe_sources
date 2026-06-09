# CreateTlgAggregateSession

- ea: `0x1800178f0`
- end: `0x1800179ad`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800184d0`

## callees

- `0x1800178f0`
- `0x1800179b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180017938`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180017938`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001790a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001790a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001791e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001791e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001795a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001795a`

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
    if ( !a1 || !dword_180025CF0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800178f0  mov     [rsp+arg_0], rbx
0x1800178f5  mov     [rsp+arg_18], rsi
0x1800178fa  push    rdi
0x1800178fb  sub     rsp, 20h
0x1800178ff  mov     sil, cl
0x180017902  xor     dil, dil
0x180017905  mov     [rsp+28h+arg_8], dil
0x18001790a  call    cs:__imp_GetProcessHeap
0x180017910  mov     rcx, rax; hHeap
0x180017913  mov     edx, 8; dwFlags
0x180017918  mov     r8d, 168h; dwBytes
0x18001791e  call    cs:__imp_HeapAlloc
0x180017924  mov     rbx, rax
0x180017927  mov     [rsp+28h+arg_10], rax
0x18001792c  test    rax, rax
0x18001792f  jz      short loc_18001798B
0x180017931  lea     rcx, [rax+108h]; SRWLock
0x180017938  call    cs:__imp_InitializeSRWLock
0x18001793e  test    sil, sil
0x180017941  jz      short loc_180017988
0x180017943  mov     ecx, cs:dword_180025CF0
0x180017949  test    ecx, ecx
0x18001794b  jnz     short loc_18001798B
0x18001794d  xor     r8d, r8d; pcbe
0x180017950  mov     rdx, rbx; pv
0x180017953  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18001795a  call    cs:__imp_CreateThreadpoolTimer
0x180017960  mov     [rbx+158h], rax
0x180017967  jmp     short loc_18001797E
0x180017969  mov     eax, 1
0x18001796e  xchg    eax, cs:dword_180025CF0
0x180017974  mov     dil, [rsp+28h+arg_8]
0x180017979  mov     rbx, [rsp+28h+arg_10]
0x18001797e  cmp     qword ptr [rbx+158h], 0
0x180017986  jz      short loc_18001798B
0x180017988  mov     dil, 1
0x18001798b  test    dil, dil
0x18001798e  jnz     short loc_18001799A
0x180017990  mov     rcx, rbx; lpMem
0x180017993  call    DestroyAggregateSession
0x180017998  xor     ebx, ebx
0x18001799a  mov     rax, rbx
0x18001799d  mov     rbx, [rsp+28h+arg_0]
0x1800179a2  mov     rsi, [rsp+28h+arg_18]
0x1800179a7  add     rsp, 20h
0x1800179ab  pop     rdi
0x1800179ac  retn
0x180018b65  push    rbp
0x180018b67  sub     rsp, 20h
0x180018b6b  mov     rbp, rdx
0x180018b6e  mov     rax, [rcx]
0x180018b71  xor     ecx, ecx
0x180018b73  cmp     dword ptr [rax], 0C000000Dh
0x180018b79  setz    cl
0x180018b7c  mov     eax, ecx
0x180018b7e  add     rsp, 20h
0x180018b82  pop     rbp
0x180018b83  retn
```
