# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140016210`
- end: `0x14001627b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140016210`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016232`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016232`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016246`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016246`

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
    result = &g_header_init_InitializeResultHeader;
    ++v0;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x140016210  mov     [rsp+arg_0], rbx
0x140016215  mov     [rsp+arg_8], rsi
0x14001621a  push    rdi
0x14001621b  sub     rsp, 20h
0x14001621f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140016226  mov     rsi, [rdi]
0x140016229  jmp     short loc_140016252
0x14001622b  mov     rbx, rsi
0x14001622e  mov     rsi, [rsi+8]
0x140016232  call    cs:__imp_GetProcessHeap
0x140016239  nop     dword ptr [rax+rax+00h]
0x14001623e  mov     r8, rbx; lpMem
0x140016241  xor     edx, edx; dwFlags
0x140016243  mov     rcx, rax; hHeap
0x140016246  call    cs:__imp_HeapFree
0x14001624d  nop     dword ptr [rax+rax+00h]
0x140016252  test    rsi, rsi
0x140016255  jnz     short loc_14001622B
0x140016257  mov     [rdi], rsi
0x14001625a  lea     rax, g_header_init_InitializeResultHeader
0x140016261  add     rdi, 8
0x140016265  cmp     rdi, rax
0x140016268  jnz     short loc_140016226
0x14001626a  mov     rbx, [rsp+28h+arg_0]
0x14001626f  mov     rsi, [rsp+28h+arg_8]
0x140016274  add     rsp, 20h
0x140016278  pop     rdi
0x140016279  retn
```
