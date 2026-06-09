# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140011dd0`
- end: `0x140011e2e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011dd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011df2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011df2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011e00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011e00`

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
0x140011dd0  mov     [rsp+arg_0], rbx
0x140011dd5  mov     [rsp+arg_8], rsi
0x140011dda  push    rdi
0x140011ddb  sub     rsp, 20h
0x140011ddf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140011de6  mov     rsi, [rdi]
0x140011de9  jmp     short loc_140011E06
0x140011deb  mov     rbx, rsi
0x140011dee  mov     rsi, [rsi+8]
0x140011df2  call    cs:__imp_GetProcessHeap
0x140011df8  mov     r8, rbx; lpMem
0x140011dfb  xor     edx, edx; dwFlags
0x140011dfd  mov     rcx, rax; hHeap
0x140011e00  call    cs:__imp_HeapFree
0x140011e06  test    rsi, rsi
0x140011e09  jnz     short loc_140011DEB
0x140011e0b  mov     [rdi], rsi
0x140011e0e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x140011e15  add     rdi, 8
0x140011e19  cmp     rdi, rax
0x140011e1c  jnz     short loc_140011DE6
0x140011e1e  mov     rbx, [rsp+28h+arg_0]
0x140011e23  mov     rsi, [rsp+28h+arg_8]
0x140011e28  add     rsp, 20h
0x140011e2c  pop     rdi
0x140011e2d  retn
```
