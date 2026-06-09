# ResolveFromPreconnAttrs<tagDbcInfoToken>(tagDbcInfoToken *,CDlgATTRs &)

- ea: `0x100493f3c`
- end: `0x100494bb2`
- name: `??$ResolveFromPreconnAttrs@UtagDbcInfoToken@@@@YAJPEAUtagDbcInfoToken@@AEAVCDlgATTRs@@@Z`
- size: `3190`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x100495b60`

## callees

- `0x1004077c0`
- `0x10046d140`
- `0x10048afc4`
- `0x100493f3c`
- `0x100520370`
- `0x100546a24`
- `0x100546a7c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004941f3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494220`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494242`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004943ab`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004943d7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494403`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10049442c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494455`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10049447e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004946b3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004946ca`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004947dc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494800`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494824`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494b8b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004941f3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494220`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494242`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004943ab`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004943d7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494403`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10049442c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494455`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10049447e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004946b3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004946ca`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004947dc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494800`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494824`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100494b8b`

## string_xrefs

- `0x1004943fc`: `ActiveDirectoryIntegrated`
- `0x10049444e`: `ActiveDirectoryPassword`
- `0x1004943d0`: `ActiveDirectoryInteractive`
- `0x100494425`: `ActiveDirectoryMSI`
- `0x100494477`: `ActiveDirectoryServicePrincipal`

## pseudocode

```c
__int64 __fastcall ResolveFromPreconnAttrs<tagDbcInfoToken>(__int64 a1, CDlgATTRs *a2)
{
  __int64 v2; // r12
  __int64 v3; // rbp
  __int64 v4; // rax
  __int64 v6; // r13
  __int64 v7; // r9
  unsigned int v8; // edi
  unsigned int v9; // r10d
  __int64 v10; // r11
  int v11; // ebx
  int v12; // edx
  int v13; // edx
  unsigned int v14; // r15d
  int v15; // r10d
  __int64 v16; // r13
  __int64 v17; // r14
  __int64 v18; // r8
  unsigned int v19; // r12d
  __int64 v20; // rax
  __int64 v21; // r9
  int v22; // eax
  unsigned int v23; // r12d
  unsigned int v24; // r8d
  int v25; // r14d
  __int64 v26; // r15
  unsigned int v27; // r13d
  const wchar_t *v28; // rcx
  _BOOL8 v29; // rcx
  int v30; // eax
  wchar_t **v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rbx
  unsigned int v34; // r15d
  unsigned int v35; // r8d
  int v36; // r14d
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rbx
  const unsigned __int16 *v40; // r8
  unsigned int v41; // r15d
  unsigned int v42; // r8d
  unsigned int v43; // r13d
  const unsigned __int16 *v44; // rbx
  const unsigned __int16 *v45; // r8
  const wchar_t *v46; // r12
  __int64 v47; // r9
  unsigned int v48; // r15d
  int v49; // r14d
  unsigned int v50; // r8d
  __int64 v51; // rcx
  const unsigned __int16 *v52; // r8
  __int64 v53; // rbx
  __int64 v54; // rdx
  __int64 v55; // r10
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  __int16 v60; // ax
  __int16 v61; // ax
  __int16 v62; // ax
  unsigned __int16 v63; // bx
  __int64 v64; // rdx
  __int64 v66; // [rsp+30h] [rbp-58h]
  unsigned int v68; // [rsp+98h] [rbp+10h]
  int v69; // [rsp+A0h] [rbp+18h]
  __int64 v70; // [rsp+A8h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 72);
  v3 = 0;
  v4 = 0;
  v70 = v2;
  v68 = 0;
  v6 = a1;
  v66 = 0;
  v7 = 1;
  v8 = 0;
  v9 = 0;
  while ( 1 )
  {
    v10 = dword_10059D540[3 * v4];
    v11 = dword_10059D544[3 * v4];
    v12 = dword_10059D548[3 * v4];
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
        {
          if ( (bidGblFlags & 2) != 0 )
            return (unsigned int)bidTraceHR(0, 393225, 2147549183LL, 1);
          else
            return (unsigned int)-2147418113;
        }
        v14 = v11 - 1200;
        v15 = v11 - 1178;
        v7 = (unsigned int)(v11 - 1178);
        if ( (unsigned int)(v11 - 1200) > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
          v7 = (unsigned int)(v11 - 1316);
        v16 = *(_QWORD *)(v6 + 72);
        v17 = 3 * v10;
        v18 = *((_QWORD *)a2 + 1);
        v19 = v11 - 1241;
        if ( ((unsigned __int8)(1 << (v7 & 7)) & *(_BYTE *)(((unsigned __int64)(unsigned int)v7 >> 3) + v16 + 14288)) != 0 )
        {
          *(_WORD *)(v18 + 24 * v10) |= 1u;
          if ( v14 > 0x28 && v19 > 0x13 )
            v15 = v11 - 1316;
          v2 = v70;
          v22 = CDlgATTRs::SetATTRValue(a2, v10, *(const unsigned __int16 **)(v70 + 8LL * v15 + 1888));
          v8 = v22;
          if ( v22 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              return v8;
            v54 = 379913;
            goto LABEL_138;
          }
          _mm_lfence();
          if ( !*(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v17 + 8) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)) )
          {
            _mm_lfence();
            *(_WORD *)(*((_QWORD *)a2 + 1) + 8 * v17) |= 0x20u;
          }
        }
        else
        {
          if ( (*(_BYTE *)(v18 + 24 * v10) & 1) != 0 )
          {
            v20 = *((_QWORD *)a2 + 2);
            if ( v14 > 0x28 && v19 > 0x13 )
              v15 = v11 - 1316;
            v21 = -1;
            do
              ++v21;
            while ( *(_WORD *)(*(_QWORD *)(v18 + 24 * v10 + 8) + *(_QWORD *)(v20 + 32) + 2 * v21) );
            ResolvedConnectionInfo::SetMappedConnAttr(
              v16,
              (unsigned int)v15,
              *(_QWORD *)(v18 + 24 * v10 + 8) + *(_QWORD *)(v20 + 32),
              2 * v21,
              2);
          }
          v2 = v70;
        }
        goto LABEL_17;
      }
      v23 = v11 - 1200;
      if ( (unsigned int)(v11 - 1200) <= 0x28 || (unsigned int)(v11 - 1241) <= 0x13 )
      {
        v24 = v11 - 1178;
        v25 = v11 - 1178;
      }
      else
      {
        v24 = v11 - 1316;
        v25 = v11 - 1178;
      }
      v7 = *((_QWORD *)a2 + 1);
      v26 = 3 * v10;
      v27 = v11 - 1241;
      if ( ((unsigned __int8)(1 << (v24 & 7)) & *(_BYTE *)(((unsigned __int64)v24 >> 3) + *(_QWORD *)(a1 + 72) + 14288)) != 0 )
      {
        *(_WORD *)(v7 + 24 * v10) |= 1u;
        v31 = `ResolveFromPreconnAttrs<tagDbcInfoToken>'::`64'::szValues;
        if ( (unsigned int)(v10 - 36) <= 1 )
          v31 = off_1005D0768;
        if ( v23 > 0x28 && v27 > 0x13 )
          v25 = v11 - 1316;
        v2 = v70;
        v32 = 0;
        v33 = *(_QWORD *)(v70 + 8LL * v25 + 1888);
        if ( v33 == 1 )
          v32 = 1;
        v22 = CDlgATTRs::SetATTRValue(a2, v10, v31[v32]);
        v8 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            return v8;
          v54 = 354313;
          goto LABEL_138;
        }
        _mm_lfence();
        *(_WORD *)(*((_QWORD *)a2 + 1) + 8 * v26) = *(_WORD *)(*((_QWORD *)a2 + 1) + 8 * v26) & 0xFFDF
                                                  | (v33 != 1 ? 0x20 : 0);
