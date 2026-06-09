# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180088d40`
- end: `0x180088dac`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180088d40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180088d83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180088d83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088d6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088d6f`

## pseudocode

```c
void wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  char *v0; // rsi
  _QWORD *v1; // rbx
  void *v2; // rdi
  HANDLE ProcessHeap; // rax

  v0 = (char *)wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *(_QWORD **)v0;
    if ( *(_QWORD *)v0 )
    {
      do
      {
        v2 = v1;
        v1 = (_QWORD *)v1[1];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
      }
      while ( v1 );
    }
    *(_QWORD *)v0 = 0;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
}

```

## disassembly

```asm
0x180088d40  push    rbx
0x180088d42  push    rbp
0x180088d43  push    rsi
0x180088d44  push    rdi
0x180088d45  push    r14
0x180088d47  sub     rsp, 20h
0x180088d4b  lea     rsi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180088d52  xor     ebp, ebp
0x180088d54  lea     r14, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180088d5b  nop     dword ptr [rax+rax+00h]
0x180088d60  mov     rbx, [rsi]
0x180088d63  test    rbx, rbx
0x180088d66  jz      short loc_180088D94
0x180088d68  mov     rdi, rbx
0x180088d6b  mov     rbx, [rbx+8]
0x180088d6f  call    cs:__imp_GetProcessHeap
0x180088d76  nop     dword ptr [rax+rax+00h]
0x180088d7b  mov     r8, rdi; lpMem
0x180088d7e  xor     edx, edx; dwFlags
0x180088d80  mov     rcx, rax; hHeap
0x180088d83  call    cs:__imp_HeapFree
0x180088d8a  nop     dword ptr [rax+rax+00h]
0x180088d8f  test    rbx, rbx
0x180088d92  jnz     short loc_180088D68
0x180088d94  mov     [rsi], rbp
0x180088d97  add     rsi, 8
0x180088d9b  cmp     rsi, r14
0x180088d9e  jnz     short loc_180088D60
0x180088da0  add     rsp, 20h
0x180088da4  pop     r14
0x180088da6  pop     rdi
0x180088da7  pop     rsi
0x180088da8  pop     rbp
0x180088da9  pop     rbx
0x180088daa  retn
```
