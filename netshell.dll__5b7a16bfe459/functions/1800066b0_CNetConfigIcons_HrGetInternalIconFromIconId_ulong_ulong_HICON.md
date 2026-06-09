# CNetConfigIcons::HrGetInternalIconFromIconId(ulong,ulong,HICON__ * &)

- ea: `0x1800066b0`
- end: `0x180006efd`
- name: `?HrGetInternalIconFromIconId@CNetConfigIcons@@AEAAJKKAEAPEAUHICON__@@@Z`
- size: `2125`
- prototype: `__int64 __fastcall(CNetConfigIcons *__hidden this, unsigned int, unsigned int, HICON *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800438dc`

## callees

- `0x1800066b0`
- `0x18000a6d8`
- `0x180019a24`
- `0x180043cc0`
- `0x1800608f8`
- `0x180060a00`
- `0x180060a68`
- `0x180060ad4`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x180006c84`
- `USER32!GetSystemMetrics` at `0x180006c84`
- `USER32!DestroyIcon` at `0x180006e1d`
- `USER32!DestroyIcon` at `0x180006e85`
- `USER32!DestroyIcon` at `0x180006e95`
- `USER32!DestroyIcon` at `0x180006ea3`
- `USER32!DestroyIcon` at `0x180006e1d`
- `USER32!DestroyIcon` at `0x180006e85`
- `USER32!DestroyIcon` at `0x180006e95`
- `USER32!DestroyIcon` at `0x180006ea3`
- `USER32!LoadImageW` at `0x180006c42`
- `USER32!LoadImageW` at `0x180006c6e`
- `USER32!LoadImageW` at `0x180006cae`
- `USER32!LoadImageW` at `0x180006c42`
- `USER32!LoadImageW` at `0x180006c6e`
- `USER32!LoadImageW` at `0x180006cae`
- `USER32!CopyIcon` at `0x180006e4f`
- `USER32!CopyIcon` at `0x180006e4f`

## pseudocode

```c
__int64 __fastcall CNetConfigIcons::HrGetInternalIconFromIconId(
        HINSTANCE *this,
        unsigned int a2,
        unsigned int a3,
        HICON *a4)
{
  int v8; // edx
  int v9; // r9d
  int v10; // r8d
  int v11; // ebp
  int v12; // r14d
  unsigned int k; // r10d
  __int64 v14; // r11
  unsigned int j; // r10d
  __int64 v16; // r14
  int v17; // r11d
  int v18; // ecx
  unsigned int m; // r10d
  int v20; // eax
  _DWORD *v21; // r15
  _DWORD *v22; // r15
  int v23; // eax
  int v24; // eax
  _DWORD *v25; // r15
  int v26; // eax
  int v27; // eax
  _DWORD *v28; // r15
  int v29; // eax
  int v30; // eax
  _DWORD *v31; // r15
  int v32; // eax
  int v33; // eax
  _DWORD *v34; // r15
  int v35; // eax
  int v36; // eax
  _DWORD *v37; // r15
  int v38; // eax
  int v39; // eax
  _DWORD *v40; // r15
  int v41; // eax
  int v42; // eax
  _DWORD *v43; // r15
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  HICON v48; // r15
  HICON v49; // r12
  __int64 **v50; // rcx
  HICON *v51; // rbp
  unsigned int v52; // eax
  __int64 *v53; // r8
  __int64 *v54; // rdx
  __int64 *v55; // r9
  __int64 *v56; // rax
  struct _IMAGELIST *v57; // r8
  __int64 *v58; // rax
  __int64 v59; // rcx
  bool v60; // zf
  int v61; // r14d
  HICON v62; // rax
  int v63; // eax
  int v64; // [rsp+30h] [rbp-B8h]
  unsigned int v65; // [rsp+30h] [rbp-B8h]
  struct _IMAGELIST *himl; // [rsp+38h] [rbp-B0h]
  unsigned int v67; // [rsp+40h] [rbp-A8h] BYREF
  int i; // [rsp+48h] [rbp-A0h]
  HICON *v69; // [rsp+50h] [rbp-98h]
  HICON hicon; // [rsp+58h] [rbp-90h]
  HICON ImageW; // [rsp+60h] [rbp-88h]
  HICON hIcon[3]; // [rsp+68h] [rbp-80h]
  _BYTE v73[28]; // [rsp+80h] [rbp-68h] BYREF
  int v74; // [rsp+9Ch] [rbp-4Ch]

  v69 = a4;
  if ( (a3 & 0xC0000000) != 0x40000000 )
    return 2147942487LL;
  v8 = a3 & 0x7F;
  v9 = a3 & 0x100000;
  v10 = a3 & 0x3F80;
  v11 = -2147467259;
  if ( (a3 & 0xE0000) != 0 )
  {
    for ( j = 0; j < 3; ++j )
    {
      v16 = j;
      if ( (a3 & 0xE0000) == LODWORD(qword_18007A450[v16]) )
      {
        v12 = HIDWORD(qword_18007A450[v16]);
        goto LABEL_5;
      }
    }
  }
  v12 = 0;
LABEL_5:
  if ( (a3 & 0x1C000) != 0 )
  {
    for ( k = 0; k < 5; ++k )
    {
      v14 = k;
      if ( (a3 & 0x1C000) == LODWORD(qword_18007A400[v14]) )
      {
        v17 = HIDWORD(qword_18007A400[v14]);
        goto LABEL_17;
      }
    }
  }
  v17 = 0;
LABEL_17:
  v18 = 0;
  for ( m = 0; m < 0x12; m += 9 )
  {
    v20 = *((_DWORD *)&qword_18007A1D8[23] + 5 * (int)m + 1);
    v21 = (_DWORD *)&qword_18007A1D8[23] + 5 * (int)m;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v20 )
        goto LABEL_31;
    }
    else
    {
      if ( v20 )
        goto LABEL_31;
      if ( v10 != *v21 )
      {
        v22 = (_DWORD *)&qword_18007A298[1] + 5 * (int)m + 1;
        goto LABEL_32;
      }
    }
    v23 = 0;
    v18 = v21[3];
    if ( (v21[2] & 0x1C000) != 0 )
      v23 = v17;
    v17 = v23;
    v24 = 0;
    if ( (v21[2] & 0xE0000) != 0 )
      v24 = v12;
    v12 = v24;
    if ( v9 && v21[4] && !v24 )
      v18 = v21[4];
