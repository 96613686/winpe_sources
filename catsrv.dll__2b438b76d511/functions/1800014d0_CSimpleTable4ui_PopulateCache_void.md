# CSimpleTable4ui::PopulateCache(void)

- ea: `0x1800014d0`
- end: `0x1800020ea`
- name: `?PopulateCache@CSimpleTable4ui@@UEAAJXZ`
- size: `3098`
- prototype: `__int64 __fastcall(CSimpleTable4ui *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800014d0`
- `0x1800020f0`
- `0x180002464`
- `0x180002590`
- `0x180002750`
- `0x1800061f0`
- `0x18000821c`
- `0x180008f9c`
- `0x180009744`
- `0x18005550e`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b52`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000178f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000178f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000209a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800020b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000209a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800020b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001c95`

## pseudocode

```c
signed int __fastcall CSimpleTable4ui::PopulateCache(CSimpleTable4ui *this)
{
  int v1; // eax
  CSimpleTable4ui *v2; // r14
  char *v3; // r12
  _BYTE *v4; // rcx
  CSimpleDataTableCursor *v5; // r13
  signed int result; // eax
  __int64 v7; // rcx
  unsigned int j; // ebx
  __int64 v9; // rcx
  __int64 v10; // r15
  __int64 v11; // rax
  int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // r12
  __int64 v15; // rax
  bool v16; // zf
  WCHAR *v17; // rax
  char *v18; // rcx
  void *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // r9
  _DWORD *v22; // rcx
  int v23; // r10d
  int v24; // r15d
  __int64 v25; // rax
  size_t v26; // r8
  unsigned int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdx
  unsigned int *v30; // r11
  __int64 v31; // rax
  _DWORD *v32; // rsi
  _BYTE *v33; // rdi
  unsigned int v34; // r10d
  unsigned int n; // eax
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rdx
  int v39; // edi
  unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  _DWORD *v42; // r14
  _BYTE *v43; // r11
  unsigned int *v44; // rsi
  unsigned int v45; // r10d
  unsigned int m; // edx
  __int64 v47; // rax
  char v48; // dl
  unsigned int k; // ebx
  void *v50; // rcx
  char *v51; // rdi
  unsigned int v52; // r15d
  __int64 v53; // rcx
  __int64 v54; // r9
  __int64 v55; // r8
  __int64 v56; // rdx
  char *v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rbx
  char v60; // al
  int v61; // edi
  int v62; // r8d
  unsigned int v63; // esi
  __int64 i; // r8
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // rcx
  int v68; // ecx
  unsigned int v69; // eax
  int v70; // r8d
  int v71; // eax
  unsigned int ii; // edi
  void *v73; // rcx
  LPWSTR lpWideCharStr; // [rsp+28h] [rbp-E0h]
  int cchWideChar[2]; // [rsp+30h] [rbp-D8h]
  __int64 v76; // [rsp+38h] [rbp-D0h]
  __int64 v77; // [rsp+40h] [rbp-C8h]
  __int64 v78; // [rsp+48h] [rbp-C0h]
  int v79; // [rsp+78h] [rbp-90h] BYREF
  _WORD v80[2]; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v81; // [rsp+80h] [rbp-88h] BYREF
  char *v82; // [rsp+88h] [rbp-80h]
  unsigned int v83; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v84; // [rsp+94h] [rbp-74h] BYREF
  int v85; // [rsp+98h] [rbp-70h] BYREF
  int v86; // [rsp+9Ch] [rbp-6Ch] BYREF
  unsigned int v87; // [rsp+A0h] [rbp-68h]
  void *v88; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v89; // [rsp+B0h] [rbp-58h] BYREF
  LPCCH lpMultiByteStr; // [rsp+B8h] [rbp-50h] BYREF
  CSimpleTable4ui *v91; // [rsp+C0h] [rbp-48h]
  _BYTE v92[48]; // [rsp+C8h] [rbp-40h] BYREF

  v1 = *((_DWORD *)this + 24);
  v91 = this;
  v2 = this;
  v79 = 0;
  v84 = 0;
  v89 = 0;
  v86 = 0;
  v83 = 0;
  v85 = 0;
  v80[0] = 0;
  v81 = 0;
  if ( (v1 & 8) != 0 )
  {
    result = CSimpleDataTableCursor::InternalPrePopulateCache((CSimpleTable4ui *)((char *)this + 24), 0);
    v79 = result;
    if ( result >= 0 )
    {
      *((_DWORD *)v2 + 24) &= ~8u;
      CSimpleDataTableCursor::InternalPostPopulateCache((CSimpleTable4ui *)((char *)v2 + 24));
      return 0;
    }
    return result;
  }
  v3 = 0;
  if ( *((_DWORD *)this + 25) == 1 && !*((_QWORD *)this + 33) )
  {
    if ( (v1 & 0x10) != 0 || (unsigned int)RegSrvrGetWICRforRead((struct IComponentRecords **)this + 33) )
    {
      result = CoRegGetICR((struct IComponentRecords **)v2 + 33);
      v79 = result;
      if ( result < 0 )
        goto LABEL_13;
    }
    else
    {
      v79 = 0;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, __int64))(**((_QWORD **)v2 + 33) + 384LL))(
               *((_QWORD *)v2 + 33),
               &COMRegSchema,
               *((unsigned int *)v2 + 22),
               (__int64)v2 + 80);
    v79 = result;
    if ( result < 0 )
    {
LABEL_11:
      if ( result < 0 )
        goto LABEL_163;
      if ( v3 )
      {
LABEL_168:
        CoTaskMemFree(v3);
        result = v79;
      }
      goto LABEL_13;
    }
  }
  v4 = (_BYTE *)*((_QWORD *)v2 + 3);
  v5 = (CSimpleTable4ui *)((char *)v2 + 24);
  if ( (v4[40] & 1) == 0 )
  {
LABEL_16:
    result = -2146367483;
    v79 = -2146367483;
    goto LABEL_11;
  }
  if ( (*(_DWORD *)v4 & 0x10000) != 0 )
  {
    result = -2147418113;
    v79 = -2147418113;
    goto LABEL_11;
  }
  if ( *((char *)v2 + 32) < 0 )
  {
    result = -2146367483;
    v79 = -2146367483;
    goto LABEL_11;
  }
  *((_BYTE *)v2 + 32) = 17;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 7) = 0;
  *((_DWORD *)v2 + 12) = -1;
  *((_DWORD *)v2 + 16) = -1;
  if ( (*((_DWORD *)v4 + 10) & 3) == 1 )
  {
    *((_DWORD *)v4 + 10) |= 2u;
    CSimpleDataTableCache::CleanupCaches((CSimpleDataTableCache *)v4);
  }
  v53 = *((_QWORD *)v2 + 33);
  v54 = *((unsigned int *)v2 + 44);
  v55 = *((_QWORD *)v2 + 13);
  v78 = *((_QWORD *)v2 + 27);
  v77 = *((_QWORD *)v2 + 26);
  v76 = *((_QWORD *)v2 + 25);
  *(_QWORD *)cchWideChar = *((_QWORD *)v2 + 24);
  v56 = *((_QWORD *)v2 + 23);
  v79 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, int *, __int64, __int64, __int64, _QWORD, _DWORD, _BYTE *, _QWORD))(*(_QWORD *)v53 + 120LL))(
             v53,
             *((_QWORD *)v2 + 10),
             v55,
             v54,
             v56,
             *(int **)cchWideChar,
             v76,
             v77,
             v78,
             0,
             0,
             v92,
             0);
  v79 = result;
  if ( result < 0 )
  {
    if ( result != -2147217360 )
      goto LABEL_11;
    v84 = 0;
    v79 = 0;
  }
  else
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, unsigned int *))(**((_QWORD **)v2 + 33) + 152LL))(
               *((_QWORD *)v2 + 33),
               v92,
               &v84);
    v79 = result;
    if ( result < 0 )
      goto LABEL_11;
  }
  v57 = (char *)CoTaskMemAlloc(saturated_mul(*((unsigned int *)v2 + 23), 8u));
  v82 = v57;
  v3 = v57;
  if ( !v57 )
  {
    result = -2147024882;
    v79 = -2147024882;
    goto LABEL_13;
  }
  memset_0(v57, 0, 8LL * *((unsigned int *)v2 + 23));
  v52 = 0;
LABEL_102:
  v87 = v52;
  if ( v52 >= v84 )
  {
    result = CSimpleDataTableCursor::InternalPostPopulateCache(v5);
    v79 = result;
    if ( result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v2 + 33) + 160LL))(*((_QWORD *)v2 + 33), v92);
      v79 = result;
    }
    goto LABEL_11;
  }
  v58 = *((_QWORD *)v2 + 33);
  v86 = 1;
  result = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int64 *, int *))(*(_QWORD *)v58 + 136LL))(
             v58,
             v92,
             1,
             &v89,
             &v86);
  v79 = result;
  if ( result < 0 )
    goto LABEL_11;
  v59 = *(_QWORD *)v5;
  if ( (**(_BYTE **)v5 & 1) != 0 && (*(_BYTE *)(v59 + 40) & 2) == 0 )
  {
    result = -2147467263;
    v79 = -2147467263;
    goto LABEL_11;
  }
  v60 = *((_BYTE *)v2 + 32);
  if ( v60 < 0 )
    goto LABEL_16;
  *((_BYTE *)v2 + 32) = v60 & 0x6F | 0x80;
  v61 = *(_DWORD *)(v59 + 8) + *(_DWORD *)(v59 + 12) + *(_DWORD *)(v59 + 16);
  v62 = *(_DWORD *)(v59 + 84);
  if ( (*(_BYTE *)(v59 + 40) & 2) == 0 )
    ++v61;
  v63 = 4 * v61;
  if ( *(_DWORD *)(v59 + 80) == v62 )
  {
    v68 = 2 * v62 + 1;
    v69 = v68 - v62;
    v70 = v62 + 2500;
    if ( v69 <= 0x9C4 )
      v70 = v68;
    *(_DWORD *)(v59 + 84) = v70;
    v71 = CSimpleDataTableCache::ResizeCache((CSimpleDataTableCache *)v59, 0x20000u, v63 * v70);
    if ( v71 < 0 )
    {
      v79 = v71;
      goto LABEL_164;
    }
  }
  *((_DWORD *)v2 + 16) = *(_DWORD *)(v59 + 80);
  *((_QWORD *)v2 + 7) = *(_QWORD *)(v59 + 88) + 4LL * (unsigned int)(*(_DWORD *)(v59 + 80) * v61);
  ++*(_DWORD *)(v59 + 80);
  memset_0(*((void **)v2 + 7), 0, v63);
  if ( (*(_BYTE *)(*(_QWORD *)v5 + 40LL) & 4) != 0 )
    *(_DWORD *)(*((_QWORD *)v2 + 7)
              + 4LL
              * (unsigned int)(*(_DWORD *)(*(_QWORD *)v5 + 8LL)
                             + *(_DWORD *)(*(_QWORD *)v5 + 12LL)
                             + *(_DWORD *)(*(_QWORD *)v5 + 16LL))) = 1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v65 = *(_QWORD *)v5;
    if ( (unsigned int)i >= *(_DWORD *)(*(_QWORD *)v5 + 4LL) )
      break;
    if ( (*(_BYTE *)(v65 + 40) & 1) == 0 )
      goto LABEL_16;
    v66 = *(_QWORD *)(v65 + 24);
    if ( *(_DWORD *)(v66 + 12 * i) == 19 && (*(_BYTE *)(v66 + 12 * i + 8) & 2) != 0 )
    {
      v67 = *(unsigned __int16 *)(*(_QWORD *)(v65 + 32) + 8 * i);
      *(_BYTE *)(v67 + *((_QWORD *)v2 + 7)) |= 1u;
    }
  }
  v79 = 0;
  for ( j = 0; ; ++j )
  {
    if ( j >= *((_DWORD *)v2 + 23) )
    {
      result = CSimpleDataTableCursor::InternalSetRow(v5);
      v3 = v82;
      v79 = result;
      if ( result < 0 )
        goto LABEL_11;
      for ( k = 0; k < *((_DWORD *)v2 + 23); *(_QWORD *)v51 = 0 )
      {
        v50 = *(void **)&v3[8 * k];
        v51 = &v3[8 * k];
        if ( v50 )
          CoTaskMemFree(v50);
        ++k;
      }
      v52 = v87 + 1;
      goto LABEL_102;
    }
    v9 = *(_QWORD *)v5;
    v88 = 0;
    if ( (*(_BYTE *)(v9 + 40) & 1) == 0 )
    {
      result = -2146367483;
      goto LABEL_159;
    }
    if ( j >= *(_DWORD *)(v9 + 4) )
    {
      result = -2146367487;
LABEL_159:
      v3 = v82;
      v79 = result;
      goto LABEL_11;
    }
    v10 = 12LL * j;
    v11 = *(_QWORD *)(v9 + 24);
    v12 = *(_DWORD *)(v11 + v10);
    v85 = *(_DWORD *)(v11 + v10 + 4);
    v79 = 0;
    v80[0] = v12;
    if ( v12 == 130 )
    {
      v13 = *((_QWORD *)v2 + 33);
      lpMultiByteStr = 0;
      v80[0] = 16514;
      v83 = j + 1;
      LODWORD(lpWideCharStr) = 1;
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, LPWSTR, _WORD *, LPCCH *, int *, unsigned int *, int *, unsigned int *))(*(_QWORD *)v13 + 64LL))(
                 v13,
                 *((_QWORD *)v2 + 10),
                 v89,
                 1,
                 lpWideCharStr,
                 v80,
                 &lpMultiByteStr,
                 &v85,
                 &v81,
                 &v79,
                 &v83);
      v79 = result;
      if ( result < 0 )
      {
        v3 = v82;
        goto LABEL_11;
      }
      v14 = 8LL * j;
      if ( result == 3 )
      {
        v19 = 0;
        v88 = 0;
        *(_QWORD *)&v82[8 * j] = 0;
        result = v79;
        v81 = 0;
      }
      else
      {
        v15 = -1;
        do
          v16 = lpMultiByteStr[++v15] == 0;
        while ( !v16 );
        v81 = 2 * v15 + 2;
        v17 = (WCHAR *)CoTaskMemAlloc(v81);
        v18 = v82;
        *(_QWORD *)&v82[8 * j] = v17;
        if ( !v17 )
        {
          v3 = v18;
          v79 = -2147024882;
          goto LABEL_164;
        }
        if ( MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, v17, v81 >> 1) )
        {
          v19 = *(void **)&v82[8 * j];
          result = v79;
          v88 = v19;
        }
        else
        {
          result = GetLastError();
          if ( result > 0 )
            result = (unsigned __int16)result | 0x80070000;
          v19 = v88;
          v79 = result;
        }
      }
    }
    else
    {
      if ( v12 != 19 && v12 != 72 && v12 != 128 && v12 != 135 )
      {
        v3 = v82;
        v79 = -2147418113;
        goto LABEL_164;
      }
      v20 = *((_QWORD *)v2 + 33);
      v80[0] = v12 | 0x4000;
      v83 = j + 1;
      LODWORD(lpWideCharStr) = 1;
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, LPWSTR, _WORD *, void **, int *, unsigned int *, int *, unsigned int *))(*(_QWORD *)v20 + 64LL))(
                 v20,
                 *((_QWORD *)v2 + 10),
                 v89,
                 1,
                 lpWideCharStr,
                 v80,
                 &v88,
                 &v85,
                 &v81,
                 &v79,
                 &v83);
      v19 = v88;
      v14 = 8LL * j;
      v79 = result;
    }
    if ( result < 0 )
      break;
    if ( result == 3 )
    {
      v37 = *(_QWORD *)v5;
      if ( (**(_BYTE **)v5 & 1) == 0 || (*(_BYTE *)(v37 + 40) & 2) != 0 )
      {
        if ( *((char *)v5 + 8) >= 0 )
        {
          result = -2146367483;
        }
        else if ( j >= *(_DWORD *)(v37 + 4) )
        {
          result = -2146367487;
        }
        else
        {
          v38 = *((_QWORD *)v5 + 4);
          v39 = *(_DWORD *)(*(_QWORD *)(v37 + 24) + v10 + 8);
          v40 = (unsigned __int16 *)(*(_QWORD *)(v37 + 32) + 8LL * j);
          v41 = v40[1];
          if ( (_WORD)v41 == 0xFFFF )
            v42 = 0;
          else
            v42 = (_DWORD *)(v38 + 4 * v41);
          v43 = (_BYTE *)(v38 + *v40);
          if ( (v39 & 0x40000) != 0 )
          {
            v44 = (unsigned int *)(v38 + 4LL * *((unsigned int *)v40 + 1));
            if ( v44 )
            {
              v45 = *(_DWORD *)(v37 + 140);
              for ( m = 0; m < v45; ++m )
              {
                v47 = *(_QWORD *)(v37 + 128);
                if ( *(_DWORD *)(v47 + 16LL * m) == j )
                {
                  *(_QWORD *)(v47 + 16LL * m + 8) = 0;
                  *v44 = m;
                  goto LABEL_79;
                }
              }
              if ( *(_DWORD *)(v37 + 136) != v45 )
              {
                *v44 = v45;
                *(_DWORD *)(*(_QWORD *)(v37 + 128) + 16LL * *(unsigned int *)(v37 + 140)) = j;
                *(_QWORD *)(*(_QWORD *)(v37 + 128) + 16LL * (unsigned int)(*(_DWORD *)(v37 + 140))++ + 8) = 0;
LABEL_79:
                *v43 &= 0xCFu;
                goto LABEL_80;
              }
              result = -2146367483;
            }
            else
            {
              result = -2147024809;
            }
          }
          else
          {
LABEL_80:
            if ( (v39 & 0x20000) != 0 && v42 )
              *v42 = 0;
            *v43 &= ~1u;
            *v43 |= 2u;
            result = 0;
          }
        }
      }
      else
      {
        result = -2147467263;
      }
    }
    else if ( v12 == 128 )
    {
      result = CSimpleDataTableCursor::InternalSetWriteColumn(v5, j, v81, v19);
    }
    else
    {
      v21 = *(_QWORD *)v5;
      if ( (**(_BYTE **)v5 & 1) != 0 && (*(_BYTE *)(v21 + 40) & 2) == 0 )
      {
        result = -2147467263;
        goto LABEL_75;
      }
      if ( *((char *)v5 + 8) >= 0 )
      {
        result = -2146367483;
      }
      else if ( j >= *(_DWORD *)(v21 + 4) )
      {
        result = -2146367487;
      }
      else
      {
        v22 = (_DWORD *)(v10 + *(_QWORD *)(v21 + 24));
        v23 = v22[2];
        v24 = v23 & 0x20000;
        if ( (v23 & 0x20000) != 0 && v19 )
        {
          result = -2146367484;
        }
        else
        {
          if ( *v22 == 130 && v19 )
          {
            v25 = -1;
            do
              v16 = *((_WORD *)v19 + ++v25) == 0;
            while ( !v16 );
            v26 = (unsigned int)(2 * v25 + 2);
            v27 = v22[1];
            if ( v27 != -1 && (unsigned int)v26 > v27 )
            {
              result = -2146367481;
              goto LABEL_75;
            }
          }
          else
          {
            v26 = (unsigned int)v22[1];
          }
          v28 = *(_QWORD *)(v21 + 32);
          v29 = *((_QWORD *)v5 + 4);
          v30 = (unsigned int *)(v29 + 4LL * *(unsigned int *)(v28 + v14 + 4));
          v31 = *(unsigned __int16 *)(v28 + v14 + 2);
          if ( (_WORD)v31 == 0xFFFF )
            v32 = 0;
          else
            v32 = (_DWORD *)(v29 + 4 * v31);
          v33 = (_BYTE *)(v29 + *(unsigned __int16 *)(v28 + v14));
          if ( (v23 & 0x40000) != 0 )
          {
            if ( v30 )
            {
              v34 = *(_DWORD *)(v21 + 140);
              for ( n = 0; n < v34; ++n )
              {
                v36 = *(_QWORD *)(v21 + 128);
                if ( *(_DWORD *)(v36 + 16LL * n) == j )
                {
                  *(_QWORD *)(v36 + 16LL * n + 8) = v19;
                  *v30 = n;
                  goto LABEL_55;
                }
              }
              if ( *(_DWORD *)(v21 + 136) != v34 )
              {
                *v30 = v34;
                *(_DWORD *)(*(_QWORD *)(v21 + 128) + 16LL * *(unsigned int *)(v21 + 140)) = j;
                *(_QWORD *)(*(_QWORD *)(v21 + 128) + 16LL * (unsigned int)(*(_DWORD *)(v21 + 140))++ + 8) = v19;
LABEL_55:
                *v33 &= 0xCFu;
                goto LABEL_71;
              }
              result = -2146367483;
            }
            else
            {
              result = -2147024809;
            }
          }
          else
          {
            if ( v19 )
              memcpy_0(v30, v19, v26);
LABEL_71:
            if ( v24 && v32 )
              *v32 = 0;
            v48 = *v33 & 0xFE;
            if ( v19 )
              v48 = *v33 | 1;
            *v33 = v48 | 2;
            result = 0;
          }
        }
      }
    }
LABEL_75:
    v2 = v91;
    v79 = result;
    if ( result < 0 )
      goto LABEL_162;
  }
  v2 = v91;
LABEL_162:
  v3 = v82;
LABEL_163:
  if ( v3 )
  {
LABEL_164:
    for ( ii = 0; ii < *((_DWORD *)v2 + 23); ++ii )
    {
      v73 = *(void **)&v3[8 * ii];
      if ( v73 )
      {
        CoTaskMemFree(v73);
        *(_QWORD *)&v3[8 * ii] = 0;
      }
    }
    goto LABEL_168;
  }
LABEL_13:
  if ( *((_DWORD *)v2 + 25) == 1 )
  {
    v7 = *((_QWORD *)v2 + 33);
    if ( v7 )
    {
      if ( dword_180072FE8 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        result = v79;
        *((_QWORD *)v2 + 33) = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800014d0  mov     r11, rsp
0x1800014d3  push    rbp
0x1800014d4  push    rbx
0x1800014d5  push    rsi
0x1800014d6  push    r14
0x1800014d8  lea     rbp, [r11-28h]
0x1800014dc  sub     rsp, 108h
0x1800014e3  mov     rax, cs:__security_cookie
0x1800014ea  xor     rax, rsp
0x1800014ed  mov     [rbp+20h+var_30], rax
0x1800014f1  mov     eax, [rcx+60h]
0x1800014f4  xor     esi, esi
0x1800014f6  mov     [rbp+20h+var_68], rcx
0x1800014fa  mov     r14, rcx
0x1800014fd  mov     [rsp+120h+var_B0], esi
0x180001501  mov     [rbp+20h+var_94], esi
0x180001504  mov     [rbp+20h+var_78], rsi
0x180001508  mov     [rbp+20h+var_8C], esi
0x18000150b  mov     [rbp+20h+var_98], esi
0x18000150e  mov     [rbp+20h+var_90], esi
0x180001511  mov     [rsp+74h], si
0x180001516  mov     [rsp+120h+var_A8], esi
0x18000151a  test    al, 8
0x18000151c  jnz     loc_180001EB9
0x180001522  cmp     dword ptr [rcx+64h], 1
0x180001526  mov     [r11+10h], rdi
0x18000152a  mov     [r11+18h], r12
0x18000152e  mov     r12d, esi
0x180001531  mov     [r11+20h], r13
0x180001535  mov     [r11-28h], r15
0x180001539  jnz     short loc_180001544
0x18000153b  cmp     [rcx+108h], rsi
0x180001542  jz      short loc_180001577
0x180001544  mov     rcx, [r14+18h]; this
0x180001548  lea     r13, [r14+18h]
0x18000154c  test    byte ptr [rcx+28h], 1
0x180001550  jz      loc_180001625
0x180001556  test    dword ptr [rcx], 10000h
0x18000155c  jnz     loc_180001F02
0x180001562  cmp     [r13+8], sil
0x180001566  jge     loc_180001F10
0x18000156c  mov     eax, 80110805h
0x180001571  mov     [rsp+120h+var_B0], eax
0x180001575  jmp     short loc_1800015C0
0x180001577  test    al, 10h
0x180001579  jz      loc_180001EE5
0x18000157f  lea     rcx, [r14+108h]
0x180001586  call    CoRegGetICR
0x18000158b  mov     [rsp+120h+var_B0], eax
0x18000158f  test    eax, eax
0x180001591  js      short loc_1800015D5
0x180001593  mov     rcx, [r14+108h]
0x18000159a  lea     r9, [r14+50h]
0x18000159e  mov     r8d, [r14+58h]
0x1800015a2  lea     rdx, ?COMRegSchema@@3U_tagCOMPLIBSCHEMA@@B; _tagCOMPLIBSCHEMA const COMRegSchema
0x1800015a9  mov     rax, [rcx]
0x1800015ac  mov     rax, [rax+180h]
0x1800015b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015b8  mov     [rsp+120h+var_B0], eax
0x1800015bc  test    eax, eax
0x1800015be  jns     short loc_180001544
0x1800015c0  xor     edx, edx
0x1800015c2  test    eax, eax
0x1800015c4  js      loc_180002076
0x1800015ca  test    r12, r12
0x1800015cd  jnz     loc_1800020AF
0x1800015d3  xor     esi, esi
0x1800015d5  cmp     dword ptr [r14+64h], 1
0x1800015da  mov     r15, [rsp+100h]
0x1800015e2  mov     r13, [rsp+120h+arg_18]
0x1800015ea  mov     r12, [rsp+120h+arg_10]
0x1800015f2  mov     rdi, [rsp+120h+arg_8]
0x1800015fa  jnz     short loc_18000160C
0x1800015fc  mov     rcx, [r14+108h]
0x180001603  test    rcx, rcx
0x180001606  jnz     loc_1800020C1
0x18000160c  mov     rcx, [rbp+20h+var_30]
0x180001610  xor     rcx, rsp; StackCookie
0x180001613  call    __security_check_cookie
0x180001618  add     rsp, 108h
0x18000161f  pop     r14
0x180001621  pop     rsi
0x180001622  pop     rbx
0x180001623  pop     rbp
0x180001624  retn
0x180001625  mov     eax, 80110805h
0x18000162a  mov     [rsp+120h+var_B0], eax
0x18000162e  jmp     short loc_1800015C0
0x180001630  xor     edx, edx
0x180001632  mov     [rsp+120h+var_B0], edx
0x180001636  mov     ebx, edx
0x180001638  nop     dword ptr [rax+rax+00000000h]
0x180001640  cmp     ebx, [r14+5Ch]
0x180001644  jnb     loc_180001B78
0x18000164a  mov     rcx, [r13+0]
0x18000164e  mov     [rbp+20h+var_80], rdx
0x180001652  test    byte ptr [rcx+28h], 1
0x180001656  jz      loc_180002053
0x18000165c  cmp     ebx, [rcx+4]
0x18000165f  jnb     loc_18000204C
0x180001665  mov     esi, ebx
0x180001667  lea     rax, [rsi+rsi*2]
0x18000166b  lea     r15, ds:0[rax*4]
0x180001673  mov     rax, [rcx+18h]
0x180001677  mov     edi, [rax+r15]
0x18000167b  mov     eax, [rax+r15+4]
0x180001680  mov     [rbp+20h+var_90], eax
0x180001683  mov     [rsp+120h+var_B0], edx
0x180001687  mov     [rsp+74h], di
0x18000168c  cmp     edi, 82h
0x180001692  jnz     loc_1800017B4
0x180001698  mov     rcx, [r14+108h]
0x18000169f  movzx   eax, di
0x1800016a2  mov     r8, [rbp+20h+var_78]
0x1800016a6  or      ax, 4000h
0x1800016aa  mov     [rbp+20h+lpMultiByteStr], rdx
0x1800016ae  mov     r9d, 1
0x1800016b4  mov     [rsp+74h], ax
0x1800016b9  lea     rdx, [rbp+20h+var_98]
0x1800016bd  mov     [rsp+120h+var_D0], rdx
0x1800016c2  lea     eax, [rbx+1]
0x1800016c5  mov     [rbp+20h+var_98], eax
0x1800016c8  lea     rdx, [rsp+120h+var_B0]
0x1800016cd  mov     rax, [rcx]
0x1800016d0  mov     [rsp+120h+var_D8], rdx
0x1800016d5  lea     rdx, [rsp+120h+var_A8]
0x1800016da  mov     [rsp+120h+var_E0], rdx
0x1800016df  lea     rdx, [rbp+20h+var_90]
0x1800016e3  mov     [rsp+120h+var_E8], rdx
0x1800016e8  lea     rdx, [rbp+20h+lpMultiByteStr]
0x1800016ec  mov     rax, [rax+40h]
0x1800016f0  mov     [rsp+120h+var_F0], rdx
0x1800016f5  lea     rdx, [rsp+74h]
0x1800016fa  mov     qword ptr [rsp+120h+cchWideChar], rdx
0x1800016ff  mov     rdx, [r14+50h]
0x180001703  mov     dword ptr [rsp+120h+lpWideCharStr], 1
0x18000170b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001710  mov     [rsp+120h+var_B0], eax
0x180001714  test    eax, eax
0x180001716  js      loc_180002065
0x18000171c  lea     r12, ds:0[rsi*8]
0x180001724  cmp     eax, 3
0x180001727  jz      loc_180001B34
0x18000172d  mov     rcx, [rbp+20h+lpMultiByteStr]
0x180001731  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001738  nop     dword ptr [rax+rax+00000000h]
0x180001740  cmp     byte ptr [rcx+rax+1], 0
0x180001745  lea     rax, [rax+1]
0x180001749  jnz     short loc_180001740
0x18000174b  lea     eax, ds:2[rax*2]
0x180001752  mov     ecx, eax; cb
0x180001754  mov     [rsp+120h+var_A8], eax
0x180001758  call    cs:__imp_CoTaskMemAlloc
0x18000175e  mov     rcx, [rbp+20h+var_A0]
0x180001762  mov     [rcx+r12], rax
0x180001766  test    rax, rax
0x180001769  jz      loc_180001E8E
0x18000176f  mov     ecx, [rsp+120h+var_A8]
0x180001773  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180001779  mov     r8, [rbp+20h+lpMultiByteStr]; lpMultiByteStr
0x18000177d  xor     edx, edx; dwFlags
0x18000177f  shr     ecx, 1
0x180001781  mov     [rsp+120h+cchWideChar], ecx; cchWideChar
0x180001785  mov     ecx, 0FDE9h; CodePage
0x18000178a  mov     [rsp+120h+lpWideCharStr], rax; lpWideCharStr
0x18000178f  call    cs:__imp_MultiByteToWideChar
0x180001795  test    eax, eax
0x180001797  jz      loc_180001B52
0x18000179d  mov     rax, [rbp+20h+var_A0]
0x1800017a1  xor     edx, edx
0x1800017a3  mov     r14, [rax+r12]
0x1800017a7  mov     eax, [rsp+120h+var_B0]
0x1800017ab  mov     [rbp+20h+var_80], r14
0x1800017af  jmp     loc_18000184F
0x1800017b4  mov     eax, edi
0x1800017b6  sub     eax, 13h
0x1800017b9  jz      short loc_1800017C9
0x1800017bb  sub     eax, 35h ; '5'
0x1800017be  jz      short loc_1800017C9
0x1800017c0  sub     eax, 38h ; '8'
0x1800017c3  jnz     loc_180001FD1
0x1800017c9  mov     rcx, [r14+108h]
0x1800017d0  lea     rdx, [rbp+20h+var_98]
0x1800017d4  mov     r8, [rbp+20h+var_78]
0x1800017d8  movzx   eax, di
0x1800017db  mov     [rsp+120h+var_D0], rdx
0x1800017e0  or      ax, 4000h
0x1800017e4  mov     [rsp+74h], ax
0x1800017e9  lea     rdx, [rsp+120h+var_B0]
0x1800017ee  mov     [rsp+120h+var_D8], rdx
0x1800017f3  lea     eax, [rbx+1]
0x1800017f6  mov     [rbp+20h+var_98], eax
0x1800017f9  lea     rdx, [rsp+120h+var_A8]
0x1800017fe  mov     rax, [rcx]
0x180001801  mov     r9d, 1
0x180001807  mov     [rsp+120h+var_E0], rdx
0x18000180c  lea     rdx, [rbp+20h+var_90]
0x180001810  mov     [rsp+120h+var_E8], rdx
0x180001815  lea     rdx, [rbp+20h+var_80]
0x180001819  mov     [rsp+120h+var_F0], rdx
0x18000181e  lea     rdx, [rsp+74h]
0x180001823  mov     rax, [rax+40h]
0x180001827  mov     qword ptr [rsp+120h+cchWideChar], rdx
0x18000182c  mov     rdx, [r14+50h]
0x180001830  mov     dword ptr [rsp+120h+lpWideCharStr], 1
0x180001838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000183d  mov     r14, [rbp+20h+var_80]
0x180001841  lea     r12, ds:0[rsi*8]
0x180001849  mov     [rsp+120h+var_B0], eax
0x18000184d  xor     edx, edx
0x18000184f  test    eax, eax
0x180001851  js      loc_18000206E
0x180001857  cmp     eax, 3
0x18000185a  jz      loc_1800019A9
0x180001860  cmp     edi, 80h
0x180001866  jz      loc_180001E75
0x18000186c  mov     r9, [r13+0]
0x180001870  test    byte ptr [r9], 1
0x180001874  jnz     loc_180001A43
0x18000187a  cmp     byte ptr [r13+8], 0
0x18000187f  jge     loc_180001E13
0x180001885  cmp     ebx, [r9+4]
0x180001889  jnb     loc_18000201D
0x18000188f  mov     rcx, [r9+18h]
0x180001893  add     rcx, r15
0x180001896  mov     r10d, [rcx+8]
0x18000189a  mov     r15d, r10d
0x18000189d  and     r15d, 20000h
0x1800018a4  jnz     loc_180001DE3
0x1800018aa  cmp     dword ptr [rcx], 82h
0x1800018b0  jnz     loc_180001B06
0x1800018b6  test    r14, r14
0x1800018b9  jz      loc_180001B06
0x1800018bf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800018c6  nop     word ptr [rax+rax+00000000h]
0x1800018d0  cmp     word ptr [r14+rax*2+2], 0
0x1800018d7  lea     rax, [rax+1]
0x1800018db  jnz     short loc_1800018D0
0x1800018dd  lea     r8d, ds:2[rax*2]; Size
0x1800018e5  mov     eax, [rcx+4]
0x1800018e8  cmp     eax, 0FFFFFFFFh
0x1800018eb  jnz     loc_180001B21
0x1800018f1  mov     rcx, [r9+20h]
0x1800018f5  mov     edi, 0FFFFh
0x1800018fa  mov     rdx, [r13+20h]
0x1800018fe  mov     eax, [rcx+r12+4]
0x180001903  lea     r11, [rdx+rax*4]
0x180001907  movzx   eax, word ptr [rcx+r12+2]
0x18000190d  cmp     di, ax
0x180001910  jnz     loc_180001B6F
0x180001916  xor     esi, esi
0x180001918  movzx   edi, word ptr [rcx+r12]
0x18000191d  add     rdi, rdx
0x180001920  bt      r10d, 12h
0x180001925  jnb     loc_180001A55
0x18000192b  test    r11, r11
0x18000192e  jz      loc_180001EA1
0x180001934  mov     r10d, [r9+8Ch]
0x18000193b  xor     eax, eax
0x18000193d  nop     dword ptr [rax]
0x180001940  cmp     eax, r10d
0x180001943  jnb     short loc_180001960
0x180001945  mov     rcx, [r9+80h]
0x18000194c  mov     r8d, eax
0x18000194f  add     r8, r8
0x180001952  cmp     [rcx+r8*8], ebx
0x180001956  jz      loc_180002027
0x18000195c  inc     eax
0x18000195e  jmp     short loc_180001940
0x180001960  cmp     [r9+88h], r10d
0x180001967  jz      loc_180002034
0x18000196d  mov     [r11], r10d
0x180001970  mov     ecx, [r9+8Ch]
0x180001977  mov     rax, [r9+80h]
0x18000197e  add     rcx, rcx
0x180001981  mov     [rax+rcx*8], ebx
0x180001984  mov     ecx, [r9+8Ch]
0x18000198b  mov     rax, [r9+80h]
0x180001992  add     rcx, rcx
0x180001995  mov     [rax+rcx*8+8], r14
0x18000199a  inc     dword ptr [r9+8Ch]
0x1800019a1  and     byte ptr [rdi], 0CFh
0x1800019a4  jmp     loc_180001A65
0x1800019a9  mov     r8, [r13+0]
0x1800019ad  test    byte ptr [r8], 1
0x1800019b1  jnz     loc_180001B0F
0x1800019b7  cmp     byte ptr [r13+8], 0
0x1800019bc  jge     loc_180001E32
0x1800019c2  cmp     ebx, [r8+4]
0x1800019c6  jnb     loc_180001FF9
0x1800019cc  mov     rax, [r8+18h]
0x1800019d0  mov     r9d, 0FFFFh
0x1800019d6  mov     rdx, [r13+20h]
0x1800019da  mov     edi, [rax+r15+8]
0x1800019df  mov     rax, [r8+20h]
0x1800019e3  lea     rcx, [rax+rsi*8]
0x1800019e7  movzx   eax, word ptr [rax+rsi*8+2]
0x1800019ec  cmp     r9w, ax
0x1800019f0  jnz     loc_180001E0A
0x1800019f6  xor     r14d, r14d
  ... truncated ...
```
