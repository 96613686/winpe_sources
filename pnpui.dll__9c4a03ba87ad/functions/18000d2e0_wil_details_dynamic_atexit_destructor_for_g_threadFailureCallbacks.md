# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000d2e0`
- end: `0x18000d33e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d2e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d302`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d302`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d310`

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
    result = g_header_init_InitializeStagingHeaderInternalApi;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x18000d2e0  mov     [rsp+arg_0], rbx
0x18000d2e5  mov     [rsp+arg_8], rsi
0x18000d2ea  push    rdi
0x18000d2eb  sub     rsp, 20h
0x18000d2ef  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000d2f6  mov     rsi, [rdi]
0x18000d2f9  jmp     short loc_18000D316
0x18000d2fb  mov     rbx, rsi
0x18000d2fe  mov     rsi, [rsi+8]
0x18000d302  call    cs:__imp_GetProcessHeap
0x18000d308  mov     r8, rbx; lpMem
0x18000d30b  xor     edx, edx; dwFlags
0x18000d30d  mov     rcx, rax; hHeap
0x18000d310  call    cs:__imp_HeapFree
0x18000d316  test    rsi, rsi
0x18000d319  jnz     short loc_18000D2FB
0x18000d31b  mov     [rdi], rsi
0x18000d31e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18000d325  add     rdi, 8
0x18000d329  cmp     rdi, rax
0x18000d32c  jnz     short loc_18000D2F6
0x18000d32e  mov     rbx, [rsp+28h+arg_0]
0x18000d333  mov     rsi, [rsp+28h+arg_8]
0x18000d338  add     rsp, 20h
0x18000d33c  pop     rdi
0x18000d33d  retn
```
