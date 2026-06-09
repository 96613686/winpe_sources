# CreateTlgAggregateSession

- ea: `0x18005d95c`
- end: `0x18005da36`
- name: `CreateTlgAggregateSession`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d7b4`

## callees

- `0x18005d95c`
- `0x18005daf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005d9b0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005d9b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005d9f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005d9f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d976`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d990`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d990`

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
    if ( !a1 || !dword_1801125E4 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18005d95c  mov     [rsp+arg_0], rbx
0x18005d961  mov     [rsp+arg_18], rsi
0x18005d966  push    rdi
0x18005d967  sub     rsp, 20h
0x18005d96b  mov     sil, cl
0x18005d96e  xor     dil, dil
0x18005d971  mov     [rsp+28h+arg_8], dil
0x18005d976  call    cs:__imp_GetProcessHeap
0x18005d97d  nop     dword ptr [rax+rax+00h]
0x18005d982  mov     rcx, rax; hHeap
0x18005d985  mov     edx, 8; dwFlags
0x18005d98a  mov     r8d, 168h; dwBytes
0x18005d990  call    cs:__imp_HeapAlloc
0x18005d997  nop     dword ptr [rax+rax+00h]
0x18005d99c  mov     rbx, rax
0x18005d99f  mov     [rsp+28h+arg_10], rax
0x18005d9a4  test    rax, rax
0x18005d9a7  jz      short loc_18005D9C4
0x18005d9a9  lea     rcx, [rax+108h]; SRWLock
0x18005d9b0  call    cs:__imp_InitializeSRWLock
0x18005d9b7  nop     dword ptr [rax+rax+00h]
0x18005d9bc  test    sil, sil
0x18005d9bf  jnz     short loc_18005D9DD
0x18005d9c1  mov     dil, 1
0x18005d9c4  test    dil, dil
0x18005d9c7  jz      short loc_18005DA2A
0x18005d9c9  mov     rax, rbx
0x18005d9cc  mov     rbx, [rsp+28h+arg_0]
0x18005d9d1  mov     rsi, [rsp+28h+arg_18]
0x18005d9d6  add     rsp, 20h
0x18005d9da  pop     rdi
0x18005d9db  retn
0x18005d9dd  mov     ecx, cs:dword_1801125E4
0x18005d9e3  test    ecx, ecx
0x18005d9e5  jnz     short loc_18005D9C4
0x18005d9e7  xor     r8d, r8d; pcbe
0x18005d9ea  mov     rdx, rbx; pv
0x18005d9ed  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18005d9f4  call    cs:__imp_CreateThreadpoolTimer
0x18005d9fb  nop     dword ptr [rax+rax+00h]
0x18005da00  mov     [rbx+158h], rax
0x18005da07  jmp     short loc_18005DA1E
0x18005da09  mov     eax, 1
0x18005da0e  xchg    eax, cs:dword_1801125E4
0x18005da14  mov     dil, [rsp+28h+arg_8]
0x18005da19  mov     rbx, [rsp+28h+arg_10]
0x18005da1e  cmp     qword ptr [rbx+158h], 0
0x18005da26  jz      short loc_18005D9C4
0x18005da28  jmp     short loc_18005D9C1
0x18005da2a  mov     rcx, rbx; lpMem
0x18005da2d  call    DestroyAggregateSession
0x18005da32  xor     ebx, ebx
0x18005da34  jmp     short loc_18005D9C9
0x1800cb112  push    rbp
0x1800cb114  sub     rsp, 20h
0x1800cb118  mov     rbp, rdx
0x1800cb11b  mov     rax, [rcx]
0x1800cb11e  xor     ecx, ecx
0x1800cb120  cmp     dword ptr [rax], 0C000000Dh
0x1800cb126  setz    cl
0x1800cb129  mov     eax, ecx
0x1800cb12b  add     rsp, 20h
0x1800cb12f  pop     rbp
0x1800cb130  retn
```
