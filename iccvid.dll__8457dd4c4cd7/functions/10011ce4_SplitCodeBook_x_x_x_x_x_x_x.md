# SplitCodeBook(x,x,x,x,x,x,x)

- ea: `0x10011ce4`
- end: `0x10011fe6`
- name: `_SplitCodeBook@28`
- size: `770`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10010735`
- `0x10010a12`

## callees

- `0x10011ce4`
- `0x10011fec`

## pseudocode

```c
__int16 __fastcall SplitCodeBook(int a1, __int16 a2, int a3, int a4, int *a5, __int16 a6, unsigned __int8 a7)
{
  int v8; // ecx
  int v9; // ebx
  int v10; // edx
  int v11; // eax
  int v12; // ecx
  int v13; // esi
  int v14; // edi
  int v15; // esi
  __int16 v16; // cx
  unsigned int v17; // ecx
  unsigned int v18; // edx
  int v19; // eax
  unsigned int v20; // ecx
  _BYTE *v21; // edx
  char v22; // al
  char v23; // al
  __int16 v24; // ax
  int v25; // eax
  bool v26; // zf
  int v27; // edx
  int v28; // eax
  int v29; // edi
  char v30; // cl
  char v31; // al
  char v32; // dl
  char v33; // al
  char v34; // dl
  char v35; // al
  int v36; // esi
  int v37; // eax
  int *v39; // [esp-24h] [ebp-C8h]
  int v40; // [esp-20h] [ebp-C4h] BYREF
  unsigned int v41; // [esp-1Ch] [ebp-C0h]
  int v42; // [esp-18h] [ebp-BCh]
  int v43; // [esp-14h] [ebp-B8h]
  int v44; // [esp-10h] [ebp-B4h]
  _DWORD *v45; // [esp-Ch] [ebp-B0h]
  _DWORD *v46; // [esp-8h] [ebp-ACh]
  _DWORD *v47; // [esp-4h] [ebp-A8h]
  _BYTE v48[24]; // [esp+10h] [ebp-94h] BYREF
  _DWORD v49[4]; // [esp+28h] [ebp-7Ch] BYREF
  _DWORD v50[6]; // [esp+38h] [ebp-6Ch] BYREF
  _DWORD v51[6]; // [esp+50h] [ebp-54h] BYREF
  int v52; // [esp+68h] [ebp-3Ch]
  int v53; // [esp+6Ch] [ebp-38h]
  int v54; // [esp+70h] [ebp-34h]
  int v55; // [esp+74h] [ebp-30h]
  unsigned int v56; // [esp+78h] [ebp-2Ch]
  unsigned int v57; // [esp+7Ch] [ebp-28h]
  unsigned int v58; // [esp+80h] [ebp-24h]
  _BYTE *v59; // [esp+84h] [ebp-20h]
  int v60; // [esp+88h] [ebp-1Ch]
  unsigned int v61; // [esp+8Ch] [ebp-18h]
  unsigned int v62; // [esp+90h] [ebp-14h]
  int v63; // [esp+94h] [ebp-10h]
  unsigned int v64; // [esp+98h] [ebp-Ch]
  char v65; // [esp+9Fh] [ebp-5h]

  v8 = 460 * a2;
  v9 = 0;
  v10 = *(__int16 *)(a1 + 8) - a2;
  v11 = *(_DWORD *)(a1 + 4);
  v12 = *(_DWORD *)a1 + v8;
  v13 = *(_DWORD *)(a1 + 12);
  v14 = *a5;
  v53 = v12;
  v15 = v13 - a3;
  v63 = v14;
  v54 = v10;
  v55 = v15;
  v16 = 0;
  v59 = (_BYTE *)(v11 + 8 * a3);
  v60 = 0;
  if ( a6 )
  {
    while ( 1 )
    {
      v17 = v10;
      v18 = 0;
      LOBYTE(v52) = *(_BYTE *)(v14 + 6);
      v19 = v53;
      v65 = 0;
      if ( v54 )
      {
        do
        {
          v64 = --v17;
          if ( (a7 & *(_BYTE *)(v19 + 7)) == 0 && *(_DWORD *)(v19 + 40) > v18 )
          {
            v9 = v19;
            v18 = *(_DWORD *)(v19 + 40);
            v65 = *(_BYTE *)(v19 + 6);
            v17 = v64;
          }
          v19 += 460;
        }
        while ( v17 );
      }
      if ( !v18 )
        goto LABEL_39;
      v20 = *(_DWORD *)(v9 + 12);
      v21 = v59;
      v64 = v20;
      if ( !v20 )
      {
LABEL_20:
        v24 = a6;
        *(_DWORD *)(v9 + 40) = 0;
        goto LABEL_38;
      }
      v22 = v65;
      while ( 1 )
      {
        if ( v21[6] != v22 )
          goto LABEL_19;
        v20 = v64;
        if ( v21[7] != (_BYTE)a4 )
          goto LABEL_19;
        v23 = *v21;
        v20 = --v64;
        if ( v23 != *(_BYTE *)v9
          || v21[1] != *(_BYTE *)(v9 + 1)
          || v21[2] != *(_BYTE *)(v9 + 2)
          || v21[3] != *(_BYTE *)(v9 + 3)
          || v21[4] != *(_BYTE *)(v9 + 4)
          || v21[5] != *(_BYTE *)(v9 + 5) )
        {
          break;
        }
        v22 = v65;
LABEL_19:
        v21 += 8;
        if ( !v20 )
          goto LABEL_20;
      }
      if ( !v21 )
        goto LABEL_20;
      *(_DWORD *)v14 = *(_DWORD *)v21;
      *(_WORD *)(v14 + 4) = *((_WORD *)v21 + 2);
      v47 = v49;
      v46 = v50;
      v45 = v51;
      v25 = *(_DWORD *)v21;
      v44 = v15;
      v43 = a4;
      v42 = v52;
      v41 = v20;
      v39 = &v40;
      v40 = v25;
      LOWORD(v41) = *((_WORD *)v21 + 2);
      LOWORD(v39) = *(_WORD *)(v9 + 4);
      SplitTwoEntries(*(_DWORD *)v9, v39, v25, v41, v52, a4, v15, v51, v50, v49);
      *(_DWORD *)(v9 + 12) = v49[0];
      *(_DWORD *)(v9 + 40) = v49[2];
      *(_DWORD *)(v14 + 12) = v49[1];
      *(_DWORD *)(v14 + 40) = v49[3];
      if ( !*(_DWORD *)(v9 + 12) )
      {
        v26 = (*(_BYTE *)(v9 + 7) & 2) == 0;
        v61 = v9 + 7;
        if ( !v26 )
        {
          v27 = v9;
          v9 = v14;
          v63 = v27;
          qmemcpy(v48, v51, sizeof(v48));
          v28 = *(_DWORD *)(v14 + 8);
          *(_BYTE *)(v14 + 7) = 2;
          qmemcpy(v51, v50, sizeof(v51));
          *(_DWORD *)(v27 + 8) = v28;
          qmemcpy(v50, v48, sizeof(v50));
          *(_BYTE *)v61 |= 1u;
          v14 = v27;
        }
      }
      if ( (*(_BYTE *)(v9 + 7) & 2) != 0 )
      {
        v29 = *(_DWORD *)(v9 + 12);
        v58 = ((v29 >> 1) + v51[0]) / (unsigned int)v29;
        v64 = ((v29 >> 1) + v51[1]) / (unsigned int)v29;
        v62 = ((v29 >> 1) + v51[2]) / (unsigned int)v29;
        v30 = v62;
        v57 = ((v29 >> 1) + v51[3]) / (unsigned int)v29;
        v56 = ((v29 >> 1) + v51[4]) / (unsigned int)v29;
        v61 = ((v29 >> 1) + v51[5]) / (unsigned int)v29;
        v31 = v64;
        if ( *(_BYTE *)v9 != (_BYTE)v58
          || *(_BYTE *)(v9 + 1) != (_BYTE)v64
          || *(_BYTE *)(v9 + 2) != (_BYTE)v62
          || *(_BYTE *)(v9 + 3) != (_BYTE)v57
          || (v31 = v64, *(_BYTE *)(v9 + 4) != (_BYTE)v56)
          || (v30 = v62, *(_BYTE *)(v9 + 5) != (_BYTE)v61) )
        {
          v32 = v58;
          *(_BYTE *)(v9 + 7) |= 4u;
          *(_BYTE *)(v9 + 1) = v31;
          v33 = v56;
          *(_BYTE *)v9 = v32;
          v34 = v57;
          *(_BYTE *)(v9 + 4) = v33;
          v35 = v61;
          *(_BYTE *)(v9 + 2) = v30;
          *(_BYTE *)(v9 + 3) = v34;
          *(_BYTE *)(v9 + 5) = v35;
        }
        v14 = v63;
      }
      v36 = *(_DWORD *)(v14 + 12);
      if ( v36 )
      {
        v37 = v50[0];
        *(_BYTE *)(v14 + 7) = 6;
        *(_BYTE *)v14 = ((v36 >> 1) + v37) / (unsigned int)v36;
        *(_BYTE *)(v14 + 1) = ((v36 >> 1) + v50[1]) / (unsigned int)v36;
        *(_BYTE *)(v14 + 2) = ((v36 >> 1) + v50[2]) / (unsigned int)v36;
        *(_BYTE *)(v14 + 3) = ((v36 >> 1) + v50[3]) / (unsigned int)v36;
        *(_BYTE *)(v14 + 4) = ((v36 >> 1) + v50[4]) / (unsigned int)v36;
        ++v60;
        *(_BYTE *)(v14 + 5) = ((v36 >> 1) + v50[5]) / (unsigned int)v36;
        v14 = *(_DWORD *)(v14 + 8);
        v24 = a6 - 1;
        v63 = v14;
        --a6;
      }
      else
      {
        v24 = a6;
      }
      v15 = v55;
LABEL_38:
      v10 = v54;
      if ( !v24 )
      {
LABEL_39:
        v16 = v60;
        break;
      }
    }
  }
  *a5 = v14;
  return v16;
}

