# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000b1c0`
- end: `0x18000b21e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b1c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1e2`

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
0x18000b1c0  mov     [rsp+arg_0], rbx
0x18000b1c5  mov     [rsp+arg_8], rsi
0x18000b1ca  push    rdi
0x18000b1cb  sub     rsp, 20h
0x18000b1cf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000b1d6  mov     rsi, [rdi]
0x18000b1d9  jmp     short loc_18000B1F6
0x18000b1db  mov     rbx, rsi
0x18000b1de  mov     rsi, [rsi+8]
0x18000b1e2  call    cs:__imp_GetProcessHeap
0x18000b1e8  mov     r8, rbx; lpMem
0x18000b1eb  xor     edx, edx; dwFlags
0x18000b1ed  mov     rcx, rax; hHeap
0x18000b1f0  call    cs:__imp_HeapFree
0x18000b1f6  test    rsi, rsi
0x18000b1f9  jnz     short loc_18000B1DB
0x18000b1fb  mov     [rdi], rsi
0x18000b1fe  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000b205  add     rdi, 8
0x18000b209  cmp     rdi, rax
0x18000b20c  jnz     short loc_18000B1D6
0x18000b20e  mov     rbx, [rsp+28h+arg_0]
0x18000b213  mov     rsi, [rsp+28h+arg_8]
0x18000b218  add     rsp, 20h
0x18000b21c  pop     rdi
0x18000b21d  retn
```
