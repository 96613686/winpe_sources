# CompareSockAddress

- ea: `0x140001360`
- end: `0x1400013dc`
- name: `CompareSockAddress`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001f408`

## callees

- `0x140001360`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140001387`
- `ntoskrnl!RtlCompareMemory` at `0x1400013bf`
- `ntoskrnl!RtlCompareMemory` at `0x140001387`
- `ntoskrnl!RtlCompareMemory` at `0x1400013bf`

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
0x140001360  sub     rsp, 28h
0x140001364  movzx   eax, word ptr [rcx]
0x140001367  cmp     ax, [rdx]
0x14000136a  jnz     short loc_1400013A9
0x14000136c  mov     [rsp+28h+var_8], rbx
0x140001371  xor     bl, bl
0x140001373  cmp     ax, 2
0x140001377  jnz     short loc_1400013B1
0x140001379  add     rdx, 4; Source2
0x14000137d  add     rcx, 4; Source1
0x140001381  mov     r8d, 4; Length
0x140001387  call    cs:__imp_RtlCompareMemory
0x14000138e  nop     dword ptr [rax+rax+00h]
0x140001393  cmp     rax, 4
0x140001397  jnz     short loc_14000139B
0x140001399  mov     bl, 1
0x14000139b  movzx   eax, bl
0x14000139e  mov     rbx, [rsp+28h+var_8]
0x1400013a3  add     rsp, 28h
0x1400013a7  retn
0x1400013a9  xor     al, al
0x1400013ab  add     rsp, 28h
0x1400013af  retn
0x1400013b1  add     rdx, 8; Source2
0x1400013b5  add     rcx, 8; Source1
0x1400013b9  mov     r8d, 10h; Length
0x1400013bf  call    cs:__imp_RtlCompareMemory
0x1400013c6  nop     dword ptr [rax+rax+00h]
0x1400013cb  movzx   ebx, bl
0x1400013ce  mov     ecx, 1
0x1400013d3  cmp     rax, 10h
0x1400013d7  cmovz   ebx, ecx
0x1400013da  jmp     short loc_14000139B
```
