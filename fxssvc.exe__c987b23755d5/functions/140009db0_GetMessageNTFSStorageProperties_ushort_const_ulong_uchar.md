# GetMessageNTFSStorageProperties(ushort const *,ulong,uchar *)

- ea: `0x140009db0`
- end: `0x14000ab05`
- name: `?GetMessageNTFSStorageProperties@@YAHPEBGKPEAE@Z`
- size: `3413`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140014c78`

## callees

- `0x140002926`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004df0`
- `0x140006b0c`
- `0x1400075d0`
- `0x140009db0`
- `0x14004f358`
- `0x140067168`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140009eb3`
- `KERNEL32!GetLastError` at `0x140009f16`
- `KERNEL32!GetLastError` at `0x14000a8bc`
- `KERNEL32!GetLastError` at `0x14000a8fc`
- `KERNEL32!GetLastError` at `0x14000a936`
- `KERNEL32!GetLastError` at `0x14000a970`
- `KERNEL32!GetLastError` at `0x140009eb3`
- `KERNEL32!GetLastError` at `0x140009f16`
- `KERNEL32!GetLastError` at `0x14000a8bc`
- `KERNEL32!GetLastError` at `0x14000a8fc`
- `KERNEL32!GetLastError` at `0x14000a936`
- `KERNEL32!GetLastError` at `0x14000a970`
- `KERNEL32!SetLastError` at `0x14000aac5`
- `KERNEL32!SetLastError` at `0x14000aac5`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a3bd`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a441`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a525`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a556`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a3bd`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a441`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a525`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a556`
- `KERNEL32!FindFirstFileW` at `0x140009e79`
- `KERNEL32!FindFirstFileW` at `0x140009e79`
- `KERNEL32!FindClose` at `0x140009eed`
- `KERNEL32!FindClose` at `0x140009eed`
- `KERNEL32!LocalFree` at `0x14000aad3`
- `KERNEL32!LocalFree` at `0x14000aad3`
- `msvcrt!wcsrchr` at `0x14000a843`
- `msvcrt!wcsrchr` at `0x14000a843`
- `ole32!FreePropVariantArray` at `0x14000aa79`
- `ole32!FreePropVariantArray` at `0x14000aa79`

## pseudocode

```c
__int64 __fastcall GetMessageNTFSStorageProperties(const unsigned __int16 *a1, unsigned int a2, unsigned __int8 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rsi
  size_t v7; // rdi
  void *v8; // r12
  ULONG v10; // r13d
  HANDLE FirstFileW; // rcx
  DWORD LastError; // eax
  DWORD v13; // eax
  HRESULT v14; // eax
  DWORD v15; // ebx
  unsigned int v16; // edi
  int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // r9
  CMapDeviceId *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  int v40; // eax
  int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v46; // eax
  int v47; // eax
  PROPVARIANT v48; // rax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  wchar_t *v52; // rax
  CFaxArchiving *v53; // rcx
  void **v54; // r9
  const unsigned __int16 *v55; // rdx
  DWORD ComponentsFromArchiveFileName; // eax
  DWORD v57; // eax
  int v58; // ecx
  HRESULT v59; // eax
  FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  int v61; // [rsp+40h] [rbp-C0h]
  void *v62; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+50h] [rbp-B0h] BYREF
  struct IPropertySetStorage *v64; // [rsp+58h] [rbp-A8h] BYREF
  int Src; // [rsp+60h] [rbp-A0h] BYREF
  int v66; // [rsp+64h] [rbp-9Ch]
  unsigned __int64 v67[2]; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+78h] [rbp-88h]
  int v69; // [rsp+7Ch] [rbp-84h]
  int v70; // [rsp+80h] [rbp-80h]
  DWORD nFileSizeLow; // [rsp+90h] [rbp-70h]
  int v73; // [rsp+94h] [rbp-6Ch]
  struct _SYSTEMTIME v82; // [rsp+D8h] [rbp-28h] BYREF
  struct _SYSTEMTIME v83; // [rsp+E8h] [rbp-18h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+F8h] [rbp-8h] BYREF
  struct _SYSTEMTIME v85; // [rsp+108h] [rbp+8h] BYREF
  int v87; // [rsp+120h] [rbp+20h]
  int v88; // [rsp+124h] [rbp+24h]
  BOOL v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  BOOL v96; // [rsp+158h] [rbp+58h]
  int v97; // [rsp+15Ch] [rbp+5Ch]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+160h] [rbp+60h] BYREF
  PROPVARIANT rgvars[88]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v3 = 0;
  v4 = a2;
  v64 = 0;
  v63 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  v7 = 256;
  memset_0(&Src, 0, 0x100u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileTime = 0;
  v8 = 0;
  v62 = 0;
  if ( (unsigned int)v4 >= 2 )
    return 87;
  v61 = 0;
  v10 = 0;
  FirstFileW = FindFirstFileW(a1, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        LastError,
        (__int64)a1);
    }
  }
  else
  {
    v66 |= 0x10u;
    nFileSizeLow = FindFileData.nFileSizeLow;
    if ( !FindClose(FirstFileW)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v13);
    }
  }
  v14 = FaxStgOpenStorageEx(a1, 0x20u, &v64);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v14);
    }
    v15 = 110;
    goto LABEL_23;
  }
  v17 = ((__int64 (__fastcall *)(struct IPropertySetStorage *, __int64 *, __int64, __int64 *))v64->lpVtbl->Open)(
          v64,
          qword_14008C750,
          16,
          &v63);
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (_DWORD)a1,
        v17);
    }
    v15 = 110;
    goto LABEL_30;
  }
  v10 = *((_DWORD *)qword_14008C940 + v4);
  if ( v10 > 0x1D )
  {
    v15 = 1359;
LABEL_30:
    v16 = 0;
    goto LABEL_201;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, PROPVARIANT *))(*(_QWORD *)v63 + 24LL))(
          v63,
          v10,
          qword_14008C950,
          rgvars);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v18);
    }
    v15 = 30;
    goto LABEL_23;
  }
  v61 = 1;
  if ( !v10 )
  {
LABEL_165:
    v52 = wcsrchr(a1, 0x5Cu);
    v54 = &v62;
    if ( !(_DWORD)v4 )
      v54 = 0;
    v55 = v52 + 1;
    if ( !v52 )
      v55 = 0;
    ComponentsFromArchiveFileName = CFaxArchiving::ExtractComponentsFromArchiveFileName(v53, v55, v67, v54);
    v15 = ComponentsFromArchiveFileName;
    if ( ComponentsFromArchiveFileName )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          113,
          &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
          ComponentsFromArchiveFileName);
      }
      v8 = v62;
      v16 = 0;
    }
    else
    {
      v8 = v62;
      v58 = v66 | 0x80000;
      v66 |= 0x80000u;
      if ( (_DWORD)v4 )
      {
        v96 = v62 == 0;
        v66 = v58 | 0x400000;
      }
      else
      {
        v7 = 232;
      }
      Src = v7;
      memcpy_0(a3, &Src, v7);
      v16 = 1;
    }
    goto LABEL_201;
  }
  while ( 1 )
  {
    if ( !LOWORD(rgvars[3 * v3]) )
      goto LABEL_164;
    v19 = qword_14008C950[2 * v3 + 1];
    if ( v19 > 0xC8 )
      break;
    if ( v19 == 200 )
    {
      if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
      {
        v25 = 8;
        v15 = 8;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_200;
        }
        v27 = 106;
LABEL_83:
        WPP_SF_d(*((_QWORD *)v26 + 2), v27, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v25);
        goto LABEL_23;
      }
    }
    else if ( v19 > 0x70 )
    {
      if ( v19 > 0x76 )
      {
        v42 = v19 - 119;
        if ( v42 )
        {
          v43 = v42 - 1;
          if ( v43 )
          {
            v44 = v43 - 1;
            if ( v44 )
            {
              v45 = v44 - 1;
              if ( v45 )
              {
                if ( v45 == 1 )
                {
                  v46 = (int)rgvars[3 * v3 + 1];
                  v66 |= 0x800000u;
                  v97 = v46;
                }
                goto LABEL_164;
              }
              if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
              {
                v25 = 8;
                v15 = 8;
                v26 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_200;
                }
                v27 = 112;
                goto LABEL_83;
              }
            }
            else
            {
              v47 = (int)rgvars[3 * v3 + 1];
              v66 |= 0x200000u;
              v94 = v47;
            }
          }
          else
          {
            v93 = LOWORD(rgvars[3 * v3 + 1]) == 0xFFFF;
          }
        }
        else
        {
          v48 = rgvars[3 * v3 + 1];
          v66 |= 0x100000u;
          v67[1] = (unsigned __int64)v48;
        }
      }
      else if ( v19 == 118 )
      {
        if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 111;
          goto LABEL_83;
        }
      }
      else
      {
        v36 = v19 - 113;
        if ( !v36 )
        {
          FileTime = (FILETIME)rgvars[3 * v3 + 1];
          if ( FileTimeToSystemTime(&FileTime, &v83) )
          {
            v66 |= 0x400u;
            goto LABEL_164;
          }
          v57 = GetLastError();
          v15 = v57;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = 103;
            goto LABEL_179;
          }
          goto LABEL_23;
        }
        v37 = v36 - 1;
        if ( !v37 )
        {
          FileTime = (FILETIME)rgvars[3 * v3 + 1];
          if ( FileTimeToSystemTime(&FileTime, &v82) )
          {
            v66 |= 0x200u;
            goto LABEL_164;
          }
          v57 = GetLastError();
          v15 = v57;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = 104;
            goto LABEL_179;
          }
          goto LABEL_23;
        }
        v38 = v37 - 1;
        if ( v38 )
        {
          v39 = v38 - 1;
          if ( v39 )
          {
            if ( v39 == 1 )
            {
              v40 = (int)rgvars[3 * v3 + 1];
              v66 |= 8u;
              v70 = v40;
            }
          }
          else
          {
            v41 = (int)rgvars[3 * v3 + 1];
            v66 |= 4u;
            v69 = v41;
          }
        }
        else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 105;
          goto LABEL_83;
        }
      }
    }
    else
    {
      if ( v19 == 112 )
      {
        FileTime = (FILETIME)rgvars[3 * v3 + 1];
        if ( FileTimeToSystemTime(&FileTime, &v85) )
        {
          v66 |= 0x1000u;
          goto LABEL_164;
        }
        v57 = GetLastError();
        v15 = v57;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v27 = 102;
          goto LABEL_179;
        }
LABEL_23:
        v16 = 0;
        goto LABEL_201;
      }
      if ( v19 > 0x6A )
      {
        v28 = v19 - 107;
        if ( !v28 )
        {
          v35 = (int)rgvars[3 * v3 + 1];
          v66 |= 0x4000u;
          v88 = v35;
          goto LABEL_164;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v34 = (int)rgvars[3 * v3 + 1];
          v66 |= 0x2000u;
          v87 = v34;
          goto LABEL_164;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
          v33 = (int)rgvars[3 * v3 + 1];
          v66 |= 0x20u;
          v73 = v33;
          goto LABEL_164;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          v32 = (int)rgvars[3 * v3 + 1];
          v66 |= 2u;
          v68 = v32;
          goto LABEL_164;
        }
        if ( v31 == 1 )
        {
          FileTime = (FILETIME)rgvars[3 * v3 + 1];
          if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
          {
            v66 |= 0x800u;
            goto LABEL_164;
          }
          v57 = GetLastError();
          v15 = v57;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = 101;
LABEL_179:
            v25 = v57;
            goto LABEL_83;
          }
          goto LABEL_23;
        }
      }
      else if ( v19 == 106 )
      {
        if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 100;
          goto LABEL_83;
        }
      }
      else
      {
        v20 = v19 - 100;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                v24 = v23 - 1;
                if ( v24 )
                {
                  if ( v24 == 1 && !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
                  {
                    v25 = 8;
                    v15 = 8;
                    v26 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_200;
                    }
                    v27 = 99;
                    goto LABEL_83;
                  }
                }
                else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
                {
                  v25 = 8;
                  v15 = 8;
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_200;
                  }
                  v27 = 98;
                  goto LABEL_83;
                }
              }
              else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
              {
                v25 = 8;
                v15 = 8;
                v26 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_200;
                }
                v27 = 97;
                goto LABEL_83;
              }
            }
            else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
            {
              v25 = 8;
              v15 = 8;
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_200;
              }
              v27 = 96;
              goto LABEL_83;
            }
          }
          else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
          {
            v25 = 8;
            v15 = 8;
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_200;
            }
            v27 = 95;
            goto LABEL_83;
          }
        }
        else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 94;
          goto LABEL_83;
        }
      }
    }
