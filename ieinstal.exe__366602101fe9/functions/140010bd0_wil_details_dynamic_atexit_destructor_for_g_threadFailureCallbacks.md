# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140010bd0`
- end: `0x140010c3b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010bd0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140010bf2`
- `KERNEL32!GetProcessHeap` at `0x140010bf2`
- `KERNEL32!HeapFree` at `0x140010c06`
- `KERNEL32!HeapFree` at `0x140010c06`

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
    result = qword_140017150;
    ++v0;
  }
  while ( v0 != qword_140017150 );
  return result;
}

```

## disassembly

```asm
0x140010bd0  mov     [rsp+arg_0], rbx
0x140010bd5  mov     [rsp+arg_8], rsi
0x140010bda  push    rdi
0x140010bdb  sub     rsp, 20h
0x140010bdf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140010be6  mov     rsi, [rdi]
0x140010be9  jmp     short loc_140010C12
0x140010beb  mov     rbx, rsi
0x140010bee  mov     rsi, [rsi+8]
0x140010bf2  call    cs:__imp_GetProcessHeap
0x140010bf9  nop     dword ptr [rax+rax+00h]
0x140010bfe  mov     r8, rbx; lpMem
0x140010c01  xor     edx, edx; dwFlags
0x140010c03  mov     rcx, rax; hHeap
0x140010c06  call    cs:__imp_HeapFree
0x140010c0d  nop     dword ptr [rax+rax+00h]
0x140010c12  test    rsi, rsi
0x140010c15  jnz     short loc_140010BEB
0x140010c17  mov     [rdi], rsi
0x140010c1a  lea     rax, qword_140017150
0x140010c21  add     rdi, 8
0x140010c25  cmp     rdi, rax
0x140010c28  jnz     short loc_140010BE6
0x140010c2a  mov     rbx, [rsp+28h+arg_0]
0x140010c2f  mov     rsi, [rsp+28h+arg_8]
0x140010c34  add     rsp, 20h
0x140010c38  pop     rdi
0x140010c39  retn
```
