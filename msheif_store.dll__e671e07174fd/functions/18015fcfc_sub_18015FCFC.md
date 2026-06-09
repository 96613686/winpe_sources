# sub_18015FCFC

- ea: `0x18015fcfc`
- end: `0x180160618`
- name: `sub_18015FCFC`
- size: `2332`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x1801590f8`

## callees

- `0x180002d00`
- `0x180059ab4`
- `0x180059eac`
- `0x18005ae04`
- `0x1800f62fc`
- `0x1800f73e8`
- `0x180105a84`
- `0x18010e3c4`
- `0x180155bc0`
- `0x18015fcfc`
- `0x18016a49c`
- `0x18016bffc`
- `0x18016ddf0`
- `0x18016de90`
- `0x180178d90`
- `0x18017dd98`
- `0x180184588`
- `0x180207168`
- `0x1802b9010`

## string_xrefs

- `0x18015fd2a`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x18015ffa3`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x180160021`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x1801600a1`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x18016015e`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x1801601ed`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x180160269`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x180160385`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x180160441`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x180160496`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x180160540`: `CItemPropertiesAtom::AddPropertyForItem`
- `0x1801605ec`: `CItemPropertiesAtom::AddPropertyForItem`

## pseudocode

```c
__int64 __fastcall sub_18015FCFC(_QWORD *a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // r12d
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  _BYTE *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 *v11; // rcx
  int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  unsigned __int16 v20; // r13
  unsigned __int16 v21; // di
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rcx
  _DWORD *v25; // rdx
  __int64 v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 *v50; // rcx
  __int64 v51; // rax
  _DWORD *v52; // r15
  __int64 v53; // rbx
  __int64 v54; // rax
  unsigned __int16 v55; // dx
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 *v62; // rcx
  __int64 v63; // rax
  __int64 *v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // rbx
  __int64 *v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 *v78; // rcx
  __int64 v79; // rax
  _BYTE v80[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v81; // [rsp+34h] [rbp-3Ch]
  __int64 v82; // [rsp+38h] [rbp-38h] BYREF
  __int64 v83; // [rsp+40h] [rbp-30h] BYREF
  _DWORD *v84; // [rsp+48h] [rbp-28h] BYREF
  __int64 v85; // [rsp+50h] [rbp-20h] BYREF
  __int64 v86; // [rsp+58h] [rbp-18h] BYREF

  v81 = a2;
  sub_180059AB4(v80, "CItemPropertiesAtom::AddPropertyForItem", 2071);
  v5 = 0;
  v6 = a1 + 22;
  v7 = 0;
  v82 = 0;
  v83 = 0;
  v86 = 0;
  if ( !a1[22] )
  {
    v8 = sub_18016DE90();
    sub_18016BFFC(a1 + 22, v8);
    if ( !*v6 )
    {
      v11 = (__int64 *)qword_180685260;
      v12 = -2147024882;
      if ( !qword_180685260 )
      {
        v11 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = sub_18005AE04(v11, v9, v10);
        if ( *(_DWORD *)(v13 + 1996) != -2147024882 )
          sub_180207168(v13, "CItemPropertiesAtom::AddPropertyForItem", 2080);
      }
      if ( byte_180685210 )
      {
        v14 = 159;
LABEL_10:
        sub_180105A84(*((_QWORD *)RequestContext + 2), v14, qword_1805E8318, a1, -2147024882);
      }
      goto LABEL_100;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*v6 + 24LL) + 40LL))(*v6 + 24LL, 1768973167);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v6 + 24LL) + 8LL))(*v6 + 24LL);
    v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 208LL))(a1, *v6);
    if ( v12 < 0 )
    {
      v17 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v17 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v18 = sub_18005AE04(v17, v15, v16);
        if ( *(_DWORD *)(v18 + 1996) != v12 )
          sub_180207168(v18, "CItemPropertiesAtom::AddPropertyForItem", 2085);
      }
      if ( byte_180685210 )
      {
        v19 = 160;
LABEL_99:
        sub_180105A84(*((_QWORD *)RequestContext + 2), v19, qword_1805E8318, a1, v12);
      }
      goto LABEL_100;
    }
  }
  v20 = 0;
  v21 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*v6 + 24LL) + 56LL))(*v6 + 24LL, &v86);
  while ( v86 )
  {
    ++v20;
    v22 = a3 + 24;
    if ( !a3 )
      v22 = 0;
    if ( v86 == v22 )
      goto LABEL_74;
    v23 = (*(__int64 (**)(void))(*(_QWORD *)v86 + 24LL))();
    v24 = v86;
    if ( v23 == 1718773093 )
    {
      v21 = v20;
      if ( v7 != v86 )
      {
        sub_1800F73E8(&v83, v86);
        v24 = v86;
        v7 = v83;
      }
    }
    v84 = 0;
    (*(void (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)v24 + 64LL))(v24, &v84);
    v25 = v84;
    v84 = 0;
    sub_18010E3C4(&v86, v25);
    sub_1800F62FC(&v84);
  }
  if ( v21 )
  {
    if ( v7 )
      v26 = v7 - 24;
    else
      v26 = 0;
    v20 = v21;
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)a1[22] + 216LL))(a1[22], v26, a3);
    if ( v12 < 0 )
    {
      v29 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v29 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v30 = sub_18005AE04(v29, v27, v28);
        if ( *(_DWORD *)(v30 + 1996) != v12 )
          sub_180207168(v30, "CItemPropertiesAtom::AddPropertyForItem", 2128);
      }
      if ( byte_180685210 )
      {
        v19 = 161;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
    LODWORD(v84) = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)(v26 + 24) + 48LL))(v26 + 24, &v84);
    if ( v12 < 0 )
    {
      v33 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v33 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v34 = sub_18005AE04(v33, v31, v32);
        if ( *(_DWORD *)(v34 + 1996) != v12 )
          sub_180207168(v34, "CItemPropertiesAtom::AddPropertyForItem", 2133);
      }
      if ( byte_180685210 )
      {
        v19 = 162;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
    LODWORD(v85) = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(a3 + 24) + 48LL))(a3 + 24, &v85);
    if ( v12 < 0 )
    {
      v37 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v37 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v38 = sub_18005AE04(v37, v35, v36);
        if ( *(_DWORD *)(v38 + 1996) != v12 )
          sub_180207168(v38, "CItemPropertiesAtom::AddPropertyForItem", 2136);
      }
      if ( byte_180685210 )
      {
        v19 = 163;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
    if ( (unsigned int)v84 < (int)v85 + 8 )
    {
      v5 = 0;
    }
    else
    {
      *(_DWORD *)(v26 + 176) -= v85;
      sub_180155BC0(v26);
      v39 = *(_QWORD *)(v26 + 24);
      *(_DWORD *)(v26 + 176) = 0;
      *(_QWORD *)(v26 + 144) = 0;
      (*(void (__fastcall **)(__int64))(v39 + 8))(v26 + 24);
      v5 = 0;
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)a1[22] + 208LL))(a1[22], v26);
      if ( v12 < 0 )
      {
        v42 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v42 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v43 = sub_18005AE04(v42, v40, v41);
          if ( *(_DWORD *)(v43 + 1996) != v12 )
            sub_180207168(v43, "CItemPropertiesAtom::AddPropertyForItem", 2152);
        }
        if ( byte_180685210 )
        {
          v19 = 164;
          goto LABEL_99;
        }
        goto LABEL_100;
      }
    }
  }
  else
  {
    ++v20;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(a3 + 24) + 8LL))(a3 + 24);
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)a1[22] + 208LL))(a1[22], a3);
    if ( v12 < 0 )
    {
      v46 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v46 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v47 = sub_18005AE04(v46, v44, v45);
        if ( *(_DWORD *)(v47 + 1996) != v12 )
          sub_180207168(v47, "CItemPropertiesAtom::AddPropertyForItem", 2161);
      }
      if ( byte_180685210 )
      {
        v19 = 165;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
  }
