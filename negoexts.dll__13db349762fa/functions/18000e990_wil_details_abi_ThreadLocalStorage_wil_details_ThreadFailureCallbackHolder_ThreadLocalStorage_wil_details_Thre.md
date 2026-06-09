# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000e990`
- end: `0x18000e9df`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f420`

## callees

- `0x18000e990`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e9bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e9bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9b1`

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
0x18000e990  push    rbx
0x18000e992  push    rbp
0x18000e993  push    rsi
0x18000e994  push    rdi
0x18000e995  sub     rsp, 28h
0x18000e999  lea     rbp, [rcx+50h]
0x18000e99d  mov     rdi, rcx
0x18000e9a0  cmp     rcx, rbp
0x18000e9a3  jz      short loc_18000E9D6
0x18000e9a5  mov     rsi, [rdi]
0x18000e9a8  jmp     short loc_18000E9C5
0x18000e9aa  mov     rbx, rsi
0x18000e9ad  mov     rsi, [rsi+8]
0x18000e9b1  call    cs:__imp_GetProcessHeap
0x18000e9b7  mov     r8, rbx; lpMem
0x18000e9ba  xor     edx, edx; dwFlags
0x18000e9bc  mov     rcx, rax; hHeap
0x18000e9bf  call    cs:__imp_HeapFree
0x18000e9c5  test    rsi, rsi
0x18000e9c8  jnz     short loc_18000E9AA
0x18000e9ca  mov     [rdi], rsi
0x18000e9cd  add     rdi, 8
0x18000e9d1  cmp     rdi, rbp
0x18000e9d4  jnz     short loc_18000E9A5
0x18000e9d6  add     rsp, 28h
0x18000e9da  pop     rdi
0x18000e9db  pop     rsi
0x18000e9dc  pop     rbp
0x18000e9dd  pop     rbx
0x18000e9de  retn
```
