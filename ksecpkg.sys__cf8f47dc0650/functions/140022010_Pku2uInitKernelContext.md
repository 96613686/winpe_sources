# Pku2uInitKernelContext

- ea: `0x140022010`
- end: `0x1400220b3`
- name: `Pku2uInitKernelContext`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007008`
- `0x140022010`
- `0x1400299f8`
- `0x140029d94`

## string_xrefs

- `0x14002207d`: `Failed to create kernel mode context: 0x%x\n`

## pseudocode

```c
__int64 __fastcall Pku2uInitKernelContext(int a1, int a2, PVOID *a3)
{
  int KernelModeContext; // eax
  PVOID v7; // rbx
  unsigned int v8; // edi
  PVOID P; // [rsp+58h] [rbp+20h] BYREF

  P = 0;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uInitKernelContext called\n");
  KernelModeContext = Pku2uCreateKernelModeContext(a1, a2, (unsigned int)&P, 0, 0);
  v7 = P;
  v8 = KernelModeContext;
  if ( KernelModeContext >= 0 )
  {
    *a3 = P;
  }
  else if ( KsecInfoLevel )
  {
    KsecDebugOut(1, "Failed to create kernel mode context: 0x%x\n", KernelModeContext);
  }
  if ( v7 )
    Pku2uDereferenceContext(v7);
  return v8;
}

```

## disassembly

```asm
0x140022010  mov     [rsp+arg_0], rbx
0x140022015  mov     [rsp+arg_8], rsi
0x14002201a  push    rdi
0x14002201b  sub     rsp, 30h
0x14002201f  cmp     cs:KsecInfoLevel, 0
0x140022026  mov     rsi, r8
0x140022029  mov     rbx, rdx
0x14002202c  mov     [rsp+38h+P], 0
0x140022035  mov     rdi, rcx
0x140022038  jz      short loc_14002204B
0x14002203a  lea     rdx, aPku2uinitkerne; "Pku2uInitKernelContext called\n"
0x140022041  mov     ecx, 4
0x140022046  call    KsecDebugOut
0x14002204b  xor     r9d, r9d
0x14002204e  mov     [rsp+38h+var_18], 0
0x140022056  lea     r8, [rsp+38h+P]
0x14002205b  mov     rdx, rbx
0x14002205e  mov     rcx, rdi
0x140022061  call    Pku2uCreateKernelModeContext
0x140022066  mov     rbx, [rsp+38h+P]
0x14002206b  mov     edi, eax
0x14002206d  test    eax, eax
0x14002206f  jns     short loc_140022090
0x140022071  cmp     cs:KsecInfoLevel, 0
0x140022078  jz      short loc_140022093
0x14002207a  mov     r8d, eax
0x14002207d  lea     rdx, aFailedToCreate_0; "Failed to create kernel mode context: 0"...
0x140022084  mov     ecx, 1
0x140022089  call    KsecDebugOut
0x14002208e  jmp     short loc_140022093
0x140022090  mov     [rsi], rbx
0x140022093  test    rbx, rbx
0x140022096  jz      short loc_1400220A0
0x140022098  mov     rcx, rbx; P
0x14002209b  call    Pku2uDereferenceContext
0x1400220a0  mov     rbx, [rsp+38h+arg_0]
0x1400220a5  mov     eax, edi
0x1400220a7  mov     rsi, [rsp+38h+arg_8]
0x1400220ac  add     rsp, 30h
0x1400220b0  pop     rdi
0x1400220b1  retn
```
