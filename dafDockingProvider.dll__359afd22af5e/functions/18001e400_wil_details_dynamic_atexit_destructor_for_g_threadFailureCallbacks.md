# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001e400`
- end: `0x18001e45e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001e400`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e430`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e422`

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
0x18001e400  mov     [rsp+arg_0], rbx
0x18001e405  mov     [rsp+arg_8], rsi
0x18001e40a  push    rdi
0x18001e40b  sub     rsp, 20h
0x18001e40f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001e416  mov     rsi, [rdi]
0x18001e419  jmp     short loc_18001E436
0x18001e41b  mov     rbx, rsi
0x18001e41e  mov     rsi, [rsi+8]
0x18001e422  call    cs:__imp_GetProcessHeap
0x18001e428  mov     r8, rbx; lpMem
0x18001e42b  xor     edx, edx; dwFlags
0x18001e42d  mov     rcx, rax; hHeap
0x18001e430  call    cs:__imp_HeapFree
0x18001e436  test    rsi, rsi
0x18001e439  jnz     short loc_18001E41B
0x18001e43b  mov     [rdi], rsi
0x18001e43e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18001e445  add     rdi, 8
0x18001e449  cmp     rdi, rax
0x18001e44c  jnz     short loc_18001E416
0x18001e44e  mov     rbx, [rsp+28h+arg_0]
0x18001e453  mov     rsi, [rsp+28h+arg_8]
0x18001e458  add     rsp, 20h
0x18001e45c  pop     rdi
0x18001e45d  retn
```
