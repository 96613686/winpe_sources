# CreateDeltaTTF

- ea: `0x180007cd4`
- end: `0x180007f9d`
- name: `CreateDeltaTTF`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180002a70`

## callees

- `0x180007cd4`
- `0x180007fa4`
- `0x180011538`
- `0x180011574`
- `0x1800143f0`
- `0x180019ac4`
- `0x18001a6c8`

## pseudocode

```c
__int64 CreateDeltaTTF(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        _DWORD *a4,
        unsigned int *a5,
        unsigned __int16 a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        unsigned __int16 a9,
        unsigned __int16 a10,
        __int64 a11,
        unsigned __int16 a12,
        __int64 (__fastcall *a13)(_QWORD, _QWORD),
        void (__fastcall *a14)(_QWORD),
        int a15,
        ...)
{
  __int64 v16; // rbx
  __int64 v17; // rsi
  unsigned __int16 NumGlyphs; // ax
  __int16 v19; // bx
  __int64 v21; // rdi
  unsigned __int16 KeepGlyphList; // bx
  unsigned __int16 v23; // r14
  __int64 v24; // rcx
  unsigned __int16 i; // dx
  __int64 v26; // rcx
  unsigned __int16 v27; // dx
  __int64 v28; // rax
  unsigned __int16 v29; // si
  unsigned __int16 DeltaTTFEx; // di
  __int16 v31; // [rsp+80h] [rbp-31h]
  _WORD v32[2]; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int16 v33; // [rsp+8Ch] [rbp-25h] BYREF
  __int128 v34; // [rsp+90h] [rbp-21h] BYREF
  __int128 v35; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-1h]
  __int64 v40; // [rsp+170h] [rbp+BFh] BYREF
  va_list va; // [rsp+170h] [rbp+BFh]
  va_list va1; // [rsp+178h] [rbp+C7h] BYREF

  va_start(va1, a15);
  va_start(va, a15);
  v40 = va_arg(va1, _QWORD);
  v36 = 0;
  v32[0] = 0;
  LOWORD(v40) = 0;
  v16 = 0;
  *(_QWORD *)&v34 = 0x7200000064LL;
  LOWORD(v17) = 0;
  *((_QWORD *)&v34 + 1) = 0x220000004DLL;
  v33 = 0;
  v35 = 0;
  if ( a11 )
  {
    if ( a10 == 1 )
    {
      *(_QWORD *)&v35 = a1;
      *((_QWORD *)&v35 + 1) = __PAIR64__(a15, a2);
      v36 = 0;
      NumGlyphs = GetNumGlyphs(&v35);
      v19 = NumGlyphs;
      if ( !NumGlyphs )
        return 1009;
      v21 = Mem_Alloc(NumGlyphs);
      if ( !v21 )
        return 1005;
      KeepGlyphList = MakeKeepGlyphList(
                        (unsigned int)&v35,
                        0,
                        3,
                        1,
                        (__int64)&v34,
                        4,
                        v21,
                        v19,
                        (__int64)v32,
                        (__int64)va,
                        0);
      if ( KeepGlyphList )
      {
        Mem_Free(v21);
        return KeepGlyphList;
      }
      v23 = a12;
      v17 = (unsigned __int16)(a12 + v40);
      v16 = Mem_Alloc(4 * v17);
      if ( !v16 )
      {
        v24 = v21;
LABEL_10:
        Mem_Free(v24);
        return 1005;
      }
      for ( i = 0; i < a12; *(_DWORD *)(v16 + 4 * v26) = *(unsigned __int16 *)(a11 + 2 * v26) )
        v26 = i++;
      v27 = 0;
      do
      {
        if ( v23 >= (unsigned __int16)v17 )
          break;
        if ( *(_BYTE *)(v27 + v21) )
        {
          v28 = v23++;
          *(_DWORD *)(v16 + 4 * v28) = v27;
        }
        ++v27;
      }
      while ( v27 <= v32[0] );
      Mem_Free(v21);
    }
    else
    {
      v16 = Mem_Alloc(4LL * ((unsigned int)a12 + 4));
      if ( !v16 )
        return 1005;
      if ( (unsigned __int16)UTF16toUCS4(a11, a12, v16, a12, (__int64)&v33) )
      {
        v24 = v16;
        goto LABEL_10;
      }
      v29 = v33;
      *(_OWORD *)(v16 + 4LL * v33) = v34;
      LOWORD(v17) = v29 + 4;
    }
  }
  DeltaTTFEx = CreateDeltaTTFEx(a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, v16, v17, a13, a14, a15, v31);
  if ( v16 )
    Mem_Free(v16);
  return DeltaTTFEx;
}

