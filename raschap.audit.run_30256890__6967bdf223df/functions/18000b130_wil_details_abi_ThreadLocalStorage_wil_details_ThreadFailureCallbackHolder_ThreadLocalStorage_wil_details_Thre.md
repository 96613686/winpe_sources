# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000b130`
- end: `0x18000b191`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026440`

## callees

- `0x18000b130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b176`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b176`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b184`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b184`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rbp
  _QWORD *v3; // rsi
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = a1;
  v2 = a1 + 10;
  do
  {
    v3 = (_QWORD *)*v1;
    if ( *v1 )
    {
      do
      {
        v4 = v3;
        v3 = (_QWORD *)v3[1];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      while ( v3 );
    }
    *v1++ = 0;
  }
  while ( v1 != v2 );
}

```

## disassembly

```asm
0x18000b130  push    rbx
0x18000b132  push    rbp
0x18000b133  push    rsi
0x18000b134  push    rdi
0x18000b135  push    r14
0x18000b137  sub     rsp, 20h
0x18000b13b  mov     rbx, rcx
0x18000b13e  lea     rbp, [rcx+50h]
0x18000b142  cmp     rcx, rbp
0x18000b145  jz      short loc_18000B164
0x18000b147  xor     r14d, r14d
0x18000b14a  nop     word ptr [rax+rax+00h]
0x18000b150  mov     rsi, [rbx]
0x18000b153  test    rsi, rsi
0x18000b156  jnz     short loc_18000B16F
0x18000b158  mov     [rbx], r14
0x18000b15b  add     rbx, 8
0x18000b15f  cmp     rbx, rbp
0x18000b162  jnz     short loc_18000B150
0x18000b164  add     rsp, 20h
0x18000b168  pop     r14
0x18000b16a  pop     rdi
0x18000b16b  pop     rsi
0x18000b16c  pop     rbp
0x18000b16d  pop     rbx
0x18000b16e  retn
0x18000b16f  mov     rdi, rsi
0x18000b172  mov     rsi, [rsi+8]
0x18000b176  call    cs:__imp_GetProcessHeap
0x18000b17c  mov     rcx, rax; hHeap
0x18000b17f  mov     r8, rdi; lpMem
0x18000b182  xor     edx, edx; dwFlags
0x18000b184  call    cs:__imp_HeapFree
0x18000b18a  test    rsi, rsi
0x18000b18d  jnz     short loc_18000B16F
0x18000b18f  jmp     short loc_18000B158
```
