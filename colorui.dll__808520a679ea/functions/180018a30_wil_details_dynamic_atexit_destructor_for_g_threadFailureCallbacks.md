# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180018a30`
- end: `0x180018a8e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018a30`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180018a52`
- `KERNEL32!GetProcessHeap` at `0x180018a52`
- `KERNEL32!HeapFree` at `0x180018a60`
- `KERNEL32!HeapFree` at `0x180018a60`

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
0x180018a30  mov     [rsp+arg_0], rbx
0x180018a35  mov     [rsp+arg_8], rsi
0x180018a3a  push    rdi
0x180018a3b  sub     rsp, 20h
0x180018a3f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180018a46  mov     rsi, [rdi]
0x180018a49  jmp     short loc_180018A66
0x180018a4b  mov     rbx, rsi
0x180018a4e  mov     rsi, [rsi+8]
0x180018a52  call    cs:__imp_GetProcessHeap
0x180018a58  mov     r8, rbx; lpMem
0x180018a5b  xor     edx, edx; dwFlags
0x180018a5d  mov     rcx, rax; hHeap
0x180018a60  call    cs:__imp_HeapFree
0x180018a66  test    rsi, rsi
0x180018a69  jnz     short loc_180018A4B
0x180018a6b  mov     [rdi], rsi
0x180018a6e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180018a75  add     rdi, 8
0x180018a79  cmp     rdi, rax
0x180018a7c  jnz     short loc_180018A46
0x180018a7e  mov     rbx, [rsp+28h+arg_0]
0x180018a83  mov     rsi, [rsp+28h+arg_8]
0x180018a88  add     rsp, 20h
0x180018a8c  pop     rdi
0x180018a8d  retn
```
