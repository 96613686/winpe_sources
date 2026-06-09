# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180007f04`
- end: `0x180007f53`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ef0`

## callees

- `0x180007f04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f3d`

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
0x180007f04  push    rbx
0x180007f06  push    rbp
0x180007f07  push    rsi
0x180007f08  push    rdi
0x180007f09  sub     rsp, 28h
0x180007f0d  lea     rbp, [rcx+50h]
0x180007f11  mov     rdi, rcx
0x180007f14  cmp     rcx, rbp
0x180007f17  jz      short loc_180007F2D
0x180007f19  mov     rsi, [rdi]
0x180007f1c  test    rsi, rsi
0x180007f1f  jnz     short loc_180007F36
0x180007f21  mov     [rdi], rsi
0x180007f24  add     rdi, 8
0x180007f28  cmp     rdi, rbp
0x180007f2b  jnz     short loc_180007F19
0x180007f2d  add     rsp, 28h
0x180007f31  pop     rdi
0x180007f32  pop     rsi
0x180007f33  pop     rbp
0x180007f34  pop     rbx
0x180007f35  retn
0x180007f36  mov     rbx, rsi
0x180007f39  mov     rsi, [rsi+8]
0x180007f3d  call    cs:__imp_GetProcessHeap
0x180007f43  mov     r8, rbx; lpMem
0x180007f46  xor     edx, edx; dwFlags
0x180007f48  mov     rcx, rax; hHeap
0x180007f4b  call    cs:__imp_HeapFree
0x180007f51  jmp     short loc_180007F1C
```
