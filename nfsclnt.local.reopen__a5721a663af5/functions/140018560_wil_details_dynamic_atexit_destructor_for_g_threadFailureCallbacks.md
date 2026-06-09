# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140018560`
- end: `0x1400185be`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140018560`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140018590`
- `KERNEL32!HeapFree` at `0x140018590`
- `KERNEL32!GetProcessHeap` at `0x140018582`
- `KERNEL32!GetProcessHeap` at `0x140018582`

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
    result = g_header_init_InitializeStagingHeaderInternalApi;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x140018560  mov     [rsp+arg_0], rbx
0x140018565  mov     [rsp+arg_8], rsi
0x14001856a  push    rdi
0x14001856b  sub     rsp, 20h
0x14001856f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140018576  mov     rsi, [rdi]
0x140018579  jmp     short loc_140018596
0x14001857b  mov     rbx, rsi
0x14001857e  mov     rsi, [rsi+8]
0x140018582  call    cs:__imp_GetProcessHeap
0x140018588  mov     r8, rbx; lpMem
0x14001858b  xor     edx, edx; dwFlags
0x14001858d  mov     rcx, rax; hHeap
0x140018590  call    cs:__imp_HeapFree
0x140018596  test    rsi, rsi
0x140018599  jnz     short loc_14001857B
0x14001859b  mov     [rdi], rsi
0x14001859e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x1400185a5  add     rdi, 8
0x1400185a9  cmp     rdi, rax
0x1400185ac  jnz     short loc_140018576
0x1400185ae  mov     rbx, [rsp+28h+arg_0]
0x1400185b3  mov     rsi, [rsp+28h+arg_8]
0x1400185b8  add     rsp, 20h
0x1400185bc  pop     rdi
0x1400185bd  retn
```
