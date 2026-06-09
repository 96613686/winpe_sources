# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14001b240`
- end: `0x14001b29e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001b240`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b262`

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
    result = &g_header_init_InitializeStagingHeaderInternalApi;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x14001b240  mov     [rsp+arg_0], rbx
0x14001b245  mov     [rsp+arg_8], rsi
0x14001b24a  push    rdi
0x14001b24b  sub     rsp, 20h
0x14001b24f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14001b256  mov     rsi, [rdi]
0x14001b259  jmp     short loc_14001B276
0x14001b25b  mov     rbx, rsi
0x14001b25e  mov     rsi, [rsi+8]
0x14001b262  call    cs:__imp_GetProcessHeap
0x14001b268  mov     r8, rbx; lpMem
0x14001b26b  xor     edx, edx; dwFlags
0x14001b26d  mov     rcx, rax; hHeap
0x14001b270  call    cs:__imp_HeapFree
0x14001b276  test    rsi, rsi
0x14001b279  jnz     short loc_14001B25B
0x14001b27b  mov     [rdi], rsi
0x14001b27e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x14001b285  add     rdi, 8
0x14001b289  cmp     rdi, rax
0x14001b28c  jnz     short loc_14001B256
0x14001b28e  mov     rbx, [rsp+28h+arg_0]
0x14001b293  mov     rsi, [rsp+28h+arg_8]
0x14001b298  add     rsp, 20h
0x14001b29c  pop     rdi
0x14001b29d  retn
```
