# sfac_ComputeIndex4

- ea: `0x140011910`
- end: `0x140011f4c`
- name: `sfac_ComputeIndex4`
- size: `1596`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140011910`
- `0x140013240`
- `0x140072578`

## pseudocode

```c
__int64 __fastcall sfac_ComputeIndex4(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 a3, _WORD *a4)
{
  unsigned __int16 *v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rsi
  unsigned __int16 *v8; // rbx
  __int64 v9; // r12
  unsigned __int16 v10; // r14
  unsigned __int16 v11; // r10
  __int16 v12; // r9
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rdx
  unsigned __int16 v15; // r9
  char *v16; // r8
  unsigned __int16 v17; // r8
  unsigned int v18; // eax
  char *v19; // r9
  unsigned __int16 *v20; // r8
  unsigned __int16 v21; // cx
  unsigned __int16 *v24; // rdx
  unsigned __int16 *v25; // kr10_8
  __int64 v26; // r15
  __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  unsigned __int16 *v29; // rdx
  __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  unsigned __int16 *v32; // rdx
  __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  unsigned __int16 *v35; // rdx
  unsigned __int16 v36; // r14
  _BYTE v37[88]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v38; // [rsp+80h] [rbp+8h] BYREF

  v5 = a1;
  if ( (unsigned int)a2 < 2 )
    goto LABEL_86;
  v6 = (unsigned int)(a2 - 2);
  v7 = v6;
  if ( (unsigned __int16 *)((char *)a1 + v6) < a1 )
    goto LABEL_86;
  a1 = (unsigned __int16 *)*(unsigned __int8 *)a1;
  v8 = v5 + 4;
  LOWORD(a1) = *((unsigned __int8 *)v5 + 1) | (unsigned __int16)((_WORD)a1 << 8);
  v9 = (unsigned __int16)a1;
  if ( (unsigned __int16)a1 < 0x10u || a3 <= 0xFFu )
    goto LABEL_29;
  if ( a4 )
  {
    v10 = a4[117];
    v11 = a4[119];
    v12 = a4[118];
  }
  else
  {
    LOWORD(a1) = (unsigned __int16)a1 >> 1;
    v12 = 0;
    v36 = 1;
    if ( (unsigned __int16)a1 >= 2u )
    {
      do
      {
        v36 *= 2;
        ++v12;
      }
      while ( 2 * (unsigned int)v36 <= (unsigned __int16)a1 );
    }
    v10 = 2 * v36;
    v11 = 2 * (_WORD)a1 - v10;
  }
  if ( v10 > (unsigned int)a2 )
    goto LABEL_86;
  a2 = (unsigned int)a2 - v10;
  if ( (unsigned int)a2 < 2 )
    goto LABEL_86;
  v13 = (unsigned __int64)v5 + (unsigned int)(a2 - 2);
  if ( v13 < (unsigned __int64)v5 )
    goto LABEL_86;
  if ( (unsigned __int64)v8 > v13 )
    return 0;
  v14 = (unsigned __int16 *)*((unsigned __int8 *)v8 + v10 + 1);
  LOWORD(v14) = _byteswap_ushort(*(unsigned __int16 *)((char *)v8 + v10));
  if ( a3 >= (unsigned __int16)v14 )
    v8 = (unsigned __int16 *)((char *)v8 + v11);
  if ( v12 == 7 )
    goto LABEL_14;
  if ( v12 != 12 )
  {
    v25 = v14;
    a2 = 0x140000000uLL;
    v26 = (unsigned int)v6;
    switch ( v12 )
    {
      case 4:
        goto LABEL_25;
      case 5:
        goto LABEL_21;
      case 6:
        goto LABEL_17;
      case 8:
        goto LABEL_64;
      case 9:
        goto LABEL_60;
      case 10:
        goto LABEL_56;
      case 11:
        goto LABEL_52;
      case 13:
        goto LABEL_80;
      case 14:
        goto LABEL_75;
      case 15:
        v38 = (unsigned int)v6;
        v27 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                           &v38,
                           v37,
                           1);
        if ( v27 < 0 )
        {
          v27 = -v27;
          if ( v27 <= (unsigned __int64)v5 )
          {
            v28 = (unsigned __int64)v5 - v27;
LABEL_72:
            v10 >>= 1;
            v29 = (unsigned __int16 *)((char *)v8 + v10);
            if ( (unsigned __int64)v29 > v28 )
              return 0;
            if ( a3 > _byteswap_ushort(*v29) )
              v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_75:
            v38 = v26;
            v30 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                               &v38,
                               v37,
                               1);
            if ( v30 < 0 )
            {
              v30 = -v30;
              if ( v30 <= (unsigned __int64)v5 )
              {
                v31 = (unsigned __int64)v5 - v30;
LABEL_77:
                v10 >>= 1;
                v32 = (unsigned __int16 *)((char *)v8 + v10);
                if ( (unsigned __int64)v32 > v31 )
                  return 0;
                if ( a3 > _byteswap_ushort(*v32) )
                  v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_80:
                v38 = v26;
                v33 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                                   &v38,
                                   v37,
                                   1);
                if ( v33 < 0 )
                {
                  v33 = -v33;
                  if ( v33 <= (unsigned __int64)v5 )
                  {
                    v34 = (unsigned __int64)v5 - v33;
                    goto LABEL_82;
                  }
                }
                else
                {
                  v34 = (unsigned __int64)v5 + v33;
                  if ( (unsigned __int16 *)((char *)v5 + v33) >= v5 )
                  {
LABEL_82:
                    v10 >>= 1;
                    v35 = (unsigned __int16 *)((char *)v8 + v10);
                    if ( (unsigned __int64)v35 > v34 )
                      return 0;
                    if ( a3 > _byteswap_ushort(*v35) )
                      v8 = (unsigned __int16 *)((char *)v8 + v10);
                    break;
                  }
                }
                SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v34, v33);
                __debugbreak();
              }
            }
            else
            {
              v31 = (unsigned __int64)v5 + v30;
              if ( (unsigned __int16 *)((char *)v5 + v30) >= v5 )
                goto LABEL_77;
            }
            SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v31, v30);
            __debugbreak();
          }
        }
        else
        {
          v28 = (unsigned __int64)v5 + v27;
          if ( (unsigned __int16 *)((char *)v5 + v27) >= v5 )
            goto LABEL_72;
        }
        SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v28, v27);
        __debugbreak();
      default:
        a2 = (unsigned __int64)v25;
        goto LABEL_29;
    }
  }
  v10 >>= 1;
  a2 = (unsigned __int64)v8 + v10;
  if ( a2 > (unsigned __int64)v5 + v7 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_52:
  a1 = (unsigned __int16 *)((char *)v5 + v7);
  if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
    goto LABEL_86;
  v10 >>= 1;
  a2 = (unsigned __int64)v8 + v10;
  if ( a2 > (unsigned __int64)a1 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_56:
  a1 = (unsigned __int16 *)((char *)v5 + v7);
  if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
    goto LABEL_86;
  v10 >>= 1;
  a2 = (unsigned __int64)v8 + v10;
  if ( a2 > (unsigned __int64)a1 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_60:
  a1 = (unsigned __int16 *)((char *)v5 + v7);
  if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
    goto LABEL_86;
  v10 >>= 1;
  a2 = (unsigned __int64)v8 + v10;
  if ( a2 > (unsigned __int64)a1 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_64:
  a1 = (unsigned __int16 *)((char *)v5 + v7);
  if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
    goto LABEL_86;
  v10 >>= 1;
  v24 = (unsigned __int16 *)((char *)v8 + v10);
  if ( v24 > a1 )
    return 0;
  if ( a3 > _byteswap_ushort(*v24) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_14:
  v10 >>= 1;
  a2 = (unsigned __int64)v8 + v10;
  if ( a2 > (unsigned __int64)v5 + v7 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_17:
  a1 = (unsigned __int16 *)((char *)v5 + v7);
  if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
    goto LABEL_86;
  v10 >>= 1;
  a2 = (unsigned __int64)v8 + v10;
  if ( a2 > (unsigned __int64)a1 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_21:
  a1 = (unsigned __int16 *)((char *)v5 + v7);
  if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
    goto LABEL_86;
  v10 >>= 1;
  a2 = (unsigned __int64)v8 + v10;
  if ( a2 > (unsigned __int64)a1 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + v10);
LABEL_25:
  a1 = (unsigned __int16 *)((char *)v5 + v7);
  if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
    goto LABEL_86;
  a2 = (unsigned __int64)v8 + ((unsigned __int64)v10 >> 1);
  if ( a2 > (unsigned __int64)a1 )
    return 0;
  if ( a3 > _byteswap_ushort(*(_WORD *)a2) )
    v8 = (unsigned __int16 *)((char *)v8 + ((unsigned __int64)v10 >> 1));
  while ( 1 )
  {
LABEL_29:
    a1 = (unsigned __int16 *)((char *)v5 + v7);
    if ( (unsigned __int16 *)((char *)v5 + v7) < v5 )
      goto LABEL_86;
    if ( v8 > a1 )
      return 0;
    a2 = (unsigned __int64)(v8 + 1);
    if ( a3 <= _byteswap_ushort(*v8) )
      break;
    ++v8;
  }
  a1 = (unsigned __int16 *)(v9 + a2);
  if ( v9 + a2 < a2 )
    goto LABEL_86;
  if ( a1 > (unsigned __int16 *)((char *)v5 + v7) )
    return 0;
  v15 = _byteswap_ushort(*a1);
  if ( a3 < v15 )
    return 0;
  v16 = (char *)a1 + v9;
  if ( (unsigned __int16 *)((char *)a1 + v9) < a1 )
    goto LABEL_86;
  if ( v16 > (char *)v5 + v7 )
    return 0;
  a1 = (unsigned __int16 *)&v16[v9];
  if ( &v16[v9] < v16 )
  {
LABEL_86:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, a2);
    __debugbreak();
  }
  a2 = (unsigned __int8)v16[1];
  LOWORD(a2) = _byteswap_ushort(*(_WORD *)v16);
  if ( a1 > (unsigned __int16 *)((char *)v5 + v7) )
    return 0;
  _mm_lfence();
  v17 = _byteswap_ushort(*a1);
  if ( !v17 )
    return (unsigned __int16)(a3 + a2);
  v18 = 2 * (unsigned __int16)(a3 - v15);
  if ( v18 > 0xFFFF )
    goto LABEL_86;
  v19 = (char *)a1 + (unsigned __int16)v18;
  if ( v19 < (char *)a1 )
    goto LABEL_86;
  v20 = (unsigned __int16 *)&v19[v17];
  if ( v20 <= (unsigned __int16 *)((char *)v5 + v7) )
  {
    v21 = _byteswap_ushort(*v20);
    if ( v21 )
      return (unsigned __int16)(v21 + a2);
    else
      return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140011910  push    rbx
0x140011912  push    rbp
0x140011913  push    rsi
0x140011914  push    rdi
0x140011915  push    r12
0x140011917  push    r13
0x140011919  push    r14
0x14001191b  push    r15
0x14001191d  sub     rsp, 38h
0x140011921  movzx   ebp, r8w
0x140011925  mov     rdi, rcx
0x140011928  cmp     edx, 2
0x14001192b  jb      loc_140011E76
0x140011931  lea     r8d, [rdx-2]
0x140011935  lea     rax, [rcx+r8]
0x140011939  mov     esi, r8d
0x14001193c  cmp     rax, rcx
0x14001193f  jb      loc_140011E76
0x140011945  movzx   ecx, byte ptr [rcx]
0x140011948  lea     rbx, [rdi+8]
0x14001194c  movzx   eax, byte ptr [rdi+1]
0x140011950  shl     cx, 8
0x140011954  or      cx, ax
0x140011957  mov     eax, 10h
0x14001195c  movzx   r12d, cx
0x140011960  cmp     ax, cx
0x140011963  ja      def_140011D4C; jumptable 0000000140011D4C default case, cases 7,12
0x140011969  mov     eax, 0FFh
0x14001196e  cmp     bp, ax
0x140011971  jbe     def_140011D4C; jumptable 0000000140011D4C default case, cases 7,12
0x140011977  mov     r13d, 1
0x14001197d  test    r9, r9
0x140011980  jz      loc_140011E83
0x140011986  movzx   r14d, word ptr [r9+0EAh]
0x14001198e  movzx   r10d, word ptr [r9+0EEh]
0x140011996  movzx   r9d, word ptr [r9+0ECh]
0x14001199e  movzx   eax, r14w
0x1400119a2  cmp     eax, edx
0x1400119a4  ja      loc_140011E76
0x1400119aa  sub     edx, eax
0x1400119ac  cmp     edx, 2
0x1400119af  jb      loc_140011E76
0x1400119b5  lea     eax, [rdx-2]
0x1400119b8  add     rax, rdi
0x1400119bb  cmp     rax, rdi
0x1400119be  jb      loc_140011E76
0x1400119c4  cmp     rbx, rax
0x1400119c7  ja      loc_140011E6F
0x1400119cd  movzx   eax, r14w
0x1400119d1  movzx   ecx, byte ptr [rax+rbx]
0x1400119d5  movzx   edx, byte ptr [rax+rbx+1]
0x1400119da  shl     cx, 8
0x1400119de  or      dx, cx
0x1400119e1  cmp     bp, dx
0x1400119e4  jb      short loc_1400119ED
0x1400119e6  movzx   eax, r10w
0x1400119ea  add     rbx, rax
0x1400119ed  movzx   eax, r9w
0x1400119f1  cmp     eax, 7
0x1400119f4  jnz     loc_140011C17
0x1400119fa  shr     r14w, 1
0x1400119fe  lea     rax, [rdi+rsi]
0x140011a02  movzx   edx, r14w
0x140011a06  add     rdx, rbx
0x140011a09  cmp     rdx, rax
0x140011a0c  ja      loc_140011E6F
0x140011a12  movzx   ecx, byte ptr [rdx]
0x140011a15  movzx   eax, byte ptr [rdx+1]
0x140011a19  shl     cx, 8
0x140011a1d  or      cx, ax
0x140011a20  cmp     bp, cx
0x140011a23  cmova   rbx, rdx
0x140011a27  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C case 6
0x140011a2b  cmp     rcx, rdi
0x140011a2e  jb      loc_140011E76
0x140011a34  shr     r14w, 1
0x140011a38  movzx   edx, r14w
0x140011a3c  add     rdx, rbx
0x140011a3f  cmp     rdx, rcx
0x140011a42  ja      loc_140011E6F
0x140011a48  movzx   ecx, byte ptr [rdx]
0x140011a4b  movzx   eax, byte ptr [rdx+1]
0x140011a4f  shl     cx, 8
0x140011a53  or      cx, ax
0x140011a56  cmp     bp, cx
0x140011a59  cmova   rbx, rdx
0x140011a5d  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C case 5
0x140011a61  cmp     rcx, rdi
0x140011a64  jb      loc_140011E76
0x140011a6a  shr     r14w, 1
0x140011a6e  movzx   edx, r14w
0x140011a72  add     rdx, rbx
0x140011a75  cmp     rdx, rcx
0x140011a78  ja      loc_140011E6F
0x140011a7e  movzx   ecx, byte ptr [rdx]
0x140011a81  movzx   eax, byte ptr [rdx+1]
0x140011a85  shl     cx, 8
0x140011a89  or      cx, ax
0x140011a8c  cmp     bp, cx
0x140011a8f  cmova   rbx, rdx
0x140011a93  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C case 4
0x140011a97  cmp     rcx, rdi
0x140011a9a  jb      loc_140011E76
0x140011aa0  movzx   edx, r14w
0x140011aa4  shr     rdx, 1
0x140011aa7  add     rdx, rbx
0x140011aaa  cmp     rdx, rcx
0x140011aad  ja      loc_140011E6F
0x140011ab3  movzx   ecx, byte ptr [rdx]
0x140011ab6  movzx   eax, byte ptr [rdx+1]
0x140011aba  shl     cx, 8
0x140011abe  or      cx, ax
0x140011ac1  cmp     bp, cx
0x140011ac4  cmova   rbx, rdx
0x140011ac8  nop     dword ptr [rax+rax+00000000h]
0x140011ad0  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C default case, cases 7,12
0x140011ad4  cmp     rcx, rdi
0x140011ad7  jb      loc_140011E76
0x140011add  cmp     rbx, rcx
0x140011ae0  ja      loc_140011E6F
0x140011ae6  movzx   ecx, byte ptr [rbx]
0x140011ae9  lea     rdx, [rbx+2]
0x140011aed  movzx   eax, byte ptr [rbx+1]
0x140011af1  shl     cx, 8
0x140011af5  or      cx, ax
0x140011af8  cmp     bp, cx
0x140011afb  jbe     short loc_140011B02
0x140011afd  mov     rbx, rdx
0x140011b00  jmp     short def_140011D4C; jumptable 0000000140011D4C default case, cases 7,12
0x140011b02  mov     r11, 7FFFFFFFFFFFFFFFh
0x140011b0c  cmp     r12, r11
0x140011b0f  ja      loc_140011E76
0x140011b15  lea     rcx, [r12+rdx]
0x140011b19  cmp     rcx, rdx
0x140011b1c  jb      loc_140011E76
0x140011b22  lea     rax, [rdi+rsi]
0x140011b26  cmp     rcx, rax
0x140011b29  ja      loc_140011E6F
0x140011b2f  movzx   r9d, byte ptr [rcx]
0x140011b33  movzx   eax, byte ptr [rcx+1]
0x140011b37  shl     r9w, 8
0x140011b3c  or      r9w, ax
0x140011b40  cmp     bp, r9w
0x140011b44  jb      loc_140011F0F
0x140011b4a  lea     r8, [r12+rcx]
0x140011b4e  cmp     r8, rcx
0x140011b51  jb      loc_140011E76
0x140011b57  lea     rax, [rdi+rsi]
0x140011b5b  cmp     r8, rax
0x140011b5e  ja      loc_140011E6F
0x140011b64  lea     rcx, [r12+r8]
0x140011b68  cmp     rcx, r8
0x140011b6b  jb      loc_140011E76
0x140011b71  movzx   eax, byte ptr [r8]
0x140011b75  movzx   edx, byte ptr [r8+1]
0x140011b7a  shl     ax, 8
0x140011b7e  or      dx, ax
0x140011b81  lea     rax, [rdi+rsi]
0x140011b85  cmp     rcx, rax
0x140011b88  ja      loc_140011E6F
0x140011b8e  lfence
0x140011b91  movzx   r8d, byte ptr [rcx]
0x140011b95  movzx   eax, byte ptr [rcx+1]
0x140011b99  shl     r8w, 8
0x140011b9e  or      r8w, ax
0x140011ba2  jz      short loc_140011C12
0x140011ba4  sub     bp, r9w
0x140011ba8  movzx   eax, bp
0x140011bab  add     eax, eax
0x140011bad  cmp     eax, 0FFFFh
0x140011bb2  ja      loc_140011E76
0x140011bb8  movzx   r9d, ax
0x140011bbc  cmp     r9, r11
0x140011bbf  ja      loc_140011E76
0x140011bc5  add     r9, rcx
0x140011bc8  cmp     r9, rcx
0x140011bcb  jb      loc_140011E76
0x140011bd1  movzx   r8d, r8w
0x140011bd5  lea     rax, [rdi+rsi]
0x140011bd9  add     r8, r9
0x140011bdc  cmp     r8, rax
0x140011bdf  ja      loc_140011E6F
0x140011be5  movzx   eax, byte ptr [r8]
0x140011be9  movzx   ecx, byte ptr [r8+1]
0x140011bee  shl     ax, 8
0x140011bf2  or      cx, ax
0x140011bf5  jz      loc_140011E7C
0x140011bfb  add     dx, cx
0x140011bfe  movzx   eax, dx
0x140011c01  add     rsp, 38h
0x140011c05  pop     r15
0x140011c07  pop     r14
0x140011c09  pop     r13
0x140011c0b  pop     r12
0x140011c0d  pop     rdi
0x140011c0e  pop     rsi
0x140011c0f  pop     rbp
0x140011c10  pop     rbx
0x140011c11  retn
0x140011c12  add     dx, bp
0x140011c15  jmp     short loc_140011BFE
0x140011c17  cmp     eax, 0Ch
0x140011c1a  jnz     loc_140011D2A
0x140011c20  shr     r14w, 1
0x140011c24  lea     rax, [rdi+rsi]
0x140011c28  movzx   edx, r14w
0x140011c2c  add     rdx, rbx
0x140011c2f  cmp     rdx, rax
0x140011c32  ja      loc_140011E6F
0x140011c38  movzx   ecx, byte ptr [rdx]
0x140011c3b  movzx   eax, byte ptr [rdx+1]
0x140011c3f  shl     cx, 8
0x140011c43  or      cx, ax
0x140011c46  cmp     bp, cx
0x140011c49  cmova   rbx, rdx
0x140011c4d  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C case 11
0x140011c51  cmp     rcx, rdi
0x140011c54  jb      loc_140011E76
0x140011c5a  shr     r14w, 1
0x140011c5e  movzx   edx, r14w
0x140011c62  add     rdx, rbx
0x140011c65  cmp     rdx, rcx
0x140011c68  ja      loc_140011E6F
0x140011c6e  movzx   ecx, byte ptr [rdx]
0x140011c71  movzx   eax, byte ptr [rdx+1]
0x140011c75  shl     cx, 8
0x140011c79  or      cx, ax
0x140011c7c  cmp     bp, cx
0x140011c7f  cmova   rbx, rdx
0x140011c83  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C case 10
0x140011c87  cmp     rcx, rdi
0x140011c8a  jb      loc_140011E76
0x140011c90  shr     r14w, 1
0x140011c94  movzx   edx, r14w
0x140011c98  add     rdx, rbx
0x140011c9b  cmp     rdx, rcx
0x140011c9e  ja      loc_140011E6F
0x140011ca4  movzx   ecx, byte ptr [rdx]
0x140011ca7  movzx   eax, byte ptr [rdx+1]
0x140011cab  shl     cx, 8
0x140011caf  or      cx, ax
0x140011cb2  cmp     bp, cx
0x140011cb5  cmova   rbx, rdx
0x140011cb9  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C case 9
0x140011cbd  cmp     rcx, rdi
0x140011cc0  jb      loc_140011E76
0x140011cc6  shr     r14w, 1
0x140011cca  movzx   edx, r14w
0x140011cce  add     rdx, rbx
0x140011cd1  cmp     rdx, rcx
0x140011cd4  ja      loc_140011E6F
0x140011cda  movzx   ecx, byte ptr [rdx]
0x140011cdd  movzx   eax, byte ptr [rdx+1]
0x140011ce1  shl     cx, 8
0x140011ce5  or      cx, ax
0x140011ce8  cmp     bp, cx
0x140011ceb  cmova   rbx, rdx
0x140011cef  lea     rcx, [rdi+rsi]; jumptable 0000000140011D4C case 8
0x140011cf3  cmp     rcx, rdi
0x140011cf6  jb      loc_140011E76
0x140011cfc  shr     r14w, 1
0x140011d00  movzx   edx, r14w
0x140011d04  add     rdx, rbx
0x140011d07  cmp     rdx, rcx
0x140011d0a  ja      loc_140011E6F
0x140011d10  movzx   ecx, byte ptr [rdx]
0x140011d13  movzx   eax, byte ptr [rdx+1]
0x140011d17  shl     cx, 8
0x140011d1b  or      cx, ax
0x140011d1e  cmp     bp, cx
0x140011d21  cmova   rbx, rdx
0x140011d25  jmp     loc_1400119FA
0x140011d2a  add     eax, 0FFFFFFFCh; switch 12 cases
0x140011d2d  cmp     eax, 0Bh
0x140011d30  ja      def_140011D4C; jumptable 0000000140011D4C default case, cases 7,12
0x140011d36  lea     rdx, cs:140000000h
0x140011d3d  cdqe
0x140011d3f  mov     r15d, r8d
0x140011d42  mov     ecx, ds:(jpt_140011D4C - 140000000h)[rdx+rax*4]
0x140011d49  add     rcx, rdx
0x140011d4c  jmp     rcx; switch jump
0x140011d4e  mov     r8, r13; jumptable 0000000140011D4C case 15
0x140011d51  mov     [rsp+78h+arg_0], r15
0x140011d59  lea     rdx, [rsp+78h+var_58]
0x140011d5e  lea     rcx, [rsp+78h+arg_0]
0x140011d66  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140011d6b  mov     rdx, [rax]
0x140011d6e  test    rdx, rdx
0x140011d71  js      loc_140011EC4
0x140011d77  lea     rcx, [rdx+rdi]
0x140011d7b  cmp     rcx, rdi
0x140011d7e  jb      loc_140011ECC
0x140011d84  shr     r14w, 1
0x140011d88  movzx   edx, r14w
0x140011d8c  add     rdx, rbx
0x140011d8f  cmp     rdx, rcx
0x140011d92  ja      loc_140011E6F
0x140011d98  movzx   eax, byte ptr [rdx]
0x140011d9b  movzx   ecx, byte ptr [rdx+1]
0x140011d9f  shl     ax, 8
  ... truncated ...
```
