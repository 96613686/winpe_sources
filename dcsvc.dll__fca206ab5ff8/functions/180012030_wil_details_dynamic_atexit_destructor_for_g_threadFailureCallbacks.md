# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180012030`
- end: `0x18001208e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012030`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012052`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012052`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012060`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012060`

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
0x180012030  mov     [rsp+arg_0], rbx
0x180012035  mov     [rsp+arg_8], rsi
0x18001203a  push    rdi
0x18001203b  sub     rsp, 20h
0x18001203f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180012046  mov     rsi, [rdi]
0x180012049  jmp     short loc_180012066
0x18001204b  mov     rbx, rsi
0x18001204e  mov     rsi, [rsi+8]
0x180012052  call    cs:__imp_GetProcessHeap
0x180012058  mov     r8, rbx; lpMem
0x18001205b  xor     edx, edx; dwFlags
0x18001205d  mov     rcx, rax; hHeap
0x180012060  call    cs:__imp_HeapFree
0x180012066  test    rsi, rsi
0x180012069  jnz     short loc_18001204B
0x18001206b  mov     [rdi], rsi
0x18001206e  lea     rax, g_header_init_InitializeResultHeader
0x180012075  add     rdi, 8
0x180012079  cmp     rdi, rax
0x18001207c  jnz     short loc_180012046
0x18001207e  mov     rbx, [rsp+28h+arg_0]
0x180012083  mov     rsi, [rsp+28h+arg_8]
0x180012088  add     rsp, 20h
0x18001208c  pop     rdi
0x18001208d  retn
```
