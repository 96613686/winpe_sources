# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400092f0`
- end: `0x14000935b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400092f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009326`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009326`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009312`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009312`

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
0x1400092f0  mov     [rsp+arg_0], rbx
0x1400092f5  mov     [rsp+arg_8], rsi
0x1400092fa  push    rdi
0x1400092fb  sub     rsp, 20h
0x1400092ff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140009306  mov     rsi, [rdi]
0x140009309  jmp     short loc_140009332
0x14000930b  mov     rbx, rsi
0x14000930e  mov     rsi, [rsi+8]
0x140009312  call    cs:__imp_GetProcessHeap
0x140009319  nop     dword ptr [rax+rax+00h]
0x14000931e  mov     r8, rbx; lpMem
0x140009321  xor     edx, edx; dwFlags
0x140009323  mov     rcx, rax; hHeap
0x140009326  call    cs:__imp_HeapFree
0x14000932d  nop     dword ptr [rax+rax+00h]
0x140009332  test    rsi, rsi
0x140009335  jnz     short loc_14000930B
0x140009337  mov     [rdi], rsi
0x14000933a  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140009341  add     rdi, 8
0x140009345  cmp     rdi, rax
0x140009348  jnz     short loc_140009306
0x14000934a  mov     rbx, [rsp+28h+arg_0]
0x14000934f  mov     rsi, [rsp+28h+arg_8]
0x140009354  add     rsp, 20h
0x140009358  pop     rdi
0x140009359  retn
```