LABEL_31:
    v22 = (_DWORD *)&qword_18007A298[1] + 5 * (int)m + 1;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v22[1] )
        goto LABEL_44;
      goto LABEL_36;
    }
LABEL_32:
    if ( v22[1] )
      goto LABEL_44;
    if ( v10 != *v22 )
    {
      v25 = (_DWORD *)&qword_18007A298[4] + 5 * (int)m;
      goto LABEL_45;
    }
LABEL_36:
    v26 = 0;
    v18 = v22[3];
    if ( (v22[2] & 0x1C000) != 0 )
      v26 = v17;
    v17 = v26;
    v27 = 0;
    if ( (v22[2] & 0xE0000) != 0 )
      v27 = v12;
    v12 = v27;
    if ( v9 && v22[4] && !v27 )
      v18 = v22[4];
LABEL_44:
    v25 = (_DWORD *)&qword_18007A298[4] + 5 * (int)m;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v25[1] )
        goto LABEL_57;
      goto LABEL_49;
    }
LABEL_45:
    if ( v25[1] )
      goto LABEL_57;
    if ( v10 != *v25 )
    {
      v28 = (_DWORD *)&qword_18007A298[6] + 5 * (int)m + 1;
      goto LABEL_58;
    }
LABEL_49:
    v29 = 0;
    v18 = v25[3];
    if ( (v25[2] & 0x1C000) != 0 )
      v29 = v17;
    v17 = v29;
    v30 = 0;
    if ( (v25[2] & 0xE0000) != 0 )
      v30 = v12;
    v12 = v30;
    if ( v9 && v25[4] && !v30 )
      v18 = v25[4];