LABEL_17:
        v6 = a1;
LABEL_18:
        v9 = v68;
        goto LABEL_19;
      }
      if ( (*(_BYTE *)(v7 + 24 * v10) & 1) != 0 )
      {
        v28 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v7 + 24 * v10 + 8));
        if ( (_DWORD)v10 == 54 )
        {
          if ( v23 > 0x28 && v27 > 0x13 )
            v25 = v11 - 1316;
          v29 = _wcsicmp(v28, L"No") != 0;
        }
        else
        {
          if ( !_wcsicmp(v28, L"Yes")
            || (v30 = _wcsicmp(
                        (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)
                                        + *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v26 + 8)),
                        L"Enabled"),
                v29 = 0,
                !v30) )
          {
            v29 = 1;
          }
          if ( v23 > 0x28 && v27 > 0x13 )
            v25 = v11 - 1316;
        }
        goto LABEL_38;
      }
      v2 = v70;
      v6 = a1;
      goto LABEL_19;
    }
    if ( (_DWORD)v10 == 38 )
    {
      v34 = v11 - 1200;
      if ( (unsigned int)(v11 - 1200) <= 0x28 || (unsigned int)(v11 - 1241) <= 0x13 )
      {
        v35 = v11 - 1178;
        v36 = v11 - 1178;
      }
      else
      {
        v35 = v11 - 1316;
        v36 = v11 - 1178;
      }
      v7 = (unsigned int)(v11 - 1241);
      if ( ((unsigned __int8)(1 << (v35 & 7)) & *(_BYTE *)(((unsigned __int64)v35 >> 3) + *(_QWORD *)(v6 + 72) + 14288)) != 0 )
      {
        if ( v34 > 0x28 && (unsigned int)v7 > 0x13 )
          v36 = v11 - 1316;
        v39 = *(_QWORD *)(v2 + 8LL * v36 + 1888);
        *(_WORD *)(*((_QWORD *)a2 + 1) + 912LL) = *(_WORD *)(*((_QWORD *)a2 + 1) + 912LL) & 0xFFFE | (v39 != 0);
        if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 912LL) & 1) != 0 )
          v40 = *(const unsigned __int16 **)&aDefault_3[4 * v39 + 4];
        else
          v40 = 0;
        v22 = CDlgATTRs::SetATTRValue(a2, 38, v40);
        v8 = v22;
        if ( v22 >= 0 )
        {
          _mm_lfence();
          *(_WORD *)(*((_QWORD *)a2 + 1) + 912LL) = *(_WORD *)(*((_QWORD *)a2 + 1) + 912LL) & 0xFFDF
                                                  | (v39 == 0 ? 0x20 : 0);
          goto LABEL_18;
        }
        if ( (bidGblFlags & 2) == 0 )
          return v8;
        v54 = 251913;
