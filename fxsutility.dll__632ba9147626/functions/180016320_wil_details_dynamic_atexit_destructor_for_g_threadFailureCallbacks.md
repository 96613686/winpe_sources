# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180016320`
- end: `0x18001637e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016320`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180016350`
- `KERNEL32!HeapFree` at `0x180016350`
- `KERNEL32!GetProcessHeap` at `0x180016342`
- `KERNEL32!GetProcessHeap` at `0x180016342`

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
0x180016320  mov     [rsp+arg_0], rbx
0x180016325  mov     [rsp+arg_8], rsi
0x18001632a  push    rdi
0x18001632b  sub     rsp, 20h
0x18001632f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180016336  mov     rsi, [rdi]
0x180016339  jmp     short loc_180016356
0x18001633b  mov     rbx, rsi
0x18001633e  mov     rsi, [rsi+8]
0x180016342  call    cs:__imp_GetProcessHeap
0x180016348  mov     r8, rbx; lpMem
0x18001634b  xor     edx, edx; dwFlags
0x18001634d  mov     rcx, rax; hHeap
0x180016350  call    cs:__imp_HeapFree
0x180016356  test    rsi, rsi
0x180016359  jnz     short loc_18001633B
0x18001635b  mov     [rdi], rsi
0x18001635e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180016365  add     rdi, 8
0x180016369  cmp     rdi, rax
0x18001636c  jnz     short loc_180016336
0x18001636e  mov     rbx, [rsp+28h+arg_0]
0x180016373  mov     rsi, [rsp+28h+arg_8]
0x180016378  add     rsp, 20h
0x18001637c  pop     rdi
0x18001637d  retn
```
