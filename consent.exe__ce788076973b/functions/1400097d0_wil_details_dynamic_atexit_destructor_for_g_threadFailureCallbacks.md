# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400097d0`
- end: `0x14000982e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400097d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009800`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009800`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x1400097d0  mov     [rsp+arg_0], rbx
0x1400097d5  mov     [rsp+arg_8], rsi
0x1400097da  push    rdi
0x1400097db  sub     rsp, 20h
0x1400097df  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1400097e6  mov     rsi, [rdi]
0x1400097e9  jmp     short loc_140009806
0x1400097eb  mov     rbx, rsi
0x1400097ee  mov     rsi, [rsi+8]
0x1400097f2  call    cs:__imp_GetProcessHeap
0x1400097f8  mov     r8, rbx; lpMem
0x1400097fb  xor     edx, edx; dwFlags
0x1400097fd  mov     rcx, rax; hHeap
0x140009800  call    cs:__imp_HeapFree
0x140009806  test    rsi, rsi
0x140009809  jnz     short loc_1400097EB
0x14000980b  mov     [rdi], rsi
0x14000980e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140009815  add     rdi, 8
0x140009819  cmp     rdi, rax
0x14000981c  jnz     short loc_1400097E6
0x14000981e  mov     rbx, [rsp+28h+arg_0]
0x140009823  mov     rsi, [rsp+28h+arg_8]
0x140009828  add     rsp, 20h
0x14000982c  pop     rdi
0x14000982d  retn
```
