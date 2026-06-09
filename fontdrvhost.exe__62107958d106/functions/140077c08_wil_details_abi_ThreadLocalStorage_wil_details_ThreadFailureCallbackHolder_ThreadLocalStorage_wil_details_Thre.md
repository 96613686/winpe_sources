# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140077c08`
- end: `0x140077c57`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140097f00`

## callees

- `0x140077c08`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140077c29`
- `KERNEL32!GetProcessHeap` at `0x140077c29`
- `KERNEL32!HeapFree` at `0x140077c37`
- `KERNEL32!HeapFree` at `0x140077c37`

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
0x140077c08  push    rbx
0x140077c0a  push    rbp
0x140077c0b  push    rsi
0x140077c0c  push    rdi
0x140077c0d  sub     rsp, 28h
0x140077c11  lea     rbp, [rcx+50h]
0x140077c15  mov     rdi, rcx
0x140077c18  cmp     rcx, rbp
0x140077c1b  jz      short loc_140077C4E
0x140077c1d  mov     rsi, [rdi]
0x140077c20  jmp     short loc_140077C3D
0x140077c22  mov     rbx, rsi
0x140077c25  mov     rsi, [rsi+8]
0x140077c29  call    cs:__imp_GetProcessHeap
0x140077c2f  mov     r8, rbx; lpMem
0x140077c32  xor     edx, edx; dwFlags
0x140077c34  mov     rcx, rax; hHeap
0x140077c37  call    cs:__imp_HeapFree
0x140077c3d  test    rsi, rsi
0x140077c40  jnz     short loc_140077C22
0x140077c42  mov     [rdi], rsi
0x140077c45  add     rdi, 8
0x140077c49  cmp     rdi, rbp
0x140077c4c  jnz     short loc_140077C1D
0x140077c4e  add     rsp, 28h
0x140077c52  pop     rdi
0x140077c53  pop     rsi
0x140077c54  pop     rbp
0x140077c55  pop     rbx
0x140077c56  retn
```
