# PortablePDB::Validate(long &)

- ea: `0x18004da00`
- end: `0x18004e7ec`
- name: `?Validate@PortablePDB@@QEAAHAEAJ@Z`
- size: `3564`
- prototype: `__int64 __fastcall(PortablePDB *__hidden this, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800333d0`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x180027430`
- `0x180027440`
- `0x1800352f0`
- `0x180049540`
- `0x18004da00`
- `0x180169440`
- `0x180169458`
- `0x1801d6350`

## string_xrefs

- `0x18004e481`: `Range error during +=`
- `0x18004e4c7`: `Range error during +=`
- `0x18004e4ea`: `Range error during +=`
- `0x18004e71a`: `Range error during null terminator search`
- `0x18004e73d`: `Range error during makeSubRange`
- `0x18004e530`: `Range error during currentVoidPtr`
- `0x18004e576`: `Range error during currentVoidPtr`
- `0x18004e5bc`: `Range error during currentVoidPtr`
- `0x18004e602`: `Range error during currentVoidPtr`
- `0x18004e648`: `Range error during currentVoidPtr`
- `0x18004e68e`: `Range error during currentVoidPtr`
- `0x18004e6d4`: `Range error during currentVoidPtr`
- `0x18004e760`: `Range error during currentVoidPtr`
- `0x18004e7a6`: `Range error during currentVoidPtr`
- `0x18004e4a4`: `Range error during peek`
- `0x18004e553`: `Range error during peek`
- `0x18004e599`: `Range error during peek`
- `0x18004e5df`: `Range error during peek`
- `0x18004e625`: `Range error during peek`
- `0x18004e66b`: `Range error during peek`
- `0x18004e6b1`: `Range error during peek`
- `0x18004e6f7`: `Range error during peek`
- `0x18004e45e`: `Range error during read`
- `0x18004e50d`: `Range error during read`
- `0x18004e783`: `Range error during read`
- `0x18004e7c9`: `Range error during read`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PortablePDB::Validate(PortablePDB *this, int *a2)
{
  PortablePDB *v2; // r13
  unsigned __int64 v3; // rax
  _DWORD *v4; // r8
  unsigned __int64 v5; // rsi
  unsigned int *v6; // rcx
  unsigned __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  unsigned int *v9; // rdx
  unsigned int v10; // r9d
  unsigned int *v11; // rcx
  unsigned int *v12; // r15
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  _BYTE *v15; // rax
  _BYTE *v16; // r14
  __int64 v17; // r14
  unsigned int v18; // edx
  unsigned int v19; // eax
  unsigned __int64 v20; // r13
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // r12
  unsigned __int64 v24; // rdx
  _QWORD *v25; // rcx
  PortablePDB *v26; // r9
  unsigned int v27; // r8d
  __int64 v28; // rcx
  __int64 v29; // rdx
  _QWORD *v30; // r12
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int64 *v33; // r12
  unsigned __int64 v34; // r12
  int v35; // r14d
  __int64 v36; // r15
  unsigned int i; // edx
  unsigned int *v38; // rcx
  unsigned int v39; // eax
  unsigned int *v40; // rdx
  __int64 v41; // rcx
  _DWORD *v42; // rax
  char *v43; // rax
  char v44; // cl
  _QWORD *v45; // rax
  unsigned int v46; // r8d
  __int64 v47; // r9
  int v48; // edx
  unsigned int *v49; // rax
  unsigned int v50; // eax
  unsigned int v51; // r8d
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rcx
  _BYTE pExceptionObject[16]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v57; // [rsp+30h] [rbp-D0h]
  int v58; // [rsp+40h] [rbp-C0h]
  unsigned int v59; // [rsp+44h] [rbp-BCh]
  unsigned __int64 v60; // [rsp+48h] [rbp-B8h]
  unsigned int v61; // [rsp+50h] [rbp-B0h]
  PortablePDB *v62; // [rsp+58h] [rbp-A8h]
  int *v63; // [rsp+60h] [rbp-A0h]
  _DWORD v64[6]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h]
  int v66; // [rsp+90h] [rbp-70h]
  int v67; // [rsp+94h] [rbp-6Ch]
  int v68; // [rsp+98h] [rbp-68h]
  int v69; // [rsp+9Ch] [rbp-64h]
  int v70; // [rsp+A0h] [rbp-60h]
  int v71; // [rsp+A4h] [rbp-5Ch]
  int v72; // [rsp+A8h] [rbp-58h]
  int v73; // [rsp+ACh] [rbp-54h]
  int v74; // [rsp+B0h] [rbp-50h]
  int v75; // [rsp+B4h] [rbp-4Ch]
  int v76; // [rsp+B8h] [rbp-48h]
  int v77; // [rsp+BCh] [rbp-44h]
  int v78; // [rsp+C0h] [rbp-40h]
  int v79; // [rsp+C4h] [rbp-3Ch]
  char v80; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int *v81; // [rsp+D0h] [rbp-30h]
  _DWORD *v82; // [rsp+D8h] [rbp-28h]
  __int64 v83; // [rsp+E0h] [rbp-20h]
  _QWORD *v84; // [rsp+E8h] [rbp-18h]
  _DWORD v85[64]; // [rsp+F0h] [rbp-10h] BYREF

  v83 = -2;
  v63 = a2;
  v2 = this;
  v62 = this;
  v3 = *((_QWORD *)this + 6);
  if ( v3 < 0x10 )
    goto LABEL_195;
  v4 = (_DWORD *)*((_QWORD *)this + 5);
  v82 = v4;
  v5 = (unsigned __int64)v4 + v3;
  if ( (_DWORD *)((char *)v4 + v3) < v4 || v4 + 1 < v4 )
    goto LABEL_197;
  if ( (unsigned __int64)(v4 + 1) > v5 )
  {
    std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during read");
    throw (std::range_error *)pExceptionObject;
  }
  if ( *v4 != 1112167234 )
  {
    *a2 = 11;
    return 0;
  }
  v6 = v4 + 3;
  if ( v4 + 3 < v4 + 1 )
    goto LABEL_197;
  if ( (unsigned __int64)v6 > v5 )
  {
    std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during +=");
    throw (std::range_error *)pExceptionObject;
  }
  if ( v4 + 4 < v4 + 3 )
    goto LABEL_197;
  if ( (unsigned __int64)(v4 + 4) > v5 )
  {
    std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
    throw (std::range_error *)pExceptionObject;
  }
  v7 = (unsigned __int64)v6 + *v6;
  if ( v7 < (unsigned __int64)v6 )
    goto LABEL_197;
  if ( v7 > v5 )
  {
    std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during +=");
    throw (std::range_error *)pExceptionObject;
  }
  v8 = (unsigned __int16 *)(v7 + 6);
  if ( v7 + 6 < v7 )
    goto LABEL_197;
  if ( (unsigned __int64)v8 > v5 )
  {
    std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during +=");
    throw (std::range_error *)pExceptionObject;
  }
  v9 = (unsigned int *)(v7 + 8);
  if ( v8 + 1 < v8 )
LABEL_197:
    msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
  if ( (unsigned __int64)v9 > v5 )
  {
    std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during read");
    throw (std::range_error *)pExceptionObject;
  }
  v61 = *v8;
  v10 = 0;
  v58 = 0;
  if ( !v61 )
  {
    v30 = (_QWORD *)((char *)v2 + 1152);
LABEL_175:
    v51 = *((_DWORD *)v2 + 290);
    if ( v51 )
    {
      do
      {
        v52 = *v30 + 32LL * v10;
        v53 = *(_QWORD *)(v52 + 16);
        v54 = *(_QWORD *)(v52 + 24);
        if ( v54 == 4 )
        {
          if ( *(_DWORD *)v53 == 1650741283 )
            *((_QWORD *)v2 + 8) = v52;
        }
        else if ( v54 == 2 && *(_WORD *)v53 == 32291 )
        {
          *((_QWORD *)v2 + 9) = v52;
        }
        else if ( v54 == 5 )
        {
          if ( *(_DWORD *)v53 == 1230325539 && *(_BYTE *)(v53 + 4) == 68 )
          {
            *((_QWORD *)v2 + 10) = v52;
          }
          else if ( *(_DWORD *)v53 == 1869365795 && *(_BYTE *)(v53 + 4) == 98 )
          {
            *((_QWORD *)v2 + 11) = v52;
          }
        }
        ++v10;
      }
      while ( v10 < v51 );
    }
    if ( !*((_QWORD *)v2 + 8) || !*((_QWORD *)v2 + 9) || !*((_QWORD *)v2 + 10) || !*((_QWORD *)v2 + 11) )
      goto LABEL_195;
    return 1;
  }
  while ( 1 )
  {
    v11 = v9 + 1;
    if ( v9 + 1 < v9 )
      goto LABEL_197;
    if ( (unsigned __int64)v11 > v5 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during read");
      throw (std::range_error *)pExceptionObject;
    }
    if ( (unsigned __int64)v9 > v5 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
      throw (std::range_error *)pExceptionObject;
    }
    v12 = v9 + 2;
    if ( v9 + 2 < v9 + 1 )
      goto LABEL_197;
    if ( (unsigned __int64)v12 > v5 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during read");
      throw (std::range_error *)pExceptionObject;
    }
    if ( (unsigned __int64)v11 > v5 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
      throw (std::range_error *)pExceptionObject;
    }
    v13 = (unsigned __int64)v4 + *v9;
    if ( v13 < (unsigned __int64)v4 )
      goto LABEL_197;
    v14 = v13 + *v11;
    if ( v14 < v13 )
      goto LABEL_197;
    if ( v13 > v5 || v14 > v5 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during makeSubRange");
      throw (std::range_error *)pExceptionObject;
    }
    v15 = memchr_0(v9 + 2, 0, v5 - (_QWORD)v12);
    v16 = (_BYTE *)v5;
    if ( v15 )
      v16 = v15;
    if ( v16 == (_BYTE *)v5 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during null terminator search");
      throw (std::range_error *)pExceptionObject;
    }
    v17 = v16 - (_BYTE *)v12;
    v81 = (unsigned int *)((char *)v12 + ((v17 + 4) & 0xFFFFFFFFFFFFFFFCuLL));
    if ( v81 < v12 )
      goto LABEL_197;
    *(_QWORD *)&v57 = v12;
    *((_QWORD *)&v57 + 1) = v17;
    LODWORD(v60) = *((_DWORD *)v2 + 290);
    v18 = v60 + 1;
    v59 = v60 + 1;
    if ( (unsigned int)(v60 + 1) > 0x7FFFFFF )
      goto LABEL_173;
    v19 = *((_DWORD *)v2 + 291);
    if ( v18 > v19 )
    {
      v20 = v18;
      if ( v18 <= (unsigned __int64)(3 * v19) >> 1 )
        v20 = (unsigned __int64)(3 * v19) >> 1;
      if ( v20 > 0x7FFFFFF )
        v20 = 0x7FFFFFF;
      v21 = 32 * v20;
      if ( !is_mul_ok(v20, 0x20u) )
        v21 = -1;
      v22 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
      v23 = v22;
      v84 = v22;
      if ( v22 )
      {
        v24 = v20;
        v25 = v22;
        for ( LODWORD(v22) = 0; v24; --v24 )
        {
          *v25 = 0;
          v25[1] = 0;
          v25[2] = 0;
          v25[3] = 0;
          v25 += 4;
        }
      }
      else
      {
        v23 = 0;
      }
      if ( !v23 )
      {
LABEL_173:
        *v63 = 2;
        return 0;
      }
      v26 = v62;
      if ( *((_QWORD *)v62 + 144) )
      {
        v27 = (unsigned int)v22;
        if ( *((_DWORD *)v62 + 290) )
        {
          do
          {
            v28 = 4LL * v27;
            v29 = *((_QWORD *)v26 + 144);
            v23[v28] = *(_QWORD *)(v29 + v28 * 8);
            v23[v28 + 1] = *(_QWORD *)(v29 + v28 * 8 + 8);
            *(_OWORD *)&v23[v28 + 2] = *(_OWORD *)(v29 + v28 * 8 + 16);
            ++v27;
          }
          while ( v27 < *((_DWORD *)v26 + 290) );
        }
        PSGSI1::EnumPubsByAddr::release(*((PSGSI1::EnumPubsByAddr **)v26 + 144));
        v26 = v62;
      }
      *((_QWORD *)v26 + 144) = v23;
      *((_DWORD *)v26 + 291) = v20;
      v18 = v59;
      v2 = v62;
    }
    *((_DWORD *)v2 + 290) = v18;
    v30 = (_QWORD *)((char *)v2 + 1152);
    v31 = 32LL * (unsigned int)v60;
    v32 = *((_QWORD *)v2 + 144);
    *(_QWORD *)(v31 + v32) = v13;
    *(_QWORD *)(v31 + v32 + 8) = v14;
    *(_OWORD *)(v31 + v32 + 16) = v57;
    if ( v17 != 4 || memcmp_0(v12, "#Pdb", 4u) )
      break;
    if ( v13 > v14 )
      goto LABEL_197;
    v60 = v14 - v13;
    if ( v14 - v13 < 0x20 )
      goto LABEL_195;
    v33 = (unsigned __int64 *)(v13 + 24);
    if ( v13 + 24 < v13 || v13 + 32 < v13 + 24 )
      goto LABEL_197;
    if ( v13 + 32 > v14 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
      throw (std::range_error *)pExceptionObject;
    }
    if ( (unsigned __int64)v33 > v14 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
      throw (std::range_error *)pExceptionObject;
    }
    v34 = *v33;
    v35 = 32;
    v36 = 0;
    memset_0(v85, 0, sizeof(v85));
    v10 = 0;
    for ( i = 0; i < 0x40; i += 16 )
    {
      if ( ((v34 >> i) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 1)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 1] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 2)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 2] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 3)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 3] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 4)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 4] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 5)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 5] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 6)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 6] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 7)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 7] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 8)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 8] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 9)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 9] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 10)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 10] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 11)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 11] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 12)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 12] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 13)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 13] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 14)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 14] = v35;
        v35 += 4;
      }
      if ( ((v34 >> ((unsigned __int8)i + 15)) & 1) != 0 )
      {
        v36 = (unsigned int)(v36 + 1);
        v85[i + 15] = v35;
        v35 += 4;
      }
    }
    if ( v60 < 4 * v36 + 32 )
      goto LABEL_195;
    if ( (v34 & 0x40) != 0 )
    {
      v38 = (unsigned int *)(v13 + v85[6]);
      if ( (unsigned __int64)v38 < v13 || v38 + 1 < v38 )
        goto LABEL_197;
      if ( (unsigned __int64)(v38 + 1) > v14 )
      {
        std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
        throw (std::range_error *)pExceptionObject;
      }
      if ( (unsigned __int64)v38 > v14 )
      {
        std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
        throw (std::range_error *)pExceptionObject;
      }
      v39 = *v38;
      *((_DWORD *)v2 + 162) = *v38;
      if ( v39 > 0xFFFFFF )
        goto LABEL_195;
      if ( (v39 & 0xFFFF0000) != 0 )
        *((_DWORD *)v2 + 161) = 4;
    }
    v64[0] = 6;
    v64[1] = 4;
    v64[2] = 1;
    v64[3] = 2;
    v64[4] = 8;
    v64[5] = 9;
    v65 = 10;
    v66 = 14;
    v67 = 23;
    v68 = 20;
    v69 = 17;
    v70 = 26;
    v71 = 27;
    v72 = 32;
    v73 = 35;
    v74 = 38;
    v75 = 39;
    v76 = 40;
    v77 = 42;
    v78 = 44;
    v79 = 43;
    v40 = v64;
    while ( 1 )
    {
      v41 = *v40;
      if ( ((v34 >> v41) & 1) != 0 )
      {
        v42 = (_DWORD *)(v13 + (unsigned int)v85[v41]);
        if ( (unsigned __int64)v42 < v13 || v42 + 1 < v42 )
          goto LABEL_197;
        if ( (unsigned __int64)(v42 + 1) > v14 )
        {
          std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
          throw (std::range_error *)pExceptionObject;
        }
        if ( (unsigned __int64)v42 > v14 )
        {
          std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
          throw (std::range_error *)pExceptionObject;
        }
        if ( *v42 > 0xFFFFFFu )
          goto LABEL_195;
        if ( *v42 >= 0x800u )
          break;
      }
      if ( ++v40 == (unsigned int *)&v80 )
        goto LABEL_111;
    }
    *((_DWORD *)v2 + 163) = 4;
LABEL_111:
    v30 = (_QWORD *)((char *)v2 + 1152);
LABEL_112:
    if ( ++v58 >= v61 )
      goto LABEL_175;
    v9 = v81;
    v4 = v82;
  }
  if ( v17 != 2 || memcmp_0(v12, "#~", 2u) )
  {
    if ( v17 == 5 && !memcmp_0(v12, "#GUID", 5u) )
    {
      if ( v13 > v14 )
        goto LABEL_197;
      if ( (((_BYTE)v14 - (_BYTE)v13) & 0xF) != 0 )
        goto LABEL_195;
      v10 = 0;
    }
    else
    {
LABEL_167:
      v10 = 0;
    }
    goto LABEL_112;
  }
  if ( v13 > v14 )
    goto LABEL_197;
  if ( v14 - v13 >= 0x24 )
  {
    v43 = (char *)(v13 + 6);
    if ( v13 + 6 < v13 || v13 + 7 < v13 + 6 )
      goto LABEL_197;
    if ( v13 + 7 > v14 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
      throw (std::range_error *)pExceptionObject;
    }
    if ( (unsigned __int64)v43 > v14 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
      throw (std::range_error *)pExceptionObject;
    }
    v44 = *v43;
    if ( (*v43 & 1) != 0 )
      *((_DWORD *)v2 + 160) = 4;
    if ( (v44 & 2) != 0 )
      *((_DWORD *)v2 + 159) = 4;
    if ( (v44 & 4) != 0 )
      *((_DWORD *)v2 + 158) = 4;
    v45 = (_QWORD *)(v13 + 8);
    if ( v13 + 8 < v13 || v13 + 16 < v13 + 8 )
      goto LABEL_197;
    if ( v13 + 16 > v14 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
      throw (std::range_error *)pExceptionObject;
    }
    if ( (unsigned __int64)v45 > v14 )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
      throw (std::range_error *)pExceptionObject;
    }
    if ( (*v45 & 0xFFFFFFFFFFFFLL) == 0 )
    {
      if ( v13 + 14 >= v13 && v13 + 16 >= v13 + 14 )
      {
        if ( v13 + 16 > v14 )
        {
          std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
          throw (std::range_error *)pExceptionObject;
        }
        if ( v13 + 14 > v14 )
        {
          std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
          throw (std::range_error *)pExceptionObject;
        }
        v46 = 24;
        v47 = HIWORD(*v45);
        v48 = 0;
        while ( 1 )
        {
          if ( (((unsigned __int16)v47 >> v48) & 1) != 0 )
          {
            ++*((_DWORD *)v2 + 172);
            if ( v14 - v13 < (unsigned __int64)v46 + 4 )
              goto LABEL_195;
            v49 = (unsigned int *)(v13 + v46);
            if ( (unsigned __int64)v49 < v13 || v49 + 1 < v49 )
              goto LABEL_197;
            if ( (unsigned __int64)(v49 + 1) > v14 )
            {
              std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during peek");
              throw (std::range_error *)pExceptionObject;
            }
            if ( (unsigned __int64)v49 > v14 )
            {
              std::range_error::range_error((std::range_error *)pExceptionObject, "Range error during currentVoidPtr");
              throw (std::range_error *)pExceptionObject;
            }
            v50 = *v49;
            if ( v50 > 0xFFFFFF )
              goto LABEL_195;
            v46 += 4;
            if ( v48 )
            {
              switch ( v48 )
              {
                case 1:
                  *((_DWORD *)v2 + 165) = v50;
                  break;
                case 2:
                  *((_DWORD *)v2 + 166) = v50;
                  break;
                case 3:
                  *((_DWORD *)v2 + 167) = v50;
                  break;
                case 4:
                  *((_DWORD *)v2 + 168) = v50;
                  break;
                case 5:
                  *((_DWORD *)v2 + 169) = v50;
                  break;
                case 6:
                  *((_DWORD *)v2 + 170) = v50;
                  break;
                case 7:
                  *((_DWORD *)v2 + 171) = v50;
                  break;
              }
            }
            else
            {
              *((_DWORD *)v2 + 164) = v50;
            }
            if ( v50 >= 0x800 && (!v48 || (unsigned int)(v48 - 2) <= 3) )
              *((_DWORD *)v2 + 163) = 4;
          }
          if ( (unsigned int)++v48 >= 0x10 )
            goto LABEL_167;
        }
      }
      goto LABEL_197;
    }
  }
LABEL_195:
  *v63 = 13;
  return 0;
}

```

