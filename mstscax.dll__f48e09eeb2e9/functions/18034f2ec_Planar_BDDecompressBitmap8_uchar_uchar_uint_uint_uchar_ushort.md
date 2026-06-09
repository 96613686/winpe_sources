# Planar::BDDecompressBitmap8(uchar *,uchar *,uint,uint,uchar,ushort)

- ea: `0x18034f2ec`
- end: `0x180350349`
- name: `?BDDecompressBitmap8@Planar@@YAJPEAE0IIEG@Z`
- size: `4189`
- prototype: `__int64 __fastcall(Planar *this, unsigned __int8 *, unsigned __int8 *, const unsigned __int16 *, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180350350`

## callees

- `0x180003920`
- `0x180006380`
- `0x1800064b0`
- `0x18003f834`
- `0x1800415dc`
- `0x180045338`
- `0x180051830`
- `0x1800829d4`
- `0x18034f2ec`
- `0x180373b78`
- `0x180373bd4`
- `0x180688f3e`

## string_xrefs

- `0x18034f366`: `Decompress reads one byte end of buffer`
- `0x18034f705`: `Decompress reads one byte end of buffer`
- `0x18034f72a`: `Decompress reads one byte end of buffer`
- `0x18034f78b`: `Decompress reads one byte end of buffer`
- `0x18034f810`: `Decompress reads one byte end of buffer`
- `0x18034f835`: `Decompress reads one byte end of buffer`
- `0x18034f92e`: `Decompress reads one byte end of buffer`
- `0x18034f953`: `Decompress reads one byte end of buffer`
- `0x18034fa2e`: `Decompress reads one byte end of buffer`
- `0x18034fa5b`: `Decompress reads one byte end of buffer`
- `0x18034fa98`: `Decompress reads one byte end of buffer`
- `0x18034fb97`: `Decompress reads one byte end of buffer`
- `0x18034fc27`: `Decompress reads one byte end of buffer`
- `0x18034fc50`: `Decompress reads one byte end of buffer`
- `0x18034fc8d`: `Decompress reads one byte end of buffer`
- `0x18034fd04`: `Decompress reads one byte end of buffer`
- `0x18034fd6d`: `Decompress reads one byte end of buffer`
- `0x18034fe68`: `Decompress reads one byte end of buffer`
- `0x18034ff79`: `Decompress reads one byte end of buffer`
- `0x18034ff9e`: `Decompress reads one byte end of buffer`
- `0x18034f569`: `Decompress write off end of buffer`
- `0x18034f5ca`: `Decompress write off end of buffer`
- `0x18034f624`: `Decompress write off end of buffer`
- `0x18034f681`: `Decompress write off end of buffer`
- `0x18034f7a9`: `Decompress write off end of buffer`
- `0x18034f8b6`: `Decompress write off end of buffer`
- `0x18034f9df`: `Decompress write off end of buffer`
- `0x18034fb3c`: `Decompress write off end of buffer`
- `0x18034fd98`: `Decompress write off end of buffer`
- `0x18034fdfa`: `Decompress write off end of buffer`
- `0x18034fe98`: `Decompress write off end of buffer`
- `0x18034fefa`: `Decompress write off end of buffer`
- `0x180350092`: `Decompress write off end of buffer`
- `0x1803500f6`: `Decompress write off end of buffer`
- `0x18034f6da`: `Decompress reads off end of buffer`
- `0x18034f7e5`: `Decompress reads off end of buffer`
- `0x18034f896`: `Decompress reads off end of buffer`
- `0x18034f903`: `Decompress reads off end of buffer`
- `0x18034f9b4`: `Decompress reads off end of buffer`
- `0x18034faba`: `Decompress reads off end of buffer`
- `0x18034fcad`: `Decompress reads off end of buffer`
- `0x18034ff4e`: `Decompress reads off end of buffer`
- `0x180350063`: `Decompress reads off end of buffer`
- `0x18034f516`: `Decompress writes one byte off end of buffer`
- `0x18034f53b`: `Decompress writes one byte off end of buffer`
- `0x18035000f`: `Decompress writes one byte off end of buffer`
- `0x1803500d4`: `Decompress writes one byte off end of buffer`
- `0x18034f4b2`: `onecore\termsrv\rdpplatform\codecs\planar\planardecompression.cpp`
- `0x18034f4c4`: `Invalid compression data %x`
- `0x180350303`: `Decompressed to %Id`
- `0x18034f49c`: `BDDecompressBitmap8`

## pseudocode

