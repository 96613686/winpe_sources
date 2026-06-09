# ResolveFromPreconnAttrs<tagDBC>(tagDBC *,CDlgATTRs &)

- ea: `0x1004e3a5c`
- end: `0x1004e45c5`
- name: `??$ResolveFromPreconnAttrs@UtagDBC@@@@YAJPEAUtagDBC@@AEAVCDlgATTRs@@@Z`
- size: `2921`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x1004ec470`

## callees

- `0x1004077c0`
- `0x10046d140`
- `0x1004e3a5c`
- `0x1004ec3fc`
- `0x100520370`
- `0x100546a24`
- `0x100546a7c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3cc0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3ce5`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3d07`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3e66`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3e92`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3ebe`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3ee7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3f10`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3f39`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e4167`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e417e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e4237`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e425b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e427f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e459f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3cc0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3ce5`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3d07`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3e66`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3e92`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3ebe`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3ee7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3f10`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e3f39`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e4167`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e417e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e4237`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e425b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e427f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e459f`

## string_xrefs

- `0x1004e3eb7`: `ActiveDirectoryIntegrated`
- `0x1004e3f09`: `ActiveDirectoryPassword`
- `0x1004e3e8b`: `ActiveDirectoryInteractive`
- `0x1004e3ee0`: `ActiveDirectoryMSI`
- `0x1004e3f32`: `ActiveDirectoryServicePrincipal`

## pseudocode

```c
__int64 __fastcall ResolveFromPreconnAttrs<tagDBC>(
        const unsigned __int16 **a1,
        CDlgATTRs *this,
        __int64 a3,
        __int64 a4)
{
  const unsigned __int16 *v4; // rbp
  __int64 v6; // rax
  unsigned int v8; // edi
  unsigned int v9; // r10d
  __int64 v10; // r11
  int v11; // ebx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  unsigned int v15; // r10d
  __int64 v16; // r14
  const unsigned __int16 *v17; // r8
  int v18; // eax
  unsigned int v19; // r12d
  unsigned int v20; // r8d
  int v21; // r14d
  __int64 v22; // r15
  unsigned int v23; // r10d
  const wchar_t *v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  bool v27; // cc
  wchar_t **v28; // rcx
  __int64 v29; // r8
  const unsigned __int16 *v30; // rbx
  unsigned int v31; // r15d
  unsigned int v32; // r8d
  int v33; // r14d
  __int64 v34; // rdx
  __int64 v35; // rcx
  const unsigned __int16 *v36; // rbx
  const unsigned __int16 *v37; // r8
  unsigned int v38; // r12d
  unsigned int v39; // r8d
  const unsigned __int16 *v40; // rbx
  const unsigned __int16 *v41; // r8
  const wchar_t *v42; // r15
  unsigned int v43; // r15d
  unsigned int v44; // r8d
  const unsigned __int16 *v45; // r8
  const unsigned __int16 *v46; // rbx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int16 v50; // ax
  __int16 v51; // ax
  __int16 v52; // ax
  unsigned __int16 v53; // bx
  __int64 v54; // rdx
  unsigned int v56; // [rsp+80h] [rbp+8h]
  int v57; // [rsp+88h] [rbp+10h]
  __int64 v58; // [rsp+98h] [rbp+20h]

  v4 = 0;
  v6 = 0;
  v56 = 0;
  v58 = 0;
  v8 = 0;
  v9 = 0;
  while ( 1 )
  {
    v10 = dword_1005A1300[3 * v6];
    v11 = dword_1005A1304[3 * v6];
    v12 = dword_1005A1308[3 * v6];
    if ( !v12 )
      break;
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
      {
        if ( (bidGblFlags & 2) != 0 )
          return (unsigned int)bidTraceHR(0, 393225, 2147549183LL, a4);
        else
          return (unsigned int)-2147418113;
      }
      v14 = v11 - 1178;
      v15 = v11 - 1178;
      if ( (unsigned int)(v11 - 1200) > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
        v15 = v11 - 1316;
      a4 = *((_QWORD *)this + 1);
      v16 = 3 * v10;
      if ( ((unsigned __int8)(1 << (v15 & 7)) & *((_BYTE *)a1 + ((unsigned __int64)v15 >> 3) + 1336)) != 0 )
      {
        *(_WORD *)(a4 + 24 * v10) |= 1u;
        if ( (unsigned int)(v11 - 1200) > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
          v14 = v11 - 1316;
        v18 = CDlgATTRs::SetATTRValue(this, v10, a1[v14 + 16]);
        v8 = v18;
        if ( v18 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            return v8;
          v47 = 379913;
          goto LABEL_126;
        }
        _mm_lfence();
        v9 = v56;
        if ( !*(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8 * v16 + 8) + *(_QWORD *)(*((_QWORD *)this + 2) + 32LL)) )
        {
          _mm_lfence();
          *(_WORD *)(*((_QWORD *)this + 1) + 8 * v16) |= 0x20u;
        }
        goto LABEL_13;
      }
      if ( (*(_BYTE *)(a4 + 24 * v10) & 1) == 0 )
        goto LABEL_12;
      v17 = (const unsigned __int16 *)(*(_QWORD *)(a4 + 24 * v10 + 8) + *(_QWORD *)(*((_QWORD *)this + 2) + 32LL));
      goto LABEL_11;
    }
    v19 = v11 - 1200;
    if ( (unsigned int)(v11 - 1200) <= 0x28 || (unsigned int)(v11 - 1241) <= 0x13 )
    {
      v20 = v11 - 1178;
      v21 = v11 - 1178;
    }
    else
    {
      v20 = v11 - 1316;
      v21 = v11 - 1178;
    }
    a4 = *((_QWORD *)this + 1);
    v22 = 3 * v10;
    v23 = v11 - 1241;
    if ( ((unsigned __int8)(1 << (v20 & 7)) & *((_BYTE *)a1 + ((unsigned __int64)v20 >> 3) + 1336)) == 0 )
    {
      if ( (*(_BYTE *)(a4 + 24 * v10) & 1) != 0 )
      {
        v24 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) + *(_QWORD *)(a4 + 24 * v10 + 8));
        if ( (_DWORD)v10 == 54 )
        {
          if ( v19 > 0x28 && v23 > 0x13 )
            v21 = v11 - 1316;
          v25 = _wcsicmp(v24, L"No") != 0;
          goto LABEL_32;
        }
        if ( !_wcsicmp(v24, L"Yes")
          || (v26 = _wcsicmp(
                      (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL)
                                      + *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v22 + 8)),
                      L"Enabled"),
              v25 = 0,
              !v26) )
        {
          v25 = 1;
        }
        if ( v19 > 0x28 )
        {
          v27 = (unsigned int)(v11 - 1241) <= 0x13;
          goto LABEL_38;
        }
        goto LABEL_32;
      }
      goto LABEL_12;
    }
    *(_WORD *)(a4 + 24 * v10) |= 1u;
    v28 = `ResolveFromPreconnAttrs<tagDBC>'::`64'::szValues;
    if ( (unsigned int)(v10 - 36) <= 1 )
      v28 = off_1005D1118;
    if ( v19 > 0x28 && v23 > 0x13 )
      v21 = v11 - 1316;
    v29 = 0;
    v30 = a1[v21 + 16];
    if ( v30 == (const unsigned __int16 *)1 )
      v29 = 1;
    v18 = CDlgATTRs::SetATTRValue(this, v10, v28[v29]);
    v8 = v18;
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v8;
      v47 = 354313;
