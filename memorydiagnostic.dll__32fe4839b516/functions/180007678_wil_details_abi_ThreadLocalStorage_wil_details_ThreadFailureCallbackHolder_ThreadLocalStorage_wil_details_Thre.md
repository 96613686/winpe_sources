# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180007678`
- end: `0x1800076eb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023880`

## callees

- `0x180007678`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800076a4`
- `KERNEL32!GetProcessHeap` at `0x1800076a4`
- `KERNEL32!HeapFree` at `0x1800076b8`
- `KERNEL32!HeapFree` at `0x1800076b8`

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
0x180007678  mov     [rsp+arg_0], rbx
0x18000767d  mov     [rsp+arg_8], rbp
0x180007682  mov     [rsp+arg_10], rsi
0x180007687  push    rdi
0x180007688  sub     rsp, 20h
0x18000768c  lea     rbp, [rcx+50h]
0x180007690  mov     rdi, rcx
0x180007693  cmp     rcx, rbp
0x180007696  jz      short loc_1800076D5
0x180007698  mov     rsi, [rdi]
0x18000769b  jmp     short loc_1800076C4
0x18000769d  mov     rbx, rsi
0x1800076a0  mov     rsi, [rsi+8]
0x1800076a4  call    cs:__imp_GetProcessHeap
0x1800076ab  nop     dword ptr [rax+rax+00h]
0x1800076b0  mov     r8, rbx; lpMem
0x1800076b3  xor     edx, edx; dwFlags
0x1800076b5  mov     rcx, rax; hHeap
0x1800076b8  call    cs:__imp_HeapFree
0x1800076bf  nop     dword ptr [rax+rax+00h]
0x1800076c4  test    rsi, rsi
0x1800076c7  jnz     short loc_18000769D
0x1800076c9  mov     [rdi], rsi
0x1800076cc  add     rdi, 8
0x1800076d0  cmp     rdi, rbp
0x1800076d3  jnz     short loc_180007698
0x1800076d5  mov     rbx, [rsp+28h+arg_0]
0x1800076da  mov     rbp, [rsp+28h+arg_8]
0x1800076df  mov     rsi, [rsp+28h+arg_10]
0x1800076e4  add     rsp, 20h
0x1800076e8  pop     rdi
0x1800076e9  retn
```
