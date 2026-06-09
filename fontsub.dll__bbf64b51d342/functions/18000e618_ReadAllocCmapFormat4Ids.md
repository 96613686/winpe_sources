# ReadAllocCmapFormat4Ids

- ea: `0x18000e618`
- end: `0x18000e74e`
- name: `ReadAllocCmapFormat4Ids`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a8dc`
- `0x18000e4c8`

## callees

- `0x18000e618`
- `0x180011538`
- `0x180011574`
- `0x18001a578`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat4Ids(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        _DWORD *a7)
{
  unsigned __int16 v10; // r10
  __int64 result; // rax
  unsigned __int16 v12; // cx
  unsigned __int16 i; // dx
  unsigned __int16 v14; // di
  unsigned __int16 v15; // si
  unsigned __int16 v16; // r10
  unsigned __int16 j; // r11
  unsigned __int16 v18; // ax
  __int64 v19; // rax
  unsigned __int16 GenericRepeat; // di

  v10 = 0;
  *a4 = 0;
  while ( v10 < a2 )
  {
    if ( *(_WORD *)(a3 + 8LL * v10) < *(_WORD *)(a3 + 8LL * v10 + 2) )
      return 1060;
    ++v10;
  }
  v12 = 0;
  for ( i = 0; i < a2; ++i )
  {
    v14 = *(_WORD *)(a3 + 8LL * i + 6);
    if ( v14 )
    {
      v15 = *(_WORD *)(a3 + 8LL * i + 2);
      v16 = *(_WORD *)(a3 + 8LL * i);
      for ( j = v15; j <= v16; ++j )
      {
        if ( v16 == 0xFFFF )
          break;
        v18 = j + i + (v14 >> 1) - v15 - a2 + 1;
        if ( v12 <= v18 )
          v12 = v18;
      }
    }
  }
  *a5 = v12;
  if ( !v12 )
    return 0;
  v19 = Mem_Alloc(2LL * v12);
  *a4 = v19;
  if ( !v19 )
    return 1005;
  GenericRepeat = ReadGenericRepeat(a1, v19, (unsigned __int8 *)&WORD_CONTROL, a6, a7, *a5, 2u);
  if ( !GenericRepeat )
    return 0;
  Mem_Free(*a4);
  result = GenericRepeat;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x18000e618  push    rbx
0x18000e61a  push    rbp
0x18000e61b  push    rsi
0x18000e61c  push    rdi
0x18000e61d  push    r14
0x18000e61f  sub     rsp, 40h
0x18000e623  mov     rbx, r9
0x18000e626  xor     r14d, r14d
0x18000e629  movzx   r9d, dx
0x18000e62d  mov     rbp, rcx
0x18000e630  mov     r10d, r14d
0x18000e633  mov     [rbx], r14
0x18000e636  cmp     r10w, r9w
0x18000e63a  jnb     short loc_18000E65D
0x18000e63c  movzx   edx, r10w
0x18000e640  movzx   eax, word ptr [r8+rdx*8+2]
0x18000e646  cmp     [r8+rdx*8], ax
0x18000e64b  jb      short loc_18000E653
0x18000e64d  inc     r10w
0x18000e651  jmp     short loc_18000E636
0x18000e653  mov     eax, 424h
0x18000e658  jmp     loc_18000E743
0x18000e65d  mov     ecx, r14d
0x18000e660  mov     edx, r14d
0x18000e663  cmp     r14w, r9w
0x18000e667  jnb     short loc_18000E6C8
0x18000e669  movzx   eax, dx
0x18000e66c  movzx   edi, word ptr [r8+rax*8+6]
0x18000e672  test    di, di
0x18000e675  jz      short loc_18000E6BF
0x18000e677  movzx   esi, word ptr [r8+rax*8+2]
0x18000e67d  movzx   r10d, word ptr [r8+rax*8]
0x18000e682  movzx   r11d, si
0x18000e686  cmp     si, r10w
0x18000e68a  ja      short loc_18000E6BF
0x18000e68c  mov     eax, 0FFFFh
0x18000e691  cmp     r10w, ax
0x18000e695  jz      short loc_18000E6BF
0x18000e697  movzx   eax, di
0x18000e69a  shr     ax, 1
0x18000e69d  sub     ax, si
0x18000e6a0  sub     ax, r9w
0x18000e6a4  inc     ax
0x18000e6a7  add     ax, dx
0x18000e6aa  add     ax, r11w
0x18000e6ae  inc     r11w
0x18000e6b2  cmp     cx, ax
0x18000e6b5  cmovbe  cx, ax
0x18000e6b9  cmp     r11w, r10w
0x18000e6bd  jbe     short loc_18000E68C
0x18000e6bf  inc     dx
0x18000e6c2  cmp     dx, r9w
0x18000e6c6  jb      short loc_18000E669
0x18000e6c8  mov     rdi, [rsp+68h+arg_20]
0x18000e6d0  mov     [rdi], cx
0x18000e6d3  test    cx, cx
0x18000e6d6  jz      short loc_18000E740
0x18000e6d8  movzx   ecx, cx
0x18000e6db  add     rcx, rcx; Size
0x18000e6de  call    Mem_Alloc
0x18000e6e3  mov     [rbx], rax
0x18000e6e6  mov     rdx, rax
0x18000e6e9  test    rax, rax
0x18000e6ec  jnz     short loc_18000E6F5
0x18000e6ee  mov     eax, 3EDh
0x18000e6f3  jmp     short loc_18000E743
0x18000e6f5  movzx   eax, word ptr [rdi]
0x18000e6f8  lea     r8, WORD_CONTROL
0x18000e6ff  mov     r9d, [rsp+68h+arg_28]
0x18000e707  mov     rcx, rbp
0x18000e70a  mov     [rsp+68h+var_38], 2
0x18000e711  mov     [rsp+68h+var_40], ax
0x18000e716  mov     rax, [rsp+68h+arg_30]
0x18000e71e  mov     [rsp+68h+var_48], rax
0x18000e723  call    ReadGenericRepeat
0x18000e728  movzx   edi, ax
0x18000e72b  test    ax, ax
0x18000e72e  jz      short loc_18000E740
0x18000e730  mov     rcx, [rbx]
0x18000e733  call    Mem_Free
0x18000e738  movzx   eax, di
0x18000e73b  mov     [rbx], r14
0x18000e73e  jmp     short loc_18000E743
0x18000e740  mov     eax, r14d
0x18000e743  add     rsp, 40h
0x18000e747  pop     r14
0x18000e749  pop     rdi
0x18000e74a  pop     rsi
0x18000e74b  pop     rbp
0x18000e74c  pop     rbx
0x18000e74d  retn
```
