# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800038c4`
- end: `0x180003913`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b040`

## callees

- `0x1800038c4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800038e5`
- `KERNEL32!GetProcessHeap` at `0x1800038e5`
- `KERNEL32!HeapFree` at `0x1800038f3`
- `KERNEL32!HeapFree` at `0x1800038f3`

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
0x1800038c4  push    rbx
0x1800038c6  push    rbp
0x1800038c7  push    rsi
0x1800038c8  push    rdi
0x1800038c9  sub     rsp, 28h
0x1800038cd  lea     rbp, [rcx+50h]
0x1800038d1  mov     rdi, rcx
0x1800038d4  cmp     rcx, rbp
0x1800038d7  jz      short loc_18000390A
0x1800038d9  mov     rsi, [rdi]
0x1800038dc  jmp     short loc_1800038F9
0x1800038de  mov     rbx, rsi
0x1800038e1  mov     rsi, [rsi+8]
0x1800038e5  call    cs:__imp_GetProcessHeap
0x1800038eb  mov     r8, rbx; lpMem
0x1800038ee  xor     edx, edx; dwFlags
0x1800038f0  mov     rcx, rax; hHeap
0x1800038f3  call    cs:__imp_HeapFree
0x1800038f9  test    rsi, rsi
0x1800038fc  jnz     short loc_1800038DE
0x1800038fe  mov     [rdi], rsi
0x180003901  add     rdi, 8
0x180003905  cmp     rdi, rbp
0x180003908  jnz     short loc_1800038D9
0x18000390a  add     rsp, 28h
0x18000390e  pop     rdi
0x18000390f  pop     rsi
0x180003910  pop     rbp
0x180003911  pop     rbx
0x180003912  retn
```
