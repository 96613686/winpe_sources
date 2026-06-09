# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003c28`
- end: `0x180003c77`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b6f0`

## callees

- `0x180003c28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c57`

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
0x180003c28  push    rbx
0x180003c2a  push    rbp
0x180003c2b  push    rsi
0x180003c2c  push    rdi
0x180003c2d  sub     rsp, 28h
0x180003c31  lea     rbp, [rcx+50h]
0x180003c35  mov     rdi, rcx
0x180003c38  cmp     rcx, rbp
0x180003c3b  jz      short loc_180003C6E
0x180003c3d  mov     rsi, [rdi]
0x180003c40  jmp     short loc_180003C5D
0x180003c42  mov     rbx, rsi
0x180003c45  mov     rsi, [rsi+8]
0x180003c49  call    cs:__imp_GetProcessHeap
0x180003c4f  mov     r8, rbx; lpMem
0x180003c52  xor     edx, edx; dwFlags
0x180003c54  mov     rcx, rax; hHeap
0x180003c57  call    cs:__imp_HeapFree
0x180003c5d  test    rsi, rsi
0x180003c60  jnz     short loc_180003C42
0x180003c62  mov     [rdi], rsi
0x180003c65  add     rdi, 8
0x180003c69  cmp     rdi, rbp
0x180003c6c  jnz     short loc_180003C3D
0x180003c6e  add     rsp, 28h
0x180003c72  pop     rdi
0x180003c73  pop     rsi
0x180003c74  pop     rbp
0x180003c75  pop     rbx
0x180003c76  retn
```
