# CMsftDiscRecorder2::InitializeDiscRecorder(ushort *)

- ea: `0x180003b00`
- end: `0x180004add`
- name: `?InitializeDiscRecorder@CMsftDiscRecorder2@@UEAAJPEAG@Z`
- size: `4061`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180003b00`
- `0x180005100`
- `0x18000f740`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x1800236b4`
- `0x180049832`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003bf9`
- `ole32!CoTaskMemFree` at `0x180003c03`
- `ole32!CoTaskMemFree` at `0x180003c0c`
- `ole32!CoTaskMemFree` at `0x180003bf9`
- `ole32!CoTaskMemFree` at `0x180003c03`
- `ole32!CoTaskMemFree` at `0x180003c0c`
- `ole32!CoTaskMemAlloc` at `0x180003dcb`
- `ole32!CoTaskMemAlloc` at `0x18000419c`
- `ole32!CoTaskMemAlloc` at `0x180004747`
- `ole32!CoTaskMemAlloc` at `0x180003dcb`
- `ole32!CoTaskMemAlloc` at `0x18000419c`
- `ole32!CoTaskMemAlloc` at `0x180004747`
- `OLEAUT32!__imp_SysAllocString` at `0x180003e92`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fa2`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fe9`
- `OLEAUT32!__imp_SysAllocString` at `0x180004300`
- `OLEAUT32!__imp_SysAllocString` at `0x180003e92`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fa2`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fe9`
- `OLEAUT32!__imp_SysAllocString` at `0x180004300`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c15`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c1f`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c29`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c33`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c15`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c1f`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c29`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c33`
- `OLEAUT32!__imp_SysFreeString` at `0x180003c4f`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b58`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b70`
- `OLEAUT32!__imp_SysStringLen` at `0x180003bdd`
- `OLEAUT32!__imp_SysStringLen` at `0x180003e2b`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b58`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b70`
- `OLEAUT32!__imp_SysStringLen` at `0x180003bdd`
- `OLEAUT32!__imp_SysStringLen` at `0x180003e2b`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180003e7d`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180003e7d`
- `KERNEL32!CloseHandle` at `0x180003c46`
- `KERNEL32!CloseHandle` at `0x180003c46`
- `KERNEL32!LocalAlloc` at `0x180003e41`
- `KERNEL32!LocalAlloc` at `0x180003e41`
- `KERNEL32!LocalFree` at `0x180003ea7`
- `KERNEL32!LocalFree` at `0x180003ea7`
- `KERNEL32!CreateFileW` at `0x18000433c`
- `KERNEL32!CreateFileW` at `0x18000433c`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::InitializeDiscRecorder(CMsftDiscRecorder2 *this, unsigned __int16 *a2)
{
  CMsftDiscRecorder2 *v2; // rdi
  OLECHAR *v4; // r14
  char *FileW; // r13
  unsigned __int8 *v6; // rbx
  UINT v8; // eax
  UINT v9; // r8d
  unsigned __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  int i; // r9d
  signed int LastErrorAsHresultForceFailure; // esi
  int v14; // edx
  int v15; // r9d
  OLECHAR *v16; // r12
  const struct _GUID *v17; // r8
  __int64 v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned __int8 *v22; // rax
  UINT v23; // eax
  __int64 v24; // rdi
  __int64 v25; // rax
  unsigned int v26; // ebx
  HLOCAL v27; // r14
  int v28; // edx
  Imapi2Utility *v29; // rcx
  OLECHAR *v30; // rdi
  __int16 v31; // ax
  OLECHAR v32; // cx
  __int16 v33; // ax
  __int16 v34; // cx
  __int16 v35; // ax
  __int16 v36; // cx
  __int16 v37; // ax
  __int16 v38; // cx
  __int16 v39; // ax
  __int16 v40; // cx
  __int16 v41; // ax
  __int16 v42; // cx
  __int16 v43; // ax
  OLECHAR *v44; // rax
  OLECHAR *v45; // rbx
  OLECHAR *v46; // rax
  CMsftDiscRecorder2 *v47; // rcx
  _QWORD *v48; // rcx
  CMsftDiscRecorder2 *v49; // rcx
  unsigned int v50; // r9d
  unsigned int v51; // ebx
  unsigned int v52; // r9d
  BSTR v53; // rax
  int v54; // ecx
  __int64 v55; // rdx
  const WCHAR *v56; // rax
  int v57; // edx
  Imapi2Utility *v58; // rcx
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  _QWORD *v61; // rcx
  __int64 v62; // rdx
  unsigned int v63; // ebx
  CMsftDiscRecorder2 *v64; // rcx
  _DWORD *v65; // r14
  CMsftDiscRecorder2 *v66; // [rsp+40h] [rbp-79h]
  unsigned __int8 *v67; // [rsp+48h] [rbp-71h]
  OLECHAR *v68; // [rsp+50h] [rbp-69h]
  SIZE_T cb; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v70; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v71; // [rsp+64h] [rbp-55h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-51h]
  BSTR v73; // [rsp+70h] [rbp-49h]
  BSTR v74; // [rsp+78h] [rbp-41h]
  LPVOID pv; // [rsp+80h] [rbp-39h]
  int v76; // [rsp+88h] [rbp-31h] BYREF
  __int64 v77; // [rsp+8Ch] [rbp-2Dh]
  __int64 v78; // [rsp+98h] [rbp-21h] BYREF
  int v79; // [rsp+A0h] [rbp-19h]
  OLECHAR psz; // [rsp+A8h] [rbp-11h] BYREF
  __int16 v81; // [rsp+AAh] [rbp-Fh]
  __int16 v82; // [rsp+ACh] [rbp-Dh]
  __int16 v83; // [rsp+AEh] [rbp-Bh]
  _QWORD v84[3]; // [rsp+B0h] [rbp-9h] BYREF
  __int16 v85; // [rsp+C8h] [rbp+Fh]

  v2 = 0;
  cb = 0;
  v4 = 0;
  bstrString = 0;
  v73 = 0;
  FileW = 0;
  v74 = 0;
  v6 = 0;
  v71 = 0;
  pv = 0;
  v66 = 0;
  if ( !SysStringLen(a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 180, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    LastErrorAsHresultForceFailure = -2147024809;
    goto LABEL_12;
  }
  v8 = SysStringLen(a2);
  v9 = v8;
  if ( !a2 || (v10 = v8 + 1, v10 > 0x7FFFFFFF) )
  {
    LastErrorAsHresultForceFailure = -2147024809;
LABEL_29:
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_12;
    }
    v21 = 181;
LABEL_33:
    WPP_SF_(v20[22], v21, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    goto LABEL_12;
  }
  v11 = a2;
  for ( i = v10; v10; --v10 )
  {
    if ( !*v11 )
      break;
    ++v11;
  }
  LastErrorAsHresultForceFailure = -2147024809;
  v14 = -2147024809;
  if ( v10 )
  {
    v14 = 0;
    v15 = i - v10;
  }
  else
  {
    v15 = 0;
  }
  if ( !v10 )
    goto LABEL_29;
  if ( v15 != v9 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_12;
    }
    v21 = 182;
    goto LABEL_33;
  }
  LastErrorAsHresultForceFailure = v14;
LABEL_12:
  if ( SysStringLen(*((BSTR *)this + 10)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 183, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    LastErrorAsHresultForceFailure = -2147467259;
    goto LABEL_14;
  }
  if ( LastErrorAsHresultForceFailure >= 0 )
  {
    v19 = *((unsigned int *)this + 60);
    if ( (v19 & 1) == 0 )
    {
      LastErrorAsHresultForceFailure = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          184,
          &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
          v19,
          -2147467259);
      }
      goto LABEL_14;
    }
    v56 = SysAllocString(a2);
    v68 = (OLECHAR *)v56;
    v4 = (OLECHAR *)v56;
    if ( !v56 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 185, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      }
      LastErrorAsHresultForceFailure = -2147024882;
      goto LABEL_14;
    }
    FileW = (char *)CreateFileW(v56, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW != (char *)-1LL )
      goto LABEL_35;
    LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(v58, v57);
    v58 = (Imapi2Utility *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        186,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        (unsigned int)LastErrorAsHresultForceFailure);
    }
    if ( LastErrorAsHresultForceFailure >= 0 )
    {
LABEL_35:
      v70 = 0;
      v78 = 0;
      v79 = 0;
      LastErrorAsHresultForceFailure = CMsftDiscRecorder2::SaferDeviceIoControl(
                                         v58,
                                         FileW,
                                         0x2D1080u,
                                         0,
                                         0,
                                         &v78,
                                         0xCu,
                                         &v70);
      if ( LastErrorAsHresultForceFailure < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            187,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            (unsigned int)LastErrorAsHresultForceFailure);
        }
        goto LABEL_14;
      }
      if ( (_DWORD)v78 != 2 )
      {
        LastErrorAsHresultForceFailure = -2147467259;
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
        {
          goto LABEL_14;
        }
        v60 = 188;
        goto LABEL_100;
      }
      if ( v79 == -1 )
      {
        v22 = (unsigned __int8 *)CoTaskMemAlloc(0x104u);
        v67 = v22;
        if ( !v22 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 190, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
          }
          v6 = 0;
          LastErrorAsHresultForceFailure = -2147024882;
          v16 = 0;
          goto LABEL_15;
        }
        LastErrorAsHresultForceFailure = CMsftDiscRecorder2::SaferDeviceIoControl(
                                           (CMsftDiscRecorder2 *)&v71,
                                           FileW,
                                           0x24064u,
                                           0,
                                           0,
                                           v22,
                                           0x104u,
                                           &v71);
        if ( LastErrorAsHresultForceFailure < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              191,
              &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
              (unsigned int)LastErrorAsHresultForceFailure);
          }
          v6 = v67;
          v16 = 0;
          goto LABEL_15;
        }
        memset_0(*((void **)this + 28), 0, *((unsigned int *)this + 58));
        v23 = SysStringLen(a2);
        v24 = v23;
        v25 = 2 * v23;
        v26 = v25;
        v27 = LocalAlloc(0x40u, v25 + 4);
        memcpy_0(v27, a2, v26);
        *((_WORD *)v27 + v24) = 92;
        *((_WORD *)v27 + (unsigned int)(v24 + 1)) = 0;
        if ( GetVolumeNameForVolumeMountPointW((LPCWSTR)v27, *((LPWSTR *)this + 28), *((_DWORD *)this + 58) >> 1) )
        {
          v16 = SysAllocString(*((const OLECHAR **)this + 28));
          if ( !v16 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 193, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
            }
            LastErrorAsHresultForceFailure = -2147024882;
          }
        }
        else
        {
          LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(v29, v28);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              192,
              &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
              (unsigned int)LastErrorAsHresultForceFailure);
          }
          v16 = (OLECHAR *)cb;
        }
        LocalFree(v27);
        if ( LastErrorAsHresultForceFailure < 0 )
          goto LABEL_71;
        v85 = 0;
        *(_OWORD *)&v84[1] = 0;
        psz = v67[8];
        v81 = v67[9];
        v82 = v67[10];
        v83 = v67[11];
        LOWORD(v84[0]) = v67[12];
        WORD1(v84[0]) = v67[13];
        WORD2(v84[0]) = v67[14];
        HIWORD(v84[0]) = v67[15];
        v30 = SysAllocString(&psz);
        bstrString = v30;
        WORD2(v84[0]) = v67[22];
        HIWORD(v84[0]) = v67[23];
        LOWORD(v84[1]) = v67[24];
        v31 = v67[25];
        v85 = 0;
        v32 = v67[16];
        WORD1(v84[1]) = v31;
        v33 = v67[26];
        psz = v32;
        v34 = v67[17];
        WORD2(v84[1]) = v33;
        v35 = v67[27];
        v81 = v34;
        v36 = v67[18];
        HIWORD(v84[1]) = v35;
        v37 = v67[28];
        v82 = v36;
        v38 = v67[19];
        LOWORD(v84[2]) = v37;
        v39 = v67[29];
        v83 = v38;
        v40 = v67[20];
        WORD1(v84[2]) = v39;
        v41 = v67[30];
        LOWORD(v84[0]) = v40;
        v42 = v67[21];
        WORD2(v84[2]) = v41;
        v43 = v67[31];
        WORD1(v84[0]) = v42;
        HIWORD(v84[2]) = v43;
        v44 = SysAllocString(&psz);
        v85 = 0;
        v45 = v44;
        psz = v67[32];
        v81 = v67[33];
        v82 = v67[34];
        v83 = v67[35];
        v73 = v44;
        memset(v84, 0, sizeof(v84));
        v46 = SysAllocString(&psz);
        v74 = v46;
        if ( !v30 || !v45 || !v46 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 194, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
          }
          LastErrorAsHresultForceFailure = -2147024882;
          goto LABEL_71;
        }
        v2 = 0;
        v76 = 1;
        v70 = 0;
        cb = 0;
        v77 = 0;
        LastErrorAsHresultForceFailure = CMsftDiscRecorder2::SaferDeviceIoControl(
                                           v47,
                                           FileW,
                                           0x2D1400u,
                                           &v76,
                                           0xCu,
                                           &cb,
                                           8u,
                                           &v70);
        if ( LastErrorAsHresultForceFailure < 0 )
        {
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
          {
            goto LABEL_48;
          }
          v55 = 195;
          goto LABEL_69;
        }
        if ( v70 != 8 )
        {
          LastErrorAsHresultForceFailure = -2147467259;
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
          {
            goto LABEL_48;
          }
          v62 = 196;
          goto LABEL_133;
        }
        v63 = HIDWORD(cb);
        pv = CoTaskMemAlloc(HIDWORD(cb));
        v65 = pv;
        if ( !pv )
        {
          LastErrorAsHresultForceFailure = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              197,
              &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
              v63,
              v63);
            v6 = v67;
            v4 = v68;
            goto LABEL_15;
          }
          goto LABEL_48;
        }
        v70 = 0;
        v77 = 0;
        v76 = 1;
        LastErrorAsHresultForceFailure = CMsftDiscRecorder2::SaferDeviceIoControl(
                                           v64,
                                           FileW,
                                           0x2D1400u,
                                           &v76,
                                           0xCu,
                                           pv,
                                           v63,
                                           &v70);
        if ( LastErrorAsHresultForceFailure < 0 )
        {
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
          {
            goto LABEL_48;
          }
          v55 = 198;
        }
        else
        {
          if ( v70 != v63 )
          {
            LastErrorAsHresultForceFailure = -2147467259;
            v61 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
            {
              goto LABEL_48;
            }
            v62 = 199;
            goto LABEL_133;
          }
          v50 = v65[1];
          if ( v50 != v63 )
          {
            LastErrorAsHresultForceFailure = -2147467259;
            v61 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
            {
              goto LABEL_48;
            }
            v62 = 200;
            goto LABEL_133;
          }
          if ( v50 < 0x20 )
          {
            LastErrorAsHresultForceFailure = -2147467259;
            v61 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
            {
              goto LABEL_48;
            }
            v62 = 201;
            goto LABEL_133;
          }
          v70 = 0;
          cb = 0;
          v77 = 0;
          v76 = 0;
          LastErrorAsHresultForceFailure = CMsftDiscRecorder2::SaferDeviceIoControl(
                                             v49,
                                             FileW,
                                             0x2D1400u,
                                             &v76,
                                             0xCu,
                                             &cb,
                                             8u,
                                             &v70);
          if ( LastErrorAsHresultForceFailure >= 0 )
          {
            if ( v70 == 8 )
            {
              v51 = HIDWORD(cb);
              v66 = (CMsftDiscRecorder2 *)CoTaskMemAlloc(HIDWORD(cb));
              if ( v66 )
              {
                v70 = 0;
                v77 = 0;
                v76 = 0;
                LastErrorAsHresultForceFailure = CMsftDiscRecorder2::SaferDeviceIoControl(
                                                   v66,
                                                   FileW,
                                                   0x2D1400u,
                                                   &v76,
                                                   0xCu,
                                                   v66,
                                                   v51,
                                                   &v70);
                if ( LastErrorAsHresultForceFailure < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 22),
                      205,
                      &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
                      (unsigned int)LastErrorAsHresultForceFailure);
                    v2 = v66;
                    goto LABEL_48;
                  }
                }
                else
                {
                  if ( v70 == v51 )
                  {
                    v2 = v66;
                    v52 = *((_DWORD *)v66 + 1);
                    if ( v52 == v51 )
                    {
                      if ( v52 >= 0x24 )
                      {
                        v53 = bstrString;
                        *((_DWORD *)this + 60) &= ~1u;
                        v54 = HIDWORD(v78);
                        *((_DWORD *)this + 60) |= 2u;
                        *((_QWORD *)this + 12) = v53;
                        *((_QWORD *)this + 13) = v73;
                        *((_QWORD *)this + 14) = v74;
                        *((_DWORD *)this + 34) = v71;
                        *((_QWORD *)this + 10) = v68;
                        *((_QWORD *)this + 15) = v16;
                        *((_QWORD *)this + 16) = v67;
                        *((_DWORD *)this + 35) = v54;
                        *((_QWORD *)this + 11) = FileW;
                        *((_QWORD *)this + 18) = v65;
                        *((_QWORD *)this + 19) = v66;
                        goto LABEL_18;
                      }
                      LastErrorAsHresultForceFailure = -2147467259;
                      v61 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
                      {
                        goto LABEL_48;
                      }
                      v62 = 208;
                    }
                    else
                    {
                      LastErrorAsHresultForceFailure = -2147467259;
                      v61 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
                      {
                        goto LABEL_48;
                      }
                      v62 = 207;
                    }
                    goto LABEL_133;
                  }
                  LastErrorAsHresultForceFailure = -2147467259;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
                  {
                    WPP_SF_DDDd(
                      *((_QWORD *)WPP_GLOBAL_Control + 22),
                      206,
                      &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
                    v2 = v66;
                    goto LABEL_48;
                  }
                }
              }
              else
              {
                LastErrorAsHresultForceFailure = -2147024882;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
                {
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 22),
                    204,
                    &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
                    v51,
                    v51);
                  v2 = 0;
                  goto LABEL_48;
                }
              }
LABEL_71:
              v6 = v67;
              v2 = v66;
              v4 = v68;
              goto LABEL_15;
            }
            LastErrorAsHresultForceFailure = -2147467259;
            v61 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
            {
              goto LABEL_48;
            }
            v62 = 203;
LABEL_133:
            WPP_SF_DDDd(v61[22], v62, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
            goto LABEL_48;
          }
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
          {
            goto LABEL_48;
          }
          v55 = 202;
        }
LABEL_69:
        WPP_SF_d(
          v48[22],
          v55,
          &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
          (unsigned int)LastErrorAsHresultForceFailure);
LABEL_48:
        v6 = v67;
        v4 = v68;
        goto LABEL_15;
      }
      LastErrorAsHresultForceFailure = -2147467259;
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        v60 = 189;
LABEL_100:
        WPP_SF_(v59[22], v60, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      }
    }
  }
LABEL_14:
  v16 = 0;
LABEL_15:
  CoTaskMemFree(v2);
  CoTaskMemFree(pv);
  CoTaskMemFree(v6);
  SysFreeString(v16);
  SysFreeString(bstrString);
  SysFreeString(v73);
  SysFreeString(v74);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  SysFreeString(v4);
LABEL_18:
  if ( (LastErrorAsHresultForceFailure & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(LastErrorAsHresultForceFailure, (int)&CLSID_MsftDiscRecorder2, v17);
  return (unsigned int)LastErrorAsHresultForceFailure;
}

```

