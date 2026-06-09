# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180006cd0`
- end: `0x180006d3b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006cd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d06`

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
0x180006cd0  mov     [rsp+arg_0], rbx
0x180006cd5  mov     [rsp+arg_8], rsi
0x180006cda  push    rdi
0x180006cdb  sub     rsp, 20h
0x180006cdf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180006ce6  mov     rsi, [rdi]
0x180006ce9  jmp     short loc_180006D12
0x180006ceb  mov     rbx, rsi
0x180006cee  mov     rsi, [rsi+8]
0x180006cf2  call    cs:__imp_GetProcessHeap
0x180006cf9  nop     dword ptr [rax+rax+00h]
0x180006cfe  mov     r8, rbx; lpMem
0x180006d01  xor     edx, edx; dwFlags
0x180006d03  mov     rcx, rax; hHeap
0x180006d06  call    cs:__imp_HeapFree
0x180006d0d  nop     dword ptr [rax+rax+00h]
0x180006d12  test    rsi, rsi
0x180006d15  jnz     short loc_180006CEB
0x180006d17  mov     [rdi], rsi
0x180006d1a  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180006d21  add     rdi, 8
0x180006d25  cmp     rdi, rax
0x180006d28  jnz     short loc_180006CE6
0x180006d2a  mov     rbx, [rsp+28h+arg_0]
0x180006d2f  mov     rsi, [rsp+28h+arg_8]
0x180006d34  add     rsp, 20h
0x180006d38  pop     rdi
0x180006d39  retn
```
