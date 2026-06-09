# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180009204`
- end: `0x180009253`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800091f0`

## callees

- `0x180009204`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000923d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000923d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000924b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000924b`

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
0x180009204  push    rbx
0x180009206  push    rbp
0x180009207  push    rsi
0x180009208  push    rdi
0x180009209  sub     rsp, 28h
0x18000920d  lea     rbp, [rcx+50h]
0x180009211  mov     rdi, rcx
0x180009214  cmp     rcx, rbp
0x180009217  jz      short loc_18000922D
0x180009219  mov     rsi, [rdi]
0x18000921c  test    rsi, rsi
0x18000921f  jnz     short loc_180009236
0x180009221  mov     [rdi], rsi
0x180009224  add     rdi, 8
0x180009228  cmp     rdi, rbp
0x18000922b  jnz     short loc_180009219
0x18000922d  add     rsp, 28h
0x180009231  pop     rdi
0x180009232  pop     rsi
0x180009233  pop     rbp
0x180009234  pop     rbx
0x180009235  retn
0x180009236  mov     rbx, rsi
0x180009239  mov     rsi, [rsi+8]
0x18000923d  call    cs:__imp_GetProcessHeap
0x180009243  mov     r8, rbx; lpMem
0x180009246  xor     edx, edx; dwFlags
0x180009248  mov     rcx, rax; hHeap
0x18000924b  call    cs:__imp_HeapFree
0x180009251  jmp     short loc_18000921C
```
