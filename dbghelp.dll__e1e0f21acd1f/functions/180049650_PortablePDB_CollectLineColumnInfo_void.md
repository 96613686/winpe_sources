# PortablePDB::CollectLineColumnInfo(void)

- ea: `0x180049650`
- end: `0x18004a720`
- name: `?CollectLineColumnInfo@PortablePDB@@AEAAJXZ`
- size: `4304`
- prototype: `__int64 __fastcall(PortablePDB *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bd90`

## callees

- `0x180026980`
- `0x180027440`
- `0x180029320`
- `0x180029550`
- `0x1800352f0`
- `0x180038bf0`
- `0x180038ce0`
- `0x1800492a0`
- `0x180049450`
- `0x180049540`
- `0x180049650`
- `0x18004c5c0`
- `0x18004c680`
- `0x18004d680`
- `0x18004d900`
- `0x18004e800`

## string_xrefs

- `0x18004a64e`: `Range error during SafeInt constructor`
- `0x18004a671`: `Range error during makeSubRange`
- `0x18004a694`: `Range error during default makeSubRange`
- `0x18004a5bc`: `Range error during currentVoidPtr`
- `0x18004a602`: `Range error during currentVoidPtr`
- `0x18004a6b7`: `Range error during currentVoidPtr`
- `0x18004a6fd`: `Range error during currentVoidPtr`
- `0x18004a593`: `Range error during read`
- `0x18004a5df`: `Range error during read`
- `0x18004a625`: `Range error during read`
- `0x18004a6da`: `Range error during read`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PortablePDB::CollectLineColumnInfo(PortablePDB *this)
{
  PortablePDB *v1; // r15
  char *v2; // rdi
  __int64 result; // rax
  char *v4; // rcx
  char *v5; // rax
  unsigned int *v6; // rcx
  unsigned __int16 *v7; // rax
  unsigned __int64 v8; // rdx
  unsigned int v9; // r14d
  unsigned __int64 v10; // rdx
  unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int64 *v16; // r8
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  char v20; // di
  char v21; // r14
  __int64 v22; // rdi
  __int64 v23; // rsi
  unsigned __int64 v24; // r8
  int v25; // r8d
  char v26; // cl
  char v27; // di
  int v28; // r12d
  int v29; // esi
  int v30; // r13d
  int v31; // edi
  char v32; // r14
  int v33; // edi
  int v34; // esi
  unsigned int v35; // r12d
  int v36; // edi
  char v37; // r14
  int v38; // edi
  int v39; // esi
  __m128i v40; // xmm6
  unsigned int v41; // edi
  unsigned int v42; // r15d
  unsigned __int64 v43; // xmm6_8
  unsigned int v44; // r14d
  unsigned int v45; // r14d
  PortablePDB *v46; // rsi
  int v47; // edi
  char v48; // r14
  int v49; // edi
  int v50; // esi
  unsigned int v51; // edi
  unsigned int v52; // esi
  int v53; // edi
  char v54; // r14
  int v55; // edi
  int v56; // esi
  __m128i v57; // xmm6
  unsigned int v58; // edx
  unsigned __int64 v59; // xmm6_8
  unsigned int v60; // r14d
  unsigned int v61; // r14d
  int v62; // edi
  char v63; // r14
  int v64; // edi
  int v65; // esi
  __m128i v66; // xmm6
  unsigned int v67; // edx
  unsigned __int64 v68; // xmm6_8
  unsigned __int16 v69; // r15
  unsigned __int64 v70; // rdx
  int v71; // edi
  char v72; // r14
  int v73; // edi
  int v74; // esi
  int v75; // eax
  int v76; // edi
  char v77; // r14
  int v78; // edi
  int v79; // esi
  int v80; // r13d
  int v81; // r15d
  int v82; // edi
  char v83; // r14
  int v84; // edi
  int v85; // esi
  unsigned int v86; // esi
  unsigned int v87; // edx
  unsigned int v88; // r9d
  int v89; // r8d
  __m128i v90; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v91; // [rsp+60h] [rbp-A0h]
  unsigned int v92; // [rsp+64h] [rbp-9Ch]
  unsigned int v93; // [rsp+68h] [rbp-98h]
  unsigned int v94; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v95; // [rsp+70h] [rbp-90h] BYREF
  int v96; // [rsp+74h] [rbp-8Ch]
  void **pExceptionObject; // [rsp+78h] [rbp-88h] BYREF
  PSGSI1::EnumPubsByAddr *v98; // [rsp+80h] [rbp-80h]
  __int64 v99; // [rsp+88h] [rbp-78h]
  int v100; // [rsp+90h] [rbp-70h]
  int v101; // [rsp+94h] [rbp-6Ch]
  unsigned __int64 v102; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v103; // [rsp+A0h] [rbp-60h]
  void **v104; // [rsp+A8h] [rbp-58h] BYREF
  PSGSI1::EnumPubsByAddr *v105; // [rsp+B0h] [rbp-50h]
  __int64 v106; // [rsp+B8h] [rbp-48h]
  unsigned int v107; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v108; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v109; // [rsp+C8h] [rbp-38h] BYREF
  int v110; // [rsp+CCh] [rbp-34h] BYREF
  __m128i v111; // [rsp+D0h] [rbp-30h]
  __int64 v112; // [rsp+E0h] [rbp-20h]
  unsigned int v114; // [rsp+158h] [rbp+58h] BYREF
  char v115; // [rsp+160h] [rbp+60h]
  unsigned int v116; // [rsp+168h] [rbp+68h] BYREF

  v112 = -2;
  v1 = this;
  v114 = 4;
  v2 = (char *)this + 864;
  if ( *((_DWORD *)this + 218) + *((_DWORD *)this + 222) - *((_DWORD *)this + 220) < 4
    && !(unsigned int)pdb_internal::Buffer::grow((PortablePDB *)((char *)this + 864), 4) )
  {
    return 2;
  }
  v4 = (char *)*((_QWORD *)v2 + 2);
  if ( *((_QWORD *)v2 + 1) )
  {
    v5 = v4 + 4;
  }
  else
  {
    *((_QWORD *)v2 + 1) = 0;
    v5 = 0;
  }
  *((_QWORD *)v2 + 2) = v5;
  memcpy_avx(v4, &v114, 4u);
  v100 = 0;
  if ( !*((_DWORD *)v1 + 165) )
    return 0;
  while ( 1 )
  {
    v6 = (unsigned int *)*((_QWORD *)v1 + 12);
    if ( (*((_DWORD *)v1 + 164) & 0xFFFF0000) != 0 )
    {
      v7 = (unsigned __int16 *)(v6 + 1);
      if ( v6 + 1 < v6 )
        goto LABEL_182;
      v10 = *((_QWORD *)v1 + 13);
      if ( (unsigned __int64)v7 > v10 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during read");
        throw (std::range_error *)&pExceptionObject;
      }
      if ( (unsigned __int64)v6 > v10 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during currentVoidPtr");
        throw (std::range_error *)&pExceptionObject;
      }
      *((_QWORD *)v1 + 12) = v7;
      v9 = *v6;
    }
    else
    {
      v7 = (unsigned __int16 *)v6 + 1;
      if ( (unsigned int *)((char *)v6 + 2) < v6 )
        goto LABEL_182;
      v8 = *((_QWORD *)v1 + 13);
      if ( (unsigned __int64)v7 > v8 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during read");
        throw (std::range_error *)&pExceptionObject;
      }
      if ( (unsigned __int64)v6 > v8 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during currentVoidPtr");
        throw (std::range_error *)&pExceptionObject;
      }
      *((_QWORD *)v1 + 12) = v7;
      v9 = *(unsigned __int16 *)v6;
    }
    v92 = v9;
    v114 = v9;
    if ( *((_DWORD *)v1 + 158) == 2 )
    {
      v11 = v7 + 1;
      if ( v7 + 1 < v7 )
        goto LABEL_182;
      v12 = *((_QWORD *)v1 + 13);
      if ( (unsigned __int64)v11 > v12 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during read");
        throw (std::range_error *)&pExceptionObject;
      }
      if ( (unsigned __int64)v7 > v12 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during currentVoidPtr");
        throw (std::range_error *)&pExceptionObject;
      }
      *((_QWORD *)v1 + 12) = v11;
      v13 = *v7;
    }
    else
    {
      v14 = v7 + 2;
      if ( v7 + 2 < v7 )
        goto LABEL_182;
      v15 = *((_QWORD *)v1 + 13);
      if ( (unsigned __int64)v14 > v15 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during read");
        throw (std::range_error *)&pExceptionObject;
      }
      if ( (unsigned __int64)v7 > v15 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during currentVoidPtr");
        throw (std::range_error *)&pExceptionObject;
      }
      *((_QWORD *)v1 + 12) = v14;
      v13 = *(unsigned int *)v7;
    }
    if ( !(_DWORD)v13 )
      goto LABEL_170;
    v16 = (unsigned __int64 *)*((_QWORD *)v1 + 11);
    v17 = *v16 + v13;
    if ( v17 < *v16 )
      goto LABEL_182;
    v18 = v16[1];
    if ( v17 > v18 )
    {
      std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during default makeSubRange");
      throw (std::range_error *)&pExceptionObject;
    }
    v102 = v17;
    v103 = v18;
    if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v102, 0) >= 0x80u )
    {
      if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v102, 0) & 0xC0) == 0x80 )
      {
        v20 = ReadOnlySafeSpanPtr::read<unsigned char>(&v102, 0);
        v19 = ((unsigned __int64)(v20 & 0x3F) << 8)
            | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v102, 0);
      }
      else
      {
        if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v102, 0) & 0xE0) != 0xC0 )
          return 13;
        v21 = ReadOnlySafeSpanPtr::read<unsigned char>(&v102, 0);
        v22 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v102, 0);
        v23 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v102, 0);
        v19 = ((v23 | ((v22 | ((unsigned __int64)(v21 & 0x1F) << 8)) << 8)) << 8)
            | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v102, 0);
        v9 = v92;
      }
    }
    else
    {
      v19 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v102, 0);
    }
    v24 = v102 + v19;
    if ( v102 + v19 < v102 )
