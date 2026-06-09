# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000dda0`
- end: `0x18000de0b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000dda0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ddd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ddd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddc2`

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
0x18000dda0  mov     [rsp+arg_0], rbx
0x18000dda5  mov     [rsp+arg_8], rsi
0x18000ddaa  push    rdi
0x18000ddab  sub     rsp, 20h
0x18000ddaf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000ddb6  mov     rsi, [rdi]
0x18000ddb9  jmp     short loc_18000DDE2
0x18000ddbb  mov     rbx, rsi
0x18000ddbe  mov     rsi, [rsi+8]
0x18000ddc2  call    cs:__imp_GetProcessHeap
0x18000ddc9  nop     dword ptr [rax+rax+00h]
0x18000ddce  mov     r8, rbx; lpMem
0x18000ddd1  xor     edx, edx; dwFlags
0x18000ddd3  mov     rcx, rax; hHeap
0x18000ddd6  call    cs:__imp_HeapFree
0x18000dddd  nop     dword ptr [rax+rax+00h]
0x18000dde2  test    rsi, rsi
0x18000dde5  jnz     short loc_18000DDBB
0x18000dde7  mov     [rdi], rsi
0x18000ddea  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000ddf1  add     rdi, 8
0x18000ddf5  cmp     rdi, rax
0x18000ddf8  jnz     short loc_18000DDB6
0x18000ddfa  mov     rbx, [rsp+28h+arg_0]
0x18000ddff  mov     rsi, [rsp+28h+arg_8]
0x18000de04  add     rsp, 20h
0x18000de08  pop     rdi
0x18000de09  retn
```
