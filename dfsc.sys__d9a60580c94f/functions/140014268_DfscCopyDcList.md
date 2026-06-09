# DfscCopyDcList

- ea: `0x140014268`
- end: `0x140014336`
- name: `DfscCopyDcList`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140021e28`
- `0x140022b60`

## callees

- `0x14000328c`
- `0x140006080`
- `0x140014268`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140014292`
- `ntoskrnl!ExAllocatePool2` at `0x140014292`

## pseudocode

```c
__int64 __fastcall DfscCopyDcList(__int64 a1, __int64 a2)
{
  void *Pool2; // rax
  __int64 v6; // rdx
  __int64 v7; // r9

  if ( *(_QWORD *)(a2 + 48) )
  {
    Pool2 = (void *)ExAllocatePool2(258, *(unsigned __int16 *)(a2 + 64), 1816356420);
    *(_QWORD *)(a1 + 48) = Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    *(_WORD *)(a1 + 64) = *(_WORD *)(a2 + 64);
    memmove(Pool2, *(const void **)(a2 + 48), *(unsigned __int16 *)(a2 + 64));
    v6 = *(_QWORD *)(a1 + 48);
    v7 = v6 + 2 * ((unsigned __int64)((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)(a2 + 48)) >> 1) >> 1);
    *(_QWORD *)(a1 + 8) = v7;
    *(_QWORD *)(a1 + 56) = v6
                         + 2 * ((unsigned __int64)((__int64)(*(_QWORD *)(a2 + 56) - *(_QWORD *)(a2 + 48)) >> 1) >> 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids, v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140014268  mov     [rsp+arg_0], rbx
0x14001426d  push    rdi
0x14001426e  sub     rsp, 20h
0x140014272  cmp     qword ptr [rdx+30h], 0
0x140014277  mov     rbx, rdx
0x14001427a  mov     rdi, rcx
0x14001427d  jz      loc_140014328
0x140014283  movzx   edx, word ptr [rdx+40h]
0x140014287  mov     ecx, 102h
0x14001428c  mov     r8d, 6C436644h
0x140014292  call    cs:__imp_ExAllocatePool2
0x140014299  nop     dword ptr [rax+rax+00h]
0x14001429e  mov     [rdi+30h], rax
0x1400142a2  mov     rcx, rax; void *
0x1400142a5  test    rax, rax
0x1400142a8  jnz     short loc_1400142B1
0x1400142aa  mov     eax, 0C000009Ah
0x1400142af  jmp     short loc_14001432A
0x1400142b1  movzx   eax, word ptr [rbx+40h]
0x1400142b5  mov     [rdi+40h], ax
0x1400142b9  movzx   r8d, word ptr [rbx+40h]; Size
0x1400142be  mov     rdx, [rbx+30h]; Src
0x1400142c2  call    memmove
0x1400142c7  mov     rcx, [rbx+8]
0x1400142cb  sub     rcx, [rbx+30h]
0x1400142cf  mov     rdx, [rdi+30h]
0x1400142d3  sar     rcx, 1
0x1400142d6  shr     rcx, 1
0x1400142d9  lea     r9, [rdx+rcx*2]
0x1400142dd  mov     [rdi+8], r9
0x1400142e1  mov     rcx, [rbx+38h]
0x1400142e5  sub     rcx, [rbx+30h]
0x1400142e9  sar     rcx, 1
0x1400142ec  shr     rcx, 1
0x1400142ef  lea     rax, [rdx+rcx*2]
0x1400142f3  mov     [rdi+38h], rax
0x1400142f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400142fe  lea     rax, WPP_GLOBAL_Control
0x140014305  cmp     rcx, rax
0x140014308  jz      short loc_140014328
0x14001430a  test    dword ptr [rcx+2Ch], 400000h
0x140014311  jz      short loc_140014328
0x140014313  mov     rcx, [rcx+18h]
0x140014317  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x14001431e  mov     edx, 0Ah
0x140014323  call    WPP_SF_S
0x140014328  xor     eax, eax
0x14001432a  mov     rbx, [rsp+28h+arg_0]
0x14001432f  add     rsp, 20h
0x140014333  pop     rdi
0x140014334  retn
```
