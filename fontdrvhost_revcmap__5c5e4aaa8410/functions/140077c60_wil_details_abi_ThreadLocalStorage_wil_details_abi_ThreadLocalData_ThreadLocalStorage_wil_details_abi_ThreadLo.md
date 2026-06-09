# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140077c60`
- end: `0x140077d3a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140077ba8`

## callees

- `0x140077c60`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140077cad`
- `KERNEL32!GetProcessHeap` at `0x140077cde`
- `KERNEL32!GetProcessHeap` at `0x140077cfc`
- `KERNEL32!GetProcessHeap` at `0x140077cad`
- `KERNEL32!GetProcessHeap` at `0x140077cde`
- `KERNEL32!GetProcessHeap` at `0x140077cfc`
- `KERNEL32!HeapFree` at `0x140077cbb`
- `KERNEL32!HeapFree` at `0x140077cec`
- `KERNEL32!HeapFree` at `0x140077d0a`
- `KERNEL32!HeapFree` at `0x140077cbb`
- `KERNEL32!HeapFree` at `0x140077cec`
- `KERNEL32!HeapFree` at `0x140077d0a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x140077c60  push    rbx
0x140077c62  push    rbp
0x140077c63  push    rsi
0x140077c64  push    rdi
0x140077c65  push    r12
0x140077c67  push    r13
0x140077c69  push    r14
0x140077c6b  push    r15
0x140077c6d  sub     rsp, 28h
0x140077c71  lea     r15, [rcx+50h]
0x140077c75  mov     rdi, rcx
0x140077c78  cmp     rcx, r15
0x140077c7b  jz      loc_140077D29
0x140077c81  mov     rsi, [rdi]
0x140077c84  jmp     loc_140077D10
0x140077c89  mov     r13, rsi
0x140077c8c  mov     r12, rsi
0x140077c8f  mov     rsi, [rsi+8]
0x140077c93  movzx   eax, word ptr [r13+30h]
0x140077c98  mov     rbp, [r13+28h]
0x140077c9c  lea     r14, [rax+rax*4]
0x140077ca0  shl     r14, 4
0x140077ca4  add     r14, rbp
0x140077ca7  jmp     short loc_140077CD5
0x140077ca9  mov     rbx, [rbp+40h]
0x140077cad  call    cs:__imp_GetProcessHeap
0x140077cb3  mov     r8, rbx; lpMem
0x140077cb6  xor     edx, edx; dwFlags
0x140077cb8  mov     rcx, rax; hHeap
0x140077cbb  call    cs:__imp_HeapFree
0x140077cc1  mov     qword ptr [rbp+40h], 0
0x140077cc9  mov     qword ptr [rbp+48h], 0
0x140077cd1  add     rbp, 50h ; 'P'
0x140077cd5  cmp     rbp, r14
0x140077cd8  jnz     short loc_140077CA9
0x140077cda  mov     rbx, [r13+28h]
0x140077cde  call    cs:__imp_GetProcessHeap
0x140077ce4  mov     r8, rbx; lpMem
0x140077ce7  xor     edx, edx; dwFlags
0x140077ce9  mov     rcx, rax; hHeap
0x140077cec  call    cs:__imp_HeapFree
0x140077cf2  xor     eax, eax
0x140077cf4  mov     [r13+30h], eax
0x140077cf8  mov     [r13+28h], rax
0x140077cfc  call    cs:__imp_GetProcessHeap
0x140077d02  mov     r8, r12; lpMem
0x140077d05  xor     edx, edx; dwFlags
0x140077d07  mov     rcx, rax; hHeap
0x140077d0a  call    cs:__imp_HeapFree
0x140077d10  test    rsi, rsi
0x140077d13  jnz     loc_140077C89
0x140077d19  mov     [rdi], rsi
0x140077d1c  add     rdi, 8
0x140077d20  cmp     rdi, r15
0x140077d23  jnz     loc_140077C81
0x140077d29  add     rsp, 28h
0x140077d2d  pop     r15
0x140077d2f  pop     r14
0x140077d31  pop     r13
0x140077d33  pop     r12
0x140077d35  pop     rdi
0x140077d36  pop     rsi
0x140077d37  pop     rbp
0x140077d38  pop     rbx
0x140077d39  retn
```