```c
__int64 __fastcall Planar::BDDecompressBitmap8(
        Planar *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 a6)
{
  unsigned __int8 *v6; // rsi
  unsigned __int8 *j; // rbx
  char v8; // r15
  unsigned __int8 *v9; // r13
  unsigned __int8 *v10; // r12
  int v11; // r14d
  unsigned __int8 *v12; // rdi
  int v13; // ecx
  int v14; // r14d
  char v15; // al
  char v16; // r15
  int v17; // r14d
  char v18; // si
  unsigned __int8 v19; // r13
  __int64 v20; // r15
  int v21; // r14d
  char v22; // si
  char v23; // r13
  int v24; // r14d
  char v25; // si
  unsigned __int8 v26; // r13
  __int64 v27; // r15
  int v28; // r14d
  char v29; // si
  char v30; // r13
  int v31; // r8d
  int v32; // r9d
  unsigned __int64 v33; // rsi
  unsigned __int8 *v34; // rbx
  unsigned __int8 v35; // si
  int v36; // r14d
  int v37; // r8d
  int v38; // r9d
  unsigned int v39; // esi
  unsigned __int8 *v40; // rbx
  unsigned __int8 v41; // si
  unsigned __int8 *v42; // rdx
  int v43; // r8d
  int v44; // r9d
  int v45; // esi
  unsigned __int8 *v46; // rbx
  unsigned __int8 v47; // si
  unsigned __int8 v48; // r14
  unsigned __int8 v49; // r15
  int v50; // r8d
  int v51; // r9d
  char v52; // si
  unsigned int v53; // esi
  char v54; // si
  unsigned __int8 v55; // r15
  int v56; // eax
  unsigned __int8 *v57; // r14
  int v58; // r8d
  int v59; // r9d
  char v60; // si
  int v61; // esi
  unsigned int v62; // esi
  char v63; // si
  unsigned int v64; // ebx
  const char *v65; // rax
  __int16 *v66; // rdx
  char v67; // al
  const unsigned __int16 *v68; // r9
  int v69; // r15d
  int v70; // r12d
  int v71; // r14d
  unsigned __int8 v72; // r13
  __int64 v73; // r13
  int v74; // r12d
  int v75; // r14d
  char v76; // si
  const unsigned __int16 *v77; // r9
  int v78; // r15d
  int v79; // r14d
  unsigned __int64 v80; // r8
  unsigned __int8 v81; // r13
  __int64 v82; // r12
  int v83; // r14d
  unsigned __int64 v84; // r8
  char v85; // r13
  int v86; // r8d
  int v87; // r9d
  unsigned __int64 v88; // rsi
  char v89; // si
  const unsigned __int16 *v90; // r9
  __int64 v91; // r15
  unsigned __int8 *v92; // r14
  unsigned __int8 *v93; // r14
  unsigned __int8 *v94; // r15
  unsigned int i; // edx
  int v97; // [rsp+50h] [rbp-39h] BYREF
  const char *v98; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int8 *v99; // [rsp+60h] [rbp-29h]
  unsigned __int8 *v100; // [rsp+68h] [rbp-21h]
  const char *v101; // [rsp+70h] [rbp-19h] BYREF
  const char *v102; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v103[10]; // [rsp+80h] [rbp-9h] BYREF
  const char *v104; // [rsp+E0h] [rbp+57h] BYREF
  unsigned __int8 *v105; // [rsp+E8h] [rbp+5Fh] BYREF
  unsigned int v106; // [rsp+F0h] [rbp+67h] BYREF
  int v107; // [rsp+F8h] [rbp+6Fh]

  v105 = a2;
  v6 = a2;
  j = (unsigned __int8 *)this;
  v8 = -1;
  v9 = (unsigned __int8 *)this + (unsigned int)a3;
  v10 = &a2[(unsigned int)a4];
  v99 = v9;
  v100 = v10;
  v11 = 1;
  LOBYTE(a5) = -1;
  v12 = a2;
  LODWORD(v104) = 0;
  v107 = 1;
  if ( this < (Planar *)v9 )
  {
    while ( 1 )
    {
      if ( v11 && (int)v12 - (int)v6 >= (unsigned int)a6 )
      {
        v107 = 0;
        LODWORD(v104) = 0;
      }
      if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
        return (unsigned int)-1626586886;
      v14 = *j;
      v15 = *j & 0xE0;
      if ( !v15 )
      {
        if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
          return (unsigned int)-1626586873;
        v89 = *j++;
        v88 = v89 & 0x1F;
        if ( !(_DWORD)v88 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586873;
          v88 = (unsigned int)*j++ + 32;
        }
        goto LABEL_201;
      }
      if ( (_BYTE)v14 == 0xF0 )
      {
        if ( !(unsigned int)CheckReadNBytes(j + 1, v9, 2u, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586869;
        v88 = *(unsigned __int16 *)(j + 1);
        j += 3;
LABEL_201:
        if ( (unsigned int)dword_1808B5850 > 5 )
        {
          v106 = v88;
          v103[0] = "Background run %u";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)byte_18086C08B,
            v86,
            v87,
            (__int64)v103,
            (__int64)&v106);
        }
        if ( v107 )
        {
          if ( (_DWORD)v104 )
          {
            if ( !(unsigned int)CheckWriteOneByte(v12, v10, L"Decompress writes one byte off end of buffer") )
              return (unsigned int)-1626586842;
            *v12++ = v8;
            v88 = (unsigned int)(v88 - 1);
          }
          if ( !(unsigned int)CheckWriteNBytes(v12, v10, v88, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586837;
          memset_0(v12, 0, v88);
          v12 += v88;
        }
        else
        {
          if ( (_DWORD)v104 )
          {
            if ( !(unsigned int)CheckWriteOneByte(v12, v10, L"Decompress writes one byte off end of buffer") )
              return (unsigned int)-1626586859;
            v91 = a6;
            v92 = &v12[-a6];
            if ( !(unsigned int)CheckReadOneByte2Ended(v92, v105, v10, v90) )
              return (unsigned int)-1626586858;
            *v12++ = *v92 ^ a5;
            LODWORD(v88) = v88 - 1;
          }
          else
          {
            v91 = a6;
          }
          v93 = &v12[-v91];
          v94 = v100;
          if ( !(unsigned int)CheckReadNBytes2Ended(
                                v93,
                                v105,
                                v100,
                                (unsigned int)v88,
                                L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586852;
          if ( !(unsigned int)CheckWriteNBytes(v12, v94, (unsigned int)v88, L"Decompress write off end of buffer") )
            return (unsigned int)-1626586851;
          this = (Planar *)v12;
          for ( i = 0; i < (unsigned int)v88; this = (Planar *)((char *)this + 1) )
          {
            ++i;
            *(_BYTE *)this = *v93++;
          }
          v12 += (unsigned int)v88;
        }
        LODWORD(v104) = 1;
        goto LABEL_220;
      }
      LODWORD(v104) = 0;
      v16 = v14 & 0xF0;
      if ( v15 == 64 || v16 == -48 )
      {
        if ( (_BYTE)v14 == 0xF2 || (_BYTE)v14 == 0xF7 )
        {
LABEL_148:
          if ( !(unsigned int)CheckReadNBytes(j + 1, v9, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586808;
          v62 = *(unsigned __int16 *)(j + 1);
          j += 3;
        }
        else if ( v15 == 64 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586800;
          v60 = *j++;
          v61 = v60 & 0x1F;
          if ( !v61 )
          {
            if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586800;
            goto LABEL_142;
          }
LABEL_143:
          v62 = 8 * v61;
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586796;
          v63 = *j++;
          v61 = v63 & 0xF;
          if ( v61 )
            goto LABEL_143;
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586796;
LABEL_142:
          v62 = *j++ + 1;
        }
        v106 = v62;
        if ( v16 == -48 || (_BYTE)v14 == 0xF7 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586789;
          v67 = *j++;
          LOBYTE(a5) = v67;
          if ( (unsigned int)dword_1808B5850 > 5 )
          {
            v65 = "Set FGBG image %u";
            v66 = &word_18086C05E;
LABEL_157:
            v103[0] = v65;
            LODWORD(v98) = v62;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1808B5850,
              (_DWORD)v66,
              (_DWORD)a3,
              (_DWORD)a4,
              (__int64)v103,
              (__int64)&v98);
          }
        }
        else if ( (unsigned int)dword_1808B5850 > 5 )
        {
          v65 = "FGBG image     %u";
          v66 = (__int16 *)&byte_18086C13F;
          goto LABEL_157;
        }
        while ( v62 > 8 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586778;
          v69 = *j;
          if ( v107 )
          {
            v70 = 8;
            v71 = 1;
            if ( !(unsigned int)CheckWriteNBytes(v12, v100, 8u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586774;
            v72 = a5;
            do
            {
              *v12 = 0;
              if ( (v69 & v71) != 0 )
                *v12 = v72;
              ++v12;
              v71 *= 2;
              --v70;
            }
            while ( v70 );
          }
          else
          {
            v73 = a6;
            if ( !(unsigned int)CheckReadOneByte2Ended(&v12[-a6], v105, v10, v68) )
              return (unsigned int)-1626586770;
            v74 = 8;
            v75 = 1;
            if ( !(unsigned int)CheckWriteNBytes(v12, v100, 8u, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586769;
            v76 = a5;
            do
            {
              LOBYTE(this) = v12[-v73];
              *v12 = (unsigned __int8)this;
              if ( (v69 & v75) != 0 )
              {
                LOBYTE(this) = v76 ^ (unsigned __int8)this;
                *v12 = (unsigned __int8)this;
              }
              ++v12;
              v75 *= 2;
              --v74;
            }
            while ( v74 );
            v62 = v106;
          }
          v9 = v99;
          ++j;
          v10 = v100;
          v62 -= 8;
          v106 = v62;
        }
        if ( v62 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586763;
          v78 = *j++;
          if ( v107 )
          {
            v79 = 1;
            v80 = 8;
            if ( v62 < 8 )
              v80 = v62;
            if ( !(unsigned int)CheckWriteNBytes(v12, v10, v80, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586759;
            v81 = a5;
            do
            {
              *v12 = 0;
              if ( (v78 & v79) != 0 )
                *v12 = v81;
              ++v12;
              v79 *= 2;
              --v62;
            }
            while ( v62 );
          }
          else
          {
            v82 = a6;
            if ( !(unsigned int)CheckReadOneByte2Ended(&v12[-a6], v105, v100, v77) )
              return (unsigned int)-1626586755;
            v83 = 1;
            v84 = 8;
            if ( v62 < 8 )
              v84 = v62;
            if ( !(unsigned int)CheckWriteNBytes(v12, v100, v84, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586751;
            v85 = a5;
            do
            {
              LOBYTE(this) = v12[-v82];
              *v12 = (unsigned __int8)this;
              if ( (v78 & v83) != 0 )
              {
                LOBYTE(this) = v85 ^ (unsigned __int8)this;
                *v12 = (unsigned __int8)this;
              }
              ++v12;
              v83 *= 2;
              --v62;
            }
            while ( v62 );
          }
          v9 = v99;
        }
        goto LABEL_220;
      }
      if ( (_BYTE)v14 == 0xF2 || (_BYTE)v14 == 0xF7 )
        goto LABEL_148;
      if ( v15 == 32 || v16 == -64 )
      {
        if ( (_BYTE)v14 == 0xF1 || (_BYTE)v14 == 0xF6 )
        {
LABEL_116:
          if ( !(unsigned int)CheckReadNBytes(j + 1, v9, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586734;
          v53 = *(unsigned __int16 *)(j + 1);
          j += 3;
        }
        else if ( v15 == 32 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586726;
          v52 = *j++;
          v53 = v52 & 0x1F;
          if ( !v53 )
          {
            if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586726;
            v53 = *j + 32;
            goto LABEL_111;
          }
        }
        else
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586722;
          v54 = *j++;
          v53 = v54 & 0xF;
          if ( !v53 )
          {
            if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586722;
            v53 = *j + 16;
LABEL_111:
            ++j;
          }
        }
        if ( v16 == -64 || (_BYTE)v14 == 0xF6 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586712;
          if ( (unsigned int)dword_1808B5850 > 5 )
          {
            a5 = v53;
            v103[0] = "Set FG run     %u";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1808B5850,
              (unsigned int)word_18086C112,
              v58,
              v59,
              (__int64)v103,
              (__int64)&a5);
          }
          v55 = *j++;
          LOBYTE(a5) = v55;
        }
        else
        {
          if ( (unsigned int)dword_1808B5850 > 5 )
          {
            v106 = v53;
            v103[0] = "FG run         %u";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1808B5850,
              (unsigned int)byte_18086C0E5,
              v50,
              v51,
              (__int64)v103,
              (__int64)&v106);
          }
          v55 = a5;
        }
        if ( !(unsigned int)CheckWriteNBytes(v12, v10, v53, L"Decompress write off end of buffer") )
          return (unsigned int)-1626586703;
        if ( v53 )
        {
          v56 = v107;
          while ( 1 )
          {
            if ( v56 )
            {
              *v12 = v55;
            }
            else
            {
              v57 = &v12[-a6];
              if ( !(unsigned int)CheckReadOneByte2Ended(v57, v105, v10, a4) )
                return (unsigned int)-1626586698;
              *v12 = *v57 ^ v55;
              v56 = v107;
            }
            ++v12;
            if ( !--v53 )
              goto LABEL_220;
          }
        }
        goto LABEL_220;
      }
      if ( (_BYTE)v14 == 0xF1 || (_BYTE)v14 == 0xF6 )
        goto LABEL_116;
      if ( v16 == -32 )
      {
        if ( (_BYTE)v14 != 0xF8 )
        {
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586672;
          v47 = *j;
          v46 = j + 1;
          v45 = v47 & 0xF;
          if ( !v45 )
          {
            if ( !(unsigned int)CheckReadOneByte(v46, v9, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586672;
            v45 = *v46++ + 16;
          }
          goto LABEL_97;
        }
      }
      else if ( (_BYTE)v14 != 0xF8 )
      {
        if ( v15 == (char)0x80 )
        {
          if ( (_BYTE)v14 == 0xF4 )
            goto LABEL_77;
          if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
            return (unsigned int)-1626586641;
          v41 = *j;
          v40 = j + 1;
          v39 = v41 & 0x1F;
          if ( !v39 )
          {
            if ( !(unsigned int)CheckReadOneByte(v40, v9, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586641;
            v39 = *v40++ + 32;
          }
        }
        else
        {
          if ( (_BYTE)v14 != 0xF4 )
          {
            if ( v15 == 96 )
            {
              if ( (_BYTE)v14 == 0xF3 )
                goto LABEL_65;
              if ( !(unsigned int)CheckReadOneByte(j, v9, L"Decompress reads one byte end of buffer") )
                return (unsigned int)-1626586613;
              v35 = *j;
              v34 = j + 1;
              v33 = v35 & 0x1F;
              if ( !(_DWORD)v33 )
              {
                if ( !(unsigned int)CheckReadOneByte(v34, v9, L"Decompress reads one byte end of buffer") )
                  return (unsigned int)-1626586613;
                v33 = (unsigned int)*v34++ + 32;
              }
            }
            else
            {
              if ( (_BYTE)v14 != 0xF3 )
              {
                if ( (unsigned int)dword_1808B5850 > 5 )
                {
                  LOBYTE(v106) = v14;
                  v98 = "Special code   %#x";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
                    v13,
                    (unsigned int)&word_18086BED6,
                    (_DWORD)a3,
                    (_DWORD)a4,
                    (__int64)&v98,
                    (__int64)&v106);
                }
                if ( v14 == 249 )
                {
                  if ( v107 )
                  {
                    v24 = 8;
                    v25 = 1;
                    if ( !(unsigned int)CheckWriteNBytes(v12, v10, 8u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586570;
                    v26 = a5;
                    do
                    {
                      *v12 = 0;
                      if ( (v25 & 3) != 0 )
                        *v12 = v26;
                      ++v12;
                      v25 *= 2;
                      --v24;
                    }
                    while ( v24 );
                  }
                  else
                  {
                    v27 = a6;
                    if ( !(unsigned int)CheckReadOneByte2Ended(&v12[-a6], v6, v10, a4) )
                      return (unsigned int)-1626586566;
                    v28 = 8;
                    v29 = 1;
                    if ( !(unsigned int)CheckWriteNBytes(v12, v10, 8u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586562;
                    v30 = a5;
                    do
                    {
                      LOBYTE(this) = v12[-v27];
                      *v12 = (unsigned __int8)this;
                      if ( (v29 & 3) != 0 )
                      {
                        LOBYTE(this) = v30 ^ (unsigned __int8)this;
                        *v12 = (unsigned __int8)this;
                      }
                      ++v12;
                      v29 *= 2;
                      --v28;
                    }
                    while ( v28 );
                  }
                }
                else
                {
                  if ( v14 != 250 )
                  {
                    LODWORD(this) = v14 - 253;
                    if ( v14 == 253 )
                    {
                      if ( !(unsigned int)CheckWriteOneByte(v12, v10, L"Decompress writes one byte off end of buffer") )
                        return (unsigned int)-1626586584;
                      *v12 = -1;
                    }
                    else
                    {
                      if ( v14 != 254 )
                      {
                        if ( (unsigned int)dword_1808B5850 > 2 )
                        {
                          LOBYTE(v106) = v14;
                          v101 = "BDDecompressBitmap8";
                          v97 = 602;
                          v102 = "onecore\\termsrv\\rdpplatform\\codecs\\planar\\planardecompression.cpp";
                          v103[0] = "Invalid compression data %x";
                          LODWORD(v98) = -2147467259;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
                            (_DWORD)this,
                            (unsigned int)byte_18086BE85,
                            (_DWORD)a3,
                            (_DWORD)a4,
                            (__int64)v103,
                            (__int64)&v98,
                            (__int64)&v102,
                            (__int64)&v97,
                            (__int64)&v101,
                            (__int64)&v106);
                        }
                        goto LABEL_63;
                      }
                      if ( !(unsigned int)CheckWriteOneByte(v12, v10, L"Decompress writes one byte off end of buffer") )
                        return (unsigned int)-1626586591;
                      *v12 = 0;
                    }
                    ++v12;
LABEL_63:
                    ++j;
                    goto LABEL_220;
                  }
                  if ( v107 )
                  {
                    v17 = 8;
                    v18 = 1;
                    if ( !(unsigned int)CheckWriteNBytes(v12, v10, 8u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586549;
                    v19 = a5;
                    do
                    {
                      *v12 = 0;
                      if ( (v18 & 5) != 0 )
                        *v12 = v19;
                      ++v12;
                      v18 *= 2;
                      --v17;
                    }
                    while ( v17 );
                  }
                  else
                  {
                    v20 = a6;
                    if ( !(unsigned int)CheckReadOneByte2Ended(&v12[-a6], v6, v10, a4) )
                      return (unsigned int)-1626586545;
                    v21 = 8;
                    v22 = 1;
                    if ( !(unsigned int)CheckWriteNBytes(v12, v10, 8u, L"Decompress write off end of buffer") )
                      return (unsigned int)-1626586541;
                    v23 = a5;
                    do
                    {
                      LOBYTE(this) = v12[-v20];
                      *v12 = (unsigned __int8)this;
                      if ( (v22 & 5) != 0 )
                      {
                        LOBYTE(this) = v23 ^ (unsigned __int8)this;
                        *v12 = (unsigned __int8)this;
                      }
                      ++v12;
                      v22 *= 2;
                      --v21;
                    }
                    while ( v21 );
                  }
                }
                v9 = v99;
                goto LABEL_63;
              }
LABEL_65:
              if ( !(unsigned int)CheckReadNBytes(j + 1, v9, 2u, L"Decompress reads off end of buffer") )
                return (unsigned int)-1626586619;
              v33 = *(unsigned __int16 *)(j + 1);
              v34 = j + 3;
            }
            if ( (unsigned int)dword_1808B5850 > 5 )
            {
              v106 = v33;
              v103[0] = "Color run      %u";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1808B5850,
                (unsigned int)byte_18086BF03,
                v31,
                v32,
                (__int64)v103,
                (__int64)&v106);
            }
            if ( !(unsigned int)CheckReadOneByte(v34, v9, L"Decompress reads one byte end of buffer") )
              return (unsigned int)-1626586609;
            v36 = *v34;
            if ( !(unsigned int)CheckWriteNBytes(v12, v10, v33, L"Decompress write off end of buffer") )
              return (unsigned int)-1626586606;
            j = v34 + 1;
            memset_0(v12, v36, v33);
            v12 += v33;
            goto LABEL_220;
          }
LABEL_77:
          if ( !(unsigned int)CheckReadNBytes(j + 1, v9, 2u, L"Decompress reads off end of buffer") )
            return (unsigned int)-1626586647;
          v39 = *(unsigned __int16 *)(j + 1);
          v40 = j + 3;
        }
        if ( (unsigned int)dword_1808B5850 > 5 )
        {
          v106 = v39;
          v103[0] = "Color image    %u";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)qword_18086BF30,
            v37,
            v38,
            (__int64)v103,
            (__int64)&v106);
        }
        if ( !(unsigned int)CheckReadNBytes(v40, v9, v39, L"Decompress reads off end of buffer") )
          return (unsigned int)-1626586637;
        if ( !(unsigned int)CheckWriteNBytes(v12, v10, v39, L"Decompress write off end of buffer") )
          return (unsigned int)-1626586636;
        this = (Planar *)v40;
        v42 = v12;
        LODWORD(a3) = 0;
        if ( v39 )
        {
          do
          {
            LODWORD(a3) = (_DWORD)a3 + 1;
            *v42 = *(_BYTE *)this;
            this = (Planar *)((char *)this + 1);
            ++v42;
          }
          while ( (unsigned int)a3 < v39 );
        }
        v12 += v39;
        j = &v40[v39];
        goto LABEL_220;
      }
      if ( !(unsigned int)CheckReadNBytes(j + 1, v9, 2u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586678;
      v45 = *(unsigned __int16 *)(j + 1);
      v46 = j + 3;
LABEL_97:
      if ( (unsigned int)dword_1808B5850 > 5 )
      {
        v106 = v45;
        v103[0] = "Dithered run   %u";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1808B5850,
          (unsigned int)qword_18086C0B8,
          v43,
          v44,
          (__int64)v103,
          (__int64)&v106);
      }
      if ( !(unsigned int)CheckReadNBytes(v46, v9, 2u, L"Decompress reads off end of buffer") )
        return (unsigned int)-1626586668;
      v48 = *v46;
      v49 = v46[1];
      if ( !(unsigned int)CheckWriteNBytes(v12, v10, (unsigned int)(2 * v45), L"Decompress write off end of buffer") )
        return (unsigned int)-1626586664;
      for ( j = v46 + 2; v45; --v45 )
      {
        *v12 = v48;
        v12[1] = v49;
        v12 += 2;
      }
LABEL_220:
      v6 = v105;
      if ( j >= v9 )
        break;
      v10 = v100;
      v8 = a5;
      v11 = v107;
    }
  }
  v64 = 0;
  if ( (unsigned int)dword_1808B5850 > 5 )
  {
    v104 = "Decompressed to %Id";
    v105 = (unsigned __int8 *)(v12 - v6);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)this,
      (unsigned int)&dword_18086C02C,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v104,
      (__int64)&v105);
  }
  return v64;
}

```

