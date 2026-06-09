# UpdateMSITables(ulong,ushort const *,ushort const *)

- ea: `0x180026978`
- end: `0x180026d8f`
- name: `?UpdateMSITables@@YAJKPEBG0@Z`
- size: `1047`
- prototype: `__int64 __fastcall(MSIHANDLE hDatabase, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002673c`

## callees

- `0x180009ee0`
- `0x180026978`
- `0x180055550`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x180026b52`
- `msi!__imp_MsiCloseHandle` at `0x180026bb3`
- `msi!__imp_MsiCloseHandle` at `0x180026c41`
- `msi!__imp_MsiCloseHandle` at `0x180026c74`
- `msi!__imp_MsiCloseHandle` at `0x180026c7e`
- `msi!__imp_MsiCloseHandle` at `0x180026d0f`
- `msi!__imp_MsiCloseHandle` at `0x180026d42`
- `msi!__imp_MsiCloseHandle` at `0x180026d4c`
- `msi!__imp_MsiCloseHandle` at `0x180026b52`
- `msi!__imp_MsiCloseHandle` at `0x180026bb3`
- `msi!__imp_MsiCloseHandle` at `0x180026c41`
- `msi!__imp_MsiCloseHandle` at `0x180026c74`
- `msi!__imp_MsiCloseHandle` at `0x180026c7e`
- `msi!__imp_MsiCloseHandle` at `0x180026d0f`
- `msi!__imp_MsiCloseHandle` at `0x180026d42`
- `msi!__imp_MsiCloseHandle` at `0x180026d4c`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026b30`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026b91`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026bed`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026cbb`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026b30`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026b91`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026bed`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026cbb`
- `msi!__imp_MsiRecordSetStringW` at `0x180026c1d`
- `msi!__imp_MsiRecordSetStringW` at `0x180026ceb`
- `msi!__imp_MsiRecordSetStringW` at `0x180026c1d`
- `msi!__imp_MsiRecordSetStringW` at `0x180026ceb`
- `msi!__imp_MsiViewExecute` at `0x180026b46`
- `msi!__imp_MsiViewExecute` at `0x180026ba7`
- `msi!__imp_MsiViewExecute` at `0x180026c03`
- `msi!__imp_MsiViewExecute` at `0x180026cd1`
- `msi!__imp_MsiViewExecute` at `0x180026b46`
- `msi!__imp_MsiViewExecute` at `0x180026ba7`
- `msi!__imp_MsiViewExecute` at `0x180026c03`
- `msi!__imp_MsiViewExecute` at `0x180026cd1`
- `msi!__imp_MsiViewFetch` at `0x180026c58`
- `msi!__imp_MsiViewFetch` at `0x180026d26`
- `msi!__imp_MsiViewFetch` at `0x180026c58`
- `msi!__imp_MsiViewFetch` at `0x180026d26`
- `msi!__imp_MsiViewModify` at `0x180026c33`
- `msi!__imp_MsiViewModify` at `0x180026d01`
- `msi!__imp_MsiViewModify` at `0x180026c33`
- `msi!__imp_MsiViewModify` at `0x180026d01`

## string_xrefs

- `0x1800269a4`: `UPDATE Class SET AppId_ = '%s' WHERE AppId_ = '%s'`
- `0x180026a16`: `UPDATE Component SET ComponentId = '%s' WHERE ComponentId = '%s'`

## pseudocode

```c
__int64 __fastcall UpdateMSITables(MSIHANDLE hDatabase, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 result; // rax
  signed int v7; // ebx
  bool v8; // cc
  UINT v9; // eax
  UINT v10; // eax
  MSIHANDLE phView; // [rsp+30h] [rbp-D0h] BYREF
  MSIHANDLE hRecord[3]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 v13[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h]
  __int128 v15; // [rsp+60h] [rbp-A0h]
  __int128 v16; // [rsp+70h] [rbp-90h]
  __int128 v17; // [rsp+80h] [rbp-80h]
  _OWORD v18[2]; // [rsp+90h] [rbp-70h]
  unsigned __int16 v19[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v20; // [rsp+C0h] [rbp-40h]
  __int128 v21; // [rsp+D0h] [rbp-30h]
  _OWORD v22[2]; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v23[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v24; // [rsp+110h] [rbp+10h]
  __int128 v25; // [rsp+120h] [rbp+20h]
  __int128 v26; // [rsp+130h] [rbp+30h]
  __int128 v27; // [rsp+140h] [rbp+40h]
  __int128 v28; // [rsp+150h] [rbp+50h]
  __int128 v29; // [rsp+160h] [rbp+60h]
  __int128 v30; // [rsp+170h] [rbp+70h]
  wchar_t v31; // [rsp+180h] [rbp+80h]
  unsigned __int16 v32[8]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v33; // [rsp+1A0h] [rbp+A0h]
  __int128 v34; // [rsp+1B0h] [rbp+B0h]
  __int128 v35; // [rsp+1C0h] [rbp+C0h]
  _OWORD v36[2]; // [rsp+1D0h] [rbp+D0h]
  WCHAR szQuery[152]; // [rsp+1F0h] [rbp+F0h] BYREF

  *(_OWORD *)v13 = *(_OWORD *)L"UPDATE Class SET AppId_ = '%s' WHERE AppId_ = '%s'";
  v15 = *(_OWORD *)L" AppId_ = '%s' WHERE AppId_ = '%s'";
  v14 = *(_OWORD *)L"lass SET AppId_ = '%s' WHERE AppId_ = '%s'";
  v17 = *(_OWORD *)L"HERE AppId_ = '%s'";
  v16 = *(_OWORD *)L"= '%s' WHERE AppId_ = '%s'";
  v18[0] = *(_OWORD *)L"Id_ = '%s'";
  *(_QWORD *)((char *)v18 + 14) = *(_QWORD *)L"%s'";
  v24 = *(_OWORD *)L"omponent SET ComponentId = '%s' WHERE ComponentId = '%s'";
  v26 = *(_OWORD *)L"ponentId = '%s' WHERE ComponentId = '%s'";
  v31 = aUpdateComponen[64];
  *(_OWORD *)v23 = *(_OWORD *)L"UPDATE Component SET ComponentId = '%s' WHERE ComponentId = '%s'";
  phView = 0;
  v28 = *(_OWORD *)L"WHERE ComponentId = '%s'";
  v25 = *(_OWORD *)L" SET ComponentId = '%s' WHERE ComponentId = '%s'";
  v30 = *(_OWORD *)L"d = '%s'";
  v27 = *(_OWORD *)L" = '%s' WHERE ComponentId = '%s'";
  *(_OWORD *)v19 = *(_OWORD *)L"SELECT * FROM AppId WHERE AppId = '%s'";
  v29 = *(_OWORD *)L"mponentId = '%s'";
  v21 = *(_OWORD *)L"pId WHERE AppId = '%s'";
  v20 = *(_OWORD *)L" FROM AppId WHERE AppId = '%s'";
  v22[0] = *(_OWORD *)L"E AppId = '%s'";
  *(_OWORD *)((char *)v22 + 14) = *(_OWORD *)L" = '%s'";
  v33 = *(_OWORD *)L" FROM Upgrade WHERE UpgradeCode = '%s'";
  *(_OWORD *)v32 = *(_OWORD *)L"SELECT * FROM Upgrade WHERE UpgradeCode = '%s'";
  v35 = *(_OWORD *)L"ERE UpgradeCode = '%s'";
  v34 = *(_OWORD *)L"grade WHERE UpgradeCode = '%s'";
  v36[0] = *(_OWORD *)L"adeCode = '%s'";
  *(_OWORD *)((char *)v36 + 14) = *(_OWORD *)L" = '%s'";
  result = StringCchPrintfW(szQuery, 0x91u, v13, a3, a2);
  if ( (int)result < 0 )
    return result;
  v7 = MsiDatabaseOpenViewW(hDatabase, szQuery, &phView);
  if ( v7 )
    goto LABEL_34;
  v7 = MsiViewExecute(phView, 0);
  MsiCloseHandle(phView);
  v8 = v7 <= 0;
  if ( v7 )
    goto LABEL_35;
  result = StringCchPrintfW(szQuery, 0x91u, v23, a3, a2);
  if ( (int)result < 0 )
    return result;
  v7 = MsiDatabaseOpenViewW(hDatabase, szQuery, &phView);
  if ( v7 )
  {
LABEL_34:
    v8 = v7 <= 0;
    goto LABEL_35;
  }
  v7 = MsiViewExecute(phView, 0);
  MsiCloseHandle(phView);
  v8 = v7 <= 0;
  if ( !v7 )
  {
    result = StringCchPrintfW(szQuery, 0x91u, v19, a2);
    if ( (int)result < 0 )
      return result;
    v7 = MsiDatabaseOpenViewW(hDatabase, szQuery, &phView);
    if ( !v7 )
    {
      v7 = MsiViewExecute(phView, 0);
      if ( !v7 )
      {
        while ( 1 )
        {
          hRecord[0] = 0;
          v9 = MsiViewFetch(phView, hRecord);
          if ( v9 )
            break;
          v9 = MsiRecordSetStringW(hRecord[0], 1u, a3);
          if ( v9 )
            break;
          v9 = MsiViewModify(phView, MSIMODIFY_REPLACE, hRecord[0]);
          if ( v9 )
            break;
          MsiCloseHandle(hRecord[0]);
        }
        v7 = 0;
        if ( v9 != 259 )
          v7 = v9;
        if ( hRecord[0] )
          MsiCloseHandle(hRecord[0]);
      }
      MsiCloseHandle(phView);
      v8 = v7 <= 0;
      if ( v7 )
        goto LABEL_35;
      result = StringCchPrintfW(szQuery, 0x91u, v32, a2);
      if ( (int)result < 0 )
        return result;
      v7 = MsiDatabaseOpenViewW(hDatabase, szQuery, &phView);
      if ( !v7 )
      {
        v7 = MsiViewExecute(phView, 0);
        if ( !v7 )
        {
          while ( 1 )
          {
            hRecord[0] = 0;
            v10 = MsiViewFetch(phView, hRecord);
            if ( v10 )
              break;
            v10 = MsiRecordSetStringW(hRecord[0], 1u, a3);
            if ( v10 )
              break;
            v10 = MsiViewModify(phView, MSIMODIFY_REPLACE, hRecord[0]);
            if ( v10 )
              break;
            MsiCloseHandle(hRecord[0]);
          }
          v7 = 0;
          if ( v10 != 259 )
            v7 = v10;
          if ( hRecord[0] )
            MsiCloseHandle(hRecord[0]);
        }
        MsiCloseHandle(phView);
        v8 = v7 <= 0;
        if ( !v7 )
          return 0;
        goto LABEL_35;
      }
    }
    goto LABEL_34;
  }
LABEL_35:
  if ( !v8 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026978  mov     [rsp-8+arg_18], rbx
0x18002697d  push    rbp
0x18002697e  push    rsi
0x18002697f  push    rdi
0x180026980  push    r12
0x180026982  push    r14
0x180026984  lea     rbp, [rsp-230h]
0x18002698c  sub     rsp, 330h
0x180026993  mov     rax, cs:__security_cookie
0x18002699a  xor     rax, rsp
0x18002699d  mov     [rbp+250h+var_30], rax
0x1800269a4  movaps  xmm0, xmmword ptr cs:aUpdateClassSet; "UPDATE Class SET AppId_ = '%s' WHERE Ap"...
0x1800269ab  mov     r14, r8
0x1800269ae  movaps  xmm1, xmmword ptr cs:aUpdateClassSet+10h; "lass SET AppId_ = '%s' WHERE AppId_ = '"...
0x1800269b5  mov     rsi, rdx
0x1800269b8  movzx   eax, word ptr cs:aUpdateComponen+80h; ""
0x1800269bf  mov     edi, ecx
0x1800269c1  movaps  xmmword ptr [rsp+350h+var_310], xmm0
0x1800269c6  lea     rcx, [rbp+250h+szQuery]; unsigned __int16 *
0x1800269cd  movaps  xmm0, xmmword ptr cs:aUpdateClassSet+20h; " AppId_ = '%s' WHERE AppId_ = '%s'"
0x1800269d4  mov     r9, r8
0x1800269d7  movaps  [rsp+350h+var_2F0], xmm0
0x1800269dc  lea     r8, [rsp+350h+var_310]; unsigned __int16 *
0x1800269e1  movaps  xmm0, xmmword ptr cs:aUpdateClassSet+40h; "HERE AppId_ = '%s'"
0x1800269e8  mov     r12d, 91h
0x1800269ee  movaps  [rsp+350h+var_300], xmm1
0x1800269f3  movaps  xmm1, xmmword ptr cs:aUpdateClassSet+30h; "= '%s' WHERE AppId_ = '%s'"
0x1800269fa  movaps  [rbp+250h+var_2D0], xmm0
0x1800269fe  movsd   xmm0, qword ptr cs:aUpdateClassSet+5Eh; "%s'"
0x180026a06  movaps  [rsp+350h+var_2E0], xmm1
0x180026a0b  movaps  xmm1, xmmword ptr cs:aUpdateClassSet+50h; "Id_ = '%s'"
0x180026a12  movaps  xmmword ptr [rbp+250h+var_2C0], xmm1
0x180026a16  movaps  xmm1, xmmword ptr cs:aUpdateComponen; "UPDATE Component SET ComponentId = '%s'"...
0x180026a1d  movsd   qword ptr [rbp+250h+var_2C0+0Eh], xmm0
0x180026a22  movaps  xmm0, xmmword ptr cs:aUpdateComponen+10h; "omponent SET ComponentId = '%s' WHERE C"...
0x180026a29  movups  [rbp+250h+var_240], xmm0
0x180026a2d  mov     [rsp+350h+var_330], rdx
0x180026a32  mov     edx, r12d; unsigned __int64
0x180026a35  movaps  xmm0, xmmword ptr cs:aUpdateComponen+30h; "ponentId = '%s' WHERE ComponentId = '%s"...
0x180026a3c  movups  [rbp+250h+var_220], xmm0
0x180026a40  mov     [rbp+250h+var_1D0], ax
0x180026a47  movaps  xmm0, xmmword ptr cs:aUpdateComponen+50h; "WHERE ComponentId = '%s'"
0x180026a4e  movups  xmmword ptr [rbp+250h+var_250], xmm1
0x180026a52  mov     [rsp+350h+phView], 0
0x180026a5a  movaps  xmm1, xmmword ptr cs:aUpdateComponen+20h; " SET ComponentId = '%s' WHERE Component"...
0x180026a61  movups  [rbp+250h+var_200], xmm0
0x180026a65  movaps  xmm0, xmmword ptr cs:aUpdateComponen+70h; "d = '%s'"
0x180026a6c  movups  [rbp+250h+var_230], xmm1
0x180026a70  movaps  xmm1, xmmword ptr cs:aUpdateComponen+40h; " = '%s' WHERE ComponentId = '%s'"
0x180026a77  movups  [rbp+250h+var_1E0], xmm0
0x180026a7b  movaps  xmm0, xmmword ptr cs:aSelectFromAppi; "SELECT * FROM AppId WHERE AppId = '%s'"
0x180026a82  movups  [rbp+250h+var_210], xmm1
0x180026a86  movaps  xmm1, xmmword ptr cs:aUpdateComponen+60h; "mponentId = '%s'"
0x180026a8d  movaps  xmmword ptr [rbp+250h+var_2A0], xmm0
0x180026a91  movaps  xmm0, xmmword ptr cs:aSelectFromAppi+20h; "pId WHERE AppId = '%s'"
0x180026a98  movups  [rbp+250h+var_1F0], xmm1
0x180026a9c  movaps  xmm1, xmmword ptr cs:aSelectFromAppi+10h; " FROM AppId WHERE AppId = '%s'"
0x180026aa3  movaps  [rbp+250h+var_280], xmm0
0x180026aa7  movups  xmm0, xmmword ptr cs:aSelectFromAppi+3Eh; " = '%s'"
0x180026aae  movaps  [rbp+250h+var_290], xmm1
0x180026ab2  movaps  xmm1, xmmword ptr cs:aSelectFromAppi+30h; "E AppId = '%s'"
0x180026ab9  movaps  xmmword ptr [rbp+250h+var_270], xmm1
0x180026abd  movaps  xmm1, xmmword ptr cs:aSelectFromUpgr; "SELECT * FROM Upgrade WHERE UpgradeCode"...
0x180026ac4  movups  xmmword ptr [rbp+250h+var_270+0Eh], xmm0
0x180026ac8  movaps  xmm0, xmmword ptr cs:aSelectFromUpgr+10h; " FROM Upgrade WHERE UpgradeCode = '%s'"
0x180026acf  movaps  [rbp+250h+var_1B0], xmm0
0x180026ad6  movaps  xmm0, xmmword ptr cs:aSelectFromUpgr+30h; "ERE UpgradeCode = '%s'"
0x180026add  movaps  xmmword ptr [rbp+250h+var_1C0], xmm1
0x180026ae4  movaps  xmm1, xmmword ptr cs:aSelectFromUpgr+20h; "grade WHERE UpgradeCode = '%s'"
0x180026aeb  movaps  [rbp+250h+var_190], xmm0
0x180026af2  movups  xmm0, xmmword ptr cs:aSelectFromUpgr+4Eh; " = '%s'"
0x180026af9  movaps  [rbp+250h+var_1A0], xmm1
0x180026b00  movaps  xmm1, xmmword ptr cs:aSelectFromUpgr+40h; "adeCode = '%s'"
0x180026b07  movaps  xmmword ptr [rbp+250h+var_180], xmm1
0x180026b0e  movups  xmmword ptr [rbp+250h+var_180+0Eh], xmm0
0x180026b15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026b1a  test    eax, eax
0x180026b1c  js      loc_180026D69
0x180026b22  lea     r8, [rsp+350h+phView]; phView
0x180026b27  mov     ecx, edi; hDatabase
0x180026b29  lea     rdx, [rbp+250h+szQuery]; szQuery
0x180026b30  call    cs:__imp_MsiDatabaseOpenViewW
0x180026b36  mov     ebx, eax
0x180026b38  test    eax, eax
0x180026b3a  jnz     loc_180026D5A
0x180026b40  mov     ecx, [rsp+350h+phView]; hView
0x180026b44  xor     edx, edx; hRecord
0x180026b46  call    cs:__imp_MsiViewExecute
0x180026b4c  mov     ecx, [rsp+350h+phView]; hAny
0x180026b50  mov     ebx, eax
0x180026b52  call    cs:__imp_MsiCloseHandle
0x180026b58  test    ebx, ebx
0x180026b5a  jnz     loc_180026D5C
0x180026b60  mov     r9, r14
0x180026b63  mov     [rsp+350h+var_330], rsi
0x180026b68  lea     r8, [rbp+250h+var_250]; unsigned __int16 *
0x180026b6c  mov     edx, r12d; unsigned __int64
0x180026b6f  lea     rcx, [rbp+250h+szQuery]; unsigned __int16 *
0x180026b76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026b7b  test    eax, eax
0x180026b7d  js      loc_180026D69
0x180026b83  lea     r8, [rsp+350h+phView]; phView
0x180026b88  mov     ecx, edi; hDatabase
0x180026b8a  lea     rdx, [rbp+250h+szQuery]; szQuery
0x180026b91  call    cs:__imp_MsiDatabaseOpenViewW
0x180026b97  mov     ebx, eax
0x180026b99  test    eax, eax
0x180026b9b  jnz     loc_180026D5A
0x180026ba1  mov     ecx, [rsp+350h+phView]; hView
0x180026ba5  xor     edx, edx; hRecord
0x180026ba7  call    cs:__imp_MsiViewExecute
0x180026bad  mov     ecx, [rsp+350h+phView]; hAny
0x180026bb1  mov     ebx, eax
0x180026bb3  call    cs:__imp_MsiCloseHandle
0x180026bb9  test    ebx, ebx
0x180026bbb  jnz     loc_180026D5C
0x180026bc1  mov     r9, rsi
0x180026bc4  lea     r8, [rbp+250h+var_2A0]; unsigned __int16 *
0x180026bc8  mov     edx, r12d; unsigned __int64
0x180026bcb  lea     rcx, [rbp+250h+szQuery]; unsigned __int16 *
0x180026bd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026bd7  test    eax, eax
0x180026bd9  js      loc_180026D69
0x180026bdf  lea     r8, [rsp+350h+phView]; phView
0x180026be4  mov     ecx, edi; hDatabase
0x180026be6  lea     rdx, [rbp+250h+szQuery]; szQuery
0x180026bed  call    cs:__imp_MsiDatabaseOpenViewW
0x180026bf3  mov     ebx, eax
0x180026bf5  test    eax, eax
0x180026bf7  jnz     loc_180026D5A
0x180026bfd  mov     ecx, [rsp+350h+phView]; hView
0x180026c01  xor     edx, edx; hRecord
0x180026c03  call    cs:__imp_MsiViewExecute
0x180026c09  mov     ebx, eax
0x180026c0b  test    eax, eax
0x180026c0d  jnz     short loc_180026C7A
0x180026c0f  jmp     short loc_180026C47
0x180026c11  mov     ecx, [rsp+350h+hRecord]; hRecord
0x180026c15  mov     r8, r14; szValue
0x180026c18  mov     edx, 1; iField
0x180026c1d  call    cs:__imp_MsiRecordSetStringW
0x180026c23  test    eax, eax
0x180026c25  jnz     short loc_180026C62
0x180026c27  mov     r8d, [rsp+350h+hRecord]; hRecord
0x180026c2c  lea     edx, [rax+4]; eModifyMode
0x180026c2f  mov     ecx, [rsp+350h+phView]; hView
0x180026c33  call    cs:__imp_MsiViewModify
0x180026c39  test    eax, eax
0x180026c3b  jnz     short loc_180026C62
0x180026c3d  mov     ecx, [rsp+350h+hRecord]; hAny
0x180026c41  call    cs:__imp_MsiCloseHandle
0x180026c47  mov     ecx, [rsp+350h+phView]; hView
0x180026c4b  lea     rdx, [rsp+350h+hRecord]; phRecord
0x180026c50  mov     [rsp+350h+hRecord], 0
0x180026c58  call    cs:__imp_MsiViewFetch
0x180026c5e  test    eax, eax
0x180026c60  jz      short loc_180026C11
0x180026c62  mov     ecx, [rsp+350h+hRecord]; hAny
0x180026c66  xor     ebx, ebx
0x180026c68  cmp     eax, 103h
0x180026c6d  cmovnz  ebx, eax
0x180026c70  test    ecx, ecx
0x180026c72  jz      short loc_180026C7A
0x180026c74  call    cs:__imp_MsiCloseHandle
0x180026c7a  mov     ecx, [rsp+350h+phView]; hAny
0x180026c7e  call    cs:__imp_MsiCloseHandle
0x180026c84  test    ebx, ebx
0x180026c86  jnz     loc_180026D5C
0x180026c8c  mov     r9, rsi
0x180026c8f  lea     r8, [rbp+250h+var_1C0]; unsigned __int16 *
0x180026c96  mov     rdx, r12; unsigned __int64
0x180026c99  lea     rcx, [rbp+250h+szQuery]; unsigned __int16 *
0x180026ca0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026ca5  test    eax, eax
0x180026ca7  js      loc_180026D69
0x180026cad  lea     r8, [rsp+350h+phView]; phView
0x180026cb2  mov     ecx, edi; hDatabase
0x180026cb4  lea     rdx, [rbp+250h+szQuery]; szQuery
0x180026cbb  call    cs:__imp_MsiDatabaseOpenViewW
0x180026cc1  mov     ebx, eax
0x180026cc3  test    eax, eax
0x180026cc5  jnz     loc_180026D5A
0x180026ccb  mov     ecx, [rsp+350h+phView]; hView
0x180026ccf  xor     edx, edx; hRecord
0x180026cd1  call    cs:__imp_MsiViewExecute
0x180026cd7  mov     ebx, eax
0x180026cd9  test    eax, eax
0x180026cdb  jnz     short loc_180026D48
0x180026cdd  jmp     short loc_180026D15
0x180026cdf  mov     ecx, [rsp+350h+hRecord]; hRecord
0x180026ce3  mov     r8, r14; szValue
0x180026ce6  mov     edx, 1; iField
0x180026ceb  call    cs:__imp_MsiRecordSetStringW
0x180026cf1  test    eax, eax
0x180026cf3  jnz     short loc_180026D30
0x180026cf5  mov     r8d, [rsp+350h+hRecord]; hRecord
0x180026cfa  lea     edx, [rax+4]; eModifyMode
0x180026cfd  mov     ecx, [rsp+350h+phView]; hView
0x180026d01  call    cs:__imp_MsiViewModify
0x180026d07  test    eax, eax
0x180026d09  jnz     short loc_180026D30
0x180026d0b  mov     ecx, [rsp+350h+hRecord]; hAny
0x180026d0f  call    cs:__imp_MsiCloseHandle
0x180026d15  mov     ecx, [rsp+350h+phView]; hView
0x180026d19  lea     rdx, [rsp+350h+hRecord]; phRecord
0x180026d1e  mov     [rsp+350h+hRecord], 0
0x180026d26  call    cs:__imp_MsiViewFetch
0x180026d2c  test    eax, eax
0x180026d2e  jz      short loc_180026CDF
0x180026d30  mov     ecx, [rsp+350h+hRecord]; hAny
0x180026d34  xor     ebx, ebx
0x180026d36  cmp     eax, 103h
0x180026d3b  cmovnz  ebx, eax
0x180026d3e  test    ecx, ecx
0x180026d40  jz      short loc_180026D48
0x180026d42  call    cs:__imp_MsiCloseHandle
0x180026d48  mov     ecx, [rsp+350h+phView]; hAny
0x180026d4c  call    cs:__imp_MsiCloseHandle
0x180026d52  test    ebx, ebx
0x180026d54  jnz     short loc_180026D5C
0x180026d56  xor     eax, eax
0x180026d58  jmp     short loc_180026D69
0x180026d5a  test    ebx, ebx
0x180026d5c  jle     short loc_180026D67
0x180026d5e  movzx   ebx, bx
0x180026d61  or      ebx, 80070000h
0x180026d67  mov     eax, ebx
0x180026d69  mov     rcx, [rbp+250h+var_30]
0x180026d70  xor     rcx, rsp; StackCookie
0x180026d73  call    __security_check_cookie
0x180026d78  mov     rbx, [rsp+350h+arg_18]
0x180026d80  add     rsp, 330h
0x180026d87  pop     r14
0x180026d89  pop     r12
0x180026d8b  pop     rdi
0x180026d8c  pop     rsi
0x180026d8d  pop     rbp
0x180026d8e  retn
```
