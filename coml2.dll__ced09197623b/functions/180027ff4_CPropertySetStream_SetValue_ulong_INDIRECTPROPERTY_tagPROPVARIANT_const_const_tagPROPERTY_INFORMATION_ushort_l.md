# CPropertySetStream::SetValue(ulong,_INDIRECTPROPERTY * *,tagPROPVARIANT const * const,tagPROPERTY_INFORMATION *,ushort *,long *)

- ea: `0x180027ff4`
- end: `0x180028cd3`
- name: `?SetValue@CPropertySetStream@@QEAAXKPEAPEAU_INDIRECTPROPERTY@@QEBUtagPROPVARIANT@@PEAUtagPROPERTY_INFORMATION@@PEAGPEAJ@Z`
- size: `3295`
- prototype: `void __usercall(CPropertySetStream *__hidden this@<rcx>, unsigned int@<edx>, struct _INDIRECTPROPERTY **@<r8>, const struct tagPROPVARIANT *const@<r9>, struct tagPROPERTY_INFORMATION *, unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180025f10`
- `0x180027128`

## callees

- `0x180026d5c`
- `0x1800273f8`
- `0x180027690`
- `0x18002773c`
- `0x18002780c`
- `0x180027ff4`
- `0x180028cdc`
- `0x180029c28`
- `0x18002c284`
- `0x18002d8b4`
- `0x180034f64`
- `0x180038d54`
- `0x180042800`
- `0x180043100`
- `0x18005a7e8`
- `0x18005a9d8`
- `0x18005ab40`
- `0x18006141c`
- `0x180061428`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800282a9`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800282a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028a07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028a07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028c75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028c75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028cc0`

## pseudocode

