# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800036a0`
- end: `0x1800036ef`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025580`

## callees

- `0x1800036a0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800036c1`
- `KERNEL32!GetProcessHeap` at `0x1800036c1`
- `KERNEL32!HeapFree` at `0x1800036cf`
- `KERNEL32!HeapFree` at `0x1800036cf`

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
0x1800036a0  push    rbx
0x1800036a2  push    rbp
0x1800036a3  push    rsi
0x1800036a4  push    rdi
0x1800036a5  sub     rsp, 28h
0x1800036a9  mov     rdi, rcx
0x1800036ac  lea     rbp, [rcx+50h]
0x1800036b0  cmp     rcx, rbp
0x1800036b3  jz      short loc_1800036E6
0x1800036b5  mov     rsi, [rdi]
0x1800036b8  jmp     short loc_1800036D5
0x1800036ba  mov     rbx, rsi
0x1800036bd  mov     rsi, [rsi+8]
0x1800036c1  call    cs:__imp_GetProcessHeap
0x1800036c7  mov     rcx, rax; hHeap
0x1800036ca  mov     r8, rbx; lpMem
0x1800036cd  xor     edx, edx; dwFlags
0x1800036cf  call    cs:__imp_HeapFree
0x1800036d5  test    rsi, rsi
0x1800036d8  jnz     short loc_1800036BA
0x1800036da  mov     [rdi], rsi
0x1800036dd  add     rdi, 8
0x1800036e1  cmp     rdi, rbp
0x1800036e4  jnz     short loc_1800036B5
0x1800036e6  add     rsp, 28h
0x1800036ea  pop     rdi
0x1800036eb  pop     rsi
0x1800036ec  pop     rbp
0x1800036ed  pop     rbx
0x1800036ee  retn
```