LABEL_182:
      msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
    if ( v102 > v103 || v24 > v103 )
    {
      std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during makeSubRange");
      throw (std::range_error *)&pExceptionObject;
    }
    if ( v102 > v24 )
    {
      std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during SafeInt constructor");
      throw (std::range_error *)&pExceptionObject;
    }
    v90.m128i_i64[0] = v102;
    v90.m128i_i64[1] = v102 + v19;
    if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
    {
      if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) != 0x80 )
      {
        if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
          return 13;
        ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
        ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
      }
      ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
    }
    ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
    if ( !v9 )
    {
      result = PortablePDB::DecompressU32(v1, (struct ReadOnlySafeSpanPtr *)&v90, &v114);
      if ( (_DWORD)result )
        return result;
      v9 = v114;
      v92 = v114;
    }
    v26 = 1;
    v115 = 1;
    v27 = 0;
    LOBYTE(v114) = 0;
    v101 = -1;
    v28 = 0;
    v29 = 0;
    v96 = 0;
    v94 = 0;
    v91 = 0;
    v116 = 0;
    v95 = 0;
    v93 = 0;
    pExceptionObject = &pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable';
    v98 = 0;
    v99 = 0;
    v104 = &pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable';
    v105 = 0;
    v106 = 0;
    if ( v90.m128i_i64[0] != v90.m128i_i64[1] )
    {
      while ( 1 )
      {
        if ( v26 )
        {
          if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
          {
            if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
            {
              v31 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
              v30 = v31 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
            else
            {
              if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
                goto LABEL_174;
              v32 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              v33 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              v34 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) << 8;
              v30 = v34
                  | ((v33 | ((v32 & 0x1F) << 8)) << 16)
                  | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
          }
          else
          {
            v30 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
          }
          if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
          {
            if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
            {
              v36 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
              v35 = v36 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
            else
            {
              if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
                goto LABEL_174;
              v37 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              v38 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              v39 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) << 8;
              v35 = v39
                  | ((v38 | ((v37 & 0x1F) << 8)) << 16)
                  | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
          }
          else
          {
            v35 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
          }
          if ( v35 )
          {
            v40 = v90;
            v111 = v90;
            v41 = PortablePDB::DecompressU32(v1, (struct ReadOnlySafeSpanPtr *)&v90, &v107);
            if ( v41 )
              goto LABEL_175;
            v42 = v107 >> 1;
            if ( (v107 & 1) != 0 )
            {
              v43 = _mm_srli_si128(v40, 8).m128i_u64[0];
              if ( v111.m128i_i64[0] > v43 || v90.m128i_i64[0] > (unsigned __int64)v90.m128i_i64[1] )
LABEL_187:
                msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
              switch ( v90.m128i_i32[0] + (_DWORD)v43 - v111.m128i_i32[0] - v90.m128i_i32[2] )
              {
                case 1:
                  v42 |= 0xFFFFFFC0;
                  break;
                case 2:
                  v42 |= 0xFFFFE000;
                  break;
                case 4:
                  v42 |= 0xF0000000;
                  break;
                default:
                  goto LABEL_174;
              }
            }
            v116 = v42;
LABEL_73:
            v44 = v91;
            if ( v91 )
            {
              v57 = v90;
              v111 = v90;
              v46 = this;
              v41 = PortablePDB::DecompressU32(this, (struct ReadOnlySafeSpanPtr *)&v90, &v108);
              if ( v41 )
                goto LABEL_175;
              v58 = v108 >> 1;
              if ( (v108 & 1) != 0 )
              {
                v59 = _mm_srli_si128(v57, 8).m128i_u64[0];
                if ( v111.m128i_i64[0] > v59 || v90.m128i_i64[0] > (unsigned __int64)v90.m128i_i64[1] )
                  goto LABEL_187;
                switch ( v90.m128i_i32[0] + (_DWORD)v59 - v111.m128i_i32[0] - v90.m128i_i32[2] )
                {
                  case 1:
                    v58 |= 0xFFFFFFC0;
                    break;
                  case 2:
                    v58 |= 0xFFFFE000;
                    break;
                  case 4:
                    v58 |= 0xF0000000;
                    break;
                  default:
                    goto LABEL_174;
                }
              }
              v45 = v58 + v44;
            }
            else if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
            {
              if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
              {
                v53 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
                v45 = v53 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v46 = this;
              }
              else
              {
                if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
                  goto LABEL_174;
                v54 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v55 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v56 = (((v55 | ((v54 & 0x1F) << 8)) << 8)
                     | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0)) << 8;
                v45 = v56 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v46 = this;
              }
            }
            else
            {
              v45 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              v46 = this;
            }
            v94 = v45;
            v91 = v45;
            v60 = v93;
            if ( v93 )
            {
              v66 = v90;
              v111 = v90;
              v41 = PortablePDB::DecompressU32(v46, (struct ReadOnlySafeSpanPtr *)&v90, &v109);
              if ( v41 )
                goto LABEL_175;
              v67 = v109 >> 1;
              if ( (v109 & 1) != 0 )
              {
                v68 = _mm_srli_si128(v66, 8).m128i_u64[0];
                if ( v111.m128i_i64[0] > v68 || v90.m128i_i64[0] > (unsigned __int64)v90.m128i_i64[1] )
                  goto LABEL_187;
                switch ( v90.m128i_i32[0] + (_DWORD)v68 - v111.m128i_i32[0] - v90.m128i_i32[2] )
                {
                  case 1:
                    v67 |= 0xFFFFFFC0;
                    break;
                  case 2:
                    v67 |= 0xFFFFE000;
                    break;
                  case 4:
                    v67 |= 0xF0000000;
                    break;
                  default:
                    goto LABEL_174;
                }
              }
              v61 = v67 + v60;
            }
            else if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
            {
              if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
              {
                v62 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
                v61 = v62 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              }
              else
              {
                if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
                  goto LABEL_174;
                v63 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v64 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v65 = (((v64 | ((v63 & 0x1F) << 8)) << 8)
                     | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0)) << 8;
                v61 = v65 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              }
            }
            else
            {
              v61 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
            v95 = v61;
            v93 = v61;
            if ( v91 >= 0x1000000 || (v61 & 0xFFFF0000) != 0 )
            {
LABEL_174:
              v41 = 13;
              goto LABEL_175;
            }
            v51 = v61;
            v52 = v91;
          }
          else
          {
            if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
            {
              if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
              {
                v47 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
                v42 = v47 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              }
              else
              {
                if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
                  goto LABEL_174;
                v48 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v49 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
                v50 = (((v49 | ((v48 & 0x1F) << 8)) << 8)
                     | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0)) << 8;
                v42 = v50 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              }
            }
            else
            {
              v42 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
            v116 = v42;
            if ( v42 )
              goto LABEL_73;
            v94 = 16707566;
            v35 = 0;
            v95 = 0;
            v42 = 0;
            v116 = 0;
            v51 = 0;
            v52 = 16707566;
          }
          if ( ((v51 + v42) & 0xFFFF0000) != 0 )
            goto LABEL_174;
          if ( v35 > 0x7F )
            LOBYTE(v35) = 127;
          v69 = v51 + v42;
          if ( !(unsigned int)pdb_internal::Array<pdb_internal::Array<unsigned __int64> *>::setSize(
                                &pExceptionObject,
                                (unsigned int)(v99 + 1))
            || (v70 = (v52 & 0xFFFFFF | (unsigned __int64)((v35 | 0xFFFFFF80) << 24)) << 32,
                v29 = v96,
                *((_QWORD *)v98 + (unsigned int)(v99 - 1)) = (unsigned int)(v30 - v96) | v70,
                !(unsigned int)pdb_internal::Array<CV_Column_t>::setSize(&v104, (unsigned int)(v106 + 1))) )
          {
            v41 = 2;
            goto LABEL_175;
          }
          *((_DWORD *)v105 + (unsigned int)(v106 - 1)) = (unsigned __int16)v51 | (v69 << 16);
          v28 = v30;
          v26 = 0;
          v115 = 0;
          v1 = this;
          goto LABEL_158;
        }
        if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
        {
          if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
          {
            v71 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
            v30 = v71 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
          }
          else
          {
            if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
              goto LABEL_174;
            v72 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            v73 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            v74 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) << 8;
            v30 = v74
                | ((v73 | ((v72 & 0x1F) << 8)) << 16)
                | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            v29 = v96;
          }
          v27 = v114;
        }
        else
        {
          v30 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
        }
        if ( !v30 )
        {
          if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
          {
            if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
            {
              v76 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
              v75 = v76 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
            else
            {
              if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
                goto LABEL_174;
              v77 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              v78 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
              v79 = (((v78 | ((v77 & 0x1F) << 8)) << 8)
                   | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0)) << 8;
              v75 = v79 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            }
          }
          else
          {
            v75 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
          }
          v101 = v92;
          v9 = v75;
          v92 = v75;
          v27 = 1;
          LOBYTE(v114) = 1;
          v26 = v115;
          v29 = v96;
          goto LABEL_159;
        }
        v28 += v30;
        if ( v27 )
        {
          v41 = PortablePDB::WriteLineBlock(
                  (_DWORD)v1,
                  v100 + 1,
                  0,
                  v92,
                  v101,
                  v28,
                  v29,
                  (__int64)&pExceptionObject,
                  (__int64)&v104);
          if ( v41 )
            goto LABEL_175;
          v80 = v28;
          v96 = v28;
          LOBYTE(v114) = 0;
        }
        else
        {
          v80 = v96;
        }
        if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) >= 0x80u )
        {
          if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xC0) == 0x80 )
          {
            v82 = (ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) & 0x3F) << 8;
            v81 = v82 | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
          }
          else
          {
            if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v90, 0) & 0xE0) != 0xC0 )
              goto LABEL_174;
            v83 = ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            v84 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
            v85 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0) << 8;
            v81 = v85
                | ((v84 | ((v83 & 0x1F) << 8)) << 16)
                | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
          }
        }
        else
        {
          v81 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v90, 0);
        }
        if ( v81 )
          break;
        v41 = PortablePDB::DecompressU32(this, (struct ReadOnlySafeSpanPtr *)&v90, &v116);
        if ( v41 )
          goto LABEL_175;
        v86 = v116;
        if ( v116 )
          goto LABEL_154;
        v87 = 16707566;
        v94 = 16707566;
        v81 = 0;
        v88 = 0;
        v95 = 0;
        v86 = 0;
        v116 = 0;
