# CImpIRowsetUpdate::InternalUndo(ulong,ulong,ulong const * const,ulong *,ulong * *,ulong * *,int)

- ea: `0x100338a0`
- end: `0x10033f1e`
- name: `?InternalUndo@CImpIRowsetUpdate@@AAEJKKQBKPAKPAPAK2H@Z`
- size: `1662`
- prototype: `int __thiscall(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, const unsigned int *const, unsigned int *, unsigned int **, unsigned int **, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x100336f0`

## callees

- `0x1000bb00`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10027a60`
- `0x100338a0`
- `0x1004ce5d`
- `0x1004cea1`

## import_xrefs

- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10033ccb`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10033ccb`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10033aa3`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10033aa3`

## pseudocode

```c
int __thiscall CImpIRowsetUpdate::InternalUndo(
        CImpIRowsetUpdate *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int *a5,
        unsigned int **a6,
        unsigned int **a7,
        int a8)
{
  int v8; // ecx
  unsigned int **v9; // edi
  unsigned int *v10; // eax
  unsigned int *v11; // eax
  bool v12; // zf
  int v13; // esi
  unsigned int *v14; // eax
  unsigned int v15; // edx
  char *v16; // ebx
  unsigned int v17; // esi
  _DWORD *v18; // ebx
  unsigned int v19; // ecx
  int v20; // eax
  _DWORD *v21; // ebx
  int v22; // ecx
  int v23; // eax
  unsigned int v24; // edx
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  _DWORD *v28; // eax
  unsigned int v29; // esi
  int v30; // eax
  CRowset *v31; // ebx
  int v32; // ecx
  int v33; // eax
  unsigned int v34; // edx
  int v35; // eax
  _DWORD *v36; // ecx
  int v37; // ecx
  _DWORD *v38; // ecx
  int v39; // eax
  struct _GUID *v41; // [esp+0h] [ebp-38h]
  int v42; // [esp+0h] [ebp-38h]
  const struct _GUID *v43; // [esp+4h] [ebp-34h]
  const struct _GUID *v44; // [esp+4h] [ebp-34h]
  unsigned int v45; // [esp+Ch] [ebp-2Ch] BYREF
  unsigned int v46; // [esp+10h] [ebp-28h]
  _DWORD *v47; // [esp+14h] [ebp-24h]
  int v48; // [esp+18h] [ebp-20h]
  int v49; // [esp+1Ch] [ebp-1Ch]
  unsigned int v50; // [esp+20h] [ebp-18h]
  CImpIRowsetUpdate *v51; // [esp+24h] [ebp-14h]
  int v52; // [esp+28h] [ebp-10h]
  int v53; // [esp+2Ch] [ebp-Ch]
  int v54; // [esp+30h] [ebp-8h]
  char *v55; // [esp+34h] [ebp-4h]

  v51 = this;
  v50 = 0;
  v53 = 0;
  v8 = 0;
  v52 = 0;
  v9 = a7;
  v10 = a5;
  v54 = 0;
  v49 = 0;
  if ( a5 )
  {
    v11 = (unsigned int *)(*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                            *(_DWORD *)(*(_DWORD *)Sys + 12),
                            Sys,
                            4 * a3);
    v12 = v11 == 0;
    *a6 = v11;
    v10 = a5;
    if ( v12 )
    {
      v13 = -2147024882;
      v54 = -2147024882;
      goto LABEL_97;
    }
    v8 = 1;
    v49 = 1;
  }
  if ( (a3 || v10) && a7 )
  {
    v14 = (unsigned int *)(*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                            *(_DWORD *)(*(_DWORD *)Sys + 12),
                            Sys,
                            4 * a3);
    *a7 = v14;
    if ( !v14 )
    {
      v13 = -2147024882;
      v54 = -2147024882;
      goto LABEL_96;
    }
    v8 = 1;
    v49 = 1;
  }
  v15 = 0;
  v16 = (char *)v51 + 8;
  v47 = (_DWORD *)v8;
  v48 = 0;
  if ( !a3 )
    goto LABEL_74;
  v55 = (char *)v51 + 8;
  do
  {
    v17 = v15;
    if ( v9 )
      (*v9)[v17] = 0;
    if ( a5 )
    {
      ++*a5;
      if ( a6 )
      {
        if ( *a6 )
          (*a6)[v15] = a4[v15];
      }
    }
    v18 = *(_DWORD **)(*(_DWORD *)v16 + 104);
    v45 = (unsigned int)v18;
    v19 = a4[v15];
    v20 = v18[5];
    v46 = v19;
    if ( v19 > v18[6] + 8 * v20 - 1
      || (*(_BYTE *)(((v19 - v18[6]) >> 3) + v18[4]) & *((_BYTE *)&Bitmap::ThisBit + ((v19 - v18[6]) & 7))) != 0
      || (v21 = (_DWORD *)(*(_DWORD *)(v45 + 8) + v46 * *v18)) == 0
      || *v21 == -1 )
    {
      v16 = v55;
      v25 = 1;
      v26 = v52;
      v53 = 1;
      if ( v9 )
      {
        (*v9)[v17] = 12;
        v25 = v53;
      }
      goto LABEL_59;
    }
    if ( a8 == 1 )
      ++v21[2];
    v22 = v21[1];
    if ( v22 != 4 )
    {
      v23 = *((_DWORD *)v51 + 2);
      v24 = *(_DWORD *)(v23 + 220);
      v45 = v24;
      if ( v24 != -1 && v24 == *v21 )
      {
        v9 = a7;
        if ( *(_DWORD *)(v23 + 224) == a4[v17] )
        {
          v45 = (v45 == -2) + 10;
          if ( CRowset::RowNotify((CRowset *)&a4[v17], v45, 0, (enum DBREASONENUM)v41, (enum DBEVENTPHASEENUM)v43) )
            goto LABEL_30;
          v50 = JetPrepareUpdate(
                  *(_DWORD *)(*(_DWORD *)(*(_DWORD *)v55 + 56) + 16),
                  *(_DWORD *)(*(_DWORD *)v55 + 112),
                  3u);
          if ( v50 )
          {
            v53 = 1;
            CRowset::RowNotify(
              (CRowset *)&a4[v17],
              0xBu,
              (const unsigned int *const)3,
              (enum DBREASONENUM)v41,
              (enum DBEVENTPHASEENUM)v43);
            v16 = v55;
            CExtError::SendJetErrortoOLEAuto(
              0,
              *(char **)(*(_DWORD *)(*(_DWORD *)v55 + 56) + 16),
              v50,
              (int)&IID_IRowsetUpdate,
              v42,
              v44);
            if ( a7 )
            {
              (*a7)[v17] = 12;
              v25 = v53;
            }
            else
            {
              v25 = 1;
            }
LABEL_58:
            v26 = v52;
            goto LABEL_59;
          }
          CRowset::RowNotify(
            (CRowset *)&a4[v17],
            v45,
            (const unsigned int *const)4,
            (enum DBREASONENUM)v41,
            (enum DBEVENTPHASEENUM)v43);
          v26 = 1;
          v52 = 1;
          if ( *(_DWORD *)(*(_DWORD *)v55 + 220) == -2 )
          {
            v21[1] = 16;
            if ( a7 )
              (*a7)[v17] = 0;
            v16 = v55;
            v25 = v53;
            v52 = 1;
          }
          else
          {
            v25 = v53;
            v21[1] = 8;
            v16 = v55;
          }
          goto LABEL_59;
        }
      }
      if ( (v22 & 4) == 0 )
      {
        if ( (v22 & 8) == 0 )
        {
          if ( (v22 & 0x10) != 0 )
          {
            if ( v9 )
              (*v9)[v17] = 8;
            v16 = v55;
            v25 = 1;
            v53 = 1;
          }
          else
          {
            v16 = v55;
            v25 = v53;
          }
          goto LABEL_58;
        }
        if ( v9 )
          (*v9)[v17] = 0;
        v16 = v55;
        v26 = 1;
        v25 = v53;
        v52 = 1;
        goto LABEL_59;
      }
    }
    if ( CRowset::RowNotify((CRowset *)&a4[v17], 0xCu, 0, (enum DBREASONENUM)v41, (enum DBEVENTPHASEENUM)v43) )
    {
LABEL_30:
      if ( v9 )
        (*v9)[v17] = 4;
      v16 = v55;
      v25 = 1;
      v53 = 1;
      goto LABEL_58;
    }
    if ( v9 )
      (*v9)[v17] = 0;
    v21[1] = 8;
    v16 = v55;
    v52 = 1;
    CRowset::RowNotify(
      (CRowset *)&a4[v17],
      0xCu,
      (const unsigned int *const)4,
      (enum DBREASONENUM)v41,
      (enum DBEVENTPHASEENUM)v43);
    v25 = v53;
    v26 = 1;
LABEL_59:
    v15 = v48 + 1;
    v48 = v15;
  }
  while ( v15 < a3 );
  if ( v26 == 1 )
  {
    v13 = 265946;
    if ( v25 != 1 )
      v13 = 0;
    v54 = v13;
  }
  else if ( v25 == 1 )
  {
    v13 = -2147217887;
    v54 = -2147217887;
    v16 = (char *)v51 + 8;
  }
  else
  {
    v13 = 0;
  }
  if ( v50 )
  {
    CExtError::SendJetErrortoOLEAuto(
      v13,
      *(char **)(*(_DWORD *)(*(_DWORD *)v16 + 56) + 16),
      v50,
      (int)&IID_IRowsetUpdate,
      (int)v41,
      v43);
    goto LABEL_73;
  }
  v54 = v13;
  if ( v13 >= 0 )
    goto LABEL_74;
  v16 = (char *)v51 + 8;
  v49 = (int)v47;
  v27 = *((_DWORD *)v51 + 2);
  v54 = v13;
  if ( !JetGetDatabaseInfo(*(_DWORD *)(*(_DWORD *)(v27 + 56) + 16), *(_DWORD *)(*(_DWORD *)(v27 + 56) + 20), &v45, 4, 3) )
  {
    CExtError::SendHRtoOLEAuto((int)&IID_IRowsetUpdate, 0, v41, (int)v43);
    v54 = v13;
    v49 = (int)v47;
    goto LABEL_96;
  }
  v13 = v54;
LABEL_73:
  if ( v13 >= 0 )
  {
LABEL_74:
    v28 = *(_DWORD **)v16;
    v29 = *(_DWORD *)(*(_DWORD *)v16 + 224);
    v28[55] = -1;
    v28[57] = 0;
    v28[56] = 0;
    v28[58] = -1;
    v28[59] = 1;
    v30 = *(_DWORD *)v16;
    v31 = 0;
    v46 = v29;
    v32 = *(_DWORD *)(v30 + 16);
    v48 = 0;
    v52 = v32;
    if ( *(_DWORD *)(*(_DWORD *)(v32 + 8) + 52) )
    {
      v31 = (CRowset *)operator new(4u);
      if ( v31 )
      {
        v32 = v52;
        goto LABEL_77;
      }
    }
    else
    {
LABEL_77:
      _mm_lfence();
      v47 = *(_DWORD **)(v32 + 8);
      v33 = v47[26];
      v34 = *(_DWORD *)(v33 + 24);
      v35 = *(_DWORD *)(v33 + 20);
      v45 = v34;
      if ( v29 <= v34 + 8 * v35 - 1 )
      {
        v9 = a7;
        if ( (*(_BYTE *)(((v29 - v45) >> 3) + *(_DWORD *)(v47[26] + 16))
            & *((_BYTE *)&Bitmap::ThisBit + ((v29 - v45) & 7))) == 0 )
        {
          v36 = (_DWORD *)(*(_DWORD *)(v47[26] + 8) + v29 * *(_DWORD *)v47[26]);
          if ( v36 )
          {
            if ( *v36 != -1 )
            {
              if ( v29 == v47[56] && v36[2] == 1 )
                v36[2] = 2;
              v12 = v36[2]-- == 1;
              if ( v12 )
              {
                if ( v31 )
                {
                  *(_DWORD *)v31 = v29;
                  v48 = 1;
                }
                v37 = *(_DWORD *)(v52 + 8);
                if ( *(_DWORD *)(v37 + 228) == v29 )
                {
                  v38 = *(_DWORD **)(v37 + 216);
                  v47 = v38;
                  if ( v38 )
                  {
                    v39 = v38[3];
                    v38[1] = 1;
                    *(_DWORD *)(v39 + 216) = 0;
                    (*(void (__thiscall **)(_DWORD *))(*v38 + 4))(v47);
                    v47[3] = 0;
                  }
                }
                CExtBuffer::DeleteFromExtBuffer((CExtBuffer *)v41, (unsigned int)v43);
                *(_DWORD *)(*(_DWORD *)(v52 + 8) + 136) = 0;
              }
            }
          }
        }
      }
      if ( v31 )
      {
        if ( v48 )
          CRowset::RowNotify(v31, 5u, (const unsigned int *const)4, (enum DBREASONENUM)v41, (enum DBEVENTPHASEENUM)v43);
        operator delete(v31);
      }
    }
    v13 = v54;
  }
LABEL_96:
  v10 = a5;
  if ( a5 )
  {
LABEL_97:
    if ( *v10 || !v49 )
      goto LABEL_99;
LABEL_101:
    if ( a6 && *a6 )
    {
      if ( Sys )
        (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)Sys + 20))(*(_DWORD *)(*(_DWORD *)Sys + 20), Sys, *a6);
      *a6 = 0;
    }
    if ( v9 && *v9 )
    {
      if ( Sys )
        (*(void (__thiscall **)(_DWORD, int, unsigned int *))(*(_DWORD *)Sys + 20))(
          *(_DWORD *)(*(_DWORD *)Sys + 20),
          Sys,
          *v9);
      *v9 = 0;
    }
    return v54;
  }
  else
  {
LABEL_99:
    if ( v13 < 0 && v13 != -2147217887 )
      goto LABEL_101;
    return v13;
  }
}

