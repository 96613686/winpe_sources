# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180006470`
- end: `0x1800064cc`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004820`

## callees

- `0x180006470`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006491`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006491`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064a5`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180006470  push    rbx
0x180006472  push    rbp
0x180006473  push    rsi
0x180006474  push    rdi
0x180006475  sub     rsp, 28h
0x180006479  lea     rbp, [rcx+50h]
0x18000647d  mov     rdi, rcx
0x180006480  cmp     rcx, rbp
0x180006483  jz      short loc_1800064C2
0x180006485  mov     rsi, [rdi]
0x180006488  jmp     short loc_1800064B1
0x18000648a  mov     rbx, rsi
0x18000648d  mov     rsi, [rsi+8]
0x180006491  call    cs:__imp_GetProcessHeap
0x180006498  nop     dword ptr [rax+rax+00h]
0x18000649d  mov     r8, rbx; lpMem
0x1800064a0  xor     edx, edx; dwFlags
0x1800064a2  mov     rcx, rax; hHeap
0x1800064a5  call    cs:__imp_HeapFree
0x1800064ac  nop     dword ptr [rax+rax+00h]
0x1800064b1  test    rsi, rsi
0x1800064b4  jnz     short loc_18000648A
0x1800064b6  mov     [rdi], rsi
0x1800064b9  add     rdi, 8
0x1800064bd  cmp     rdi, rbp
0x1800064c0  jnz     short loc_180006485
0x1800064c2  add     rsp, 28h
0x1800064c6  pop     rdi
0x1800064c7  pop     rsi
0x1800064c8  pop     rbp
0x1800064c9  pop     rbx
0x1800064ca  retn
```