LABEL_156:
        v89 = v81;
        v1 = this;
        v41 = PortablePDB::SaveLineColumnInfo(
                (_DWORD)this,
                v87,
                v89,
                v88,
                v86,
                v28,
                v80,
                (__int64)&pExceptionObject,
                (__int64)&v104);
        if ( v41 )
          goto LABEL_175;
        v30 = v28;
        v26 = v115;
        v29 = v96;
LABEL_158:
        v9 = v92;
        v27 = v114;
LABEL_159:
        if ( v90.m128i_i64[0] == v90.m128i_i64[1] )
          goto LABEL_165;
      }
      v41 = PortablePDB::DecompressS32(this, (struct ReadOnlySafeSpanPtr *)&v90, &v110);
      if ( v41 )
        break;
      v86 = v110;
      v116 = v110;
LABEL_154:
      v41 = PortablePDB::ReadLineColumnStart(this, (struct ReadOnlySafeSpanPtr *)&v90, v91, v93, &v94, &v95);
      if ( v41 )
        break;
      v87 = v94;
      v91 = v94;
      v88 = v95;
      v93 = v95;
      goto LABEL_156;
    }
    v30 = 0;
LABEL_165:
    LOBYTE(v25) = 1;
    v41 = PortablePDB::WriteLineBlock(
            (_DWORD)v1,
            v100 + 1,
            v25,
            v9,
            v101,
            v30,
            v29,
            (__int64)&pExceptionObject,
            (__int64)&v104);
    if ( v41 )
      break;
    if ( v105 )
      PSGSI1::EnumPubsByAddr::release(v105);
    if ( v98 )
      PSGSI1::EnumPubsByAddr::release(v98);
