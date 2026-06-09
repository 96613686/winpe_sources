# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800037b4`
- end: `0x180003803`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800097b0`

## callees

- `0x1800037b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037d5`

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
0x1800037b4  push    rbx
0x1800037b6  push    rbp
0x1800037b7  push    rsi
0x1800037b8  push    rdi
0x1800037b9  sub     rsp, 28h
0x1800037bd  lea     rbp, [rcx+50h]
0x1800037c1  mov     rdi, rcx
0x1800037c4  cmp     rcx, rbp
0x1800037c7  jz      short loc_1800037FA
0x1800037c9  mov     rsi, [rdi]
0x1800037cc  jmp     short loc_1800037E9
0x1800037ce  mov     rbx, rsi
0x1800037d1  mov     rsi, [rsi+8]
0x1800037d5  call    cs:__imp_GetProcessHeap
0x1800037db  mov     r8, rbx; lpMem
0x1800037de  xor     edx, edx; dwFlags
0x1800037e0  mov     rcx, rax; hHeap
0x1800037e3  call    cs:__imp_HeapFree
0x1800037e9  test    rsi, rsi
0x1800037ec  jnz     short loc_1800037CE
0x1800037ee  mov     [rdi], rsi
0x1800037f1  add     rdi, 8
0x1800037f5  cmp     rdi, rbp
0x1800037f8  jnz     short loc_1800037C9
0x1800037fa  add     rsp, 28h
0x1800037fe  pop     rdi
0x1800037ff  pop     rsi
0x180003800  pop     rbp
0x180003801  pop     rbx
0x180003802  retn
```