```

## disassembly

```asm
0x100338a0  mov     edi, edi
0x100338a2  push    ebp
0x100338a3  mov     ebp, esp
0x100338a5  sub     esp, 2Ch
0x100338a8  xor     eax, eax
0x100338aa  mov     [ebp+var_14], ecx
0x100338ad  mov     [ebp+var_18], eax
0x100338b0  xor     edx, edx
0x100338b2  mov     [ebp+var_C], eax
0x100338b5  xor     ecx, ecx
0x100338b7  mov     [ebp+var_10], eax
0x100338ba  mov     eax, [ebp+arg_4]
0x100338bd  push    ebx
0x100338be  push    esi; enum DBEVENTPHASEENUM
0x100338bf  push    edi; enum DBREASONENUM
0x100338c0  mov     edi, [ebp+arg_14]
0x100338c3  lea     ebx, ds:0[eax*4]
0x100338ca  mov     eax, [ebp+arg_C]
0x100338cd  mov     [ebp+var_8], edx
0x100338d0  mov     [ebp+var_1C], ecx
0x100338d3  test    eax, eax
0x100338d5  jz      short loc_1003390F
0x100338d7  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x100338dd  push    ebx
0x100338de  push    ecx
0x100338df  mov     eax, [ecx]
0x100338e1  mov     esi, [eax+0Ch]
0x100338e4  mov     ecx, esi
0x100338e6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100338ec  call    esi
0x100338ee  mov     ecx, [ebp+arg_10]
0x100338f1  test    eax, eax
0x100338f3  mov     [ecx], eax
0x100338f5  mov     eax, [ebp+arg_C]
0x100338f8  jnz     short loc_10033907
0x100338fa  mov     esi, 8007000Eh
0x100338ff  mov     [ebp+var_8], esi
0x10033902  jmp     loc_10033E98
0x10033907  mov     ecx, 1
0x1003390c  mov     [ebp+var_1C], ecx
0x1003390f  cmp     [ebp+arg_4], 0
0x10033913  jnz     short loc_10033919
0x10033915  test    eax, eax
0x10033917  jz      short loc_1003394F
0x10033919  test    edi, edi
0x1003391b  jz      short loc_1003394F
0x1003391d  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10033923  push    ebx
0x10033924  push    ecx
0x10033925  mov     eax, [ecx]
0x10033927  mov     esi, [eax+0Ch]
0x1003392a  mov     ecx, esi
0x1003392c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10033932  call    esi
0x10033934  mov     [edi], eax
0x10033936  test    eax, eax
0x10033938  jnz     short loc_10033947
0x1003393a  mov     esi, 8007000Eh
0x1003393f  mov     [ebp+var_8], esi
0x10033942  jmp     loc_10033E91
0x10033947  mov     ecx, 1
0x1003394c  mov     [ebp+var_1C], ecx
0x1003394f  mov     ebx, [ebp+var_14]
0x10033952  xor     edx, edx
0x10033954  add     ebx, 8
0x10033957  mov     [ebp+var_24], ecx
0x1003395a  mov     [ebp+var_20], edx
0x1003395d  cmp     [ebp+arg_4], edx
0x10033960  jbe     loc_10033CFB
0x10033966  mov     [ebp+var_4], ebx
0x10033969  nop     dword ptr [eax+00000000h]
0x10033970  lea     esi, ds:0[edx*4]
0x10033977  test    edi, edi
0x10033979  jz      short loc_10033984
0x1003397b  mov     eax, [edi]
0x1003397d  mov     dword ptr [esi+eax], 0
0x10033984  mov     eax, [ebp+arg_C]
0x10033987  test    eax, eax
0x10033989  jz      short loc_100339A3
0x1003398b  inc     dword ptr [eax]
0x1003398d  mov     eax, [ebp+arg_10]
0x10033990  test    eax, eax
0x10033992  jz      short loc_100339A3
0x10033994  mov     ecx, [eax]
0x10033996  test    ecx, ecx
0x10033998  jz      short loc_100339A3
0x1003399a  mov     eax, [ebp+arg_8]
0x1003399d  mov     eax, [eax+esi]
0x100339a0  mov     [ecx+esi], eax
0x100339a3  mov     eax, [ebx]
0x100339a5  mov     ebx, [eax+68h]
0x100339a8  mov     eax, [ebp+arg_8]
0x100339ab  mov     [ebp+var_2C], ebx
0x100339ae  mov     ecx, [eax+esi]
0x100339b1  mov     eax, [ebx+14h]
0x100339b4  mov     [ebp+var_28], ecx
0x100339b7  lea     eax, ds:0FFFFFFFFh[eax*8]
0x100339be  add     eax, [ebx+18h]
0x100339c1  cmp     ecx, eax
0x100339c3  ja      loc_10033C11
0x100339c9  mov     eax, [ebx+10h]
0x100339cc  mov     edx, ecx
0x100339ce  sub     edx, [ebx+18h]
0x100339d1  mov     ecx, edx
0x100339d3  and     edx, 7
0x100339d6  shr     ecx, 3
0x100339d9  mov     al, [ecx+eax]
0x100339dc  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x100339e2  jnz     loc_10033C11
0x100339e8  mov     ebx, [ebx]
0x100339ea  imul    ebx, [ebp+var_28]
0x100339ee  mov     eax, [ebp+var_2C]
0x100339f1  add     ebx, [eax+8]
0x100339f4  jz      loc_10033C11
0x100339fa  cmp     dword ptr [ebx], 0FFFFFFFFh
0x100339fd  jz      loc_10033C11
0x10033a03  cmp     [ebp+arg_18], 1
0x10033a07  jnz     short loc_10033A0C
0x10033a09  inc     dword ptr [ebx+8]
0x10033a0c  mov     ecx, [ebx+4]
0x10033a0f  cmp     ecx, 4
0x10033a12  jz      loc_10033BB2
0x10033a18  mov     eax, [ebp+var_14]
0x10033a1b  mov     eax, [eax+8]
0x10033a1e  mov     edx, [eax+0DCh]
0x10033a24  mov     [ebp+var_2C], edx
0x10033a27  cmp     edx, 0FFFFFFFFh
0x10033a2a  jz      loc_10033B62
0x10033a30  cmp     edx, [ebx]
0x10033a32  jnz     loc_10033B62
0x10033a38  mov     edx, [ebp+arg_8]
0x10033a3b  mov     eax, [eax+0E0h]
0x10033a41  add     edx, esi
0x10033a43  mov     edi, [ebp+arg_14]
0x10033a46  cmp     eax, [edx]
0x10033a48  jnz     loc_10033B62
0x10033a4e  xor     eax, eax
0x10033a50  cmp     [ebp+var_2C], 0FFFFFFFEh
0x10033a54  push    0; unsigned int *
0x10033a56  setz    al
0x10033a59  add     eax, 0Ah
0x10033a5c  push    eax; unsigned int
0x10033a5d  mov     [ebp+var_2C], eax
0x10033a60  mov     eax, [ebp+var_14]
0x10033a63  push    edx; this
0x10033a64  mov     edx, 1
0x10033a69  mov     ecx, [eax+8]
0x10033a6c  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10033a71  test    eax, eax
0x10033a73  jz      short loc_10033A92
0x10033a75  test    edi, edi
0x10033a77  jz      short loc_10033A82
0x10033a79  mov     eax, [edi]
0x10033a7b  mov     dword ptr [esi+eax], 4
0x10033a82  mov     ebx, [ebp+var_4]
0x10033a85  mov     eax, 1
0x10033a8a  mov     [ebp+var_C], eax
0x10033a8d  jmp     loc_10033C3E
0x10033a92  mov     eax, [ebp+var_4]
0x10033a95  push    3; prep
0x10033a97  mov     eax, [eax]
0x10033a99  mov     ecx, [eax+70h]
0x10033a9c  mov     eax, [eax+38h]
0x10033a9f  push    ecx; tableid
0x10033aa0  push    dword ptr [eax+10h]; sesid
0x10033aa3  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10033aa9  mov     edx, eax
0x10033aab  mov     eax, [ebp+var_4]
0x10033aae  mov     [ebp+var_18], edx
0x10033ab1  test    edx, edx
0x10033ab3  mov     edx, [ebp+arg_8]
0x10033ab6  mov     ecx, [eax]
0x10033ab8  jz      short loc_10033B06
0x10033aba  push    3; unsigned int *
0x10033abc  add     edx, esi
0x10033abe  mov     [ebp+var_C], 1
0x10033ac5  push    0Bh; unsigned int
0x10033ac7  push    edx; this
0x10033ac8  mov     edx, 1
0x10033acd  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10033ad2  mov     ebx, [ebp+var_4]
0x10033ad5  xor     edx, edx
0x10033ad7  mov     eax, [ebp+var_18]
0x10033ada  push    offset _IID_IRowsetUpdate; int
0x10033adf  push    eax; unsigned int
0x10033ae0  mov     eax, [ebx]
0x10033ae2  mov     ecx, [eax+38h]
0x10033ae5  mov     ecx, [ecx+10h]
0x10033ae8  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10033aed  test    edi, edi
0x10033aef  jz      loc_10033C39
0x10033af5  mov     eax, [edi]
0x10033af7  mov     dword ptr [esi+eax], 0Ch
0x10033afe  mov     eax, [ebp+var_C]
0x10033b01  jmp     loc_10033C3E
0x10033b06  push    4; unsigned int *
0x10033b08  push    [ebp+var_2C]; unsigned int
0x10033b0b  add     edx, esi
0x10033b0d  push    edx; this
0x10033b0e  mov     edx, 1
0x10033b13  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10033b18  mov     eax, [ebp+var_4]
0x10033b1b  mov     ecx, 1
0x10033b20  mov     [ebp+var_10], ecx
0x10033b23  mov     eax, [eax]
0x10033b25  cmp     dword ptr [eax+0DCh], 0FFFFFFFEh
0x10033b2c  jnz     short loc_10033B50
0x10033b2e  mov     dword ptr [ebx+4], 10h
0x10033b35  test    edi, edi
0x10033b37  jz      short loc_10033B42
0x10033b39  mov     eax, [edi]
0x10033b3b  mov     dword ptr [esi+eax], 0
0x10033b42  mov     ebx, [ebp+var_4]
0x10033b45  mov     eax, [ebp+var_C]
0x10033b48  mov     [ebp+var_10], ecx
0x10033b4b  jmp     loc_10033C41
0x10033b50  mov     eax, [ebp+var_C]
0x10033b53  mov     dword ptr [ebx+4], 8
0x10033b5a  mov     ebx, [ebp+var_4]
0x10033b5d  jmp     loc_10033C41
0x10033b62  test    cl, 4
0x10033b65  jnz     short loc_10033BB2
0x10033b67  test    cl, 8
0x10033b6a  jz      short loc_10033B8C
0x10033b6c  test    edi, edi
0x10033b6e  jz      short loc_10033B79
0x10033b70  mov     eax, [edi]
0x10033b72  mov     dword ptr [esi+eax], 0
0x10033b79  mov     ebx, [ebp+var_4]
0x10033b7c  mov     ecx, 1
0x10033b81  mov     eax, [ebp+var_C]
0x10033b84  mov     [ebp+var_10], ecx
0x10033b87  jmp     loc_10033C41
0x10033b8c  test    cl, 10h
0x10033b8f  jz      loc_10033C31
0x10033b95  test    edi, edi
0x10033b97  jz      short loc_10033BA2
0x10033b99  mov     eax, [edi]
0x10033b9b  mov     dword ptr [esi+eax], 8
0x10033ba2  mov     ebx, [ebp+var_4]
0x10033ba5  mov     eax, 1
0x10033baa  mov     [ebp+var_C], eax
0x10033bad  jmp     loc_10033C3E
0x10033bb2  mov     eax, [ebp+var_4]
0x10033bb5  mov     edx, [ebp+arg_8]
0x10033bb8  push    0; unsigned int *
0x10033bba  add     edx, esi
0x10033bbc  mov     ecx, [eax]
0x10033bbe  push    0Ch; unsigned int
0x10033bc0  push    edx; this
0x10033bc1  mov     edx, 1
0x10033bc6  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10033bcb  test    eax, eax
0x10033bcd  jnz     loc_10033A75
0x10033bd3  test    edi, edi
0x10033bd5  jz      short loc_10033BE0
0x10033bd7  mov     eax, [edi]
0x10033bd9  mov     dword ptr [esi+eax], 0
0x10033be0  mov     eax, [ebp+arg_8]
0x10033be3  mov     edx, 1
0x10033be8  mov     dword ptr [ebx+4], 8
0x10033bef  add     eax, esi
0x10033bf1  mov     ebx, [ebp+var_4]
0x10033bf4  push    4; unsigned int *
0x10033bf6  push    0Ch; unsigned int
0x10033bf8  push    eax; this
0x10033bf9  mov     ecx, [ebx]
0x10033bfb  mov     [ebp+var_10], 1
0x10033c02  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10033c07  mov     eax, [ebp+var_C]
0x10033c0a  mov     ecx, 1
0x10033c0f  jmp     short loc_10033C41
0x10033c11  mov     ebx, [ebp+var_4]
0x10033c14  mov     eax, 1
0x10033c19  mov     ecx, [ebp+var_10]
0x10033c1c  mov     [ebp+var_C], eax
0x10033c1f  test    edi, edi
0x10033c21  jz      short loc_10033C41
0x10033c23  mov     eax, [edi]
0x10033c25  mov     dword ptr [esi+eax], 0Ch
0x10033c2c  mov     eax, [ebp+var_C]
0x10033c2f  jmp     short loc_10033C41
0x10033c31  mov     ebx, [ebp+var_4]
0x10033c34  mov     eax, [ebp+var_C]
0x10033c37  jmp     short loc_10033C3E
0x10033c39  mov     eax, 1
0x10033c3e  mov     ecx, [ebp+var_10]
0x10033c41  mov     edx, [ebp+var_20]
0x10033c44  inc     edx
0x10033c45  mov     [ebp+var_20], edx
0x10033c48  cmp     edx, [ebp+arg_4]
0x10033c4b  jb      loc_10033970
0x10033c51  cmp     ecx, 1
0x10033c54  jnz     short loc_10033C67
0x10033c56  xor     edx, edx
0x10033c58  mov     esi, 40EDAh
0x10033c5d  cmp     eax, ecx
0x10033c5f  cmovnz  esi, edx
0x10033c62  mov     [ebp+var_8], esi
0x10033c65  jmp     short loc_10033C7E
  ... truncated ...
```
