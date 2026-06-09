# CompareSockAddress

- ea: `0x1400020e0`
- end: `0x140002157`
- name: `CompareSockAddress`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011d04`
- `0x14001c2a4`

## callees

- `0x1400020e0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140002100`
- `ntoskrnl!RtlCompareMemory` at `0x140002135`
- `ntoskrnl!RtlCompareMemory` at `0x140002100`
- `ntoskrnl!RtlCompareMemory` at `0x140002135`

## pseudocode

```c
bool __fastcall CompareSockAddress(_WORD *a1, _WORD *a2)
{
  if ( *a1 != *a2 )
    return 0;
  if ( *a1 == 2 )
    return RtlCompareMemory(a1 + 2, a2 + 2, 4u) == 4;
  else
    return RtlCompareMemory(a1 + 4, a2 + 4, 0x10u) == 16;
}

```

## disassembly

```asm
0x1400020e0  sub     rsp, 28h
0x1400020e4  movzx   eax, word ptr [rcx]
0x1400020e7  cmp     ax, [rdx]
0x1400020ea  jnz     short loc_14000211C
0x1400020ec  cmp     ax, 2
0x1400020f0  jnz     short loc_140002120
0x1400020f2  add     rdx, 4; Source2
0x1400020f6  add     rcx, 4; Source1
0x1400020fa  mov     r8d, 4; Length
0x140002100  call    cs:__imp_RtlCompareMemory
0x140002107  nop     dword ptr [rax+rax+00h]
0x14000210c  cmp     rax, 4
0x140002110  setz    cl
0x140002113  movzx   eax, cl
0x140002116  add     rsp, 28h
0x14000211a  retn
0x14000211c  xor     al, al
0x14000211e  jmp     short loc_140002116
0x140002120  mov     [rsp+28h+var_8], rbx
0x140002125  add     rdx, 8; Source2
0x140002129  add     rcx, 8; Source1
0x14000212d  mov     r8d, 10h; Length
0x140002133  xor     bl, bl
0x140002135  call    cs:__imp_RtlCompareMemory
0x14000213c  nop     dword ptr [rax+rax+00h]
0x140002141  movzx   ecx, bl
0x140002144  mov     edx, 1
0x140002149  mov     rbx, [rsp+28h+var_8]
0x14000214e  cmp     rax, 10h
0x140002152  cmovz   ecx, edx
0x140002155  jmp     short loc_140002113
```
