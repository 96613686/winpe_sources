# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140004e80`
- end: `0x140004ede`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004eb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004eb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ea2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ea2`

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
    result = qword_140008130;
    ++v0;
  }
  while ( v0 != qword_140008130 );
  return result;
}

```

## disassembly

```asm
0x140004e80  mov     [rsp+arg_0], rbx
0x140004e85  mov     [rsp+arg_8], rsi
0x140004e8a  push    rdi
0x140004e8b  sub     rsp, 20h
0x140004e8f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140004e96  mov     rsi, [rdi]
0x140004e99  jmp     short loc_140004EB6
0x140004e9b  mov     rbx, rsi
0x140004e9e  mov     rsi, [rsi+8]
0x140004ea2  call    cs:__imp_GetProcessHeap
0x140004ea8  mov     r8, rbx; lpMem
0x140004eab  xor     edx, edx; dwFlags
0x140004ead  mov     rcx, rax; hHeap
0x140004eb0  call    cs:__imp_HeapFree
0x140004eb6  test    rsi, rsi
0x140004eb9  jnz     short loc_140004E9B
0x140004ebb  mov     [rdi], rsi
0x140004ebe  lea     rax, qword_140008130
0x140004ec5  add     rdi, 8
0x140004ec9  cmp     rdi, rax
0x140004ecc  jnz     short loc_140004E96
0x140004ece  mov     rbx, [rsp+28h+arg_0]
0x140004ed3  mov     rsi, [rsp+28h+arg_8]
0x140004ed8  add     rsp, 20h
0x140004edc  pop     rdi
0x140004edd  retn
```