LABEL_74:
  v84 = 0;
  v12 = sub_180178D90((__int64)a1, v81, &v82, &v84);
  if ( v12 < 0 )
  {
    v50 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v50 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v50 + 8) )
    {
      v51 = sub_18005AE04(v50, v48, v49);
      if ( *(_DWORD *)(v51 + 1996) != v12 )
        sub_180207168(v51, "CItemPropertiesAtom::AddPropertyForItem", 2168);
    }
    if ( byte_180685210 )
    {
      v19 = 166;
      goto LABEL_99;
    }
    goto LABEL_100;
  }
  if ( v82 && v82 != 24 )
  {
    v52 = v84;
    v53 = v82 - 24;
    if ( v84 && *v84 )
    {
      while ( 1 )
      {
        v54 = *((_QWORD *)v52 + 1);
        v85 = 0;
        v55 = *(_WORD *)(v54 + 2LL * v5) & 0x7FFF;
        LODWORD(v84) = v55;
        v12 = sub_18017DD98((__int64)a1, v55, &v85);
        if ( v12 < 0 )
          break;
        if ( v85 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v85 + 24LL))(v85) == 1668116580 )
          {
            v12 = sub_180184588(v53, v81, (__int16)v84);
            if ( v12 < 0 )
            {
              v65 = (__int64 *)qword_180685260;
              if ( !qword_180685260 )
              {
                v65 = &qword_180684620;
                qword_180685260 = (__int64)&qword_180684620;
              }
              if ( *((_BYTE *)v65 + 8) )
              {
                v66 = sub_18005AE04(v65, v58, v59);
                if ( *(_DWORD *)(v66 + 1996) != v12 )
                  sub_180207168(v66, "CItemPropertiesAtom::AddPropertyForItem", 2201);
              }
              if ( byte_180685210 )
              {
                v67 = 170;
LABEL_115:
                sub_180105A84(*((_QWORD *)RequestContext + 2), v67, qword_1805E8318, a1, v12);
                goto LABEL_116;
              }
              goto LABEL_116;
            }
          }
        }
        sub_1800F62FC(&v85);
        if ( ++v5 >= *v52 )
          goto LABEL_91;
      }
      v68 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v68 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v68 + 8) )
      {
        v69 = sub_18005AE04(v68, v56, v57);
        if ( *(_DWORD *)(v69 + 1996) != v12 )
          sub_180207168(v69, "CItemPropertiesAtom::AddPropertyForItem", 2195);
      }
      if ( byte_180685210 )
      {
        v67 = 169;
        goto LABEL_115;
      }