LABEL_126:
      _mm_lfence();
      bidTraceHR(0, v47, (unsigned int)v18, a4);
      return v8;
    }
    _mm_lfence();
    v9 = v56;
    *(_WORD *)(*((_QWORD *)this + 1) + 8 * v22) = *(_WORD *)(*((_QWORD *)this + 1) + 8 * v22) & 0xFFDF
                                                | (v30 != (const unsigned __int16 *)1 ? 0x20 : 0);
LABEL_13:
    ++v9;
    v6 = v58 + 1;
    v56 = v9;
    ++v58;
    if ( v9 >= 0x14 )
    {
      v48 = *((_QWORD *)this + 1);
      if ( ((_BYTE)a1[168] & 0x20) != 0 )
      {
        *(_WORD *)(v48 + 744) |= 1u;
        v18 = CDlgATTRs::SetATTRValue(this, 31, a1[85]);
        v8 = v18;
        if ( v18 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v47 = 421897;
            goto LABEL_126;
          }
          return v8;
        }
        _mm_lfence();
        *(_WORD *)(*((_QWORD *)this + 1) + 744LL) = *(_WORD *)(*((_QWORD *)this + 1) + 744LL) & 0xFFDF
                                                  | ((unsigned int)StringToApplicationIntent((wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 1) + 752LL) + *(_QWORD *)(*((_QWORD *)this + 2) + 32LL))) == 0
                                                   ? 0x20
                                                   : 0);
      }
      else if ( (*(_BYTE *)(v48 + 744) & 1) != 0 )
      {
        SetPreconnAttr(
          (struct tagDBC *)a1,
          1247,
          (const unsigned __int16 *)(*(_QWORD *)(v48 + 752) + *(_QWORD *)(*((_QWORD *)this + 2) + 32LL)));
      }
      if ( (*((_BYTE *)a1 + 1342) & 1) != 0 )
      {
        *(_WORD *)(*((_QWORD *)this + 1) + 1368LL) |= 1u;
        v18 = CDlgATTRs::SetATTRValue(this, 57, a1[64]);
        v8 = v18;
        if ( v18 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v47 = 436233;
            goto LABEL_126;
          }
          return v8;
        }
      }
      v49 = *((_QWORD *)this + 1);
      v50 = *(_WORD *)(v49 + 432);
      if ( (v50 & 1) != 0 && (v50 & 0x20) == 0 )
      {
        v51 = *(_WORD *)(v49 + 264);
        if ( (v51 & 1) == 0 || (v51 & 0x20) != 0 )
        {
          v53 = -25088;
          if ( (bidGblFlags & 2) != 0 )
          {
            v54 = 448521;
            goto LABEL_159;
          }
LABEL_160:
          v8 = -2147467259;
          goto LABEL_161;
        }
        v52 = *(_WORD *)(v49 + 768);
        if ( (v52 & 1) != 0 && (v52 & 0x20) == 0 )
        {
          v53 = -25040;
          if ( (bidGblFlags & 2) != 0 )
          {
            v54 = 458761;
LABEL_159:
            v8 = bidTraceHR(0, v54, 2147500037LL, a4);
LABEL_161:
            if ( (bidGblFlags & 2) != 0 )
              bidTraceMark(0, 474121);
            PostSQLErrorEx((struct tagOBJBASE *)a1, v53, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
            return v8;
          }
          goto LABEL_160;
        }
      }
      LOBYTE(v4) = _wcsicmp(
                     (const wchar_t *)(*(_QWORD *)(v49 + 608) + *(_QWORD *)(*((_QWORD *)this + 2) + 32LL)),
                     L"Yes") == 0;
      a1[157] = v4;
      return v8;
    }
  }
  if ( (_DWORD)v10 == 38 )
  {
    v31 = v11 - 1200;
    if ( (unsigned int)(v11 - 1200) <= 0x28 || (unsigned int)(v11 - 1241) <= 0x13 )
    {
      v32 = v11 - 1178;
      v33 = v11 - 1178;
    }
    else
    {
      v32 = v11 - 1316;
      v33 = v11 - 1178;
    }
    a4 = (unsigned int)(v11 - 1241);
    if ( ((unsigned __int8)(1 << (v32 & 7)) & *((_BYTE *)a1 + ((unsigned __int64)v32 >> 3) + 1336)) == 0 )
    {
      v34 = *((_QWORD *)this + 1);
      if ( (*(_BYTE *)(v34 + 912) & 1) != 0 )
      {
        if ( _wcsicmp(
               (const wchar_t *)(*(_QWORD *)(v34 + 920) + *(_QWORD *)(*((_QWORD *)this + 2) + 32LL)),
               L"SqlPassword") )
        {
          if ( _wcsicmp(
                 (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)this + 1) + 920LL)),
                 L"ActiveDirectoryInteractive") )
          {
            if ( _wcsicmp(
                   (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL)
                                   + *(_QWORD *)(*((_QWORD *)this + 1) + 920LL)),
                   L"ActiveDirectoryIntegrated") )
            {
              if ( _wcsicmp(
                     (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL)
                                     + *(_QWORD *)(*((_QWORD *)this + 1) + 920LL)),
                     L"ActiveDirectoryMSI") )
              {
                if ( _wcsicmp(
                       (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL)
                                       + *(_QWORD *)(*((_QWORD *)this + 1) + 920LL)),
                       L"ActiveDirectoryPassword") )
                {
                  v35 = _wcsicmp(
                          (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL)
                                          + *(_QWORD *)(*((_QWORD *)this + 1) + 920LL)),
                          L"ActiveDirectoryServicePrincipal") == 0
                      ? 7
                      : 0;
                }
                else
                {
                  v35 = 3;
                }
              }
              else
              {
                v35 = 6;
              }
            }
            else
            {
              v35 = 2;
            }
          }
          else
          {
            v35 = 4;
          }
        }
        else
        {
          v35 = 1;
        }
        v9 = v56;
      }
      else
      {
        v35 = 0;
      }
      if ( v31 > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
        v33 = v11 - 1316;
      a1[v33 + 16] = (const unsigned __int16 *)v35;
      goto LABEL_13;
    }
    if ( v31 > 0x28 && (unsigned int)a4 > 0x13 )
      v33 = v11 - 1316;
    v36 = a1[v33 + 16];
    *(_WORD *)(*((_QWORD *)this + 1) + 912LL) = *(_WORD *)(*((_QWORD *)this + 1) + 912LL) & 0xFFFE | (v36 != 0);
    if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 912LL) & 1) != 0 )
      v37 = (const unsigned __int16 *)qword_1005D10E0[(_QWORD)v36];
    else
      v37 = 0;
    v18 = CDlgATTRs::SetATTRValue(this, 38, v37);
    v8 = v18;
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v8;
      v47 = 251913;
      goto LABEL_126;
    }
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)this + 1) + 912LL) = *(_WORD *)(*((_QWORD *)this + 1) + 912LL) & 0xFFDF
                                              | (v36 == 0 ? 0x20 : 0);
    goto LABEL_81;
  }
  if ( (_DWORD)v10 == 36 )
  {
    v38 = v11 - 1200;
    if ( (unsigned int)(v11 - 1200) > 0x28 )
    {
      v21 = v11 - 1178;
      v39 = v11 - 1178;
      if ( (unsigned int)(v11 - 1241) > 0x13 )
        v39 = v11 - 1316;
    }
    else
    {
      v39 = v11 - 1178;
      v21 = v11 - 1178;
    }
    if ( ((unsigned __int8)(1 << (v39 & 7)) & *((_BYTE *)a1 + ((unsigned __int64)v39 >> 3) + 1336)) != 0 )
    {
      if ( v38 > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
        v21 = v11 - 1316;
      v40 = a1[v21 + 16];
      v41 = v40;
      *(_WORD *)(*((_QWORD *)this + 1) + 864LL) |= 1u;
      if ( v40 == (const unsigned __int16 *)1 )
        v41 = L"Enabled";
      if ( !v40 )
        v41 = L"Disabled";
      v18 = CDlgATTRs::SetATTRValue(this, 36, v41);
      v8 = v18;
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v8;
        v47 = 269321;
        goto LABEL_126;
      }
      _mm_lfence();
      *(_WORD *)(*((_QWORD *)this + 1) + 864LL) = *(_WORD *)(*((_QWORD *)this + 1) + 864LL) & 0xFFDF
                                                | (v40 == 0 ? 0x20 : 0);
      goto LABEL_81;
    }
    v42 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)this + 1) + 872LL));
    v57 = _wcsicmp(v42, L"Enabled");
    if ( !_wcsicmp(v42, L"Disabled") || !v57 )
    {
      if ( v38 > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
        v21 = v11 - 1316;
      v25 = v57 == 0;
      goto LABEL_32;
    }
    v17 = v42;
LABEL_11:
    SetPreconnAttr((struct tagDBC *)a1, v11, v17);
    goto LABEL_12;
  }
  if ( (_DWORD)v10 != 15 )
    goto LABEL_13;
  v43 = v11 - 1200;
  v21 = v11 - 1178;
  v44 = v11 - 1178;
  if ( (unsigned int)(v11 - 1200) > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
    v44 = v11 - 1316;
  if ( ((unsigned __int8)(1 << (v44 & 7)) & *((_BYTE *)a1 + ((unsigned __int64)v44 >> 3) + 1336)) == 0 )
  {
    if ( _wcsicmp(
           (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 1) + 368LL) + *(_QWORD *)(*((_QWORD *)this + 2) + 32LL)),
           L"No")
      && _wcsicmp(
           (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)this + 1) + 368LL)),
           L"Optional") )
    {
      v25 = 2LL
          - (_wcsicmp(
               (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)this + 1) + 368LL)),
               L"Strict") != 0);
    }
    else
    {
      v25 = 0;
    }
    if ( v43 <= 0x28 )
      goto LABEL_32;
    v27 = (unsigned int)(v11 - 1241) <= 0x13;
