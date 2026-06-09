# ImportHelper::MergeUpdateTokenInFieldSig(CMiniMdRW *,CMiniMdRW *,IMetaModelCommon *,void const *,ulong,IMetaModelCommon *,uchar const *,MDTOKENMAP *,CQuickBytes *,ulong,ulong *,ulong *)

- ea: `0x1800b74b4`
- end: `0x1800b80a2`
- name: `?MergeUpdateTokenInFieldSig@ImportHelper@@SAJPEAVCMiniMdRW@@0PEAVIMetaModelCommon@@PEBXK1PEBEPEAVMDTOKENMAP@@PEAVCQuickBytes@@KPEAK6@Z`
- size: `3054`
- prototype: `__int64 __fastcall(struct CMiniMdRW *, struct CMiniMdRW *, struct IMetaModelCommon *, const void *, unsigned int, struct IMetaModelCommon *, const unsigned __int8 *, struct MDTOKENMAP *, struct CQuickBytes *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b74b4`
- `0x1800b80a4`

## callees

- `0x180040d24`
- `0x180079d00`
- `0x1800b607c`
- `0x1800b74b4`
- `0x1800b80a4`
- `0x1800b883c`
- `0x1800b8c0c`
- `0x1800cd720`
- `0x1800d65f4`
- `0x1800d7050`
- `0x1800f0d20`
- `0x1800f21d0`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800b7c56`
- `KERNEL32!HeapFree` at `0x1800b7dd1`
- `KERNEL32!HeapFree` at `0x1800b7c56`
- `KERNEL32!HeapFree` at `0x1800b7dd1`
- `KERNEL32!GetProcessHeap` at `0x1800b7c41`
- `KERNEL32!GetProcessHeap` at `0x1800b7dbc`
- `KERNEL32!GetProcessHeap` at `0x1800b7c41`
- `KERNEL32!GetProcessHeap` at `0x1800b7dbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ImportHelper::MergeUpdateTokenInFieldSig(
        struct CMiniMdRW *a1,
        struct CMiniMdRW *a2,
        struct IMetaModelCommon *a3,
        void *a4,
        unsigned int a5,
        struct IMetaModelCommon *a6,
        unsigned __int8 *a7,
        struct MDTOKENMAP *a8,
        struct CQuickBytes *a9,
        unsigned int a10,
        unsigned int *a11,
        unsigned int *a12)
{
  unsigned int v12; // edx
  int v13; // r15d
  unsigned __int64 v14; // rsi
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // r14d
  unsigned int v18; // r12d
  struct CQuickBytes *v19; // r13
  int v20; // edi
  char *v21; // rax
  const unsigned __int8 *v22; // rsi
  unsigned int v23; // ebx
  unsigned int v24; // r14d
  unsigned int v25; // esi
  unsigned int v26; // r12d
  char *v27; // rax
  char *v28; // rcx
  unsigned int v29; // eax
  char *v30; // rcx
  unsigned int v31; // r15d
  const unsigned __int8 *v32; // r12
  unsigned int v33; // ebx
  unsigned int v34; // r14d
  const unsigned __int8 *v35; // rdi
  const unsigned __int8 *v36; // r12
  unsigned int v37; // edx
  unsigned int v38; // esi
  unsigned int v39; // edx
  unsigned int v40; // edi
  unsigned int v41; // eax
  unsigned int v42; // esi
  const unsigned __int8 *v43; // r13
  int v44; // eax
  unsigned int v45; // ecx
  unsigned int v46; // edx
  unsigned int v47; // edi
  unsigned int v48; // eax
  const unsigned __int8 *v49; // r13
  int v50; // eax
  unsigned int v51; // ecx
  __int64 v52; // r15
  char *v53; // rax
  int updated; // eax
  __int64 v55; // rcx
  const void *v56; // r9
  unsigned int v57; // esi
  unsigned int v58; // esi
  unsigned int v59; // eax
  int v60; // eax
  struct IMetaModelCommon *v61; // r12
  void *v62; // rbx
  HANDLE v63; // rax
  struct CMiniMdRW *v64; // r15
  const unsigned __int8 *v65; // rdx
  int TypeSpec; // eax
  _BYTE *v67; // rcx
  _DWORD *v68; // rax
  void *v69; // rdi
  HANDLE ProcessHeap; // rax
  int v71; // eax
  unsigned int v72; // esi
  unsigned int v73; // r12d
  unsigned int v74; // eax
  int v75; // r13d
  struct CQuickBytes *v76; // rdx
  char *v77; // rax
  unsigned int v78; // ecx
  char *v79; // r8
  unsigned int v80; // esi
  unsigned int v81; // r12d
  char *v82; // rax
  char *v83; // rcx
  int v84; // eax
  unsigned int v86; // [rsp+20h] [rbp-E0h]
  bool v87; // [rsp+38h] [rbp-C8h]
  unsigned int v88; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v89; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v90; // [rsp+68h] [rbp-98h]
  unsigned int v91; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v92; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v93; // [rsp+74h] [rbp-8Ch] BYREF
  void *Src; // [rsp+78h] [rbp-88h]
  unsigned int v95; // [rsp+80h] [rbp-80h] BYREF
  struct IMetaModelCommon *v96; // [rsp+88h] [rbp-78h]
  struct IMetaModelCommon *v97; // [rsp+90h] [rbp-70h]
  struct CMiniMdRW *v98; // [rsp+98h] [rbp-68h]
  struct CMiniMdRW *v99; // [rsp+A0h] [rbp-60h]
  MDTOKENMAP *v100; // [rsp+A8h] [rbp-58h]
  void *v101; // [rsp+B0h] [rbp-50h]
  struct CQuickBytes *v102; // [rsp+B8h] [rbp-48h]
  void *v103; // [rsp+C0h] [rbp-40h] BYREF
  struct TOKENREC *v104; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v105; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int *v106; // [rsp+D8h] [rbp-28h]
  unsigned int *v107; // [rsp+E0h] [rbp-20h]
  __int64 v108; // [rsp+F0h] [rbp-10h]
  __int64 v109; // [rsp+F8h] [rbp-8h]
  __int64 v110; // [rsp+100h] [rbp+0h]
  __int64 v111; // [rsp+310h] [rbp+210h]
  __int64 v112; // [rsp+318h] [rbp+218h]
  __int64 v113; // [rsp+320h] [rbp+220h]
  __int64 v114; // [rsp+530h] [rbp+430h]
  __int64 v115; // [rsp+538h] [rbp+438h]
  __int64 v116; // [rsp+540h] [rbp+440h]
  LPVOID lpMem[3]; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v118[520]; // [rsp+768h] [rbp+668h] BYREF

  v101 = a4;
  v97 = a3;
  v98 = a2;
  v99 = a1;
  Src = a7;
  v96 = a6;
  v100 = a8;
  v102 = a9;
  v90 = a10;
  v106 = a11;
  v107 = a12;
  v89 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 512;
  v111 = 0;
  v112 = 0;
  v113 = 512;
  v114 = 0;
  v115 = 0;
  v116 = 512;
  v88 = 0;
  v13 = -1;
  if ( (int)CorSigUncompressData(a7, 0xFFu, &v89, &v88) >= 0 )
  {
    v15 = v88;
    v14 = v89;
    v88 = v89;
  }
  else
  {
    v14 = 0;
    v88 = 0;
    v89 = 0;
    v15 = -1;
  }
  while ( (unsigned int)(v14 - 15) <= 1 || (v14 & 0x40) != 0 )
  {
    v88 = 0;
    if ( (int)CorSigUncompressData(&a7[v15], v12, &v89, &v88) >= 0 )
    {
      v16 = v88;
      v14 = v89;
    }
    else
    {
      v14 = 0;
      v89 = 0;
      v16 = -1;
    }
    v15 += v16;
  }
  v88 = v14;
  v17 = v15;
  v18 = v15 + a10;
  v19 = v102;
  v20 = CQuickMemoryBase<512,128>::ReSizeNoThrow(v102, v15 + a10);
  if ( v20 < 0 )
    return (unsigned int)v20;
  v21 = *(char **)v19;
  if ( !*(_QWORD *)v19 )
    v21 = (char *)v19 + 24;
  memmove(&v21[v90], Src, v15);
  if ( (unsigned int)v14 > 0x1B )
  {
    if ( (_DWORD)v14 == 29 )
    {
      updated = ImportHelper::MergeUpdateTokenInFieldSig(
                  v99,
                  v98,
                  v97,
                  v101,
                  a5,
                  v96,
                  (const unsigned __int8 *)Src + v15,
                  v100,
                  v19,
                  v18,
                  &v91,
                  &v92);
      goto LABEL_151;
    }
    if ( (_DWORD)v14 == 30 )
      goto LABEL_136;
    if ( (unsigned int)(v14 - 31) >= 2 )
      goto LABEL_69;
    goto LABEL_72;
  }
  switch ( (_DWORD)v14 )
  {
    case 0x1B:
      updated = ImportHelper::MergeUpdateTokenInSig(
                  v99,
                  v98,
                  v97,
                  v101,
                  a5,
                  v96,
                  (const unsigned __int8 *)Src + v15,
                  v100,
                  v19,
                  v18,
                  &v91,
                  &v92);
      goto LABEL_151;
    case 0x11:
    case 0x12:
LABEL_72:
      v89 = 0;
      if ( (int)CorSigUncompressData((const unsigned __int8 *)Src + v15, 0xFFu, &v95, &v89) >= 0 )
      {
        v93 = v89;
        v57 = v95;
      }
      else
      {
        v57 = 0;
        v93 = -1;
      }
      v58 = *((_DWORD *)&g_tkCorEncodeToken + (v57 & 3)) | (v57 >> 2);
      v59 = v58 & 0xFF000000;
      if ( v100 )
      {
        if ( v59 != 1912602624 && (v58 & 0xFFFFFF) != 0 )
        {
          if ( !MDTOKENMAP::Find(v100, v58, &v104) )
            return (unsigned int)-2146233974;
          v58 = *((_DWORD *)v104 + 2);
        }
        goto LABEL_110;
      }
      if ( v59 == 0x2000000 )
      {
        v60 = ImportHelper::ImportTypeDef(v99, v98, v97, v56, v86, v96, v58, v87, &v89);
LABEL_85:
        v20 = v60;
        if ( v60 < 0 )
          return (unsigned int)v20;
        v58 = v89;
        goto LABEL_110;
      }
      if ( v59 == 0x1000000 )
      {
        v60 = ImportHelper::ImportTypeRef(v99, v98, v97, v56, v86, v96, v58, &v89);
        goto LABEL_85;
      }
      if ( v59 != 452984832 )
      {
LABEL_110:
        v71 = v58 & 0xFFFFFF;
        v72 = v58 & 0xFF000000;
        v73 = 4 * v71;
        v74 = 4 * v71;
        switch ( v72 )
        {
          case 0x1000000u:
            v74 |= 1u;
            break;
          case 0x1B000000u:
            v74 |= 2u;
            break;
          case 0x72000000u:
            v74 |= 3u;
            break;
        }
        if ( v74 > 0x7F )
        {
          v75 = 4;
          if ( v74 <= 0x3FFF )
            v75 = 2;
        }
        else
        {
          v75 = 1;
        }
        v20 = CQuickMemoryBase<512,128>::ReSizeNoThrow(v102, v15 + v75 + v90);
        if ( v20 < 0 )
          return (unsigned int)v20;
        v76 = v102;
        v77 = *(char **)v102;
        if ( !*(_QWORD *)v102 )
          v77 = (char *)v102 + 24;
        switch ( v72 )
        {
          case 0x1000000u:
            v73 |= 1u;
            break;
          case 0x1B000000u:
            v73 |= 2u;
            break;
          case 0x72000000u:
            v73 |= 3u;
            break;
        }
        v78 = v90;
        v79 = &v77[v90];
        if ( v73 > 0x7F )
        {
          if ( v73 > 0x3FFF )
          {
            v79[v15 + 1] = BYTE2(v73);
            v79[v15 + 2] = BYTE1(v73);
            v79[v15 + 3] = v73;
            LOBYTE(v73) = HIBYTE(v73) | 0xC0;
          }
          else
          {
            v79[v15 + 1] = v73;
            LOBYTE(v73) = BYTE1(v73) | 0x80;
          }
          v78 = v90;
        }
        v79[v15] = v73;
        v15 += v93;
        v17 += v75;
        if ( v88 - 31 > 1 )
        {
LABEL_153:
          if ( v106 )
            *v106 = v15;
          *v107 = v17;
          return (unsigned int)v20;
        }
        updated = ImportHelper::MergeUpdateTokenInFieldSig(
                    v99,
                    v98,
                    v97,
                    v101,
                    a5,
                    v96,
                    (const unsigned __int8 *)Src + v15,
                    v100,
                    v76,
                    v78 + v17,
                    &v91,
                    &v92);
LABEL_151:
        v20 = updated;
        if ( updated < 0 )
          return (unsigned int)v20;
        v15 += v91;
        v17 += v92;
        goto LABEL_153;
      }
      lpMem[0] = 0;
      lpMem[1] = 0;
      lpMem[2] = (LPVOID)512;
      v61 = v96;
      v20 = (*(__int64 (__fastcall **)(struct IMetaModelCommon *, _QWORD, unsigned __int8 **, struct TOKENREC **))(*(_QWORD *)v96 + 24LL))(
              v96,
              v58,
              &v105,
              &v104);
      if ( v20 >= 0 )
      {
        v64 = v98;
        v20 = ImportHelper::MergeUpdateTokenInFieldSig(
                v99,
                v98,
                v97,
                v101,
                a5,
                v61,
                v105,
                0,
                (struct CQuickBytes *)lpMem,
                0,
                0,
                &v95);
        if ( v20 >= 0 )
        {
          v65 = v118;
          if ( lpMem[0] )
            v65 = (const unsigned __int8 *)lpMem[0];
          TypeSpec = ImportHelper::FindTypeSpec(v64, v65, v95, &v89);
          v20 = TypeSpec;
          if ( TypeSpec == -2146234064 )
          {
            v20 = CMiniMdRW::AddRecord(v64, 0x1Bu, &v103, &v89);
            if ( v20 >= 0 )
            {
              v67 = v118;
              if ( lpMem[0] )
                v67 = lpMem[0];
              v20 = CMiniMdRW::PutBlob(v64, 0x1Bu, 0, v103, v67, v95);
              if ( v20 >= 0 )
              {
                v58 = v89 | 0x1B000000;
                if ( (*((_DWORD *)v64 + 1577) & 7) != 1 )
                  goto LABEL_106;
                v20 = CMiniMdRW::AddRecord(v64, 0x1Eu, &v103, &v89);
                if ( v20 >= 0 )
                {
                  v68 = v103;
                  *(_DWORD *)v103 = v58;
                  v68[1] = 0;
                  goto LABEL_106;
                }
              }
            }
          }
          else if ( TypeSpec >= 0 )
          {
            v58 = v89;
LABEL_106:
            v69 = lpMem[0];
            if ( lpMem[0] )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v69);
              lpMem[0] = 0;
            }
            goto LABEL_110;
          }
        }
      }
      v62 = lpMem[0];
      if ( lpMem[0] )
      {
        v63 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v63 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v63;
        }
        HeapFree(v63, 0, v62);
        lpMem[0] = 0;
      }
      return (unsigned int)v20;
    case 0x13:
