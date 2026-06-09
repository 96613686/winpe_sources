# GetCompositeGlyphStats

- ea: `0x1800178ec`
- end: `0x180017a41`
- name: `GetCompositeGlyphStats`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800175f4`

## callees

- `0x18000de24`
- `0x1800178ec`
- `0x180017a48`

## pseudocode

```c
__int64 __fastcall GetCompositeGlyphStats(
        __int64 a1,
        int a2,
        _WORD *a3,
        _WORD *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        __int16 a8,
        int a9,
        int a10,
        __int64 a11,
        unsigned __int16 a12)
{
  unsigned __int16 v12; // di
  __int16 v15; // si
  __int16 v16; // r14
  unsigned __int16 v17; // bx
  unsigned __int16 v18; // r15
  unsigned __int16 v19; // ax
  __int64 result; // rax
  _WORD v21[2]; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 v22; // [rsp+54h] [rbp-24h] BYREF
  __int16 v23; // [rsp+58h] [rbp-20h] BYREF
  __int16 v24; // [rsp+5Ch] [rbp-1Ch] BYREF
  _DWORD v25[6]; // [rsp+60h] [rbp-18h] BYREF
  int v26; // [rsp+C0h] [rbp+48h]

  v26 = a1;
  v12 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v23 = 0;
  v24 = 0;
  v21[0] = 0;
  v22 = 0;
  v25[0] = 0;
  GetComponentGlyphList(a1, a2, &v22, a11, a12, a7, 0, a8, a9, a10);
  v18 = v22;
  if ( *a6 <= v22 )
    v19 = v22;
  else
    v19 = *a6;
  *a6 = v19;
  while ( v12 < v18 )
  {
    result = GetGlyphStats(
               v26,
               *(unsigned __int16 *)(a11 + 2LL * v12),
               (unsigned int)&v23,
               (unsigned int)&v24,
               (__int64)v21,
               a8,
               a9,
               a10,
               (__int64)v25);
    if ( (_WORD)result )
      return result;
    if ( v25[0] == 1 && v23 > 0 )
    {
      v16 += v24;
      v15 += v23;
      if ( v17 <= v21[0] )
        v17 = v21[0];
    }
    ++v12;
  }
  *a3 = v15;
  *a4 = v16;
  *a5 = v17;
  return 0;
}

```

## disassembly

```asm
0x1800178ec  mov     rax, rsp
0x1800178ef  mov     [rax+8], rcx
0x1800178f3  push    rbp
0x1800178f4  push    rbx
0x1800178f5  push    rsi
0x1800178f6  push    rdi
0x1800178f7  push    r12
0x1800178f9  push    r13
0x1800178fb  push    r14
0x1800178fd  push    r15
0x1800178ff  mov     rbp, rsp
0x180017902  sub     rsp, 78h
0x180017906  xor     edi, edi
0x180017908  mov     r13, r8
0x18001790b  mov     r8d, [rbp+arg_48]
0x180017912  mov     r12, r9
0x180017915  mov     r9, [rbp+arg_50]
0x18001791c  mov     esi, edi
0x18001791e  mov     [rax-70h], r8d
0x180017922  mov     r14d, edi
0x180017925  mov     r8d, [rbp+arg_40]
0x18001792c  mov     ebx, edi
0x18001792e  mov     [rax-78h], r8d
0x180017932  movzx   r8d, [rbp+arg_38]
0x18001793a  mov     [rax-80h], r8w
0x18001793f  lea     r8, [rbp+var_24]
0x180017943  mov     rax, [rbp+arg_30]
0x180017947  mov     word ptr [rsp+78h+var_48], di
0x18001794c  mov     [rsp+78h+var_50], rax
0x180017951  movzx   eax, [rbp+arg_58]
0x180017958  mov     word ptr [rsp+78h+var_58], ax
0x18001795d  mov     [rbp+var_20], di
0x180017961  mov     [rbp+var_1C], di
0x180017965  mov     [rbp+var_28], di
0x180017969  mov     [rbp+var_24], di
0x18001796d  mov     [rbp+var_18], edi
0x180017970  call    GetComponentGlyphList
0x180017975  mov     rcx, [rbp+arg_28]
0x180017979  movzx   r15d, [rbp+var_24]
0x18001797e  cmp     [rcx], r15w
0x180017982  jbe     short loc_180017989
0x180017984  movzx   eax, word ptr [rcx]
0x180017987  jmp     short loc_18001798C
0x180017989  mov     eax, r15d
0x18001798c  mov     [rcx], ax
0x18001798f  xor     ecx, ecx
0x180017991  cmp     di, r15w
0x180017995  jnb     loc_180017A1D
0x18001799b  mov     rcx, [rbp+arg_0]
0x18001799f  lea     rax, [rbp+var_18]
0x1800179a3  mov     [rsp+78h+var_38], rax
0x1800179a8  lea     r9, [rbp+var_1C]
0x1800179ac  mov     eax, [rbp+arg_48]
0x1800179b2  lea     r8, [rbp+var_20]
0x1800179b6  mov     [rsp+78h+var_40], eax
0x1800179ba  mov     eax, [rbp+arg_40]
0x1800179c0  mov     [rsp+78h+var_48], eax
0x1800179c4  movzx   eax, [rbp+arg_38]
0x1800179cb  mov     word ptr [rsp+78h+var_50], ax
0x1800179d0  lea     rax, [rbp+var_28]
0x1800179d4  mov     [rsp+78h+var_58], rax
0x1800179d9  mov     rax, [rbp+arg_50]
0x1800179e0  movzx   edx, di
0x1800179e3  movzx   edx, word ptr [rax+rdx*2]
0x1800179e7  call    GetGlyphStats
0x1800179ec  xor     ecx, ecx
0x1800179ee  test    ax, ax
0x1800179f1  jnz     short loc_180017A30
0x1800179f3  lea     edx, [rcx+1]
0x1800179f6  cmp     [rbp+var_18], edx
0x1800179f9  jnz     short loc_180017A15
0x1800179fb  movzx   eax, [rbp+var_20]
0x1800179ff  test    ax, ax
0x180017a02  jle     short loc_180017A15
0x180017a04  add     r14w, [rbp+var_1C]
0x180017a09  add     si, ax
0x180017a0c  cmp     bx, [rbp+var_28]
0x180017a10  cmovbe  bx, [rbp+var_28]
0x180017a15  add     di, dx
0x180017a18  jmp     loc_180017991
0x180017a1d  mov     rax, [rbp+arg_20]
0x180017a21  mov     [r13+0], si
0x180017a26  mov     [r12], r14w
0x180017a2b  mov     [rax], bx
0x180017a2e  mov     eax, ecx
0x180017a30  add     rsp, 78h
0x180017a34  pop     r15
0x180017a36  pop     r14
0x180017a38  pop     r13
0x180017a3a  pop     r12
0x180017a3c  pop     rdi
0x180017a3d  pop     rsi
0x180017a3e  pop     rbx
0x180017a3f  pop     rbp
0x180017a40  retn
```