```c
void __fastcall CPropertySetStream::SetValue(
        CPropertySetStream *this,
        unsigned int a2,
        struct _INDIRECTPROPERTY **a3,
        const struct tagPROPVARIANT *const a4,
        struct tagPROPERTY_INFORMATION *a5,
        unsigned __int16 *a6,
        int *a7)
{
  struct tagPROPERTY_INFORMATION *v8; // r15
  unsigned int v9; // r13d
  void **v10; // r12
  unsigned int v11; // edx
  SHORT v12; // ax
  char *v13; // rcx
  unsigned __int8 v14; // dl
  int v15; // esi
  unsigned __int8 v16; // cl
  int v17; // r10d
  __int64 v18; // rsi
  __int64 v19; // r14
  struct CStreamChunk *FreeChunk; // rax
  unsigned int *v21; // rcx
  unsigned int v22; // r14d
  size_t v23; // r8
  unsigned int v24; // esi
  unsigned int v25; // r15d
  unsigned int v26; // eax
  int v27; // ecx
  unsigned int *v28; // r12
  unsigned int v29; // edx
  struct CStreamChunk *v30; // rdx
  int v31; // r13d
  int v32; // r13d
  int v33; // esi
  unsigned int v34; // r14d
  __int64 v35; // rdx
  int v36; // ecx
  int v37; // esi
  struct tagPROPERTY_INFORMATION *v38; // r13
  struct CStreamChunk *v39; // rax
  size_t v40; // rdx
  void *v41; // rcx
  unsigned int v42; // r12d
  char v43; // r13
  unsigned int v44; // r15d
  struct tagSERIALIZEDPROPERTYVALUE *Property; // rax
  unsigned __int16 v46; // dx
  const struct tagPROPVARIANT *v47; // rcx
  struct tagSERIALIZEDPROPERTYVALUE *v48; // rax
  __int64 v49; // rcx
  __int64 v50; // r13
  unsigned int v51; // r12d
  __int64 v52; // rsi
  unsigned int v53; // edx
  unsigned __int8 IsLocalizationSettable; // al
  unsigned __int16 *v55; // rcx
  SHORT v56; // ax
  struct tagSERIALIZEDPROPERTYVALUE *v57; // r15
  struct tagSERIALIZEDPROPERTYVALUE *v58; // rax
  struct tagPROPERTY_INFORMATION *v59; // r8
  unsigned int i; // edx
  unsigned int v61; // r14d
  int *v62; // rsi
  VARTYPE vt; // cx
  __int64 v64; // rax
  unsigned __int64 v65; // rax
  unsigned int v66; // esi
  void *v67; // rax
  void **v68; // r13
  unsigned int v69; // r12d
  unsigned int v70; // edx
  struct tagSERIALIZEDPROPERTYVALUE *v71; // rax
  unsigned int *rgb; // rsi
  void *v73; // rbx
  LPVOID *v74; // rsi
  int v75; // eax
  struct CStreamChunk *v76; // rax
  unsigned int v77; // edx
  unsigned __int16 *v78; // rsi
  unsigned __int16 v79; // r8
  int v80; // r14d
  unsigned int v81; // r15d
  void *v82; // rax
  __int64 v83; // rax
  VARTYPE v84; // cx
  unsigned int v85; // eax
  unsigned int v86; // ecx
  unsigned int v87; // ecx
  unsigned int v88; // edx
  unsigned int v89; // edx
  struct CStreamChunk *v90; // rdx
  int v91; // edi
  int v92; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v93[2]; // [rsp+54h] [rbp-ACh] BYREF
  int v94; // [rsp+58h] [rbp-A8h]
  unsigned int v95; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v96; // [rsp+60h] [rbp-A0h]
  unsigned int v97; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v98; // [rsp+68h] [rbp-98h]
  struct tagPROPERTY_INFORMATION *v99; // [rsp+70h] [rbp-90h]
  unsigned int v100; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v101; // [rsp+7Ch] [rbp-84h] BYREF
  SHORT iVal; // [rsp+80h] [rbp-80h]
  int v103; // [rsp+84h] [rbp-7Ch]
  unsigned int v104; // [rsp+88h] [rbp-78h]
  unsigned int v105; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int *v106; // [rsp+90h] [rbp-70h]
  const struct tagPROPVARIANT *v107; // [rsp+98h] [rbp-68h]
  struct _INDIRECTPROPERTY **v108; // [rsp+A0h] [rbp-60h]
  unsigned int v109; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD NumOfElements[3]; // [rsp+ACh] [rbp-54h]
  char v111; // [rsp+B8h] [rbp-48h]
  int v112; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v113; // [rsp+C8h] [rbp-38h] BYREF
  struct CStreamChunk *v114; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v115; // [rsp+D8h] [rbp-28h]
  char v116; // [rsp+E0h] [rbp-20h] BYREF

  v8 = a5;
  v9 = a2;
  v96 = a2;
  v10 = (void **)a3;
  v11 = a2 + 2;
  v115 = a6;
  v12 = *((_WORD *)this + 8);
  *a7 = 0;
  v13 = &v116;
  if ( v11 > 6 )
    v13 = 0;
  v109 = v11;
  v14 = *((_BYTE *)this + 19);
  v15 = 0;
  *(_QWORD *)&NumOfElements[1] = v13;
  v16 = *((_BYTE *)this + 18);
  v107 = a4;
  v108 = a3;
  v99 = a5;
  v92 = 0;
  iVal = v12;
  NumOfElements[0] = 0;
  v111 = 0;
  if ( IsReadOnlyPropertySet(v16, v14) )
  {
    *a7 = -1073741790;
    goto LABEL_127;
  }
  (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 120LL))(*((_QWORD *)this + 5), a7);
  v17 = 0;
  if ( *a7 < 0 )
  {
LABEL_127:
    if ( !v10 || !v15 )
      return;
    if ( v9 == 1 )
    {
      v73 = v10;
      v74 = v10;
    }
    else
    {
      v73 = *v10;
      if ( !*v10 )
        goto LABEL_204;
      v74 = (LPVOID *)*v10;
    }
    v91 = v17;
    if ( v92 > 0 )
    {
      do
        CoTaskMemFree(v74[2 * (unsigned int)v91++ + 1]);
      while ( v91 < v92 );
    }
    if ( v9 == 1 )
      return;
LABEL_204:
    CoTaskMemFree(v73);
    *v10 = 0;
    return;
  }
  v18 = *((int *)this + 2);
  v19 = *(_QWORD *)this;
  FreeChunk = CStreamChunkList::GetFreeChunk((CStreamChunkList *)&v109, a7);
  v17 = 0;
  v114 = FreeChunk;
  if ( *a7 < 0 )
  {
LABEL_132:
    v15 = 0;
    goto LABEL_68;
  }
  *(_QWORD *)FreeChunk = 0;
  if ( v9 > 0x200000 )
  {
    *a7 = -1073741811;
    goto LABEL_132;
  }
  v21 = (unsigned int *)(v19 + v18);
  v112 = *((_DWORD *)this + 7);
  v22 = 0;
  v105 = *((_DWORD *)this + 2);
  v104 = *v21;
  v106 = v21;
  v101 = 0;
  v97 = 0;
  *(_DWORD *)v93 = 0;
  v98 = 0;
  v94 = 0;
  v103 = 0;
  while ( 1 )
  {
    v23 = 2;
    if ( v22 >= v9 )
      break;
    v50 = v22;
    v51 = 0;
    v100 = 0;
    v52 = 3LL * v22;
    v53 = *((_DWORD *)v8 + 3 * v22);
    if ( v53 - 2 > 0x7FFFFFFD && v53 < 0xC0000000 )
    {
      if ( v96 != 1 || *(_DWORD *)v8 || !*((_DWORD *)v8 + 1) || !v107 || v107->vt != 0x1FFF )
      {
        if ( v53 != 1 && v53 != 0x80000000 )
          goto LABEL_66;
        if ( v22 )
        {
          if ( v22 != 1 || *(_DWORD *)v8 != 1 && *(_DWORD *)v8 != 0x80000000 )
            goto LABEL_66;
        }
        else
        {
          IsLocalizationSettable = CPropertySetStream::_IsLocalizationSettable(this, a7);
          v17 = 0;
          if ( *a7 < 0 )
            goto LABEL_67;
          if ( !IsLocalizationSettable
            || (LOWORD(v23) = 2, v96 != 1)
            && (v96 != 2 || *((_DWORD *)v8 + 3) != 1 && *((_DWORD *)v8 + 3) != 0x80000000) )
          {
LABEL_66:
            *a7 = -1073741811;
            goto LABEL_67;
          }
        }
      }
      v53 = *((_DWORD *)v8 + 3 * v22);
      if ( v53 == 1 && v107 )
      {
        if ( (_WORD)v23 != v107[v22].vt )
          goto LABEL_66;
        iVal = v107[v22].iVal;
LABEL_82:
        v58 = CPropertySetStream::_LoadProperty(this, v53, &v100, a7);
        v17 = 0;
        v57 = v58;
        if ( *a7 < 0 )
          goto LABEL_67;
        v51 = v100;
        goto LABEL_84;
      }
      if ( v53 == 0x80000000 && v107 && v107[v22].vt != 19 )
        goto LABEL_66;
    }
    v57 = 0;
    if ( v53 != -1 )
      goto LABEL_82;
LABEL_84:
    v59 = v99;
    v95 = ++v22;
    for ( i = v22; ; ++i )
    {
      if ( i >= v96 )
      {
        if ( i != v96 )
          goto LABEL_89;
        v61 = *((_DWORD *)v99 + v52 + 1);
        if ( v61 <= 0x200000 )
        {
          if ( v57 )
          {
            if ( v61 )
            {
              v62 = (int *)((char *)v99 + 4 * v52 + 8);
              if ( v51 == v61 )
              {
                ++v101;
                *v62 = 5;
                goto LABEL_96;
              }
              v103 += v61;
              v75 = 4;
              ++v97;
            }
            else
            {
              ++v98;
              v75 = 2;
              v61 = 0;
              v62 = (int *)((char *)v99 + 4 * v52 + 8);
            }
            *v62 = v75;
            v76 = CStreamChunkList::GetFreeChunk((CStreamChunkList *)&v109, a7);
            v17 = 0;
            if ( *a7 < 0 )
              goto LABEL_67;
            *(_DWORD *)v76 = (_DWORD)v57 - *((_DWORD *)this + 2) - *(_DWORD *)this;
            *((_DWORD *)v76 + 1) = -v51;
LABEL_96:
            v94 += v61 - v51;
          }
          else
          {
            v62 = (int *)((char *)v99 + 4 * v52 + 8);
            if ( v61 )
            {
              v103 += v61;
              v94 += v61;
              ++*(_DWORD *)v93;
              *v62 = 3;
            }
            else
            {
              *v62 = 1;
            }
          }
          v10 = (void **)v108;
          if ( v108 && *v62 != 1 )
          {
            if ( v57 && (v57->dwType - 66 <= 3 || v57->dwType == 73)
              || v107 && ((vt = v107[v50].vt, (unsigned __int16)(vt - 66) <= 3u) || vt == 73) )
            {
              ++v92;
            }
          }
          v22 = v95;
          v8 = v99;
          goto LABEL_90;
        }
LABEL_149:
        *a7 = -1073741697;
        goto LABEL_67;
      }
      if ( *((_DWORD *)v99 + 3 * i) == *((_DWORD *)v99 + v52) )
        break;
    }
    *((_DWORD *)v99 + v52 + 2) = 1;
LABEL_89:
    v10 = (void **)v108;
    v8 = v59;
LABEL_90:
    v9 = v96;
  }
  if ( !v10 || (v15 = v92) == 0 )
  {
LABEL_10:
    v24 = v98;
    v25 = 0;
    if ( *(_DWORD *)v93 <= v98 )
    {
      if ( *(_DWORD *)v93 < v98 )
      {
        v85 = CPropertySetStream::_CountFreePropertyOffsets(this, a7);
        v17 = 0;
        v23 = v85;
        if ( *a7 < 0 )
          goto LABEL_67;
        v28 = v106;
        v86 = v24;
        v33 = *(_DWORD *)v93;
        v87 = v86 - *(_DWORD *)v93;
        if ( (*((_BYTE *)this + 19) & 0x10) == 0 )
        {
          v88 = 90;
          if ( v106[1] - v87 < 0x5A )
            v88 = v106[1] - v87;
          v89 = v88 / 0xA + 1;
          if ( v87 + v85 <= v89 )
          {
            v32 = v94;
            goto LABEL_22;
          }
          v87 = v85 + v87 - v89;
        }
        v32 = v94;
        if ( v87 )
        {
          v90 = v114;
          v23 = v106[1] + v85 - v87;
          *(_DWORD *)v114 = 8 * v23 + 8;
          *((_DWORD *)v90 + 1) = -8 * v87;
          v32 -= 8 * v87;
          v94 = v32;
        }
        goto LABEL_22;
      }
      v28 = v106;
      v32 = v94;
    }
    else
    {
      v26 = CPropertySetStream::_CountFreePropertyOffsets(this, a7);
      v17 = 0;
      if ( *a7 < 0 )
        goto LABEL_67;
      v23 = *(_DWORD *)v93 - v24;
      if ( v26 <= *(_DWORD *)v93 - v24 )
        v23 = v26;
      v27 = *(_DWORD *)v93 - v24 - v23;
      if ( (unsigned int)(v27 - 1) > 1 || (_DWORD)v23 )
      {
        v28 = v106;
      }
      else
      {
        v28 = v106;
        if ( (*((_BYTE *)this + 19) & 0x10) == 0 )
        {
          v29 = 90;
          if ( v106[1] < 0x5A )
            v29 = v106[1];
          v25 = v29 / 0xA + 1;
          v27 += v25;
        }
      }
      v30 = v114;
      v31 = v94;
      *(_DWORD *)v114 = 8 * (v23 + v28[1]) + 8;
      v32 = 8 * v27 + v31;
      *((_DWORD *)v30 + 1) = 8 * v27;
      v94 = v32;
    }
    v33 = *(_DWORD *)v93;
LABEL_22:
    v34 = v105 + v104 + v112;
    v104 = v34;
    if ( v32 > 0 )
    {
      v35 = v34 + v32;
      if ( (unsigned int)v35 > 0x200000 )
        goto LABEL_149;
      LOBYTE(v23) = 1;
      (*(void (__fastcall **)(_QWORD, __int64, size_t, CPropertySetStream *, int *))(**((_QWORD **)this + 5) + 80LL))(
        *((_QWORD *)this + 5),
        v35,
        v23,
        this,
        a7);
      v17 = 0;
      if ( *a7 < 0 )
        goto LABEL_67;
      v36 = *((_DWORD *)this + 7);
      v28 = (unsigned int *)(*(_QWORD *)this + *((int *)this + 2));
      if ( v36 )
      {
        memmove_0(
          (void *)((int)(v34 - v36) + *(_QWORD *)this + v32),
          (const void *)((int)(v34 - v36) + *(_QWORD *)this),
          *((unsigned int *)this + 7));
        v17 = 0;
      }
    }
    v37 = v97 + v33;
    if ( v37 + v98 )
    {
      v38 = v99;
      if ( v97 + v98 )
      {
        CPropertySetStream::_DeleteMovePropertyOffsets(this, v99, v96, a7);
        v17 = 0;
        if ( *a7 < 0 )
          goto LABEL_67;
        v28[1] -= v98;
      }
      v39 = CStreamChunkList::GetFreeChunk((CStreamChunkList *)&v109, a7);
      v17 = 0;
      if ( *a7 < 0 )
        goto LABEL_67;
      v40 = NumOfElements[0];
      *(_DWORD *)v39 = *v28;
      v41 = *(void **)&NumOfElements[1];
      *((_DWORD *)v39 + 1) = 0;
      qsort(v41, v40, 8u, fnChunkCompare);
      if ( v98 > *(_DWORD *)v93 )
      {
        CPropertySetStream::_UpdatePropertyOffsets(this, (const struct CStreamChunkList *)&v109, a7);
        v17 = 0;
        if ( *a7 < 0 )
          goto LABEL_67;
      }
      CPropertySetStream::_CompactStream(this, (const struct CStreamChunkList *)&v109);
      if ( v98 > *(_DWORD *)v93 )
      {
        v17 = 0;
      }
      else
      {
        CPropertySetStream::_UpdatePropertyOffsets(this, (const struct CStreamChunkList *)&v109, a7);
        v17 = 0;
        if ( *a7 < 0 )
          goto LABEL_67;
      }
      *v28 += v94;
      if ( v37 )
      {
        CPropertySetStream::_InsertMovePropertyOffsets(this, v38, v96, *v28 - v103, v25, a7);
        v17 = 0;
        if ( *a7 < 0 )
          goto LABEL_67;
        v28[1] += *(_DWORD *)v93;
      }
      v23 = *((unsigned int *)this + 7);
      if ( (_DWORD)v23 )
      {
        if ( v94 < 0 )
          memmove_0(
            (void *)(*(_QWORD *)this + (int)(v34 - v23) + v94),
            (const void *)(*(_QWORD *)this + (int)(v34 - v23)),
            v23);
        CPropertySetStream::_PatchSectionOffsets(this, v94);
        v17 = 0;
      }
    }
    if ( *(_DWORD *)v93 + v101 + v97 )
    {
      v42 = 0;
      v43 = *((_BYTE *)this + 19) & 0x18;
      while ( 1 )
      {
        if ( v42 >= v96 )
        {
          v34 = v104;
          break;
        }
        if ( (unsigned int)(*((_DWORD *)v99 + 3 * v42 + 2) - 3) <= 2 )
        {
          v44 = *((_DWORD *)v99 + 3 * v42);
          v97 = 0;
          v105 = 0;
          Property = CPropertySetStream::_LoadProperty(this, v44, 0, a7);
          v17 = 0;
          v23 = (size_t)Property;
          if ( *a7 < 0 )
            goto LABEL_67;
          if ( !v44 )
          {
            Property->dwType = 0;
            goto LABEL_49;
          }
          v46 = 0;
          v93[0] = 0;
          v97 = *((_DWORD *)v99 + 3 * v42 + 1);
          v47 = &v107[v42];
          if ( v47->vt )
          {
            v48 = VariantToProperty_Worker(
                    v47,
                    *((_WORD *)this + 8),
                    Property,
                    &v97,
                    *((_DWORD *)v99 + 3 * v42),
                    0,
                    0,
                    &v105,
                    v93,
                    a7);
            v46 = v93[0];
            v23 = (size_t)v48;
            v17 = 0;
          }
          else
          {
            v97 = 0;
          }
          if ( *a7 < 0 )
            goto LABEL_67;
          v49 = *(_QWORD *)this;
          if ( *(_WORD *)(*(_QWORD *)this + 2LL) > v46 )
            v46 = *(_WORD *)(v49 + 2);
          *(_WORD *)(v49 + 2) = v46;
          if ( v43 == 8 && *((_WORD *)this + 8) != 1200 )
          {
            v101 = v97;
            if ( v44 == 12 )
            {
              CPropertySetStream::_FixHeadingPairVector(this, 1, v23, &v101);
            }
            else
            {
              if ( v44 != 13 )
                goto LABEL_49;
              CPropertySetStream::_FixDocPartsVector(this, 1, v23, &v101);
            }
            v17 = 0;
          }
        }
LABEL_49:
        ++v42;
      }
    }
    if ( v94 >= 0
      || (LOBYTE(v23) = 1,
          (*(void (__fastcall **)(_QWORD, _QWORD, size_t, CPropertySetStream *, int *))(**((_QWORD **)this + 5) + 80LL))(
            *((_QWORD *)this + 5),
            v34 + v94,
            v23,
            this,
            a7),
          v17 = 0,
          *a7 >= 0) )
    {
      v55 = v115;
      v15 = v92;
      if ( v115 )
      {
        v56 = iVal;
        *((_WORD *)this + 8) = iVal;
        *v55 = v56;
      }
      goto LABEL_68;
    }
LABEL_67:
    v15 = v92;
    goto LABEL_68;
  }
  if ( v9 == 1 )
  {
    v68 = v10;
    *(_OWORD *)v10 = 0;
    goto LABEL_116;
  }
  v64 = (unsigned int)(v92 + 1);
  if ( (unsigned int)v64 >= v92 )
  {
    v65 = 16 * v64;
    if ( v65 <= 0xFFFFFFFF )
    {
      v66 = v65;
      v67 = CoTaskMemAlloc((unsigned int)v65);
      v17 = 0;
      *v10 = v67;
      v68 = (void **)v67;
      if ( !v67 )
      {
LABEL_153:
        *a7 = -1073741670;
        goto LABEL_67;
      }
      memset_0(v67, 0, v66);
      v17 = 0;
      LODWORD(v68[2 * v92]) = -1;
LABEL_116:
      v100 = 0;
      v69 = 0;
      while ( 2 )
      {
        if ( v69 >= v96 )
          goto LABEL_10;
        v95 = 0;
        if ( *((_DWORD *)v8 + 3 * v69 + 2) == 1 )
          goto LABEL_167;
        v70 = *((_DWORD *)v8 + 3 * v69);
        if ( v70 == -1 )
          goto LABEL_167;
        v71 = CPropertySetStream::_LoadProperty(this, v70, &v95, a7);
        v17 = 0;
        if ( *a7 < 0 )
          goto LABEL_67;
        if ( !v71 )
        {
          v23 = 73;
          goto LABEL_169;
        }
        if ( v71->dwType - 66 <= 3 )
        {
          if ( v95 < 8 )
            goto LABEL_173;
          rgb = (unsigned int *)v71->rgb;
LABEL_156:
          v77 = *rgb;
          v78 = (unsigned __int16 *)(rgb + 1);
          v79 = *((_WORD *)this + 8);
          v95 = v77;
          v113 = v78;
          if ( v79 == 1200 )
          {
            if ( v78[((unsigned __int64)v77 >> 1) - 1] )
              goto LABEL_173;
            v80 = 0;
          }
          else
          {
            if ( *((_BYTE *)v78 + v77 - 1) )
            {
LABEL_173:
              *a7 = -1073741596;
              goto LABEL_67;
            }
            PrpConvertToUnicode((LPCCH)v78, v77, v79, &v113, &v95, a7);
            v17 = 0;
            if ( *a7 < 0 )
              goto LABEL_67;
            v78 = v113;
            v80 = 1;
            v77 = v95;
          }
          v81 = v77;
          v82 = CoTaskMemAlloc(v77);
          v17 = 0;
          v68[2 * (int)v100 + 1] = v82;
          if ( !v82 )
            goto LABEL_153;
          memcpy_0(v82, v78, v81);
          v17 = 0;
          if ( v80 )
          {
            CoTaskMemFree(v78);
            v17 = 0;
          }
          v8 = v99;
        }
        else
        {
          v23 = 73;
          if ( v71->dwType == 73 )
          {
            if ( v95 < 0x18 )
              goto LABEL_173;
            rgb = (unsigned int *)v71[2].rgb;
            goto LABEL_156;
          }
LABEL_169:
          if ( !v107 || (v84 = v107[v69].vt, (unsigned __int16)(v84 - 66) > 3u) && v84 != 73 )
          {
LABEL_167:
            ++v69;
            continue;
          }
        }
        break;
      }
      v83 = 2LL * (int)v100++;
      LODWORD(v68[v83]) = v69;
      goto LABEL_167;
    }
  }
  *a7 = -2147483643;
LABEL_68:
  if ( v111 )
  {
    CoTaskMemFree(*(LPVOID *)&NumOfElements[1]);
    v17 = 0;
  }
  v10 = (void **)v108;
  v9 = v96;
  if ( *a7 < 0 )
    goto LABEL_127;
}

```

