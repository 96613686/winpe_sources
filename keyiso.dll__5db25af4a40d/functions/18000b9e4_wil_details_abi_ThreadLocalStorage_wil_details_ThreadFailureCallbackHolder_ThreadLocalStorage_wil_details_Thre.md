# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000b9e4`
- end: `0x18000ba33`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018c30`

## callees

- `0x18000b9e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba13`

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
0x18000b9e4  push    rbx
0x18000b9e6  push    rbp
0x18000b9e7  push    rsi
0x18000b9e8  push    rdi
0x18000b9e9  sub     rsp, 28h
0x18000b9ed  lea     rbp, [rcx+50h]
0x18000b9f1  mov     rdi, rcx
0x18000b9f4  cmp     rcx, rbp
0x18000b9f7  jz      short loc_18000BA2A
0x18000b9f9  mov     rsi, [rdi]
0x18000b9fc  jmp     short loc_18000BA19
0x18000b9fe  mov     rbx, rsi
0x18000ba01  mov     rsi, [rsi+8]
0x18000ba05  call    cs:__imp_GetProcessHeap
0x18000ba0b  mov     r8, rbx; lpMem
0x18000ba0e  xor     edx, edx; dwFlags
0x18000ba10  mov     rcx, rax; hHeap
0x18000ba13  call    cs:__imp_HeapFree
0x18000ba19  test    rsi, rsi
0x18000ba1c  jnz     short loc_18000B9FE
0x18000ba1e  mov     [rdi], rsi
0x18000ba21  add     rdi, 8
0x18000ba25  cmp     rdi, rbp
0x18000ba28  jnz     short loc_18000B9F9
0x18000ba2a  add     rsp, 28h
0x18000ba2e  pop     rdi
0x18000ba2f  pop     rsi
0x18000ba30  pop     rbp
0x18000ba31  pop     rbx
0x18000ba32  retn
```