LABEL_136:
      v93 = 0;
      if ( (int)CorSigUncompressData((const unsigned __int8 *)Src + v15, 0xFFu, &v89, &v93) >= 0 )
      {
        v81 = v93;
        v80 = v89;
      }
      else
      {
        v80 = 0;
        v81 = -1;
      }
      v20 = CQuickMemoryBase<512,128>::ReSizeNoThrow(v19, v15 + v81 + v90);
      if ( v20 < 0 )
        return (unsigned int)v20;
      v82 = *(char **)v19;
      if ( !*(_QWORD *)v19 )
        v82 = (char *)v19 + 24;
      v83 = &v82[v90 + v15];
      if ( v80 > 0x7F )
      {
        if ( v80 > 0x3FFF )
        {
          if ( v80 > 0x1FFFFFFF )
          {
            v84 = -1;
          }
          else
          {
            *v83 = HIBYTE(v80) | 0xC0;
            v83[1] = BYTE2(v80);
            v83[2] = BYTE1(v80);
            v83[3] = v80;
            v84 = 4;
          }
        }
        else
        {
          *v83 = BYTE1(v80) | 0x80;
          v83[1] = v80;
          v84 = 2;
        }
      }
      else
      {
        *v83 = v80;
        v84 = 1;
      }
      v15 += v81;
      v17 += v84;
      goto LABEL_153;
    case 0x14:
      v20 = ImportHelper::MergeUpdateTokenInFieldSig(
              v99,
              v98,
              v97,
              v101,
              a5,
              v96,
              (const unsigned __int8 *)Src + v15,
              v100,
              v19,
              v18,
              &v91,
              &v92);
      if ( v20 < 0 )
        return (unsigned int)v20;
      v33 = v91 + v15;
      v34 = v92 + v17;
      v88 = 0;
      v35 = (const unsigned __int8 *)Src;
      v36 = (const unsigned __int8 *)Src + v33;
      if ( (int)CorSigUncompressData(v36, 0xFFu, &v89, &v88) >= 0 )
      {
        v38 = v88;
        if ( v89 )
        {
          v88 = 0;
          if ( (int)CorSigUncompressData(&v35[v38 + v33], v37, &v89, &v88) >= 0 )
          {
            v41 = v88;
            v40 = v89;
          }
          else
          {
            v40 = 0;
            v41 = -1;
          }
          v42 = v41 + v38;
          if ( v40 )
          {
            v43 = (const unsigned __int8 *)Src;
            do
            {
              v88 = 0;
              v44 = CorSigUncompressData(&v43[v42 + v33], v39, &v93, &v88);
              v45 = v88;
              if ( v44 < 0 )
                v45 = -1;
              v42 += v45;
              --v40;
            }
            while ( v40 );
            v19 = v102;
          }
          v89 = v40 - 1;
          v88 = 0;
          if ( (int)CorSigUncompressData((const unsigned __int8 *)Src + v42 + v33, v39, &v89, &v88) >= 0 )
          {
            v48 = v88;
            v47 = v89;
          }
          else
          {
            v47 = 0;
            v48 = -1;
          }
          v38 = v48 + v42;
          if ( v47 )
          {
            v49 = (const unsigned __int8 *)Src;
            do
            {
              v88 = 0;
              v50 = CorSigUncompressData(&v49[v38 + v33], v46, &v93, &v88);
              v51 = v88;
              if ( v50 < 0 )
                v51 = -1;
              v38 += v51;
              --v47;
            }
            while ( v47 );
            v19 = v102;
          }
        }
      }
      else
      {
        v38 = -1;
      }
      v52 = v90;
      v20 = CQuickMemoryBase<512,128>::ReSizeNoThrow(v19, v34 + v90 + v38);
      if ( v20 < 0 )
        return (unsigned int)v20;
      v53 = *(char **)v19;
      if ( !*(_QWORD *)v19 )
        v53 = (char *)v19 + 24;
      memmove(&v53[v34 + v52], v36, v38);
      v15 = v38 + v33;
      v17 = v38 + v34;
      goto LABEL_153;
  }
  if ( (_DWORD)v14 != 21 )
  {
LABEL_69:
    if ( (unsigned int)v14 > 0x21 )
      return (unsigned int)-2146233966;
    v55 = 0x3FF7E7FFFLL;
    if ( !_bittest64(&v55, v14) )
      return (unsigned int)-2146233966;
    goto LABEL_153;
  }
  v22 = (const unsigned __int8 *)Src;
  v20 = ImportHelper::MergeUpdateTokenInFieldSig(
          v99,
          v98,
          v97,
          v101,
          a5,
          v96,
          (const unsigned __int8 *)Src + v15,
          v100,
          v19,
          v18,
          &v91,
          &v92);
  if ( v20 < 0 )
    return (unsigned int)v20;
  v23 = v91 + v15;
  v24 = v92 + v17;
  v88 = 0;
  if ( (int)CorSigUncompressData(&v22[v23], 0xFFu, &v93, &v88) >= 0 )
  {
    v26 = v88;
    v25 = v93;
  }
  else
  {
    v25 = 0;
    v26 = -1;
  }
  v20 = CQuickMemoryBase<512,128>::ReSizeNoThrow(v19, v24 + v26 + v90);
  if ( v20 < 0 )
    return (unsigned int)v20;
  v27 = *(char **)v19;
  if ( !*(_QWORD *)v19 )
    v27 = (char *)v19 + 24;
  v28 = &v27[v24];
  v29 = v90;
  v30 = &v28[v90];
  if ( v25 <= 0x7F )
  {
    *v30 = v25;
    v13 = 1;
    goto LABEL_34;
  }
  if ( v25 > 0x3FFF )
  {
    if ( v25 > 0x1FFFFFFF )
      goto LABEL_34;
    *v30 = HIBYTE(v25) | 0xC0;
    v30[1] = BYTE2(v25);
    v30[2] = BYTE1(v25);
    v30[3] = v25;
    v13 = 4;
  }
  else
  {
    *v30 = BYTE1(v25) | 0x80;
    v30[1] = v25;
    v13 = 2;
  }
  v29 = v90;
