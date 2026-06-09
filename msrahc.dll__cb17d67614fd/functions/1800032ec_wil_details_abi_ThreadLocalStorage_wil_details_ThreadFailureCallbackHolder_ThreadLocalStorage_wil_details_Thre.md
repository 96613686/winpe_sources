# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800032ec`
- end: `0x18000333b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b2d0`

## callees

- `0x1800032ec`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000330d`
- `KERNEL32!GetProcessHeap` at `0x18000330d`
- `KERNEL32!HeapFree` at `0x18000331b`
- `KERNEL32!HeapFree` at `0x18000331b`

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
0x1800032ec  push    rbx
0x1800032ee  push    rbp
0x1800032ef  push    rsi
0x1800032f0  push    rdi
0x1800032f1  sub     rsp, 28h
0x1800032f5  lea     rbp, [rcx+50h]
0x1800032f9  mov     rdi, rcx
0x1800032fc  cmp     rcx, rbp
0x1800032ff  jz      short loc_180003332
0x180003301  mov     rsi, [rdi]
0x180003304  jmp     short loc_180003321
0x180003306  mov     rbx, rsi
0x180003309  mov     rsi, [rsi+8]
0x18000330d  call    cs:__imp_GetProcessHeap
0x180003313  mov     r8, rbx; lpMem
0x180003316  xor     edx, edx; dwFlags
0x180003318  mov     rcx, rax; hHeap
0x18000331b  call    cs:__imp_HeapFree
0x180003321  test    rsi, rsi
0x180003324  jnz     short loc_180003306
0x180003326  mov     [rdi], rsi
0x180003329  add     rdi, 8
0x18000332d  cmp     rdi, rbp
0x180003330  jnz     short loc_180003301
0x180003332  add     rsp, 28h
0x180003336  pop     rdi
0x180003337  pop     rsi
0x180003338  pop     rbp
0x180003339  pop     rbx
0x18000333a  retn
```
