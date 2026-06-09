# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180011ef0`
- end: `0x180011f3f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800176e0`

## callees

- `0x180011ef0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011f1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011f1f`

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
0x180011ef0  push    rbx
0x180011ef2  push    rbp
0x180011ef3  push    rsi
0x180011ef4  push    rdi
0x180011ef5  sub     rsp, 28h
0x180011ef9  lea     rbp, [rcx+50h]
0x180011efd  mov     rdi, rcx
0x180011f00  cmp     rcx, rbp
0x180011f03  jz      short loc_180011F36
0x180011f05  mov     rsi, [rdi]
0x180011f08  jmp     short loc_180011F25
0x180011f0a  mov     rbx, rsi
0x180011f0d  mov     rsi, [rsi+8]
0x180011f11  call    cs:__imp_GetProcessHeap
0x180011f17  mov     r8, rbx; lpMem
0x180011f1a  xor     edx, edx; dwFlags
0x180011f1c  mov     rcx, rax; hHeap
0x180011f1f  call    cs:__imp_HeapFree
0x180011f25  test    rsi, rsi
0x180011f28  jnz     short loc_180011F0A
0x180011f2a  mov     [rdi], rsi
0x180011f2d  add     rdi, 8
0x180011f31  cmp     rdi, rbp
0x180011f34  jnz     short loc_180011F05
0x180011f36  add     rsp, 28h
0x180011f3a  pop     rdi
0x180011f3b  pop     rsi
0x180011f3c  pop     rbp
0x180011f3d  pop     rbx
0x180011f3e  retn
```
