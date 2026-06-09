# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140005e90`
- end: `0x140005eee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005e90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ec0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ec0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005eb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005eb2`

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
0x140005e90  mov     [rsp+arg_0], rbx
0x140005e95  mov     [rsp+arg_8], rsi
0x140005e9a  push    rdi
0x140005e9b  sub     rsp, 20h
0x140005e9f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140005ea6  mov     rsi, [rdi]
0x140005ea9  jmp     short loc_140005EC6
0x140005eab  mov     rbx, rsi
0x140005eae  mov     rsi, [rsi+8]
0x140005eb2  call    cs:__imp_GetProcessHeap
0x140005eb8  mov     r8, rbx; lpMem
0x140005ebb  xor     edx, edx; dwFlags
0x140005ebd  mov     rcx, rax; hHeap
0x140005ec0  call    cs:__imp_HeapFree
0x140005ec6  test    rsi, rsi
0x140005ec9  jnz     short loc_140005EAB
0x140005ecb  mov     [rdi], rsi
0x140005ece  lea     rax, g_header_init_InitializeResultHeader
0x140005ed5  add     rdi, 8
0x140005ed9  cmp     rdi, rax
0x140005edc  jnz     short loc_140005EA6
0x140005ede  mov     rbx, [rsp+28h+arg_0]
0x140005ee3  mov     rsi, [rsp+28h+arg_8]
0x140005ee8  add     rsp, 20h
0x140005eec  pop     rdi
0x140005eed  retn
```