```

## disassembly

```asm
0x180007cd4  mov     rax, rsp
0x180007cd7  mov     [rax+10h], rbx
0x180007cdb  mov     [rax+20h], r9
0x180007cdf  mov     [rax+18h], r8
0x180007ce3  mov     [rax+8], rcx
0x180007ce7  push    rbp
0x180007ce8  push    rsi
0x180007ce9  push    rdi
0x180007cea  push    r12
0x180007cec  push    r13
0x180007cee  push    r14
0x180007cf0  push    r15
0x180007cf2  lea     rbp, [rax-3Fh]
0x180007cf6  sub     rsp, 0B0h
0x180007cfd  mov     r15, [rbp+37h+arg_50]
0x180007d04  xor     edi, edi
0x180007d06  movzx   r12d, [rbp+37h+arg_48]
0x180007d0e  xor     eax, eax
0x180007d10  mov     [rbp+37h+var_38], rax
0x180007d14  xorps   xmm0, xmm0
0x180007d17  mov     [rbp+37h+var_60], di
0x180007d1b  mov     r13d, edx
0x180007d1e  mov     word ptr [rbp+37h+arg_78], di
0x180007d25  mov     ebx, edi
0x180007d27  mov     dword ptr [rbp+37h+var_58], 64h ; 'd'
0x180007d2e  mov     esi, edi
0x180007d30  mov     dword ptr [rbp+37h+var_58+4], 72h ; 'r'
0x180007d37  mov     dword ptr [rbp+37h+var_58+8], 4Dh ; 'M'
0x180007d3e  mov     dword ptr [rbp+37h+var_58+0Ch], 22h ; '"'
0x180007d45  mov     [rbp+37h+var_5C], di
0x180007d49  movups  [rbp+37h+var_48], xmm0
0x180007d4d  test    r15, r15
0x180007d50  jz      loc_180007EF9
0x180007d56  lea     eax, [rdi+1]
0x180007d59  cmp     r12w, ax
0x180007d5d  jnz     loc_180007E9B
0x180007d63  mov     eax, [rbp+37h+arg_70]
0x180007d69  mov     qword ptr [rbp+37h+var_48], rcx
0x180007d6d  lea     rcx, [rbp+37h+var_48]
0x180007d71  mov     dword ptr [rbp+37h+var_48+8], edx
0x180007d74  mov     dword ptr [rbp+37h+var_48+0Ch], eax
0x180007d77  mov     [rbp+37h+var_38], rdi
0x180007d7b  call    GetNumGlyphs
0x180007d80  movzx   ebx, ax
0x180007d83  test    bx, bx
0x180007d86  jnz     short loc_180007D92
0x180007d88  mov     eax, 3F1h
0x180007d8d  jmp     loc_180007F82
0x180007d92  mov     rcx, rbx; Size
0x180007d95  call    Mem_Alloc
0x180007d9a  mov     rdi, rax
0x180007d9d  test    rax, rax
0x180007da0  jz      loc_180007E39
0x180007da6  mov     dword ptr [rsp+0E0h+var_90], esi
0x180007daa  lea     rax, [rbp+37h+arg_78]
0x180007db1  mov     [rsp+0E0h+var_98], rax
0x180007db6  lea     rcx, [rbp+37h+var_48]
0x180007dba  xor     edx, edx
0x180007dbc  lea     rax, [rbp+37h+var_60]
0x180007dc0  mov     [rsp+0E0h+var_A0], rax
0x180007dc5  lea     rax, [rbp+37h+var_58]
0x180007dc9  mov     word ptr [rsp+0E0h+var_A8], bx
0x180007dce  mov     qword ptr [rsp+0E0h+var_B0], rdi
0x180007dd3  mov     word ptr [rsp+0E0h+var_B8], 4
0x180007dda  lea     r9d, [rdx+1]
0x180007dde  lea     r8d, [rdx+3]
0x180007de2  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180007de7  call    MakeKeepGlyphList
0x180007dec  movzx   ebx, ax
0x180007def  test    ax, ax
0x180007df2  jz      short loc_180007E04
0x180007df4  mov     rcx, rdi
0x180007df7  call    Mem_Free
0x180007dfc  movzx   eax, bx
0x180007dff  jmp     loc_180007F82
0x180007e04  movzx   eax, word ptr [rbp+37h+arg_78]
0x180007e0b  movzx   r14d, [rbp+37h+arg_58]
0x180007e13  add     ax, r14w
0x180007e17  movzx   ecx, ax
0x180007e1a  movzx   esi, cx
0x180007e1d  shl     rcx, 2; Size
0x180007e21  call    Mem_Alloc
0x180007e26  xor     r8d, r8d
0x180007e29  mov     rbx, rax
0x180007e2c  test    rax, rax
0x180007e2f  jnz     short loc_180007E43
0x180007e31  mov     rcx, rdi
0x180007e34  call    Mem_Free
0x180007e39  mov     eax, 3EDh
0x180007e3e  jmp     loc_180007F82
0x180007e43  mov     edx, r8d
0x180007e46  mov     r9d, 1
0x180007e4c  cmp     r8w, r14w
0x180007e50  jnb     short loc_180007E67
0x180007e52  movzx   ecx, dx
0x180007e55  add     dx, r9w
0x180007e59  movzx   eax, word ptr [r15+rcx*2]
0x180007e5e  mov     [rbx+rcx*4], eax
0x180007e61  cmp     dx, r14w
0x180007e65  jb      short loc_180007E52
0x180007e67  mov     edx, r8d
0x180007e6a  cmp     r14w, si
0x180007e6e  jnb     short loc_180007E91
0x180007e70  movzx   eax, dx
0x180007e73  cmp     [rax+rdi], r8b
0x180007e77  jz      short loc_180007E87
0x180007e79  movzx   eax, r14w
0x180007e7d  add     r14w, r9w
0x180007e81  movzx   ecx, dx
0x180007e84  mov     [rbx+rax*4], ecx
0x180007e87  add     dx, r9w
0x180007e8b  cmp     dx, [rbp+37h+var_60]
0x180007e8f  jbe     short loc_180007E6A
0x180007e91  mov     rcx, rdi
0x180007e94  call    Mem_Free
0x180007e99  jmp     short loc_180007EF9
0x180007e9b  movzx   edi, [rbp+37h+arg_58]
0x180007ea2  mov     r14d, 4
0x180007ea8  lea     ecx, [r14+rdi]
0x180007eac  shl     rcx, 2; Size
0x180007eb0  call    Mem_Alloc
0x180007eb5  mov     rbx, rax
0x180007eb8  test    rax, rax
0x180007ebb  jz      loc_180007E39
0x180007ec1  lea     rax, [rbp+37h+var_5C]
0x180007ec5  movzx   r9d, di
0x180007ec9  mov     r8, rbx
0x180007ecc  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180007ed1  movzx   edx, di
0x180007ed4  mov     rcx, r15
0x180007ed7  call    UTF16toUCS4
0x180007edc  test    ax, ax
0x180007edf  jz      short loc_180007EE9
0x180007ee1  mov     rcx, rbx
0x180007ee4  jmp     loc_180007E34
0x180007ee9  movzx   esi, [rbp+37h+var_5C]
0x180007eed  movups  xmm0, [rbp+37h+var_58]
0x180007ef1  movups  xmmword ptr [rbx+rsi*4], xmm0
0x180007ef5  add     si, r14w
0x180007ef9  mov     eax, [rbp+37h+arg_70]
0x180007eff  mov     edx, r13d
0x180007f02  mov     r9, [rbp+37h+arg_18]
0x180007f06  mov     r8, [rbp+37h+arg_10]
0x180007f0a  mov     rcx, [rbp+37h+arg_0]
0x180007f0e  mov     [rsp+70h], eax
0x180007f12  mov     rax, [rbp+37h+arg_68]
0x180007f19  mov     qword ptr [rsp+0E0h+var_78], rax
0x180007f1e  mov     rax, [rbp+37h+arg_60]
0x180007f25  mov     [rsp+0E0h+var_80], rax
0x180007f2a  movzx   eax, [rbp+37h+arg_40]
0x180007f31  mov     word ptr [rsp+0E0h+var_88], si
0x180007f36  mov     qword ptr [rsp+0E0h+var_90], rbx
0x180007f3b  mov     word ptr [rsp+0E0h+var_98], r12w
0x180007f41  mov     word ptr [rsp+0E0h+var_A0], ax
0x180007f46  movzx   eax, [rbp+37h+arg_38]
0x180007f4a  mov     word ptr [rsp+0E0h+var_A8], ax
0x180007f4f  movzx   eax, [rbp+37h+arg_30]
0x180007f53  mov     [rsp+0E0h+var_B0], ax
0x180007f58  movzx   eax, [rbp+37h+arg_28]
0x180007f5c  mov     word ptr [rsp+0E0h+var_B8], ax
0x180007f61  mov     rax, [rbp+37h+arg_20]
0x180007f65  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180007f6a  call    CreateDeltaTTFEx
0x180007f6f  movzx   edi, ax
0x180007f72  test    rbx, rbx
0x180007f75  jz      short loc_180007F7F
0x180007f77  mov     rcx, rbx
0x180007f7a  call    Mem_Free
0x180007f7f  movzx   eax, di
0x180007f82  mov     rbx, [rsp+0E0h+arg_8]
0x180007f8a  add     rsp, 0B0h
0x180007f91  pop     r15
0x180007f93  pop     r14
0x180007f95  pop     r13
0x180007f97  pop     r12
0x180007f99  pop     rdi
0x180007f9a  pop     rsi
0x180007f9b  pop     rbp
0x180007f9c  retn
```
