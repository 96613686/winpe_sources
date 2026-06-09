# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140019ce0`
- end: `0x140019d4b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140019ce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019d02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019d02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019d16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019d16`

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
0x140019ce0  mov     [rsp+arg_0], rbx
0x140019ce5  mov     [rsp+arg_8], rsi
0x140019cea  push    rdi
0x140019ceb  sub     rsp, 20h
0x140019cef  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140019cf6  mov     rsi, [rdi]
0x140019cf9  jmp     short loc_140019D22
0x140019cfb  mov     rbx, rsi
0x140019cfe  mov     rsi, [rsi+8]
0x140019d02  call    cs:__imp_GetProcessHeap
0x140019d09  nop     dword ptr [rax+rax+00h]
0x140019d0e  mov     r8, rbx; lpMem
0x140019d11  xor     edx, edx; dwFlags
0x140019d13  mov     rcx, rax; hHeap
0x140019d16  call    cs:__imp_HeapFree
0x140019d1d  nop     dword ptr [rax+rax+00h]
0x140019d22  test    rsi, rsi
0x140019d25  jnz     short loc_140019CFB
0x140019d27  mov     [rdi], rsi
0x140019d2a  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140019d31  add     rdi, 8
0x140019d35  cmp     rdi, rax
0x140019d38  jnz     short loc_140019CF6
0x140019d3a  mov     rbx, [rsp+28h+arg_0]
0x140019d3f  mov     rsi, [rsp+28h+arg_8]
0x140019d44  add     rsp, 20h
0x140019d48  pop     rdi
0x140019d49  retn
```
