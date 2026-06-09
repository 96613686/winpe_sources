# CJetParameterList::DetermineSizeOfJetBuffer(tagREDACCESSOR *,tagDBPARAMS *,ulong &)

- ea: `0x10049c60`
- end: `0x1004a03b`
- name: `?DetermineSizeOfJetBuffer@CJetParameterList@@AAEJPAUtagREDACCESSOR@@PAUtagDBPARAMS@@AAK@Z`
- size: `987`
- prototype: `int __thiscall(CJetParameterList *__hidden this, struct tagREDACCESSOR *, struct tagDBPARAMS *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1004a120`

## callees

- `0x10049c60`

## pseudocode

```c
int __thiscall CJetParameterList::DetermineSizeOfJetBuffer(
        CJetParameterList *this,
        struct tagREDACCESSOR *a2,
        struct tagDBPARAMS *a3,
        unsigned int *a4)
{
  CJetParameterList *v4; // eax
  int v5; // edi
  unsigned int i; // ebx
  int v7; // eax
  unsigned int v8; // edx
  int v9; // ecx
  int v11; // edx
  unsigned int v12; // esi
  char *v13; // ecx
  char *v14; // ecx
  int v15; // esi
  unsigned int v16; // edx
  int v17; // edx
  int *v18; // edi
  int v19; // ecx
  unsigned int v20; // esi
  int v21; // ecx
  unsigned int v22; // eax
  int v23; // ecx
  __int16 *v24; // edi
  __int16 *v25; // esi
  __int16 *v26; // edi
  __int16 v27; // dx
  __int16 *v28; // esi
  int v29; // esi
  int v30; // ecx
  __int16 v31; // si
  int v32; // edx
  __int16 v33; // si
  int v34; // ecx
  __int16 v35; // si
  int *v36; // ebx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  unsigned int v42; // [esp+10h] [ebp-14h]
  unsigned int v43; // [esp+14h] [ebp-10h]
  __int16 v44; // [esp+14h] [ebp-10h]
  int *v45; // [esp+18h] [ebp-Ch]
  char *v46; // [esp+1Ch] [ebp-8h]
  __int16 *v47; // [esp+1Ch] [ebp-8h]
  int *v48; // [esp+20h] [ebp-4h]

  v4 = this;
  v5 = 0;
  *a4 = 0;
  for ( i = 1; ; i = v42 + 1 )
  {
LABEL_2:
    v7 = *(_DWORD *)v4;
    v8 = 0;
    v42 = i;
    if ( v7 )
    {
      v9 = v7;
      do
      {
        v9 = *(_DWORD *)(v9 + 40);
        ++v8;
      }
      while ( v9 );
    }
    if ( i > v8 )
      break;
    if ( !v7 )
      return -2147467259;
    while ( *(_DWORD *)v7 != i )
    {
      v7 = *(_DWORD *)(v7 + 40);
      if ( !v7 )
        return -2147467259;
    }
    if ( *(_DWORD *)(v7 + 8) == 1 )
      return -2147467259;
    v11 = 0;
    v12 = *((_DWORD *)a2 + 9);
    if ( !v12 )
      return -2147467259;
    while ( i != *((_DWORD *)a2 + 13 * v11 + 10) )
    {
      if ( ++v11 >= v12 )
        return -2147467259;
    }
    v13 = (char *)a2 + 52 * v11;
    v46 = v13;
    if ( (v13[68] & 1) != 0 )
      v14 = (char *)a3->pData + *((_DWORD *)v13 + 11);
    else
      v14 = 0;
    v15 = *a4;
    v16 = *a4 + 4;
    *a4 = v16;
    v5 = 0;
    v43 = v16;
    if ( v14 )
    {
      v17 = *(_DWORD *)(v7 + 24);
      v18 = (int *)(v7 + 24);
      v48 = (int *)(v7 + 24);
      if ( v17 )
      {
        v19 = *(_DWORD *)(v7 + 24);
        v45 = (int *)(v7 + 32);
        v18 = (int *)(v7 + 24);
      }
      else
      {
        v45 = (int *)(v7 + 32);
        v19 = *(_DWORD *)(v7 + 32);
      }
      switch ( v19 )
      {
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 15:
          if ( !v17 )
            v17 = *v45;
          v5 = 0;
          ++i;
          *a4 = v43 + ((dword_10051944[2 * v17] + 3) & 0xFFFFFFFC);
          v4 = this;
          goto LABEL_2;
        case 9:
        case 10:
          v20 = v15 + 8;
          *a4 = v20;
          v21 = *v18;
          if ( *v18 )
          {
            v5 = 0;
            v22 = (dword_10051944[2 * v21] + 3) & 0xFFFFFFFC;
          }
          else
          {
            v5 = 0;
            v22 = (*(_DWORD *)(v7 + 36) + 3) & 0xFFFFFFFC;
          }
          ++i;
          *a4 = v20 + v22;
          v4 = this;
          goto LABEL_2;
        case 11:
        case 12:
        case 17:
          v5 = 0;
          ++i;
          *a4 = v15 + 12;
          v4 = this;
          goto LABEL_2;
        default:
          v23 = *(_DWORD *)(v7 + 8);
          if ( v23 == 1 )
            goto LABEL_37;
          if ( v23 == 2 )
          {
            v17 = *v18;
LABEL_37:
            v25 = (__int16 *)(v7 + 22);
            v44 = *(_WORD *)(v7 + 22);
            v24 = (__int16 *)(v7 + 28);
          }
          else
          {
            if ( v23 )
            {
              v26 = (__int16 *)(v7 + 22);
              v27 = 10;
              v28 = (__int16 *)(v7 + 28);
              v47 = (__int16 *)(v7 + 22);
              goto LABEL_58;
            }
            v24 = (__int16 *)(v7 + 28);
            v44 = *(_WORD *)(v7 + 28);
            v25 = (__int16 *)(v7 + 22);
            v17 = *v48;
          }
          if ( !v44 )
          {
            v5 = 0;
            if ( *v45 )
              goto LABEL_73;
            v29 = *((unsigned __int16 *)v46 + 44);
            if ( (v29 & 0xFFFF8FFF) == 0x80 )
            {
              v17 = 11;
              *v48 = 11;
            }
            else if ( (v29 & 0xFFFF8FFF) == 0x82 )
            {
              v17 = 12;
              *v48 = 12;
            }
            else
            {
              v17 = 0;
              v30 = 0;
              v31 = v29 & 0x8FFF;
              while ( v31 != word_100518A0[4 * v30] )
              {
                if ( (unsigned int)++v30 >= 0xD )
                  goto LABEL_47;
              }
              v17 = dword_100518A4[2 * v30];
LABEL_47:
              *v48 = v17;
              if ( !v17 || v17 == 16 )
              {
                *v48 = 12;
                *(_WORD *)(v7 + 22) = 130;
                v17 = 12;
                goto LABEL_73;
              }
            }
            *(_WORD *)(v7 + 22) = *((_WORD *)v46 + 44) & 0x8FFF;
LABEL_73:
            if ( !v17 )
            {
              v36 = v45;
              v37 = *v45;
              goto LABEL_80;
            }
LABEL_79:
            v36 = v45;
            v37 = v17;
LABEL_80:
            if ( v37 == 11 || (v17 ? (v38 = v17) : (v38 = *v36), v38 == 12) )
            {
              *a4 += 8;
            }
            else
            {
              if ( v17 )
                v39 = v17;
              else
                v39 = *v36;
              if ( (unsigned int)(v39 - 1) <= 0x12 )
              {
                if ( !v17 )
                  v17 = *v36;
                *a4 += (dword_10051944[2 * v17] + 3) & 0xFFFFFFFC;
              }
              else
              {
                v5 = -2147467259;
              }
            }
            v40 = *v48;
            if ( !*v48 )
              v40 = *v36;
            *(_DWORD *)(v7 + 36) = dword_10051944[2 * v40];
            break;
          }
          v47 = v25;
          if ( v23 == 1 || v23 == 2 )
          {
            v27 = *v25;
            v28 = v24;
          }
          else
          {
            v28 = v24;
            v27 = *v24;
          }
          v26 = v47;
LABEL_58:
          v32 = (v27 & 0x8FFF) - 128;
          if ( v32 )
          {
            if ( v32 != 2 )
            {
              if ( v23 == 1 || v23 == 2 )
              {
                v33 = *v26;
              }
              else if ( v23 )
              {
                v33 = 10;
              }
              else
              {
                v33 = *v28;
              }
              v17 = 0;
              v34 = 0;
              v35 = v33 & 0x8FFF;
              v5 = 0;
              while ( v35 != word_100518A0[4 * v34] )
              {
                if ( (unsigned int)++v34 >= 0xD )
                  goto LABEL_71;
              }
              v17 = dword_100518A4[2 * v34];
LABEL_71:
              *v48 = v17;
              if ( !v17 || v17 == 16 )
              {
                *v48 = 12;
                *v47 = 130;
                v17 = 12;
                goto LABEL_79;
              }
              goto LABEL_73;
            }
            v17 = 12;
            *v48 = 12;
          }
          else
          {
            v17 = 11;
            *v48 = 11;
          }
          v5 = 0;
          goto LABEL_79;
      }
    }
    v4 = this;
  }
  return v5;
}

```

