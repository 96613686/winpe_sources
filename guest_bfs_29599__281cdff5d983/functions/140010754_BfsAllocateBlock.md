# BfsAllocateBlock

- ea: `0x140010754`
- end: `0x1400107ba`
- name: `BfsAllocateBlock`
- size: `102`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140010cc8`
- `0x1400115f0`
- `0x140011ea8`

## callees

- `0x140010754`

## import_xrefs

- `ntoskrnl!RtlFindClearBits` at `0x140010774`
- `ntoskrnl!RtlFindClearBits` at `0x140010774`
- `ntoskrnl!RtlSetBits` at `0x140010799`
- `ntoskrnl!RtlSetBits` at `0x140010799`

## pseudocode

```c
__int64 __fastcall BfsAllocateBlock(__int64 a1, ULONG *a2)
{
  struct _RTL_BITMAP *v2; // rdi
  ULONG ClearBits; // eax
  ULONG v5; // ebx
  __int64 result; // rax

  v2 = (struct _RTL_BITMAP *)(a1 + 24);
  ClearBits = RtlFindClearBits((PRTL_BITMAP)(a1 + 24), 1u, 0);
  v5 = ClearBits;
  if ( ClearBits == -1 )
    return 2147483674LL;
  RtlSetBits(v2, ClearBits, 1u);
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x140010754  mov     [rsp+arg_0], rbx
0x140010759  mov     [rsp+arg_8], rsi
0x14001075e  push    rdi
0x14001075f  sub     rsp, 20h
0x140010763  xor     r8d, r8d; HintIndex
0x140010766  lea     rdi, [rcx+18h]
0x14001076a  mov     rsi, rdx
0x14001076d  mov     rcx, rdi; BitMapHeader
0x140010770  lea     edx, [r8+1]; NumberToFind
0x140010774  call    cs:__imp_RtlFindClearBits
0x14001077b  nop     dword ptr [rax+rax+00h]
0x140010780  mov     ebx, eax
0x140010782  cmp     eax, 0FFFFFFFFh
0x140010785  jnz     short loc_14001078E
0x140010787  mov     eax, 8000001Ah
0x14001078c  jmp     short loc_1400107A9
0x14001078e  mov     r8d, 1; NumberToSet
0x140010794  mov     edx, ebx; StartingIndex
0x140010796  mov     rcx, rdi; BitMapHeader
0x140010799  call    cs:__imp_RtlSetBits
0x1400107a0  nop     dword ptr [rax+rax+00h]
0x1400107a5  xor     eax, eax
0x1400107a7  mov     [rsi], ebx
0x1400107a9  mov     rbx, [rsp+28h+arg_0]
0x1400107ae  mov     rsi, [rsp+28h+arg_8]
0x1400107b3  add     rsp, 20h
0x1400107b7  pop     rdi
0x1400107b8  retn
```
