# CPropertySetStream::SetPropertyNames(ulong,ulong const *,ushort const * const * const,long *)

- ea: `0x180025f10`
- end: `0x1800269b9`
- name: `?SetPropertyNames@CPropertySetStream@@QEAAXKPEBKQEBQEBGPEAJ@Z`
- size: `2729`
- prototype: `void __usercall(CPropertySetStream *__hidden this@<rcx>, unsigned int@<edx>, const unsigned int *@<r8>, const unsigned __int16 *const *const@<r9>, int *)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002495c`
- `0x180059670`

## callees

- `0x180025db8`
- `0x180025f10`
- `0x180026ae8`
- `0x180026b94`
- `0x18002780c`
- `0x180027ff4`
- `0x180029c28`
- `0x180029dec`
- `0x180031c14`
- `0x180042800`
- `0x180043100`
- `0x18005ab40`
- `0x18005ab78`
- `0x18006141c`
- `0x180061428`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800266dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800266dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002680c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002680c`

## pseudocode

```c
void __fastcall CPropertySetStream::SetPropertyNames(
        CPropertySetStream *this,
        unsigned int a2,
        const unsigned int *a3,
        const unsigned __int16 **a4,
        int *a5)
{
  unsigned __int8 v8; // dl
  unsigned __int8 v9; // cl
  __int64 v10; // r8
  const unsigned int *v11; // r9
  signed int v12; // r11d
  const unsigned __int16 **v13; // r12
  unsigned int v14; // r13d
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // r14d
  unsigned __int16 v19; // cx
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // rbx
  char *v23; // r8
  __int64 v24; // rax
  int v25; // eax
  struct tagPROPERTYIDOFFSET *v26; // r14
  unsigned int j; // ebx
  struct tagPROPERTYIDOFFSET *v28; // rax
  char v29; // r9
  int v30; // r13d
  unsigned int v31; // r15d
  struct tagENTRY *v32; // rbx
  unsigned int k; // r14d
  unsigned int v34; // eax
  const WCHAR *v35; // r9
  __int64 v36; // rax
  int v37; // edx
  int v38; // eax
  struct tagENTRY *DictionaryEntry; // rax
  unsigned __int8 v40; // al
  __int64 v41; // r8
  int v42; // ecx
  int v43; // r13d
  int v44; // r15d
  unsigned int v45; // r13d
  int v46; // eax
  unsigned int v47; // r15d
  int v48; // ebx
  char *v49; // r15
  char *v50; // rdx
  char *v51; // r14
  signed int v52; // ebx
  unsigned int m; // eax
  unsigned int n; // r13d
  signed int v55; // eax
  unsigned int v56; // ecx
  signed int v57; // eax
  unsigned int v58; // edx
  __int64 v59; // r15
  unsigned int jj; // r14d
  unsigned int v61; // r9d
  __int64 kk; // rbx
  unsigned int v63; // r13d
  const unsigned __int16 *v64; // rdx
  char *v65; // r9
  unsigned __int8 v66; // al
  struct tagPROPERTYSECTIONHEADER *v67; // rax
  struct tagPROPERTYSECTIONHEADER *v68; // r8
  unsigned int v69; // r8d
  const unsigned __int16 *v70; // rcx
  __int64 v71; // rax
  unsigned int v72; // ebx
  unsigned int v73; // eax
  const WCHAR *v74; // r9
  __int64 v75; // rax
  int v76; // edx
  int v77; // eax
  __int64 v78; // rax
  __int64 v79; // rdx
  size_t v80; // rbx
  struct tagPROPERTYIDOFFSET *ii; // rcx
  unsigned __int8 v82; // al
  const unsigned __int16 **v83; // rax
  unsigned int i; // ebx
  unsigned int v85; // ebx
  const unsigned __int16 **v86; // r12
  unsigned __int8 v87; // al
  bool v88; // zf
  unsigned int v89; // edx
  unsigned int v90; // [rsp+20h] [rbp-91h]
  char v91; // [rsp+40h] [rbp-71h]
  char v92; // [rsp+41h] [rbp-70h]
  char v93; // [rsp+42h] [rbp-6Fh]
  unsigned int v94; // [rsp+44h] [rbp-6Dh]
  char v95; // [rsp+48h] [rbp-69h]
  unsigned int v96; // [rsp+4Ch] [rbp-65h] BYREF
  unsigned int v97; // [rsp+50h] [rbp-61h]
  struct tagPROPERTYIDOFFSET *v98; // [rsp+58h] [rbp-59h] BYREF
  const unsigned __int16 **v99; // [rsp+60h] [rbp-51h]
  const unsigned int *v100; // [rsp+68h] [rbp-49h]
  int v101; // [rsp+70h] [rbp-41h]
  signed int v102; // [rsp+74h] [rbp-3Dh]
  void *Src; // [rsp+78h] [rbp-39h] BYREF
  unsigned int v104; // [rsp+80h] [rbp-31h]
  signed int v105; // [rsp+84h] [rbp-2Dh]
  signed int v106; // [rsp+88h] [rbp-29h]
  _DWORD Size[3]; // [rsp+8Ch] [rbp-25h]
  const unsigned __int16 *const *v108; // [rsp+98h] [rbp-19h]
  struct tagPROPVARIANT v109; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v110; // [rsp+B8h] [rbp+7h] BYREF
  int v111; // [rsp+C0h] [rbp+Fh]

  v108 = a4;
  v100 = a3;
  v98 = 0;
  *a5 = 0;
  v8 = *((_BYTE *)this + 19);
  v9 = *((_BYTE *)this + 18);
  v94 = a2;
  v96 = 0;
  if ( IsReadOnlyPropertySet(v9, v8) )
  {
    *a5 = -1073741790;
    return;
  }
  *(_QWORD *)&Size[1] = a4;
  v13 = a4;
  if ( a4 && *((_WORD *)this + 8) != 1200 )
  {
    v80 = 8 * v10;
    if ( (unsigned __int64)(8 * v10) > 0xFFFFFFFF )
    {
      *a5 = -2147483643;
      return;
    }
    v83 = (const unsigned __int16 **)CoTaskMemAlloc((unsigned int)v80);
    *(_QWORD *)&Size[1] = v83;
    v13 = v83;
    if ( !v83 )
    {
      *a5 = -1073741670;
      return;
    }
    memset_0(v83, 0, v80);
    LODWORD(v10) = v94;
    v12 = 0;
    for ( i = 0; i < (unsigned int)v10; ++i )
    {
      if ( v100[i] != -1 )
      {
        v13[i] = 0;
        CPropertySetStream::_WideCharToMultiByte(this, a4[i], v10, *((_WORD *)this + 8), (char **)&v13[i], a5);
        LODWORD(v10) = v94;
        v12 = 0;
        if ( *a5 < 0 )
          goto LABEL_148;
      }
    }
    v11 = v100;
  }
  v99 = v13;
  v14 = v12;
  v92 = v12;
  v93 = v12;
  v95 = v12;
  v97 = v12;
  v102 = v12;
  while ( v14 < (unsigned int)v10 )
  {
    if ( v13 )
    {
      if ( v11[v14] != -1 )
      {
        v15 = v13[v14];
        v16 = -1;
        if ( *((_WORD *)this + 8) == 1200 )
        {
          do
            ++v16;
          while ( v15[v16] != (_WORD)v12 );
          v17 = v16 + 1;
          v18 = 2 * v17;
        }
        else
        {
          do
            ++v16;
          while ( *((_BYTE *)v15 + v16) != (_BYTE)v12 );
          v17 = v16 + 1;
          v18 = v17;
        }
        HIBYTE(v19) = BYTE1(v12);
        LOBYTE(v19) = v17 > 0x100;
        if ( *((_WORD *)this + 8) == 1200 )
          v20 = v18 == 2;
        else
          v20 = v18 == 1;
        if ( v20 )
        {
          *a5 = -1073741811;
          goto LABEL_148;
        }
        v21 = *(_QWORD *)this;
        v22 = v14 + 1;
        if ( *(_WORD *)(*(_QWORD *)this + 2LL) > v19 )
          v19 = *(_WORD *)(v21 + 2);
        *(_WORD *)(v21 + 2) = v19;
        while ( (unsigned int)v22 < (unsigned int)v10 )
        {
          if ( v11[v22] == v11[v14] )
          {
            v92 = 1;
            goto LABEL_26;
          }
          v23 = (char *)v13[v22];
          v24 = -1;
          if ( *((_WORD *)this + 8) == 1200 )
          {
            do
              ++v24;
            while ( *(_WORD *)&v23[2 * v24] != (_WORD)v12 );
            v25 = 2 * v24 + 2;
          }
          else
          {
            do
              ++v24;
            while ( v23[v24] != (_BYTE)v12 );
            v25 = v24 + 1;
          }
          if ( v18 == v25 )
          {
            v40 = CPropertySetStream::_ComparePropertyNames(this, v13[v14], v23, (int)v11, v90, a5);
            v11 = v100;
            v12 = 0;
            if ( v40 )
            {
              LODWORD(v10) = v94;
              v93 = 1;
              goto LABEL_26;
            }
          }
          LODWORD(v10) = v94;
          if ( *a5 < v12 )
            goto LABEL_149;
          v22 = (unsigned int)(v22 + 1);
        }
        if ( (_DWORD)v22 == (_DWORD)v10 )
        {
          ++v102;
          v58 = v18 + v97 + 8;
          v97 = v58;
          if ( *((_WORD *)this + 8) == 1200 )
            v97 = (v58 + 3) & 0xFFFFFFFC;
        }
        v12 = 0;
      }
    }
    else if ( v11[v14] == v12 )
    {
      if ( (_DWORD)v10 != 1 )
      {
        *a5 = -1073741811;
        return;
      }
      v95 = 1;
    }
LABEL_26:
    ++v14;
  }
  (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 120LL))(*((_QWORD *)this + 5), a5);
  v12 = 0;
  if ( *a5 >= 0 )
  {
    v26 = v98;
    for ( j = 0; j <= 2; ++j )
    {
      v110 = 0;
      v111 = 0;
      memset(&v109, 0, sizeof(v109));
      if ( j >= 2 )
      {
        *a5 = -1073741596;
        goto LABEL_84;
      }
      v28 = (struct tagPROPERTYIDOFFSET *)CPropertySetStream::_LoadProperty(this, 0, &v96, a5);
      v12 = 0;
      v98 = v28;
      v26 = v28;
      if ( *a5 < 0 )
        goto LABEL_84;
      if ( v28 )
        break;
      LODWORD(v10) = v94;
      if ( !v94 )
        goto LABEL_85;
      if ( !v13 )
        return;
      v109.vt = 0x1FFF;
      v110 = 0x400000000LL;
      CPropertySetStream::SetValue(this, 1u, 0, &v109, (struct tagPROPERTY_INFORMATION *)&v110, 0, a5);
      v12 = 0;
      if ( *a5 < 0 )
      {
LABEL_159:
        LODWORD(v10) = v94;
        goto LABEL_148;
      }
      *a5 = 0;
    }
    v29 = 0;
    v91 = 0;
    v30 = 0;
    v101 = 0;
    v31 = 0;
    v32 = (struct tagPROPERTYIDOFFSET *)((char *)v26 + 4);
    while ( v31 < *(_DWORD *)v26 )
    {
      LODWORD(v10) = v94;
      for ( k = v12; k < (unsigned int)v10; ++k )
      {
        v34 = v100[k];
        if ( v34 != -1 )
        {
          if ( v95 != (_BYTE)v12 || v34 == *(_DWORD *)v32 )
            goto LABEL_127;
          if ( v13 )
          {
            v35 = v13[k];
            v36 = -1;
            if ( *((_WORD *)this + 8) == 1200 )
            {
              do
                ++v36;
              while ( v35[v36] != (_WORD)v12 );
              v37 = 2 * v36 + 2;
            }
            else
            {
              do
                ++v36;
              while ( *((_BYTE *)v35 + v36) != (_BYTE)v12 );
              v37 = v36 + 1;
            }
            v38 = 2 * *((_DWORD *)v32 + 1);
            if ( *((_WORD *)this + 8) != 1200 )
              v38 = *((_DWORD *)v32 + 1);
            if ( v37 == v38 )
            {
              v82 = CPropertySetStream::_ComparePropertyNames(this, v35, (char *)v32 + 8, (int)v35, v90, a5);
              v12 = 0;
              if ( v82 )
              {
                v91 = 1;
LABEL_127:
                ++v101;
                v30 += CPropertySetStream::_DictionaryEntryLength(this, v32);
                break;
              }
              LODWORD(v10) = v94;
            }
            if ( *a5 < v12 )
              goto LABEL_148;
          }
        }
      }
      ++v31;
      DictionaryEntry = CPropertySetStream::_NextDictionaryEntry(this, v32);
      v26 = v98;
      v32 = DictionaryEntry;
    }
    v41 = *((int *)this + 2);
    v42 = v97 - v30;
    v43 = (_DWORD)v26 - *(_QWORD *)this;
    v44 = *((_DWORD *)this + 7) + *(_DWORD *)(v41 + *(_QWORD *)this);
    v105 = (v96 + 3) & 0xFFFFFFFC;
    v45 = v43 - v41;
    v106 = (v42 + v96 + 3) & 0xFFFFFFFC;
    v46 = v44 + v41;
    v104 = v45;
    LODWORD(v99) = v44 + v41;
    v47 = v44 - v105 - v45;
    v48 = v106 - v105;
    v97 = v106 - v105;
    Size[0] = v47;
    if ( v106 - v105 <= 0 )
      goto LABEL_53;
    v79 = (unsigned int)(v46 + v48);
    if ( (unsigned int)v79 > 0x200000 )
    {
      *a5 = -1073741697;
      goto LABEL_84;
    }
    LOBYTE(v41) = 1;
    v90 = (unsigned int)a5;
    (*(void (__fastcall **)(_QWORD, __int64, __int64, CPropertySetStream *))(**((_QWORD **)this + 5) + 80LL))(
      *((_QWORD *)this + 5),
      v79,
      v41,
      this);
    v12 = 0;
    if ( *a5 >= 0 )
    {
      v98 = (struct tagPROPERTYIDOFFSET *)(*(_QWORD *)this + (int)v45 + (__int64)*((int *)this + 2));
      v26 = v98;
      memmove_0((char *)v26 + v106, (char *)v26 + v105, v47);
      v29 = v91;
      v12 = 0;
LABEL_53:
      v49 = (char *)v26 + 4;
      if ( v95 == (_BYTE)v12 )
      {
        v50 = (char *)v26 + 4;
        v51 = (char *)v26 + 4;
        Src = v49;
        v52 = v12;
        for ( m = v12; ; m = v96 + 1 )
        {
          v96 = m;
          if ( m >= *(_DWORD *)v98 )
            break;
          LODWORD(v10) = v94;
          for ( n = v12; n < (unsigned int)v10 && v100[n] != *(_DWORD *)v49; ++n )
          {
            if ( v29 )
            {
              v74 = v13[n];
              v75 = -1;
              if ( *((_WORD *)this + 8) == 1200 )
              {
                do
                  ++v75;
                while ( v74[v75] != (_WORD)v12 );
                v76 = 2 * v75 + 2;
              }
              else
              {
                do
                  ++v75;
                while ( *((_BYTE *)v74 + v75) != (_BYTE)v12 );
                v76 = v75 + 1;
              }
              v77 = 2 * *((_DWORD *)v49 + 1);
              if ( *((_WORD *)this + 8) != 1200 )
                v77 = *((_DWORD *)v49 + 1);
              if ( v76 == v77 )
              {
                v87 = CPropertySetStream::_ComparePropertyNames(this, v74, v49 + 8, (int)v74, v90, a5);
                LODWORD(v10) = v94;
                v12 = 0;
                if ( v87 )
                  break;
              }
              if ( *a5 < v12 )
                goto LABEL_85;
              v29 = v91;
            }
          }
          v55 = v12;
          LOBYTE(v55) = *((_WORD *)this + 8) == 1200;
          v56 = *((_DWORD *)v49 + 1) * (v55 + 1) + 8;
          if ( *((_WORD *)this + 8) == 1200 )
          {
            v57 = (*((_DWORD *)v49 + 1) * (v55 + 1) + 11) & 0xFFFFFFFC;
            v56 = (v56 + 3) & 0xFFFFFFFC;
          }
          else
          {
            v57 = *((_DWORD *)v49 + 1) * (v55 + 1) + 8;
          }
          v49 += v57;
          if ( n == (_DWORD)v10 )
          {
            v50 = (char *)Src;
            v52 += v56;
          }
          else
          {
            if ( v52 )
            {
              if ( Src != v51 )
              {
                memmove_0(v51, Src, (unsigned int)v52);
                v12 = 0;
              }
              v78 = v52;
              v52 = v12;
              v51 += v78;
            }
            v50 = v49;
            Src = v49;
          }
          v29 = v91;
        }
        if ( v52 && v50 != v51 )
        {
          memmove_0(v51, v50, (unsigned int)v52);
          v12 = 0;
        }
        v45 = v104;
        v59 = v52;
        v48 = v97;
        v49 = &v51[v59];
        v26 = v98;
      }
      *(_DWORD *)v26 -= v101;
      if ( !v13 )
      {
LABEL_83:
        memset_0(v49, 0, ((_DWORD)v26 - (_DWORD)v49) & 3);
        v98 = 0;
        Src = 0;
        v67 = CPropertySetStream::_LoadPropertyOffsetPointers(this, &v98, (struct tagPROPERTYIDOFFSET **)&Src, a5);
        v12 = 0;
        v68 = v67;
        if ( *a5 >= 0 )
        {
          for ( ii = v98; ii < Src; ii = (struct tagPROPERTYIDOFFSET *)((char *)ii + 8) )
          {
            v89 = *((_DWORD *)ii + 1);
            if ( v89 > v45 )
              *((_DWORD *)ii + 1) = v89 + v48;
          }
          *(_DWORD *)v67 += v48;
          if ( v48 < 0 )
          {
            memmove_0((char *)v26 + v106, (char *)v26 + v105, Size[0]);
            v12 = 0;
          }
          if ( *((_DWORD *)this + 7) )
            CPropertySetStream::_PatchSectionOffsets(this, v48);
          if ( v48 < 0 )
          {
            LOBYTE(v68) = 1;
            (*(void (__fastcall **)(_QWORD, _QWORD, struct tagPROPERTYSECTIONHEADER *, CPropertySetStream *, int *))(**((_QWORD **)this + 5) + 80LL))(
              *((_QWORD *)this + 5),
              (unsigned int)(v48 + (_DWORD)v99),
              v68,
              this,
              a5);
            v12 = 0;
          }
        }
        goto LABEL_84;
      }
      for ( jj = v12; ; ++jj )
      {
        v61 = v94;
        if ( jj >= v94 )
        {
          v26 = v98;
          v48 = v97;
          v45 = v104;
          *(_DWORD *)v98 += v102;
          goto LABEL_83;
        }
        if ( v92 == (_BYTE)v12 )
          break;
        kk = jj + 1;
        v88 = (_DWORD)kk == v94;
        if ( (unsigned int)kk >= v94 )
        {
LABEL_87:
          if ( !v88 )
            goto LABEL_88;
          goto LABEL_76;
        }
        while ( v100[kk] != v100[jj] )
        {
          kk = (unsigned int)(kk + 1);
          v88 = (_DWORD)kk == v94;
          if ( (unsigned int)kk >= v94 )
            goto LABEL_87;
        }
LABEL_88:
        v69 = v100[jj];
        if ( v69 != -1 && (_DWORD)kk == v61 )
        {
          v70 = v13[jj];
          v71 = -1;
          if ( *((_WORD *)this + 8) == 1200 )
          {
            do
              ++v71;
            while ( v70[v71] != (_WORD)v12 );
            v72 = 2 * v71 + 2;
          }
          else
          {
            do
              ++v71;
            while ( *((_BYTE *)v70 + v71) != (_BYTE)v12 );
            v72 = v71 + 1;
          }
          *(_DWORD *)v49 = v69;
          v73 = v72 >> 1;
          if ( *((_WORD *)this + 8) != 1200 )
            v73 = v72;
          *((_DWORD *)v49 + 1) = v73;
          memcpy_0(v49 + 8, v13[jj], v72);
          memset_0(&v49[v72 + 8], 0, -((_DWORD)v49 + v72) & 3);
          v49 += (int)CPropertySetStream::_DictionaryEntryLength(this, (const struct tagENTRY *)v49);
        }
        v12 = 0;
      }
      LODWORD(kk) = v94;
LABEL_76:
      if ( v93 != (_BYTE)v12 )
      {
        v96 = v12;
        CPropertySetStream::_PropertyNameLength(this, v13[jj], &v96);
        v63 = v96;
        for ( kk = jj + 1; (unsigned int)kk < v61; kk = (unsigned int)(kk + 1) )
        {
          v64 = v13[kk];
          v96 = v12;
          CPropertySetStream::_PropertyNameLength(this, v64, &v96);
          if ( v63 == v96 )
          {
            v66 = CPropertySetStream::_ComparePropertyNames(this, v13[jj], v65, (int)v65, v90, a5);
            v12 = 0;
            if ( v66 )
            {
              v61 = v94;
              goto LABEL_88;
            }
          }
          if ( *a5 < v12 )
            goto LABEL_159;
          v61 = v94;
        }
      }
      goto LABEL_88;
    }
  }
