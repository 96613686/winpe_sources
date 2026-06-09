# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180001f00`
- end: `0x180001f75`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009fa0`

## callees

- `0x180001f00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f45`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rsi
  _QWORD *v2; // rbx
  _QWORD *v3; // rbp
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    if ( *v2 )
    {
      do
      {
        v4 = v3;
        v3 = (_QWORD *)v3[1];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      while ( v3 );
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180001f00  mov     [rsp+arg_10], rbx
0x180001f05  push    rsi
0x180001f06  sub     rsp, 20h
0x180001f0a  lea     rsi, [rcx+50h]
0x180001f0e  mov     rbx, rcx
0x180001f11  cmp     rcx, rsi
0x180001f14  jz      short loc_180001F6A
0x180001f16  mov     [rsp+28h+arg_0], rbp
0x180001f1b  mov     [rsp+28h+arg_8], rdi
0x180001f20  mov     rbp, [rbx]
0x180001f23  test    rbp, rbp
0x180001f26  jz      short loc_180001F50
0x180001f28  nop     dword ptr [rax+rax+00000000h]
0x180001f30  mov     rdi, rbp
0x180001f33  mov     rbp, [rbp+8]
0x180001f37  call    cs:__imp_GetProcessHeap
0x180001f3d  mov     r8, rdi; lpMem
0x180001f40  xor     edx, edx; dwFlags
0x180001f42  mov     rcx, rax; hHeap
0x180001f45  call    cs:__imp_HeapFree
0x180001f4b  test    rbp, rbp
0x180001f4e  jnz     short loc_180001F30
0x180001f50  mov     qword ptr [rbx], 0
0x180001f57  add     rbx, 8
0x180001f5b  cmp     rbx, rsi
0x180001f5e  jnz     short loc_180001F20
0x180001f60  mov     rdi, [rsp+28h+arg_8]
0x180001f65  mov     rbp, [rsp+28h+arg_0]
0x180001f6a  mov     rbx, [rsp+28h+arg_10]
0x180001f6f  add     rsp, 20h
0x180001f73  pop     rsi
0x180001f74  retn
```
