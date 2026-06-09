# FCpConstructFullPath

- ea: `0x14000f880`
- end: `0x14000f953`
- name: `FCpConstructFullPath`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f2f0`

## callees

- `0x140003b80`
- `0x14000f880`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f8ca`
- `ntoskrnl!ExAllocatePool2` at `0x14000f8ca`

## pseudocode

```c
__int64 __fastcall FCpConstructFullPath(__int64 a1, __int64 a2)
{
  __int16 v2; // ax
  char v5; // bp
  unsigned __int16 v6; // bx
  char *Pool2; // rax
  char *v8; // rdi
  char *v9; // rdi
  char *v10; // rcx
  __int64 result; // rax

  v2 = *(_WORD *)(a1 + 88);
  v5 = 1;
  v6 = *(_WORD *)(a1 + 104) + v2 + 2;
  if ( v2 && *(_WORD *)(*(_QWORD *)(a1 + 96) + 2 * ((unsigned __int64)*(unsigned __int16 *)(a1 + 88) >> 1) - 2) != 92 )
  {
    v6 += 2;
    v5 = 0;
  }
  Pool2 = (char *)ExAllocatePool2(256, v6, 1718502214);
  v8 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_QWORD *)(a2 + 8) = Pool2;
  *(_WORD *)a2 = 0;
  *(_WORD *)(a2 + 2) = v6;
  memmove(Pool2, *(const void **)(a1 + 112), *(unsigned __int16 *)(a1 + 104));
  v9 = &v8[2 * ((unsigned __int64)*(unsigned __int16 *)(a1 + 104) >> 1)];
  memmove(v9, *(const void **)(a1 + 96), *(unsigned __int16 *)(a1 + 88));
  v10 = &v9[2 * ((unsigned __int64)*(unsigned __int16 *)(a1 + 88) >> 1)];
  if ( !v5 )
  {
    *(_WORD *)v10 = 92;
    v10 += 2;
  }
  result = 0;
  *(_WORD *)v10 = 0;
  *(_WORD *)a2 = v6 - 2;
  return result;
}

```

## disassembly

```asm
0x14000f880  push    rbx
0x14000f882  push    rbp
0x14000f883  push    rsi
0x14000f884  push    rdi
0x14000f885  push    r14
0x14000f887  sub     rsp, 20h
0x14000f88b  movzx   eax, word ptr [rcx+58h]
0x14000f88f  mov     r14, rdx
0x14000f892  mov     rsi, rcx
0x14000f895  mov     bpl, 1
0x14000f898  lea     ebx, [rax+2]
0x14000f89b  add     bx, [rcx+68h]
0x14000f89f  test    ax, ax
0x14000f8a2  jz      short loc_14000F8BC
0x14000f8a4  mov     ecx, eax
0x14000f8a6  mov     rax, [rsi+60h]
0x14000f8aa  shr     rcx, 1
0x14000f8ad  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14000f8b3  jz      short loc_14000F8BC
0x14000f8b5  add     bx, 2
0x14000f8b9  xor     bpl, bpl
0x14000f8bc  movzx   edx, bx
0x14000f8bf  mov     ecx, 100h
0x14000f8c4  mov     r8d, 666E4346h
0x14000f8ca  call    cs:__imp_ExAllocatePool2
0x14000f8d1  nop     dword ptr [rax+rax+00h]
0x14000f8d6  mov     rdi, rax
0x14000f8d9  test    rax, rax
0x14000f8dc  jz      short loc_14000F94C
0x14000f8de  xor     ecx, ecx
0x14000f8e0  mov     [r14+8], rax
0x14000f8e4  mov     [r14], cx
0x14000f8e8  mov     rcx, rax; void *
0x14000f8eb  mov     [r14+2], bx
0x14000f8f0  movzx   r8d, word ptr [rsi+68h]; Size
0x14000f8f5  mov     rdx, [rsi+70h]; Src
0x14000f8f9  call    memmove
0x14000f8fe  movzx   ecx, word ptr [rsi+68h]
0x14000f902  movzx   r8d, word ptr [rsi+58h]; Size
0x14000f907  mov     rdx, [rsi+60h]; Src
0x14000f90b  shr     rcx, 1
0x14000f90e  lea     rdi, [rdi+rcx*2]
0x14000f912  mov     rcx, rdi; void *
0x14000f915  call    memmove
0x14000f91a  movzx   eax, word ptr [rsi+58h]
0x14000f91e  shr     rax, 1
0x14000f921  lea     rcx, [rdi+rax*2]
0x14000f925  test    bpl, bpl
0x14000f928  jnz     short loc_14000F933
0x14000f92a  mov     word ptr [rcx], 5Ch ; '\'
0x14000f92f  add     rcx, 2
0x14000f933  xor     eax, eax
0x14000f935  sub     bx, 2
0x14000f939  mov     [rcx], ax
0x14000f93c  mov     [r14], bx
0x14000f940  add     rsp, 20h
0x14000f944  pop     r14
0x14000f946  pop     rdi
0x14000f947  pop     rsi
0x14000f948  pop     rbp
0x14000f949  pop     rbx
0x14000f94a  retn
0x14000f94c  mov     eax, 0C000009Ah
0x14000f951  jmp     short loc_14000F940
```