LABEL_57:
    v28 = (_DWORD *)&qword_18007A298[6] + 5 * (int)m + 1;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v28[1] )
        goto LABEL_70;
      goto LABEL_62;
    }
LABEL_58:
    if ( v28[1] )
      goto LABEL_70;
    if ( v10 != *v28 )
    {
      v31 = (_DWORD *)&qword_18007A298[9] + 5 * (int)m;
      goto LABEL_71;
    }
LABEL_62:
    v32 = 0;
    v18 = v28[3];
    if ( (v28[2] & 0x1C000) != 0 )
      v32 = v17;
    v17 = v32;
    v33 = 0;
    if ( (v28[2] & 0xE0000) != 0 )
      v33 = v12;
    v12 = v33;
    if ( v9 && v28[4] && !v33 )
      v18 = v28[4];
LABEL_70:
    v31 = (_DWORD *)&qword_18007A298[9] + 5 * (int)m;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v31[1] )
        goto LABEL_83;
      goto LABEL_75;
    }
LABEL_71:
    if ( v31[1] )
      goto LABEL_83;
    if ( v10 != *v31 )
    {
      v34 = (_DWORD *)&qword_18007A298[11] + 5 * (int)m + 1;
      goto LABEL_84;
    }
LABEL_75:
    v35 = 0;
    v18 = v31[3];
    if ( (v31[2] & 0x1C000) != 0 )
      v35 = v17;
    v17 = v35;
    v36 = 0;
    if ( (v31[2] & 0xE0000) != 0 )
      v36 = v12;
    v12 = v36;
    if ( v9 && v31[4] && !v36 )
      v18 = v31[4];
LABEL_83:
    v34 = (_DWORD *)&qword_18007A298[11] + 5 * (int)m + 1;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v34[1] )
        goto LABEL_96;
      goto LABEL_88;
    }
LABEL_84:
    if ( v34[1] )
      goto LABEL_96;
    if ( v10 != *v34 )
    {
      v37 = (_DWORD *)&qword_18007A298[14] + 5 * (int)m;
      goto LABEL_97;
    }
LABEL_88:
    v38 = 0;
    v18 = v34[3];
    if ( (v34[2] & 0x1C000) != 0 )
      v38 = v17;
    v17 = v38;
    v39 = 0;
    if ( (v34[2] & 0xE0000) != 0 )
      v39 = v12;
    v12 = v39;
    if ( v9 && v34[4] && !v39 )
      v18 = v34[4];
LABEL_96:
    v37 = (_DWORD *)&qword_18007A298[14] + 5 * (int)m;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v37[1] )
        goto LABEL_109;
      goto LABEL_101;
    }
LABEL_97:
    if ( v37[1] )
      goto LABEL_109;
    if ( v10 != *v37 )
    {
      v40 = (_DWORD *)&qword_18007A298[16] + 5 * (int)m + 1;
      goto LABEL_110;
    }
LABEL_101:
    v41 = 0;
    v18 = v37[3];
    if ( (v37[2] & 0x1C000) != 0 )
      v41 = v17;
    v17 = v41;
    v42 = 0;
    if ( (v37[2] & 0xE0000) != 0 )
      v42 = v12;
    v12 = v42;
    if ( v9 && v37[4] && !v42 )
      v18 = v37[4];
LABEL_109:
    v40 = (_DWORD *)&qword_18007A298[16] + 5 * (int)m + 1;
    if ( (a3 & 0x7F) != 0 )
    {
      if ( v8 != v40[1] )
        goto LABEL_122;
      goto LABEL_114;
    }
LABEL_110:
    if ( v40[1] )
      goto LABEL_122;
    if ( v10 != *v40 )
    {
      v43 = (_DWORD *)&qword_18007A298[19] + 5 * (int)m;
LABEL_123:
      if ( v43[1] || v10 != *v43 )
        continue;
      goto LABEL_127;
    }
