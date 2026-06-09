# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800144f0`
- end: `0x18001454e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800144f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014512`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014512`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014520`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014520`

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
0x1800144f0  mov     [rsp+arg_0], rbx
0x1800144f5  mov     [rsp+arg_8], rsi
0x1800144fa  push    rdi
0x1800144fb  sub     rsp, 20h
0x1800144ff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180014506  mov     rsi, [rdi]
0x180014509  jmp     short loc_180014526
0x18001450b  mov     rbx, rsi
0x18001450e  mov     rsi, [rsi+8]
0x180014512  call    cs:__imp_GetProcessHeap
0x180014518  mov     r8, rbx; lpMem
0x18001451b  xor     edx, edx; dwFlags
0x18001451d  mov     rcx, rax; hHeap
0x180014520  call    cs:__imp_HeapFree
0x180014526  test    rsi, rsi
0x180014529  jnz     short loc_18001450B
0x18001452b  mov     [rdi], rsi
0x18001452e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180014535  add     rdi, 8
0x180014539  cmp     rdi, rax
0x18001453c  jnz     short loc_180014506
0x18001453e  mov     rbx, [rsp+28h+arg_0]
0x180014543  mov     rsi, [rsp+28h+arg_8]
0x180014548  add     rsp, 20h
0x18001454c  pop     rdi
0x18001454d  retn
```
