# GetComponentGlyphList

- ea: `0x18000de24`
- end: `0x18000e00b`
- name: `GetComponentGlyphList`
- size: `487`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000de24`
- `0x1800143f0`
- `0x1800178ec`

## callees

- `0x18000de24`
- `0x18000e014`
- `0x18001a2cc`
- `0x18001a680`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall GetComponentGlyphList(
        __int64 a1,
        int a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 a5,
        unsigned __int16 *a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        int a9,
        int a10)
{
  __int64 v10; // rdi
  __int64 result; // rax
  unsigned __int16 GenericSize; // ax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  unsigned int v17; // ebx
  int v18; // edx
  char v19; // di
  _WORD v20[2]; // [rsp+50h] [rbp-41h] BYREF
  __int16 v21; // [rsp+54h] [rbp-3Dh] BYREF
  __int16 v22; // [rsp+58h] [rbp-39h] BYREF
  __int16 v23; // [rsp+5Ch] [rbp-35h] BYREF
  int v24; // [rsp+60h] [rbp-31h] BYREF
  __int64 v25; // [rsp+68h] [rbp-29h]
  __int64 v26; // [rsp+70h] [rbp-21h] BYREF
  __int16 v27; // [rsp+78h] [rbp-19h]

  v26 = 0;
  v27 = 0;
  v10 = a4;
  v25 = a4;
  *a3 = 0;
  v21 = 0;
  v20[0] = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  result = GetGlyphHeader(a1, a2, a8, a9, a10, (__int64)&v26, (__int64)&v24, (__int64)&v23);
  if ( !(_WORD)result )
  {
    if ( *a6 < a7 )
      *a6 = a7;
    if ( (v26 & 0x8000u) == 0LL )
    {
      return 0;
    }
    else
    {
      GenericSize = GetGenericSize(&GLYF_HEADER_CONTROL);
      v15 = v24 + GenericSize;
      while ( *a3 < a5 )
      {
        result = ReadWord(a1, (__int64)&v21, v15);
        if ( (_WORD)result )
          return result;
        v17 = v15 + 2;
        result = ReadWord(v16, (__int64)v20, v17);
        if ( (_WORD)result )
          return result;
        v18 = v20[0];
        *(_WORD *)(v10 + 2LL * *a3) = v20[0];
        v19 = v21;
        ++*a3;
        v15 = v17 + 2 * (v19 & 1) + 4;
        if ( (v19 & 8) != 0 )
        {
          v15 += 2;
        }
        else if ( (v19 & 0x40) != 0 )
        {
          v15 += 4;
        }
        else if ( v19 < 0 )
        {
          v15 += 8;
        }
        result = GetComponentGlyphList(
                   a1,
                   v18,
                   (unsigned int)&v22,
                   (unsigned int)v25 + 2 * *a3,
                   a5 - *a3,
                   (__int64)a6,
                   a7 + 1,
                   a8,
                   a9,
                   a10);
        if ( (_WORD)result )
          return result;
        if ( v22 )
          *a3 += v22;
        if ( (v19 & 0x20) == 0 )
          return 0;
        v10 = v25;
      }
      return 1066;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000de24  push    rbp
0x18000de26  push    rbx
0x18000de27  push    rsi
0x18000de28  push    rdi
0x18000de29  push    r12
0x18000de2b  push    r13
0x18000de2d  push    r14
0x18000de2f  push    r15
0x18000de31  lea     rbp, [rsp-7]
0x18000de36  sub     rsp, 98h
0x18000de3d  mov     rax, cs:__security_cookie
0x18000de44  xor     rax, rsp
0x18000de47  mov     [rbp+3Fh+var_50], rax
0x18000de4b  mov     r15, [rbp+3Fh+arg_28]
0x18000de4f  xor     eax, eax
0x18000de51  xor     ebx, ebx
0x18000de53  mov     [rbp+3Fh+var_60], rax
0x18000de57  mov     [rbp+3Fh+var_58], ax
0x18000de5b  mov     rdi, r9
0x18000de5e  lea     rax, [rbp+3Fh+var_74]
0x18000de62  mov     [rbp+3Fh+var_68], r9
0x18000de66  mov     r9d, [rbp+3Fh+arg_40]
0x18000de6d  mov     rsi, r8
0x18000de70  mov     [rsp+0D0h+var_98], rax
0x18000de75  mov     r13, rcx
0x18000de78  lea     rax, [rbp+3Fh+var_70]
0x18000de7c  mov     [r8], bx
0x18000de80  movzx   r8d, [rbp+3Fh+arg_38]
0x18000de88  mov     [rsp+0D0h+var_A0], rax
0x18000de8d  lea     rax, [rbp+3Fh+var_60]
0x18000de91  mov     [rsp+0D0h+var_A8], rax
0x18000de96  mov     eax, [rbp+3Fh+arg_48]
0x18000de9c  mov     [rsp+0D0h+var_B0], eax
0x18000dea0  mov     [rbp+3Fh+var_7C], bx
0x18000dea4  mov     [rbp+3Fh+var_80], bx
0x18000dea8  mov     [rbp+3Fh+var_70], ebx
0x18000deab  mov     [rbp+3Fh+var_74], bx
0x18000deaf  mov     [rbp+3Fh+var_78], bx
0x18000deb3  call    GetGlyphHeader
0x18000deb8  test    ax, ax
0x18000debb  jnz     loc_18000DFEB
0x18000dec1  movzx   r14d, [rbp+3Fh+arg_30]
0x18000dec6  cmp     [r15], r14w
0x18000deca  jnb     short loc_18000DED0
0x18000decc  mov     [r15], r14w
0x18000ded0  cmp     word ptr [rbp+3Fh+var_60], bx
0x18000ded4  jge     loc_18000DFE9
0x18000deda  lea     rcx, GLYF_HEADER_CONTROL
0x18000dee1  call    GetGenericSize
0x18000dee6  movzx   r12d, [rbp+3Fh+arg_20]
0x18000deeb  movzx   ebx, ax
0x18000deee  add     ebx, [rbp+3Fh+var_70]
0x18000def1  cmp     [rsi], r12w
0x18000def5  jnb     loc_18000DFE0
0x18000defb  mov     r8d, ebx
0x18000defe  lea     rdx, [rbp+3Fh+var_7C]
0x18000df02  mov     rcx, r13
0x18000df05  call    ReadWord
0x18000df0a  test    ax, ax
0x18000df0d  jnz     loc_18000DFEB
0x18000df13  add     ebx, 2
0x18000df16  lea     rdx, [rbp+3Fh+var_80]
0x18000df1a  mov     r8d, ebx
0x18000df1d  call    ReadWord
0x18000df22  test    ax, ax
0x18000df25  jnz     loc_18000DFEB
0x18000df2b  movzx   eax, word ptr [rsi]
0x18000df2e  mov     r8d, 1
0x18000df34  movzx   edx, [rbp+3Fh+var_80]
0x18000df38  mov     [rdi+rax*2], dx
0x18000df3c  movzx   edi, [rbp+3Fh+var_7C]
0x18000df40  add     [rsi], r8w
0x18000df44  mov     eax, edi
0x18000df46  and     eax, r8d
0x18000df49  lea     ebx, [rbx+rax*2]
0x18000df4c  add     ebx, 4
0x18000df4f  test    dil, 8
0x18000df53  jz      short loc_18000DF5A
0x18000df55  add     ebx, 2
0x18000df58  jmp     short loc_18000DF6D
0x18000df5a  test    dil, 40h
0x18000df5e  jz      short loc_18000DF65
0x18000df60  add     ebx, 4
0x18000df63  jmp     short loc_18000DF6D
0x18000df65  test    dil, dil
0x18000df68  jns     short loc_18000DF6D
0x18000df6a  add     ebx, 8
0x18000df6d  movzx   eax, word ptr [rsi]
0x18000df70  lea     ecx, [r8+r14]
0x18000df74  mov     r9, [rbp+3Fh+var_68]
0x18000df78  movzx   r8d, r12w
0x18000df7c  sub     r8w, [rsi]
0x18000df80  lea     r9, [r9+rax*2]
0x18000df84  mov     eax, [rbp+3Fh+arg_48]
0x18000df8a  mov     [rsp+0D0h+var_88], eax
0x18000df8e  mov     eax, [rbp+3Fh+arg_40]
0x18000df94  mov     [rsp+0D0h+var_90], eax
0x18000df98  movzx   eax, [rbp+3Fh+arg_38]
0x18000df9f  mov     word ptr [rsp+0D0h+var_98], ax
0x18000dfa4  mov     word ptr [rsp+0D0h+var_A0], cx
0x18000dfa9  mov     rcx, r13
0x18000dfac  mov     [rsp+0D0h+var_A8], r15
0x18000dfb1  mov     word ptr [rsp+0D0h+var_B0], r8w
0x18000dfb7  lea     r8, [rbp+3Fh+var_78]
0x18000dfbb  call    GetComponentGlyphList
0x18000dfc0  test    ax, ax
0x18000dfc3  jnz     short loc_18000DFEB
0x18000dfc5  movzx   eax, [rbp+3Fh+var_78]
0x18000dfc9  test    ax, ax
0x18000dfcc  jz      short loc_18000DFD1
0x18000dfce  add     [rsi], ax
0x18000dfd1  test    dil, 20h
0x18000dfd5  jz      short loc_18000DFE7
0x18000dfd7  mov     rdi, [rbp+3Fh+var_68]
0x18000dfdb  jmp     loc_18000DEF1
0x18000dfe0  mov     eax, 42Ah
0x18000dfe5  jmp     short loc_18000DFEB
0x18000dfe7  xor     ebx, ebx
0x18000dfe9  mov     eax, ebx
0x18000dfeb  mov     rcx, [rbp+3Fh+var_50]
0x18000dfef  xor     rcx, rsp; StackCookie
0x18000dff2  call    __security_check_cookie
0x18000dff7  add     rsp, 98h
0x18000dffe  pop     r15
0x18000e000  pop     r14
0x18000e002  pop     r13
0x18000e004  pop     r12
0x18000e006  pop     rdi
0x18000e007  pop     rsi
0x18000e008  pop     rbx
0x18000e009  pop     rbp
0x18000e00a  retn
```
