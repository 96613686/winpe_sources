# NgcPackAuthBufferInternal(ushort const *,ushort const *,ushort const *,unsigned __int64,ushort const *,unsigned __int64,int,bool,uchar * *,ulong *)

- ea: `0x18001c7e0`
- end: `0x18001d4f4`
- name: `?NgcPackAuthBufferInternal@@YAJPEBG00_K01H_NPEAPEAEPEAK@Z`
- size: `3348`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, int, bool, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001d500`

## callees

- `0x18001c7e0`
- `0x18002a27c`
- `0x18002b31c`
- `0x18002cb1c`
- `0x18002cbf8`
- `0x18002dff0`
- `0x18002e02c`
- `0x18002f7db`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d171`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d2a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d3d8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d497`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d171`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d2a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d3d8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d497`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcPackAuthBufferInternal(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned __int16 *a5,
        unsigned __int64 a6,
        int a7,
        bool a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  unsigned __int16 *v10; // rax
  unsigned __int64 v11; // r14
  __int64 v12; // rcx
  int v13; // r13d
  int v14; // ebx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  _BYTE *v20; // rsi
  size_t v21; // r9
  unsigned __int64 v22; // r15
  _QWORD *v23; // rdi
  unsigned __int64 v24; // r12
  size_t v25; // rcx
  void *v26; // rax
  _WORD *v27; // rax
  __int64 v28; // rcx
  _WORD *v29; // rsi
  __int64 v31; // rdx
  unsigned __int64 v32; // r12
  _QWORD *v33; // rsi
  void *v34; // rax
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rax
  unsigned int v38; // r9d
  _WORD *v39; // rax
  __int64 v40; // rcx
  unsigned __int64 v41; // r12
  unsigned __int64 v42; // rdx
  _WORD *v43; // rax
  __int64 v44; // rcx
  void *v45; // r10
  unsigned __int64 v46; // rax
  unsigned int v47; // eax
  __int64 v48; // rdx
  unsigned __int8 *v49; // rbx
  __int64 v50; // rcx
  unsigned __int16 v51; // ax
  __int64 v52; // rcx
  __int16 v53; // r8
  __int16 v54; // dx
  unsigned __int8 *v55; // rax
  unsigned __int8 *v56; // r12
  int v57; // edx
  int v58; // eax
  int v59; // eax
  unsigned __int64 v60; // rax
  unsigned __int64 v61; // rax
  __int64 v62; // rax
  void **v63; // rdx
  void **v64; // rdx
  unsigned __int64 v65; // rdx
  void *v66; // rcx
  unsigned __int64 v67; // rdx
  void *v68; // rcx
  unsigned __int64 v70; // rdx
  _BYTE *v71; // rcx
  unsigned __int64 v72; // rdx
  _BYTE *v73; // rcx
  unsigned int v74; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v75; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v76; // [rsp+40h] [rbp-C0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v78; // [rsp+58h] [rbp-A8h]
  unsigned __int8 *v79; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  unsigned __int64 v81; // [rsp+70h] [rbp-90h]
  void *v82; // [rsp+78h] [rbp-88h]
  void *v83; // [rsp+80h] [rbp-80h]
  void *v84; // [rsp+88h] [rbp-78h]
  __int64 v85; // [rsp+90h] [rbp-70h]
  __int64 v86; // [rsp+98h] [rbp-68h]
  void *v87; // [rsp+A0h] [rbp-60h]
  unsigned __int8 **v88; // [rsp+A8h] [rbp-58h]
  __int128 v89; // [rsp+B0h] [rbp-50h]
  __int64 v90; // [rsp+C0h] [rbp-40h]
  __int64 v91; // [rsp+C8h] [rbp-38h]
  void *v92[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v93; // [rsp+E0h] [rbp-20h]
  __int64 v94; // [rsp+E8h] [rbp-18h]
  void *v95[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v96; // [rsp+100h] [rbp+0h]
  __int64 v97; // [rsp+108h] [rbp+8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+110h] [rbp+10h] BYREF
  __int16 *v99; // [rsp+120h] [rbp+20h]
  __int64 v100; // [rsp+128h] [rbp+28h]
  unsigned __int64 *v101; // [rsp+130h] [rbp+30h]
  __int64 v102; // [rsp+138h] [rbp+38h]
  _BYTE v103[48]; // [rsp+16Ah] [rbp+6Ah] BYREF
  _BYTE v104[6]; // [rsp+19Ah] [rbp+9Ah] BYREF

  v10 = a3;
  v87 = a3;
  v83 = a2;
  v82 = a1;
  v84 = a5;
  v88 = a9;
  *(_QWORD *)&EventDescriptor.Id = a10;
  v89 = 0;
  v90 = 0;
  v11 = 7;
  v91 = 7;
  LOWORD(v89) = 0;
  UserData = 0;
  v99 = 0;
  v100 = 7;
  LOWORD(UserData.Ptr) = 0;
  if ( !a3 )
  {
    v14 = -2147024809;
LABEL_136:
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v75) = v14;
      v101 = &v75;
      v102 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v99 = word_18005F482;
      v100 = 0x10000002ELL;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    return (unsigned int)v14;
  }
  v12 = 0x7FFFFFFF;
  while ( 1 )
  {
    v13 = -2147024809;
    if ( !*v10 )
      break;
    ++v10;
    if ( !--v12 )
    {
      v14 = -2147024809;
      v15 = 0;
      goto LABEL_7;
    }
  }
  v14 = 0;
  v15 = 2 * (0x7FFFFFFF - v12);
LABEL_7:
  v76 = v15;
  if ( v14 < 0 )
    goto LABEL_136;
  v16 = v15 + 44;
  if ( v15 > 0xFFD3
    || (v17 = (unsigned __int16)v16, v16 = (unsigned __int16)v16 + 2LL, v16 < v17)
    || v16 > 0xFFFF
    || (v18 = (unsigned __int16)v16, v16 = (unsigned __int16)v16 + 78LL, v16 < v18)
    || v16 > 0xFFFF
    || (v19 = (unsigned __int16)v16, v16 = (unsigned __int16)v16 + 2LL, v81 = v16, v16 < v19)
    || v16 > 0xFFFF )
  {
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v16, a5);
  }
  v20 = v103;
  do
  {
    v20 -= 2;
    *(_WORD *)v20 = a4 % 0xA + 48;
    a4 /= 0xAu;
  }
  while ( a4 );
  *(_OWORD *)v92 = 0;
  v93 = 0;
  v94 = 0;
  v21 = -2;
  if ( v20 == v103 )
  {
    v75 = 0;
    v93 = 0;
    v22 = 7;
    v94 = 7;
    LOWORD(v92[0]) = 0;
    v23 = v92[0];
    goto LABEL_36;
  }
  v24 = (v103 - v20) >> 1;
  v75 = v24;
  if ( v24 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v24 > 7 )
  {
    v22 = v24 | 7;
    if ( (v24 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v22 < 0xA )
        v22 = 10;
      if ( v22 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_145;
      v25 = 2 * (v22 + 1);
      if ( !v25 )
      {
        v23 = 0;
        goto LABEL_34;
      }
    }
    else
    {
      v22 = 0x7FFFFFFFFFFFFFFELL;
      v25 = -2;
    }
    if ( v25 >= 0x1000 )
    {
      if ( v25 + 39 >= v25 )
      {
        v26 = operator new(v25 + 39);
        if ( !v26 )
          goto LABEL_134;
        v23 = (_QWORD *)(((unsigned __int64)v26 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v23 - 1) = v26;
        goto LABEL_34;
      }
LABEL_145:
      std::_Throw_bad_array_new_length();
    }
    v23 = operator new(v25);
LABEL_34:
    v92[0] = v23;
    v93 = (v103 - v20) >> 1;
    v94 = v22;
    memcpy_0(v23, v20, 2 * v24);
    *((_WORD *)v23 + v24) = 0;
    goto LABEL_35;
  }
  v93 = (v103 - v20) >> 1;
  v94 = 7;
  memcpy_0(v92, v20, 2 * v24);
  *((_WORD *)v92 + v24) = 0;
  v22 = v94;
  v75 = v93;
  v23 = v92[0];
LABEL_35:
  v21 = -2;
  v15 = v76;
LABEL_36:
  v27 = v84;
  if ( v84 )
  {
    v28 = 0x7FFFFFFF;
    while ( *v27 )
    {
      ++v27;
      if ( !--v28 )
      {
        v14 = -2147024809;
        v78 = 0;
        goto LABEL_42;
      }
    }
    v14 = 0;
    v78 = 2 * (0x7FFFFFFF - v28);
    v76 = v15;
LABEL_42:
    if ( v14 >= 0 )
    {
      v29 = v104;
      do
      {
        *--v29 = a6 % 0xA + 48;
        a6 /= 0xAu;
        v31 = a6;
      }
      while ( a6 );
      Src = v29;
      *(_OWORD *)v95 = 0;
      v96 = 0;
      v97 = 0;
      if ( v29 == (_WORD *)v104 )
      {
        v32 = 0;
        v96 = 0;
        v97 = 7;
        LOWORD(v95[0]) = 0;
        v33 = v95[0];
        goto LABEL_63;
      }
      v32 = (v104 - (_BYTE *)v29) >> 1;
      if ( v32 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v32 <= 7 )
      {
        v96 = (v104 - (_BYTE *)v29) >> 1;
        v97 = 7;
        memcpy_0(v95, v29, 2 * v32);
        *((_WORD *)v95 + v32) = 0;
        v11 = v97;
        v32 = v96;
        v33 = v95[0];
        goto LABEL_63;
      }
      v11 = v32 | 7;
      if ( (v32 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v11 < 0xA )
          v11 = 10;
        if ( v11 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          goto LABEL_144;
        v21 = 2 * (v11 + 1);
        if ( !v21 )
        {
          v33 = 0;
          goto LABEL_62;
        }
      }
      else
      {
        v11 = 0x7FFFFFFFFFFFFFFELL;
      }
      if ( v21 >= 0x1000 )
      {
        if ( v21 + 39 >= v21 )
        {
          v34 = operator new(v21 + 39);
          if ( !v34 )
            goto LABEL_123;
          v33 = (_QWORD *)(((unsigned __int64)v34 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v33 - 1) = v34;
          goto LABEL_62;
        }
LABEL_144:
        std::_Throw_bad_array_new_length();
      }
      v33 = operator new(v21);
LABEL_62:
      v95[0] = v33;
      v96 = v32;
      v97 = v11;
      memcpy_0(v33, Src, 2 * v32);
      *((_WORD *)v33 + v32) = 0;
LABEL_63:
      v35 = (unsigned int)(unsigned __int16)v81 + 44;
      if ( (unsigned int)v35 > 0xFFFF )
        goto LABEL_143;
      v31 = 2 * v75;
      v85 = 2 * v75;
      v35 = (unsigned __int16)(v81 + 44) + 2 * v75;
      if ( v35 < (unsigned __int16)(v81 + 44) )
        goto LABEL_143;
      if ( v35 > 0xFFFF )
        goto LABEL_143;
      v36 = (unsigned __int16)v35;
      v35 = (unsigned __int16)v35 + v78;
      if ( v35 < v36 )
        goto LABEL_143;
      if ( v35 > 0xFFFF )
        goto LABEL_143;
      v31 = 2 * v32;
      v86 = 2 * v32;
      v37 = (unsigned __int16)v35;
      v35 = (unsigned __int16)v35 + 2 * v32;
      if ( v35 < v37 )
        goto LABEL_143;
      if ( v35 > 0xFFFF )
        goto LABEL_143;
      LODWORD(v75) = (unsigned __int16)v35;
      v38 = (unsigned __int16)v35 + 28;
      if ( v38 > 0xFFFF )
        goto LABEL_143;
      v39 = v82;
      if ( v82 )
      {
        v40 = 0x7FFFFFFF;
        while ( *v39 )
        {
          ++v39;
          if ( !--v40 )
          {
            v14 = -2147024809;
            v41 = 0;
            v42 = v76;
            goto LABEL_77;
          }
        }
        v14 = 0;
        v41 = 2 * (0x7FFFFFFF - v40);
        v42 = v76;
LABEL_77:
        if ( v14 >= 0 )
        {
          v43 = v83;
          if ( !v83 )
            goto LABEL_101;
          v44 = 0x7FFFFFFF;
          while ( *v43 )
          {
            ++v43;
            if ( !--v44 )
            {
              v45 = 0;
              Src = 0;
              goto LABEL_84;
            }
          }
          v13 = 0;
          v45 = (void *)(2 * (0x7FFFFFFF - v44));
          Src = v45;
          v76 = v42;
LABEL_84:
          if ( v13 < 0 )
          {
LABEL_101:
            if ( (unsigned int)dword_18006E000 > 2 )
            {
              LODWORD(v75) = v13;
              v101 = &v75;
              v102 = 4;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              *(_DWORD *)&EventDescriptor.Level = 2;
              EventDescriptor.Keyword = 0;
              UserData.Ptr = (ULONGLONG)off_18006E008;
              UserData.Size = *(unsigned __int16 *)off_18006E008;
              UserData.Reserved = 2;
              v99 = (__int16 *)&unk_18005F3D8;
              v100 = 0x10000002BLL;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
            }
            goto LABEL_103;
          }
          v35 = v41 + 48;
          v31 = 4294967247LL;
          if ( v41 <= 0xFFFFFFCF )
          {
            v46 = (unsigned int)v35;
            v35 = (unsigned __int64)v45 + (unsigned int)v35;
            if ( v35 >= v46 && v35 <= 0xFFFFFFFF )
            {
              v47 = v35 + (unsigned __int16)v38;
              v74 = v47;
              if ( v47 >= (unsigned int)v35 )
              {
                wil::make_unique_hlocal_secure<unsigned char [0]>(&v79, v47);
                v49 = v79;
                *(_DWORD *)v79 = 513;
                v50 = 48;
                *((_WORD *)v49 + 2) = 48;
                *((_DWORD *)v49 + 2) = v74;
                *((_DWORD *)v49 + 3) = 48;
                if ( v41 > 0xFFFF )
                  goto LABEL_142;
                *((_WORD *)v49 + 8) = v41;
                v50 = (unsigned int)(unsigned __int16)v41 + 48;
                *((_DWORD *)v49 + 5) = v50;
                v51 = (unsigned __int16)Src;
                if ( (unsigned __int64)Src > 0xFFFF )
                  goto LABEL_142;
                *((_WORD *)v49 + 12) = (_WORD)Src;
                v52 = v51 + (unsigned int)v50;
                *((_DWORD *)v49 + 7) = v52;
                v53 = v75;
                v54 = v75 + 28;
                *((_WORD *)v49 + 16) = v75 + 28;
                *(_QWORD *)(v49 + 36) = 0;
                *((_WORD *)v49 + 22) = 0;
                v55 = v79;
                *(_WORD *)&v79[v52] = 28;
                *(_WORD *)&v55[v52 + 2] = v54;
                *(_OWORD *)&v55[v52 + 4] = SEC_WINNT_AUTH_DATA_TYPE_NGC;
                *(_DWORD *)&v55[v52 + 20] = 28;
                *(_WORD *)&v55[v52 + 24] = v53;
                v56 = &v55[v52 + 28];
                *(_QWORD *)v56 = 0;
                *((_DWORD *)v56 + 2) = 0;
                if ( a8 )
                  *((_DWORD *)v56 + 2) = 8;
                *((_DWORD *)v56 + 3) = 44;
                v57 = (unsigned __int16)v81;
                *((_WORD *)v56 + 8) = v81;
                *((_DWORD *)v56 + 5) = v57 + 44;
                v58 = (unsigned __int16)v85;
                *((_WORD *)v56 + 12) = v85;
                v50 = (unsigned int)(v58 + v57 + 44);
                *((_DWORD *)v56 + 7) = v50;
                v59 = (unsigned __int16)v78;
                *((_WORD *)v56 + 16) = v78;
                *((_DWORD *)v56 + 9) = v50 + v59;
                *((_WORD *)v56 + 20) = v86;
                *((_DWORD *)v56 + 11) = v57;
                *((_DWORD *)v56 + 12) = 1;
                *(_QWORD *)(v56 + 52) = 0;
                *((_DWORD *)v56 + 15) = 0;
                v48 = 0xFFFFFFFFLL;
                *((_DWORD *)v56 + 16) = -1;
                *((_DWORD *)v56 + 17) = 0;
                *((_DWORD *)v56 + 18) = 1;
                *((_DWORD *)v56 + 19) = 2;
                v60 = v76 >> 1;
                if ( v76 >> 1 > 0xFFFFFFFF
                  || (v50 = (unsigned int)(v60 + 2), (unsigned int)v50 < (unsigned int)v60)
                  || (v61 = (unsigned int)v50 + 1LL, v61 > 0xFFFFFFFF) )
                {
LABEL_142:
                  SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v50, v48);
                }
                *((_DWORD *)v56 + 20) = v61;
                memcpy_0(&v49[*((unsigned int *)v49 + 3)], v82, *((unsigned __int16 *)v49 + 8));
                memcpy_0(&v49[*((unsigned int *)v49 + 5)], v83, *((unsigned __int16 *)v49 + 12));
                *(_WORD *)&v56[2 * *((unsigned int *)v56 + 17) + 84] = 0;
                *(_WORD *)&v56[2 * *((unsigned int *)v56 + 18) + 84] = 0;
                memcpy_0(&v56[2 * *((unsigned int *)v56 + 19) + 84], v87, v76 + 2);
                v62 = *((unsigned int *)v56 + 20);
                *(_OWORD *)&v56[2 * v62 + 84] = *(_OWORD *)L"Microsoft Passport Key Storage Provider";
                *(_OWORD *)&v56[2 * v62 + 100] = *(_OWORD *)L"t Passport Key Storage Provider";
                *(_OWORD *)&v56[2 * v62 + 116] = *(_OWORD *)L"rt Key Storage Provider";
                *(_OWORD *)&v56[2 * v62 + 132] = *(_OWORD *)L"torage Provider";
                *(_OWORD *)&v56[2 * v62 + 148] = *(_OWORD *)L"rovider";
                v63 = v92;
                if ( v22 > 7 )
                  v63 = (void **)v23;
                memcpy_0(&v56[*((unsigned int *)v56 + 5)], v63, *((unsigned __int16 *)v56 + 12));
                memcpy_0(&v56[*((unsigned int *)v56 + 7)], v84, *((unsigned __int16 *)v56 + 16));
                v64 = v95;
                if ( v11 > 7 )
                  v64 = (void **)v33;
                memcpy_0(&v56[*((unsigned int *)v56 + 9)], v64, *((unsigned __int16 *)v56 + 20));
                *v88 = v79;
                **(_DWORD **)&EventDescriptor.Id = v74;
                v79 = 0;
LABEL_103:
                if ( v11 <= 7 )
                {
LABEL_109:
                  if ( v22 <= 7 )
                    return (unsigned int)v13;
                  v67 = 2 * v22 + 2;
                  if ( v67 < 0x1000 )
                  {
                    v68 = v23;
                    goto LABEL_114;
                  }
                  v68 = (void *)*(v23 - 1);
                  if ( (unsigned __int64)((char *)v23 - (_BYTE *)v68 - 8) <= 0x1F )
                  {
                    v67 = 2 * v22 + 41;
LABEL_114:
                    operator delete(v68, v67);
                    return (unsigned int)v13;
                  }
LABEL_134:
                  __fastfail(5u);
                }
                v65 = 2 * v11 + 2;
                if ( v65 < 0x1000 )
                {
                  v66 = v33;
                  goto LABEL_108;
                }
                v66 = (void *)*(v33 - 1);
                if ( (unsigned __int64)((char *)v33 - (_BYTE *)v66 - 8) <= 0x1F )
                {
                  v65 = 2 * v11 + 41;
LABEL_108:
                  operator delete(v66, v65);
                  goto LABEL_109;
                }
LABEL_123:
                __fastfail(5u);
              }
            }
          }
LABEL_143:
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v35, v31);
        }
      }
      else
      {
        v14 = -2147024809;
      }
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        LODWORD(v75) = v14;
        v101 = &v75;
        v102 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_18006E008;
        UserData.Size = *(unsigned __int16 *)off_18006E008;
        UserData.Reserved = 2;
        v99 = (__int16 *)&byte_18005F40F;
        v100 = 0x100000029LL;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      if ( v11 > 7 )
      {
        v70 = 2 * v11 + 2;
        if ( v70 < 0x1000 )
        {
          v71 = v33;
        }
        else
        {
          v71 = (_BYTE *)*(v33 - 1);
          if ( (unsigned __int64)((char *)v33 - v71 - 8) > 0x1F )
            goto LABEL_123;
          v70 = 2 * v11 + 41;
        }
        operator delete(v71, v70);
      }
      goto LABEL_126;
    }
  }
  else
  {
    v14 = -2147024809;
  }
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    LODWORD(v75) = v14;
    v101 = &v75;
    v102 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    UserData.Reserved = 2;
    v99 = (__int16 *)&dword_18005F444;
    v100 = 0x100000032LL;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
LABEL_126:
  if ( v22 > 7 )
  {
    v72 = 2 * v22 + 2;
    if ( v72 < 0x1000 )
    {
      operator delete(v23, v72);
    }
    else
    {
      v73 = (_BYTE *)*(v23 - 1);
      if ( (unsigned __int64)((char *)v23 - v73 - 8) > 0x1F )
        goto LABEL_134;
      operator delete(v73, 2 * v22 + 41);
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001c7e0  mov     [rsp-8+arg_18], rbx
0x18001c7e5  push    rbp
0x18001c7e6  push    rsi
0x18001c7e7  push    rdi
0x18001c7e8  push    r12
0x18001c7ea  push    r13
0x18001c7ec  push    r14
0x18001c7ee  push    r15
0x18001c7f0  lea     rbp, [rsp-0B0h]
0x18001c7f8  sub     rsp, 1B0h
0x18001c7ff  mov     rax, cs:__security_cookie
0x18001c806  xor     rax, rsp
0x18001c809  mov     [rbp+0E0h+var_40], rax
0x18001c810  mov     rax, r8
0x18001c813  mov     [rbp+0E0h+var_140], rax
0x18001c817  mov     [rbp+0E0h+var_160], rdx
0x18001c81b  mov     [rsp+1E0h+var_168], rcx
0x18001c820  mov     rdx, [rbp+0E0h+arg_20]
0x18001c827  mov     [rbp+0E0h+var_158], rdx
0x18001c82b  mov     rcx, [rbp+0E0h+arg_40]
0x18001c832  mov     [rbp+0E0h+var_138], rcx
0x18001c836  mov     rcx, [rbp+0E0h+arg_48]
0x18001c83d  mov     qword ptr [rsp+1E0h+EventDescriptor.Id], rcx
0x18001c842  xor     r11d, r11d
0x18001c845  xorps   xmm0, xmm0
0x18001c848  movups  [rbp+0E0h+var_130], xmm0
0x18001c84c  mov     [rbp+0E0h+var_120], r11
0x18001c850  mov     r14d, 7
0x18001c856  mov     [rbp+0E0h+var_118], r14
0x18001c85a  xor     ecx, ecx
0x18001c85c  mov     word ptr [rbp+0E0h+var_130], cx
0x18001c860  movups  xmmword ptr [rbp+0E0h+var_D0.Ptr], xmm0
0x18001c864  mov     [rbp+0E0h+var_C0], r11
0x18001c868  mov     [rbp+0E0h+var_B8], r14
0x18001c86c  mov     word ptr [rbp+0E0h+var_D0.Ptr], cx
0x18001c870  test    r8, r8
0x18001c873  jz      loc_18001D3EA
0x18001c879  mov     r10d, 7FFFFFFFh
0x18001c87f  mov     ecx, r10d
0x18001c882  mov     r13d, 80070057h
0x18001c888  cmp     word ptr [rax], 0
0x18001c88c  jz      short loc_18001C8A0
0x18001c88e  add     rax, 2
0x18001c892  sub     rcx, 1
0x18001c896  jnz     short loc_18001C882
0x18001c898  mov     ebx, r13d
0x18001c89b  mov     r8, r11
0x18001c89e  jmp     short loc_18001C8AC
0x18001c8a0  mov     ebx, r11d
0x18001c8a3  mov     r8, r10
0x18001c8a6  sub     r8, rcx
0x18001c8a9  add     r8, r8
0x18001c8ac  mov     [rsp+1E0h+var_1A0], r8
0x18001c8b1  test    ebx, ebx
0x18001c8b3  js      loc_18001D3EF
0x18001c8b9  lea     rcx, [r8+2Ch]
0x18001c8bd  lea     rax, [rcx-2Ch]
0x18001c8c1  cmp     rax, 0FFD3h
0x18001c8c7  ja      loc_18001D4CA
0x18001c8cd  movzx   eax, cx
0x18001c8d0  lea     rcx, [rax+2]
0x18001c8d4  cmp     rcx, rax
0x18001c8d7  jb      loc_18001D4CA
0x18001c8dd  cmp     rcx, 0FFFFh
0x18001c8e4  ja      loc_18001D4CA
0x18001c8ea  movzx   eax, cx
0x18001c8ed  lea     rcx, [rax+4Eh]
0x18001c8f1  cmp     rcx, rax
0x18001c8f4  jb      loc_18001D4CA
0x18001c8fa  cmp     rcx, 0FFFFh
0x18001c901  ja      loc_18001D4CA
0x18001c907  movzx   eax, cx
0x18001c90a  lea     rcx, [rax+2]
0x18001c90e  mov     [rsp+1E0h+var_170], rcx
0x18001c913  cmp     rcx, rax
0x18001c916  jb      loc_18001D4CA
0x18001c91c  cmp     rcx, 0FFFFh
0x18001c923  ja      loc_18001D4CA
0x18001c929  lea     rsi, [rbp+0E0h+var_76]
0x18001c92d  mov     r12, 0CCCCCCCCCCCCCCCDh
0x18001c937  nop     word ptr [rax+rax+00000000h]
0x18001c940  sub     rsi, 2
0x18001c944  mov     rax, r12
0x18001c947  mul     r9
0x18001c94a  shr     rdx, 3
0x18001c94e  movzx   eax, dx
0x18001c951  shl     ax, 2
0x18001c955  lea     ecx, [rax+rdx]
0x18001c958  add     cx, cx
0x18001c95b  sub     r9w, cx
0x18001c95f  add     r9w, 30h ; '0'
0x18001c964  mov     [rsi], r9w
0x18001c968  mov     r9, rdx
0x18001c96b  test    rdx, rdx
0x18001c96e  jnz     short loc_18001C940
0x18001c970  xorps   xmm0, xmm0
0x18001c973  movups  xmmword ptr [rbp+0E0h+var_110], xmm0
0x18001c977  mov     [rbp+0E0h+var_100], r11
0x18001c97b  mov     [rbp+0E0h+var_F8], r11
0x18001c97f  lea     rax, [rbp+0E0h+var_76]
0x18001c983  mov     edx, 0Ah
0x18001c988  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18001c992  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18001c99c  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001c9a3  cmp     rsi, rax
0x18001c9a6  jnz     short loc_18001C9C9
0x18001c9a8  mov     rcx, r11
0x18001c9ab  mov     [rsp+1E0h+var_1A8], rcx
0x18001c9b0  mov     [rbp+0E0h+var_100], rcx
0x18001c9b4  mov     r15, r14
0x18001c9b7  mov     [rbp+0E0h+var_F8], r14
0x18001c9bb  mov     word ptr [rbp+0E0h+var_110], r11w
0x18001c9c0  mov     rdi, [rbp+0E0h+var_110]
0x18001c9c4  jmp     loc_18001CAD0
0x18001c9c9  lea     r12, [rbp+0E0h+var_76]
0x18001c9cd  sub     r12, rsi
0x18001c9d0  sar     r12, 1
0x18001c9d3  mov     [rsp+1E0h+var_1A8], r12
0x18001c9d8  cmp     r12, rcx
0x18001c9db  ja      loc_18001D4D0
0x18001c9e1  cmp     r12, 7
0x18001c9e5  ja      short loc_18001CA21
0x18001c9e7  mov     [rbp+0E0h+var_100], r12
0x18001c9eb  mov     [rbp+0E0h+var_F8], r14
0x18001c9ef  lea     rbx, [r12+r12]
0x18001c9f3  mov     r8, rbx; Size
0x18001c9f6  mov     rdx, rsi; Src
0x18001c9f9  lea     rcx, [rbp+0E0h+var_110]; void *
0x18001c9fd  call    memcpy_0
0x18001ca02  xor     r11d, r11d
0x18001ca05  mov     word ptr [rbp+rbx+0E0h+var_110], r11w
0x18001ca0b  mov     r15, [rbp+0E0h+var_F8]
0x18001ca0f  mov     rax, [rbp+0E0h+var_100]
0x18001ca13  mov     [rsp+1E0h+var_1A8], rax
0x18001ca18  mov     rdi, [rbp+0E0h+var_110]
0x18001ca1c  jmp     loc_18001CAB4
0x18001ca21  mov     r15, r12
0x18001ca24  or      r15, 7
0x18001ca28  cmp     r15, rcx
0x18001ca2b  jbe     short loc_18001CA68
0x18001ca2d  mov     r15, rcx
0x18001ca30  mov     rcx, r9; Size
0x18001ca33  cmp     rcx, 1000h
0x18001ca3a  jb      short loc_18001CA86
0x18001ca3c  lea     rax, [rcx+27h]
0x18001ca40  cmp     rax, rcx
0x18001ca43  jbe     loc_18001D4EE
0x18001ca49  mov     rcx, rax; Size
0x18001ca4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ca51  test    rax, rax
0x18001ca54  jz      loc_18001D3E3
0x18001ca5a  lea     rdi, [rax+27h]
0x18001ca5e  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001ca62  mov     [rdi-8], rax
0x18001ca66  jmp     short loc_18001CA8E
0x18001ca68  cmp     r15, rdx
0x18001ca6b  cmovb   r15, rdx
0x18001ca6f  lea     rcx, [r15+1]
0x18001ca73  cmp     rcx, rbx
0x18001ca76  ja      loc_18001D4EE
0x18001ca7c  add     rcx, rcx
0x18001ca7f  jnz     short loc_18001CA33
0x18001ca81  mov     rdi, r11
0x18001ca84  jmp     short loc_18001CA8E
0x18001ca86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ca8b  mov     rdi, rax
0x18001ca8e  mov     [rbp+0E0h+var_110], rdi
0x18001ca92  mov     [rbp+0E0h+var_100], r12
0x18001ca96  mov     [rbp+0E0h+var_F8], r15
0x18001ca9a  lea     rbx, [r12+r12]
0x18001ca9e  mov     r8, rbx; Size
0x18001caa1  mov     rdx, rsi; Src
0x18001caa4  mov     rcx, rdi; void *
0x18001caa7  call    memcpy_0
0x18001caac  xor     r11d, r11d
0x18001caaf  mov     [rdi+rbx], r11w
0x18001cab4  mov     r12, 0CCCCCCCCCCCCCCCDh
0x18001cabe  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001cac5  mov     r8, [rsp+1E0h+var_1A0]
0x18001caca  mov     r10d, 7FFFFFFFh
0x18001cad0  mov     rax, [rbp+0E0h+var_158]
0x18001cad4  test    rax, rax
0x18001cad7  jz      loc_18001D331
0x18001cadd  mov     rcx, r10
0x18001cae0  cmp     word ptr [rax], 0
0x18001cae4  jz      short loc_18001CAFA
0x18001cae6  add     rax, 2
0x18001caea  sub     rcx, 1
0x18001caee  jnz     short loc_18001CAE0
0x18001caf0  mov     ebx, r13d
0x18001caf3  mov     [rsp+1E0h+var_188], r11
0x18001caf8  jmp     short loc_18001CB10
0x18001cafa  mov     ebx, r11d
0x18001cafd  mov     rax, r10
0x18001cb00  sub     rax, rcx
0x18001cb03  add     rax, rax
0x18001cb06  mov     [rsp+1E0h+var_188], rax
0x18001cb0b  mov     [rsp+1E0h+var_1A0], r8
0x18001cb10  test    ebx, ebx
0x18001cb12  js      loc_18001D334
0x18001cb18  lea     rsi, [rbp+0E0h+var_46]
0x18001cb1f  mov     r8, [rbp+0E0h+arg_28]
0x18001cb26  nop     word ptr [rax+rax+00000000h]
0x18001cb30  sub     rsi, 2
0x18001cb34  mov     rax, r12
0x18001cb37  mul     r8
0x18001cb3a  shr     rdx, 3
0x18001cb3e  movzx   eax, dx
0x18001cb41  shl     ax, 2
0x18001cb45  lea     ecx, [rax+rdx]
0x18001cb48  add     cx, cx
0x18001cb4b  sub     r8w, cx
0x18001cb4f  add     r8w, 30h ; '0'
0x18001cb54  mov     [rsi], r8w
0x18001cb58  mov     r8, rdx
0x18001cb5b  test    rdx, rdx
0x18001cb5e  jnz     short loc_18001CB30
0x18001cb60  mov     [rsp+1E0h+Src], rsi
0x18001cb65  xorps   xmm0, xmm0
0x18001cb68  movups  xmmword ptr [rbp+0E0h+var_F0], xmm0
0x18001cb6c  mov     [rbp+0E0h+var_E0], r11
0x18001cb70  mov     [rbp+0E0h+var_D8], r11
0x18001cb74  lea     rax, [rbp+0E0h+var_46]
0x18001cb7b  cmp     rsi, rax
0x18001cb7e  jnz     short loc_18001CB99
0x18001cb80  mov     r12, r11
0x18001cb83  mov     [rbp+0E0h+var_E0], r11
0x18001cb87  mov     [rbp+0E0h+var_D8], r14
0x18001cb8b  mov     word ptr [rbp+0E0h+var_F0], r11w
0x18001cb90  mov     rsi, [rbp+0E0h+var_F0]
0x18001cb94  jmp     loc_18001CC9C
0x18001cb99  lea     r12, [rbp+0E0h+var_46]
0x18001cba0  sub     r12, rsi
0x18001cba3  sar     r12, 1
0x18001cba6  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001cbb0  cmp     r12, rax
0x18001cbb3  ja      loc_18001D4D6
0x18001cbb9  cmp     r12, 7
0x18001cbbd  ja      short loc_18001CBF4
0x18001cbbf  mov     [rbp+0E0h+var_E0], r12
0x18001cbc3  mov     [rbp+0E0h+var_D8], r14
0x18001cbc7  lea     rbx, [r12+r12]
0x18001cbcb  mov     r8, rbx; Size
0x18001cbce  mov     rdx, rsi; Src
0x18001cbd1  lea     rcx, [rbp+0E0h+var_F0]; void *
0x18001cbd5  call    memcpy_0
0x18001cbda  xor     r11d, r11d
0x18001cbdd  mov     word ptr [rbp+rbx+0E0h+var_F0], r11w
0x18001cbe3  mov     r14, [rbp+0E0h+var_D8]
0x18001cbe7  mov     r12, [rbp+0E0h+var_E0]
0x18001cbeb  mov     rsi, [rbp+0E0h+var_F0]
0x18001cbef  jmp     loc_18001CC96
0x18001cbf4  mov     r14, r12
0x18001cbf7  or      r14, 7
0x18001cbfb  cmp     r14, rax
0x18001cbfe  jbe     short loc_18001CC35
0x18001cc00  mov     r14, rax
0x18001cc03  cmp     r9, 1000h
0x18001cc0a  jb      short loc_18001CC63
0x18001cc0c  lea     rcx, [r9+27h]; Size
0x18001cc10  cmp     rcx, r9
0x18001cc13  jbe     loc_18001D4E8
0x18001cc19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cc1e  test    rax, rax
0x18001cc21  jz      loc_18001D2D6
0x18001cc27  lea     rsi, [rax+27h]
0x18001cc2b  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18001cc2f  mov     [rsi-8], rax
0x18001cc33  jmp     short loc_18001CC6E
0x18001cc35  cmp     r14, 0Ah
0x18001cc39  mov     eax, 0Ah
0x18001cc3e  cmovb   r14, rax
0x18001cc42  lea     r9, [r14+1]
0x18001cc46  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001cc50  cmp     r9, rax
0x18001cc53  ja      loc_18001D4E8
0x18001cc59  add     r9, r9
0x18001cc5c  jnz     short loc_18001CC03
0x18001cc5e  mov     rsi, r11
0x18001cc61  jmp     short loc_18001CC6E
0x18001cc63  mov     rcx, r9; Size
0x18001cc66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cc6b  mov     rsi, rax
0x18001cc6e  mov     [rbp+0E0h+var_F0], rsi
0x18001cc72  mov     [rbp+0E0h+var_E0], r12
0x18001cc76  mov     [rbp+0E0h+var_D8], r14
0x18001cc7a  lea     rbx, [r12+r12]
0x18001cc7e  mov     r8, rbx; Size
0x18001cc81  mov     rdx, [rsp+1E0h+Src]; Src
0x18001cc86  mov     rcx, rsi; void *
0x18001cc89  call    memcpy_0
0x18001cc8e  xor     r11d, r11d
0x18001cc91  mov     [rsi+rbx], r11w
0x18001cc96  mov     r10d, 7FFFFFFFh
0x18001cc9c  movzx   ecx, word ptr [rsp+1E0h+var_170]
0x18001cca1  add     ecx, 2Ch ; ','
0x18001cca4  cmp     ecx, 0FFFFh
0x18001ccaa  ja      loc_18001D4E2
0x18001ccb0  mov     rax, [rsp+1E0h+var_1A8]
0x18001ccb5  lea     rdx, [rax+rax]
  ... truncated ...
```
