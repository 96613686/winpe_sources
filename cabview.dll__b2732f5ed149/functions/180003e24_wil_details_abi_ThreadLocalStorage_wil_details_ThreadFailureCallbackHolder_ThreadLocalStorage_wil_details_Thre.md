# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003e24`
- end: `0x180003e73`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012c50`

## callees

- `0x180003e24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e45`

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
0x180003e24  push    rbx
0x180003e26  push    rbp
0x180003e27  push    rsi
0x180003e28  push    rdi
0x180003e29  sub     rsp, 28h
0x180003e2d  lea     rbp, [rcx+50h]
0x180003e31  mov     rdi, rcx
0x180003e34  cmp     rcx, rbp
0x180003e37  jz      short loc_180003E6A
0x180003e39  mov     rsi, [rdi]
0x180003e3c  jmp     short loc_180003E59
0x180003e3e  mov     rbx, rsi
0x180003e41  mov     rsi, [rsi+8]
0x180003e45  call    cs:__imp_GetProcessHeap
0x180003e4b  mov     r8, rbx; lpMem
0x180003e4e  xor     edx, edx; dwFlags
0x180003e50  mov     rcx, rax; hHeap
0x180003e53  call    cs:__imp_HeapFree
0x180003e59  test    rsi, rsi
0x180003e5c  jnz     short loc_180003E3E
0x180003e5e  mov     [rdi], rsi
0x180003e61  add     rdi, 8
0x180003e65  cmp     rdi, rbp
0x180003e68  jnz     short loc_180003E39
0x180003e6a  add     rsp, 28h
0x180003e6e  pop     rdi
0x180003e6f  pop     rsi
0x180003e70  pop     rbp
0x180003e71  pop     rbx
0x180003e72  retn
```
