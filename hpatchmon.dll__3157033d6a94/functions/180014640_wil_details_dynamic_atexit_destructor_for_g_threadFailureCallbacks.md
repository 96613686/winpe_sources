# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180014640`
- end: `0x18001469e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014640`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014670`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014670`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014662`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014662`

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
0x180014640  mov     [rsp+arg_0], rbx
0x180014645  mov     [rsp+arg_8], rsi
0x18001464a  push    rdi
0x18001464b  sub     rsp, 20h
0x18001464f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180014656  mov     rsi, [rdi]
0x180014659  jmp     short loc_180014676
0x18001465b  mov     rbx, rsi
0x18001465e  mov     rsi, [rsi+8]
0x180014662  call    cs:__imp_GetProcessHeap
0x180014668  mov     r8, rbx; lpMem
0x18001466b  xor     edx, edx; dwFlags
0x18001466d  mov     rcx, rax; hHeap
0x180014670  call    cs:__imp_HeapFree
0x180014676  test    rsi, rsi
0x180014679  jnz     short loc_18001465B
0x18001467b  mov     [rdi], rsi
0x18001467e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180014685  add     rdi, 8
0x180014689  cmp     rdi, rax
0x18001468c  jnz     short loc_180014656
0x18001468e  mov     rbx, [rsp+28h+arg_0]
0x180014693  mov     rsi, [rsp+28h+arg_8]
0x180014698  add     rsp, 20h
0x18001469c  pop     rdi
0x18001469d  retn
```
