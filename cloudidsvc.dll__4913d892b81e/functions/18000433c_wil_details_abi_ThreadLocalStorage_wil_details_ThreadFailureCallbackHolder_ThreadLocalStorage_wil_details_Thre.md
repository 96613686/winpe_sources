# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000433c`
- end: `0x18000438b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800115a0`

## callees

- `0x18000433c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000435d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000435d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000436b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000436b`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18000433c  push    rbx
0x18000433e  push    rbp
0x18000433f  push    rsi
0x180004340  push    rdi
0x180004341  sub     rsp, 28h
0x180004345  lea     rbp, [rcx+50h]
0x180004349  mov     rdi, rcx
0x18000434c  cmp     rcx, rbp
0x18000434f  jz      short loc_180004382
0x180004351  mov     rsi, [rdi]
0x180004354  jmp     short loc_180004371
0x180004356  mov     rbx, rsi
0x180004359  mov     rsi, [rsi+8]
0x18000435d  call    cs:__imp_GetProcessHeap
0x180004363  mov     r8, rbx; lpMem
0x180004366  xor     edx, edx; dwFlags
0x180004368  mov     rcx, rax; hHeap
0x18000436b  call    cs:__imp_HeapFree
0x180004371  test    rsi, rsi
0x180004374  jnz     short loc_180004356
0x180004376  mov     [rdi], rsi
0x180004379  add     rdi, 8
0x18000437d  cmp     rdi, rbp
0x180004380  jnz     short loc_180004351
0x180004382  add     rsp, 28h
0x180004386  pop     rdi
0x180004387  pop     rsi
0x180004388  pop     rbp
0x180004389  pop     rbx
0x18000438a  retn
```
