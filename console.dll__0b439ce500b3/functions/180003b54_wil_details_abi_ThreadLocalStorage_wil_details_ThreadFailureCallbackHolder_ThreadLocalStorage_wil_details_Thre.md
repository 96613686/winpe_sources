# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003b54`
- end: `0x180003bb0`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800196a0`

## callees

- `0x180003b54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b75`

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
0x180003b54  push    rbx
0x180003b56  push    rbp
0x180003b57  push    rsi
0x180003b58  push    rdi
0x180003b59  sub     rsp, 28h
0x180003b5d  lea     rbp, [rcx+50h]
0x180003b61  mov     rdi, rcx
0x180003b64  cmp     rcx, rbp
0x180003b67  jz      short loc_180003BA6
0x180003b69  mov     rsi, [rdi]
0x180003b6c  jmp     short loc_180003B95
0x180003b6e  mov     rbx, rsi
0x180003b71  mov     rsi, [rsi+8]
0x180003b75  call    cs:__imp_GetProcessHeap
0x180003b7c  nop     dword ptr [rax+rax+00h]
0x180003b81  mov     r8, rbx; lpMem
0x180003b84  xor     edx, edx; dwFlags
0x180003b86  mov     rcx, rax; hHeap
0x180003b89  call    cs:__imp_HeapFree
0x180003b90  nop     dword ptr [rax+rax+00h]
0x180003b95  test    rsi, rsi
0x180003b98  jnz     short loc_180003B6E
0x180003b9a  mov     [rdi], rsi
0x180003b9d  add     rdi, 8
0x180003ba1  cmp     rdi, rbp
0x180003ba4  jnz     short loc_180003B69
0x180003ba6  add     rsp, 28h
0x180003baa  pop     rdi
0x180003bab  pop     rsi
0x180003bac  pop     rbp
0x180003bad  pop     rbx
0x180003bae  retn
```
