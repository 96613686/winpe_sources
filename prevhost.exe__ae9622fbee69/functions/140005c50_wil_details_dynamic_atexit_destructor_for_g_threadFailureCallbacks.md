# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140005c50`
- end: `0x140005cae`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005c50`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140005c72`
- `KERNEL32!GetProcessHeap` at `0x140005c72`
- `KERNEL32!HeapFree` at `0x140005c80`
- `KERNEL32!HeapFree` at `0x140005c80`

## pseudocode

```c
__int64 *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rdi
  __int64 v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *result; // rax

  v0 = wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = (void *)v1;
      v1 = *(_QWORD *)(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x140005c50  mov     [rsp+arg_0], rbx
0x140005c55  mov     [rsp+arg_8], rsi
0x140005c5a  push    rdi
0x140005c5b  sub     rsp, 20h
0x140005c5f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140005c66  mov     rsi, [rdi]
0x140005c69  jmp     short loc_140005C86
0x140005c6b  mov     rbx, rsi
0x140005c6e  mov     rsi, [rsi+8]
0x140005c72  call    cs:__imp_GetProcessHeap
0x140005c78  mov     r8, rbx; lpMem
0x140005c7b  xor     edx, edx; dwFlags
0x140005c7d  mov     rcx, rax; hHeap
0x140005c80  call    cs:__imp_HeapFree
0x140005c86  test    rsi, rsi
0x140005c89  jnz     short loc_140005C6B
0x140005c8b  mov     [rdi], rsi
0x140005c8e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140005c95  add     rdi, 8
0x140005c99  cmp     rdi, rax
0x140005c9c  jnz     short loc_140005C66
0x140005c9e  mov     rbx, [rsp+28h+arg_0]
0x140005ca3  mov     rsi, [rsp+28h+arg_8]
0x140005ca8  add     rsp, 20h
0x140005cac  pop     rdi
0x140005cad  retn
```
