# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180013230`
- end: `0x18001328e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013230`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180013260`
- `KERNEL32!HeapFree` at `0x180013260`
- `KERNEL32!GetProcessHeap` at `0x180013252`
- `KERNEL32!GetProcessHeap` at `0x180013252`

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
0x180013230  mov     [rsp+arg_0], rbx
0x180013235  mov     [rsp+arg_8], rsi
0x18001323a  push    rdi
0x18001323b  sub     rsp, 20h
0x18001323f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180013246  mov     rsi, [rdi]
0x180013249  jmp     short loc_180013266
0x18001324b  mov     rbx, rsi
0x18001324e  mov     rsi, [rsi+8]
0x180013252  call    cs:__imp_GetProcessHeap
0x180013258  mov     r8, rbx; lpMem
0x18001325b  xor     edx, edx; dwFlags
0x18001325d  mov     rcx, rax; hHeap
0x180013260  call    cs:__imp_HeapFree
0x180013266  test    rsi, rsi
0x180013269  jnz     short loc_18001324B
0x18001326b  mov     [rdi], rsi
0x18001326e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180013275  add     rdi, 8
0x180013279  cmp     rdi, rax
0x18001327c  jnz     short loc_180013246
0x18001327e  mov     rbx, [rsp+28h+arg_0]
0x180013283  mov     rsi, [rsp+28h+arg_8]
0x180013288  add     rsp, 20h
0x18001328c  pop     rdi
0x18001328d  retn
```
