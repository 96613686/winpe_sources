# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000f850`
- end: `0x14000f8ae`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000f850`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000f872`
- `KERNEL32!GetProcessHeap` at `0x14000f872`
- `KERNEL32!HeapFree` at `0x14000f880`
- `KERNEL32!HeapFree` at `0x14000f880`

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
0x14000f850  mov     [rsp+arg_0], rbx
0x14000f855  mov     [rsp+arg_8], rsi
0x14000f85a  push    rdi
0x14000f85b  sub     rsp, 20h
0x14000f85f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000f866  mov     rsi, [rdi]
0x14000f869  jmp     short loc_14000F886
0x14000f86b  mov     rbx, rsi
0x14000f86e  mov     rsi, [rsi+8]
0x14000f872  call    cs:__imp_GetProcessHeap
0x14000f878  mov     r8, rbx; lpMem
0x14000f87b  xor     edx, edx; dwFlags
0x14000f87d  mov     rcx, rax; hHeap
0x14000f880  call    cs:__imp_HeapFree
0x14000f886  test    rsi, rsi
0x14000f889  jnz     short loc_14000F86B
0x14000f88b  mov     [rdi], rsi
0x14000f88e  lea     rax, g_header_init_InitializeResultHeader
0x14000f895  add     rdi, 8
0x14000f899  cmp     rdi, rax
0x14000f89c  jnz     short loc_14000F866
0x14000f89e  mov     rbx, [rsp+28h+arg_0]
0x14000f8a3  mov     rsi, [rsp+28h+arg_8]
0x14000f8a8  add     rsp, 20h
0x14000f8ac  pop     rdi
0x14000f8ad  retn
```
