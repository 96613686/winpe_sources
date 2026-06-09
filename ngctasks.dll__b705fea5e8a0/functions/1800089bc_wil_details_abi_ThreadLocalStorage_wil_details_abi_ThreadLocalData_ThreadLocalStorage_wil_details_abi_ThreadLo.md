# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800089bc`
- end: `0x180008a13`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008e6c`
- `0x18001f0d3`
- `0x18001f4d5`

## callees

- `0x1800089bc`
- `0x180008de4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089f3`

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
0x1800089bc  push    rbx
0x1800089be  push    rbp
0x1800089bf  push    rsi
0x1800089c0  push    rdi
0x1800089c1  sub     rsp, 28h
0x1800089c5  mov     rdi, rcx
0x1800089c8  lea     rbp, [rcx+50h]
0x1800089cc  cmp     rcx, rbp
0x1800089cf  jz      short loc_180008A0A
0x1800089d1  mov     rsi, [rdi]
0x1800089d4  jmp     short loc_1800089F9
0x1800089d6  mov     rbx, rsi
0x1800089d9  mov     rsi, [rsi+8]
0x1800089dd  mov     rcx, rbx
0x1800089e0  call    ??1Node@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::Node::~Node(void)
0x1800089e5  call    cs:__imp_GetProcessHeap
0x1800089eb  mov     rcx, rax; hHeap
0x1800089ee  mov     r8, rbx; lpMem
0x1800089f1  xor     edx, edx; dwFlags
0x1800089f3  call    cs:__imp_HeapFree
0x1800089f9  test    rsi, rsi
0x1800089fc  jnz     short loc_1800089D6
0x1800089fe  mov     [rdi], rsi
0x180008a01  add     rdi, 8
0x180008a05  cmp     rdi, rbp
0x180008a08  jnz     short loc_1800089D1
0x180008a0a  add     rsp, 28h
0x180008a0e  pop     rdi
0x180008a0f  pop     rsi
0x180008a10  pop     rbp
0x180008a11  pop     rbx
0x180008a12  retn
```
