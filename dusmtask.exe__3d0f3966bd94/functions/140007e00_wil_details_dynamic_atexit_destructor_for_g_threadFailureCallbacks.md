# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140007e00`
- end: `0x140007e5e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007e00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007e30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007e30`

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
0x140007e00  mov     [rsp+arg_0], rbx
0x140007e05  mov     [rsp+arg_8], rsi
0x140007e0a  push    rdi
0x140007e0b  sub     rsp, 20h
0x140007e0f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140007e16  mov     rsi, [rdi]
0x140007e19  jmp     short loc_140007E36
0x140007e1b  mov     rbx, rsi
0x140007e1e  mov     rsi, [rsi+8]
0x140007e22  call    cs:__imp_GetProcessHeap
0x140007e28  mov     r8, rbx; lpMem
0x140007e2b  xor     edx, edx; dwFlags
0x140007e2d  mov     rcx, rax; hHeap
0x140007e30  call    cs:__imp_HeapFree
0x140007e36  test    rsi, rsi
0x140007e39  jnz     short loc_140007E1B
0x140007e3b  mov     [rdi], rsi
0x140007e3e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140007e45  add     rdi, 8
0x140007e49  cmp     rdi, rax
0x140007e4c  jnz     short loc_140007E16
0x140007e4e  mov     rbx, [rsp+28h+arg_0]
0x140007e53  mov     rsi, [rsp+28h+arg_8]
0x140007e58  add     rsp, 20h
0x140007e5c  pop     rdi
0x140007e5d  retn
```