## disassembly

```asm
0x18034f2ec  mov     [rsp-8+arg_8], rdx
0x18034f2f1  push    rbp
0x18034f2f2  push    rbx
0x18034f2f3  push    rsi
0x18034f2f4  push    rdi
0x18034f2f5  push    r12
0x18034f2f7  push    r13
0x18034f2f9  push    r14
0x18034f2fb  push    r15
0x18034f2fd  lea     rbp, [rsp-0Fh]
0x18034f302  sub     rsp, 98h
0x18034f309  mov     rsi, rdx
0x18034f30c  mov     rbx, rcx
0x18034f30f  mov     r13d, r8d
0x18034f312  mov     r15b, 0FFh
0x18034f315  add     r13, rcx
0x18034f318  mov     r12d, r9d
0x18034f31b  add     r12, rdx
0x18034f31e  mov     [rbp+47h+var_70], r13
0x18034f322  mov     [rbp+47h+var_68], r12
0x18034f326  mov     r14d, 1
0x18034f32c  mov     byte ptr [rbp+47h+arg_20], r15b
0x18034f330  mov     rdi, rdx
0x18034f333  mov     dword ptr [rbp+47h+arg_0], 0
0x18034f33a  mov     [rbp+47h+arg_18], r14d
0x18034f33e  cmp     rcx, r13
0x18034f341  jnb     loc_1803502F6
0x18034f347  test    r14d, r14d
0x18034f34a  jz      short loc_18034F366
0x18034f34c  movzx   eax, [rbp+47h+arg_28]
0x18034f350  mov     ecx, edi
0x18034f352  sub     ecx, esi
0x18034f354  cmp     ecx, eax
0x18034f356  jb      short loc_18034F366
0x18034f358  mov     [rbp+47h+arg_18], 0
0x18034f35f  mov     dword ptr [rbp+47h+arg_0], 0
0x18034f366  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18034f36d  mov     rdx, r13; unsigned __int8 *
0x18034f370  mov     rcx, rbx; unsigned __int8 *
0x18034f373  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x18034f378  test    eax, eax
0x18034f37a  jz      loc_1803502EF
0x18034f380  movzx   r14d, byte ptr [rbx]
0x18034f384  mov     al, r14b
0x18034f387  and     al, 0E0h
0x18034f389  jz      loc_18034FF79
0x18034f38f  cmp     r14b, 0F0h
0x18034f393  jz      loc_18034FF4E
0x18034f399  mov     r15b, r14b
0x18034f39c  mov     dword ptr [rbp+47h+arg_0], 0
0x18034f3a3  and     r15b, 0F0h
0x18034f3a7  cmp     al, 40h ; '@'
0x18034f3a9  jz      loc_18034FC13
0x18034f3af  cmp     r15b, 0D0h
0x18034f3b3  jz      loc_18034FC13
0x18034f3b9  cmp     r14b, 0F2h
0x18034f3bd  jz      loc_18034FCAD
0x18034f3c3  cmp     r14b, 0F7h
0x18034f3c7  jz      loc_18034FCAD
0x18034f3cd  cmp     al, 20h ; ' '
0x18034f3cf  jz      loc_18034FA1A
0x18034f3d5  cmp     r15b, 0C0h
0x18034f3d9  jz      loc_18034FA1A
0x18034f3df  cmp     r14b, 0F1h
0x18034f3e3  jz      loc_18034FABA
0x18034f3e9  cmp     r14b, 0F6h
0x18034f3ed  jz      loc_18034FABA
0x18034f3f3  cmp     r15b, 0E0h
0x18034f3f7  jz      loc_18034F8FD
0x18034f3fd  cmp     r14b, 0F8h
0x18034f401  jz      loc_18034F903
0x18034f407  cmp     al, 80h
0x18034f409  jz      loc_18034F7DF
0x18034f40f  cmp     r14b, 0F4h
0x18034f413  jz      loc_18034F7E5
0x18034f419  cmp     al, 60h ; '`'
0x18034f41b  jz      loc_18034F6D4
0x18034f421  cmp     r14b, 0F3h
0x18034f425  jz      loc_18034F6DA
0x18034f42b  mov     eax, cs:dword_1808B5850
0x18034f431  cmp     eax, 5
0x18034f434  jbe     short loc_18034F463
0x18034f436  lea     rax, aSpecialCodeX; "Special code   %#x"
0x18034f43d  mov     byte ptr [rbp+47h+arg_10], r14b
0x18034f441  mov     [rbp+47h+var_78], rax
0x18034f445  lea     rdx, word_18086BED6
0x18034f44c  lea     rax, [rbp+47h+arg_10]
0x18034f450  mov     [rsp+0D0h+var_A8], rax
0x18034f455  lea     rax, [rbp+47h+var_78]
0x18034f459  mov     [rsp+0D0h+var_B0], rax
0x18034f45e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &)
0x18034f463  mov     ecx, r14d
0x18034f466  sub     ecx, 0F9h
0x18034f46c  jz      loc_18034F616
0x18034f472  sub     ecx, 1
0x18034f475  jz      loc_18034F55A
0x18034f47b  sub     ecx, 3
0x18034f47e  jz      loc_18034F53B
0x18034f484  cmp     ecx, 1
0x18034f487  jz      loc_18034F516
0x18034f48d  mov     eax, cs:dword_1808B5850
0x18034f493  cmp     eax, 2
0x18034f496  jbe     loc_18034F6CC
0x18034f49c  lea     rax, aBddecompressbi; "BDDecompressBitmap8"
0x18034f4a3  mov     byte ptr [rbp+47h+arg_10], r14b
0x18034f4a7  mov     [rbp+47h+var_60], rax
0x18034f4ab  lea     rdx, byte_18086BE85
0x18034f4b2  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x18034f4b9  mov     [rbp+47h+var_80], 25Ah
0x18034f4c0  mov     [rbp+47h+var_58], rax
0x18034f4c4  lea     rax, aInvalidCompres; "Invalid compression data %x"
0x18034f4cb  mov     [rbp+47h+var_50], rax
0x18034f4cf  lea     rax, [rbp+47h+arg_10]
0x18034f4d3  mov     [rsp+0D0h+var_88], rax
0x18034f4d8  lea     rax, [rbp+47h+var_60]
0x18034f4dc  mov     [rsp+0D0h+var_90], rax
0x18034f4e1  lea     rax, [rbp+47h+var_80]
0x18034f4e5  mov     [rsp+0D0h+var_98], rax
0x18034f4ea  lea     rax, [rbp+47h+var_58]
0x18034f4ee  mov     [rsp+0D0h+var_A0], rax
0x18034f4f3  lea     rax, [rbp+47h+var_78]
0x18034f4f7  mov     [rsp+0D0h+var_A8], rax
0x18034f4fc  lea     rax, [rbp+47h+var_50]
0x18034f500  mov     [rsp+0D0h+var_B0], rax
0x18034f505  mov     dword ptr [rbp+47h+var_78], 80004005h
0x18034f50c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &)
0x18034f511  jmp     loc_18034F6CC
0x18034f516  lea     r8, aDecompressWrit_0; "Decompress writes one byte off end of b"...
0x18034f51d  mov     rdx, r12; unsigned __int8 *
0x18034f520  mov     rcx, rdi; unsigned __int8 *
0x18034f523  call    ?CheckWriteOneByte@@YAHPEAE0PEBG@Z; CheckWriteOneByte(uchar *,uchar *,ushort const *)
0x18034f528  test    eax, eax
0x18034f52a  jz      loc_180350148
0x18034f530  mov     byte ptr [rdi], 0
0x18034f533  inc     rdi
0x18034f536  jmp     loc_18034F6CC
0x18034f53b  lea     r8, aDecompressWrit_0; "Decompress writes one byte off end of b"...
0x18034f542  mov     rdx, r12; unsigned __int8 *
0x18034f545  mov     rcx, rdi; unsigned __int8 *
0x18034f548  call    ?CheckWriteOneByte@@YAHPEAE0PEBG@Z; CheckWriteOneByte(uchar *,uchar *,ushort const *)
0x18034f54d  test    eax, eax
0x18034f54f  jz      loc_180350152
0x18034f555  mov     byte ptr [rdi], 0FFh
0x18034f558  jmp     short loc_18034F533
0x18034f55a  cmp     [rbp+47h+arg_18], 0
0x18034f55e  mov     rcx, rdi; unsigned __int8 *
0x18034f561  jz      short loc_18034F5AA
0x18034f563  mov     r15d, 8
0x18034f569  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034f570  mov     r8d, r15d; unsigned __int64
0x18034f573  mov     rdx, r12; unsigned __int8 *
0x18034f576  mov     r14d, r15d
0x18034f579  lea     esi, [r15-7]
0x18034f57d  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034f582  test    eax, eax
0x18034f584  jz      loc_18035015C
0x18034f58a  mov     r13b, byte ptr [rbp+47h+arg_20]
0x18034f58e  mov     byte ptr [rdi], 0
0x18034f591  test    sil, 5
0x18034f595  jz      short loc_18034F59A
0x18034f597  mov     [rdi], r13b
0x18034f59a  inc     rdi
0x18034f59d  add     esi, esi
0x18034f59f  add     r14d, 0FFFFFFFFh
0x18034f5a3  jnz     short loc_18034F58E
0x18034f5a5  jmp     loc_18034F6C8
0x18034f5aa  movzx   r15d, [rbp+47h+arg_28]
0x18034f5af  mov     r8, r12; unsigned __int8 *
0x18034f5b2  sub     rcx, r15; unsigned __int8 *
0x18034f5b5  mov     rdx, rsi; unsigned __int8 *
0x18034f5b8  call    ?CheckReadOneByte2Ended@@YAHPEAE00PEBG@Z; CheckReadOneByte2Ended(uchar *,uchar *,uchar *,ushort const *)
0x18034f5bd  test    eax, eax
0x18034f5bf  jz      loc_180350170
0x18034f5c5  mov     eax, 8
0x18034f5ca  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034f5d1  mov     r8d, eax; unsigned __int64
0x18034f5d4  mov     rdx, r12; unsigned __int8 *
0x18034f5d7  mov     rcx, rdi; unsigned __int8 *
0x18034f5da  mov     r14d, eax
0x18034f5dd  lea     esi, [rax-7]
0x18034f5e0  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034f5e5  test    eax, eax
0x18034f5e7  jz      loc_180350166
0x18034f5ed  mov     r13b, byte ptr [rbp+47h+arg_20]
0x18034f5f1  mov     rax, rdi
0x18034f5f4  sub     rax, r15
0x18034f5f7  mov     cl, [rax]
0x18034f5f9  mov     [rdi], cl
0x18034f5fb  test    sil, 5
0x18034f5ff  jz      short loc_18034F606
0x18034f601  xor     cl, r13b
0x18034f604  mov     [rdi], cl
0x18034f606  inc     rdi
0x18034f609  add     esi, esi
0x18034f60b  add     r14d, 0FFFFFFFFh
0x18034f60f  jnz     short loc_18034F5F1
0x18034f611  jmp     loc_18034F6C8
0x18034f616  cmp     [rbp+47h+arg_18], 0
0x18034f61a  mov     rcx, rdi; unsigned __int8 *
0x18034f61d  jz      short loc_18034F661
0x18034f61f  mov     eax, 8
0x18034f624  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034f62b  mov     r8d, eax; unsigned __int64
0x18034f62e  mov     rdx, r12; unsigned __int8 *
0x18034f631  mov     r14d, eax
0x18034f634  lea     esi, [rax-7]
0x18034f637  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034f63c  test    eax, eax
0x18034f63e  jz      loc_18035017A
0x18034f644  mov     r13b, byte ptr [rbp+47h+arg_20]
0x18034f648  mov     byte ptr [rdi], 0
0x18034f64b  test    sil, 3
0x18034f64f  jz      short loc_18034F654
0x18034f651  mov     [rdi], r13b
0x18034f654  inc     rdi
0x18034f657  add     esi, esi
0x18034f659  add     r14d, 0FFFFFFFFh
0x18034f65d  jnz     short loc_18034F648
0x18034f65f  jmp     short loc_18034F6C8
0x18034f661  movzx   r15d, [rbp+47h+arg_28]
0x18034f666  mov     r8, r12; unsigned __int8 *
0x18034f669  sub     rcx, r15; unsigned __int8 *
0x18034f66c  mov     rdx, rsi; unsigned __int8 *
0x18034f66f  call    ?CheckReadOneByte2Ended@@YAHPEAE00PEBG@Z; CheckReadOneByte2Ended(uchar *,uchar *,uchar *,ushort const *)
0x18034f674  test    eax, eax
0x18034f676  jz      loc_18035018E
0x18034f67c  mov     eax, 8
0x18034f681  lea     r9, aDecompressWrit; "Decompress write off end of buffer"
0x18034f688  mov     r8d, eax; unsigned __int64
0x18034f68b  mov     rdx, r12; unsigned __int8 *
0x18034f68e  mov     rcx, rdi; unsigned __int8 *
0x18034f691  mov     r14d, eax
0x18034f694  lea     esi, [rax-7]
0x18034f697  call    ?CheckWriteNBytes@@YAHPEAE0_KPEBG@Z; CheckWriteNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034f69c  test    eax, eax
0x18034f69e  jz      loc_180350184
0x18034f6a4  mov     r13b, byte ptr [rbp+47h+arg_20]
0x18034f6a8  mov     rax, rdi
0x18034f6ab  sub     rax, r15
0x18034f6ae  mov     cl, [rax]
0x18034f6b0  mov     [rdi], cl
0x18034f6b2  test    sil, 3
0x18034f6b6  jz      short loc_18034F6BD
0x18034f6b8  xor     cl, r13b
0x18034f6bb  mov     [rdi], cl
0x18034f6bd  inc     rdi
0x18034f6c0  add     esi, esi
0x18034f6c2  add     r14d, 0FFFFFFFFh
0x18034f6c6  jnz     short loc_18034F6A8
0x18034f6c8  mov     r13, [rbp+47h+var_70]
0x18034f6cc  inc     rbx
0x18034f6cf  jmp     loc_18035012A
0x18034f6d4  cmp     r14b, 0F3h
0x18034f6d8  jnz     short loc_18034F705
0x18034f6da  lea     r9, aDecompressRead; "Decompress reads off end of buffer"
0x18034f6e1  mov     r8d, 2; unsigned __int64
0x18034f6e7  mov     rdx, r13; unsigned __int8 *
0x18034f6ea  lea     rcx, [rbx+1]; unsigned __int8 *
0x18034f6ee  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18034f6f3  test    eax, eax
0x18034f6f5  jz      loc_180350198
0x18034f6fb  movzx   esi, word ptr [rbx+1]
0x18034f6ff  add     rbx, 3
0x18034f703  jmp     short loc_18034F74D
0x18034f705  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18034f70c  mov     rdx, r13; unsigned __int8 *
0x18034f70f  mov     rcx, rbx; unsigned __int8 *
0x18034f712  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x18034f717  test    eax, eax
0x18034f719  jz      loc_1803501B6
0x18034f71f  movzx   esi, byte ptr [rbx]
0x18034f722  inc     rbx
0x18034f725  and     esi, 1Fh
0x18034f728  jnz     short loc_18034F74D
0x18034f72a  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18034f731  mov     rdx, r13; unsigned __int8 *
0x18034f734  mov     rcx, rbx; unsigned __int8 *
0x18034f737  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
0x18034f73c  test    eax, eax
0x18034f73e  jz      loc_1803501B6
0x18034f744  movzx   esi, byte ptr [rbx]
0x18034f747  add     esi, 20h ; ' '
0x18034f74a  inc     rbx
0x18034f74d  mov     eax, cs:dword_1808B5850
0x18034f753  cmp     eax, 5
0x18034f756  jbe     short loc_18034F78B
0x18034f758  lea     rax, aColorRunU; "Color run      %u"
0x18034f75f  mov     [rbp+47h+arg_10], esi
0x18034f762  mov     [rbp+47h+var_50], rax
0x18034f766  lea     rdx, byte_18086BF03
0x18034f76d  lea     rax, [rbp+47h+arg_10]
0x18034f771  mov     [rsp+0D0h+var_A8], rax
0x18034f776  lea     rcx, dword_1808B5850
0x18034f77d  lea     rax, [rbp+47h+var_50]
0x18034f781  mov     [rsp+0D0h+var_B0], rax
0x18034f786  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18034f78b  lea     r8, aDecompressRead_1; "Decompress reads one byte end of buffer"
0x18034f792  mov     rdx, r13; unsigned __int8 *
0x18034f795  mov     rcx, rbx; unsigned __int8 *
0x18034f798  call    ?CheckReadOneByte@@YAHPEAE0PEBG@Z; CheckReadOneByte(uchar *,uchar *,ushort const *)
  ... truncated ...
```
