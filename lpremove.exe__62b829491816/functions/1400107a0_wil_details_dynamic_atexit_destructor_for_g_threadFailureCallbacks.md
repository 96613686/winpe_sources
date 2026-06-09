# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400107a0`
- end: `0x1400107fe`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400107a0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400107c2`
- `KERNEL32!GetProcessHeap` at `0x1400107c2`
- `KERNEL32!HeapFree` at `0x1400107d0`
- `KERNEL32!HeapFree` at `0x1400107d0`

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
    result = &g_header_init_InitializeResultHeader;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x1400107a0  mov     [rsp+arg_0], rbx
0x1400107a5  mov     [rsp+arg_8], rsi
0x1400107aa  push    rdi
0x1400107ab  sub     rsp, 20h
0x1400107af  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1400107b6  mov     rsi, [rdi]
0x1400107b9  jmp     short loc_1400107D6
0x1400107bb  mov     rbx, rsi
0x1400107be  mov     rsi, [rsi+8]
0x1400107c2  call    cs:__imp_GetProcessHeap
0x1400107c8  mov     r8, rbx; lpMem
0x1400107cb  xor     edx, edx; dwFlags
0x1400107cd  mov     rcx, rax; hHeap
0x1400107d0  call    cs:__imp_HeapFree
0x1400107d6  test    rsi, rsi
0x1400107d9  jnz     short loc_1400107BB
0x1400107db  mov     [rdi], rsi
0x1400107de  lea     rax, g_header_init_InitializeResultHeader
0x1400107e5  add     rdi, 8
0x1400107e9  cmp     rdi, rax
0x1400107ec  jnz     short loc_1400107B6
0x1400107ee  mov     rbx, [rsp+28h+arg_0]
0x1400107f3  mov     rsi, [rsp+28h+arg_8]
0x1400107f8  add     rsp, 20h
0x1400107fc  pop     rdi
0x1400107fd  retn
```