LABEL_116:
      sub_1800F62FC(&v85);
      goto LABEL_100;
    }
    goto LABEL_91;
  }
  v70 = sub_18016DDF0();
  sub_18010E3C4(&v82, (v70 + 24) & ((unsigned __int128)-(__int128)(unsigned __int64)v70 >> 64));
  v73 = v82;
  if ( !v82 )
  {
    v74 = (__int64 *)qword_180685260;
    v12 = -2147024882;
    if ( !qword_180685260 )
    {
      v74 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v74 + 8) )
    {
      v75 = sub_18005AE04(v74, v71, v72);
      if ( *(_DWORD *)(v75 + 1996) != -2147024882 )
        sub_180207168(v75, "CItemPropertiesAtom::AddPropertyForItem", 2176);
    }
    if ( byte_180685210 )
    {
      v14 = 167;
      goto LABEL_10;
    }
    goto LABEL_100;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 40LL))(v82, 1768975713);
  v53 = (v73 - 24) & -(__int64)(v73 != 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v53 + 24) + 8LL))(v53 + 24);
  v12 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*a1 + 208LL))(a1, v53);
  if ( v12 >= 0 )
  {
LABEL_91:
    v12 = sub_18016A49C(v53, v81, v20, 1);
    if ( v12 < 0 )
    {
      v62 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v62 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v62 + 8) )
      {
        v63 = sub_18005AE04(v62, v60, v61);
        if ( *(_DWORD *)(v63 + 1996) != v12 )
          sub_180207168(v63, "CItemPropertiesAtom::AddPropertyForItem", 2210);
      }
      if ( byte_180685210 )
      {
        v19 = 171;
        goto LABEL_99;
      }
    }
    goto LABEL_100;
  }
  v78 = (__int64 *)qword_180685260;
  if ( !qword_180685260 )
  {
    v78 = &qword_180684620;
    qword_180685260 = (__int64)&qword_180684620;
  }
  if ( *((_BYTE *)v78 + 8) )
  {
    v79 = sub_18005AE04(v78, v76, v77);
    if ( *(_DWORD *)(v79 + 1996) != v12 )
      sub_180207168(v79, "CItemPropertiesAtom::AddPropertyForItem", 2183);
  }
  if ( byte_180685210 )
  {
    v19 = 168;
    goto LABEL_99;
  }
