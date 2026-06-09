# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800160c0`
- end: `0x18001611e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800160c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800160f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800160f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160e2`

## pseudocode

```c
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
    result = &g_header_init_InitializeStagingHeaderInternalApi;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x1800160c0  mov     [rsp+arg_0], rbx
0x1800160c5  mov     [rsp+arg_8], rsi
0x1800160ca  push    rdi
0x1800160cb  sub     rsp, 20h
0x1800160cf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800160d6  mov     rsi, [rdi]
0x1800160d9  jmp     short loc_1800160F6
0x1800160db  mov     rbx, rsi
0x1800160de  mov     rsi, [rsi+8]
0x1800160e2  call    cs:__imp_GetProcessHeap
0x1800160e8  mov     r8, rbx; lpMem
0x1800160eb  xor     edx, edx; dwFlags
0x1800160ed  mov     rcx, rax; hHeap
0x1800160f0  call    cs:__imp_HeapFree
0x1800160f6  test    rsi, rsi
0x1800160f9  jnz     short loc_1800160DB
0x1800160fb  mov     [rdi], rsi
0x1800160fe  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180016105  add     rdi, 8
0x180016109  cmp     rdi, rax
0x18001610c  jnz     short loc_1800160D6
0x18001610e  mov     rbx, [rsp+28h+arg_0]
0x180016113  mov     rsi, [rsp+28h+arg_8]
0x180016118  add     rsp, 20h
0x18001611c  pop     rdi
0x18001611d  retn
```
