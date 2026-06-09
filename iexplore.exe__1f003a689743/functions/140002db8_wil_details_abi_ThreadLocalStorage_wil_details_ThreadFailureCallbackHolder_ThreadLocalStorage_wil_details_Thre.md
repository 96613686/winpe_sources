# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140002db8`
- end: `0x140002e07`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005b60`

## callees

- `0x140002db8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140002dd9`
- `KERNEL32!GetProcessHeap` at `0x140002dd9`
- `KERNEL32!HeapFree` at `0x140002de7`
- `KERNEL32!HeapFree` at `0x140002de7`

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
0x140002db8  push    rbx
0x140002dba  push    rbp
0x140002dbb  push    rsi
0x140002dbc  push    rdi
0x140002dbd  sub     rsp, 28h
0x140002dc1  lea     rbp, [rcx+50h]
0x140002dc5  mov     rdi, rcx
0x140002dc8  cmp     rcx, rbp
0x140002dcb  jz      short loc_140002DFE
0x140002dcd  mov     rsi, [rdi]
0x140002dd0  jmp     short loc_140002DED
0x140002dd2  mov     rbx, rsi
0x140002dd5  mov     rsi, [rsi+8]
0x140002dd9  call    cs:__imp_GetProcessHeap
0x140002ddf  mov     r8, rbx; lpMem
0x140002de2  xor     edx, edx; dwFlags
0x140002de4  mov     rcx, rax; hHeap
0x140002de7  call    cs:__imp_HeapFree
0x140002ded  test    rsi, rsi
0x140002df0  jnz     short loc_140002DD2
0x140002df2  mov     [rdi], rsi
0x140002df5  add     rdi, 8
0x140002df9  cmp     rdi, rbp
0x140002dfc  jnz     short loc_140002DCD
0x140002dfe  add     rsp, 28h
0x140002e02  pop     rdi
0x140002e03  pop     rsi
0x140002e04  pop     rbp
0x140002e05  pop     rbx
0x140002e06  retn
```
