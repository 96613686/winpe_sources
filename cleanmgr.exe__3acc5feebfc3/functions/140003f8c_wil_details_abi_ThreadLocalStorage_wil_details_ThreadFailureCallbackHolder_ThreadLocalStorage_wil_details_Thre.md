# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140003f8c`
- end: `0x140003fdb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400178d0`

## callees

- `0x140003f8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003fad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003fbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003fbb`

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
0x140003f8c  push    rbx
0x140003f8e  push    rbp
0x140003f8f  push    rsi
0x140003f90  push    rdi
0x140003f91  sub     rsp, 28h
0x140003f95  lea     rbp, [rcx+50h]
0x140003f99  mov     rdi, rcx
0x140003f9c  cmp     rcx, rbp
0x140003f9f  jz      short loc_140003FD2
0x140003fa1  mov     rsi, [rdi]
0x140003fa4  jmp     short loc_140003FC1
0x140003fa6  mov     rbx, rsi
0x140003fa9  mov     rsi, [rsi+8]
0x140003fad  call    cs:__imp_GetProcessHeap
0x140003fb3  mov     r8, rbx; lpMem
0x140003fb6  xor     edx, edx; dwFlags
0x140003fb8  mov     rcx, rax; hHeap
0x140003fbb  call    cs:__imp_HeapFree
0x140003fc1  test    rsi, rsi
0x140003fc4  jnz     short loc_140003FA6
0x140003fc6  mov     [rdi], rsi
0x140003fc9  add     rdi, 8
0x140003fcd  cmp     rdi, rbp
0x140003fd0  jnz     short loc_140003FA1
0x140003fd2  add     rsp, 28h
0x140003fd6  pop     rdi
0x140003fd7  pop     rsi
0x140003fd8  pop     rbp
0x140003fd9  pop     rbx
0x140003fda  retn
```
