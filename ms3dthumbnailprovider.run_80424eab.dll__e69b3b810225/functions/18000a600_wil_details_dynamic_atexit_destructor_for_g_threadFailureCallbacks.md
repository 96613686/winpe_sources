# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000a600`
- end: `0x18000a65e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a600`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000a630`
- `KERNEL32!HeapFree` at `0x18000a630`
- `KERNEL32!GetProcessHeap` at `0x18000a622`
- `KERNEL32!GetProcessHeap` at `0x18000a622`

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
0x18000a600  mov     [rsp+arg_0], rbx
0x18000a605  mov     [rsp+arg_8], rsi
0x18000a60a  push    rdi
0x18000a60b  sub     rsp, 20h
0x18000a60f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000a616  mov     rsi, [rdi]
0x18000a619  jmp     short loc_18000A636
0x18000a61b  mov     rbx, rsi
0x18000a61e  mov     rsi, [rsi+8]
0x18000a622  call    cs:__imp_GetProcessHeap
0x18000a628  mov     r8, rbx; lpMem
0x18000a62b  xor     edx, edx; dwFlags
0x18000a62d  mov     rcx, rax; hHeap
0x18000a630  call    cs:__imp_HeapFree
0x18000a636  test    rsi, rsi
0x18000a639  jnz     short loc_18000A61B
0x18000a63b  mov     [rdi], rsi
0x18000a63e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000a645  add     rdi, 8
0x18000a649  cmp     rdi, rax
0x18000a64c  jnz     short loc_18000A616
0x18000a64e  mov     rbx, [rsp+28h+arg_0]
0x18000a653  mov     rsi, [rsp+28h+arg_8]
0x18000a658  add     rsp, 20h
0x18000a65c  pop     rdi
0x18000a65d  retn
```
