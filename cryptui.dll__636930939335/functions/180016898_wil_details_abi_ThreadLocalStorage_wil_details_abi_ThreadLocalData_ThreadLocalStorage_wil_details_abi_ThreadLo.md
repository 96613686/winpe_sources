# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180016898`
- end: `0x1800168ef`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180016d14`
- `0x18003f799`
- `0x18003fb3e`

## callees

- `0x180016898`
- `0x180016c8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800168cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800168cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800168c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800168c1`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
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
      wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::Node::~Node(v4);
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
0x180016898  push    rbx
0x18001689a  push    rbp
0x18001689b  push    rsi
0x18001689c  push    rdi
0x18001689d  sub     rsp, 28h
0x1800168a1  mov     rdi, rcx
0x1800168a4  lea     rbp, [rcx+50h]
0x1800168a8  cmp     rcx, rbp
0x1800168ab  jz      short loc_1800168E6
0x1800168ad  mov     rsi, [rdi]
0x1800168b0  jmp     short loc_1800168D5
0x1800168b2  mov     rbx, rsi
0x1800168b5  mov     rsi, [rsi+8]
0x1800168b9  mov     rcx, rbx
0x1800168bc  call    ??1Node@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::Node::~Node(void)
0x1800168c1  call    cs:__imp_GetProcessHeap
0x1800168c7  mov     rcx, rax; hHeap
0x1800168ca  mov     r8, rbx; lpMem
0x1800168cd  xor     edx, edx; dwFlags
0x1800168cf  call    cs:__imp_HeapFree
0x1800168d5  test    rsi, rsi
0x1800168d8  jnz     short loc_1800168B2
0x1800168da  mov     [rdi], rsi
0x1800168dd  add     rdi, 8
0x1800168e1  cmp     rdi, rbp
0x1800168e4  jnz     short loc_1800168AD
0x1800168e6  add     rsp, 28h
0x1800168ea  pop     rdi
0x1800168eb  pop     rsi
0x1800168ec  pop     rbp
0x1800168ed  pop     rbx
0x1800168ee  retn
```
