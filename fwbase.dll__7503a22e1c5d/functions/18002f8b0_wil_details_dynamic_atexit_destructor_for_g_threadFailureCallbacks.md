# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18002f8b0`
- end: `0x18002f917`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002f8b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f8f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f8e7`

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
  while ( v0 != &g_header_init_InitializeStagingHeaderInternalApi );
}

```

## disassembly

```asm
0x18002f8b0  push    rbx
0x18002f8b2  push    rbp
0x18002f8b3  push    rsi
0x18002f8b4  push    rdi
0x18002f8b5  push    r14
0x18002f8b7  sub     rsp, 20h
0x18002f8bb  lea     rsi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18002f8c2  xor     ebp, ebp
0x18002f8c4  lea     r14, g_header_init_InitializeStagingHeaderInternalApi
0x18002f8cb  nop     dword ptr [rax+rax+00h]
0x18002f8d0  mov     rbx, [rsi]
0x18002f8d3  test    rbx, rbx
0x18002f8d6  jz      short loc_18002F900
0x18002f8d8  nop     dword ptr [rax+rax+00000000h]
0x18002f8e0  mov     rdi, rbx
0x18002f8e3  mov     rbx, [rbx+8]
0x18002f8e7  call    cs:__imp_GetProcessHeap
0x18002f8ed  mov     r8, rdi; lpMem
0x18002f8f0  xor     edx, edx; dwFlags
0x18002f8f2  mov     rcx, rax; hHeap
0x18002f8f5  call    cs:__imp_HeapFree
0x18002f8fb  test    rbx, rbx
0x18002f8fe  jnz     short loc_18002F8E0
0x18002f900  mov     [rsi], rbp
0x18002f903  add     rsi, 8
0x18002f907  cmp     rsi, r14
0x18002f90a  jnz     short loc_18002F8D0
0x18002f90c  add     rsp, 20h
0x18002f910  pop     r14
0x18002f912  pop     rdi
0x18002f913  pop     rsi
0x18002f914  pop     rbp
0x18002f915  pop     rbx
0x18002f916  retn
```
