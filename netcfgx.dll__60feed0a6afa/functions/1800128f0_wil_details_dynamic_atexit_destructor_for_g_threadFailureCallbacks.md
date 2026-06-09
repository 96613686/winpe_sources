# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800128f0`
- end: `0x18001294e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800128f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012920`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012912`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012912`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    v0 += 8;
    result = &g_header_init_InitializeResultHeader;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x1800128f0  mov     [rsp+arg_0], rbx
0x1800128f5  mov     [rsp+arg_8], rsi
0x1800128fa  push    rdi
0x1800128fb  sub     rsp, 20h
0x1800128ff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180012906  mov     rsi, [rdi]
0x180012909  jmp     short loc_180012926
0x18001290b  mov     rbx, rsi
0x18001290e  mov     rsi, [rsi+8]
0x180012912  call    cs:__imp_GetProcessHeap
0x180012918  mov     rcx, rax; hHeap
0x18001291b  mov     r8, rbx; lpMem
0x18001291e  xor     edx, edx; dwFlags
0x180012920  call    cs:__imp_HeapFree
0x180012926  test    rsi, rsi
0x180012929  jnz     short loc_18001290B
0x18001292b  mov     [rdi], rsi
0x18001292e  add     rdi, 8
0x180012932  lea     rax, g_header_init_InitializeResultHeader
0x180012939  cmp     rdi, rax
0x18001293c  jnz     short loc_180012906
0x18001293e  mov     rbx, [rsp+28h+arg_0]
0x180012943  mov     rsi, [rsp+28h+arg_8]
0x180012948  add     rsp, 20h
0x18001294c  pop     rdi
0x18001294d  retn
```