LABEL_34:
  v15 = v26 + v23;
  v17 = v13 + v24;
  v31 = 0;
  if ( !v25 )
    goto LABEL_153;
  v32 = (const unsigned __int8 *)Src;
  while ( 1 )
  {
    v20 = ImportHelper::MergeUpdateTokenInFieldSig(
            v99,
            v98,
            v97,
            v101,
            a5,
            v96,
            &v32[v15],
            v100,
            v19,
            v17 + v29,
            &v91,
            &v92);
    if ( v20 < 0 )
      return (unsigned int)v20;
    v15 += v91;
    v17 += v92;
    ++v31;
    v29 = v90;
    if ( v31 >= v25 )
      goto LABEL_153;
  }
}

```

## disassembly

```asm
0x1800b74b4  push    rbp
0x1800b74b6  push    rbx
0x1800b74b7  push    rsi
0x1800b74b8  push    rdi
0x1800b74b9  push    r12
0x1800b74bb  push    r13
0x1800b74bd  push    r14
0x1800b74bf  push    r15
0x1800b74c1  lea     rbp, [rsp-888h]
0x1800b74c9  sub     rsp, 988h
0x1800b74d0  mov     rax, cs:__security_cookie
0x1800b74d7  xor     rax, rsp
0x1800b74da  mov     [rbp+8C0h+var_50], rax
0x1800b74e1  mov     [rbp+8C0h+var_910], r9
0x1800b74e5  mov     [rbp+8C0h+var_930], r8
0x1800b74e9  mov     [rbp+8C0h+var_928], rdx
0x1800b74ed  mov     [rbp+8C0h+var_920], rcx
0x1800b74f1  mov     rdi, [rbp+8C0h+arg_30]
0x1800b74f8  mov     [rsp+9C0h+Src], rdi
0x1800b74fd  mov     rax, [rbp+8C0h+arg_28]
0x1800b7504  mov     [rbp+8C0h+var_938], rax
0x1800b7508  mov     rax, [rbp+8C0h+arg_38]
0x1800b750f  mov     [rbp+8C0h+var_918], rax
0x1800b7513  mov     r13, [rbp+8C0h+arg_40]
0x1800b751a  mov     [rbp+8C0h+var_908], r13
0x1800b751e  mov     r12d, [rbp+8C0h+arg_48]
0x1800b7525  mov     [rsp+9C0h+var_958], r12d
0x1800b752a  mov     rax, [rbp+8C0h+arg_50]
0x1800b7531  mov     [rbp+8C0h+var_8E8], rax
0x1800b7535  mov     rax, [rbp+8C0h+arg_58]
0x1800b753c  mov     [rbp+8C0h+var_8E0], rax
0x1800b7540  xor     r14d, r14d
0x1800b7543  mov     [rsp+9C0h+var_95C], r14d
0x1800b7548  mov     [rbp+8C0h+var_8D0], r14
0x1800b754c  mov     [rbp+8C0h+var_8C8], r14
0x1800b7550  mov     eax, 200h
0x1800b7555  mov     [rbp+8C0h+var_8C0], rax
0x1800b7559  mov     [rbp+8C0h+var_6B0], r14
0x1800b7560  mov     [rbp+8C0h+var_6A8], r14
0x1800b7567  mov     [rbp+8C0h+var_6A0], rax
0x1800b756e  mov     [rbp+8C0h+var_490], r14
0x1800b7575  mov     [rbp+8C0h+var_488], r14
0x1800b757c  mov     [rbp+8C0h+var_480], rax
0x1800b7583  mov     [rsp+9C0h+var_960], r14d
0x1800b7588  lea     r9, [rsp+9C0h+var_960]; unsigned int *
0x1800b758d  lea     r8, [rsp+9C0h+var_95C]; unsigned int *
0x1800b7592  mov     edx, 0FFh; unsigned int
0x1800b7597  mov     rcx, rdi; unsigned __int8 *
0x1800b759a  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
0x1800b759f  or      r15d, 0FFFFFFFFh
0x1800b75a3  test    eax, eax
0x1800b75a5  jns     short loc_1800B75B9
0x1800b75a7  mov     esi, r14d
0x1800b75aa  mov     [rsp+9C0h+var_960], r14d
0x1800b75af  mov     [rsp+9C0h+var_95C], r14d
0x1800b75b4  mov     ebx, r15d
0x1800b75b7  jmp     short loc_1800B75C5
0x1800b75b9  mov     ebx, [rsp+9C0h+var_960]
0x1800b75bd  mov     esi, [rsp+9C0h+var_95C]
0x1800b75c1  mov     [rsp+9C0h+var_960], esi
0x1800b75c5  lea     eax, [rsi-0Fh]
0x1800b75c8  cmp     eax, 1
0x1800b75cb  jbe     short loc_1800B75D3
0x1800b75cd  test    sil, 40h
0x1800b75d1  jz      short loc_1800B7609
0x1800b75d3  mov     [rsp+9C0h+var_960], r14d
0x1800b75d8  mov     ecx, ebx
0x1800b75da  add     rcx, rdi; unsigned __int8 *
0x1800b75dd  lea     r9, [rsp+9C0h+var_960]; unsigned int *
0x1800b75e2  lea     r8, [rsp+9C0h+var_95C]; unsigned int *
0x1800b75e7  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
0x1800b75ec  test    eax, eax
0x1800b75ee  jns     short loc_1800B75FD
0x1800b75f0  mov     esi, r14d
0x1800b75f3  mov     [rsp+9C0h+var_95C], r14d
0x1800b75f8  mov     eax, r15d
0x1800b75fb  jmp     short loc_1800B7605
0x1800b75fd  mov     eax, [rsp+9C0h+var_960]
0x1800b7601  mov     esi, [rsp+9C0h+var_95C]
0x1800b7605  add     ebx, eax
0x1800b7607  jmp     short loc_1800B75C5
0x1800b7609  mov     [rsp+9C0h+var_960], esi
0x1800b760d  mov     r14d, ebx
0x1800b7610  add     r12d, ebx
0x1800b7613  mov     edx, r12d
0x1800b7616  mov     r13, [rbp+8C0h+var_908]
0x1800b761a  mov     rcx, r13
0x1800b761d  call    ?ReSizeNoThrow@?$CQuickMemoryBase@$0CAA@$0IA@@@QEAAJ_K@Z; CQuickMemoryBase<512,128>::ReSizeNoThrow(unsigned __int64)
0x1800b7622  mov     edi, eax
0x1800b7624  test    eax, eax
0x1800b7626  js      loc_1800B807D
0x1800b762c  mov     rax, [r13+0]
0x1800b7630  test    rax, rax
0x1800b7633  jnz     short loc_1800B7639
0x1800b7635  lea     rax, [r13+18h]
0x1800b7639  mov     r8d, ebx; Size
0x1800b763c  mov     ecx, [rsp+9C0h+var_958]
0x1800b7640  add     rcx, rax; void *
0x1800b7643  mov     rdx, [rsp+9C0h+Src]; Src
0x1800b7648  call    memmove
0x1800b764d  cmp     esi, 1Bh
0x1800b7650  ja      loc_1800B7A85
0x1800b7656  jz      loc_1800B7A25
0x1800b765c  mov     eax, esi
0x1800b765e  sub     eax, 11h
0x1800b7661  jz      loc_1800B7AC6
0x1800b7667  sub     eax, 1
0x1800b766a  jz      loc_1800B7AC6
0x1800b7670  sub     eax, 1
0x1800b7673  jz      loc_1800B7F34
0x1800b7679  sub     eax, 1
0x1800b767c  jz      loc_1800B7855
0x1800b7682  cmp     eax, 1
0x1800b7685  jnz     loc_1800B7AA3
0x1800b768b  mov     eax, ebx
0x1800b768d  mov     rsi, [rsp+9C0h+Src]
0x1800b7692  add     rax, rsi
0x1800b7695  lea     rcx, [rsp+9C0h+var_950]
0x1800b769a  mov     [rsp+9C0h+var_968], rcx; unsigned int *
0x1800b769f  lea     rcx, [rsp+9C0h+var_954]
0x1800b76a4  mov     [rsp+9C0h+var_970], rcx; unsigned int *
0x1800b76a9  mov     [rsp+9C0h+var_978], r12d; unsigned int
0x1800b76ae  mov     [rsp+9C0h+var_980], r13; struct CQuickBytes *
0x1800b76b3  mov     rcx, [rbp+8C0h+var_918]
0x1800b76b7  mov     [rsp+9C0h+var_988], rcx; bool
0x1800b76bc  mov     [rsp+9C0h+var_990], rax; unsigned __int8 *
0x1800b76c1  mov     rax, [rbp+8C0h+var_938]
0x1800b76c5  mov     [rsp+9C0h+var_998], rax; struct IMetaModelCommon *
0x1800b76ca  mov     eax, [rbp+8C0h+arg_20]
0x1800b76d0  mov     dword ptr [rsp+9C0h+var_9A0], eax; unsigned int
0x1800b76d4  mov     r9, [rbp+8C0h+var_910]; void *
0x1800b76d8  mov     r8, [rbp+8C0h+var_930]; struct IMetaModelCommon *
0x1800b76dc  mov     rdx, [rbp+8C0h+var_928]; struct CMiniMdRW *
0x1800b76e0  mov     rcx, [rbp+8C0h+var_920]; struct CMiniMdRW *
0x1800b76e4  call    ?MergeUpdateTokenInFieldSig@ImportHelper@@SAJPEAVCMiniMdRW@@0PEAVIMetaModelCommon@@PEBXK1PEBEPEAVMDTOKENMAP@@PEAVCQuickBytes@@KPEAK6@Z; ImportHelper::MergeUpdateTokenInFieldSig(CMiniMdRW *,CMiniMdRW *,IMetaModelCommon *,void const *,ulong,IMetaModelCommon *,uchar const *,MDTOKENMAP *,CQuickBytes *,ulong,ulong *,ulong *)
0x1800b76e9  mov     edi, eax
0x1800b76eb  test    eax, eax
0x1800b76ed  js      loc_1800B807D
0x1800b76f3  add     ebx, [rsp+9C0h+var_954]
0x1800b76f7  add     r14d, [rsp+9C0h+var_950]
0x1800b76fc  and     [rsp+9C0h+var_960], 0
0x1800b7701  mov     ecx, ebx
0x1800b7703  add     rcx, rsi; unsigned __int8 *
0x1800b7706  lea     r9, [rsp+9C0h+var_960]; unsigned int *
0x1800b770b  lea     r8, [rsp+9C0h+var_94C]; unsigned int *
0x1800b7710  mov     edx, 0FFh; unsigned int
0x1800b7715  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
0x1800b771a  test    eax, eax
0x1800b771c  jns     short loc_1800B7725
0x1800b771e  xor     esi, esi
0x1800b7720  mov     r12d, r15d
0x1800b7723  jmp     short loc_1800B772E
0x1800b7725  mov     r12d, [rsp+9C0h+var_960]
0x1800b772a  mov     esi, [rsp+9C0h+var_94C]
0x1800b772e  mov     edx, [rsp+9C0h+var_958]
0x1800b7732  add     edx, r12d
0x1800b7735  add     edx, r14d
0x1800b7738  mov     rcx, r13
0x1800b773b  call    ?ReSizeNoThrow@?$CQuickMemoryBase@$0CAA@$0IA@@@QEAAJ_K@Z; CQuickMemoryBase<512,128>::ReSizeNoThrow(unsigned __int64)
0x1800b7740  mov     edi, eax
0x1800b7742  test    eax, eax
0x1800b7744  js      loc_1800B807D
0x1800b774a  mov     rax, [r13+0]
0x1800b774e  test    rax, rax
0x1800b7751  jnz     short loc_1800B7757
0x1800b7753  lea     rax, [r13+18h]
0x1800b7757  mov     ecx, r14d
0x1800b775a  add     rcx, rax
0x1800b775d  mov     eax, [rsp+9C0h+var_958]
0x1800b7761  add     rcx, rax
0x1800b7764  cmp     esi, 7Fh
0x1800b7767  ja      short loc_1800B7774
0x1800b7769  mov     [rcx], sil
0x1800b776c  mov     r15d, 1
0x1800b7772  jmp     short loc_1800B77C0
0x1800b7774  cmp     esi, 3FFFh
0x1800b777a  ja      short loc_1800B7791
0x1800b777c  mov     eax, esi
0x1800b777e  shr     eax, 8
0x1800b7781  or      al, 80h
0x1800b7783  mov     [rcx], al
0x1800b7785  mov     [rcx+1], sil
0x1800b7789  mov     r15d, 2
0x1800b778f  jmp     short loc_1800B77BC
0x1800b7791  cmp     esi, 1FFFFFFFh
0x1800b7797  ja      short loc_1800B77C0
0x1800b7799  mov     eax, esi
0x1800b779b  shr     eax, 18h
0x1800b779e  or      al, 0C0h
0x1800b77a0  mov     [rcx], al
0x1800b77a2  mov     eax, esi
0x1800b77a4  shr     eax, 10h
0x1800b77a7  mov     [rcx+1], al
0x1800b77aa  mov     eax, esi
0x1800b77ac  shr     eax, 8
0x1800b77af  mov     [rcx+2], al
0x1800b77b2  mov     [rcx+3], sil
0x1800b77b6  mov     r15d, 4
0x1800b77bc  mov     eax, [rsp+9C0h+var_958]
0x1800b77c0  add     ebx, r12d
0x1800b77c3  add     r14d, r15d
0x1800b77c6  xor     r15d, r15d
0x1800b77c9  test    esi, esi
0x1800b77cb  jz      loc_1800B806B
0x1800b77d1  mov     r12, [rsp+9C0h+Src]
0x1800b77d6  add     eax, r14d
0x1800b77d9  mov     ecx, ebx
0x1800b77db  add     rcx, r12
0x1800b77de  lea     rdx, [rsp+9C0h+var_950]
0x1800b77e3  mov     [rsp+9C0h+var_968], rdx; unsigned int *
0x1800b77e8  lea     rdx, [rsp+9C0h+var_954]
0x1800b77ed  mov     [rsp+9C0h+var_970], rdx; unsigned int *
0x1800b77f2  mov     [rsp+9C0h+var_978], eax; unsigned int
0x1800b77f6  mov     [rsp+9C0h+var_980], r13; struct CQuickBytes *
0x1800b77fb  mov     rax, [rbp+8C0h+var_918]
0x1800b77ff  mov     [rsp+9C0h+var_988], rax; struct MDTOKENMAP *
0x1800b7804  mov     [rsp+9C0h+var_990], rcx; unsigned __int8 *
0x1800b7809  mov     rax, [rbp+8C0h+var_938]
0x1800b780d  mov     [rsp+9C0h+var_998], rax; struct IMetaModelCommon *
0x1800b7812  mov     eax, [rbp+8C0h+arg_20]
0x1800b7818  mov     dword ptr [rsp+9C0h+var_9A0], eax; unsigned int
0x1800b781c  mov     r9, [rbp+8C0h+var_910]; void *
0x1800b7820  mov     r8, [rbp+8C0h+var_930]; struct IMetaModelCommon *
0x1800b7824  mov     rdx, [rbp+8C0h+var_928]; struct CMiniMdRW *
0x1800b7828  mov     rcx, [rbp+8C0h+var_920]; struct CMiniMdRW *
0x1800b782c  call    ?MergeUpdateTokenInFieldSig@ImportHelper@@SAJPEAVCMiniMdRW@@0PEAVIMetaModelCommon@@PEBXK1PEBEPEAVMDTOKENMAP@@PEAVCQuickBytes@@KPEAK6@Z; ImportHelper::MergeUpdateTokenInFieldSig(CMiniMdRW *,CMiniMdRW *,IMetaModelCommon *,void const *,ulong,IMetaModelCommon *,uchar const *,MDTOKENMAP *,CQuickBytes *,ulong,ulong *,ulong *)
0x1800b7831  mov     edi, eax
0x1800b7833  test    eax, eax
0x1800b7835  js      loc_1800B807D
0x1800b783b  add     ebx, [rsp+9C0h+var_954]
0x1800b783f  add     r14d, [rsp+9C0h+var_950]
0x1800b7844  inc     r15d
0x1800b7847  cmp     r15d, esi
0x1800b784a  mov     eax, [rsp+9C0h+var_958]
0x1800b784e  jb      short loc_1800B77D6
0x1800b7850  jmp     loc_1800B806B
0x1800b7855  mov     eax, ebx
0x1800b7857  add     rax, [rsp+9C0h+Src]
0x1800b785c  lea     rcx, [rsp+9C0h+var_950]
0x1800b7861  mov     [rsp+9C0h+var_968], rcx; unsigned int *
0x1800b7866  lea     rcx, [rsp+9C0h+var_954]
0x1800b786b  mov     [rsp+9C0h+var_970], rcx; unsigned int *
0x1800b7870  mov     [rsp+9C0h+var_978], r12d; unsigned int
0x1800b7875  mov     [rsp+9C0h+var_980], r13; struct CQuickBytes *
0x1800b787a  mov     rcx, [rbp+8C0h+var_918]
0x1800b787e  mov     [rsp+9C0h+var_988], rcx; struct MDTOKENMAP *
0x1800b7883  mov     [rsp+9C0h+var_990], rax; unsigned __int8 *
0x1800b7888  mov     rax, [rbp+8C0h+var_938]
0x1800b788c  mov     [rsp+9C0h+var_998], rax; struct IMetaModelCommon *
0x1800b7891  mov     eax, [rbp+8C0h+arg_20]
0x1800b7897  mov     dword ptr [rsp+9C0h+var_9A0], eax; unsigned int
0x1800b789b  mov     r9, [rbp+8C0h+var_910]; void *
0x1800b789f  mov     r8, [rbp+8C0h+var_930]; struct IMetaModelCommon *
0x1800b78a3  mov     rdx, [rbp+8C0h+var_928]; struct CMiniMdRW *
0x1800b78a7  mov     rcx, [rbp+8C0h+var_920]; struct CMiniMdRW *
0x1800b78ab  call    ?MergeUpdateTokenInFieldSig@ImportHelper@@SAJPEAVCMiniMdRW@@0PEAVIMetaModelCommon@@PEBXK1PEBEPEAVMDTOKENMAP@@PEAVCQuickBytes@@KPEAK6@Z; ImportHelper::MergeUpdateTokenInFieldSig(CMiniMdRW *,CMiniMdRW *,IMetaModelCommon *,void const *,ulong,IMetaModelCommon *,uchar const *,MDTOKENMAP *,CQuickBytes *,ulong,ulong *,ulong *)
0x1800b78b0  mov     edi, eax
0x1800b78b2  test    eax, eax
0x1800b78b4  js      loc_1800B807D
0x1800b78ba  add     ebx, [rsp+9C0h+var_954]
0x1800b78be  add     r14d, [rsp+9C0h+var_950]
0x1800b78c3  and     [rsp+9C0h+var_960], 0
0x1800b78c8  mov     r12d, ebx
0x1800b78cb  mov     rdi, [rsp+9C0h+Src]
0x1800b78d0  add     r12, rdi
0x1800b78d3  lea     r9, [rsp+9C0h+var_960]; unsigned int *
0x1800b78d8  lea     r8, [rsp+9C0h+var_95C]; unsigned int *
0x1800b78dd  mov     edx, 0FFh; unsigned int
0x1800b78e2  mov     rcx, r12; unsigned __int8 *
0x1800b78e5  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
0x1800b78ea  test    eax, eax
0x1800b78ec  jns     short loc_1800B78F6
0x1800b78ee  mov     esi, r15d
0x1800b78f1  jmp     loc_1800B79DC
0x1800b78f6  mov     esi, [rsp+9C0h+var_960]
0x1800b78fa  cmp     [rsp+9C0h+var_95C], 0
0x1800b78ff  jz      loc_1800B79DC
0x1800b7905  and     [rsp+9C0h+var_960], 0
0x1800b790a  lea     ecx, [rsi+rbx]
0x1800b790d  add     rcx, rdi; unsigned __int8 *
0x1800b7910  lea     r9, [rsp+9C0h+var_960]; unsigned int *
0x1800b7915  lea     r8, [rsp+9C0h+var_95C]; unsigned int *
0x1800b791a  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
0x1800b791f  test    eax, eax
0x1800b7921  jns     short loc_1800B792A
0x1800b7923  xor     edi, edi
0x1800b7925  mov     eax, r15d
0x1800b7928  jmp     short loc_1800B7932
0x1800b792a  mov     eax, [rsp+9C0h+var_960]
0x1800b792e  mov     edi, [rsp+9C0h+var_95C]
0x1800b7932  add     esi, eax
0x1800b7934  test    edi, edi
0x1800b7936  jz      short loc_1800B796C
0x1800b7938  mov     r13, [rsp+9C0h+Src]
0x1800b793d  and     [rsp+9C0h+var_960], 0
0x1800b7942  lea     ecx, [rsi+rbx]
0x1800b7945  add     rcx, r13; unsigned __int8 *
0x1800b7948  lea     r9, [rsp+9C0h+var_960]; unsigned int *
0x1800b794d  lea     r8, [rsp+9C0h+var_94C]; unsigned int *
0x1800b7952  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
  ... truncated ...
```