LABEL_100:
  sub_1800F62FC(&v83);
  sub_1800F62FC(&v86);
  sub_1800F62FC(&v82);
  sub_180059EAC(v80);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18015fcfc  mov     [rsp-38h+arg_18], rbx
0x18015fd01  push    rbp
0x18015fd02  push    rsi
0x18015fd03  push    rdi
0x18015fd04  push    r12
0x18015fd06  push    r13
0x18015fd08  push    r14
0x18015fd0a  push    r15
0x18015fd0c  mov     rbp, rsp
0x18015fd0f  sub     rsp, 70h
0x18015fd13  mov     rax, cs:__security_cookie
0x18015fd1a  xor     rax, rsp
0x18015fd1d  mov     [rbp+var_10], rax
0x18015fd21  mov     r15, r8
0x18015fd24  mov     [rbp+var_3C], edx
0x18015fd27  mov     r14, rcx
0x18015fd2a  lea     r13, aCitempropertie; "CItemPropertiesAtom::AddPropertyForItem"
0x18015fd31  mov     rdx, r13
0x18015fd34  lea     rcx, [rbp+var_40]
0x18015fd38  mov     r8d, 817h
0x18015fd3e  call    sub_180059AB4
0x18015fd43  xor     r12d, r12d
0x18015fd46  lea     rsi, [r14+0B0h]
0x18015fd4d  mov     ebx, r12d
0x18015fd50  mov     [rbp+var_38], r12
0x18015fd54  mov     [rbp+var_30], rbx
0x18015fd58  mov     [rbp+var_18], r12
0x18015fd5c  cmp     [rsi], r12
0x18015fd5f  jnz     loc_18015FE85
0x18015fd65  call    sub_18016DE90
0x18015fd6a  mov     rdx, rax
0x18015fd6d  mov     rcx, rsi
0x18015fd70  call    sub_18016BFFC
0x18015fd75  mov     rcx, [rsi]
0x18015fd78  test    rcx, rcx
0x18015fd7b  jnz     short loc_18015FDE5
0x18015fd7d  mov     rcx, cs:qword_180685260
0x18015fd84  mov     ebx, 8007000Eh
0x18015fd89  mov     edi, ebx
0x18015fd8b  test    rcx, rcx
0x18015fd8e  jnz     short loc_18015FD9E
0x18015fd90  lea     rcx, qword_180684620
0x18015fd97  mov     cs:qword_180685260, rcx
0x18015fd9e  cmp     [rcx+8], r12b
0x18015fda2  jz      short loc_18015FDC5
0x18015fda4  call    sub_18005AE04
0x18015fda9  cmp     [rax+7CCh], ebx
0x18015fdaf  jz      short loc_18015FDC5
0x18015fdb1  mov     r9d, ebx
0x18015fdb4  mov     r8d, 820h
0x18015fdba  mov     rdx, r13
0x18015fdbd  mov     rcx, rax
0x18015fdc0  call    sub_180207168
0x18015fdc5  mov     esi, 1
0x18015fdca  cmp     cs:byte_180685210, sil
0x18015fdd1  jb      loc_1801603C6
0x18015fdd7  mov     edx, 9Fh
0x18015fddc  mov     [rsp+70h+var_50], ebx
0x18015fde0  jmp     loc_1801603AC
0x18015fde5  add     rcx, 18h
0x18015fde9  mov     edx, 6970636Fh
0x18015fdee  mov     rax, [rcx]
0x18015fdf1  mov     rax, [rax+28h]
0x18015fdf5  call    j__guard_dispatch_icall
0x18015fdfa  mov     rcx, [rsi]
0x18015fdfd  add     rcx, 18h
0x18015fe01  mov     rax, [rcx]
0x18015fe04  mov     rax, [rax+8]
0x18015fe08  call    j__guard_dispatch_icall
0x18015fe0d  mov     rax, [r14]
0x18015fe10  mov     rcx, r14
0x18015fe13  mov     rdx, [rsi]
0x18015fe16  mov     rax, [rax+0D0h]
0x18015fe1d  call    j__guard_dispatch_icall
0x18015fe22  mov     edi, eax
0x18015fe24  test    eax, eax
0x18015fe26  jns     short loc_18015FE85
0x18015fe28  mov     rcx, cs:qword_180685260
0x18015fe2f  test    rcx, rcx
0x18015fe32  jnz     short loc_18015FE42
0x18015fe34  lea     rcx, qword_180684620
0x18015fe3b  mov     cs:qword_180685260, rcx
0x18015fe42  cmp     [rcx+8], r12b
0x18015fe46  jz      short loc_18015FE69
0x18015fe48  call    sub_18005AE04
0x18015fe4d  cmp     [rax+7CCh], edi
0x18015fe53  jz      short loc_18015FE69
0x18015fe55  mov     r9d, edi
0x18015fe58  mov     r8d, 825h
0x18015fe5e  mov     rdx, r13
0x18015fe61  mov     rcx, rax
0x18015fe64  call    sub_180207168
0x18015fe69  mov     esi, 1
0x18015fe6e  cmp     cs:byte_180685210, sil
0x18015fe75  jb      loc_1801603C6
0x18015fe7b  mov     edx, 0A0h
0x18015fe80  jmp     loc_1801603A8
0x18015fe85  mov     rcx, [rsi]
0x18015fe88  lea     rdx, [rbp+var_18]
0x18015fe8c  add     rcx, 18h
0x18015fe90  movzx   r13d, r12w
0x18015fe94  movzx   edi, r12w
0x18015fe98  mov     rax, [rcx]
0x18015fe9b  mov     rax, [rax+38h]
0x18015fe9f  call    j__guard_dispatch_icall
0x18015fea4  mov     esi, 1
0x18015fea9  mov     rcx, [rbp+var_18]
0x18015fead  test    rcx, rcx
0x18015feb0  jz      loc_18015FF36
0x18015feb6  add     r13w, si
0x18015feba  lea     rax, [r15+18h]
0x18015febe  test    r15, r15
0x18015fec1  jnz     short loc_18015FEC6
0x18015fec3  mov     rax, r12
0x18015fec6  cmp     rcx, rax
0x18015fec9  jz      loc_18016021C
0x18015fecf  mov     rax, [rcx]
0x18015fed2  mov     rax, [rax+18h]
0x18015fed6  call    j__guard_dispatch_icall
0x18015fedb  mov     rcx, [rbp+var_18]
0x18015fedf  cmp     eax, 66726565h
0x18015fee4  jnz     short loc_18015FF03
0x18015fee6  movzx   edi, r13w
0x18015feea  cmp     rbx, rcx
0x18015feed  jz      short loc_18015FF03
0x18015feef  mov     rdx, rcx
0x18015fef2  lea     rcx, [rbp+var_30]
0x18015fef6  call    sub_1800F73E8
0x18015fefb  mov     rcx, [rbp+var_18]
0x18015feff  mov     rbx, [rbp+var_30]
0x18015ff03  mov     [rbp+var_28], r12
0x18015ff07  lea     rdx, [rbp+var_28]
0x18015ff0b  mov     rax, [rcx]
0x18015ff0e  mov     rax, [rax+40h]
0x18015ff12  call    j__guard_dispatch_icall
0x18015ff17  mov     rdx, [rbp+var_28]
0x18015ff1b  lea     rcx, [rbp+var_18]
0x18015ff1f  mov     [rbp+var_28], r12
0x18015ff23  call    sub_18010E3C4
0x18015ff28  lea     rcx, [rbp+var_28]
0x18015ff2c  call    sub_1800F62FC
0x18015ff31  jmp     loc_18015FEA9
0x18015ff36  test    di, di
0x18015ff39  jz      loc_18016018A
0x18015ff3f  test    rbx, rbx
0x18015ff42  jz      short loc_18015FF4A
0x18015ff44  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18015ff48  jmp     short loc_18015FF4D
0x18015ff4a  mov     rbx, r12
0x18015ff4d  mov     rcx, [r14+0B0h]
0x18015ff54  mov     r8, r15
0x18015ff57  mov     rdx, rbx
0x18015ff5a  movzx   r13d, di
0x18015ff5e  mov     rax, [rcx]
0x18015ff61  mov     rax, [rax+0D8h]
0x18015ff68  call    j__guard_dispatch_icall
0x18015ff6d  mov     edi, eax
0x18015ff6f  test    eax, eax
0x18015ff71  jns     short loc_18015FFCF
0x18015ff73  mov     rcx, cs:qword_180685260
0x18015ff7a  test    rcx, rcx
0x18015ff7d  jnz     short loc_18015FF8D
0x18015ff7f  lea     rcx, qword_180684620
0x18015ff86  mov     cs:qword_180685260, rcx
0x18015ff8d  cmp     [rcx+8], r12b
0x18015ff91  jz      short loc_18015FFB8
0x18015ff93  call    sub_18005AE04
0x18015ff98  cmp     [rax+7CCh], edi
0x18015ff9e  jz      short loc_18015FFB8
0x18015ffa0  mov     r9d, edi
0x18015ffa3  lea     rdx, aCitempropertie; "CItemPropertiesAtom::AddPropertyForItem"
0x18015ffaa  mov     r8d, 850h
0x18015ffb0  mov     rcx, rax
0x18015ffb3  call    sub_180207168
0x18015ffb8  cmp     cs:byte_180685210, sil
0x18015ffbf  jb      loc_1801603C6
0x18015ffc5  mov     edx, 0A1h
0x18015ffca  jmp     loc_1801603A8
0x18015ffcf  mov     dword ptr [rbp+var_28], r12d
0x18015ffd3  lea     rdx, [rbp+var_28]
0x18015ffd7  lea     r12, [rbx+18h]
0x18015ffdb  mov     rax, [r12]
0x18015ffdf  mov     rcx, r12
0x18015ffe2  mov     rax, [rax+30h]
0x18015ffe6  call    j__guard_dispatch_icall
0x18015ffeb  mov     edi, eax
0x18015ffed  test    eax, eax
0x18015ffef  jns     short loc_18016004D
0x18015fff1  mov     rcx, cs:qword_180685260
0x18015fff8  test    rcx, rcx
0x18015fffb  jnz     short loc_18016000B
0x18015fffd  lea     rcx, qword_180684620
0x180160004  mov     cs:qword_180685260, rcx
0x18016000b  cmp     byte ptr [rcx+8], 0
0x18016000f  jz      short loc_180160036
0x180160011  call    sub_18005AE04
0x180160016  cmp     [rax+7CCh], edi
0x18016001c  jz      short loc_180160036
0x18016001e  mov     r9d, edi
0x180160021  lea     rdx, aCitempropertie; "CItemPropertiesAtom::AddPropertyForItem"
0x180160028  mov     r8d, 855h
0x18016002e  mov     rcx, rax
0x180160031  call    sub_180207168
0x180160036  cmp     cs:byte_180685210, sil
0x18016003d  jb      loc_1801603C6
0x180160043  mov     edx, 0A2h
0x180160048  jmp     loc_1801603A8
0x18016004d  lea     rcx, [r15+18h]
0x180160051  mov     dword ptr [rbp+var_20], 0
0x180160058  mov     rax, [rcx]
0x18016005b  lea     rdx, [rbp+var_20]
0x18016005f  mov     rax, [rax+30h]
0x180160063  call    j__guard_dispatch_icall
0x180160068  xor     r15d, r15d
0x18016006b  mov     edi, eax
0x18016006d  test    eax, eax
0x18016006f  jns     short loc_1801600CD
0x180160071  mov     rcx, cs:qword_180685260
0x180160078  test    rcx, rcx
0x18016007b  jnz     short loc_18016008B
0x18016007d  lea     rcx, qword_180684620
0x180160084  mov     cs:qword_180685260, rcx
0x18016008b  cmp     [rcx+8], r15b
0x18016008f  jz      short loc_1801600B6
0x180160091  call    sub_18005AE04
0x180160096  cmp     [rax+7CCh], edi
0x18016009c  jz      short loc_1801600B6
0x18016009e  mov     r9d, edi
0x1801600a1  lea     rdx, aCitempropertie; "CItemPropertiesAtom::AddPropertyForItem"
0x1801600a8  mov     r8d, 858h
0x1801600ae  mov     rcx, rax
0x1801600b1  call    sub_180207168
0x1801600b6  cmp     cs:byte_180685210, sil
0x1801600bd  jb      loc_1801603C6
0x1801600c3  mov     edx, 0A3h
0x1801600c8  jmp     loc_1801603A8
0x1801600cd  mov     ecx, dword ptr [rbp+var_20]
0x1801600d0  lea     eax, [rcx+8]
0x1801600d3  cmp     dword ptr [rbp+var_28], eax
0x1801600d6  jb      loc_180160219
0x1801600dc  sub     [rbx+0B0h], ecx
0x1801600e2  mov     rcx, rbx
0x1801600e5  call    sub_180155BC0
0x1801600ea  mov     rax, [r12]
0x1801600ee  mov     rcx, r12
0x1801600f1  mov     [rbx+0B0h], r15d
0x1801600f8  mov     [rbx+90h], r15
0x1801600ff  mov     rax, [rax+8]
0x180160103  call    j__guard_dispatch_icall
0x180160108  mov     rcx, [r14+0B0h]
0x18016010f  mov     rdx, rbx
0x180160112  mov     rax, [rcx]
0x180160115  mov     rax, [rax+0D0h]
0x18016011c  call    j__guard_dispatch_icall
0x180160121  xor     r12d, r12d
0x180160124  mov     edi, eax
0x180160126  test    eax, eax
0x180160128  jns     loc_18016021C
0x18016012e  mov     rcx, cs:qword_180685260
0x180160135  test    rcx, rcx
0x180160138  jnz     short loc_180160148
0x18016013a  lea     rcx, qword_180684620
0x180160141  mov     cs:qword_180685260, rcx
0x180160148  cmp     [rcx+8], r12b
0x18016014c  jz      short loc_180160173
0x18016014e  call    sub_18005AE04
0x180160153  cmp     [rax+7CCh], edi
0x180160159  jz      short loc_180160173
0x18016015b  mov     r9d, edi
0x18016015e  lea     rdx, aCitempropertie; "CItemPropertiesAtom::AddPropertyForItem"
0x180160165  mov     r8d, 868h
0x18016016b  mov     rcx, rax
0x18016016e  call    sub_180207168
0x180160173  cmp     cs:byte_180685210, sil
0x18016017a  jb      loc_1801603C6
0x180160180  mov     edx, 0A4h
0x180160185  jmp     loc_1801603A8
0x18016018a  lea     rcx, [r15+18h]
0x18016018e  add     r13w, si
0x180160192  mov     rax, [rcx]
0x180160195  mov     rax, [rax+8]
0x180160199  call    j__guard_dispatch_icall
0x18016019e  mov     rcx, [r14+0B0h]
0x1801601a5  mov     rdx, r15
0x1801601a8  mov     rax, [rcx]
0x1801601ab  mov     rax, [rax+0D0h]
0x1801601b2  call    j__guard_dispatch_icall
0x1801601b7  mov     edi, eax
0x1801601b9  test    eax, eax
0x1801601bb  jns     short loc_18016021C
0x1801601bd  mov     rcx, cs:qword_180685260
0x1801601c4  test    rcx, rcx
0x1801601c7  jnz     short loc_1801601D7
0x1801601c9  lea     rcx, qword_180684620
0x1801601d0  mov     cs:qword_180685260, rcx
0x1801601d7  cmp     [rcx+8], r12b
0x1801601db  jz      short loc_180160202
0x1801601dd  call    sub_18005AE04
0x1801601e2  cmp     [rax+7CCh], edi
0x1801601e8  jz      short loc_180160202
  ... truncated ...
```
