# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800231e0`
- end: `0x180023237`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800235bc`
- `0x18003981a`
- `0x180039aa5`

## callees

- `0x1800231e0`
- `0x180023534`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023217`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023209`

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
0x1800231e0  push    rbx
0x1800231e2  push    rbp
0x1800231e3  push    rsi
0x1800231e4  push    rdi
0x1800231e5  sub     rsp, 28h
0x1800231e9  mov     rdi, rcx
0x1800231ec  lea     rbp, [rcx+50h]
0x1800231f0  cmp     rcx, rbp
0x1800231f3  jz      short loc_18002322E
0x1800231f5  mov     rsi, [rdi]
0x1800231f8  jmp     short loc_18002321D
0x1800231fa  mov     rbx, rsi
0x1800231fd  mov     rsi, [rsi+8]
0x180023201  mov     rcx, rbx
0x180023204  call    ??1Node@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::Node::~Node(void)
0x180023209  call    cs:__imp_GetProcessHeap
0x18002320f  mov     rcx, rax; hHeap
0x180023212  mov     r8, rbx; lpMem
0x180023215  xor     edx, edx; dwFlags
0x180023217  call    cs:__imp_HeapFree
0x18002321d  test    rsi, rsi
0x180023220  jnz     short loc_1800231FA
0x180023222  mov     [rdi], rsi
0x180023225  add     rdi, 8
0x180023229  cmp     rdi, rbp
0x18002322c  jnz     short loc_1800231F5
0x18002322e  add     rsp, 28h
0x180023232  pop     rdi
0x180023233  pop     rsi
0x180023234  pop     rbp
0x180023235  pop     rbx
0x180023236  retn
```
