# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000763c`
- end: `0x18000768b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011d90`

## callees

- `0x18000763c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000766b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000766b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000765d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000765d`

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
0x18000763c  push    rbx
0x18000763e  push    rbp
0x18000763f  push    rsi
0x180007640  push    rdi
0x180007641  sub     rsp, 28h
0x180007645  lea     rbp, [rcx+50h]
0x180007649  mov     rdi, rcx
0x18000764c  cmp     rcx, rbp
0x18000764f  jz      short loc_180007682
0x180007651  mov     rsi, [rdi]
0x180007654  jmp     short loc_180007671
0x180007656  mov     rbx, rsi
0x180007659  mov     rsi, [rsi+8]
0x18000765d  call    cs:__imp_GetProcessHeap
0x180007663  mov     r8, rbx; lpMem
0x180007666  xor     edx, edx; dwFlags
0x180007668  mov     rcx, rax; hHeap
0x18000766b  call    cs:__imp_HeapFree
0x180007671  test    rsi, rsi
0x180007674  jnz     short loc_180007656
0x180007676  mov     [rdi], rsi
0x180007679  add     rdi, 8
0x18000767d  cmp     rdi, rbp
0x180007680  jnz     short loc_180007651
0x180007682  add     rsp, 28h
0x180007686  pop     rdi
0x180007687  pop     rsi
0x180007688  pop     rbp
0x180007689  pop     rbx
0x18000768a  retn
```
