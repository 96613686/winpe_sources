# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000c070`
- end: `0x18000c0ce`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c092`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c092`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0a0`

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
0x18000c070  mov     [rsp+arg_0], rbx
0x18000c075  mov     [rsp+arg_8], rsi
0x18000c07a  push    rdi
0x18000c07b  sub     rsp, 20h
0x18000c07f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000c086  mov     rsi, [rdi]
0x18000c089  jmp     short loc_18000C0A6
0x18000c08b  mov     rbx, rsi
0x18000c08e  mov     rsi, [rsi+8]
0x18000c092  call    cs:__imp_GetProcessHeap
0x18000c098  mov     r8, rbx; lpMem
0x18000c09b  xor     edx, edx; dwFlags
0x18000c09d  mov     rcx, rax; hHeap
0x18000c0a0  call    cs:__imp_HeapFree
0x18000c0a6  test    rsi, rsi
0x18000c0a9  jnz     short loc_18000C08B
0x18000c0ab  mov     [rdi], rsi
0x18000c0ae  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000c0b5  add     rdi, 8
0x18000c0b9  cmp     rdi, rax
0x18000c0bc  jnz     short loc_18000C086
0x18000c0be  mov     rbx, [rsp+28h+arg_0]
0x18000c0c3  mov     rsi, [rsp+28h+arg_8]
0x18000c0c8  add     rsp, 20h
0x18000c0cc  pop     rdi
0x18000c0cd  retn
```