LABEL_114:
    v44 = 0;
    v18 = v40[3];
    if ( (v40[2] & 0x1C000) != 0 )
      v44 = v17;
    v17 = v44;
    v45 = 0;
    if ( (v40[2] & 0xE0000) != 0 )
      v45 = v12;
    v12 = v45;
    if ( v9 && v40[4] && !v45 )
      v18 = v40[4];
LABEL_122:
    v43 = (_DWORD *)&qword_18007A298[19] + 5 * (int)m;
    if ( (a3 & 0x7F) == 0 )
      goto LABEL_123;
    if ( v8 != v43[1] )
      continue;
LABEL_127:
    v46 = 0;
    v18 = v43[3];
    if ( (v43[2] & 0x1C000) != 0 )
      v46 = v17;
    v17 = v46;
    v47 = 0;
    if ( (v43[2] & 0xE0000) != 0 )
      v47 = v12;
    v12 = v47;
    if ( v9 && v43[4] && !v47 )
      v18 = v43[4];
  }
  v64 = v17;
  if ( !v18 )
    return (unsigned int)v11;
  ImageW = (HICON)LoadImageW(this[9], (LPCWSTR)(unsigned __int16)v18, 1u, a2, a2, 0);
  if ( v12 )
    v48 = (HICON)LoadImageW(this[9], (LPCWSTR)(unsigned __int16)v12, 1u, a2, a2, 0);
  else
    v48 = 0;
  v49 = 0;
  if ( a2 != GetSystemMetrics(49) && v64 )
    v49 = (HICON)LoadImageW(this[9], (LPCWSTR)(unsigned __int16)v64, 1u, a2, a2, 0);
  hIcon[1] = ImageW;
  v50 = (__int64 **)(this + 7);
  v51 = v69;
  v52 = 0;
  hIcon[0] = v49;
  hIcon[2] = v48;
  v65 = 0;
  *v69 = 0;
  while ( 2 )
  {
    v53 = *v50;
    v67 = a2;
    v74 = 0;
    v54 = v53;
    v55 = (__int64 *)v53[1];
    if ( !*((_BYTE *)v55 + 25) )
    {
      do
      {
        v56 = v55 + 2;
        if ( *((_DWORD *)v55 + 8) >= a2 )
        {
          v56 = v55;
          v54 = v55;
        }
        v55 = (__int64 *)*v56;
      }
      while ( !*(_BYTE *)(*v56 + 25) );
      v52 = v65;
      v50 = (__int64 **)(this + 7);
    }
    if ( !*((_BYTE *)v54 + 25) && a2 >= *((_DWORD *)v54 + 8) && v54 != v53 )
    {
      v57 = (struct _IMAGELIST *)v54[5];
      himl = v57;
LABEL_156:
      v60 = *v51 == 0;
      v61 = 1;
      v62 = hIcon[v52];
      hicon = v62;
      if ( v60 )
      {
        *v51 = CopyIcon(v62);
        v50 = (__int64 **)(this + 7);
        v11 = 1;
      }
      else
      {
        if ( v62 )
        {
          v61 = -2147467259;
          if ( ImageList_Remove(v57, -1) )
          {
            i = ImageList_ReplaceIcon(himl, -1, *v51);
            if ( i != -1 )
            {
              v63 = ImageList_ReplaceIcon(himl, -1, hicon);
              if ( v63 != -1 )
              {
                if ( ImageList_SetOverlayImage(himl, v63, 1) )
                {
                  DestroyIcon(*v51);
                  *v51 = ImageList_GetIcon(himl, i, 0x100u);
                  v61 = 0;
                }
              }
            }
          }
          v50 = (__int64 **)(this + 7);
        }
        v11 = v61;
        if ( v61 < 0 )
          goto LABEL_170;
      }
      v52 = v65 + 1;
      v65 = v52;
      if ( v52 >= 3 )
        goto LABEL_170;
      v51 = v69;
      continue;
    }
    break;
  }
  himl = ImageList_Create(a2, a2, 0x21u, 2, 0);
  if ( himl )
  {
    v58 = (__int64 *)std::map<unsigned long,_IMAGELIST *>::_Try_emplace<unsigned long const &,>(this + 7, v73, &v67);
    v57 = himl;
    v59 = *v58;
    v52 = v65;
    *(_QWORD *)(v59 + 40) = himl;
    v50 = (__int64 **)(this + 7);
    goto LABEL_156;
  }
  v11 = -2147467259;
  v61 = -2147467259;