LABEL_138:
        _mm_lfence();
        bidTraceHR(0, v54, (unsigned int)v22, v7);
        return v8;
      }
      v37 = *((_QWORD *)a2 + 1);
      if ( (*(_BYTE *)(v37 + 912) & 1) != 0 )
      {
        if ( _wcsicmp(
               (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v37 + 920)),
               L"SqlPassword") )
        {
          if ( _wcsicmp(
                 (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
                 L"ActiveDirectoryInteractive") )
          {
            if ( _wcsicmp(
                   (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
                   L"ActiveDirectoryIntegrated") )
            {
              if ( _wcsicmp(
                     (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
                     L"ActiveDirectoryMSI") )
              {
                if ( _wcsicmp(
                       (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL)
                                       + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
                       L"ActiveDirectoryPassword") )
                {
                  v38 = _wcsicmp(
                          (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL)
                                          + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
                          L"ActiveDirectoryServicePrincipal") == 0
                      ? 7
                      : 0;
                }
                else
                {
                  v38 = 3;
                }
              }
              else
              {
                v38 = 6;
              }
            }
            else
            {
              v38 = 2;
            }
          }
          else
          {
            v38 = 4;
          }
        }
        else
        {
          v38 = 1;
        }
        v9 = v68;
      }
      else
      {
        v38 = 0;
      }
      if ( v34 > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
        v36 = v11 - 1316;
      *(_QWORD *)(v2 + 8LL * v36 + 1888) = v38;
      goto LABEL_19;
    }
    if ( (_DWORD)v10 == 36 )
    {
      v41 = v11 - 1200;
      if ( (unsigned int)(v11 - 1200) > 0x28 )
      {
        v25 = v11 - 1178;
        v42 = v11 - 1178;
        if ( (unsigned int)(v11 - 1241) > 0x13 )
          v42 = v11 - 1316;
      }
      else
      {
        v42 = v11 - 1178;
        v25 = v11 - 1178;
      }
      v43 = v11 - 1241;
      if ( ((unsigned __int8)(1 << (v42 & 7)) & *(_BYTE *)(((unsigned __int64)v42 >> 3) + *(_QWORD *)(a1 + 72) + 14288)) != 0 )
      {
        if ( v41 > 0x28 && v43 > 0x13 )
          v25 = v11 - 1316;
        v44 = *(const unsigned __int16 **)(v2 + 8LL * v25 + 1888);
        v45 = v44;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 864LL) |= 1u;
        if ( v44 == (const unsigned __int16 *)1 )
          v45 = L"Enabled";
        if ( !v44 )
          v45 = L"Disabled";
        v22 = CDlgATTRs::SetATTRValue(a2, 36, v45);
        v8 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            return v8;
          v54 = 269321;
          goto LABEL_138;
        }
        _mm_lfence();
        *(_WORD *)(*((_QWORD *)a2 + 1) + 864LL) = *(_WORD *)(*((_QWORD *)a2 + 1) + 864LL) & 0xFFDF
                                                | (v44 == 0 ? 0x20 : 0);
        goto LABEL_17;
      }
      v46 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)a2 + 1) + 872LL));
      v69 = _wcsicmp(v46, L"Enabled");
      if ( _wcsicmp(v46, L"Disabled") && v69 )
      {
        if ( v41 > 0x28 && v43 > 0x13 )
          v25 = v11 - 1316;
        v47 = -1;
        do
          ++v47;
        while ( v46[v47] );
        v6 = a1;
        ResolvedConnectionInfo::SetMappedConnAttr(*(_QWORD *)(a1 + 72), (unsigned int)v25, v46, 2 * v47, 2);
        v2 = v70;
        goto LABEL_18;
      }
      if ( v41 > 0x28 && v43 > 0x13 )
        v25 = v11 - 1316;
      v29 = v69 == 0;