## disassembly

```asm
0x180003b00  mov     [rsp-8+arg_10], rbx
0x180003b05  push    rbp
0x180003b06  push    rsi
0x180003b07  push    rdi
0x180003b08  push    r12
0x180003b0a  push    r13
0x180003b0c  push    r14
0x180003b0e  push    r15
0x180003b10  lea     rbp, [rsp-27h]
0x180003b15  sub     rsp, 0E0h
0x180003b1c  mov     rax, cs:__security_cookie
0x180003b23  xor     rax, rsp
0x180003b26  mov     [rbp+57h+var_40], rax
0x180003b2a  xor     edi, edi
0x180003b2c  mov     r15, rcx
0x180003b2f  mov     rcx, rdx; pbstr
0x180003b32  mov     [rbp+57h+cb], rdi
0x180003b36  mov     r14d, edi
0x180003b39  mov     [rbp+57h+bstrString], rdi
0x180003b3d  mov     [rbp+57h+var_A0], rdi
0x180003b41  mov     r13d, edi
0x180003b44  mov     [rbp+57h+var_98], rdi
0x180003b48  mov     ebx, edi
0x180003b4a  mov     [rbp+57h+var_AC], edi
0x180003b4d  mov     r12, rdx
0x180003b50  mov     [rbp+57h+pv], rdi
0x180003b54  mov     [rbp+57h+var_D0], rdi
0x180003b58  call    cs:__imp_SysStringLen
0x180003b5e  lea     rdx, WPP_GLOBAL_Control
0x180003b65  test    eax, eax
0x180003b67  jz      loc_180003C90
0x180003b6d  mov     rcx, r12; pbstr
0x180003b70  call    cs:__imp_SysStringLen
0x180003b76  mov     r8d, eax
0x180003b79  test    r12, r12
0x180003b7c  jz      loc_180003D12
0x180003b82  lea     ecx, [rax+1]
0x180003b85  cmp     rcx, 7FFFFFFFh
0x180003b8c  ja      loc_180003D12
0x180003b92  mov     rax, r12
0x180003b95  mov     r9d, ecx
0x180003b98  test    rcx, rcx
0x180003b9b  jz      short loc_180003BAF
0x180003b9d  nop     dword ptr [rax]
0x180003ba0  cmp     [rax], bx
0x180003ba3  jz      short loc_180003BAF
0x180003ba5  add     rax, 2
0x180003ba9  sub     rcx, 1
0x180003bad  jnz     short loc_180003BA0
0x180003baf  mov     esi, 80070057h
0x180003bb4  test    rcx, rcx
0x180003bb7  mov     edx, esi
0x180003bb9  cmovnz  edx, edi
0x180003bbc  jz      loc_1800043DE
0x180003bc2  sub     r9, rcx
0x180003bc5  test    rcx, rcx
0x180003bc8  jz      loc_180003D17
0x180003bce  cmp     r9d, r8d
0x180003bd1  jnz     loc_1800043E6
0x180003bd7  mov     esi, edx
0x180003bd9  mov     rcx, [r15+50h]; pbstr
0x180003bdd  call    cs:__imp_SysStringLen
0x180003be3  test    eax, eax
0x180003be5  jnz     loc_180004421
0x180003beb  test    esi, esi
0x180003bed  jns     loc_180003CAA
0x180003bf3  mov     r12, rbx
0x180003bf6  mov     rcx, rdi; pv
0x180003bf9  call    cs:__imp_CoTaskMemFree
0x180003bff  mov     rcx, [rbp+57h+pv]; pv
0x180003c03  call    cs:__imp_CoTaskMemFree
0x180003c09  mov     rcx, rbx; pv
0x180003c0c  call    cs:__imp_CoTaskMemFree
0x180003c12  mov     rcx, r12; bstrString
0x180003c15  call    cs:__imp_SysFreeString
0x180003c1b  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180003c1f  call    cs:__imp_SysFreeString
0x180003c25  mov     rcx, [rbp+57h+var_A0]; bstrString
0x180003c29  call    cs:__imp_SysFreeString
0x180003c2f  mov     rcx, [rbp+57h+var_98]; bstrString
0x180003c33  call    cs:__imp_SysFreeString
0x180003c39  lea     rax, [r13-1]
0x180003c3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003c41  ja      short loc_180003C4C
0x180003c43  mov     rcx, r13; hObject
0x180003c46  call    cs:__imp_CloseHandle
0x180003c4c  mov     rcx, r14; bstrString
0x180003c4f  call    cs:__imp_SysFreeString
0x180003c55  mov     eax, esi
0x180003c57  and     eax, 80FF0000h
0x180003c5c  cmp     eax, 80AA0000h
0x180003c61  jz      loc_180004ACA
0x180003c67  mov     eax, esi
0x180003c69  mov     rcx, [rbp+57h+var_40]
0x180003c6d  xor     rcx, rsp; StackCookie
0x180003c70  call    __security_check_cookie
0x180003c75  mov     rbx, [rsp+110h+arg_10]
0x180003c7d  add     rsp, 0E0h
0x180003c84  pop     r15
0x180003c86  pop     r14
0x180003c88  pop     r13
0x180003c8a  pop     r12
0x180003c8c  pop     rdi
0x180003c8d  pop     rsi
0x180003c8e  pop     rbp
0x180003c8f  retn
0x180003c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c97  cmp     rcx, rdx
0x180003c9a  jnz     loc_1800043A7
0x180003ca0  mov     esi, 80070057h
0x180003ca5  jmp     loc_180003BD9
0x180003caa  mov     r9d, [r15+0F0h]
0x180003cb1  test    r9b, 1
0x180003cb5  jnz     loc_1800042FD
0x180003cbb  mov     esi, 80004005h
0x180003cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cc7  lea     rax, WPP_GLOBAL_Control
0x180003cce  cmp     rcx, rax
0x180003cd1  jz      loc_180003BF3
0x180003cd7  test    byte ptr [rcx+0BCh], 4
0x180003cde  jz      loc_180003BF3
0x180003ce4  cmp     byte ptr [rcx+0B9h], 3
0x180003ceb  jb      loc_180003BF3
0x180003cf1  mov     rcx, [rcx+0B0h]
0x180003cf8  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180003cff  mov     edx, 0B8h
0x180003d04  mov     [rsp+110h+dwCreationDisposition], esi
0x180003d08  call    WPP_SF_Dd
0x180003d0d  jmp     loc_180003BF3
0x180003d12  mov     esi, 80070057h
0x180003d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d1e  lea     rax, WPP_GLOBAL_Control
0x180003d25  cmp     rcx, rax
0x180003d28  jz      loc_180003BD9
0x180003d2e  test    byte ptr [rcx+0BCh], 4
0x180003d35  jz      loc_180003BD9
0x180003d3b  cmp     byte ptr [rcx+0B9h], 3
0x180003d42  jb      loc_180003BD9
0x180003d48  mov     edx, 0B5h
0x180003d4d  mov     rcx, [rcx+0B0h]
0x180003d54  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180003d5b  call    WPP_SF_
0x180003d60  jmp     loc_180003BD9
0x180003d65  test    esi, esi
0x180003d67  js      loc_180003BF3
0x180003d6d  xor     eax, eax
0x180003d6f  mov     [rbp+57h+var_B0], edi
0x180003d72  mov     [rbp+57h+var_78], rax
0x180003d76  xor     r9d, r9d; void *
0x180003d79  mov     [rbp+57h+var_70], eax
0x180003d7c  mov     r8d, 2D1080h; unsigned int
0x180003d82  lea     rax, [rbp+57h+var_B0]
0x180003d86  mov     rdx, r13; void *
0x180003d89  mov     [rsp+110h+var_D8], rax; unsigned int *
0x180003d8e  lea     rax, [rbp+57h+var_78]
0x180003d92  mov     dword ptr [rsp+110h+hTemplateFile], 0Ch; unsigned int
0x180003d9a  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax; void *
0x180003d9f  mov     [rsp+110h+dwCreationDisposition], edi; unsigned int
0x180003da3  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180003da8  mov     esi, eax
0x180003daa  test    eax, eax
0x180003dac  js      loc_180004084
0x180003db2  cmp     dword ptr [rbp+57h+var_78], 2
0x180003db6  jnz     loc_1800044AF
0x180003dbc  cmp     [rbp+57h+var_70], 0FFFFFFFFh
0x180003dc0  jnz     loc_180004509
0x180003dc6  mov     ecx, 104h; cb
0x180003dcb  call    cs:__imp_CoTaskMemAlloc
0x180003dd1  mov     [rbp+57h+var_C8], rax
0x180003dd5  test    rax, rax
0x180003dd8  jz      loc_180004541
0x180003dde  lea     rcx, [rbp+57h+var_AC]; this
0x180003de2  xor     r9d, r9d; void *
0x180003de5  mov     [rsp+110h+var_D8], rcx; unsigned int *
0x180003dea  mov     r8d, 24064h; unsigned int
0x180003df0  mov     dword ptr [rsp+110h+hTemplateFile], 104h; unsigned int
0x180003df8  mov     rdx, r13; void *
0x180003dfb  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax; void *
0x180003e00  mov     [rsp+110h+dwCreationDisposition], edi; unsigned int
0x180003e04  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180003e09  mov     esi, eax
0x180003e0b  test    eax, eax
0x180003e0d  js      loc_18000458F
0x180003e13  mov     r8d, [r15+0E8h]; Size
0x180003e1a  xor     edx, edx; Val
0x180003e1c  mov     rcx, [r15+0E0h]; void *
0x180003e23  call    memset_0
0x180003e28  mov     rcx, r12; pbstr
0x180003e2b  call    cs:__imp_SysStringLen
0x180003e31  mov     edi, eax
0x180003e33  mov     ecx, 40h ; '@'; uFlags
0x180003e38  lea     eax, [rdi+rdi]
0x180003e3b  lea     rdx, [rax+4]; uBytes
0x180003e3f  mov     ebx, eax
0x180003e41  call    cs:__imp_LocalAlloc
0x180003e47  mov     r8d, ebx; Size
0x180003e4a  mov     rdx, r12; Src
0x180003e4d  mov     rcx, rax; void *
0x180003e50  mov     r14, rax
0x180003e53  call    memcpy_0
0x180003e58  mov     word ptr [r14+rdi*2], 5Ch ; '\'
0x180003e5f  lea     ecx, [rdi+1]
0x180003e62  xor     eax, eax
0x180003e64  mov     [r14+rcx*2], ax
0x180003e69  mov     rcx, r14; lpszVolumeMountPoint
0x180003e6c  mov     r8d, [r15+0E8h]
0x180003e73  mov     rdx, [r15+0E0h]; lpszVolumeName
0x180003e7a  shr     r8d, 1; cchBufferLength
0x180003e7d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180003e83  test    eax, eax
0x180003e85  jz      loc_1800045DB
0x180003e8b  mov     rcx, [r15+0E0h]; psz
0x180003e92  call    cs:__imp_SysAllocString
0x180003e98  mov     r12, rax
0x180003e9b  test    rax, rax
0x180003e9e  jz      loc_18000462B
0x180003ea4  mov     rcx, r14; hMem
0x180003ea7  call    cs:__imp_LocalFree
0x180003ead  test    esi, esi
0x180003eaf  js      loc_1800042EC
0x180003eb5  mov     rsi, [rbp+57h+var_C8]
0x180003eb9  lea     rcx, [rbp+57h+psz]; psz
0x180003ebd  xor     eax, eax
0x180003ebf  xorps   xmm0, xmm0
0x180003ec2  mov     [rbp+57h+var_48], ax
0x180003ec6  movdqu  xmmword ptr [rbp+57h+var_60+8], xmm0
0x180003ecb  movzx   eax, byte ptr [rsi+8]
0x180003ecf  mov     [rbp+57h+psz], ax
0x180003ed3  movzx   eax, byte ptr [rsi+9]
0x180003ed7  mov     [rbp+57h+var_66], ax
0x180003edb  movzx   eax, byte ptr [rsi+0Ah]
0x180003edf  mov     [rbp+57h+var_64], ax
0x180003ee3  movzx   eax, byte ptr [rsi+0Bh]
0x180003ee7  mov     [rbp+57h+var_62], ax
0x180003eeb  movzx   eax, byte ptr [rsi+0Ch]
0x180003eef  mov     word ptr [rbp+57h+var_60], ax
0x180003ef3  movzx   eax, byte ptr [rsi+0Dh]
0x180003ef7  mov     word ptr [rbp+57h+var_60+2], ax
0x180003efb  movzx   eax, byte ptr [rsi+0Eh]
0x180003eff  mov     word ptr [rbp+57h+var_60+4], ax
0x180003f03  movzx   eax, byte ptr [rsi+0Fh]
0x180003f07  mov     word ptr [rbp+57h+var_60+6], ax
0x180003f0b  call    cs:__imp_SysAllocString
0x180003f11  mov     rdi, rax
0x180003f14  mov     [rbp+57h+bstrString], rax
0x180003f18  movzx   eax, byte ptr [rsi+16h]
0x180003f1c  xor     ecx, ecx
0x180003f1e  mov     word ptr [rbp+57h+var_60+4], ax
0x180003f22  movzx   eax, byte ptr [rsi+17h]
0x180003f26  mov     word ptr [rbp+57h+var_60+6], ax
0x180003f2a  movzx   eax, byte ptr [rsi+18h]
0x180003f2e  mov     word ptr [rbp+57h+var_60+8], ax
0x180003f32  movzx   eax, byte ptr [rsi+19h]
0x180003f36  mov     [rbp+57h+var_48], cx
0x180003f3a  movzx   ecx, byte ptr [rsi+10h]
0x180003f3e  mov     word ptr [rbp+57h+var_60+0Ah], ax
0x180003f42  movzx   eax, byte ptr [rsi+1Ah]
0x180003f46  mov     [rbp+57h+psz], cx
0x180003f4a  movzx   ecx, byte ptr [rsi+11h]
0x180003f4e  mov     word ptr [rbp+57h+var_60+0Ch], ax
0x180003f52  movzx   eax, byte ptr [rsi+1Bh]
0x180003f56  mov     [rbp+57h+var_66], cx
0x180003f5a  movzx   ecx, byte ptr [rsi+12h]
0x180003f5e  mov     word ptr [rbp+57h+var_60+0Eh], ax
0x180003f62  movzx   eax, byte ptr [rsi+1Ch]
0x180003f66  mov     [rbp+57h+var_64], cx
0x180003f6a  movzx   ecx, byte ptr [rsi+13h]
0x180003f6e  mov     word ptr [rbp+57h+var_60+10h], ax
0x180003f72  movzx   eax, byte ptr [rsi+1Dh]
0x180003f76  mov     [rbp+57h+var_62], cx
0x180003f7a  movzx   ecx, byte ptr [rsi+14h]
0x180003f7e  mov     word ptr [rbp+57h+var_60+12h], ax
0x180003f82  movzx   eax, byte ptr [rsi+1Eh]
0x180003f86  mov     word ptr [rbp+57h+var_60], cx
0x180003f8a  movzx   ecx, byte ptr [rsi+15h]
0x180003f8e  mov     word ptr [rbp+57h+var_60+14h], ax
0x180003f92  movzx   eax, byte ptr [rsi+1Fh]
0x180003f96  mov     word ptr [rbp+57h+var_60+2], cx
0x180003f9a  lea     rcx, [rbp+57h+psz]; psz
0x180003f9e  mov     word ptr [rbp+57h+var_60+16h], ax
0x180003fa2  call    cs:__imp_SysAllocString
0x180003fa8  xor     ecx, ecx
0x180003faa  mov     qword ptr [rbp+57h+var_60+10h], 0
0x180003fb2  mov     [rbp+57h+var_48], cx
0x180003fb6  xorps   xmm0, xmm0
0x180003fb9  movzx   ecx, byte ptr [rsi+20h]
0x180003fbd  mov     rbx, rax
0x180003fc0  mov     [rbp+57h+psz], cx
0x180003fc4  movzx   ecx, byte ptr [rsi+21h]
0x180003fc8  mov     [rbp+57h+var_66], cx
0x180003fcc  movzx   ecx, byte ptr [rsi+22h]
0x180003fd0  mov     [rbp+57h+var_64], cx
0x180003fd4  movzx   ecx, byte ptr [rsi+23h]
0x180003fd8  mov     [rbp+57h+var_62], cx
0x180003fdc  lea     rcx, [rbp+57h+psz]; psz
0x180003fe0  mov     [rbp+57h+var_A0], rax
0x180003fe4  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180003fe9  call    cs:__imp_SysAllocString
0x180003fef  mov     [rbp+57h+var_98], rax
0x180003ff3  test    rdi, rdi
  ... truncated ...
```
