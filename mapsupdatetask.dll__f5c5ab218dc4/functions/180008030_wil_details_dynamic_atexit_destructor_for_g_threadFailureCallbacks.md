# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180008030`
- end: `0x18000808e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008030`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008052`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008052`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008060`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008060`

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
0x180008030  mov     [rsp+arg_0], rbx
0x180008035  mov     [rsp+arg_8], rsi
0x18000803a  push    rdi
0x18000803b  sub     rsp, 20h
0x18000803f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180008046  mov     rsi, [rdi]
0x180008049  jmp     short loc_180008066
0x18000804b  mov     rbx, rsi
0x18000804e  mov     rsi, [rsi+8]
0x180008052  call    cs:__imp_GetProcessHeap
0x180008058  mov     r8, rbx; lpMem
0x18000805b  xor     edx, edx; dwFlags
0x18000805d  mov     rcx, rax; hHeap
0x180008060  call    cs:__imp_HeapFree
0x180008066  test    rsi, rsi
0x180008069  jnz     short loc_18000804B
0x18000806b  mov     [rdi], rsi
0x18000806e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180008075  add     rdi, 8
0x180008079  cmp     rdi, rax
0x18000807c  jnz     short loc_180008046
0x18000807e  mov     rbx, [rsp+28h+arg_0]
0x180008083  mov     rsi, [rsp+28h+arg_8]
0x180008088  add     rsp, 20h
0x18000808c  pop     rdi
0x18000808d  retn
```
