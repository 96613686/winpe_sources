# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180012e30`
- end: `0x180012e7f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024d00`

## callees

- `0x180012e30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e69`

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
0x180012e30  push    rbx
0x180012e32  push    rbp
0x180012e33  push    rsi
0x180012e34  push    rdi
0x180012e35  sub     rsp, 28h
0x180012e39  lea     rbp, [rcx+50h]
0x180012e3d  mov     rdi, rcx
0x180012e40  cmp     rcx, rbp
0x180012e43  jz      short loc_180012E59
0x180012e45  mov     rsi, [rdi]
0x180012e48  test    rsi, rsi
0x180012e4b  jnz     short loc_180012E62
0x180012e4d  mov     [rdi], rsi
0x180012e50  add     rdi, 8
0x180012e54  cmp     rdi, rbp
0x180012e57  jnz     short loc_180012E45
0x180012e59  add     rsp, 28h
0x180012e5d  pop     rdi
0x180012e5e  pop     rsi
0x180012e5f  pop     rbp
0x180012e60  pop     rbx
0x180012e61  retn
0x180012e62  mov     rbx, rsi
0x180012e65  mov     rsi, [rsi+8]
0x180012e69  call    cs:__imp_GetProcessHeap
0x180012e6f  mov     r8, rbx; lpMem
0x180012e72  xor     edx, edx; dwFlags
0x180012e74  mov     rcx, rax; hHeap
0x180012e77  call    cs:__imp_HeapFree
0x180012e7d  jmp     short loc_180012E48
```
