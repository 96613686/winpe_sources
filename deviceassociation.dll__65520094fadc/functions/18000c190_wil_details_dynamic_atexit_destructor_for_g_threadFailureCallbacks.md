# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000c190`
- end: `0x18000c1ee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c190`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1c0`

## pseudocode

```c
char *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  char *v0; // rdi
  _QWORD *v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  char *result; // rax

  v0 = (char *)wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *(_QWORD **)v0;
    while ( v1 )
    {
      v2 = v1;
      v1 = (_QWORD *)v1[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *(_QWORD *)v0 = 0;
    result = &g_header_init_InitializeResultHeader;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x18000c190  mov     [rsp+arg_0], rbx
0x18000c195  mov     [rsp+arg_8], rsi
0x18000c19a  push    rdi
0x18000c19b  sub     rsp, 20h
0x18000c19f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000c1a6  mov     rsi, [rdi]
0x18000c1a9  jmp     short loc_18000C1C6
0x18000c1ab  mov     rbx, rsi
0x18000c1ae  mov     rsi, [rsi+8]
0x18000c1b2  call    cs:__imp_GetProcessHeap
0x18000c1b8  mov     r8, rbx; lpMem
0x18000c1bb  xor     edx, edx; dwFlags
0x18000c1bd  mov     rcx, rax; hHeap
0x18000c1c0  call    cs:__imp_HeapFree
0x18000c1c6  test    rsi, rsi
0x18000c1c9  jnz     short loc_18000C1AB
0x18000c1cb  mov     [rdi], rsi
0x18000c1ce  lea     rax, g_header_init_InitializeResultHeader
0x18000c1d5  add     rdi, 8
0x18000c1d9  cmp     rdi, rax
0x18000c1dc  jnz     short loc_18000C1A6
0x18000c1de  mov     rbx, [rsp+28h+arg_0]
0x18000c1e3  mov     rsi, [rsp+28h+arg_8]
0x18000c1e8  add     rsp, 20h
0x18000c1ec  pop     rdi
0x18000c1ed  retn
```
