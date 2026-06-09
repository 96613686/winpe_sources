# ComputeEventEntryHash

- ea: `0x18001877c`
- end: `0x180018813`
- name: `ComputeEventEntryHash`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800184c8`

## callees

- `0x18001877c`

## pseudocode

```c
__int64 __fastcall ComputeEventEntryHash(char a1, unsigned __int8 a2, __int64 a3)
{
  unsigned int v3; // r10d
  unsigned __int64 i; // rcx
  int v7; // eax
  unsigned __int8 j; // r11
  unsigned __int64 k; // rdx
  int v10; // eax

  v3 = 0;
  for ( i = 0; i < 8; ++i )
  {
    v7 = *(unsigned __int8 *)(a3 + i + 16);
    v3 = (1025 * (v3 + v7)) ^ ((1025 * (v3 + v7)) >> 6);
  }
  for ( j = a1 + 2; j < a2; ++j )
  {
    for ( k = 0; k < *(unsigned int *)(a3 + 16LL * j + 8); v3 = (1025 * (v3 + v10)) ^ ((1025 * (v3 + v10)) >> 6) )
      v10 = *(unsigned __int8 *)(*(_QWORD *)(a3 + 16LL * j) + k++);
  }
  return 32769 * ((9 * v3) ^ ((9 * v3) >> 11));
}

```

## disassembly

```asm
0x18001877c  mov     [rsp+arg_0], rbx
0x180018781  mov     [rsp+arg_8], rdi
0x180018786  xor     r10d, r10d
0x180018789  mov     r11b, cl
0x18001878c  xor     ecx, ecx
0x18001878e  mov     bl, dl
0x180018790  movzx   eax, byte ptr [r8+rcx+10h]
0x180018796  inc     rcx
0x180018799  add     eax, r10d
0x18001879c  imul    r9d, eax, 401h
0x1800187a3  mov     r10d, r9d
0x1800187a6  shr     r10d, 6
0x1800187aa  xor     r10d, r9d
0x1800187ad  cmp     rcx, 8
0x1800187b1  jb      short loc_180018790
0x1800187b3  add     r11b, 2
0x1800187b7  jmp     short loc_1800187F2
0x1800187b9  movzx   eax, r11b
0x1800187bd  xor     edx, edx
0x1800187bf  add     rax, rax
0x1800187c2  mov     r9d, [r8+rax*8+8]
0x1800187c7  mov     rdi, [r8+rax*8]
0x1800187cb  test    r9, r9
0x1800187ce  jz      short loc_1800187EF
0x1800187d0  movzx   eax, byte ptr [rdi+rdx]
0x1800187d4  inc     rdx
0x1800187d7  add     eax, r10d
0x1800187da  imul    ecx, eax, 401h
0x1800187e0  mov     r10d, ecx
0x1800187e3  shr     r10d, 6
0x1800187e7  xor     r10d, ecx
0x1800187ea  cmp     rdx, r9
0x1800187ed  jb      short loc_1800187D0
0x1800187ef  inc     r11b
0x1800187f2  cmp     r11b, bl
0x1800187f5  jb      short loc_1800187B9
0x1800187f7  mov     rbx, [rsp+arg_0]
0x1800187fc  lea     eax, [r10+r10*8]
0x180018800  mov     rdi, [rsp+arg_8]
0x180018805  mov     ecx, eax
0x180018807  shr     ecx, 0Bh
0x18001880a  xor     ecx, eax
0x18001880c  imul    eax, ecx, 8001h
0x180018812  retn
```
