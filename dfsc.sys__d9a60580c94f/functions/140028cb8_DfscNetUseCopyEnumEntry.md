# DfscNetUseCopyEnumEntry

- ea: `0x140028cb8`
- end: `0x140028d98`
- name: `DfscNetUseCopyEnumEntry`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140017a64`

## callees

- `0x140006080`
- `0x140028cb8`

## import_xrefs

- `ntoskrnl!towupper` at `0x140028cf6`
- `ntoskrnl!towupper` at `0x140028cf6`

## pseudocode

```c
__int64 __fastcall DfscNetUseCopyEnumEntry(__int64 a1, __int64 a2, unsigned int a3, int *a4)
{
  unsigned int v4; // ebp
  unsigned __int64 v5; // rbx
  wint_t *v6; // rdi
  int v10; // eax
  size_t v11; // r15
  unsigned int v12; // ebx
  int v13; // r8d
  __int64 v14; // r8

  v4 = 12;
  v5 = a3;
  v6 = (wint_t *)(a1 + 104);
  if ( a3 < 0xC )
    goto LABEL_7;
  if ( *v6 )
  {
    v4 = 18;
    if ( a3 < 0x12 )
      goto LABEL_7;
    *(_WORD *)(a2 + 12) = towupper(*v6);
    v10 = 6;
    *(_DWORD *)(a2 + 14) = 58;
  }
  else
  {
    v10 = 0;
  }
  *(_DWORD *)(a2 + 4) = v10;
  v11 = *(unsigned __int16 *)(a1 + 88);
  if ( v4 + v11 + 4 <= v5 )
  {
    *(_WORD *)(v4 + a2) = 92;
    v12 = 0;
    memmove((void *)(v4 + a2 + 2), *(const void **)(a1 + 96), v11);
    v14 = v4 + (_DWORD)v11 + 2;
    *(_WORD *)(v14 + a2) = 0;
    *(_DWORD *)(a2 + 8) = v11 + 4;
    v13 = v14 + 2;
    goto LABEL_9;
  }
LABEL_7:
  v12 = -2147483643;
  v13 = (*v6 != 0 ? 22 : 16) + *(unsigned __int16 *)(a1 + 88);
LABEL_9:
  *a4 = v13;
  return v12;
}

```

## disassembly

```asm
0x140028cb8  push    rbx
0x140028cba  push    rbp
0x140028cbb  push    rsi
0x140028cbc  push    rdi
0x140028cbd  push    r12
0x140028cbf  push    r13
0x140028cc1  push    r14
0x140028cc3  push    r15
0x140028cc5  sub     rsp, 28h
0x140028cc9  mov     ebp, 0Ch
0x140028cce  mov     ebx, r8d
0x140028cd1  lea     rdi, [rcx+68h]
0x140028cd5  mov     r12, r9
0x140028cd8  mov     r14, rdx
0x140028cdb  mov     rsi, rcx
0x140028cde  cmp     r8d, ebp
0x140028ce1  jb      short loc_140028D2E
0x140028ce3  movzx   ecx, word ptr [rdi]; C
0x140028ce6  xor     r13d, r13d
0x140028ce9  test    cx, cx
0x140028cec  jz      short loc_140028D14
0x140028cee  lea     ebp, [r13+12h]
0x140028cf2  cmp     ebx, ebp
0x140028cf4  jb      short loc_140028D2E
0x140028cf6  call    cs:__imp_towupper
0x140028cfd  nop     dword ptr [rax+rax+00h]
0x140028d02  mov     [r14+0Ch], ax
0x140028d07  lea     eax, [rbp-0Ch]
0x140028d0a  mov     dword ptr [r14+0Eh], 3Ah ; ':'
0x140028d12  jmp     short loc_140028D17
0x140028d14  mov     eax, r13d
0x140028d17  mov     [r14+4], eax
0x140028d1b  movzx   r15d, word ptr [rsi+58h]
0x140028d20  mov     edx, ebp
0x140028d22  lea     rcx, [r15+4]
0x140028d26  add     rcx, rdx
0x140028d29  cmp     rcx, rbx
0x140028d2c  jbe     short loc_140028D4B
0x140028d2e  movzx   eax, word ptr [rdi]
0x140028d31  mov     ebx, 80000005h
0x140028d36  movzx   r8d, word ptr [rsi+58h]
0x140028d3b  neg     ax
0x140028d3e  sbb     ecx, ecx
0x140028d40  and     ecx, 6
0x140028d43  add     ecx, 10h
0x140028d46  add     r8d, ecx
0x140028d49  jmp     short loc_140028D80
0x140028d4b  mov     word ptr [rdx+r14], 5Ch ; '\'
0x140028d52  lea     rcx, [r14+2]
0x140028d56  add     rcx, rdx; void *
0x140028d59  mov     r8, r15; Size
0x140028d5c  mov     rdx, [rsi+60h]; Src
0x140028d60  mov     ebx, r13d
0x140028d63  call    memmove
0x140028d68  lea     r8d, [r15+2]
0x140028d6c  add     r8d, ebp
0x140028d6f  lea     ecx, [r15+4]
0x140028d73  mov     [r8+r14], r13w
0x140028d78  mov     [r14+8], ecx
0x140028d7c  add     r8d, 2
0x140028d80  mov     [r12], r8d
0x140028d84  mov     eax, ebx
0x140028d86  add     rsp, 28h
0x140028d8a  pop     r15
0x140028d8c  pop     r14
0x140028d8e  pop     r13
0x140028d90  pop     r12
0x140028d92  pop     rdi
0x140028d93  pop     rsi
0x140028d94  pop     rbp
0x140028d95  pop     rbx
0x140028d96  retn
```