```

## disassembly

```asm
0x10011ce4  mov     edi, edi
0x10011ce6  push    ebp
0x10011ce7  mov     ebp, esp
0x10011ce9  sub     esp, 98h
0x10011cef  push    ebx
0x10011cf0  push    esi
0x10011cf1  mov     esi, ecx
0x10011cf3  movsx   eax, dx
0x10011cf6  imul    ecx, eax, 1CCh
0x10011cfc  xor     ebx, ebx
0x10011cfe  push    edi
0x10011cff  mov     edi, [ebp+arg_8]
0x10011d02  movsx   edx, word ptr [esi+8]
0x10011d06  sub     edx, eax
0x10011d08  mov     eax, [esi+4]
0x10011d0b  add     ecx, [esi]
0x10011d0d  mov     esi, [esi+0Ch]
0x10011d10  mov     edi, [edi]
0x10011d12  mov     [ebp+var_38], ecx
0x10011d15  mov     ecx, [ebp+arg_0]
0x10011d18  sub     esi, ecx
0x10011d1a  mov     [ebp+var_10], edi
0x10011d1d  mov     [ebp+var_34], edx
0x10011d20  mov     [ebp+var_30], esi
0x10011d23  lea     eax, [eax+ecx*8]
0x10011d26  xor     ecx, ecx
0x10011d28  mov     [ebp+var_20], eax
0x10011d2b  mov     [ebp+var_1C], ecx
0x10011d2e  cmp     word ptr [ebp+arg_C], cx
0x10011d32  jz      loc_10011FD7
0x10011d38  mov     al, [edi+6]
0x10011d3b  mov     ecx, edx
0x10011d3d  xor     edx, edx
0x10011d3f  mov     byte ptr [ebp+var_3C], al
0x10011d42  mov     eax, [ebp+var_38]
0x10011d45  mov     [ebp+var_5], 0
0x10011d49  cmp     [ebp+var_34], edx
0x10011d4c  jz      short loc_10011D79
0x10011d4e  dec     ecx
0x10011d4f  mov     [ebp+var_C], ecx
0x10011d52  mov     cl, [ebp+arg_10]
0x10011d55  test    [eax+7], cl
0x10011d58  mov     ecx, [ebp+var_C]
0x10011d5b  jnz     short loc_10011D70
0x10011d5d  cmp     [eax+28h], edx
0x10011d60  jbe     short loc_10011D70
0x10011d62  mov     cl, [eax+6]
0x10011d65  mov     ebx, eax
0x10011d67  mov     edx, [eax+28h]
0x10011d6a  mov     [ebp+var_5], cl
0x10011d6d  mov     ecx, [ebp+var_C]
0x10011d70  add     eax, 1CCh
0x10011d75  test    ecx, ecx
0x10011d77  jnz     short loc_10011D4E
0x10011d79  test    edx, edx
0x10011d7b  jz      loc_10011FD4
0x10011d81  mov     ecx, [ebx+0Ch]
0x10011d84  mov     edx, [ebp+var_20]
0x10011d87  mov     [ebp+var_C], ecx
0x10011d8a  test    ecx, ecx
0x10011d8c  jz      short loc_10011DDD
0x10011d8e  mov     al, [ebp+var_5]
0x10011d91  cmp     [edx+6], al
0x10011d94  jnz     short loc_10011DD6
0x10011d96  mov     ecx, [ebp+arg_4]
0x10011d99  cmp     [edx+7], cl
0x10011d9c  mov     ecx, [ebp+var_C]
0x10011d9f  jnz     short loc_10011DD6
0x10011da1  mov     al, [edx]
0x10011da3  dec     ecx
0x10011da4  mov     [ebp+var_C], ecx
0x10011da7  cmp     al, [ebx]
0x10011da9  jnz     short loc_10011DEC
0x10011dab  mov     al, [edx+1]
0x10011dae  cmp     al, [ebx+1]
0x10011db1  jnz     short loc_10011DEC
0x10011db3  mov     al, [edx+2]
0x10011db6  cmp     al, [ebx+2]
0x10011db9  jnz     short loc_10011DEC
0x10011dbb  mov     al, [edx+3]
0x10011dbe  cmp     al, [ebx+3]
0x10011dc1  jnz     short loc_10011DEC
0x10011dc3  mov     al, [edx+4]
0x10011dc6  cmp     al, [ebx+4]
0x10011dc9  jnz     short loc_10011DEC
0x10011dcb  mov     al, [edx+5]
0x10011dce  cmp     al, [ebx+5]
0x10011dd1  jnz     short loc_10011DEC
0x10011dd3  mov     al, [ebp+var_5]
0x10011dd6  add     edx, 8
0x10011dd9  test    ecx, ecx
0x10011ddb  jnz     short loc_10011D91
0x10011ddd  mov     eax, [ebp+arg_C]
0x10011de0  mov     dword ptr [ebx+28h], 0
0x10011de7  jmp     loc_10011FC8
0x10011dec  test    edx, edx
0x10011dee  jz      short loc_10011DDD
0x10011df0  mov     eax, [edx]
0x10011df2  mov     [edi], eax
0x10011df4  mov     ax, [edx+4]
0x10011df8  mov     [edi+4], ax
0x10011dfc  lea     eax, [ebp+var_7C]
0x10011dff  push    eax
0x10011e00  lea     eax, [ebp+var_6C]
0x10011e03  push    eax
0x10011e04  lea     eax, [ebp+var_54]
0x10011e07  push    eax
0x10011e08  mov     eax, [edx]
0x10011e0a  push    esi
0x10011e0b  push    [ebp+arg_4]
0x10011e0e  push    [ebp+var_3C]
0x10011e11  push    ecx
0x10011e12  push    ecx
0x10011e13  mov     ecx, esp
0x10011e15  push    ecx
0x10011e16  push    ecx
0x10011e17  mov     [ecx], eax
0x10011e19  mov     ax, [edx+4]
0x10011e1d  mov     dl, [ebp+var_5]
0x10011e20  mov     [ecx+4], ax
0x10011e24  mov     ecx, esp
0x10011e26  mov     eax, [ebx]
0x10011e28  mov     [ecx], eax
0x10011e2a  mov     ax, [ebx+4]
0x10011e2e  mov     [ecx+4], ax
0x10011e32  mov     ecx, [ebp+var_20]
0x10011e35  call    _SplitTwoEntries@48; SplitTwoEntries(x,x,x,x,x,x,x,x,x,x,x,x)
0x10011e3a  mov     eax, [ebp+var_7C]
0x10011e3d  mov     [ebx+0Ch], eax
0x10011e40  mov     eax, [ebp+var_74]
0x10011e43  mov     [ebx+28h], eax
0x10011e46  mov     eax, [ebp+var_78]
0x10011e49  mov     [edi+0Ch], eax
0x10011e4c  mov     eax, [ebp+var_70]
0x10011e4f  mov     [edi+28h], eax
0x10011e52  cmp     dword ptr [ebx+0Ch], 0
0x10011e56  jnz     short loc_10011EA3
0x10011e58  lea     eax, [ebx+7]
0x10011e5b  test    byte ptr [eax], 2
0x10011e5e  mov     [ebp+var_18], eax
0x10011e61  jz      short loc_10011EA3
0x10011e63  push    6
0x10011e65  mov     edx, ebx
0x10011e67  lea     esi, [ebp+var_54]
0x10011e6a  mov     ebx, edi
0x10011e6c  mov     [ebp+var_10], edx
0x10011e6f  pop     ecx
0x10011e70  lea     edi, [ebp+var_94]
0x10011e76  rep movsd
0x10011e78  mov     eax, [ebx+8]
0x10011e7b  lea     esi, [ebp+var_6C]
0x10011e7e  push    6
0x10011e80  pop     ecx
0x10011e81  lea     edi, [ebp+var_54]
0x10011e84  mov     byte ptr [ebx+7], 2
0x10011e88  rep movsd
0x10011e8a  push    6
0x10011e8c  mov     [edx+8], eax
0x10011e8f  lea     esi, [ebp+var_94]
0x10011e95  mov     eax, [ebp+var_18]
0x10011e98  lea     edi, [ebp+var_6C]
0x10011e9b  pop     ecx
0x10011e9c  rep movsd
0x10011e9e  or      byte ptr [eax], 1
0x10011ea1  mov     edi, edx
0x10011ea3  test    byte ptr [ebx+7], 2
0x10011ea7  jz      loc_10011F5A
0x10011ead  mov     edi, [ebx+0Ch]
0x10011eb0  xor     edx, edx
0x10011eb2  mov     eax, [ebp+var_54]
0x10011eb5  mov     esi, edi
0x10011eb7  sar     esi, 1
0x10011eb9  add     eax, esi
0x10011ebb  div     edi
0x10011ebd  xor     edx, edx
0x10011ebf  mov     [ebp+var_24], eax
0x10011ec2  mov     eax, [ebp+var_50]
0x10011ec5  lea     eax, [esi+eax]
0x10011ec8  div     edi
0x10011eca  xor     edx, edx
0x10011ecc  mov     [ebp+var_C], eax
0x10011ecf  mov     eax, [ebp+var_4C]
0x10011ed2  lea     eax, [esi+eax]
0x10011ed5  div     edi
0x10011ed7  xor     edx, edx
0x10011ed9  mov     [ebp+var_14], eax
0x10011edc  mov     eax, [ebp+var_48]
0x10011edf  mov     ecx, [ebp+var_14]
0x10011ee2  lea     eax, [esi+eax]
0x10011ee5  div     edi
0x10011ee7  xor     edx, edx
0x10011ee9  mov     [ebp+var_28], eax
0x10011eec  mov     eax, [ebp+var_44]
0x10011eef  lea     eax, [esi+eax]
0x10011ef2  div     edi
0x10011ef4  xor     edx, edx
0x10011ef6  mov     [ebp+var_2C], eax
0x10011ef9  mov     eax, [ebp+var_40]
0x10011efc  lea     eax, [esi+eax]
0x10011eff  div     edi
0x10011f01  mov     [ebp+var_18], eax
0x10011f04  mov     eax, [ebp+var_24]
0x10011f07  cmp     [ebx], al
0x10011f09  mov     eax, [ebp+var_C]
0x10011f0c  jnz     short loc_10011F36
0x10011f0e  cmp     [ebx+1], al
0x10011f11  jnz     short loc_10011F36
0x10011f13  cmp     [ebx+2], cl
0x10011f16  jnz     short loc_10011F36
0x10011f18  mov     edx, [ebp+var_28]
0x10011f1b  cmp     [ebx+3], dl
0x10011f1e  jnz     short loc_10011F36
0x10011f20  mov     eax, [ebp+var_2C]
0x10011f23  cmp     [ebx+4], al
0x10011f26  mov     eax, [ebp+var_C]
0x10011f29  jnz     short loc_10011F36
0x10011f2b  mov     ecx, [ebp+var_18]
0x10011f2e  cmp     [ebx+5], cl
0x10011f31  mov     ecx, [ebp+var_14]
0x10011f34  jz      short loc_10011F57
0x10011f36  mov     edx, [ebp+var_24]
0x10011f39  or      byte ptr [ebx+7], 4
0x10011f3d  mov     [ebx+1], al
0x10011f40  mov     eax, [ebp+var_2C]
0x10011f43  mov     [ebx], dl
0x10011f45  mov     edx, [ebp+var_28]
0x10011f48  mov     [ebx+4], al
0x10011f4b  mov     eax, [ebp+var_18]
0x10011f4e  mov     [ebx+2], cl
0x10011f51  mov     [ebx+3], dl
0x10011f54  mov     [ebx+5], al
0x10011f57  mov     edi, [ebp+var_10]
0x10011f5a  mov     esi, [edi+0Ch]
0x10011f5d  test    esi, esi
0x10011f5f  jz      short loc_10011FC2
0x10011f61  mov     eax, [ebp+var_6C]
0x10011f64  xor     edx, edx
0x10011f66  mov     ecx, esi
0x10011f68  mov     byte ptr [edi+7], 6
0x10011f6c  sar     ecx, 1
0x10011f6e  add     eax, ecx
0x10011f70  div     esi
0x10011f72  xor     edx, edx
0x10011f74  mov     [edi], al
0x10011f76  mov     eax, [ebp+var_68]
0x10011f79  add     eax, ecx
0x10011f7b  div     esi
0x10011f7d  xor     edx, edx
0x10011f7f  mov     [edi+1], al
0x10011f82  mov     eax, [ebp+var_64]
0x10011f85  add     eax, ecx
0x10011f87  div     esi
0x10011f89  xor     edx, edx
0x10011f8b  mov     [edi+2], al
0x10011f8e  mov     eax, [ebp+var_60]
0x10011f91  add     eax, ecx
0x10011f93  div     esi
0x10011f95  xor     edx, edx
0x10011f97  mov     [edi+3], al
0x10011f9a  mov     eax, [ebp+var_5C]
0x10011f9d  add     eax, ecx
0x10011f9f  div     esi
0x10011fa1  xor     edx, edx
0x10011fa3  mov     [edi+4], al
0x10011fa6  mov     eax, [ebp+var_58]
0x10011fa9  add     eax, ecx
0x10011fab  div     esi
0x10011fad  inc     [ebp+var_1C]
0x10011fb0  mov     [edi+5], al
0x10011fb3  mov     eax, [ebp+arg_C]
0x10011fb6  mov     edi, [edi+8]
0x10011fb9  dec     eax
0x10011fba  mov     [ebp+var_10], edi
0x10011fbd  mov     [ebp+arg_C], eax
0x10011fc0  jmp     short loc_10011FC5
0x10011fc2  mov     eax, [ebp+arg_C]
0x10011fc5  mov     esi, [ebp+var_30]
0x10011fc8  mov     edx, [ebp+var_34]
0x10011fcb  test    ax, ax
0x10011fce  jnz     loc_10011D38
0x10011fd4  mov     ecx, [ebp+var_1C]
0x10011fd7  mov     eax, [ebp+arg_8]
0x10011fda  mov     [eax], edi
0x10011fdc  mov     ax, cx
0x10011fdf  pop     edi
0x10011fe0  pop     esi
0x10011fe1  pop     ebx
0x10011fe2  leave
0x10011fe3  retn    14h
```
