# sl_compress_tcp

- ea: `0x14002e99c`
- end: `0x14002eecd`
- name: `sl_compress_tcp`
- size: `1329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002e080`

## callees

- `0x14000a290`
- `0x1400161f0`
- `0x1400162e0`
- `0x140016400`
- `0x14002e99c`

## pseudocode

```c
char __fastcall sl_compress_tcp(__int64 *a1, unsigned int *a2, unsigned int *a3, _DWORD *a4, __int64 ***a5)
{
  __int64 v5; // r15
  char *p_Src; // r14
  unsigned int v8; // ecx
  __int64 v9; // rbx
  __int64 *v10; // r13
  unsigned int v11; // edx
  _WORD *v12; // r12
  __int64 *v13; // rcx
  __int64 **v14; // rdx
  unsigned int v15; // esi
  char result; // al
  int v17; // edx
  unsigned __int8 v18; // cl
  __int16 v19; // cx
  __int16 v20; // cx
  int v21; // edx
  unsigned __int16 v22; // cx
  _BYTE *v23; // r14
  unsigned __int32 v24; // r8d
  _BYTE *v25; // r14
  unsigned __int32 v26; // ecx
  _BYTE *v27; // r14
  __int16 v28; // r10
  unsigned __int16 v29; // r9
  int v30; // r8d
  char v31; // si
  char v32; // di
  bool v33; // zf
  char v34; // bl
  size_t v35; // r8
  __int64 v36; // rcx
  unsigned __int8 v37; // [rsp+20h] [rbp-58h]
  unsigned int Size; // [rsp+24h] [rbp-54h]
  int Size_4; // [rsp+28h] [rbp-50h]
  char Src; // [rsp+58h] [rbp-20h] BYREF
  _BYTE v45[2]; // [rsp+59h] [rbp-1Fh] BYREF
  char v46; // [rsp+5Bh] [rbp-1Dh] BYREF
  _QWORD savedregs[8]; // [rsp+78h] [rbp+0h] BYREF

  v5 = *a1;
  p_Src = &Src;
  if ( (*(_WORD *)(*a1 + 6) & 0xFF3F) != 0 )
    return 64;
  v8 = *a2;
  if ( *a2 < 0x28 )
    return 64;
  if ( *(_BYTE *)(v5 + 9) != 6 )
    return 64;
  v9 = *(_BYTE *)v5 & 0xF;
  if ( (*(_BYTE *)(v5 + 4 * v9 + 13) & 0x17) != 0x10 )
    return 64;
  v10 = **a5;
  v11 = (unsigned __int16)__ROR2__(*(_WORD *)(v5 + 2), 8);
  if ( v8 > v11 )
    *a2 = v11;
  v12 = (_WORD *)v10 + 6;
  ++*((_DWORD *)a5 + 4);
  if ( *(_QWORD *)(v5 + 12) != v10[3] || *(_DWORD *)(v5 + 4 * v9) != *(_DWORD *)&v12[2 * (*(_BYTE *)v12 & 0xF)] )
  {
    v13 = (__int64 *)*a5;
    do
    {
      v14 = (__int64 **)v10;
      v10 = (__int64 *)*v10;
      ++*((_DWORD *)a5 + 6);
      v12 = (_WORD *)v10 + 6;
      if ( *(_QWORD *)(v5 + 12) == v10[3] && *(_DWORD *)(v5 + 4 * v9) == *(_DWORD *)&v12[2 * (*(_BYTE *)v12 & 0xF)] )
      {
        if ( v10 == v13 )
        {
          *a5 = v14;
        }
        else
        {
          *v14 = (__int64 *)*v10;
          *v10 = *v13;
          *v13 = (__int64)v10;
        }
        goto LABEL_18;
      }
    }
    while ( v10 != v13 );
    ++*((_DWORD *)a5 + 7);
    *a5 = v14;
    v15 = ((*(unsigned __int8 *)(v5 + 4 * v9 + 12) >> 2) & 0x3FFFFFFC) + 4 * v9;
    if ( v15 > *a2 )
      return 64;
    goto LABEL_14;
  }
LABEL_18:
  v17 = *(unsigned __int8 *)(v5 + 4 * v9 + 12);
  Size_4 = v17;
  v15 = (((unsigned int)v17 >> 2) & 0x3FFFFFFC) + 4 * v9;
  Size = v15;
  if ( v15 > *a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids);
    }
    return 64;
  }
  if ( *(_WORD *)v5 != *v12 )
    goto LABEL_14;
  if ( *(_WORD *)(v5 + 6) != v12[3] )
    goto LABEL_14;
  if ( *(_WORD *)(v5 + 8) != v12[4] )
    goto LABEL_14;
  v18 = (unsigned __int8)v17 >> 4;
  v37 = (unsigned __int8)v17 >> 4;
  if ( (unsigned __int8)v17 >> 4 != LOBYTE(v12[2 * v9 + 6]) >> 4 )
    goto LABEL_14;
  if ( (unsigned int)v9 > 5 )
  {
    if ( memcmp((const void *)(v5 + 24), v12 + 12, (unsigned int)(4 * v9 - 20)) )
      goto LABEL_14;
    v18 = v37;
    v17 = Size_4;
  }
  if ( v18 > 5u && memcmp((const void *)(v5 + 24 + 4 * v9), &v12[2 * v9 + 12], ((v17 >> 2) & 0xFFFFFFFC) - 20LL) )
    goto LABEL_14;
  v19 = *(_WORD *)(v5 + 4 * v9 + 18);
  if ( (*(_BYTE *)(v5 + 4 * v9 + 13) & 0x20) != 0 )
  {
    v20 = __ROR2__(v19, 8);
    if ( (unsigned __int16)(v20 - 1) > 0xFEu )
    {
      v45[1] = v20;
      p_Src = &v46;
      v45[0] = HIBYTE(v20);
      Src = 0;
    }
    else
    {
      Src = v20;
      p_Src = v45;
    }
    v21 = 1;
  }
  else
  {
    v21 = 0;
    if ( v19 != v12[2 * v9 + 9] )
      goto LABEL_14;
  }
  v22 = __ROR2__(*(_WORD *)(v5 + 4 * v9 + 14), 8) - __ROR2__(v12[2 * v9 + 7], 8);
  if ( v22 )
  {
    if ( v22 < 0x100u )
    {
      *p_Src++ = v22;
    }
    else
    {
      *p_Src = 0;
      v23 = p_Src + 1;
      v23[1] = v22;
      *v23 = HIBYTE(v22);
      p_Src = v23 + 2;
    }
    v21 |= 2u;
  }
  v24 = _byteswap_ulong(*(_DWORD *)(v5 + 4 * v9 + 8)) - _byteswap_ulong(*(_DWORD *)&v12[2 * v9 + 4]);
  if ( v24 )
  {
    if ( v24 > 0xFFFF )
      goto LABEL_14;
    if ( (unsigned __int16)v24 < 0x100u )
    {
      *p_Src++ = v24;
    }
    else
    {
      *p_Src = 0;
      v25 = p_Src + 1;
      v25[1] = v24;
      *v25 = BYTE1(v24);
      p_Src = v25 + 2;
    }
    v21 |= 4u;
  }
  v26 = _byteswap_ulong(*(_DWORD *)(v5 + 4 * v9 + 4)) - _byteswap_ulong(*(_DWORD *)&v12[2 * v9 + 2]);
  if ( v26 )
  {
    if ( v26 > 0xFFFF )
      goto LABEL_14;
    if ( (unsigned __int16)v26 < 0x100u )
    {
      *p_Src++ = v26;
    }
    else
    {
      *p_Src = 0;
      v27 = p_Src + 1;
      v27[1] = v26;
      *v27 = BYTE1(v26);
      p_Src = v27 + 2;
    }
    v21 |= 8u;
  }
  v28 = v12[1];
  v29 = __ROR2__(v28, 8);
  switch ( v21 )
  {
    case 0:
      if ( *(_WORD *)(v5 + 2) != v28 && v29 == v15 )
        goto LABEL_70;
      goto LABEL_14;
    case 8:
      if ( v26 != v29 - v15 )
        goto LABEL_70;
      LOBYTE(v21) = 15;
      break;
    case 11:
      goto LABEL_14;
    case 12:
      if ( v26 != v24 || v26 != v29 - v15 )
        goto LABEL_70;
      LOBYTE(v21) = 11;
      break;
    case 15:
LABEL_14:
      memmove(v12, (const void *)v5, v15);
      *(_BYTE *)(v5 + 9) = *((_BYTE *)v10 + 10);
      *((_BYTE *)a5 + 9) = *((_BYTE *)v10 + 10);
      return 112;
    default:
      goto LABEL_70;
  }
  p_Src = &Src;
LABEL_70:
  v30 = (unsigned __int16)__ROR2__(*(_WORD *)(v5 + 4), 8) - (unsigned __int16)__ROR2__(v12[2], 8);
  if ( v30 != 1 )
  {
    if ( (unsigned __int16)(v30 - 1) > 0xFEu )
    {
      *p_Src++ = 0;
      p_Src[1] = v30;
      *p_Src = BYTE1(v30);
      LODWORD(p_Src) = (_DWORD)p_Src + 2;
    }
    else
    {
      *p_Src = v30;
      LODWORD(p_Src) = (_DWORD)p_Src + 1;
    }
    LOBYTE(v21) = v21 | 0x20;
  }
  v31 = *(_BYTE *)(v5 + 4 * v9 + 16);
  v32 = v21 | 0x10;
  v33 = (*(_BYTE *)(v5 + 4 * v9 + 13) & 8) == 0;
  v34 = *(_BYTE *)(v5 + 4 * v9 + 17);
  if ( v33 )
    v32 = v21;
  memmove(v12, (const void *)v5, Size);
  v35 = (unsigned int)p_Src - ((unsigned int)savedregs - 32);
  *a3 = Size;
  v36 = Size - (unsigned int)v35 - 4;
  *((_BYTE *)a5 + 9) = *((_BYTE *)v10 + 10);
  *a4 = v35 + 4;
  *(_BYTE *)(v36 + v5) = v32 | 0x40;
  *(_BYTE *)(v36 + v5 + 1) = *((_BYTE *)v10 + 10);
  *a2 -= v36;
  *a1 += (unsigned int)v36;
  *(_BYTE *)(v36 + v5 + 2) = v31;
  *(_BYTE *)(v36 + v5 + 3) = v34;
  memmove((void *)((unsigned int)v36 + v5 + 4), &Src, v35);
  result = 0x80;
  ++*((_DWORD *)a5 + 5);
  return result;
}

```