LABEL_170:
    if ( (unsigned int)++v100 >= *((_DWORD *)v1 + 165) )
      return 0;
  }
LABEL_175:
  if ( v105 )
    PSGSI1::EnumPubsByAddr::release(v105);
  if ( v98 )
    PSGSI1::EnumPubsByAddr::release(v98);
  return v41;
}

```

## disassembly

```asm
0x180049650  mov     [rsp-8+arg_0], rcx
0x180049655  push    rbp
0x180049656  push    rbx
0x180049657  push    rsi
0x180049658  push    rdi
0x180049659  push    r12
0x18004965b  push    r13
0x18004965d  push    r14
0x18004965f  push    r15
0x180049661  lea     rbp, [rsp-8]
0x180049666  sub     rsp, 108h
0x18004966d  mov     [rbp+40h+var_60], 0FFFFFFFFFFFFFFFEh
0x180049675  movaps  [rsp+140h+var_50], xmm6
0x18004967d  mov     r15, rcx
0x180049680  mov     [rbp+40h+arg_8], 4
0x180049687  lea     rdi, [rcx+360h]
0x18004968e  mov     eax, [rdi+18h]
0x180049691  sub     eax, [rdi+10h]
0x180049694  add     eax, [rdi+8]
0x180049697  cmp     eax, 4
0x18004969a  jge     short loc_1800496B7
0x18004969c  mov     edx, 4; int
0x1800496a1  mov     rcx, rdi; this
0x1800496a4  call    ?grow@Buffer@pdb_internal@@AEAAHJ@Z; pdb_internal::Buffer::grow(long)
0x1800496a9  test    eax, eax
0x1800496ab  jnz     short loc_1800496B7
0x1800496ad  mov     eax, 2
0x1800496b2  jmp     loc_18004A543
0x1800496b7  mov     rcx, [rdi+10h]; void *
0x1800496bb  xor     ebx, ebx
0x1800496bd  cmp     [rdi+8], rbx
0x1800496c1  jnz     short loc_1800496CB
0x1800496c3  mov     [rdi+8], rbx
0x1800496c7  mov     eax, ebx
0x1800496c9  jmp     short loc_1800496CF
0x1800496cb  lea     rax, [rcx+4]
0x1800496cf  mov     [rdi+10h], rax
0x1800496d3  mov     r8d, 4; unsigned __int64
0x1800496d9  lea     rdx, [rbp+40h+arg_8]; void *
0x1800496dd  call    ?memcpy_avx@@YAPEBXPEBX0_K@Z; memcpy_avx(void const *,void const *,unsigned __int64)
0x1800496e2  mov     [rbp+40h+var_B0], ebx
0x1800496e5  cmp     [r15+294h], ebx
0x1800496ec  jbe     loc_18004A541
0x1800496f2  lea     r13, ??_7?$Array@VReadOnlySafeSpanPtr@@@pdb_internal@@6B@; const pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable'
0x1800496f9  nop     dword ptr [rax+00000000h]
0x180049700  mov     rcx, [r15+60h]
0x180049704  test    dword ptr [r15+290h], 0FFFF0000h
0x18004970f  jnz     short loc_18004973E
0x180049711  lea     rax, [rcx+2]
0x180049715  cmp     rax, rcx
0x180049718  jb      loc_18004A5B6
0x18004971e  mov     rdx, [r15+68h]
0x180049722  cmp     rax, rdx
0x180049725  ja      loc_18004A5DF
0x18004972b  cmp     rcx, rdx
0x18004972e  ja      loc_18004A5BC
0x180049734  mov     [r15+60h], rax
0x180049738  movzx   r14d, word ptr [rcx]
0x18004973c  jmp     short loc_180049768
0x18004973e  lea     rax, [rcx+4]
0x180049742  cmp     rax, rcx
0x180049745  jb      loc_18004A5B6
0x18004974b  mov     rdx, [r15+68h]
0x18004974f  cmp     rax, rdx
0x180049752  ja      loc_18004A593
0x180049758  cmp     rcx, rdx
0x18004975b  ja      loc_18004A6FD
0x180049761  mov     [r15+60h], rax
0x180049765  mov     r14d, [rcx]
0x180049768  mov     [rsp+140h+var_DC], r14d
0x18004976d  mov     [rbp+40h+arg_8], r14d
0x180049771  cmp     dword ptr [r15+278h], 2
0x180049779  jnz     short loc_1800497A7
0x18004977b  lea     rcx, [rax+2]
0x18004977f  cmp     rcx, rax
0x180049782  jb      loc_18004A5B6
0x180049788  mov     rdx, [r15+68h]
0x18004978c  cmp     rcx, rdx
0x18004978f  ja      loc_18004A625
0x180049795  cmp     rax, rdx
0x180049798  ja      loc_18004A602
0x18004979e  mov     [r15+60h], rcx
0x1800497a2  movzx   edx, word ptr [rax]
0x1800497a5  jmp     short loc_1800497D0
0x1800497a7  lea     rcx, [rax+4]
0x1800497ab  cmp     rcx, rax
0x1800497ae  jb      loc_18004A5B6
0x1800497b4  mov     rdx, [r15+68h]
0x1800497b8  cmp     rcx, rdx
0x1800497bb  ja      loc_18004A6DA
0x1800497c1  cmp     rax, rdx
0x1800497c4  ja      loc_18004A6B7
0x1800497ca  mov     [r15+60h], rcx
0x1800497ce  mov     edx, [rax]
0x1800497d0  test    edx, edx
0x1800497d2  jz      loc_18004A52C
0x1800497d8  mov     r8, [r15+58h]
0x1800497dc  add     rdx, [r8]
0x1800497df  cmp     rdx, [r8]
0x1800497e2  jb      loc_18004A5B6
0x1800497e8  mov     rax, [r8+8]
0x1800497ec  cmp     rdx, rax
0x1800497ef  ja      loc_18004A694
0x1800497f5  mov     [rbp+40h+var_A8], rdx
0x1800497f9  mov     [rbp+40h+var_A0], rax
0x1800497fd  mov     rdx, rbx
0x180049800  lea     rcx, [rbp+40h+var_A8]
0x180049804  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049809  mov     rdx, rbx
0x18004980c  lea     rcx, [rbp+40h+var_A8]
0x180049810  cmp     al, 80h
0x180049812  jnb     short loc_180049821
0x180049814  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049819  movzx   edx, al
0x18004981c  jmp     loc_1800498C0
0x180049821  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049826  and     al, 0C0h
0x180049828  mov     rdx, rbx
0x18004982b  lea     rcx, [rbp+40h+var_A8]
0x18004982f  cmp     al, 80h
0x180049831  jnz     short loc_180049856
0x180049833  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049838  movzx   edi, al
0x18004983b  mov     rdx, rbx
0x18004983e  lea     rcx, [rbp+40h+var_A8]
0x180049842  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049847  movzx   edx, al
0x18004984a  and     edi, 3Fh
0x18004984d  shl     rdi, 8
0x180049851  or      rdx, rdi
0x180049854  jmp     short loc_1800498C0
0x180049856  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004985b  and     al, 0E0h
0x18004985d  cmp     al, 0C0h
0x18004985f  jnz     loc_18004A58C
0x180049865  mov     rdx, rbx
0x180049868  lea     rcx, [rbp+40h+var_A8]
0x18004986c  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049871  movzx   r14d, al
0x180049875  mov     rdx, rbx
0x180049878  lea     rcx, [rbp+40h+var_A8]
0x18004987c  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049881  movzx   edi, al
0x180049884  mov     rdx, rbx
0x180049887  lea     rcx, [rbp+40h+var_A8]
0x18004988b  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049890  movzx   esi, al
0x180049893  mov     rdx, rbx
0x180049896  lea     rcx, [rbp+40h+var_A8]
0x18004989a  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004989f  movzx   edx, al
0x1800498a2  and     r14d, 1Fh
0x1800498a6  shl     r14, 8
0x1800498aa  or      r14, rdi
0x1800498ad  shl     r14, 8
0x1800498b1  or      r14, rsi
0x1800498b4  shl     r14, 8
0x1800498b8  or      rdx, r14
0x1800498bb  mov     r14d, [rsp+140h+var_DC]
0x1800498c0  mov     rcx, [rbp+40h+var_A8]
0x1800498c4  lea     r8, [rcx+rdx]
0x1800498c8  cmp     r8, rcx
0x1800498cb  jb      loc_18004A5B6
0x1800498d1  mov     rax, [rbp+40h+var_A0]
0x1800498d5  cmp     rcx, rax
0x1800498d8  ja      loc_18004A671
0x1800498de  cmp     r8, rax
0x1800498e1  ja      loc_18004A671
0x1800498e7  cmp     rcx, r8
0x1800498ea  ja      loc_18004A64E
0x1800498f0  mov     qword ptr [rsp+140h+var_F0], rcx
0x1800498f5  mov     qword ptr [rsp+140h+var_F0+8], r8
0x1800498fa  mov     rdx, rbx
0x1800498fd  lea     rcx, [rsp+140h+var_F0]
0x180049902  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049907  mov     rdx, rbx
0x18004990a  lea     rcx, [rsp+140h+var_F0]
0x18004990f  cmp     al, 80h
0x180049911  jb      short loc_180049964
0x180049913  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049918  and     al, 0C0h
0x18004991a  mov     rdx, rbx
0x18004991d  lea     rcx, [rsp+140h+var_F0]
0x180049922  cmp     al, 80h
0x180049924  jz      short loc_180049957
0x180049926  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004992b  and     al, 0E0h
0x18004992d  cmp     al, 0C0h
0x18004992f  jnz     loc_18004A58C
0x180049935  mov     rdx, rbx
0x180049938  lea     rcx, [rsp+140h+var_F0]
0x18004993d  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049942  mov     rdx, rbx
0x180049945  lea     rcx, [rsp+140h+var_F0]
0x18004994a  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004994f  mov     rdx, rbx
0x180049952  lea     rcx, [rsp+140h+var_F0]
0x180049957  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004995c  lea     rcx, [rsp+140h+var_F0]
0x180049961  mov     rdx, rbx
0x180049964  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049969  test    r14d, r14d
0x18004996c  jnz     short loc_180049990
0x18004996e  lea     r8, [rbp+40h+arg_8]; unsigned int *
0x180049972  lea     rdx, [rsp+140h+var_F0]; struct ReadOnlySafeSpanPtr *
0x180049977  mov     rcx, r15; this
0x18004997a  call    ?DecompressU32@PortablePDB@@AEAAJPEAVReadOnlySafeSpanPtr@@AEAK@Z; PortablePDB::DecompressU32(ReadOnlySafeSpanPtr *,ulong &)
0x18004997f  test    eax, eax
0x180049981  jnz     loc_18004A543
0x180049987  mov     r14d, [rbp+40h+arg_8]
0x18004998b  mov     [rsp+140h+var_DC], r14d
0x180049990  mov     cl, 1
0x180049992  mov     [rbp+40h+arg_10], cl
0x180049995  xor     dil, dil
0x180049998  mov     byte ptr [rbp+40h+arg_8], dil
0x18004999c  mov     [rbp+40h+var_AC], 0FFFFFFFFh
0x1800499a3  mov     r12d, ebx
0x1800499a6  mov     esi, ebx
0x1800499a8  mov     [rsp+140h+var_CC], ebx
0x1800499ac  mov     [rsp+140h+var_D4], ebx
0x1800499b0  mov     [rsp+140h+var_E0], ebx
0x1800499b4  mov     [rbp+40h+arg_18], ebx
0x1800499b7  mov     [rsp+140h+var_D0], ebx
0x1800499bb  mov     [rsp+140h+var_D8], ebx
0x1800499bf  mov     [rsp+140h+pExceptionObject], r13
0x1800499c4  mov     [rbp+40h+var_C0], rbx
0x1800499c8  mov     [rbp+40h+var_B8], rbx
0x1800499cc  lea     rax, ??_7?$Array@VReadOnlySafeSpanPtr@@@pdb_internal@@6B@; const pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable'
0x1800499d3  mov     [rbp+40h+var_98], rax
0x1800499d7  mov     [rbp+40h+var_90], rbx
0x1800499db  mov     [rbp+40h+var_88], rbx
0x1800499df  mov     rax, qword ptr [rsp+140h+var_F0+8]
0x1800499e4  cmp     qword ptr [rsp+140h+var_F0], rax
0x1800499e9  jz      loc_18004A4C9
0x1800499ef  nop
0x1800499f0  mov     rdx, rbx
0x1800499f3  test    cl, cl
0x1800499f5  lea     rcx, [rsp+140h+var_F0]
0x1800499fa  jz      loc_18004A0D9
0x180049a00  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a05  mov     rdx, rbx
0x180049a08  lea     rcx, [rsp+140h+var_F0]
0x180049a0d  cmp     al, 80h
0x180049a0f  jnb     short loc_180049A1F
0x180049a11  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a16  movzx   r13d, al
0x180049a1a  jmp     loc_180049ABF
0x180049a1f  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a24  and     al, 0C0h
0x180049a26  mov     rdx, rbx
0x180049a29  lea     rcx, [rsp+140h+var_F0]
0x180049a2e  cmp     al, 80h
0x180049a30  jnz     short loc_180049A56
0x180049a32  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a37  movzx   edi, al
0x180049a3a  and     edi, 3Fh
0x180049a3d  shl     edi, 8
0x180049a40  mov     rdx, rbx
0x180049a43  lea     rcx, [rsp+140h+var_F0]
0x180049a48  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a4d  movzx   r13d, al
0x180049a51  or      r13d, edi
0x180049a54  jmp     short loc_180049ABF
0x180049a56  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a5b  and     al, 0E0h
0x180049a5d  cmp     al, 0C0h
0x180049a5f  jnz     loc_18004A566
0x180049a65  mov     rdx, rbx
0x180049a68  lea     rcx, [rsp+140h+var_F0]
0x180049a6d  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a72  movzx   r14d, al
0x180049a76  mov     rdx, rbx
0x180049a79  lea     rcx, [rsp+140h+var_F0]
0x180049a7e  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a83  movzx   edi, al
0x180049a86  mov     rdx, rbx
0x180049a89  lea     rcx, [rsp+140h+var_F0]
0x180049a8e  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049a93  movzx   esi, al
0x180049a96  shl     esi, 8
0x180049a99  mov     rdx, rbx
0x180049a9c  lea     rcx, [rsp+140h+var_F0]
0x180049aa1  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049aa6  movzx   r13d, al
0x180049aaa  and     r14d, 1Fh
0x180049aae  shl     r14d, 8
0x180049ab2  or      r14d, edi
0x180049ab5  shl     r14d, 10h
0x180049ab9  or      r13d, r14d
0x180049abc  or      r13d, esi
0x180049abf  mov     rdx, rbx
0x180049ac2  lea     rcx, [rsp+140h+var_F0]
0x180049ac7  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049acc  mov     rdx, rbx
0x180049acf  lea     rcx, [rsp+140h+var_F0]
0x180049ad4  cmp     al, 80h
0x180049ad6  jnb     short loc_180049AE6
0x180049ad8  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x180049add  movzx   r12d, al
0x180049ae1  jmp     loc_180049B86
  ... truncated ...
```