LABEL_164:
    if ( ++v3 >= v10 )
      goto LABEL_165;
  }
  v49 = v19 - 201;
  if ( !v49 )
  {
    if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    {
      v25 = 8;
      v15 = 8;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = 107;
        goto LABEL_83;
      }
      goto LABEL_200;
    }
    goto LABEL_164;
  }
  v50 = v49 - 99;
  if ( !v50 )
  {
    if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    {
      v25 = 8;
      v15 = 8;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = 110;
        goto LABEL_83;
      }
      goto LABEL_200;
    }
    goto LABEL_164;
  }
  v51 = v50 - 1;
  if ( !v51 )
  {
    if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    {
      v25 = 8;
      v15 = 8;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = 108;
        goto LABEL_83;
      }
      goto LABEL_200;
    }
    goto LABEL_164;
  }
  if ( v51 != 1 )
    goto LABEL_164;
  if ( StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    goto LABEL_164;
  v25 = 8;
  v15 = 8;
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v27 = 109;
    goto LABEL_83;
  }
LABEL_200:
  v16 = 0;
LABEL_201:
  if ( v63 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v64 )
    ((void (__fastcall *)(struct IPropertySetStorage *))v64->lpVtbl->Release)(v64);
  if ( v61 == 1 )
  {
    v59 = FreePropVariantArray(v10, rgvars);
    if ( v59 < 0
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v59);
    }
  }
  if ( !v16 )
  {
    FreeMessageBuffer1((struct _FAX_MESSAGE_1 *)&Src, 0);
    SetLastError(v15);
  }
  if ( v8 )
    LocalFree(v8);
  return v16;
}