## disassembly

```asm
0x18004da00  push    rbp
0x18004da02  push    rsi
0x18004da03  push    rdi
0x18004da04  push    r12
0x18004da06  push    r13
0x18004da08  push    r14
0x18004da0a  push    r15
0x18004da0c  lea     rbp, [rsp-100h]
0x18004da14  sub     rsp, 200h
0x18004da1b  mov     [rbp+130h+var_150], 0FFFFFFFFFFFFFFFEh
0x18004da23  mov     [rsp+230h+arg_10], rbx
0x18004da2b  mov     rax, cs:__security_cookie
0x18004da32  xor     rax, rsp
0x18004da35  mov     [rbp+130h+var_40], rax
0x18004da3c  mov     [rsp+230h+var_1D0], rdx
0x18004da41  mov     r13, rcx
0x18004da44  mov     [rsp+230h+var_1D8], rcx
0x18004da49  mov     rax, [rcx+30h]
0x18004da4d  cmp     rax, 10h
0x18004da51  jb      loc_18004E421
0x18004da57  mov     r8, [rcx+28h]
0x18004da5b  mov     [rbp+130h+var_158], r8
0x18004da5f  lea     rsi, [r8+rax]
0x18004da63  cmp     rsi, r8
0x18004da66  jb      loc_18004E458
0x18004da6c  lea     rax, [r8+4]
0x18004da70  cmp     rax, r8
0x18004da73  jb      loc_18004E458
0x18004da79  cmp     rax, rsi
0x18004da7c  ja      loc_18004E45E
0x18004da82  cmp     dword ptr [r8], 424A5342h
0x18004da89  jz      short loc_18004DA96
0x18004da8b  mov     dword ptr [rdx], 0Bh
0x18004da91  jmp     loc_18004E42C
0x18004da96  lea     rcx, [rax+8]
0x18004da9a  cmp     rcx, rax
0x18004da9d  jb      loc_18004E458
0x18004daa3  cmp     rcx, rsi
0x18004daa6  ja      loc_18004E481
0x18004daac  lea     rax, [rcx+4]
0x18004dab0  cmp     rax, rcx
0x18004dab3  jb      loc_18004E458
0x18004dab9  cmp     rax, rsi
0x18004dabc  ja      loc_18004E4A4
0x18004dac2  mov     edx, [rcx]
0x18004dac4  add     rdx, rcx
0x18004dac7  cmp     rdx, rcx
0x18004daca  jb      loc_18004E458
0x18004dad0  cmp     rdx, rsi
0x18004dad3  ja      loc_18004E4C7
0x18004dad9  lea     rax, [rdx+6]
0x18004dadd  cmp     rax, rdx
0x18004dae0  jb      loc_18004E458
0x18004dae6  cmp     rax, rsi
0x18004dae9  ja      loc_18004E4EA
0x18004daef  lea     rdx, [rax+2]
0x18004daf3  cmp     rdx, rax
0x18004daf6  jb      loc_18004E458
0x18004dafc  cmp     rdx, rsi
0x18004daff  ja      loc_18004E50D
0x18004db05  movzx   eax, word ptr [rax]
0x18004db08  mov     [rsp+230h+var_1E0], eax
0x18004db0c  xor     r9d, r9d
0x18004db0f  mov     [rsp+230h+var_1F0], r9d
0x18004db14  test    eax, eax
0x18004db16  jz      loc_18004E37D
0x18004db1c  mov     r12d, 7FFFFFFh
0x18004db22  lea     rcx, [rdx+4]
0x18004db26  cmp     rcx, rdx
0x18004db29  jb      loc_18004E458
0x18004db2f  cmp     rcx, rsi
0x18004db32  ja      loc_18004E7C9
0x18004db38  cmp     rdx, rsi
0x18004db3b  ja      loc_18004E7A6
0x18004db41  lea     r15, [rcx+4]
0x18004db45  cmp     r15, rcx
0x18004db48  jb      loc_18004E458
0x18004db4e  cmp     r15, rsi
0x18004db51  ja      loc_18004E783
0x18004db57  cmp     rcx, rsi
0x18004db5a  ja      loc_18004E760
0x18004db60  mov     edi, [rdx]
0x18004db62  add     rdi, r8
0x18004db65  cmp     rdi, r8
0x18004db68  jb      loc_18004E458
0x18004db6e  mov     ebx, [rcx]
0x18004db70  add     rbx, rdi
0x18004db73  cmp     rbx, rdi
0x18004db76  jb      loc_18004E458
0x18004db7c  cmp     rdi, rsi
0x18004db7f  ja      loc_18004E73D
0x18004db85  cmp     rbx, rsi
0x18004db88  ja      loc_18004E73D
0x18004db8e  mov     r8, rsi
0x18004db91  sub     r8, r15; MaxCount
0x18004db94  xor     edx, edx; Val
0x18004db96  mov     rcx, r15; Buf
0x18004db99  call    memchr_0
0x18004db9e  mov     r14, rsi
0x18004dba1  test    rax, rax
0x18004dba4  cmovnz  r14, rax
0x18004dba8  cmp     r14, rsi
0x18004dbab  jz      loc_18004E71A
0x18004dbb1  sub     r14, r15
0x18004dbb4  lea     rcx, [r14+4]
0x18004dbb8  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004dbbc  add     rcx, r15
0x18004dbbf  mov     [rbp+130h+var_160], rcx
0x18004dbc3  cmp     rcx, r15
0x18004dbc6  jb      loc_18004E458
0x18004dbcc  mov     qword ptr [rsp+230h+var_200], r15
0x18004dbd1  mov     qword ptr [rsp+230h+var_200+8], r14
0x18004dbd6  mov     eax, [r13+488h]
0x18004dbdd  mov     dword ptr [rsp+230h+var_1E8], eax
0x18004dbe1  lea     edx, [rax+1]
0x18004dbe4  mov     [rsp+230h+var_1EC], edx
0x18004dbe8  cmp     edx, r12d
0x18004dbeb  ja      loc_18004E36D
0x18004dbf1  mov     eax, [r13+48Ch]
0x18004dbf8  cmp     edx, eax
0x18004dbfa  jbe     loc_18004DD0F
0x18004dc00  lea     ecx, [rax+rax*2]
0x18004dc03  shr     rcx, 1
0x18004dc06  mov     r13d, edx
0x18004dc09  cmp     r13, rcx
0x18004dc0c  cmovbe  r13, rcx
0x18004dc10  cmp     r13, r12
0x18004dc13  cmova   r13, r12
0x18004dc17  mov     eax, 20h ; ' '
0x18004dc1c  mul     r13
0x18004dc1f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004dc26  cmovb   rax, rcx
0x18004dc2a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004dc31  mov     rcx, rax; unsigned __int64
0x18004dc34  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004dc39  mov     r12, rax
0x18004dc3c  mov     [rbp+130h+var_148], rax
0x18004dc40  test    rax, rax
0x18004dc43  jz      short loc_18004DC7B
0x18004dc45  mov     rdx, r13
0x18004dc48  mov     rcx, rax
0x18004dc4b  xor     eax, eax
0x18004dc4d  test    r13, r13
0x18004dc50  jz      short loc_18004DC7E
0x18004dc52  nop     dword ptr [rax+00h]
0x18004dc56  nop     word ptr [rax+rax+00000000h]
0x18004dc60  mov     [rcx], rax
0x18004dc63  mov     [rcx+8], rax
0x18004dc67  mov     [rcx+10h], rax
0x18004dc6b  mov     [rcx+18h], rax
0x18004dc6f  lea     rcx, [rcx+20h]
0x18004dc73  sub     rdx, 1
0x18004dc77  jnz     short loc_18004DC60
0x18004dc79  jmp     short loc_18004DC7E
0x18004dc7b  mov     r12, rax
0x18004dc7e  test    r12, r12
0x18004dc81  jz      loc_18004E36D
0x18004dc87  mov     r9, [rsp+230h+var_1D8]
0x18004dc8c  cmp     qword ptr [r9+480h], 0
0x18004dc94  jz      short loc_18004DCF8
0x18004dc96  mov     r8d, eax
0x18004dc99  cmp     dword ptr [r9+488h], 0
0x18004dca1  jbe     short loc_18004DCE7
0x18004dca3  nop     dword ptr [rax+00h]
0x18004dca7  nop     word ptr [rax+rax+00000000h]
0x18004dcb0  mov     ecx, r8d
0x18004dcb3  shl     rcx, 5
0x18004dcb7  mov     rdx, [r9+480h]
0x18004dcbe  mov     rax, [rdx+rcx]
0x18004dcc2  mov     [rcx+r12], rax
0x18004dcc6  mov     rax, [rdx+rcx+8]
0x18004dccb  mov     [rcx+r12+8], rax
0x18004dcd0  movups  xmm0, xmmword ptr [rdx+rcx+10h]
0x18004dcd5  movups  xmmword ptr [rcx+r12+10h], xmm0
0x18004dcdb  inc     r8d
0x18004dcde  cmp     r8d, [r9+488h]
0x18004dce5  jb      short loc_18004DCB0
0x18004dce7  mov     rcx, [r9+480h]; this
0x18004dcee  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18004dcf3  mov     r9, [rsp+230h+var_1D8]
0x18004dcf8  mov     [r9+480h], r12
0x18004dcff  mov     [r9+48Ch], r13d
0x18004dd06  mov     edx, [rsp+230h+var_1EC]
0x18004dd0a  mov     r13, [rsp+230h+var_1D8]
0x18004dd0f  mov     [r13+488h], edx
0x18004dd16  lea     r12, [r13+480h]
0x18004dd1d  mov     ecx, dword ptr [rsp+230h+var_1E8]
0x18004dd21  shl     rcx, 5
0x18004dd25  mov     rax, [r12]
0x18004dd29  mov     [rcx+rax], rdi
0x18004dd2d  mov     [rcx+rax+8], rbx
0x18004dd32  movups  xmm0, [rsp+230h+var_200]
0x18004dd37  movups  xmmword ptr [rcx+rax+10h], xmm0
0x18004dd3c  cmp     r14, 4
0x18004dd40  jnz     loc_18004E113
0x18004dd46  mov     r8, r14; Size
0x18004dd49  lea     rdx, aPdb_0; "#Pdb"
0x18004dd50  mov     rcx, r15; Buf1
0x18004dd53  call    memcmp_0
0x18004dd58  test    eax, eax
0x18004dd5a  jnz     loc_18004E113
0x18004dd60  cmp     rdi, rbx
0x18004dd63  ja      loc_18004E458
0x18004dd69  mov     rax, rbx
0x18004dd6c  sub     rax, rdi
0x18004dd6f  mov     [rsp+230h+var_1E8], rax
0x18004dd74  cmp     rax, 20h ; ' '
0x18004dd78  jb      loc_18004E421
0x18004dd7e  lea     r12, [rdi+18h]
0x18004dd82  cmp     r12, rdi
0x18004dd85  jb      loc_18004E458
0x18004dd8b  lea     rax, [r12+8]
0x18004dd90  cmp     rax, r12
0x18004dd93  jb      loc_18004E458
0x18004dd99  cmp     rax, rbx
0x18004dd9c  ja      loc_18004E5DF
0x18004dda2  cmp     r12, rbx
0x18004dda5  ja      loc_18004E5BC
0x18004ddab  mov     r12, [r12]
0x18004ddaf  mov     r14d, 20h ; ' '
0x18004ddb5  xor     r15d, r15d
0x18004ddb8  xor     edx, edx; Val
0x18004ddba  mov     r8d, 100h; Size
0x18004ddc0  lea     rcx, [rbp+130h+var_140]; void *
0x18004ddc4  call    memset_0
0x18004ddc9  xor     r9d, r9d
0x18004ddcc  mov     edx, r9d
0x18004ddcf  nop
0x18004ddd0  mov     rax, r12
0x18004ddd3  mov     ecx, edx
0x18004ddd5  shr     rax, cl
0x18004ddd8  test    al, 1
0x18004ddda  jz      short loc_18004DDEA
0x18004dddc  inc     r15d
0x18004dddf  mov     eax, edx
0x18004dde1  mov     [rbp+rax*4+130h+var_140], r14d
0x18004dde6  add     r14d, 4
0x18004ddea  lea     ecx, [rdx+1]
0x18004dded  mov     rax, r12
0x18004ddf0  shr     rax, cl
0x18004ddf3  test    al, 1
0x18004ddf5  jz      short loc_18004DE03
0x18004ddf7  inc     r15d
0x18004ddfa  mov     [rbp+rcx*4+130h+var_140], r14d
0x18004ddff  add     r14d, 4
0x18004de03  lea     ecx, [rdx+2]
0x18004de06  mov     rax, r12
0x18004de09  shr     rax, cl
0x18004de0c  test    al, 1
0x18004de0e  jz      short loc_18004DE1C
0x18004de10  inc     r15d
0x18004de13  mov     [rbp+rcx*4+130h+var_140], r14d
0x18004de18  add     r14d, 4
0x18004de1c  lea     ecx, [rdx+3]
0x18004de1f  mov     rax, r12
0x18004de22  shr     rax, cl
0x18004de25  test    al, 1
0x18004de27  jz      short loc_18004DE35
0x18004de29  inc     r15d
0x18004de2c  mov     [rbp+rcx*4+130h+var_140], r14d
0x18004de31  add     r14d, 4
0x18004de35  lea     ecx, [rdx+4]
0x18004de38  mov     rax, r12
0x18004de3b  shr     rax, cl
0x18004de3e  test    al, 1
0x18004de40  jz      short loc_18004DE4E
0x18004de42  inc     r15d
0x18004de45  mov     [rbp+rcx*4+130h+var_140], r14d
0x18004de4a  add     r14d, 4
0x18004de4e  lea     ecx, [rdx+5]
0x18004de51  mov     rax, r12
0x18004de54  shr     rax, cl
0x18004de57  test    al, 1
0x18004de59  jz      short loc_18004DE67
0x18004de5b  inc     r15d
0x18004de5e  mov     [rbp+rcx*4+130h+var_140], r14d
0x18004de63  add     r14d, 4
0x18004de67  lea     ecx, [rdx+6]
0x18004de6a  mov     rax, r12
0x18004de6d  shr     rax, cl
0x18004de70  test    al, 1
0x18004de72  jz      short loc_18004DE80
0x18004de74  inc     r15d
0x18004de77  mov     [rbp+rcx*4+130h+var_140], r14d
0x18004de7c  add     r14d, 4
0x18004de80  lea     ecx, [rdx+7]
0x18004de83  mov     rax, r12
0x18004de86  shr     rax, cl
0x18004de89  test    al, 1
0x18004de8b  jz      short loc_18004DE99
0x18004de8d  inc     r15d
0x18004de90  mov     [rbp+rcx*4+130h+var_140], r14d
0x18004de95  add     r14d, 4
0x18004de99  lea     ecx, [rdx+8]
0x18004de9c  mov     rax, r12
0x18004de9f  shr     rax, cl
0x18004dea2  test    al, 1
0x18004dea4  jz      short loc_18004DEB2
0x18004dea6  inc     r15d
0x18004dea9  mov     [rbp+rcx*4+130h+var_140], r14d
  ... truncated ...
```