## disassembly

```asm
0x10049c60  mov     edi, edi
0x10049c62  push    ebp
0x10049c63  mov     ebp, esp
0x10049c65  sub     esp, 18h
0x10049c68  mov     edx, [ebp+arg_8]
0x10049c6b  mov     eax, ecx
0x10049c6d  push    ebx
0x10049c6e  push    esi
0x10049c6f  push    edi
0x10049c70  xor     edi, edi
0x10049c72  mov     [ebp+var_18], eax
0x10049c75  mov     [edx], edi
0x10049c77  mov     ebx, 1
0x10049c7c  mov     eax, [eax]
0x10049c7e  xor     edx, edx
0x10049c80  mov     [ebp+var_14], ebx
0x10049c83  test    eax, eax
0x10049c85  jz      short loc_10049C98
0x10049c87  mov     ecx, eax
0x10049c89  nop     dword ptr [eax+00000000h]
0x10049c90  mov     ecx, [ecx+28h]
0x10049c93  inc     edx
0x10049c94  test    ecx, ecx
0x10049c96  jnz     short loc_10049C90
0x10049c98  cmp     ebx, edx
0x10049c9a  ja      loc_1004A030
0x10049ca0  test    eax, eax
0x10049ca2  jz      short loc_10049CAF
0x10049ca4  cmp     [eax], ebx
0x10049ca6  jz      short loc_10049CBD
0x10049ca8  mov     eax, [eax+28h]
0x10049cab  test    eax, eax
0x10049cad  jnz     short loc_10049CA4
0x10049caf  pop     edi
0x10049cb0  pop     esi
0x10049cb1  mov     eax, 80004005h
0x10049cb6  pop     ebx
0x10049cb7  mov     esp, ebp
0x10049cb9  pop     ebp
0x10049cba  retn    0Ch
0x10049cbd  cmp     dword ptr [eax+8], 1
0x10049cc1  jz      short loc_10049CAF
0x10049cc3  mov     edi, [ebp+arg_0]
0x10049cc6  xor     edx, edx
0x10049cc8  mov     esi, [edi+24h]
0x10049ccb  test    esi, esi
0x10049ccd  jz      short loc_10049CAF
0x10049ccf  nop
0x10049cd0  imul    ecx, edx, 34h ; '4'
0x10049cd3  cmp     ebx, [ecx+edi+28h]
0x10049cd7  jz      short loc_10049CEC
0x10049cd9  inc     edx
0x10049cda  cmp     edx, esi
0x10049cdc  jb      short loc_10049CD0
0x10049cde  pop     edi
0x10049cdf  pop     esi
0x10049ce0  mov     eax, 80004005h
0x10049ce5  pop     ebx
0x10049ce6  mov     esp, ebp
0x10049ce8  pop     ebp
0x10049ce9  retn    0Ch
0x10049cec  imul    ecx, edx, 34h ; '4'
0x10049cef  xor     ebx, ebx
0x10049cf1  add     ecx, edi
0x10049cf3  mov     [ebp+var_8], ecx
0x10049cf6  test    byte ptr [ecx+44h], 1
0x10049cfa  jz      short loc_10049D06
0x10049cfc  mov     edx, [ebp+arg_4]
0x10049cff  mov     ecx, [ecx+2Ch]
0x10049d02  add     ecx, [edx]
0x10049d04  jmp     short loc_10049D08
0x10049d06  mov     ecx, ebx
0x10049d08  mov     edi, [ebp+arg_8]
0x10049d0b  mov     esi, [edi]
0x10049d0d  lea     edx, [esi+4]
0x10049d10  mov     [edi], edx
0x10049d12  mov     edi, ebx
0x10049d14  mov     [ebp+var_10], edx
0x10049d17  test    ecx, ecx
0x10049d19  jz      loc_1004A024
0x10049d1f  mov     edx, [eax+18h]
0x10049d22  lea     edi, [eax+18h]
0x10049d25  mov     [ebp+var_4], edi
0x10049d28  test    edx, edx
0x10049d2a  jnz     short loc_10049D36
0x10049d2c  lea     ecx, [eax+20h]
0x10049d2f  mov     [ebp+var_C], ecx
0x10049d32  mov     ecx, [ecx]
0x10049d34  jmp     short loc_10049D41
0x10049d36  lea     edi, [eax+20h]
0x10049d39  mov     ecx, edx
0x10049d3b  mov     [ebp+var_C], edi
0x10049d3e  mov     edi, [ebp+var_4]
0x10049d41  dec     ecx; switch 17 cases
0x10049d42  cmp     ecx, 10h
0x10049d45  ja      def_10049D52; jumptable 10049D52 default case, cases 13,14,16
0x10049d4b  movzx   ecx, ds:byte_1004A04C[ecx]
0x10049d52  jmp     ds:jpt_10049D52[ecx*4]; switch jump
0x10049d59  test    edx, edx; jumptable 10049D52 cases 1-8,15
0x10049d5b  jnz     short loc_10049D62
0x10049d5d  mov     eax, [ebp+var_C]
0x10049d60  mov     edx, [eax]
0x10049d62  mov     eax, dword_10051944[edx*8]
0x10049d69  mov     edi, ebx
0x10049d6b  mov     edx, [ebp+arg_8]
0x10049d6e  add     eax, 3
0x10049d71  mov     ebx, [ebp+var_14]
0x10049d74  and     eax, 0FFFFFFFCh
0x10049d77  add     eax, [ebp+var_10]
0x10049d7a  inc     ebx
0x10049d7b  mov     [edx], eax
0x10049d7d  mov     eax, [ebp+var_18]
0x10049d80  jmp     loc_10049C7C
0x10049d85  mov     edx, [ebp+arg_8]; jumptable 10049D52 cases 9,10
0x10049d88  add     esi, 8
0x10049d8b  mov     [edx], esi
0x10049d8d  mov     ecx, [edi]
0x10049d8f  test    ecx, ecx
0x10049d91  jnz     short loc_10049DAE
0x10049d93  mov     eax, [eax+24h]
0x10049d96  mov     edi, ebx
0x10049d98  mov     ebx, [ebp+var_14]
0x10049d9b  add     eax, 3
0x10049d9e  and     eax, 0FFFFFFFCh
0x10049da1  add     eax, esi
0x10049da3  inc     ebx
0x10049da4  mov     [edx], eax
0x10049da6  mov     eax, [ebp+var_18]
0x10049da9  jmp     loc_10049C7C
0x10049dae  mov     eax, dword_10051944[ecx*8]
0x10049db5  mov     edi, ebx
0x10049db7  mov     ebx, [ebp+var_14]
0x10049dba  add     eax, 3
0x10049dbd  and     eax, 0FFFFFFFCh
0x10049dc0  add     eax, esi
0x10049dc2  inc     ebx
0x10049dc3  mov     [edx], eax
0x10049dc5  mov     eax, [ebp+var_18]
0x10049dc8  jmp     loc_10049C7C
0x10049dcd  mov     edx, [ebp+arg_8]; jumptable 10049D52 cases 11,12,17
0x10049dd0  lea     eax, [esi+0Ch]
0x10049dd3  mov     edi, ebx
0x10049dd5  mov     ebx, [ebp+var_14]
0x10049dd8  inc     ebx
0x10049dd9  mov     [edx], eax
0x10049ddb  mov     eax, [ebp+var_18]
0x10049dde  jmp     loc_10049C7C
0x10049de3  mov     ecx, [eax+8]; jumptable 10049D52 default case, cases 13,14,16
0x10049de6  cmp     ecx, 1
0x10049de9  jz      short loc_10049E1D
0x10049deb  cmp     ecx, 2
0x10049dee  jz      short loc_10049E1B
0x10049df0  test    ecx, ecx
0x10049df2  jnz     short loc_10049E08
0x10049df4  movzx   edx, word ptr [eax+1Ch]
0x10049df8  lea     edi, [eax+1Ch]
0x10049dfb  mov     [ebp+var_10], edx
0x10049dfe  lea     esi, [eax+16h]
0x10049e01  mov     edx, [ebp+var_4]
0x10049e04  mov     edx, [edx]
0x10049e06  jmp     short loc_10049E2A
0x10049e08  lea     edi, [eax+16h]
0x10049e0b  mov     edx, 0Ah
0x10049e10  lea     esi, [eax+1Ch]
0x10049e13  mov     [ebp+var_8], edi
0x10049e16  jmp     loc_10049F12
0x10049e1b  mov     edx, [edi]
0x10049e1d  movzx   edi, word ptr [eax+16h]
0x10049e21  lea     esi, [eax+16h]
0x10049e24  mov     [ebp+var_10], edi
0x10049e27  lea     edi, [eax+1Ch]
0x10049e2a  cmp     word ptr [ebp+var_10], bx
0x10049e2e  jnz     loc_10049EE4
0x10049e34  mov     ecx, [ebp+var_C]
0x10049e37  mov     edi, ebx
0x10049e39  cmp     [ecx], ebx
0x10049e3b  jnz     loc_10049F7F
0x10049e41  mov     ecx, [ebp+var_8]
0x10049e44  movzx   ecx, word ptr [ecx+58h]
0x10049e48  mov     esi, ecx
0x10049e4a  and     ecx, 0FFFF8FFFh
0x10049e50  sub     ecx, 80h
0x10049e56  jz      short loc_10049EBE
0x10049e58  sub     ecx, 2
0x10049e5b  jz      short loc_10049EAE
0x10049e5d  xor     edx, edx
0x10049e5f  xor     ecx, ecx
0x10049e61  and     esi, 8FFFh
0x10049e67  nop     word ptr [eax+eax+00000000h]
0x10049e70  cmp     si, word_100518A0[ecx*8]
0x10049e78  jz      short loc_10049E82
0x10049e7a  inc     ecx
0x10049e7b  cmp     ecx, 0Dh
0x10049e7e  jb      short loc_10049E70
0x10049e80  jmp     short loc_10049E89
0x10049e82  mov     edx, dword_100518A4[ecx*8]
0x10049e89  mov     ecx, [ebp+var_4]
0x10049e8c  mov     [ecx], edx
0x10049e8e  test    edx, edx
0x10049e90  jz      short loc_10049E97
0x10049e92  cmp     edx, 10h
0x10049e95  jnz     short loc_10049ECC
0x10049e97  mov     dword ptr [ecx], 0Ch
0x10049e9d  mov     ecx, 82h
0x10049ea2  mov     [eax+16h], cx
0x10049ea6  lea     edx, [ecx-76h]
0x10049ea9  jmp     loc_10049F7F
0x10049eae  mov     ecx, [ebp+var_4]
0x10049eb1  mov     edx, 0Ch
0x10049eb6  mov     dword ptr [ecx], 0Ch
0x10049ebc  jmp     short loc_10049ECC
0x10049ebe  mov     ecx, [ebp+var_4]
0x10049ec1  mov     edx, 0Bh
0x10049ec6  mov     dword ptr [ecx], 0Bh
0x10049ecc  mov     ecx, [ebp+var_8]
0x10049ecf  mov     ebx, 8FFFh
0x10049ed4  mov     cx, [ecx+58h]
0x10049ed8  and     cx, bx
0x10049edb  mov     [eax+16h], cx
0x10049edf  jmp     loc_10049F7F
0x10049ee4  mov     [ebp+var_8], esi
0x10049ee7  mov     [ebp+var_10], edi
0x10049eea  cmp     ecx, 1
0x10049eed  jz      short loc_10049F09
0x10049eef  cmp     ecx, 2
0x10049ef2  jz      short loc_10049F09
0x10049ef4  mov     esi, edi
0x10049ef6  test    ecx, ecx
0x10049ef8  jnz     short loc_10049EFF
0x10049efa  movzx   edx, word ptr [edi]
0x10049efd  jmp     short loc_10049F0F
0x10049eff  mov     edi, [ebp+var_8]
0x10049f02  mov     edx, 0Ah
0x10049f07  jmp     short loc_10049F12
0x10049f09  movzx   edx, word ptr [esi]
0x10049f0c  mov     esi, [ebp+var_10]
0x10049f0f  mov     edi, [ebp+var_8]
0x10049f12  movzx   edx, dx
0x10049f15  and     edx, 0FFFF8FFFh
0x10049f1b  sub     edx, 80h
0x10049f21  jz      loc_10049FAF
0x10049f27  sub     edx, 2
0x10049f2a  jz      short loc_10049F9F
0x10049f2c  cmp     ecx, 1
0x10049f2f  jz      short loc_10049F46
0x10049f31  cmp     ecx, 2
0x10049f34  jz      short loc_10049F46
0x10049f36  test    ecx, ecx
0x10049f38  jnz     short loc_10049F3F
0x10049f3a  movzx   esi, word ptr [esi]
0x10049f3d  jmp     short loc_10049F49
0x10049f3f  mov     esi, 0Ah
0x10049f44  jmp     short loc_10049F49
0x10049f46  movzx   esi, word ptr [edi]
0x10049f49  xor     edx, edx
0x10049f4b  xor     ecx, ecx
0x10049f4d  and     esi, 8FFFh
0x10049f53  mov     edi, ebx
0x10049f55  cmp     si, word_100518A0[ecx*8]
0x10049f5d  jz      short loc_10049F67
0x10049f5f  inc     ecx
0x10049f60  cmp     ecx, 0Dh
0x10049f63  jb      short loc_10049F55
0x10049f65  jmp     short loc_10049F6E
0x10049f67  mov     edx, dword_100518A4[ecx*8]
0x10049f6e  mov     ebx, [ebp+var_4]
0x10049f71  mov     ecx, [ebp+var_8]
0x10049f74  mov     [ebx], edx
0x10049f76  test    edx, edx
0x10049f78  jz      short loc_10049F8A
0x10049f7a  cmp     edx, 10h
0x10049f7d  jz      short loc_10049F8A
0x10049f7f  test    edx, edx
0x10049f81  jnz     short loc_10049FBF
0x10049f83  mov     ebx, [ebp+var_C]
0x10049f86  mov     ecx, [ebx]
0x10049f88  jmp     short loc_10049FC4
0x10049f8a  mov     edx, 82h
0x10049f8f  mov     dword ptr [ebx], 0Ch
0x10049f95  mov     [ecx], dx
0x10049f98  mov     edx, 0Ch
0x10049f9d  jmp     short loc_10049FBF
0x10049f9f  mov     ecx, [ebp+var_4]
0x10049fa2  mov     edx, 0Ch
0x10049fa7  mov     dword ptr [ecx], 0Ch
0x10049fad  jmp     short loc_10049FBD
0x10049faf  mov     ecx, [ebp+var_4]
0x10049fb2  mov     edx, 0Bh
0x10049fb7  mov     dword ptr [ecx], 0Bh
0x10049fbd  mov     edi, ebx
0x10049fbf  mov     ebx, [ebp+var_C]
0x10049fc2  mov     ecx, edx
0x10049fc4  cmp     ecx, 0Bh
0x10049fc7  jz      short loc_1004A009
0x10049fc9  test    edx, edx
0x10049fcb  jnz     short loc_10049FD1
0x10049fcd  mov     ecx, [ebx]
0x10049fcf  jmp     short loc_10049FD3
0x10049fd1  mov     ecx, edx
0x10049fd3  cmp     ecx, 0Ch
  ... truncated ...
```
