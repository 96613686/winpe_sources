# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140017028`
- end: `0x140017077`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f320`

## callees

- `0x140017028`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140017057`
- `KERNEL32!HeapFree` at `0x140017057`
- `KERNEL32!GetProcessHeap` at `0x140017049`
- `KERNEL32!GetProcessHeap` at `0x140017049`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbp
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1;
  v2 = a1 + 10;
  do
  {
    v3 = (_QWORD *)*v1;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v1++ = 0;
  }
  while ( v1 != v2 );
}

```

## disassembly

```asm
0x140017028  push    rbx
0x14001702a  push    rbp
0x14001702b  push    rsi
0x14001702c  push    rdi
0x14001702d  sub     rsp, 28h
0x140017031  mov     rdi, rcx
0x140017034  lea     rbp, [rcx+50h]
0x140017038  cmp     rcx, rbp
0x14001703b  jz      short loc_14001706E
0x14001703d  mov     rsi, [rdi]
0x140017040  jmp     short loc_14001705D
0x140017042  mov     rbx, rsi
0x140017045  mov     rsi, [rsi+8]
0x140017049  call    cs:__imp_GetProcessHeap
0x14001704f  mov     rcx, rax; hHeap
0x140017052  mov     r8, rbx; lpMem
0x140017055  xor     edx, edx; dwFlags
0x140017057  call    cs:__imp_HeapFree
0x14001705d  test    rsi, rsi
0x140017060  jnz     short loc_140017042
0x140017062  mov     [rdi], rsi
0x140017065  add     rdi, 8
0x140017069  cmp     rdi, rbp
0x14001706c  jnz     short loc_14001703D
0x14001706e  add     rsp, 28h
0x140017072  pop     rdi
0x140017073  pop     rsi
0x140017074  pop     rbp
0x140017075  pop     rbx
0x140017076  retn
```
