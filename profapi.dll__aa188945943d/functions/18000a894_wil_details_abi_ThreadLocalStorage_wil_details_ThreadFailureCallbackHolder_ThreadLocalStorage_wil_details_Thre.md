# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000a894`
- end: `0x18000a8e3`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a880`

## callees

- `0x18000a894`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8cd`

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
0x18000a894  push    rbx
0x18000a896  push    rbp
0x18000a897  push    rsi
0x18000a898  push    rdi
0x18000a899  sub     rsp, 28h
0x18000a89d  lea     rbp, [rcx+50h]
0x18000a8a1  mov     rdi, rcx
0x18000a8a4  cmp     rcx, rbp
0x18000a8a7  jz      short loc_18000A8BD
0x18000a8a9  mov     rsi, [rdi]
0x18000a8ac  test    rsi, rsi
0x18000a8af  jnz     short loc_18000A8C6
0x18000a8b1  mov     [rdi], rsi
0x18000a8b4  add     rdi, 8
0x18000a8b8  cmp     rdi, rbp
0x18000a8bb  jnz     short loc_18000A8A9
0x18000a8bd  add     rsp, 28h
0x18000a8c1  pop     rdi
0x18000a8c2  pop     rsi
0x18000a8c3  pop     rbp
0x18000a8c4  pop     rbx
0x18000a8c5  retn
0x18000a8c6  mov     rbx, rsi
0x18000a8c9  mov     rsi, [rsi+8]
0x18000a8cd  call    cs:__imp_GetProcessHeap
0x18000a8d3  mov     r8, rbx; lpMem
0x18000a8d6  xor     edx, edx; dwFlags
0x18000a8d8  mov     rcx, rax; hHeap
0x18000a8db  call    cs:__imp_HeapFree
0x18000a8e1  jmp     short loc_18000A8AC
```