## disassembly

```asm
0x14002e99c  push    rbp
0x14002e99e  push    rbx
0x14002e99f  push    rsi
0x14002e9a0  push    rdi
0x14002e9a1  push    r12
0x14002e9a3  push    r13
0x14002e9a5  push    r14
0x14002e9a7  push    r15
0x14002e9a9  mov     rbp, rsp
0x14002e9ac  sub     rsp, 78h
0x14002e9b0  mov     rax, cs:__security_cookie
0x14002e9b7  xor     rax, rsp
0x14002e9ba  mov     [rbp+var_10], rax
0x14002e9be  mov     r15, [rcx]
0x14002e9c1  lea     r14, [rbp+Src]
0x14002e9c5  mov     rdi, [rbp+arg_20]
0x14002e9c9  mov     [rbp+var_28], rcx
0x14002e9cd  mov     ecx, 0FF3Fh
0x14002e9d2  mov     [rbp+var_48], r8
0x14002e9d6  mov     r8, rdx
0x14002e9d9  mov     [rbp+var_38], r9
0x14002e9dd  mov     [rbp+var_30], rdx
0x14002e9e1  mov     [rbp+var_40], rdi
0x14002e9e5  test    [r15+6], cx
0x14002e9ea  jnz     loc_14002EB60
0x14002e9f0  mov     ecx, [rdx]
0x14002e9f2  cmp     ecx, 28h ; '('
0x14002e9f5  jb      loc_14002EB60
0x14002e9fb  cmp     byte ptr [r15+9], 6
0x14002ea00  jnz     loc_14002EB60
0x14002ea06  movzx   eax, byte ptr [r15]
0x14002ea0a  and     eax, 0Fh
0x14002ea0d  mov     ebx, eax
0x14002ea0f  mov     al, [r15+rax*4+0Dh]
0x14002ea14  and     al, 17h
0x14002ea16  cmp     al, 10h
0x14002ea18  jnz     loc_14002EB60
0x14002ea1e  mov     rax, [rdi]
0x14002ea21  mov     r13, [rax]
0x14002ea24  movzx   eax, word ptr [r15+2]
0x14002ea29  ror     ax, 8
0x14002ea2d  movzx   edx, ax
0x14002ea30  cmp     ecx, edx
0x14002ea32  jbe     short loc_14002EA37
0x14002ea34  mov     [r8], edx
0x14002ea37  mov     r9d, 1
0x14002ea3d  lea     r12, [r13+0Ch]
0x14002ea41  add     [rdi+10h], r9d
0x14002ea45  mov     eax, [r12+0Ch]
0x14002ea4a  cmp     [r15+0Ch], eax
0x14002ea4e  jnz     short loc_14002EA71
0x14002ea50  mov     eax, [r12+10h]
0x14002ea55  cmp     [r15+10h], eax
0x14002ea59  jnz     short loc_14002EA71
0x14002ea5b  movzx   eax, byte ptr [r12]
0x14002ea60  and     eax, 0Fh
0x14002ea63  mov     eax, [r12+rax*4]
0x14002ea67  cmp     [r15+rbx*4], eax
0x14002ea6b  jz      loc_14002EB0D
0x14002ea71  mov     rcx, [rdi]
0x14002ea74  mov     rdx, r13
0x14002ea77  mov     r13, [r13+0]
0x14002ea7b  add     [rdi+18h], r9d
0x14002ea7f  lea     r12, [r13+0Ch]
0x14002ea83  mov     eax, [r12+0Ch]
0x14002ea88  cmp     [r15+0Ch], eax
0x14002ea8c  jnz     short loc_14002EAAB
0x14002ea8e  mov     eax, [r12+10h]
0x14002ea93  cmp     [r15+10h], eax
0x14002ea97  jnz     short loc_14002EAAB
0x14002ea99  movzx   eax, byte ptr [r12]
0x14002ea9e  and     eax, 0Fh
0x14002eaa1  mov     eax, [r12+rax*4]
0x14002eaa5  cmp     [r15+rbx*4], eax
0x14002eaa9  jz      short loc_14002EAF2
0x14002eaab  cmp     r13, rcx
0x14002eaae  jnz     short loc_14002EA74
0x14002eab0  add     [rdi+1Ch], r9d
0x14002eab4  mov     [rdi], rdx
0x14002eab7  movzx   eax, byte ptr [r15+rbx*4+0Ch]
0x14002eabd  shr     eax, 2
0x14002eac0  and     eax, 3FFFFFFCh
0x14002eac5  lea     esi, [rax+rbx*4]
0x14002eac8  cmp     esi, [r8]
0x14002eacb  ja      loc_14002EB60
0x14002ead1  mov     r8d, esi; Size
0x14002ead4  mov     rdx, r15; Src
0x14002ead7  mov     rcx, r12; void *
0x14002eada  call    memmove
0x14002eadf  mov     al, [r13+0Ah]
0x14002eae3  mov     [r15+9], al
0x14002eae7  mov     al, [r13+0Ah]
0x14002eaeb  mov     [rdi+9], al
0x14002eaee  mov     al, 70h ; 'p'
0x14002eaf0  jmp     short loc_14002EB62
0x14002eaf2  cmp     r13, rcx
0x14002eaf5  jnz     short loc_14002EAFC
0x14002eaf7  mov     [rdi], rdx
0x14002eafa  jmp     short loc_14002EB0D
0x14002eafc  mov     rax, [r13+0]
0x14002eb00  mov     [rdx], rax
0x14002eb03  mov     rax, [rcx]
0x14002eb06  mov     [r13+0], rax
0x14002eb0a  mov     [rcx], r13
0x14002eb0d  movzx   edx, byte ptr [r15+rbx*4+0Ch]
0x14002eb13  mov     eax, edx
0x14002eb15  mov     dword ptr [rbp+Size+4], edx
0x14002eb18  shr     eax, 2
0x14002eb1b  and     eax, 3FFFFFFCh
0x14002eb20  lea     esi, [rax+rbx*4]
0x14002eb23  mov     dword ptr [rbp+Size], esi
0x14002eb26  cmp     esi, [r8]
0x14002eb29  jbe     short loc_14002EB80
0x14002eb2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eb32  lea     rax, WPP_GLOBAL_Control
0x14002eb39  cmp     rcx, rax
0x14002eb3c  jz      short loc_14002EB60
0x14002eb3e  mov     eax, [rcx+2Ch]
0x14002eb41  test    al, al
0x14002eb43  jns     short loc_14002EB60
0x14002eb45  cmp     byte ptr [rcx+29h], 3
0x14002eb49  jb      short loc_14002EB60
0x14002eb4b  mov     rcx, [rcx+18h]
0x14002eb4f  lea     r8, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids
0x14002eb56  mov     edx, 0Ah
0x14002eb5b  call    WPP_SF_
0x14002eb60  mov     al, 40h ; '@'
0x14002eb62  mov     rcx, [rbp+var_10]
0x14002eb66  xor     rcx, rsp; StackCookie
0x14002eb69  call    __security_check_cookie
0x14002eb6e  add     rsp, 78h
0x14002eb72  pop     r15
0x14002eb74  pop     r14
0x14002eb76  pop     r13
0x14002eb78  pop     r12
0x14002eb7a  pop     rdi
0x14002eb7b  pop     rsi
0x14002eb7c  pop     rbx
0x14002eb7d  pop     rbp
0x14002eb7e  retn
0x14002eb80  movzx   eax, word ptr [r12]
0x14002eb85  cmp     [r15], ax
0x14002eb89  jnz     loc_14002EAD1
0x14002eb8f  movzx   eax, word ptr [r12+6]
0x14002eb95  cmp     [r15+6], ax
0x14002eb9a  jnz     loc_14002EAD1
0x14002eba0  movzx   eax, word ptr [r12+8]
0x14002eba6  cmp     [r15+8], ax
0x14002ebab  jnz     loc_14002EAD1
0x14002ebb1  mov     al, [r12+rbx*4+0Ch]
0x14002ebb6  mov     cl, dl
0x14002ebb8  shr     cl, 4
0x14002ebbb  shr     al, 4
0x14002ebbe  mov     [rbp+var_58], cl
0x14002ebc1  cmp     cl, al
0x14002ebc3  jnz     loc_14002EAD1
0x14002ebc9  cmp     ebx, 5
0x14002ebcc  jbe     short loc_14002EBF2
0x14002ebce  lea     r8d, ds:0FFFFFFFFFFFFFFECh[rbx*4]; Size
0x14002ebd6  lea     rdx, [r12+18h]; Buf2
0x14002ebdb  lea     rcx, [r15+18h]; Buf1
0x14002ebdf  call    memcmp
0x14002ebe4  test    eax, eax
0x14002ebe6  jnz     loc_14002EAD1
0x14002ebec  mov     cl, [rbp+var_58]
0x14002ebef  mov     edx, dword ptr [rbp+Size+4]
0x14002ebf2  cmp     cl, 5
0x14002ebf5  jbe     short loc_14002EC27
0x14002ebf7  mov     r8d, edx
0x14002ebfa  lea     rcx, [r15+18h]
0x14002ebfe  sar     r8d, 2
0x14002ec02  lea     rdx, [rbx+6]
0x14002ec06  mov     eax, 0FFFFFFFCh
0x14002ec0b  lea     rdx, [r12+rdx*4]; Buf2
0x14002ec0f  and     r8, rax
0x14002ec12  lea     rcx, [rcx+rbx*4]; Buf1
0x14002ec16  sub     r8, 14h; Size
0x14002ec1a  call    memcmp
0x14002ec1f  test    eax, eax
0x14002ec21  jnz     loc_14002EAD1
0x14002ec27  test    byte ptr [r15+rbx*4+0Dh], 20h
0x14002ec2d  mov     edx, 0FEh
0x14002ec32  movzx   ecx, word ptr [r15+rbx*4+12h]
0x14002ec38  jz      short loc_14002EC70
0x14002ec3a  ror     cx, 8
0x14002ec3e  mov     r11d, 1
0x14002ec44  movzx   eax, cx
0x14002ec47  sub     ax, r11w
0x14002ec4b  cmp     ax, dx
0x14002ec4e  ja      short loc_14002EC59
0x14002ec50  mov     [rbp+Src], cl
0x14002ec53  lea     r14, [rbp+var_1F]
0x14002ec57  jmp     short loc_14002EC6B
0x14002ec59  mov     [rbp+var_1E], cl
0x14002ec5c  lea     r14, [rbp+var_1D]
0x14002ec60  shr     cx, 8
0x14002ec64  mov     [rbp+var_1F], cl
0x14002ec67  mov     [rbp+Src], 0
0x14002ec6b  mov     edx, r11d
0x14002ec6e  jmp     short loc_14002EC82
0x14002ec70  xor     edx, edx
0x14002ec72  cmp     cx, [r12+rbx*4+12h]
0x14002ec78  jnz     loc_14002EAD1
0x14002ec7e  lea     r11d, [rdx+1]
0x14002ec82  movzx   ecx, word ptr [r12+rbx*4+0Eh]
0x14002ec88  mov     r9d, 100h
0x14002ec8e  movzx   eax, word ptr [r15+rbx*4+0Eh]
0x14002ec94  ror     cx, 8
0x14002ec98  ror     ax, 8
0x14002ec9c  sub     ax, cx
0x14002ec9f  movzx   ecx, ax
0x14002eca2  jz      short loc_14002ECCA
0x14002eca4  cmp     cx, r9w
0x14002eca8  jb      short loc_14002ECC1
0x14002ecaa  mov     byte ptr [r14], 0
0x14002ecae  add     r14, r11
0x14002ecb1  mov     [r14+1], cl
0x14002ecb5  shr     ecx, 8
0x14002ecb8  mov     [r14], cl
0x14002ecbb  add     r14, 2
0x14002ecbf  jmp     short loc_14002ECC7
0x14002ecc1  mov     [r14], cl
0x14002ecc4  add     r14, r11
0x14002ecc7  or      edx, 2
0x14002ecca  mov     eax, [r12+rbx*4+8]
0x14002eccf  mov     r10d, 0FFFFh
0x14002ecd5  mov     r8d, [r15+rbx*4+8]
0x14002ecda  bswap   eax
0x14002ecdc  bswap   r8d
0x14002ecdf  sub     r8d, eax
0x14002ece2  jz      short loc_14002ED16
0x14002ece4  cmp     r8d, r10d
0x14002ece7  ja      loc_14002EAD1
0x14002eced  cmp     r8w, r9w
0x14002ecf1  jb      short loc_14002ED0D
0x14002ecf3  mov     byte ptr [r14], 0
0x14002ecf7  mov     eax, r8d
0x14002ecfa  add     r14, r11
0x14002ecfd  shr     eax, 8
0x14002ed00  mov     [r14+1], r8b
0x14002ed04  mov     [r14], al
0x14002ed07  add     r14, 2
0x14002ed0b  jmp     short loc_14002ED13
0x14002ed0d  mov     [r14], r8b
0x14002ed10  add     r14, r11
0x14002ed13  or      edx, 4
0x14002ed16  mov     eax, [r12+rbx*4+4]
0x14002ed1b  mov     ecx, [r15+rbx*4+4]
0x14002ed20  bswap   eax
0x14002ed22  bswap   ecx
0x14002ed24  sub     ecx, eax
0x14002ed26  jz      short loc_14002ED59
0x14002ed28  cmp     ecx, r10d
0x14002ed2b  ja      loc_14002EAD1
0x14002ed31  cmp     cx, r9w
0x14002ed35  jb      short loc_14002ED50
0x14002ed37  mov     byte ptr [r14], 0
0x14002ed3b  mov     eax, ecx
0x14002ed3d  add     r14, r11
0x14002ed40  shr     eax, 8
0x14002ed43  mov     [r14+1], cl
0x14002ed47  mov     [r14], al
0x14002ed4a  add     r14, 2
0x14002ed4e  jmp     short loc_14002ED56
0x14002ed50  mov     [r14], cl
0x14002ed53  add     r14, r11
0x14002ed56  or      edx, 8
0x14002ed59  movzx   r10d, word ptr [r12+2]
0x14002ed5f  mov     eax, edx
0x14002ed61  movzx   r9d, r10w
0x14002ed65  ror     r9w, 8
0x14002ed6a  test    edx, edx
0x14002ed6c  jz      short loc_14002EDB7
0x14002ed6e  sub     eax, 8
0x14002ed71  jz      short loc_14002EDA6
0x14002ed73  sub     eax, 3
0x14002ed76  jz      loc_14002EAD1
0x14002ed7c  sub     eax, 1
0x14002ed7f  jz      short loc_14002ED8C
0x14002ed81  cmp     eax, 3
0x14002ed84  jz      loc_14002EAD1
0x14002ed8a  jmp     short loc_14002EDCE
0x14002ed8c  cmp     ecx, r8d
0x14002ed8f  jnz     short loc_14002EDCE
0x14002ed91  movzx   eax, r9w
0x14002ed95  sub     eax, esi
0x14002ed97  cmp     ecx, eax
0x14002ed99  jnz     short loc_14002EDCE
0x14002ed9b  mov     edx, 0Bh
0x14002eda0  lea     r14, [rbp+Src]
0x14002eda4  jmp     short loc_14002EDCE
0x14002eda6  movzx   eax, r9w
0x14002edaa  sub     eax, esi
0x14002edac  cmp     ecx, eax
0x14002edae  jnz     short loc_14002EDCE
0x14002edb0  mov     edx, 0Fh
0x14002edb5  jmp     short loc_14002EDA0
0x14002edb7  cmp     [r15+2], r10w
0x14002edbc  jz      loc_14002EAD1
0x14002edc2  movzx   eax, r9w
  ... truncated ...
```
