# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000c7d0`
- end: `0x18000c82e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c7d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c800`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c800`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7f2`

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
0x18000c7d0  mov     [rsp+arg_0], rbx
0x18000c7d5  mov     [rsp+arg_8], rsi
0x18000c7da  push    rdi
0x18000c7db  sub     rsp, 20h
0x18000c7df  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000c7e6  mov     rsi, [rdi]
0x18000c7e9  jmp     short loc_18000C806
0x18000c7eb  mov     rbx, rsi
0x18000c7ee  mov     rsi, [rsi+8]
0x18000c7f2  call    cs:__imp_GetProcessHeap
0x18000c7f8  mov     r8, rbx; lpMem
0x18000c7fb  xor     edx, edx; dwFlags
0x18000c7fd  mov     rcx, rax; hHeap
0x18000c800  call    cs:__imp_HeapFree
0x18000c806  test    rsi, rsi
0x18000c809  jnz     short loc_18000C7EB
0x18000c80b  mov     [rdi], rsi
0x18000c80e  lea     rax, g_header_init_InitializeResultHeader
0x18000c815  add     rdi, 8
0x18000c819  cmp     rdi, rax
0x18000c81c  jnz     short loc_18000C7E6
0x18000c81e  mov     rbx, [rsp+28h+arg_0]
0x18000c823  mov     rsi, [rsp+28h+arg_8]
0x18000c828  add     rsp, 20h
0x18000c82c  pop     rdi
0x18000c82d  retn
```