LABEL_84:
  LODWORD(v10) = v94;
LABEL_85:
  if ( v13 )
  {
LABEL_148:
    v99 = v13;
LABEL_149:
    if ( v13 != v108 )
    {
      v85 = v12;
      if ( (_DWORD)v10 )
      {
        v86 = v99;
        do
          (*(void (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 4) + 8LL))(
            *((_QWORD *)this + 4),
            v86[v85++]);
        while ( v85 < v94 );
        v13 = *(const unsigned __int16 ***)&Size[1];
      }
      CoTaskMemFree(v13);
    }
  }
}

```

## disassembly

```asm
0x180025f10  mov     [rsp-8+arg_10], rbx
0x180025f15  push    rbp
0x180025f16  push    rsi
0x180025f17  push    rdi
0x180025f18  push    r12
0x180025f1a  push    r13
0x180025f1c  push    r14
0x180025f1e  push    r15
0x180025f20  lea     rbp, [rsp-1Fh]
0x180025f25  sub     rsp, 0D0h
0x180025f2c  mov     rax, cs:__security_cookie
0x180025f33  xor     rax, rsp
0x180025f36  mov     [rbp+4Fh+var_38], rax
0x180025f3a  mov     rsi, [rbp+4Fh+arg_20]
0x180025f3e  xor     r11d, r11d
0x180025f41  mov     rdi, rcx
0x180025f44  mov     [rbp+4Fh+var_68], r9
0x180025f48  mov     r14, r9
0x180025f4b  mov     [rbp+4Fh+var_98], r8
0x180025f4f  mov     r9, r8
0x180025f52  mov     [rbp+4Fh+var_A8], r11
0x180025f56  mov     r8d, edx
0x180025f59  mov     [rsi], r11d
0x180025f5c  mov     dl, [rcx+13h]; unsigned __int8
0x180025f5f  mov     cl, [rcx+12h]; unsigned __int8
0x180025f62  mov     [rbp+4Fh+var_BC], r8d
0x180025f66  mov     [rbp+4Fh+var_B4], r11d
0x180025f6a  call    ?IsReadOnlyPropertySet@@YAEEE@Z; IsReadOnlyPropertySet(uchar,uchar)
0x180025f6f  test    al, al
0x180025f71  jnz     loc_1800266D0
0x180025f77  mov     qword ptr [rbp+4Fh+Size+4], r14
0x180025f7b  mov     r12, r14
0x180025f7e  mov     edx, 4B0h
0x180025f83  mov     r10d, 0FFFFFFFFh
0x180025f89  test    r14, r14
0x180025f8c  jnz     loc_180026615
0x180025f92  mov     [rbp+4Fh+var_A0], r12
0x180025f96  mov     r13d, r11d
0x180025f99  mov     [rbp+4Fh+var_BF], r11b
0x180025f9d  mov     [rbp+4Fh+var_BE], r11b
0x180025fa1  mov     [rbp+4Fh+var_B8], r11b
0x180025fa5  mov     [rbp+4Fh+var_B0], r11d
0x180025fa9  mov     [rbp+4Fh+var_8C], r11d
0x180025fad  cmp     r13d, r8d
0x180025fb0  jnb     loc_1800260A5
0x180025fb6  mov     r15d, r13d
0x180025fb9  test    r12, r12
0x180025fbc  jz      loc_18002676C
0x180025fc2  cmp     [r9+r15*4], r10d
0x180025fc6  jz      loc_180026092
0x180025fcc  mov     rcx, [r12+r15*8]
0x180025fd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025fd4  cmp     [rdi+10h], dx
0x180025fd8  jnz     loc_180026785
0x180025fde  inc     rax
0x180025fe1  cmp     [rcx+rax*2], r11w
0x180025fe6  jnz     short loc_180025FDE
0x180025fe8  inc     eax
0x180025fea  lea     r14d, [rax+rax]
0x180025fee  cmp     eax, 100h
0x180025ff3  mov     ecx, r11d
0x180025ff6  setnbe  cl
0x180025ff9  cmp     dx, [rdi+10h]
0x180025ffd  jz      loc_18002633A
0x180026003  cmp     r14d, 1
0x180026007  jz      loc_1800267C6
0x18002600d  mov     rax, [rdi]
0x180026010  lea     ebx, [r13+1]
0x180026014  cmp     [rax+2], cx
0x180026018  cmova   cx, [rax+2]
0x18002601d  mov     [rax+2], cx
0x180026021  cmp     ebx, r8d
0x180026024  jnb     short loc_180026071
0x180026026  mov     eax, [r9+r15*4]
0x18002602a  cmp     [r9+rbx*4], eax
0x18002602e  jz      loc_1800267B2
0x180026034  mov     r8, [r12+rbx*8]; char *
0x180026038  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002603c  cmp     [rdi+10h], dx
0x180026040  jnz     loc_180026798
0x180026046  inc     rax
0x180026049  cmp     [r8+rax*2], r11w
0x18002604e  jnz     short loc_180026046
0x180026050  lea     eax, ds:2[rax*2]
0x180026057  cmp     r14d, eax
0x18002605a  jz      loc_1800261DA
0x180026060  mov     r8d, [rbp+4Fh+var_BC]
0x180026064  cmp     [rsi], r11d
0x180026067  jl      loc_1800267D0
0x18002606d  inc     ebx
0x18002606f  jmp     short loc_180026021
0x180026071  mov     r11b, [rbp+4Fh+var_BE]
0x180026075  mov     r10b, [rbp+4Fh+var_BF]
0x180026079  mov     [rbp+4Fh+var_BE], r11b
0x18002607d  mov     [rbp+4Fh+var_BF], r10b
0x180026081  jz      loc_18002630E
0x180026087  mov     [rbp+4Fh+var_BF], r10b
0x18002608b  mov     [rbp+4Fh+var_BE], r11b
0x18002608f  xor     r11d, r11d
0x180026092  inc     r13d
0x180026095  mov     edx, 4B0h
0x18002609a  mov     r10d, 0FFFFFFFFh
0x1800260a0  jmp     loc_180025FAD
0x1800260a5  mov     rcx, [rdi+28h]
0x1800260a9  mov     rdx, rsi
0x1800260ac  mov     rax, [rcx]
0x1800260af  mov     rax, [rax+78h]
0x1800260b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260b8  xor     r11d, r11d
0x1800260bb  cmp     [rsi], r11d
0x1800260be  jl      loc_18002645A
0x1800260c4  mov     r14, [rbp+4Fh+var_A8]
0x1800260c8  mov     ebx, r11d
0x1800260cb  cmp     ebx, 2
0x1800260ce  ja      short loc_18002611A
0x1800260d0  xor     eax, eax
0x1800260d2  xorps   xmm0, xmm0
0x1800260d5  mov     [rbp+4Fh+var_48], rax
0x1800260d9  mov     [rbp+4Fh+var_40], eax
0x1800260dc  mov     qword ptr [rbp+4Fh+var_60+10h], rax
0x1800260e0  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x1800260e4  cmp     ebx, 2
0x1800260e7  jnb     loc_180026882
0x1800260ed  mov     r9, rsi; int *
0x1800260f0  lea     r8, [rbp+4Fh+var_B4]; unsigned int *
0x1800260f4  xor     edx, edx; unsigned int
0x1800260f6  mov     rcx, rdi; this
0x1800260f9  call    ?_LoadProperty@CPropertySetStream@@AEAAPEAUtagSERIALIZEDPROPERTYVALUE@@KPEAKPEAJ@Z; CPropertySetStream::_LoadProperty(ulong,ulong *,long *)
0x1800260fe  xor     r11d, r11d
0x180026101  mov     [rbp+4Fh+var_A8], rax
0x180026105  mov     r14, rax
0x180026108  cmp     [rsi], r11d
0x18002610b  jl      loc_18002645A
0x180026111  test    rax, rax
0x180026114  jz      loc_180026817
0x18002611a  mov     r9b, r11b
0x18002611d  mov     [rbp+4Fh+var_C0], r11b
0x180026121  mov     r13d, r11d
0x180026124  mov     [rbp+4Fh+var_90], r11d
0x180026128  mov     r15d, r11d
0x18002612b  lea     rbx, [r14+4]
0x18002612f  cmp     r15d, [r14]
0x180026132  jnb     loc_180026207
0x180026138  mov     r8d, [rbp+4Fh+var_BC]
0x18002613c  mov     r14d, r11d
0x18002613f  cmp     r14d, r8d
0x180026142  jnb     short loc_1800261BC
0x180026144  mov     rax, [rbp+4Fh+var_98]
0x180026148  mov     edx, 0FFFFFFFFh
0x18002614d  mov     ecx, r14d
0x180026150  mov     eax, [rax+rcx*4]
0x180026153  cmp     eax, edx
0x180026155  jz      short loc_1800261B7
0x180026157  cmp     [rbp+4Fh+var_B8], r11b
0x18002615b  jnz     loc_1800268A7
0x180026161  cmp     eax, [rbx]
0x180026163  jz      loc_1800268A7
0x180026169  test    r12, r12
0x18002616c  jz      short loc_1800261B7
0x18002616e  mov     r9, [r12+rcx*8]; int
0x180026172  mov     r10d, 4B0h
0x180026178  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002617c  cmp     [rdi+10h], r10w
0x180026181  jnz     loc_18002688D
0x180026187  inc     rax
0x18002618a  cmp     [r9+rax*2], r11w
0x18002618f  jnz     short loc_180026187
0x180026191  lea     edx, ds:2[rax*2]
0x180026198  mov     ecx, [rbx+4]
0x18002619b  cmp     [rdi+10h], r10w
0x1800261a0  lea     eax, [rcx+rcx]
0x1800261a3  cmovnz  eax, ecx
0x1800261a6  cmp     edx, eax
0x1800261a8  jz      loc_180026694
0x1800261ae  cmp     [rsi], r11d
0x1800261b1  jl      loc_1800267CC
0x1800261b7  inc     r14d
0x1800261ba  jmp     short loc_18002613F
0x1800261bc  mov     r9b, [rbp+4Fh+var_C0]
0x1800261c0  inc     r15d
0x1800261c3  mov     rdx, rbx; struct tagENTRY *
0x1800261c6  mov     rcx, rdi; this
0x1800261c9  call    ?_NextDictionaryEntry@CPropertySetStream@@AEBAPEFAUtagENTRY@@PEFBU2@@Z; CPropertySetStream::_NextDictionaryEntry(tagENTRY const *)
0x1800261ce  mov     r14, [rbp+4Fh+var_A8]
0x1800261d2  mov     rbx, rax
0x1800261d5  jmp     loc_18002612F
0x1800261da  mov     rdx, [r12+r15*8]; lpString1
0x1800261de  mov     rcx, rdi; this
0x1800261e1  mov     [rsp+100h+var_D8], rsi; int *
0x1800261e6  call    ?_ComparePropertyNames@CPropertySetStream@@AEBAEPEBX0HKPEAJ@Z; CPropertySetStream::_ComparePropertyNames(void const *,void const *,int,ulong,long *)
0x1800261eb  mov     r9, [rbp+4Fh+var_98]
0x1800261ef  xor     r11d, r11d
0x1800261f2  test    al, al
0x1800261f4  jz      loc_1800267A8
0x1800261fa  mov     r8d, [rbp+4Fh+var_BC]
0x1800261fe  mov     [rbp+4Fh+var_BE], 1
0x180026202  jmp     loc_180026092
0x180026207  movsxd  r8, dword ptr [rdi+8]
0x18002620b  mov     eax, [rbp+4Fh+var_B4]
0x18002620e  mov     rdx, [rdi]
0x180026211  mov     ecx, [rbp+4Fh+var_B0]
0x180026214  sub     ecx, r13d
0x180026217  mov     r13d, r14d
0x18002621a  lea     r10d, [rax+3]
0x18002621e  sub     r13d, edx
0x180026221  mov     r15d, [r8+rdx]
0x180026225  add     eax, 3
0x180026228  add     r15d, [rdi+1Ch]
0x18002622c  and     r10d, 0FFFFFFFCh
0x180026230  add     eax, ecx
0x180026232  mov     [rbp+4Fh+var_7C], r10d
0x180026236  and     eax, 0FFFFFFFCh
0x180026239  sub     r13d, r8d
0x18002623c  mov     ebx, eax
0x18002623e  mov     [rbp+4Fh+var_78], eax
0x180026241  lea     eax, [r15+r8]
0x180026245  mov     [rbp+4Fh+var_80], r13d
0x180026249  sub     r15d, r10d
0x18002624c  mov     dword ptr [rbp+4Fh+var_A0], eax
0x18002624f  sub     r15d, r13d
0x180026252  sub     ebx, r10d
0x180026255  mov     [rbp+4Fh+var_B0], ebx
0x180026258  mov     dword ptr [rbp+4Fh+Size], r15d
0x18002625c  test    ebx, ebx
0x18002625e  jg      loc_1800265AC
0x180026264  lea     r15, [r14+4]
0x180026268  cmp     [rbp+4Fh+var_B8], r11b
0x18002626c  jnz     loc_18002635C
0x180026272  mov     rdx, r15; Src
0x180026275  mov     r14, r15
0x180026278  mov     [rbp+4Fh+Src], rdx
0x18002627c  mov     ebx, r11d
0x18002627f  mov     eax, r11d
0x180026282  mov     rcx, [rbp+4Fh+var_A8]
0x180026286  mov     [rbp+4Fh+var_B4], eax
0x180026289  cmp     eax, [rcx]
0x18002628b  jnb     loc_180026343
0x180026291  mov     r8d, [rbp+4Fh+var_BC]
0x180026295  mov     r13d, r11d
0x180026298  cmp     r13d, r8d
0x18002629b  jnb     short loc_1800262BA
0x18002629d  mov     rdx, [rbp+4Fh+var_98]
0x1800262a1  mov     eax, [r15]
0x1800262a4  mov     ecx, r13d
0x1800262a7  cmp     [rdx+rcx*4], eax
0x1800262aa  jz      short loc_1800262BA
0x1800262ac  test    r9b, r9b
0x1800262af  jnz     loc_180026533
0x1800262b5  inc     r13d
0x1800262b8  jmp     short loc_180026298
0x1800262ba  mov     edx, 4B0h
0x1800262bf  mov     eax, r11d
0x1800262c2  cmp     [rdi+10h], dx
0x1800262c6  setz    al
0x1800262c9  lea     ecx, [rax+1]
0x1800262cc  imul    ecx, [r15+4]
0x1800262d1  add     ecx, 8
0x1800262d4  cmp     [rdi+10h], dx
0x1800262d8  jnz     loc_18002668D
0x1800262de  add     ecx, 3
0x1800262e1  mov     edx, 0FFFFFFFCh
0x1800262e6  mov     eax, ecx
0x1800262e8  and     eax, edx
0x1800262ea  and     ecx, edx
0x1800262ec  cdqe
0x1800262ee  add     r15, rax
0x1800262f1  cmp     r13d, r8d
0x1800262f4  jnz     loc_180026586
0x1800262fa  mov     rdx, [rbp+4Fh+Src]
0x1800262fe  add     ebx, ecx
0x180026300  mov     eax, [rbp+4Fh+var_B4]
0x180026303  mov     r9b, [rbp+4Fh+var_C0]
0x180026307  inc     eax
0x180026309  jmp     loc_180026282
0x18002630e  mov     edx, [rbp+4Fh+var_B0]
0x180026311  mov     eax, 4B0h
0x180026316  inc     [rbp+4Fh+var_8C]
0x180026319  add     edx, 8
0x18002631c  add     edx, r14d
0x18002631f  mov     [rbp+4Fh+var_B0], edx
0x180026322  cmp     [rdi+10h], ax
0x180026326  jnz     loc_180026087
0x18002632c  add     edx, 3
0x18002632f  and     edx, 0FFFFFFFCh
0x180026332  mov     [rbp+4Fh+var_B0], edx
0x180026335  jmp     loc_18002608F
0x18002633a  cmp     r14d, 2
0x18002633e  jmp     loc_180026007
0x180026343  test    ebx, ebx
0x180026345  jnz     loc_180026907
0x18002634b  mov     r13d, [rbp+4Fh+var_80]
0x18002634f  movsxd  r15, ebx
0x180026352  mov     ebx, [rbp+4Fh+var_B0]
0x180026355  add     r15, r14
0x180026358  mov     r14, [rbp+4Fh+var_A8]
0x18002635c  mov     eax, [rbp+4Fh+var_90]
0x18002635f  sub     [r14], eax
0x180026362  test    r12, r12
0x180026365  jz      loc_180026417
0x18002636b  mov     r14d, r11d
  ... truncated ...
```