LABEL_170:
  if ( v49 )
    DestroyIcon(v49);
  if ( ImageW )
    DestroyIcon(ImageW);
  if ( v48 )
    DestroyIcon(v48);
  if ( v61 >= 0 )
  {
    v11 = CNetConfigIcons::HrMergeCharacteristicsIcons((CNetConfigIcons *)this, a2, a3, v69);
    if ( v11 >= 0 )
      return 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800066b0  push    rsi
0x1800066b2  push    rdi
0x1800066b3  push    r13
0x1800066b5  sub     rsp, 0D0h
0x1800066bc  mov     eax, r8d
0x1800066bf  mov     [rsp+0E8h+var_98], r9
0x1800066c4  and     eax, 0C0000000h
0x1800066c9  mov     edi, r8d
0x1800066cc  mov     esi, edx
0x1800066ce  mov     r13, rcx
0x1800066d1  cmp     eax, 40000000h
0x1800066d6  jz      short loc_1800066E2
0x1800066d8  mov     eax, 80070057h
0x1800066dd  jmp     loc_180006EF1
0x1800066e2  mov     [rsp+0E8h+arg_10], rbx
0x1800066ea  mov     edx, edi
0x1800066ec  mov     [rsp+0E8h+var_20], rbp
0x1800066f4  mov     r9d, edi
0x1800066f7  mov     [rsp+0E8h+var_28], r12
0x1800066ff  and     edx, 7Fh
0x180006702  and     r9d, 100000h
0x180006709  mov     [rsp+0E8h+var_30], r14
0x180006711  and     r8d, 3F80h
0x180006718  mov     [rsp+0E8h+var_38], r15
0x180006720  mov     ecx, edi
0x180006722  lea     r15, __ImageBase
0x180006729  mov     ebp, 80004005h
0x18000672e  and     ecx, 0E0000h
0x180006734  jnz     short loc_180006768
0x180006736  xor     ebx, ebx
0x180006738  mov     r14d, ebx
0x18000673b  mov     ecx, edi
0x18000673d  and     ecx, 1C000h
0x180006743  jz      short loc_1800067A6
0x180006745  mov     r10d, ebx
0x180006748  cmp     r10d, 5
0x18000674c  jnb     short loc_1800067A6
0x18000674e  mov     eax, r10d
0x180006751  lea     r11, ds:0[rax*8]
0x180006759  cmp     ecx, [r11+r15+7A400h]
0x180006761  jz      short loc_180006797
0x180006763  inc     r10d
0x180006766  jmp     short loc_180006748
0x180006768  xor     ebx, ebx
0x18000676a  mov     r10d, ebx
0x18000676d  cmp     r10d, 3
0x180006771  jnb     short loc_180006738
0x180006773  mov     eax, r10d
0x180006776  lea     r14, ds:0[rax*8]
0x18000677e  cmp     ecx, [r14+r15+7A450h]
0x180006786  jz      short loc_18000678D
0x180006788  inc     r10d
0x18000678b  jmp     short loc_18000676D
0x18000678d  mov     r14d, [r14+r15+7A454h]
0x180006795  jmp     short loc_18000673B
0x180006797  mov     r11d, [r11+r15+7A404h]
0x18000679f  mov     [rsp+0E8h+var_B8], r11d
0x1800067a4  jmp     short loc_1800067AD
0x1800067a6  mov     [rsp+0E8h+var_B8], ebx
0x1800067aa  mov     r11d, ebx
0x1800067ad  mov     ecx, ebx
0x1800067af  mov     r10d, ebx
0x1800067b2  movsxd  r12, r10d
0x1800067b5  lea     rax, [r12+r12*4]
0x1800067b9  lea     r15, [r15+rax*4]
0x1800067bd  mov     eax, [r15+7A294h]
0x1800067c4  lea     r15, [r15+7A290h]
0x1800067cb  test    edx, edx
0x1800067cd  jnz     short loc_1800067F0
0x1800067cf  test    eax, eax
0x1800067d1  jnz     short loc_18000682E
0x1800067d3  cmp     r8d, [r15]
0x1800067d6  jz      short loc_1800067F4
0x1800067d8  lea     rax, [r12+r12*4]
0x1800067dc  lea     r15, __ImageBase
0x1800067e3  lea     r15, [r15+rax*4]
0x1800067e7  lea     r15, [r15+7A2A4h]
0x1800067ee  jmp     short loc_180006848
0x1800067f0  cmp     edx, eax
0x1800067f2  jnz     short loc_18000682E
0x1800067f4  test    dword ptr [r15+8], 1C000h
0x1800067fc  mov     eax, ebx
0x1800067fe  mov     ecx, [r15+0Ch]
0x180006802  cmovnz  eax, r11d
0x180006806  test    dword ptr [r15+8], 0E0000h
0x18000680e  mov     r11d, eax
0x180006811  mov     eax, ebx
0x180006813  cmovnz  eax, r14d
0x180006817  mov     r14d, eax
0x18000681a  test    r9d, r9d
0x18000681d  jz      short loc_18000682E
0x18000681f  mov     eax, [r15+10h]
0x180006823  test    eax, eax
0x180006825  jz      short loc_18000682E
0x180006827  test    r14d, r14d
0x18000682a  jnz     short loc_18000682E
0x18000682c  mov     ecx, eax
0x18000682e  lea     rax, [r12+r12*4]
0x180006832  lea     r15, __ImageBase
0x180006839  lea     r15, [r15+rax*4]
0x18000683d  lea     r15, [r15+7A2A4h]
0x180006844  test    edx, edx
0x180006846  jnz     short loc_18000686C
0x180006848  cmp     dword ptr [r15+4], 0
0x18000684d  jnz     short loc_1800068AC
0x18000684f  cmp     r8d, [r15]
0x180006852  jz      short loc_180006872
0x180006854  lea     rax, [r12+r12*4]
0x180006858  lea     r15, __ImageBase
0x18000685f  lea     r15, [r15+rax*4]
0x180006863  lea     r15, [r15+7A2B8h]
0x18000686a  jmp     short loc_1800068C6
0x18000686c  cmp     edx, [r15+4]
0x180006870  jnz     short loc_1800068AC
0x180006872  test    dword ptr [r15+8], 1C000h
0x18000687a  mov     eax, ebx
0x18000687c  mov     ecx, [r15+0Ch]
0x180006880  cmovnz  eax, r11d
0x180006884  test    dword ptr [r15+8], 0E0000h
0x18000688c  mov     r11d, eax
0x18000688f  mov     eax, ebx
0x180006891  cmovnz  eax, r14d
0x180006895  mov     r14d, eax
0x180006898  test    r9d, r9d
0x18000689b  jz      short loc_1800068AC
0x18000689d  mov     eax, [r15+10h]
0x1800068a1  test    eax, eax
0x1800068a3  jz      short loc_1800068AC
0x1800068a5  test    r14d, r14d
0x1800068a8  jnz     short loc_1800068AC
0x1800068aa  mov     ecx, eax
0x1800068ac  lea     rax, [r12+r12*4]
0x1800068b0  lea     r15, __ImageBase
0x1800068b7  lea     r15, [r15+rax*4]
0x1800068bb  lea     r15, [r15+7A2B8h]
0x1800068c2  test    edx, edx
0x1800068c4  jnz     short loc_1800068EA
0x1800068c6  cmp     dword ptr [r15+4], 0
0x1800068cb  jnz     short loc_18000692A
0x1800068cd  cmp     r8d, [r15]
0x1800068d0  jz      short loc_1800068F0
0x1800068d2  lea     rax, [r12+r12*4]
0x1800068d6  lea     r15, __ImageBase
0x1800068dd  lea     r15, [r15+rax*4]
0x1800068e1  lea     r15, [r15+7A2CCh]
0x1800068e8  jmp     short loc_180006944
0x1800068ea  cmp     edx, [r15+4]
0x1800068ee  jnz     short loc_18000692A
0x1800068f0  test    dword ptr [r15+8], 1C000h
0x1800068f8  mov     eax, ebx
0x1800068fa  mov     ecx, [r15+0Ch]
0x1800068fe  cmovnz  eax, r11d
0x180006902  test    dword ptr [r15+8], 0E0000h
0x18000690a  mov     r11d, eax
0x18000690d  mov     eax, ebx
0x18000690f  cmovnz  eax, r14d
0x180006913  mov     r14d, eax
0x180006916  test    r9d, r9d
0x180006919  jz      short loc_18000692A
0x18000691b  mov     eax, [r15+10h]
0x18000691f  test    eax, eax
0x180006921  jz      short loc_18000692A
0x180006923  test    r14d, r14d
0x180006926  jnz     short loc_18000692A
0x180006928  mov     ecx, eax
0x18000692a  lea     rax, [r12+r12*4]
0x18000692e  lea     r15, __ImageBase
0x180006935  lea     r15, [r15+rax*4]
0x180006939  lea     r15, [r15+7A2CCh]
0x180006940  test    edx, edx
0x180006942  jnz     short loc_180006968
0x180006944  cmp     dword ptr [r15+4], 0
0x180006949  jnz     short loc_1800069A8
0x18000694b  cmp     r8d, [r15]
0x18000694e  jz      short loc_18000696E
0x180006950  lea     rax, [r12+r12*4]
0x180006954  lea     r15, __ImageBase
0x18000695b  lea     r15, [r15+rax*4]
0x18000695f  lea     r15, [r15+7A2E0h]
0x180006966  jmp     short loc_1800069C2
0x180006968  cmp     edx, [r15+4]
0x18000696c  jnz     short loc_1800069A8
0x18000696e  test    dword ptr [r15+8], 1C000h
0x180006976  mov     eax, ebx
0x180006978  mov     ecx, [r15+0Ch]
0x18000697c  cmovnz  eax, r11d
0x180006980  test    dword ptr [r15+8], 0E0000h
0x180006988  mov     r11d, eax
0x18000698b  mov     eax, ebx
0x18000698d  cmovnz  eax, r14d
0x180006991  mov     r14d, eax
0x180006994  test    r9d, r9d
0x180006997  jz      short loc_1800069A8
0x180006999  mov     eax, [r15+10h]
0x18000699d  test    eax, eax
0x18000699f  jz      short loc_1800069A8
0x1800069a1  test    r14d, r14d
0x1800069a4  jnz     short loc_1800069A8
0x1800069a6  mov     ecx, eax
0x1800069a8  lea     rax, [r12+r12*4]
0x1800069ac  lea     r15, __ImageBase
0x1800069b3  lea     r15, [r15+rax*4]
0x1800069b7  lea     r15, [r15+7A2E0h]
0x1800069be  test    edx, edx
0x1800069c0  jnz     short loc_1800069E6
0x1800069c2  cmp     dword ptr [r15+4], 0
0x1800069c7  jnz     short loc_180006A26
0x1800069c9  cmp     r8d, [r15]
0x1800069cc  jz      short loc_1800069EC
0x1800069ce  lea     rax, [r12+r12*4]
0x1800069d2  lea     r15, __ImageBase
0x1800069d9  lea     r15, [r15+rax*4]
0x1800069dd  lea     r15, [r15+7A2F4h]
0x1800069e4  jmp     short loc_180006A40
0x1800069e6  cmp     edx, [r15+4]
0x1800069ea  jnz     short loc_180006A26
0x1800069ec  test    dword ptr [r15+8], 1C000h
0x1800069f4  mov     eax, ebx
0x1800069f6  mov     ecx, [r15+0Ch]
0x1800069fa  cmovnz  eax, r11d
0x1800069fe  test    dword ptr [r15+8], 0E0000h
0x180006a06  mov     r11d, eax
0x180006a09  mov     eax, ebx
0x180006a0b  cmovnz  eax, r14d
0x180006a0f  mov     r14d, eax
0x180006a12  test    r9d, r9d
0x180006a15  jz      short loc_180006A26
0x180006a17  mov     eax, [r15+10h]
0x180006a1b  test    eax, eax
0x180006a1d  jz      short loc_180006A26
0x180006a1f  test    r14d, r14d
0x180006a22  jnz     short loc_180006A26
0x180006a24  mov     ecx, eax
0x180006a26  lea     rax, [r12+r12*4]
0x180006a2a  lea     r15, __ImageBase
0x180006a31  lea     r15, [r15+rax*4]
0x180006a35  lea     r15, [r15+7A2F4h]
0x180006a3c  test    edx, edx
0x180006a3e  jnz     short loc_180006A64
0x180006a40  cmp     dword ptr [r15+4], 0
0x180006a45  jnz     short loc_180006AA4
0x180006a47  cmp     r8d, [r15]
0x180006a4a  jz      short loc_180006A6A
0x180006a4c  lea     rax, [r12+r12*4]
0x180006a50  lea     r15, __ImageBase
0x180006a57  lea     r15, [r15+rax*4]
0x180006a5b  lea     r15, [r15+7A308h]
0x180006a62  jmp     short loc_180006ABE
0x180006a64  cmp     edx, [r15+4]
0x180006a68  jnz     short loc_180006AA4
0x180006a6a  test    dword ptr [r15+8], 1C000h
0x180006a72  mov     eax, ebx
0x180006a74  mov     ecx, [r15+0Ch]
0x180006a78  cmovnz  eax, r11d
0x180006a7c  test    dword ptr [r15+8], 0E0000h
0x180006a84  mov     r11d, eax
0x180006a87  mov     eax, ebx
0x180006a89  cmovnz  eax, r14d
0x180006a8d  mov     r14d, eax
0x180006a90  test    r9d, r9d
0x180006a93  jz      short loc_180006AA4
0x180006a95  mov     eax, [r15+10h]
0x180006a99  test    eax, eax
0x180006a9b  jz      short loc_180006AA4
0x180006a9d  test    r14d, r14d
0x180006aa0  jnz     short loc_180006AA4
0x180006aa2  mov     ecx, eax
0x180006aa4  lea     rax, [r12+r12*4]
0x180006aa8  lea     r15, __ImageBase
0x180006aaf  lea     r15, [r15+rax*4]
0x180006ab3  lea     r15, [r15+7A308h]
0x180006aba  test    edx, edx
0x180006abc  jnz     short loc_180006AE2
0x180006abe  cmp     dword ptr [r15+4], 0
0x180006ac3  jnz     short loc_180006B22
0x180006ac5  cmp     r8d, [r15]
0x180006ac8  jz      short loc_180006AE8
0x180006aca  lea     rax, [r12+r12*4]
0x180006ace  lea     r15, __ImageBase
0x180006ad5  lea     r15, [r15+rax*4]
0x180006ad9  lea     r15, [r15+7A31Ch]
0x180006ae0  jmp     short loc_180006B3C
0x180006ae2  cmp     edx, [r15+4]
0x180006ae6  jnz     short loc_180006B22
0x180006ae8  test    dword ptr [r15+8], 1C000h
0x180006af0  mov     eax, ebx
0x180006af2  mov     ecx, [r15+0Ch]
0x180006af6  cmovnz  eax, r11d
0x180006afa  test    dword ptr [r15+8], 0E0000h
0x180006b02  mov     r11d, eax
0x180006b05  mov     eax, ebx
0x180006b07  cmovnz  eax, r14d
0x180006b0b  mov     r14d, eax
0x180006b0e  test    r9d, r9d
0x180006b11  jz      short loc_180006B22
0x180006b13  mov     eax, [r15+10h]
0x180006b17  test    eax, eax
0x180006b19  jz      short loc_180006B22
0x180006b1b  test    r14d, r14d
0x180006b1e  jnz     short loc_180006B22
  ... truncated ...
```