LABEL_38:
    if ( !v27 )
      v21 = v11 - 1316;
LABEL_32:
    a1[v21 + 16] = (const unsigned __int16 *)v25;
LABEL_12:
    v9 = v56;
    goto LABEL_13;
  }
  if ( v43 > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
    v21 = v11 - 1316;
  v45 = L"Yes";
  v46 = a1[v21 + 16];
  *(_WORD *)(*((_QWORD *)this + 1) + 360LL) |= 1u;
  if ( v46 == (const unsigned __int16 *)2 )
    v45 = L"Strict";
  if ( !v46 )
    v45 = L"No";
  v18 = CDlgATTRs::SetATTRValue(this, 15, v45);
  v8 = v18;
  if ( v18 >= 0 )
  {
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)this + 1) + 360LL) = *(_WORD *)(*((_QWORD *)this + 1) + 360LL) & 0xFFDF
                                              | (v46 == 0 ? 0x20 : 0);
LABEL_81:
    v9 = v56;
    goto LABEL_13;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v47 = 311305;
    goto LABEL_126;
  }
  return v8;
}

```

## disassembly

```asm
0x1004e3a5c  push    rbx
0x1004e3a5e  push    rbp
0x1004e3a5f  push    rsi
0x1004e3a60  push    rdi
0x1004e3a61  push    r12
0x1004e3a63  push    r13
0x1004e3a65  push    r14
0x1004e3a67  push    r15
0x1004e3a69  sub     rsp, 38h
0x1004e3a6d  xor     ebp, ebp
0x1004e3a6f  mov     rsi, rdx
0x1004e3a72  mov     eax, ebp
0x1004e3a74  mov     [rsp+78h+arg_0], ebp
0x1004e3a7b  mov     r13, rcx
0x1004e3a7e  mov     [rsp+78h+arg_18], rax
0x1004e3a86  mov     edi, ebp
0x1004e3a88  mov     r10d, ebp
0x1004e3a8b  lea     r12d, [rbp+1]
0x1004e3a8f  mov     r14d, 0FFDFh
0x1004e3a95  lea     r15d, [rbp+20h]
0x1004e3a99  lea     rdx, __ImageBase
0x1004e3aa0  lea     rcx, [rax+rax*2]
0x1004e3aa4  movsxd  r11, ds:rva dword_1005A1300[rdx+rcx*4]
0x1004e3aac  mov     ebx, ds:rva dword_1005A1304[rdx+rcx*4]
0x1004e3ab3  mov     edx, ds:rva dword_1005A1308[rdx+rcx*4]
0x1004e3aba  test    edx, edx
0x1004e3abc  jz      loc_1004E3DD8
0x1004e3ac2  sub     edx, 1
0x1004e3ac5  jz      loc_1004E3C0F
0x1004e3acb  cmp     edx, 1
0x1004e3ace  jnz     loc_1004E436E
0x1004e3ad4  lea     r15d, [rbx-4B0h]
0x1004e3adb  lea     edx, [rbx-49Ah]
0x1004e3ae1  mov     r10d, edx
0x1004e3ae4  cmp     r15d, 28h ; '('
0x1004e3ae8  jbe     short loc_1004E3AFC
0x1004e3aea  lea     eax, [rbx-4D9h]
0x1004e3af0  cmp     eax, 13h
0x1004e3af3  jbe     short loc_1004E3AFC
0x1004e3af5  lea     r10d, [rbx-524h]
0x1004e3afc  mov     r9, [rsi+8]
0x1004e3b00  lea     r14, [r11+r11*2]
0x1004e3b04  mov     ecx, 0FFFFFB27h
0x1004e3b09  mov     eax, ebx
0x1004e3b0b  mov     eax, r10d
0x1004e3b0e  mov     r8d, 1
0x1004e3b14  shr     rax, 3
0x1004e3b18  lea     r12d, [rcx+rbx]
0x1004e3b1c  mov     ecx, r10d
0x1004e3b1f  and     ecx, 7
0x1004e3b22  shl     r8d, cl
0x1004e3b25  test    [rax+r13+538h], r8b
0x1004e3b2d  mov     eax, 1
0x1004e3b32  jnz     short loc_1004E3B9A
0x1004e3b34  test    [r9+r14*8], al
0x1004e3b38  jz      short loc_1004E3B51
0x1004e3b3a  mov     rax, [rsi+10h]
0x1004e3b3e  mov     r8, [rax+20h]
0x1004e3b42  add     r8, [r9+r14*8+8]; unsigned __int16 *
0x1004e3b47  mov     edx, ebx; int
0x1004e3b49  mov     rcx, r13; struct tagDBC *
0x1004e3b4c  call    ?SetPreconnAttr@@YAFPEAUtagDBC@@JPEBG@Z; SetPreconnAttr(tagDBC *,long,ushort const *)
0x1004e3b51  mov     r10d, [rsp+78h+arg_0]
0x1004e3b59  mov     r15d, 20h ; ' '
0x1004e3b5f  mov     r14d, 0FFDFh
0x1004e3b65  mov     rax, [rsp+78h+arg_18]
0x1004e3b6d  mov     ebx, 1
0x1004e3b72  add     r10d, ebx
0x1004e3b75  add     rax, rbx
0x1004e3b78  mov     [rsp+78h+arg_0], r10d
0x1004e3b80  mov     [rsp+78h+arg_18], rax
0x1004e3b88  cmp     r10d, 14h
0x1004e3b8c  jnb     loc_1004E43ED
0x1004e3b92  mov     r12d, ebx
0x1004e3b95  jmp     loc_1004E3A99
0x1004e3b9a  or      [r9+r14*8], ax
0x1004e3b9f  cmp     r15d, 28h ; '('
0x1004e3ba3  jbe     short loc_1004E3BB1
0x1004e3ba5  cmp     r12d, 13h
0x1004e3ba9  jbe     short loc_1004E3BB1
0x1004e3bab  lea     edx, [rbx-524h]
0x1004e3bb1  movsxd  r8, edx
0x1004e3bb4  mov     rcx, rsi; this
0x1004e3bb7  mov     edx, r11d; int
0x1004e3bba  mov     r8, [r13+r8*8+80h]; unsigned __int16 *
0x1004e3bc2  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e3bc7  mov     edi, eax
0x1004e3bc9  test    eax, eax
0x1004e3bcb  js      loc_1004E434A
0x1004e3bd1  lfence
0x1004e3bd4  mov     rcx, [rsi+8]
0x1004e3bd8  mov     r15d, 20h ; ' '
0x1004e3bde  mov     rdx, [rsi+10h]
0x1004e3be2  mov     r10d, [rsp+78h+arg_0]
0x1004e3bea  mov     r8, [rcx+r14*8+8]
0x1004e3bef  mov     rcx, [rdx+20h]
0x1004e3bf3  cmp     [r8+rcx], bp
0x1004e3bf8  jnz     loc_1004E3B5F
0x1004e3bfe  lfence
0x1004e3c01  mov     rcx, [rsi+8]
0x1004e3c05  or      [rcx+r14*8], r15w
0x1004e3c0a  jmp     loc_1004E3B5F
0x1004e3c0f  lea     r12d, [rbx-4B0h]
0x1004e3c16  cmp     r12d, 28h ; '('
0x1004e3c1a  ja      short loc_1004E3C28
0x1004e3c1c  lea     r8d, [rbx-49Ah]
0x1004e3c23  mov     r14d, r8d
0x1004e3c26  jmp     short loc_1004E3C41
0x1004e3c28  lea     eax, [rbx-4D9h]
0x1004e3c2e  cmp     eax, 13h
0x1004e3c31  jbe     short loc_1004E3C1C
0x1004e3c33  lea     r8d, [rbx-524h]
0x1004e3c3a  lea     r14d, [rbx-49Ah]
0x1004e3c41  mov     r9, [rsi+8]
0x1004e3c45  lea     r15, [r11+r11*2]
0x1004e3c49  mov     ecx, 0FFFFFB27h
0x1004e3c4e  mov     eax, ebx
0x1004e3c50  mov     eax, r8d
0x1004e3c53  mov     edx, 1
0x1004e3c58  shr     rax, 3
0x1004e3c5c  lea     r10d, [rbx+rcx]
0x1004e3c60  mov     ecx, r8d
0x1004e3c63  and     ecx, 7
0x1004e3c66  mov     [rsp+78h+arg_8], r10d
0x1004e3c6e  shl     edx, cl
0x1004e3c70  test    [rax+r13+538h], dl
0x1004e3c78  jnz     loc_1004E3D32
0x1004e3c7e  mov     eax, 1
0x1004e3c83  test    [r9+r15*8], al
0x1004e3c87  jz      loc_1004E3B51
0x1004e3c8d  mov     rax, [rsi+10h]
0x1004e3c91  mov     r8d, 20h ; ' '
0x1004e3c97  mov     rcx, [r9+r15*8+8]
0x1004e3c9c  add     rcx, [rax+r8]; String1
0x1004e3ca0  cmp     r11d, 36h ; '6'
0x1004e3ca4  jnz     short loc_1004E3CDE
0x1004e3ca6  cmp     r12d, 28h ; '('
0x1004e3caa  jbe     short loc_1004E3CB9
0x1004e3cac  cmp     r10d, 13h
0x1004e3cb0  jbe     short loc_1004E3CB9
0x1004e3cb2  lea     r14d, [rbx-524h]
0x1004e3cb9  lea     rdx, aNo; "No"
0x1004e3cc0  call    cs:__imp__wcsicmp
0x1004e3cc6  test    eax, eax
0x1004e3cc8  mov     rcx, rbp
0x1004e3ccb  setnz   cl
0x1004e3cce  movsxd  rax, r14d
0x1004e3cd1  mov     [r13+rax*8+80h], rcx
0x1004e3cd9  jmp     loc_1004E3B51
0x1004e3cde  lea     rdx, aYes_1; "Yes"
0x1004e3ce5  call    cs:__imp__wcsicmp
0x1004e3ceb  test    eax, eax
0x1004e3ced  jz      short loc_1004E3D14
0x1004e3cef  mov     rdx, [rsi+10h]
0x1004e3cf3  mov     rax, [rsi+8]
0x1004e3cf7  mov     rcx, [rax+r15*8+8]
0x1004e3cfc  add     rcx, [rdx+20h]; String1
0x1004e3d00  lea     rdx, aEnabled; "Enabled"
0x1004e3d07  call    cs:__imp__wcsicmp
0x1004e3d0d  mov     rcx, rbp
0x1004e3d10  test    eax, eax
0x1004e3d12  jnz     short loc_1004E3D19
0x1004e3d14  mov     ecx, 1
0x1004e3d19  cmp     r12d, 28h ; '('
0x1004e3d1d  jbe     short loc_1004E3CCE
0x1004e3d1f  cmp     [rsp+78h+arg_8], 13h
0x1004e3d27  jbe     short loc_1004E3CCE
0x1004e3d29  lea     r14d, [rbx-524h]
0x1004e3d30  jmp     short loc_1004E3CCE
0x1004e3d32  mov     edi, 1
0x1004e3d37  lea     eax, [r11-24h]
0x1004e3d3b  or      [r9+r15*8], di
0x1004e3d40  lea     rcx, ?szValues@?EA@???$ResolveFromPreconnAttrs@UtagDBC@@@@YAJPEAUtagDBC@@AEAVCDlgATTRs@@@Z@4PAY01PEBGA; ushort const * (near * `ResolveFromPreconnAttrs<tagDBC>(tagDBC *,CDlgATTRs &)'::`64'::szValues)[2]
0x1004e3d47  cmp     eax, edi
0x1004e3d49  lea     rdx, off_1005D1118; "Disabled"
0x1004e3d50  cmovbe  rcx, rdx
0x1004e3d54  cmp     r12d, 28h ; '('
0x1004e3d58  jbe     short loc_1004E3D67
0x1004e3d5a  cmp     r10d, 13h
0x1004e3d5e  jbe     short loc_1004E3D67
0x1004e3d60  lea     r14d, [rbx-524h]
0x1004e3d67  movsxd  rax, r14d
0x1004e3d6a  mov     r8, rbp
0x1004e3d6d  mov     edx, r11d; int
0x1004e3d70  mov     rbx, [r13+rax*8+80h]
0x1004e3d78  mov     eax, 8
0x1004e3d7d  cmp     rbx, rdi
0x1004e3d80  cmovz   r8, rax
0x1004e3d84  mov     r8, [r8+rcx]; unsigned __int16 *
0x1004e3d88  mov     rcx, rsi; this
0x1004e3d8b  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e3d90  mov     edi, eax
0x1004e3d92  test    eax, eax
0x1004e3d94  js      loc_1004E439A
0x1004e3d9a  lfence
0x1004e3d9d  mov     rdx, [rsi+8]
0x1004e3da1  dec     rbx
0x1004e3da4  mov     r10d, [rsp+78h+arg_0]
0x1004e3dac  neg     rbx
0x1004e3daf  mov     r14d, 0FFDFh
0x1004e3db5  sbb     cx, cx
0x1004e3db8  movzx   eax, word ptr [rdx+r15*8]
0x1004e3dbd  and     cx, 20h
0x1004e3dc1  and     ax, r14w
0x1004e3dc5  or      cx, ax
0x1004e3dc8  mov     [rdx+r15*8], cx
0x1004e3dcd  mov     r15d, 20h ; ' '
0x1004e3dd3  jmp     loc_1004E3B65
0x1004e3dd8  cmp     r11d, 26h ; '&'
0x1004e3ddc  jnz     loc_1004E403E
0x1004e3de2  lea     r15d, [rbx-4B0h]
0x1004e3de9  cmp     r15d, 28h ; '('
0x1004e3ded  ja      short loc_1004E3DFB
0x1004e3def  lea     r8d, [rbx-49Ah]
0x1004e3df6  mov     r14d, r8d
0x1004e3df9  jmp     short loc_1004E3E14
0x1004e3dfb  lea     eax, [rbx-4D9h]
0x1004e3e01  cmp     eax, 13h
0x1004e3e04  jbe     short loc_1004E3DEF
0x1004e3e06  lea     r8d, [rbx-524h]
0x1004e3e0d  lea     r14d, [rbx-49Ah]
0x1004e3e14  mov     ecx, 0FFFFFB27h
0x1004e3e19  mov     eax, ebx
0x1004e3e1b  mov     eax, r8d
0x1004e3e1e  mov     edx, r12d
0x1004e3e21  shr     rax, 3
0x1004e3e25  lea     r9d, [rcx+rbx]
0x1004e3e29  mov     ecx, r8d
0x1004e3e2c  and     ecx, 7
0x1004e3e2f  shl     edx, cl
0x1004e3e31  test    [rax+r13+538h], dl
0x1004e3e39  jnz     loc_1004E3F7F
0x1004e3e3f  mov     rdx, [rsi+8]
0x1004e3e43  test    [rdx+390h], r12b
0x1004e3e4a  jz      loc_1004E3F54
0x1004e3e50  mov     rax, [rsi+10h]
0x1004e3e54  mov     rcx, [rax+20h]
0x1004e3e58  add     rcx, [rdx+398h]; String1
0x1004e3e5f  lea     rdx, aSqlpassword; "SqlPassword"
0x1004e3e66  call    cs:__imp__wcsicmp
0x1004e3e6c  test    eax, eax
0x1004e3e6e  jnz     short loc_1004E3E78
0x1004e3e70  mov     rcx, r12
0x1004e3e73  jmp     loc_1004E3F4A
0x1004e3e78  mov     rdx, [rsi+10h]
0x1004e3e7c  mov     rax, [rsi+8]
0x1004e3e80  mov     rcx, [rax+398h]
0x1004e3e87  add     rcx, [rdx+20h]; String1
0x1004e3e8b  lea     rdx, aActivedirector; "ActiveDirectoryInteractive"
0x1004e3e92  call    cs:__imp__wcsicmp
0x1004e3e98  test    eax, eax
0x1004e3e9a  jnz     short loc_1004E3EA4
0x1004e3e9c  lea     ecx, [rax+4]
0x1004e3e9f  jmp     loc_1004E3F4A
0x1004e3ea4  mov     rdx, [rsi+10h]
0x1004e3ea8  mov     rax, [rsi+8]
0x1004e3eac  mov     rcx, [rax+398h]
0x1004e3eb3  add     rcx, [rdx+20h]; String1
0x1004e3eb7  lea     rdx, aActivedirector_1; "ActiveDirectoryIntegrated"
0x1004e3ebe  call    cs:__imp__wcsicmp
0x1004e3ec4  test    eax, eax
0x1004e3ec6  jnz     short loc_1004E3ECD
0x1004e3ec8  lea     ecx, [rax+2]
0x1004e3ecb  jmp     short loc_1004E3F4A
0x1004e3ecd  mov     rdx, [rsi+10h]
0x1004e3ed1  mov     rax, [rsi+8]
0x1004e3ed5  mov     rcx, [rax+398h]
0x1004e3edc  add     rcx, [rdx+20h]; String1
0x1004e3ee0  lea     rdx, aActivedirector_3; "ActiveDirectoryMSI"
0x1004e3ee7  call    cs:__imp__wcsicmp
0x1004e3eed  test    eax, eax
0x1004e3eef  jnz     short loc_1004E3EF6
0x1004e3ef1  lea     ecx, [rax+6]
0x1004e3ef4  jmp     short loc_1004E3F4A
0x1004e3ef6  mov     rdx, [rsi+10h]
0x1004e3efa  mov     rax, [rsi+8]
0x1004e3efe  mov     rcx, [rax+398h]
0x1004e3f05  add     rcx, [rdx+20h]; String1
0x1004e3f09  lea     rdx, aActivedirector_2; "ActiveDirectoryPassword"
0x1004e3f10  call    cs:__imp__wcsicmp
0x1004e3f16  test    eax, eax
0x1004e3f18  jnz     short loc_1004E3F1F
0x1004e3f1a  lea     ecx, [rax+3]
0x1004e3f1d  jmp     short loc_1004E3F4A
0x1004e3f1f  mov     rdx, [rsi+10h]
0x1004e3f23  mov     rax, [rsi+8]
0x1004e3f27  mov     rcx, [rax+398h]
0x1004e3f2e  add     rcx, [rdx+20h]; String1
0x1004e3f32  lea     rdx, aActivedirector_0; "ActiveDirectoryServicePrincipal"
0x1004e3f39  call    cs:__imp__wcsicmp
0x1004e3f3f  neg     eax
0x1004e3f41  sbb     rcx, rcx
0x1004e3f44  not     rcx
0x1004e3f47  and     ecx, 7
0x1004e3f4a  mov     r10d, [rsp+78h+arg_0]
0x1004e3f52  jmp     short loc_1004E3F57
0x1004e3f54  mov     rcx, rbp
0x1004e3f57  cmp     r15d, 28h ; '('
0x1004e3f5b  jbe     short loc_1004E3F6F
0x1004e3f5d  lea     eax, [rbx-4D9h]
  ... truncated ...
```
