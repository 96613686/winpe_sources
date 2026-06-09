# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003fa0`
- end: `0x180004015`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac00`

## callees

- `0x180003fa0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fe5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fd7`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rsi
  _QWORD *v3; // rbx
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
0x180003fa0  mov     [rsp+arg_10], rbp
0x180003fa5  push    rsi
0x180003fa6  sub     rsp, 20h
0x180003faa  lea     rbp, [rcx+50h]
0x180003fae  mov     rsi, rcx
0x180003fb1  cmp     rcx, rbp
0x180003fb4  jz      short loc_18000400A
0x180003fb6  mov     [rsp+28h+arg_0], rbx
0x180003fbb  mov     [rsp+28h+arg_8], rdi
0x180003fc0  mov     rbx, [rsi]
0x180003fc3  test    rbx, rbx
0x180003fc6  jz      short loc_180003FF0
0x180003fc8  nop     dword ptr [rax+rax+00000000h]
0x180003fd0  mov     rdi, rbx
0x180003fd3  mov     rbx, [rbx+8]
0x180003fd7  call    cs:__imp_GetProcessHeap
0x180003fdd  mov     r8, rdi; lpMem
0x180003fe0  xor     edx, edx; dwFlags
0x180003fe2  mov     rcx, rax; hHeap
0x180003fe5  call    cs:__imp_HeapFree
0x180003feb  test    rbx, rbx
0x180003fee  jnz     short loc_180003FD0
0x180003ff0  mov     qword ptr [rsi], 0
0x180003ff7  add     rsi, 8
0x180003ffb  cmp     rsi, rbp
0x180003ffe  jnz     short loc_180003FC0
0x180004000  mov     rdi, [rsp+28h+arg_8]
0x180004005  mov     rbx, [rsp+28h+arg_0]
0x18000400a  mov     rbp, [rsp+28h+arg_10]
0x18000400f  add     rsp, 20h
0x180004013  pop     rsi
0x180004014  retn
```
