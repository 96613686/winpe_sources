# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000d5e0`
- end: `0x18000d64b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d616`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d602`

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
0x18000d5e0  mov     [rsp+arg_0], rbx
0x18000d5e5  mov     [rsp+arg_8], rsi
0x18000d5ea  push    rdi
0x18000d5eb  sub     rsp, 20h
0x18000d5ef  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000d5f6  mov     rsi, [rdi]
0x18000d5f9  jmp     short loc_18000D622
0x18000d5fb  mov     rbx, rsi
0x18000d5fe  mov     rsi, [rsi+8]
0x18000d602  call    cs:__imp_GetProcessHeap
0x18000d609  nop     dword ptr [rax+rax+00h]
0x18000d60e  mov     r8, rbx; lpMem
0x18000d611  xor     edx, edx; dwFlags
0x18000d613  mov     rcx, rax; hHeap
0x18000d616  call    cs:__imp_HeapFree
0x18000d61d  nop     dword ptr [rax+rax+00h]
0x18000d622  test    rsi, rsi
0x18000d625  jnz     short loc_18000D5FB
0x18000d627  mov     [rdi], rsi
0x18000d62a  lea     rax, g_header_init_InitializeResultHeader
0x18000d631  add     rdi, 8
0x18000d635  cmp     rdi, rax
0x18000d638  jnz     short loc_18000D5F6
0x18000d63a  mov     rbx, [rsp+28h+arg_0]
0x18000d63f  mov     rsi, [rsp+28h+arg_8]
0x18000d644  add     rsp, 20h
0x18000d648  pop     rdi
0x18000d649  retn
```
