# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800222b0`
- end: `0x18002230e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800222b0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800222d2`
- `KERNEL32!GetProcessHeap` at `0x1800222d2`
- `KERNEL32!HeapFree` at `0x1800222e0`
- `KERNEL32!HeapFree` at `0x1800222e0`

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
0x1800222b0  mov     [rsp+arg_0], rbx
0x1800222b5  mov     [rsp+arg_8], rsi
0x1800222ba  push    rdi
0x1800222bb  sub     rsp, 20h
0x1800222bf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800222c6  mov     rsi, [rdi]
0x1800222c9  jmp     short loc_1800222E6
0x1800222cb  mov     rbx, rsi
0x1800222ce  mov     rsi, [rsi+8]
0x1800222d2  call    cs:__imp_GetProcessHeap
0x1800222d8  mov     r8, rbx; lpMem
0x1800222db  xor     edx, edx; dwFlags
0x1800222dd  mov     rcx, rax; hHeap
0x1800222e0  call    cs:__imp_HeapFree
0x1800222e6  test    rsi, rsi
0x1800222e9  jnz     short loc_1800222CB
0x1800222eb  mov     [rdi], rsi
0x1800222ee  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x1800222f5  add     rdi, 8
0x1800222f9  cmp     rdi, rax
0x1800222fc  jnz     short loc_1800222C6
0x1800222fe  mov     rbx, [rsp+28h+arg_0]
0x180022303  mov     rsi, [rsp+28h+arg_8]
0x180022308  add     rsp, 20h
0x18002230c  pop     rdi
0x18002230d  retn
```
