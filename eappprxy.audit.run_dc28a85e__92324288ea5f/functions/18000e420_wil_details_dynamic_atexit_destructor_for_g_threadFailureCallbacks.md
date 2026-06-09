# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000e420`
- end: `0x18000e48b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e420`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e442`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e442`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e456`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e456`

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
0x18000e420  mov     [rsp+arg_0], rbx
0x18000e425  mov     [rsp+arg_8], rsi
0x18000e42a  push    rdi
0x18000e42b  sub     rsp, 20h
0x18000e42f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000e436  mov     rsi, [rdi]
0x18000e439  jmp     short loc_18000E462
0x18000e43b  mov     rbx, rsi
0x18000e43e  mov     rsi, [rsi+8]
0x18000e442  call    cs:__imp_GetProcessHeap
0x18000e449  nop     dword ptr [rax+rax+00h]
0x18000e44e  mov     r8, rbx; lpMem
0x18000e451  xor     edx, edx; dwFlags
0x18000e453  mov     rcx, rax; hHeap
0x18000e456  call    cs:__imp_HeapFree
0x18000e45d  nop     dword ptr [rax+rax+00h]
0x18000e462  test    rsi, rsi
0x18000e465  jnz     short loc_18000E43B
0x18000e467  mov     [rdi], rsi
0x18000e46a  lea     rax, g_header_init_InitializeResultHeader
0x18000e471  add     rdi, 8
0x18000e475  cmp     rdi, rax
0x18000e478  jnz     short loc_18000E436
0x18000e47a  mov     rbx, [rsp+28h+arg_0]
0x18000e47f  mov     rsi, [rsp+28h+arg_8]
0x18000e484  add     rsp, 20h
0x18000e488  pop     rdi
0x18000e489  retn
```