LABEL_38:
      v2 = v70;
      *(_QWORD *)(v70 + 8LL * v25 + 1888) = v29;
      goto LABEL_17;
    }
    if ( (_DWORD)v10 == 15 )
      break;
LABEL_19:
    ++v9;
    v4 = v66 + 1;
    v68 = v9;
    ++v66;
    if ( v9 >= 0x14 )
    {
      v55 = *(_QWORD *)(v6 + 72);
      v56 = *((_QWORD *)a2 + 1);
      if ( (*(_BYTE *)(v55 + 14296) & 0x20) != 0 )
      {
        *(_WORD *)(v56 + 744) |= 1u;
        v22 = CDlgATTRs::SetATTRValue(a2, 31, *(const unsigned __int16 **)(v2 + 2440));
        v8 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v54 = 421897;
            goto LABEL_138;
          }
          return v8;
        }
        _mm_lfence();
        *(_WORD *)(*((_QWORD *)a2 + 1) + 744LL) = *(_WORD *)(*((_QWORD *)a2 + 1) + 744LL) & 0xFFDF
                                                | ((unsigned int)StringToApplicationIntent((wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 752LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL))) == 0
                                                 ? 0x20
                                                 : 0);
      }
      else if ( (*(_BYTE *)(v56 + 744) & 1) != 0 )
      {
        v57 = *(_QWORD *)(v56 + 752) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
        v58 = -1;
        do
          ++v58;
        while ( *(_WORD *)(v57 + 2 * v58) );
        ResolvedConnectionInfo::SetMappedConnAttr(v55, 69, v57, 2 * v58, 2);
      }
      if ( (*(_BYTE *)(*(_QWORD *)(v6 + 72) + 14294LL) & 1) != 0 )
      {
        *(_WORD *)(*((_QWORD *)a2 + 1) + 1368LL) |= 1u;
        v22 = CDlgATTRs::SetATTRValue(a2, 57, *(const unsigned __int16 **)(v2 + 2272));
        v8 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v54 = 436233;
            goto LABEL_138;
          }
          return v8;
        }
      }
      v59 = *((_QWORD *)a2 + 1);
      v60 = *(_WORD *)(v59 + 432);
      if ( (v60 & 1) != 0 && (v60 & 0x20) == 0 )
      {
        v61 = *(_WORD *)(v59 + 264);
        if ( (v61 & 1) == 0 || (v61 & 0x20) != 0 )
        {
          v63 = -25088;
          if ( (bidGblFlags & 2) != 0 )
          {
            v64 = 448521;
            goto LABEL_173;
          }
LABEL_174:
          v8 = -2147467259;
          goto LABEL_175;
        }
        v62 = *(_WORD *)(v59 + 768);
        if ( (v62 & 1) != 0 && (v62 & 0x20) == 0 )
        {
          v63 = -25040;
          if ( (bidGblFlags & 2) != 0 )
          {
            v64 = 458761;
LABEL_173:
            v8 = bidTraceHR(0, v64, 2147500037LL, v7);
LABEL_175:
            if ( (bidGblFlags & 2) != 0 )
              bidTraceMark(0, 474121);
            PostSQLErrorEx((struct tagOBJBASE *)v6, v63, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
            return v8;
          }
          goto LABEL_174;
        }
      }
      LOBYTE(v3) = _wcsicmp((const wchar_t *)(*(_QWORD *)(v59 + 608) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)), L"Yes") == 0;
      *(_QWORD *)(v2 + 3016) = v3;
      return v8;
    }
    v7 = 1;
  }
  v48 = v11 - 1200;
  v49 = v11 - 1178;
  v50 = v11 - 1178;
  if ( (unsigned int)(v11 - 1200) > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
    v50 = v11 - 1316;
  if ( ((unsigned __int8)(1 << (v50 & 7)) & *(_BYTE *)(((unsigned __int64)v50 >> 3) + *(_QWORD *)(v6 + 72) + 14288)) == 0 )
  {
    if ( _wcsicmp(
           (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)a2 + 1) + 368LL)),
           L"No")
      && _wcsicmp(
           (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)a2 + 1) + 368LL)),
           L"Optional") )
    {
      v51 = 2LL
          - (_wcsicmp(
               (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)a2 + 1) + 368LL)),
               L"Strict") != 0);
    }
    else
    {
      v51 = 0;
    }
    if ( v48 > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
      v49 = v11 - 1316;
    *(_QWORD *)(v2 + 8LL * v49 + 1888) = v51;
    goto LABEL_18;
  }
  if ( v48 > 0x28 && (unsigned int)(v11 - 1241) > 0x13 )
    v49 = v11 - 1316;
  v52 = L"Yes";
  v53 = *(_QWORD *)(v2 + 8LL * v49 + 1888);
  *(_WORD *)(*((_QWORD *)a2 + 1) + 360LL) |= 1u;
  if ( v53 == 2 )
    v52 = L"Strict";
  if ( !v53 )
    v52 = L"No";
  v22 = CDlgATTRs::SetATTRValue(a2, 15, v52);
  v8 = v22;
  if ( v22 >= 0 )
  {
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)a2 + 1) + 360LL) = *(_WORD *)(*((_QWORD *)a2 + 1) + 360LL) & 0xFFDF | (v53 == 0 ? 0x20 : 0);
    goto LABEL_18;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v54 = 311305;
    goto LABEL_138;
  }
  return v8;
}

