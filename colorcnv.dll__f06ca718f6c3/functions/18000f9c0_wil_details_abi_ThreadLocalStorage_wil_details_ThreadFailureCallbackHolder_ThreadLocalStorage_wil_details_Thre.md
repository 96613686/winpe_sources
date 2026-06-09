# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000f9c0`
- end: `0x18000fa0f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a130`

## callees

- `0x18000f9c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9e1`

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
0x18000f9c0  push    rbx
0x18000f9c2  push    rbp
0x18000f9c3  push    rsi
0x18000f9c4  push    rdi
0x18000f9c5  sub     rsp, 28h
0x18000f9c9  lea     rbp, [rcx+50h]
0x18000f9cd  mov     rdi, rcx
0x18000f9d0  cmp     rcx, rbp
0x18000f9d3  jz      short loc_18000FA06
0x18000f9d5  mov     rsi, [rdi]
0x18000f9d8  jmp     short loc_18000F9F5
0x18000f9da  mov     rbx, rsi
0x18000f9dd  mov     rsi, [rsi+8]
0x18000f9e1  call    cs:__imp_GetProcessHeap
0x18000f9e7  mov     r8, rbx; lpMem
0x18000f9ea  xor     edx, edx; dwFlags
0x18000f9ec  mov     rcx, rax; hHeap
0x18000f9ef  call    cs:__imp_HeapFree
0x18000f9f5  test    rsi, rsi
0x18000f9f8  jnz     short loc_18000F9DA
0x18000f9fa  mov     [rdi], rsi
0x18000f9fd  add     rdi, 8
0x18000fa01  cmp     rdi, rbp
0x18000fa04  jnz     short loc_18000F9D5
0x18000fa06  add     rsp, 28h
0x18000fa0a  pop     rdi
0x18000fa0b  pop     rsi
0x18000fa0c  pop     rbp
0x18000fa0d  pop     rbx
0x18000fa0e  retn
```
