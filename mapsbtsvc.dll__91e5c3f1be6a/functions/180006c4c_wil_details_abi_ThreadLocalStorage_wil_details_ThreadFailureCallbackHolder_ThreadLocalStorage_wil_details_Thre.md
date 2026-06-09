# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180006c4c`
- end: `0x180006c9b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014950`

## callees

- `0x180006c4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c6d`

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
0x180006c4c  push    rbx
0x180006c4e  push    rbp
0x180006c4f  push    rsi
0x180006c50  push    rdi
0x180006c51  sub     rsp, 28h
0x180006c55  lea     rbp, [rcx+50h]
0x180006c59  mov     rdi, rcx
0x180006c5c  cmp     rcx, rbp
0x180006c5f  jz      short loc_180006C92
0x180006c61  mov     rsi, [rdi]
0x180006c64  jmp     short loc_180006C81
0x180006c66  mov     rbx, rsi
0x180006c69  mov     rsi, [rsi+8]
0x180006c6d  call    cs:__imp_GetProcessHeap
0x180006c73  mov     r8, rbx; lpMem
0x180006c76  xor     edx, edx; dwFlags
0x180006c78  mov     rcx, rax; hHeap
0x180006c7b  call    cs:__imp_HeapFree
0x180006c81  test    rsi, rsi
0x180006c84  jnz     short loc_180006C66
0x180006c86  mov     [rdi], rsi
0x180006c89  add     rdi, 8
0x180006c8d  cmp     rdi, rbp
0x180006c90  jnz     short loc_180006C61
0x180006c92  add     rsp, 28h
0x180006c96  pop     rdi
0x180006c97  pop     rsi
0x180006c98  pop     rbp
0x180006c99  pop     rbx
0x180006c9a  retn
```