```

## disassembly

```asm
0x140009db0  mov     [rsp-8+arg_18], rbx
0x140009db5  push    rbp
0x140009db6  push    rsi
0x140009db7  push    rdi
0x140009db8  push    r12
0x140009dba  push    r13
0x140009dbc  push    r14
0x140009dbe  push    r15
0x140009dc0  lea     rbp, [rsp-580h]
0x140009dc8  sub     rsp, 680h
0x140009dcf  mov     rax, cs:__security_cookie
0x140009dd6  xor     rax, rsp
0x140009dd9  mov     [rbp+5B0h+var_40], rax
0x140009de0  xor     ebx, ebx
0x140009de2  mov     esi, edx
0x140009de4  mov     [rsp+6B0h+var_658], rbx
0x140009de9  mov     r15, r8
0x140009dec  mov     [rsp+6B0h+var_660], rbx
0x140009df1  mov     r14, rcx
0x140009df4  mov     rcx, cs:WPP_GLOBAL_Control
0x140009dfb  lea     rax, WPP_GLOBAL_Control
0x140009e02  cmp     rcx, rax
0x140009e05  jz      short loc_140009E26
0x140009e07  test    byte ptr [rcx+1Ch], 4
0x140009e0b  jz      short loc_140009E26
0x140009e0d  cmp     byte ptr [rcx+19h], 5
0x140009e11  jb      short loc_140009E26
0x140009e13  mov     rcx, [rcx+10h]
0x140009e17  lea     edx, [rbx+58h]
0x140009e1a  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140009e21  call    WPP_SF_
0x140009e26  mov     edi, 100h
0x140009e2b  lea     rcx, [rsp+6B0h+Src]; void *
0x140009e30  mov     r8d, edi; Size
0x140009e33  xor     edx, edx; Val
0x140009e35  call    memset_0
0x140009e3a  xor     edx, edx; Val
0x140009e3c  lea     rcx, [rbp+5B0h+FindFileData]; void *
0x140009e40  mov     r8d, 250h; Size
0x140009e46  call    memset_0
0x140009e4b  mov     qword ptr [rsp+6B0h+FileTime.dwLowDateTime], rbx
0x140009e50  mov     r12, rbx
0x140009e53  mov     [rsp+6B0h+var_668], rbx
0x140009e58  cmp     esi, 2
0x140009e5b  jb      short loc_140009E67
0x140009e5d  mov     eax, 57h ; 'W'
0x140009e62  jmp     loc_14000AADB
0x140009e67  lea     rdx, [rbp+5B0h+FindFileData]; lpFindFileData
0x140009e6b  mov     [rsp+6B0h+var_680], ebx
0x140009e6f  mov     rcx, r14; lpFileName
0x140009e72  mov     [rsp+6B0h+var_670], ebx
0x140009e76  mov     r13d, ebx
0x140009e79  call    cs:__imp_FindFirstFileW
0x140009e7f  mov     rcx, rax; hFindFile
0x140009e82  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009e86  jnz     short loc_140009EDF
0x140009e88  mov     rax, cs:WPP_GLOBAL_Control
0x140009e8f  lea     rcx, WPP_GLOBAL_Control
0x140009e96  cmp     rax, rcx
0x140009e99  jz      loc_140009F3B
0x140009e9f  test    byte ptr [rax+1Ch], 4
0x140009ea3  jz      loc_140009F3B
0x140009ea9  cmp     byte ptr [rax+19h], 2
0x140009ead  jb      loc_140009F3B
0x140009eb3  call    cs:__imp_GetLastError
0x140009eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ec0  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140009ec7  mov     edx, 59h ; 'Y'
0x140009ecc  mov     [rsp+6B0h+var_690], r14
0x140009ed1  mov     r9d, eax
0x140009ed4  mov     rcx, [rcx+10h]
0x140009ed8  call    WPP_SF_DS
0x140009edd  jmp     short loc_140009F3B
0x140009edf  mov     eax, [rbp+5B0h+FindFileData.nFileSizeLow]
0x140009ee5  or      [rsp+6B0h+var_64C], 10h
0x140009eea  mov     [rbp+5B0h+var_620], eax
0x140009eed  call    cs:__imp_FindClose
0x140009ef3  test    eax, eax
0x140009ef5  jnz     short loc_140009F3B
0x140009ef7  mov     rax, cs:WPP_GLOBAL_Control
0x140009efe  lea     rcx, WPP_GLOBAL_Control
0x140009f05  cmp     rax, rcx
0x140009f08  jz      short loc_140009F3B
0x140009f0a  test    byte ptr [rax+1Ch], 4
0x140009f0e  jz      short loc_140009F3B
0x140009f10  cmp     byte ptr [rax+19h], 2
0x140009f14  jb      short loc_140009F3B
0x140009f16  call    cs:__imp_GetLastError
0x140009f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f23  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140009f2a  mov     edx, 5Ah ; 'Z'
0x140009f2f  mov     r9d, eax
0x140009f32  mov     rcx, [rcx+10h]
0x140009f36  call    WPP_SF_d
0x140009f3b  lea     r8, [rsp+6B0h+var_658]; struct IPropertySetStorage **
0x140009f40  mov     edx, 20h ; ' '; unsigned int
0x140009f45  mov     rcx, r14; unsigned __int16 *
0x140009f48  call    ?FaxStgOpenStorageEx@@YAJPEBGKPEAPEAUIPropertySetStorage@@@Z; FaxStgOpenStorageEx(ushort const *,ulong,IPropertySetStorage * *)
0x140009f4d  test    eax, eax
0x140009f4f  jns     short loc_140009F95
0x140009f51  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f58  lea     r14, WPP_GLOBAL_Control
0x140009f5f  cmp     rcx, r14
0x140009f62  jz      short loc_140009F88
0x140009f64  test    byte ptr [rcx+1Ch], 4
0x140009f68  jz      short loc_140009F88
0x140009f6a  cmp     byte ptr [rcx+19h], 2
0x140009f6e  jb      short loc_140009F88
0x140009f70  mov     rcx, [rcx+10h]
0x140009f74  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140009f7b  mov     edx, 5Bh ; '['
0x140009f80  mov     r9d, eax
0x140009f83  call    WPP_SF_d
0x140009f88  mov     ebx, 6Eh ; 'n'
0x140009f8d  mov     edi, r12d
0x140009f90  jmp     loc_14000AA3C
0x140009f95  mov     rcx, [rsp+6B0h+var_658]
0x140009f9a  lea     r9, [rsp+6B0h+var_660]
0x140009f9f  mov     r8d, 10h
0x140009fa5  lea     rdx, qword_14008C750
0x140009fac  mov     rax, [rcx]
0x140009faf  mov     rax, [rax+20h]
0x140009fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fb8  test    eax, eax
0x140009fba  jns     short loc_14000A00B
0x140009fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140009fc3  lea     rdx, WPP_GLOBAL_Control
0x140009fca  cmp     rcx, rdx
0x140009fcd  jz      short loc_140009FF7
0x140009fcf  test    byte ptr [rcx+1Ch], 4
0x140009fd3  jz      short loc_140009FF7
0x140009fd5  cmp     byte ptr [rcx+19h], 2
0x140009fd9  jb      short loc_140009FF7
0x140009fdb  mov     rcx, [rcx+10h]
0x140009fdf  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140009fe6  mov     edx, 5Ch ; '\'
0x140009feb  mov     dword ptr [rsp+6B0h+var_690], eax
0x140009fef  mov     r9, r14
0x140009ff2  call    WPP_SF_Sd
0x140009ff7  mov     ebx, 6Eh ; 'n'
0x140009ffc  mov     edi, r12d
0x140009fff  lea     r14, WPP_GLOBAL_Control
0x14000a006  jmp     loc_14000AA3C
0x14000a00b  lea     r13, qword_14008C940
0x14000a012  mov     r13d, [r13+rsi*4+0]
0x14000a017  cmp     r13d, 1Dh
0x14000a01b  jbe     short loc_14000A024
0x14000a01d  mov     ebx, 54Fh
0x14000a022  jmp     short loc_140009FFC
0x14000a024  mov     rcx, [rsp+6B0h+var_660]
0x14000a029  lea     r9, [rbp+5B0h+rgvars]
0x14000a030  lea     r8, qword_14008C950
0x14000a037  mov     edx, r13d
0x14000a03a  mov     rax, [rcx]
0x14000a03d  mov     rax, [rax+18h]
0x14000a041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a046  test    eax, eax
0x14000a048  jns     short loc_14000A08B
0x14000a04a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a051  lea     r14, WPP_GLOBAL_Control
0x14000a058  cmp     rcx, r14
0x14000a05b  jz      short loc_14000A081
0x14000a05d  test    byte ptr [rcx+1Ch], 4
0x14000a061  jz      short loc_14000A081
0x14000a063  cmp     byte ptr [rcx+19h], 2
0x14000a067  jb      short loc_14000A081
0x14000a069  mov     rcx, [rcx+10h]
0x14000a06d  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000a074  mov     edx, 5Dh ; ']'
0x14000a079  mov     r9d, eax
0x14000a07c  call    WPP_SF_d
0x14000a081  mov     ebx, 1Eh
0x14000a086  jmp     loc_140009F8D
0x14000a08b  xor     edx, edx
0x14000a08d  mov     [rsp+6B0h+var_670], 1
0x14000a095  test    r13d, r13d
0x14000a098  jz      loc_14000A83B
0x14000a09e  mov     eax, ebx
0x14000a0a0  lea     rcx, [rax+rax*2]
0x14000a0a4  cmp     word ptr [rbp+rcx*8+5B0h+rgvars], dx
0x14000a0ac  jz      loc_14000A830
0x14000a0b2  add     rax, rax
0x14000a0b5  lea     r8, qword_14008C950
0x14000a0bc  mov     eax, [r8+rax*8+8]
0x14000a0c1  cmp     eax, 0C8h
0x14000a0c6  ja      loc_14000A6F4
0x14000a0cc  jz      loc_14000A69E
0x14000a0d2  cmp     eax, 70h ; 'p'
0x14000a0d5  ja      loc_14000A45C
0x14000a0db  jz      loc_14000A42B
0x14000a0e1  cmp     eax, 6Ah ; 'j'
0x14000a0e4  ja      loc_14000A386
0x14000a0ea  jz      loc_14000A333
0x14000a0f0  sub     eax, 64h ; 'd'
0x14000a0f3  jz      loc_14000A2CD
0x14000a0f9  sub     eax, 1
0x14000a0fc  jz      loc_14000A27A
0x14000a102  sub     eax, 1
0x14000a105  jz      loc_14000A224
0x14000a10b  sub     eax, 1
0x14000a10e  jz      loc_14000A1CE
0x14000a114  sub     eax, 1
0x14000a117  jz      short loc_14000A178
0x14000a119  cmp     eax, 1
0x14000a11c  jnz     loc_14000A830
0x14000a122  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a12a  call    StringDup
0x14000a12f  xor     edx, edx
0x14000a131  mov     [rbp+5B0h+var_588], rax
0x14000a135  test    rax, rax
0x14000a138  jnz     loc_14000A830
0x14000a13e  lea     r9d, [rax+8]
0x14000a142  mov     ebx, r9d
0x14000a145  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a14c  lea     r14, WPP_GLOBAL_Control
0x14000a153  cmp     rcx, r14
0x14000a156  jz      loc_14000AA3A
0x14000a15c  test    byte ptr [rcx+1Ch], 4
0x14000a160  jz      loc_14000AA3A
0x14000a166  cmp     byte ptr [rcx+19h], 2
0x14000a16a  jb      loc_14000AA3A
0x14000a170  lea     edx, [rax+63h]
0x14000a173  jmp     loc_14000A31E
0x14000a178  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a180  call    StringDup
0x14000a185  xor     edx, edx
0x14000a187  mov     [rbp+5B0h+var_578], rax
0x14000a18b  test    rax, rax
0x14000a18e  jnz     loc_14000A830
0x14000a194  lea     r9d, [rax+8]
0x14000a198  mov     ebx, r9d
0x14000a19b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1a2  lea     r14, WPP_GLOBAL_Control
0x14000a1a9  cmp     rcx, r14
0x14000a1ac  jz      loc_14000AA3A
0x14000a1b2  test    byte ptr [rcx+1Ch], 4
0x14000a1b6  jz      loc_14000AA3A
0x14000a1bc  cmp     byte ptr [rcx+19h], 2
0x14000a1c0  jb      loc_14000AA3A
0x14000a1c6  lea     edx, [rax+62h]
0x14000a1c9  jmp     loc_14000A31E
0x14000a1ce  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a1d6  call    StringDup
0x14000a1db  xor     edx, edx
0x14000a1dd  mov     [rbp+5B0h+var_570], rax
0x14000a1e1  test    rax, rax
0x14000a1e4  jnz     loc_14000A830
0x14000a1ea  lea     r9d, [rax+8]
0x14000a1ee  mov     ebx, r9d
0x14000a1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1f8  lea     r14, WPP_GLOBAL_Control
0x14000a1ff  cmp     rcx, r14
0x14000a202  jz      loc_14000AA3A
0x14000a208  test    byte ptr [rcx+1Ch], 4
0x14000a20c  jz      loc_14000AA3A
0x14000a212  cmp     byte ptr [rcx+19h], 2
0x14000a216  jb      loc_14000AA3A
0x14000a21c  lea     edx, [rax+61h]
0x14000a21f  jmp     loc_14000A31E
0x14000a224  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a22c  call    StringDup
0x14000a231  xor     edx, edx
0x14000a233  mov     [rbp+5B0h+var_598], rax
0x14000a237  test    rax, rax
0x14000a23a  jnz     loc_14000A830
0x14000a240  lea     r9d, [rax+8]
0x14000a244  mov     ebx, r9d
0x14000a247  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a24e  lea     r14, WPP_GLOBAL_Control
0x14000a255  cmp     rcx, r14
0x14000a258  jz      loc_14000AA3A
0x14000a25e  test    byte ptr [rcx+1Ch], 4
0x14000a262  jz      loc_14000AA3A
0x14000a268  cmp     byte ptr [rcx+19h], 2
0x14000a26c  jb      loc_14000AA3A
0x14000a272  lea     edx, [rax+60h]
0x14000a275  jmp     loc_14000A31E
0x14000a27a  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a282  call    StringDup
0x14000a287  xor     edx, edx
0x14000a289  mov     [rbp+5B0h+var_5F8], rax
0x14000a28d  test    rax, rax
0x14000a290  jnz     loc_14000A830
0x14000a296  lea     r9d, [rax+8]
0x14000a29a  mov     ebx, r9d
0x14000a29d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2a4  lea     r14, WPP_GLOBAL_Control
0x14000a2ab  cmp     rcx, r14
0x14000a2ae  jz      loc_14000AA3A
0x14000a2b4  test    byte ptr [rcx+1Ch], 4
0x14000a2b8  jz      loc_14000AA3A
0x14000a2be  cmp     byte ptr [rcx+19h], 2
0x14000a2c2  jb      loc_14000AA3A
0x14000a2c8  lea     edx, [rax+5Fh]
0x14000a2cb  jmp     short loc_14000A31E
0x14000a2cd  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a2d5  call    StringDup
0x14000a2da  xor     edx, edx
0x14000a2dc  mov     [rbp+5B0h+var_5F0], rax
0x14000a2e0  test    rax, rax
  ... truncated ...
```
