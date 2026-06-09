# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180008250`
- end: `0x1800082ae`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008250`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008280`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008280`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008272`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008272`

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
0x180008250  mov     [rsp+arg_0], rbx
0x180008255  mov     [rsp+arg_8], rsi
0x18000825a  push    rdi
0x18000825b  sub     rsp, 20h
0x18000825f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180008266  mov     rsi, [rdi]
0x180008269  jmp     short loc_180008286
0x18000826b  mov     rbx, rsi
0x18000826e  mov     rsi, [rsi+8]
0x180008272  call    cs:__imp_GetProcessHeap
0x180008278  mov     r8, rbx; lpMem
0x18000827b  xor     edx, edx; dwFlags
0x18000827d  mov     rcx, rax; hHeap
0x180008280  call    cs:__imp_HeapFree
0x180008286  test    rsi, rsi
0x180008289  jnz     short loc_18000826B
0x18000828b  mov     [rdi], rsi
0x18000828e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180008295  add     rdi, 8
0x180008299  cmp     rdi, rax
0x18000829c  jnz     short loc_180008266
0x18000829e  mov     rbx, [rsp+28h+arg_0]
0x1800082a3  mov     rsi, [rsp+28h+arg_8]
0x1800082a8  add     rsp, 20h
0x1800082ac  pop     rdi
0x1800082ad  retn
```