## disassembly

```asm
0x180027ff4  mov     [rsp-8+arg_8], rbx
0x180027ff9  push    rbp
0x180027ffa  push    rsi
0x180027ffb  push    rdi
0x180027ffc  push    r12
0x180027ffe  push    r13
0x180028000  push    r14
0x180028002  push    r15
0x180028004  lea     rbp, [rsp-20h]
0x180028009  sub     rsp, 120h
0x180028010  mov     rax, cs:__security_cookie
0x180028017  xor     rax, rsp
0x18002801a  mov     [rbp+50h+var_40], rax
0x18002801e  mov     rax, [rbp+50h+arg_28]
0x180028025  xor     r10d, r10d
0x180028028  mov     rbx, [rbp+50h+arg_30]
0x18002802f  mov     rdi, rcx
0x180028032  mov     r15, [rbp+50h+arg_20]
0x180028039  mov     r13d, edx
0x18002803c  mov     [rsp+150h+var_F0], edx
0x180028040  mov     r12, r8
0x180028043  add     edx, 2
0x180028046  mov     [rbp+50h+var_78], rax
0x18002804a  movzx   eax, word ptr [rcx+10h]
0x18002804e  cmp     edx, 6
0x180028051  mov     [rbx], r10d
0x180028054  lea     rcx, [rbp+50h+var_70]
0x180028058  cmova   rcx, r10
0x18002805c  mov     [rbp+50h+var_A8], edx
0x18002805f  mov     dl, [rdi+13h]; unsigned __int8
0x180028062  mov     esi, r10d
0x180028065  mov     qword ptr [rbp+50h+NumOfElements+4], rcx
0x180028069  mov     cl, [rdi+12h]; unsigned __int8
0x18002806c  mov     [rbp+50h+var_B8], r9
0x180028070  mov     [rbp+50h+var_B0], r8
0x180028074  mov     [rsp+150h+var_E0], r15
0x180028079  mov     [rsp+150h+var_100], r10d
0x18002807e  mov     [rbp+50h+var_D0], ax
0x180028082  mov     dword ptr [rbp+50h+NumOfElements], r10d
0x180028086  mov     [rbp+50h+var_98], r10b
0x18002808a  call    ?IsReadOnlyPropertySet@@YAEEE@Z; IsReadOnlyPropertySet(uchar,uchar)
0x18002808f  test    al, al
0x180028091  jnz     loc_18002881C
0x180028097  mov     rcx, [rdi+28h]
0x18002809b  mov     rdx, rbx
0x18002809e  mov     rax, [rcx]
0x1800280a1  mov     rax, [rax+78h]
0x1800280a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280aa  xor     r10d, r10d
0x1800280ad  cmp     [rbx], r10d
0x1800280b0  jl      loc_180028822
0x1800280b6  movsxd  rsi, dword ptr [rdi+8]
0x1800280ba  lea     rcx, [rbp+50h+var_A8]; this
0x1800280be  mov     r14, [rdi]
0x1800280c1  mov     rdx, rbx; int *
0x1800280c4  call    ?GetFreeChunk@CStreamChunkList@@QEAAPEAUCStreamChunk@@PEAJ@Z; CStreamChunkList::GetFreeChunk(long *)
0x1800280c9  xor     r10d, r10d
0x1800280cc  mov     [rbp+50h+var_80], rax
0x1800280d0  cmp     [rbx], r10d
0x1800280d3  jl      loc_18002884E
0x1800280d9  mov     [rax], r10
0x1800280dc  cmp     r13d, 200000h
0x1800280e3  ja      loc_180028848
0x1800280e9  mov     eax, [rdi+1Ch]
0x1800280ec  lea     rcx, [r14+rsi]
0x1800280f0  mov     [rbp+50h+var_90], eax
0x1800280f3  mov     r14d, r10d
0x1800280f6  mov     eax, [rdi+8]
0x1800280f9  mov     [rbp+50h+var_C4], eax
0x1800280fc  mov     eax, [rcx]
0x1800280fe  mov     [rbp+50h+var_C8], eax
0x180028101  mov     [rbp+50h+var_C0], rcx
0x180028105  mov     [rsp+150h+var_D4], r10d
0x18002810a  mov     [rsp+150h+var_EC], r10d
0x18002810f  mov     dword ptr [rsp+150h+var_FC], r10d
0x180028114  mov     [rsp+150h+var_E8], r10d
0x180028119  mov     [rsp+150h+var_F8], r10d
0x18002811e  mov     [rbp+50h+var_CC], r10d
0x180028122  mov     r9d, 0FFFFFFFFh
0x180028128  mov     r8d, 2
0x18002812e  cmp     r14d, r13d
0x180028131  jb      loc_180028457
0x180028137  mov     r14d, 4B0h
0x18002813d  test    r12, r12
0x180028140  jnz     loc_180028953
0x180028146  mov     esi, [rsp+150h+var_E8]
0x18002814a  mov     r15d, r10d
0x18002814d  cmp     dword ptr [rsp+150h+var_FC], esi
0x180028151  jbe     loc_18002855D
0x180028157  mov     rdx, rbx; int *
0x18002815a  mov     rcx, rdi; this
0x18002815d  call    ?_CountFreePropertyOffsets@CPropertySetStream@@AEAAKPEAJ@Z; CPropertySetStream::_CountFreePropertyOffsets(long *)
0x180028162  xor     r10d, r10d
0x180028165  cmp     [rbx], r10d
0x180028168  jl      loc_180028516
0x18002816e  mov     ecx, dword ptr [rsp+150h+var_FC]
0x180028172  sub     ecx, esi
0x180028174  cmp     eax, ecx
0x180028176  mov     r8d, ecx
0x180028179  cmovbe  r8d, eax
0x18002817d  sub     ecx, r8d
0x180028180  lea     eax, [rcx-1]
0x180028183  cmp     eax, 1
0x180028186  ja      loc_1800285AA
0x18002818c  test    r8d, r8d
0x18002818f  jnz     loc_1800285AA
0x180028195  test    byte ptr [rdi+13h], 10h
0x180028199  mov     r12, [rbp+50h+var_C0]
0x18002819d  jnz     short loc_1800281BF
0x18002819f  lea     edx, [r10+5Ah]
0x1800281a3  mov     eax, 0CCCCCCCDh
0x1800281a8  cmp     [r12+4], edx
0x1800281ad  cmovb   edx, [r12+4]
0x1800281b3  mul     edx
0x1800281b5  shr     edx, 3
0x1800281b8  lea     r15d, [rdx+1]
0x1800281bc  add     ecx, r15d
0x1800281bf  mov     eax, [r12+4]
0x1800281c4  mov     rdx, [rbp+50h+var_80]
0x1800281c8  add     eax, r8d
0x1800281cb  mov     r13d, [rsp+150h+var_F8]
0x1800281d0  lea     eax, ds:8[rax*8]
0x1800281d7  mov     [rdx], eax
0x1800281d9  lea     eax, ds:0[rcx*8]
0x1800281e0  add     r13d, eax
0x1800281e3  mov     [rdx+4], eax
0x1800281e6  mov     [rsp+150h+var_F8], r13d
0x1800281eb  mov     esi, dword ptr [rsp+150h+var_FC]
0x1800281ef  mov     r14d, [rbp+50h+var_90]
0x1800281f3  add     r14d, [rbp+50h+var_C8]
0x1800281f7  add     r14d, [rbp+50h+var_C4]
0x1800281fb  mov     [rbp+50h+var_C8], r14d
0x1800281ff  test    r13d, r13d
0x180028202  jle     short loc_180028250
0x180028204  lea     edx, [r14+r13]
0x180028208  cmp     edx, 200000h
0x18002820e  ja      loc_180028948
0x180028214  mov     rcx, [rdi+28h]
0x180028218  mov     r9, rdi
0x18002821b  mov     r8b, 1
0x18002821e  mov     [rsp+150h+var_130], rbx
0x180028223  mov     rax, [rcx]
0x180028226  mov     rax, [rax+50h]
0x18002822a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002822f  xor     r10d, r10d
0x180028232  cmp     [rbx], r10d
0x180028235  jl      loc_180028516
0x18002823b  mov     rdx, [rdi]
0x18002823e  movsxd  r12, dword ptr [rdi+8]
0x180028242  mov     ecx, [rdi+1Ch]
0x180028245  add     r12, rdx
0x180028248  test    ecx, ecx
0x18002824a  jnz     loc_180028B47
0x180028250  mov     edx, [rsp+150h+var_EC]
0x180028254  add     esi, edx
0x180028256  mov     ecx, [rsp+150h+var_E8]
0x18002825a  lea     eax, [rsi+rcx]
0x18002825d  test    eax, eax
0x18002825f  jz      loc_180028342
0x180028265  mov     r13, [rsp+150h+var_E0]
0x18002826a  lea     eax, [rdx+rcx]
0x18002826d  test    eax, eax
0x18002826f  jnz     loc_180028B67
0x180028275  mov     rdx, rbx; int *
0x180028278  lea     rcx, [rbp+50h+var_A8]; this
0x18002827c  call    ?GetFreeChunk@CStreamChunkList@@QEAAPEAUCStreamChunk@@PEAJ@Z; CStreamChunkList::GetFreeChunk(long *)
0x180028281  xor     r10d, r10d
0x180028284  cmp     [rbx], r10d
0x180028287  jl      loc_180028516
0x18002828d  mov     ecx, [r12]
0x180028291  lea     r9, ?fnChunkCompare@@YAHPEBX0@Z; CompareFunction
0x180028298  mov     edx, dword ptr [rbp+50h+NumOfElements]; NumOfElements
0x18002829b  lea     r8d, [r10+8]; SizeOfElements
0x18002829f  mov     [rax], ecx
0x1800282a1  mov     rcx, qword ptr [rbp+50h+NumOfElements+4]; Base
0x1800282a5  mov     [rax+4], r10d
0x1800282a9  call    cs:__imp_qsort
0x1800282af  mov     ecx, dword ptr [rsp+150h+var_FC]
0x1800282b3  cmp     [rsp+150h+var_E8], ecx
0x1800282b7  ja      loc_180028B94
0x1800282bd  lea     rdx, [rbp+50h+var_A8]; struct CStreamChunkList *
0x1800282c1  mov     rcx, rdi; this
0x1800282c4  call    ?_CompactStream@CPropertySetStream@@AEAAXPEBVCStreamChunkList@@@Z; CPropertySetStream::_CompactStream(CStreamChunkList const *)
0x1800282c9  mov     eax, dword ptr [rsp+150h+var_FC]
0x1800282cd  cmp     [rsp+150h+var_E8], eax
0x1800282d1  ja      loc_180028571
0x1800282d7  mov     r8, rbx; int *
0x1800282da  lea     rdx, [rbp+50h+var_A8]; struct CStreamChunkList *
0x1800282de  mov     rcx, rdi; this
0x1800282e1  call    ?_UpdatePropertyOffsets@CPropertySetStream@@AEAAXPEBVCStreamChunkList@@PEAJ@Z; CPropertySetStream::_UpdatePropertyOffsets(CStreamChunkList const *,long *)
0x1800282e6  xor     r10d, r10d
0x1800282e9  cmp     [rbx], r10d
0x1800282ec  jl      loc_180028516
0x1800282f2  mov     eax, [rsp+150h+var_F8]
0x1800282f6  add     [r12], eax
0x1800282fa  mov     r9d, [r12]
0x1800282fe  test    esi, esi
0x180028300  jz      short loc_180028335
0x180028302  sub     r9d, [rbp+50h+var_CC]; unsigned int
0x180028306  mov     rdx, r13; struct tagPROPERTY_INFORMATION *
0x180028309  mov     r8d, [rsp+150h+var_F0]; unsigned int
0x18002830e  mov     rcx, rdi; this
0x180028311  mov     [rsp+150h+var_128], rbx; int *
0x180028316  mov     dword ptr [rsp+150h+var_130], r15d; unsigned int
0x18002831b  call    ?_InsertMovePropertyOffsets@CPropertySetStream@@AEAAXPEBUtagPROPERTY_INFORMATION@@KKKPEAJ@Z; CPropertySetStream::_InsertMovePropertyOffsets(tagPROPERTY_INFORMATION const *,ulong,ulong,ulong,long *)
0x180028320  xor     r10d, r10d
0x180028323  cmp     [rbx], r10d
0x180028326  jl      loc_180028516
0x18002832c  mov     eax, dword ptr [rsp+150h+var_FC]
0x180028330  add     [r12+4], eax
0x180028335  mov     r8d, [rdi+1Ch]; Size
0x180028339  test    r8d, r8d
0x18002833c  jnz     loc_180028BB4
0x180028342  mov     eax, [rsp+150h+var_EC]
0x180028346  add     eax, [rsp+150h+var_D4]
0x18002834a  add     eax, dword ptr [rsp+150h+var_FC]
0x18002834e  jz      loc_180028579
0x180028354  mov     r13b, [rdi+13h]
0x180028358  mov     r12d, r10d
0x18002835b  and     r13b, 18h
0x18002835f  cmp     r12d, [rsp+150h+var_F0]
0x180028364  jnb     loc_180028C39
0x18002836a  mov     r9, [rsp+150h+var_E0]
0x18002836f  mov     esi, r12d
0x180028372  lea     r14, [rsi+rsi*2]
0x180028376  mov     eax, [r9+r14*4+8]
0x18002837b  sub     eax, 3
0x18002837e  cmp     eax, 2
0x180028381  ja      loc_18002844F
0x180028387  mov     r15d, [r9+r14*4]
0x18002838b  xor     r8d, r8d; unsigned int *
0x18002838e  mov     r9, rbx; int *
0x180028391  mov     [rsp+150h+var_EC], r10d
0x180028396  mov     edx, r15d; unsigned int
0x180028399  mov     [rbp+50h+var_C4], r10d
0x18002839d  mov     rcx, rdi; this
0x1800283a0  call    ?_LoadProperty@CPropertySetStream@@AEAAPEAUtagSERIALIZEDPROPERTYVALUE@@KPEAKPEAJ@Z; CPropertySetStream::_LoadProperty(ulong,ulong *,long *)
0x1800283a5  xor     r10d, r10d
0x1800283a8  mov     r8, rax; struct tagSERIALIZEDPROPERTYVALUE *
0x1800283ab  cmp     [rbx], r10d
0x1800283ae  jl      loc_180028516
0x1800283b4  test    r15d, r15d
0x1800283b7  jz      loc_1800285A2
0x1800283bd  mov     r9, [rsp+150h+var_E0]
0x1800283c2  mov     edx, r10d
0x1800283c5  mov     rcx, [rbp+50h+var_B8]
0x1800283c9  mov     [rsp+150h+var_FC], dx
0x1800283ce  mov     eax, [r9+r14*4+4]
0x1800283d3  mov     [rsp+150h+var_EC], eax
0x1800283d7  lea     rax, [rsi+rsi*2]
0x1800283db  lea     rcx, [rcx+rax*8]; struct tagPROPVARIANT *
0x1800283df  cmp     [rcx], r10w
0x1800283e3  jz      loc_1800285B3
0x1800283e9  movzx   edx, word ptr [rdi+10h]; unsigned __int16
0x1800283ed  lea     rax, [rsp+150h+var_FC]
0x1800283f2  mov     [rsp+150h+var_108], rbx; int *
0x1800283f7  mov     [rsp+150h+var_110], rax; unsigned __int16 *
0x1800283fc  lea     rax, [rbp+50h+var_C4]
0x180028400  mov     [rsp+150h+var_118], rax; unsigned int *
0x180028405  mov     eax, [r9+r14*4]
0x180028409  lea     r9, [rsp+150h+var_EC]; unsigned int *
0x18002840e  mov     [rsp+150h+var_120], r10b; char
0x180028413  mov     byte ptr [rsp+150h+var_128], r10b; char
0x180028418  mov     dword ptr [rsp+150h+var_130], eax; unsigned int
0x18002841c  call    ?VariantToProperty_Worker@@YAPEAUtagSERIALIZEDPROPERTYVALUE@@PEBUtagPROPVARIANT@@GPEAU1@PEAKKEE2PEAGPEAJ@Z; VariantToProperty_Worker(tagPROPVARIANT const *,ushort,tagSERIALIZEDPROPERTYVALUE *,ulong *,ulong,uchar,uchar,ulong *,ushort *,long *)
0x180028421  movzx   edx, [rsp+150h+var_FC]
0x180028426  mov     r8, rax
0x180028429  xor     r10d, r10d
0x18002842c  cmp     [rbx], r10d
0x18002842f  jl      loc_180028516
0x180028435  mov     rcx, [rdi]
0x180028438  cmp     [rcx+2], dx
0x18002843c  cmova   dx, [rcx+2]
0x180028441  mov     [rcx+2], dx
0x180028445  cmp     r13b, 8
0x180028449  jz      loc_180028BE6
0x18002844f  inc     r12d
0x180028452  jmp     loc_18002835F
0x180028457  mov     r13d, r14d
0x18002845a  mov     r12d, r10d
0x18002845d  mov     [rsp+150h+var_D8], r10d
0x180028462  lea     rsi, ds:0[r13*2]
0x18002846a  add     rsi, r13
0x18002846d  mov     edx, [r15+rsi*4]; unsigned int
0x180028471  lea     eax, [rdx-2]
0x180028474  cmp     eax, 7FFFFFFDh
0x180028479  jbe     loc_1800285BD
0x18002847f  cmp     edx, 0C0000000h
0x180028485  jnb     loc_1800285BD
0x18002848b  cmp     [rsp+150h+var_F0], 1
0x180028490  jnz     short loc_1800284B4
0x180028492  cmp     [r15], r10d
0x180028495  jnz     short loc_1800284B4
0x180028497  cmp     [r15+4], r10d
0x18002849b  jz      short loc_1800284B4
0x18002849d  mov     rax, [rbp+50h+var_B8]
0x1800284a1  test    rax, rax
0x1800284a4  jz      short loc_1800284B4
0x1800284a6  mov     ecx, 1FFFh
0x1800284ab  cmp     [rax], cx
  ... truncated ...
```
