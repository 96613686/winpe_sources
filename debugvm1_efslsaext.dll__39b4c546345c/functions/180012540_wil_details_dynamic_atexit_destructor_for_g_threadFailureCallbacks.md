# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180012540`
- end: `0x18001259e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012540`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012562`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012570`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012570`

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
0x180012540  mov     [rsp+arg_0], rbx
0x180012545  mov     [rsp+arg_8], rsi
0x18001254a  push    rdi
0x18001254b  sub     rsp, 20h
0x18001254f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180012556  mov     rsi, [rdi]
0x180012559  jmp     short loc_180012576
0x18001255b  mov     rbx, rsi
0x18001255e  mov     rsi, [rsi+8]
0x180012562  call    cs:__imp_GetProcessHeap
0x180012568  mov     r8, rbx; lpMem
0x18001256b  xor     edx, edx; dwFlags
0x18001256d  mov     rcx, rax; hHeap
0x180012570  call    cs:__imp_HeapFree
0x180012576  test    rsi, rsi
0x180012579  jnz     short loc_18001255B
0x18001257b  mov     [rdi], rsi
0x18001257e  lea     rax, g_header_init_InitializeResultHeader
0x180012585  add     rdi, 8
0x180012589  cmp     rdi, rax
0x18001258c  jnz     short loc_180012556
0x18001258e  mov     rbx, [rsp+28h+arg_0]
0x180012593  mov     rsi, [rsp+28h+arg_8]
0x180012598  add     rsp, 20h
0x18001259c  pop     rdi
0x18001259d  retn
```