```

## disassembly

```asm
0x100493f3c  mov     [rsp+arg_0], rcx
0x100493f41  push    rbx
0x100493f42  push    rbp
0x100493f43  push    rsi
0x100493f44  push    rdi
0x100493f45  push    r12
0x100493f47  push    r13
0x100493f49  push    r14
0x100493f4b  push    r15
0x100493f4d  sub     rsp, 48h
0x100493f51  mov     r12, [rcx+48h]
0x100493f55  xor     ebp, ebp
0x100493f57  mov     eax, ebp
0x100493f59  mov     [rsp+88h+arg_18], r12
0x100493f61  mov     rsi, rdx
0x100493f64  mov     [rsp+88h+arg_8], ebp
0x100493f6b  mov     r13, rcx
0x100493f6e  mov     [rsp+88h+var_58], rax
0x100493f73  lea     r9d, [rbp+1]
0x100493f77  mov     edi, ebp
0x100493f79  lea     r14d, [rbp+20h]
0x100493f7d  mov     r10d, ebp
0x100493f80  mov     r15d, 0FFDFh
0x100493f86  lea     rdx, __ImageBase
0x100493f8d  lea     rcx, [rax+rax*2]
0x100493f91  movsxd  r11, ds:rva dword_10059D540[rdx+rcx*4]
0x100493f99  mov     ebx, ds:rva dword_10059D544[rdx+rcx*4]
0x100493fa0  mov     edx, ds:rva dword_10059D548[rdx+rcx*4]
0x100493fa7  test    edx, edx
0x100493fa9  jz      loc_100494314
0x100493faf  sub     edx, 1
0x100493fb2  jz      loc_100494140
0x100493fb8  cmp     edx, 1
0x100493fbb  jnz     loc_100494938
0x100493fc1  lea     r15d, [rbx-4B0h]
0x100493fc8  lea     r10d, [rbx-49Ah]
0x100493fcf  mov     r9d, r10d
0x100493fd2  cmp     r15d, 28h ; '('
0x100493fd6  jbe     short loc_100493FEA
0x100493fd8  lea     eax, [rbx-4D9h]
0x100493fde  cmp     eax, 13h
0x100493fe1  jbe     short loc_100493FEA
0x100493fe3  lea     r9d, [rbx-524h]
0x100493fea  mov     r13, [r13+48h]
0x100493fee  lea     r14, [r11+r11*2]
0x100493ff2  mov     r8, [rsi+8]
0x100493ff6  mov     ecx, 0FFFFFB27h
0x100493ffb  mov     eax, ebx
0x100493ffd  mov     edx, 1
0x100494002  mov     eax, r9d
0x100494005  shr     rax, 3
0x100494009  lea     r12d, [rcx+rbx]
0x10049400d  mov     ecx, r9d
0x100494010  and     ecx, 7
0x100494013  shl     edx, cl
0x100494015  test    [rax+r13+37D0h], dl
0x10049401d  mov     eax, 1
0x100494022  jnz     loc_1004940C8
0x100494028  test    [r8+r14*8], al
0x10049402c  jz      short loc_100494075
0x10049402e  mov     rax, [rsi+10h]
0x100494032  mov     rcx, [rax+20h]
0x100494036  add     rcx, [r8+r14*8+8]
0x10049403b  cmp     r15d, 28h ; '('
0x10049403f  jbe     short loc_10049404E
0x100494041  cmp     r12d, 13h
0x100494045  jbe     short loc_10049404E
0x100494047  lea     r10d, [rbx-524h]
0x10049404e  or      r9, 0FFFFFFFFFFFFFFFFh
0x100494052  inc     r9
0x100494055  cmp     [rcx+r9*2], bp
0x10049405a  jnz     short loc_100494052
0x10049405c  mov     r8, rcx
0x10049405f  mov     [rsp+88h+var_68], 2; unsigned int
0x100494067  mov     rcx, r13
0x10049406a  add     r9, r9
0x10049406d  mov     edx, r10d
0x100494070  call    ?SetMappedConnAttr@ResolvedConnectionInfo@@QEAAJJ_K_KW4ATTR_VALUE_TYPE@@@Z; ResolvedConnectionInfo::SetMappedConnAttr(long,unsigned __int64,unsigned __int64,ATTR_VALUE_TYPE)
0x100494075  mov     r12, [rsp+88h+arg_18]
0x10049407d  mov     r14d, 20h ; ' '
0x100494083  mov     r15d, 0FFDFh
0x100494089  mov     r13, [rsp+88h+arg_0]
0x100494091  mov     r10d, [rsp+88h+arg_8]
0x100494099  mov     rax, [rsp+88h+var_58]
0x10049409e  mov     ebx, 1
0x1004940a3  add     r10d, ebx
0x1004940a6  add     rax, rbx
0x1004940a9  mov     [rsp+88h+arg_8], r10d
0x1004940b1  mov     [rsp+88h+var_58], rax
0x1004940b6  cmp     r10d, 14h
0x1004940ba  jnb     loc_1004949B7
0x1004940c0  mov     r9d, ebx
0x1004940c3  jmp     loc_100493F86
0x1004940c8  or      [r8+r14*8], ax
0x1004940cd  cmp     r15d, 28h ; '('
0x1004940d1  jbe     short loc_1004940E0
0x1004940d3  cmp     r12d, 13h
0x1004940d7  jbe     short loc_1004940E0
0x1004940d9  lea     r10d, [rbx-524h]
0x1004940e0  mov     r12, [rsp+88h+arg_18]
0x1004940e8  mov     edx, r11d; int
0x1004940eb  movsxd  r8, r10d
0x1004940ee  mov     rcx, rsi; this
0x1004940f1  mov     r8, [r12+r8*8+760h]; unsigned __int16 *
0x1004940f9  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004940fe  mov     edi, eax
0x100494100  test    eax, eax
0x100494102  js      loc_100494914
0x100494108  lfence
0x10049410b  mov     rcx, [rsi+8]
0x10049410f  mov     rdx, [rsi+10h]
0x100494113  mov     r8, [rcx+r14*8+8]
0x100494118  mov     rcx, [rdx+20h]
0x10049411c  cmp     [r8+rcx], bp
0x100494121  jnz     loc_10049407D
0x100494127  lfence
0x10049412a  mov     rcx, [rsi+8]
0x10049412e  mov     edx, 20h ; ' '
0x100494133  or      [rcx+r14*8], dx
0x100494138  mov     r14d, edx
0x10049413b  jmp     loc_100494083
0x100494140  lea     r12d, [rbx-4B0h]
0x100494147  cmp     r12d, 28h ; '('
0x10049414b  ja      short loc_100494159
0x10049414d  lea     r8d, [rbx-49Ah]
0x100494154  mov     r14d, r8d
0x100494157  jmp     short loc_100494172
0x100494159  lea     eax, [rbx-4D9h]
0x10049415f  cmp     eax, 13h
0x100494162  jbe     short loc_10049414D
0x100494164  lea     r8d, [rbx-524h]
0x10049416b  lea     r14d, [rbx-49Ah]
0x100494172  mov     r9, [rsi+8]
0x100494176  lea     r15, [r11+r11*2]
0x10049417a  mov     ecx, 0FFFFFB27h
0x10049417f  mov     eax, ebx
0x100494181  mov     rax, [rsp+88h+arg_0]
0x100494189  mov     edx, 1
0x10049418e  lea     r13d, [rbx+rcx]
0x100494192  mov     ecx, r8d
0x100494195  mov     rax, [rax+48h]
0x100494199  and     ecx, 7
0x10049419c  shl     edx, cl
0x10049419e  mov     ecx, r8d
0x1004941a1  shr     rcx, 3
0x1004941a5  test    [rcx+rax+37D0h], dl
0x1004941ac  jnz     loc_100494269
0x1004941b2  mov     eax, 1
0x1004941b7  test    [r9+r15*8], al
0x1004941bb  jz      loc_1004948FF
0x1004941c1  mov     rax, [rsi+10h]
0x1004941c5  mov     edx, 20h ; ' '
0x1004941ca  mov     rcx, [r9+r15*8+8]
0x1004941cf  add     rcx, [rax+rdx]; String1
0x1004941d3  cmp     r11d, 36h ; '6'
0x1004941d7  jnz     short loc_100494219
0x1004941d9  cmp     r12d, 28h ; '('
0x1004941dd  jbe     short loc_1004941EC
0x1004941df  cmp     r13d, 13h
0x1004941e3  jbe     short loc_1004941EC
0x1004941e5  lea     r14d, [rbx-524h]
0x1004941ec  lea     rdx, aNo; "No"
0x1004941f3  call    cs:__imp__wcsicmp
0x1004941f9  test    eax, eax
0x1004941fb  mov     rcx, rbp
0x1004941fe  setnz   cl
0x100494201  mov     r12, [rsp+88h+arg_18]
0x100494209  movsxd  rax, r14d
0x10049420c  mov     [r12+rax*8+760h], rcx
0x100494214  jmp     loc_10049407D
0x100494219  lea     rdx, aYes_1; "Yes"
0x100494220  call    cs:__imp__wcsicmp
0x100494226  test    eax, eax
0x100494228  jz      short loc_10049424F
0x10049422a  mov     rdx, [rsi+10h]
0x10049422e  mov     rax, [rsi+8]
0x100494232  mov     rcx, [rax+r15*8+8]
0x100494237  add     rcx, [rdx+20h]; String1
0x10049423b  lea     rdx, aEnabled; "Enabled"
0x100494242  call    cs:__imp__wcsicmp
0x100494248  mov     rcx, rbp
0x10049424b  test    eax, eax
0x10049424d  jnz     short loc_100494254
0x10049424f  mov     ecx, 1
0x100494254  cmp     r12d, 28h ; '('
0x100494258  jbe     short loc_100494201
0x10049425a  cmp     r13d, 13h
0x10049425e  jbe     short loc_100494201
0x100494260  lea     r14d, [rbx-524h]
0x100494267  jmp     short loc_100494201
0x100494269  mov     r10d, 1
0x10049426f  lea     eax, [r11-24h]
0x100494273  or      [r9+r15*8], r10w
0x100494278  lea     rcx, ?szValues@?EA@???$ResolveFromPreconnAttrs@UtagDbcInfoToken@@@@YAJPEAUtagDbcInfoToken@@AEAVCDlgATTRs@@@Z@4PAY01PEBGA; ushort const * (near * `ResolveFromPreconnAttrs<tagDbcInfoToken>(tagDbcInfoToken *,CDlgATTRs &)'::`64'::szValues)[2]
0x10049427f  cmp     eax, r10d
0x100494282  lea     rdx, off_1005D0768; "Disabled"
0x100494289  cmovbe  rcx, rdx
0x10049428d  cmp     r12d, 28h ; '('
0x100494291  jbe     short loc_1004942A0
0x100494293  cmp     r13d, 13h
0x100494297  jbe     short loc_1004942A0
0x100494299  lea     r14d, [rbx-524h]
0x1004942a0  mov     r12, [rsp+88h+arg_18]
0x1004942a8  mov     r8, rbp
0x1004942ab  movsxd  rax, r14d
0x1004942ae  mov     edx, r11d; int
0x1004942b1  mov     rbx, [r12+rax*8+760h]
0x1004942b9  mov     eax, 8
0x1004942be  cmp     rbx, r10
0x1004942c1  cmovz   r8, rax
0x1004942c5  mov     r8, [r8+rcx]; unsigned __int16 *
0x1004942c9  mov     rcx, rsi; this
0x1004942cc  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004942d1  mov     edi, eax
0x1004942d3  test    eax, eax
0x1004942d5  js      loc_100494964
0x1004942db  lfence
0x1004942de  mov     rdx, [rsi+8]
0x1004942e2  dec     rbx
0x1004942e5  neg     rbx
0x1004942e8  mov     r8d, 0FFDFh
0x1004942ee  mov     r14d, 20h ; ' '
0x1004942f4  sbb     cx, cx
0x1004942f7  movzx   eax, word ptr [rdx+r15*8]
0x1004942fc  and     cx, r14w
0x100494300  and     ax, r8w
0x100494304  or      cx, ax
0x100494307  mov     [rdx+r15*8], cx
0x10049430c  mov     r15d, r8d
0x10049430f  jmp     loc_100494089
0x100494314  cmp     r11d, 26h ; '&'
0x100494318  jnz     loc_100494587
0x10049431e  lea     r15d, [rbx-4B0h]
0x100494325  cmp     r15d, 28h ; '('
0x100494329  ja      short loc_100494337
0x10049432b  lea     r8d, [rbx-49Ah]
0x100494332  mov     r14d, r8d
0x100494335  jmp     short loc_100494350
0x100494337  lea     eax, [rbx-4D9h]
0x10049433d  cmp     eax, 13h
0x100494340  jbe     short loc_10049432B
0x100494342  lea     r8d, [rbx-524h]
0x100494349  lea     r14d, [rbx-49Ah]
0x100494350  mov     ecx, 0FFFFFB27h
0x100494355  mov     r11d, 1
0x10049435b  mov     edx, r11d
0x10049435e  mov     eax, ebx
0x100494360  mov     rax, [r13+48h]
0x100494364  lea     r9d, [rcx+rbx]
0x100494368  mov     ecx, r8d
0x10049436b  and     ecx, 7
0x10049436e  shl     edx, cl
0x100494370  mov     ecx, r8d
0x100494373  shr     rcx, 3
0x100494377  test    [rcx+rax+37D0h], dl
0x10049437e  jnz     loc_1004944D0
0x100494384  mov     rcx, [rsi+8]
0x100494388  test    [rcx+390h], r11b
0x10049438f  jz      loc_100494499
0x100494395  mov     rax, [rsi+10h]
0x100494399  lea     rdx, aSqlpassword; "SqlPassword"
0x1004943a0  mov     rcx, [rcx+398h]
0x1004943a7  add     rcx, [rax+20h]; String1
0x1004943ab  call    cs:__imp__wcsicmp
0x1004943b1  test    eax, eax
0x1004943b3  jnz     short loc_1004943BD
0x1004943b5  lea     ecx, [rax+1]
0x1004943b8  jmp     loc_10049448F
0x1004943bd  mov     rdx, [rsi+8]
0x1004943c1  mov     rax, [rsi+10h]
0x1004943c5  mov     rcx, [rax+20h]
0x1004943c9  add     rcx, [rdx+398h]; String1
0x1004943d0  lea     rdx, aActivedirector; "ActiveDirectoryInteractive"
0x1004943d7  call    cs:__imp__wcsicmp
0x1004943dd  test    eax, eax
0x1004943df  jnz     short loc_1004943E9
0x1004943e1  lea     ecx, [rax+4]
0x1004943e4  jmp     loc_10049448F
0x1004943e9  mov     rdx, [rsi+8]
0x1004943ed  mov     rax, [rsi+10h]
0x1004943f1  mov     rcx, [rax+20h]
0x1004943f5  add     rcx, [rdx+398h]; String1
0x1004943fc  lea     rdx, aActivedirector_1; "ActiveDirectoryIntegrated"
0x100494403  call    cs:__imp__wcsicmp
0x100494409  test    eax, eax
0x10049440b  jnz     short loc_100494412
0x10049440d  lea     ecx, [rax+2]
0x100494410  jmp     short loc_10049448F
0x100494412  mov     rdx, [rsi+8]
0x100494416  mov     rax, [rsi+10h]
0x10049441a  mov     rcx, [rax+20h]
0x10049441e  add     rcx, [rdx+398h]; String1
0x100494425  lea     rdx, aActivedirector_3; "ActiveDirectoryMSI"
0x10049442c  call    cs:__imp__wcsicmp
0x100494432  test    eax, eax
0x100494434  jnz     short loc_10049443B
0x100494436  lea     ecx, [rax+6]
0x100494439  jmp     short loc_10049448F
0x10049443b  mov     rdx, [rsi+8]
0x10049443f  mov     rax, [rsi+10h]
  ... truncated ...
```
