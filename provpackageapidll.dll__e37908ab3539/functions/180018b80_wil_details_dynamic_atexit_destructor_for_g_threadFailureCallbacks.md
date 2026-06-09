# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180018b80`
- end: `0x180018bde`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018b80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ba2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ba2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018bb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018bb0`

## pseudocode

```c
__int64 *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rdi
  __int64 v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *result; // rax

  v0 = wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = (void *)v1;
      v1 = *(_QWORD *)(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x180018b80  mov     [rsp+arg_0], rbx
0x180018b85  mov     [rsp+arg_8], rsi
0x180018b8a  push    rdi
0x180018b8b  sub     rsp, 20h
0x180018b8f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180018b96  mov     rsi, [rdi]
0x180018b99  jmp     short loc_180018BB6
0x180018b9b  mov     rbx, rsi
0x180018b9e  mov     rsi, [rsi+8]
0x180018ba2  call    cs:__imp_GetProcessHeap
0x180018ba8  mov     r8, rbx; lpMem
0x180018bab  xor     edx, edx; dwFlags
0x180018bad  mov     rcx, rax; hHeap
0x180018bb0  call    cs:__imp_HeapFree
0x180018bb6  test    rsi, rsi
0x180018bb9  jnz     short loc_180018B9B
0x180018bbb  mov     [rdi], rsi
0x180018bbe  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180018bc5  add     rdi, 8
0x180018bc9  cmp     rdi, rax
0x180018bcc  jnz     short loc_180018B96
0x180018bce  mov     rbx, [rsp+28h+arg_0]
0x180018bd3  mov     rsi, [rsp+28h+arg_8]
0x180018bd8  add     rsp, 20h
0x180018bdc  pop     rdi
0x180018bdd  retn
```
