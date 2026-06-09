# CheckGPOs(_GPEXT *,_GPOINFO *,ulong,int *,int *,_GROUP_POLICY_OBJECTW * *)

- ea: `0x180002530`
- end: `0x18000375f`
- name: `?CheckGPOs@@YAHPEAU_GPEXT@@PEAU_GPOINFO@@KPEAH2PEAPEAU_GROUP_POLICY_OBJECTW@@@Z`
- size: `4655`
- prototype: `__int64 __fastcall(struct _GPEXT *, struct _GPOINFO *, unsigned int, int *, int *, struct _GROUP_POLICY_OBJECTW **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058f20`
- `0x18005ce5c`

## callees

- `0x180002530`
- `0x180003770`
- `0x180003800`
- `0x18002ba60`
- `0x18007521c`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002607`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002881`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800028f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002903`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002607`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002881`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800028f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002823`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002787`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003677`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002787`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003677`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002ab0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002b53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002c6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002e93`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003639`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002ab0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002b53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002c6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002e93`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003639`

## string_xrefs

- `0x1800035c2`: `GetDeletedList: No old GPOs.  Leaving.`
- `0x1800035f7`: `GetDeletedList: No old GPOs.  Leaving.`
- `0x18000369a`: `GetDeletedGPOList: Finished.`
- `0x1800036cc`: `GetDeletedGPOList: Finished.`
- `0x180002adc`: `CheckForGPOsToRemove: GPO <%s> needs to be removed`
- `0x180002b0a`: `CheckForGPOsToRemove: GPO <%s> needs to be removed`
- `0x180002b7f`: `CheckForGPOsToRemove: GPO <%s> needs to be removed`
- `0x180002bad`: `CheckForGPOsToRemove: GPO <%s> needs to be removed`
- `0x180002c04`: `CompareGPOLists:  One list is empty`
- `0x180002c2e`: `CompareGPOLists:  One list is empty`
- `0x180002e2a`: `CompareGPOLists:  One list is empty`
- `0x180002e54`: `CompareGPOLists:  One list is empty`
- `0x180002d68`: `CompareGPOLists:  Different entries found.`
- `0x180002d9d`: `CompareGPOLists:  Different entries found.`
- `0x180002f8f`: `CompareGPOLists:  Different entries found.`
- `0x180002fc4`: `CompareGPOLists:  Different entries found.`
- `0x180002d02`: `CompareGPOLists:  Different version numbers found`
- `0x180002d37`: `CompareGPOLists:  Different version numbers found`
- `0x180002f29`: `CompareGPOLists:  Different version numbers found`
- `0x180002f5e`: `CompareGPOLists:  Different version numbers found`
- `0x180002c41`: `CompareGPOLists:  One list has more entries than the other`
- `0x180002cd1`: `CompareGPOLists:  One list has more entries than the other`
- `0x180002e67`: `CompareGPOLists:  One list has more entries than the other`
- `0x180002ef8`: `CompareGPOLists:  One list has more entries than the other`
- `0x1800027fe`: `CompareGPOLists:  The lists are the same.`
- `0x180002dc1`: `CompareGPOLists:  The lists are the same.`
- `0x180002df6`: `CompareGPOLists:  The lists are the same.`
- `0x180002ff8`: `CompareGPOLists:  The lists are the same.`
- `0x18000293e`: `CheckGPOs: ReadGPOList count = %d`
- `0x180002980`: `CheckGPOs: ReadGPOList count = %d`
- `0x1800029ab`: `CheckGPOs: ReadGPOList failed.`
- `0x1800029d5`: `CheckGPOs: ReadGPOList failed.`
- `0x180002a11`: `CheckGPOs: ReadGPOList count = %d for user: %ls`
- `0x180002a57`: `CheckGPOs: ReadGPOList count = %d for user: %ls`
- `0x1800028ba`: `CheckGPOs: ReadGPOList for user local settings failed.`
- `0x180002a81`: `CheckGPOs: ReadGPOList for user local settings failed.`
- `0x180003713`: `CheckGPOs: GetDeletedList failed for %s.`
- `0x180003749`: `CheckGPOs: GetDeletedList failed for %s.`
- `0x18000301e`: `CheckGPOs: No GPO changes but couldn't read extension %s's status or policy time.`
- `0x180003053`: `CheckGPOs: No GPO changes but couldn't read extension %s's status or policy time.`
- `0x180003569`: `CheckGPOs: No GPO changes but called in force refresh flag or extension %s needs to run force refresh in foreground processing`
- `0x18000359c`: `CheckGPOs: No GPO changes but called in force refresh flag or extension %s needs to run force refresh in foreground processing`
- `0x1800030b1`: `CheckGPOs: No GPO changes but extension %s had returned ERROR_SYNC_FOREGROUND_REFRESH_REQUIRED for previous policy processing call.`
- `0x1800030e4`: `CheckGPOs: No GPO changes but extension %s had returned ERROR_SYNC_FOREGROUND_REFRESH_REQUIRED for previous policy processing call.`
- `0x180003117`: `CheckGPOs: No GPO changes but extension %s had returned ERROR_OVERRIDE_NOCHANGES for previous policy processing call.`
- `0x18000314a`: `CheckGPOs: No GPO changes but extension %s had returned ERROR_OVERRIDE_NOCHANGES for previous policy processing call.`
- `0x1800031cd`: `CheckGPOs: No GPO changes but extension %s's returned error status %d earlier.`
- `0x180003204`: `CheckGPOs: No GPO changes but extension %s's returned error status %d earlier.`
- `0x180003196`: `CheckGPOs: No GPO changes but extension %s's has a link speed transition from %d to %d.`
- `0x18000323e`: `CheckGPOs: No GPO changes but extension %s's has a link speed transition from %d to %d.`
- `0x18000329c`: `CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition from %d to %d.`
- `0x1800032dd`: `CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition from %d to %d.`
- `0x180003329`: `CheckGPOs: No GPO changes but rsop is on and extension <%s> failed to log rsop wih error 0x%x.`
- `0x180003366`: `CheckGPOs: No GPO changes but rsop is on and extension <%s> failed to log rsop wih error 0x%x.`
- `0x1800033ad`: `CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition because name space was created now.`
- `0x1800033e2`: `CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition because name space was created now.`
- `0x1800034a2`: `CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded due to clock overflow.`
- `0x1800034d7`: `CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded due to clock overflow.`
- `0x180003444`: `CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded.`
- `0x180003479`: `CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded.`
- `0x1800034fc`: `CheckGPOs: No GPO changes and no security group membership change and extension %s has NoGPOChanges set.`
- `0x18000352a`: `CheckGPOs: No GPO changes and no security group membership change and extension %s has NoGPOChanges set.`

## pseudocode

```c
__int64 __fastcall CheckGPOs(
        struct _GPEXT *a1,
        struct _GPOINFO *a2,
        unsigned int a3,
        int *a4,
        int *a5,
        struct _GROUP_POLICY_OBJECTW **a6)
{
  struct _GPEXT *v7; // r13
  int v8; // r12d
  BOOL v9; // r14d
  HKEY v10; // r15
  __int64 v11; // rdi
  DWORD LastError; // ebx
  int v13; // eax
  int GPOList; // edi
  __int64 v15; // rbx
  const WCHAR *v16; // rdi
  int v17; // r15d
  __int64 v18; // rbx
  const WCHAR *v19; // rdi
  int v20; // r15d
  struct _GROUP_POLICY_OBJECTW **v21; // rbx
  struct _GROUP_POLICY_OBJECTW **v22; // r12
  __int64 v24; // rdi
  const WCHAR *v25; // rbx
  int v26; // ebx
  int v27; // eax
  int v28; // ebx
  int v29; // r8d
  _DWORD *v30; // rdx
  _QWORD *v31; // rcx
  _QWORD *v32; // rbx
  _QWORD *v33; // rcx
  _QWORD *v34; // rbx
  __int64 v35; // r14
  const WCHAR *v36; // rdi
  __int64 v37; // rdi
  __int64 v38; // r12
  __int64 v39; // r15
  DWORD v40; // ebx
  int v41; // eax
  unsigned int GPOCount; // eax
  void (*v43)(__int64, const unsigned __int16 *, ...); // r10
  unsigned int v44; // eax
  unsigned int v45; // eax
  void (*v46)(__int64, const unsigned __int16 *, ...); // r10
  unsigned int v47; // eax
  __int64 i; // r13
  __int64 j; // r13
  int v50; // r8d
  int v51; // r9d
  int v52; // eax
  int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // eax
  WCHAR *v56; // rdi
  struct _GROUP_POLICY_OBJECTW **v57; // r15
  struct _GROUP_POLICY_OBJECTW *k; // rsi
  __int64 v59; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL v61; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v62; // [rsp+40h] [rbp-C0h]
  struct _GROUP_POLICY_OBJECTW **v63; // [rsp+48h] [rbp-B8h]
  unsigned int v64; // [rsp+50h] [rbp-B0h]
  struct _GPEXT *v65; // [rsp+58h] [rbp-A8h]
  int *v66; // [rsp+60h] [rbp-A0h]
  int *v67; // [rsp+68h] [rbp-98h]
  unsigned __int16 v68[400]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v69[400]; // [rsp+390h] [rbp+290h] BYREF

  v66 = a4;
  v64 = a3;
  v7 = a1;
  v65 = a1;
  v67 = a5;
  v63 = a6;
  hMem = 0;
  v61 = 0;
  v8 = 0;
  v9 = *((_DWORD *)a1 + 24) && (*(_BYTE *)a2 & 1) == 0;
  *a4 = 1;
  *a5 = 0;
  *a6 = 0;
  v10 = (HKEY)*((_QWORD *)a2 + 5);
  v11 = *((_QWORD *)a1 + 1);
  LastError = GetLastError();
  v62 = LastError;
  v13 = StringCchPrintfW(v69, 0x190u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\History\\%ws", v11);
  if ( v13 < 0 )
  {
    v62 = (unsigned __int16)v13;
    SetLastError((unsigned __int16)v13);
    GPOList = 0;
  }
  else
  {
    GPOList = ReadGPOList(v10, v69, (struct _GROUP_POLICY_OBJECTW **)&hMem, 0);
    SetLastError(LastError);
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      GPOCount = GetGPOCount((struct _GROUP_POLICY_OBJECTW *)hMem);
      v43(2, L"CheckGPOs: ReadGPOList count = %d", GPOCount);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v44 = GetGPOCount((struct _GROUP_POLICY_OBJECTW *)hMem);
      RedirectDebugMsg(2u, L"CheckGPOs: ReadGPOList count = %d", v44);
    }
  }
  if ( !GPOList )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CheckGPOs: ReadGPOList failed.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CheckGPOs: ReadGPOList failed.");
      }
    }
    hMem = 0;
  }
  if ( v9 )
  {
    v37 = *((_QWORD *)a2 + 9);
    v38 = *((_QWORD *)a2 + 5);
    v39 = *((_QWORD *)v7 + 1);
    v40 = GetLastError();
    v62 = v40;
    if ( v37 )
      v41 = StringCchPrintfW(
              v68,
              0x190u,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws\\History\\%ws",
              v37,
              v39);
    else
      v41 = StringCchPrintfW(
              v68,
              0x190u,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\History\\%ws",
              v39);
    if ( v41 < 0 )
    {
      SetLastError((unsigned __int16)v41);
      v8 = 0;
    }
    else
    {
      if ( v37 )
        v38 = -2147483646;
      v8 = ReadGPOList((HKEY)v38, v68, (struct _GROUP_POLICY_OBJECTW **)&v61, 0);
      SetLastError(v40);
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        v45 = GetGPOCount((struct _GROUP_POLICY_OBJECTW *)v61);
        v46(2, L"CheckGPOs: ReadGPOList count = %d for user: %ls", v45, *((_QWORD *)a2 + 9));
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v47 = GetGPOCount((struct _GROUP_POLICY_OBJECTW *)v61);
        RedirectDebugMsg(2u, L"CheckGPOs: ReadGPOList count = %d for user: %ls", v47, *((_QWORD *)a2 + 9));
      }
    }
    if ( !v8 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CheckGPOs: ReadGPOList for user local settings failed.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CheckGPOs: ReadGPOList for user local settings failed.");
        }
      }
      v61 = 0;
    }
  }
  v15 = *((_QWORD *)a2 + 8);
  v16 = (const WCHAR *)hMem;
  v17 = 0;
  if ( hMem )
  {
    do
    {
      for ( i = v15; i; i = *(_QWORD *)(i + 144) )
      {
        if ( !lstrcmpiW(v16 + 16, (LPCWSTR)(i + 32)) )
          goto LABEL_96;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CheckForGPOsToRemove: GPO <%s> needs to be removed", *((_QWORD *)v16 + 3));
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CheckForGPOsToRemove: GPO <%s> needs to be removed", *((_QWORD *)v16 + 3));
        }
      }
      *((_QWORD *)v16 + 17) |= 1uLL;
      v17 = 1;
LABEL_96:
      v16 = (const WCHAR *)*((_QWORD *)v16 + 18);
    }
    while ( v16 );
    v7 = v65;
  }
  if ( v9 )
  {
    v18 = *((_QWORD *)a2 + 8);
    v19 = (const WCHAR *)v61;
    v8 = 0;
    if ( v61 )
    {
      do
      {
        for ( j = v18; j; j = *(_QWORD *)(j + 144) )
        {
          if ( !lstrcmpiW(v19 + 16, (LPCWSTR)(j + 32)) )
            goto LABEL_109;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"CheckForGPOsToRemove: GPO <%s> needs to be removed", *((_QWORD *)v19 + 3));
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"CheckForGPOsToRemove: GPO <%s> needs to be removed", *((_QWORD *)v19 + 3));
          }
        }
        *((_QWORD *)v19 + 17) |= 1uLL;
        v8 = 1;
LABEL_109:
        v19 = (const WCHAR *)*((_QWORD *)v19 + 18);
      }
      while ( v19 );
      v7 = v65;
    }
  }
  if ( !v17 )
  {
    if ( !v9 )
    {
      if ( *((_DWORD *)a2 + 32) )
      {
LABEL_14:
        v20 = 1;
        goto LABEL_23;
      }
LABEL_22:
      v20 = 0;
LABEL_23:
      v24 = *((_QWORD *)a2 + 8);
      v25 = (const WCHAR *)hMem;
      if ( hMem )
      {
        if ( v24 )
          goto LABEL_25;
      }
      else if ( !v24 )
      {
        while ( 1 )
        {
LABEL_25:
          if ( !v25 || !v24 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"CompareGPOLists:  The lists are the same.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"CompareGPOLists:  The lists are the same.");
              }
            }
            v26 = 1;
            goto LABEL_28;
          }
          if ( lstrcmpiW(v25 + 16, (LPCWSTR)(v24 + 32)) )
            break;
          if ( *((_DWORD *)v25 + 1) != *(_DWORD *)(v24 + 4) )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_119;
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"CompareGPOLists:  Different version numbers found");
              goto LABEL_119;
            }
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"CompareGPOLists:  Different version numbers found");
              v26 = 0;
              goto LABEL_28;
            }
            goto LABEL_119;
          }
          v25 = (const WCHAR *)*((_QWORD *)v25 + 18);
          v24 = *(_QWORD *)(v24 + 144);
          if ( v25 )
          {
            if ( !v24 )
              goto LABEL_127;
          }
          else if ( v24 )
          {
LABEL_127:
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"CompareGPOLists:  One list has more entries than the other");
                goto LABEL_119;
              }
              if ( g_lpDebugMsgContextInstance && (char *)g_lpDebugMsgContext != (char *)g_lpDebugMsg )
              {
                RedirectDebugMsg(4u, L"CompareGPOLists:  One list has more entries than the other");
                v26 = 0;
                goto LABEL_28;
              }
            }
            goto LABEL_119;
          }
        }
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_119;
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CompareGPOLists:  Different entries found.");
          goto LABEL_119;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CompareGPOLists:  Different entries found.");
          v26 = 0;
          goto LABEL_28;
        }
LABEL_119:
        v26 = 0;
LABEL_28:
        if ( !v9 )
        {
LABEL_29:
          v27 = 1;
LABEL_30:
          if ( !v26 || !v27 || v20 || *((_DWORD *)a2 + 34) )
            goto LABEL_37;
          v28 = 1;
          v29 = *(_DWORD *)a2;
          v30 = (_DWORD *)*((_QWORD *)v7 + 19);
          if ( !v30[5] )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(
                  4u,
                  L"CheckGPOs: No GPO changes but couldn't read extension %s's status or policy time.",
                  *(_QWORD *)v7);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CheckGPOs: No GPO changes but couldn't read extension %s's status or policy time.",
                  *(_QWORD *)v7);
              }
            }
            goto LABEL_36;
          }
          if ( (v29 & 0x100000) != 0 || (v50 = v29 & 0x10000) == 0 && v30[6] )
          {
            v28 = 0;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(
                  4u,
                  L"CheckGPOs: No GPO changes but called in force refresh flag or extension %s needs to run force refresh "
                   "in foreground processing",
                  *(_QWORD *)v7);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CheckGPOs: No GPO changes but called in force refresh flag or extension %s needs to run force refresh "
                   "in foreground processing",
                  *(_QWORD *)v7);
              }
            }
            goto LABEL_36;
          }
          v51 = v30[2];
          switch ( v51 )
          {
            case 1274:
              if ( !v50 )
              {
                v28 = 0;
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(
                      4u,
                      L"CheckGPOs: No GPO changes but extension %s had returned ERROR_SYNC_FOREGROUND_REFRESH_REQUIRED for"
                       " previous policy processing call.",
                      *(_QWORD *)v7);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(
                      4u,
                      L"CheckGPOs: No GPO changes but extension %s had returned ERROR_SYNC_FOREGROUND_REFRESH_REQUIRED for"
                       " previous policy processing call.",
                      *(_QWORD *)v7);
                  }
                }
                goto LABEL_36;
              }
              break;
            case 1252:
              v28 = 0;
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(
                    4u,
                    L"CheckGPOs: No GPO changes but extension %s had returned ERROR_OVERRIDE_NOCHANGES for previous policy"
                     " processing call.",
                    *(_QWORD *)v7);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    4u,
                    L"CheckGPOs: No GPO changes but extension %s had returned ERROR_OVERRIDE_NOCHANGES for previous policy"
                     " processing call.",
                    *(_QWORD *)v7);
                }
              }
              goto LABEL_36;
            case 0:
              if ( !*((_DWORD *)v7 + 27) || *v30 == ((*(_DWORD *)a2 >> 18) & 1) )
              {
                if ( *((_DWORD *)v7 + 18) )
                {
                  v52 = *((_DWORD *)a2 + 54);
                  v53 = v30[1];
                  if ( v53 != v52 )
                  {
                    *((_DWORD *)v7 + 33) = 1;
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        LODWORD(v59) = v52;
                        g_lpDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition from %d to %d.",
                          *(_QWORD *)v7,
                          (unsigned int)v30[1],
                          v59);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        LODWORD(v59) = v52;
                        RedirectDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition from %d to %d.",
                          *(_QWORD *)v7,
                          (unsigned int)v30[1],
                          v59);
                      }
                    }
                    goto LABEL_36;
                  }
                  if ( v53 && (int)v30[3] < 0 )
                  {
                    *((_DWORD *)v7 + 33) = 1;
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but rsop is on and extension <%s> failed to log rsop wih error 0x%x.",
                          *(_QWORD *)v7,
                          (unsigned int)v30[3]);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but rsop is on and extension <%s> failed to log rsop wih error 0x%x.",
                          *(_QWORD *)v7,
                          (unsigned int)v30[3]);
                      }
                    }
                    goto LABEL_36;
                  }
                  if ( v52 && *((_DWORD *)a2 + 55) )
                  {
                    *((_DWORD *)v7 + 33) = 1;
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition because name space "
                           "was created now.",
                          *(_QWORD *)v7);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but extension %s's has a Rsop Logging transition because name space "
                           "was created now.",
                          *(_QWORD *)v7);
                      }
                    }
                    goto LABEL_36;
                  }
                }
                if ( *((_DWORD *)v7 + 23) )
                {
                  v54 = *((_DWORD *)v7 + 28);
                  if ( !v54 )
                    goto LABEL_265;
                  if ( !v64 || (v55 = v30[4]) == 0 || v64 < v55 )
                  {
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded due"
                           " to clock overflow.",
                          *(_QWORD *)v7);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded due"
                           " to clock overflow.",
                          *(_QWORD *)v7);
                      }
                    }
                    goto LABEL_36;
                  }
                  if ( v64 - v55 <= v54 )
                  {
LABEL_265:
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes and no security group membership change and extension %s has NoGPOChanges set.",
                          *(_QWORD *)v7);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(
                          4u,
                          L"CheckGPOs: No GPO changes and no security group membership change and extension %s has NoGPOChanges set.",
                          *(_QWORD *)v7);
                      }
                    }
                    *v66 = 0;
                    goto LABEL_37;
                  }
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(
                        4u,
                        L"CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded.",
                        *(_QWORD *)v7);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(
                        4u,
                        L"CheckGPOs: No GPO changes but extension %s's MaxNoGPOListChangesInterval has been exceeded.",
                        *(_QWORD *)v7);
                    }
                  }
                }
              }
              else if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(
                    4u,
                    L"CheckGPOs: No GPO changes but extension %s's has a link speed transition from %d to %d.",
                    *(_QWORD *)v7);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    4u,
                    L"CheckGPOs: No GPO changes but extension %s's has a link speed transition from %d to %d.",
                    *(_QWORD *)v7);
                }
              }
LABEL_36:
              *v67 = v28;
LABEL_37:
              v31 = hMem;
              if ( hMem )
              {
                do
                {
                  v32 = (_QWORD *)v31[18];
                  LocalFree(v31);
                  v31 = v32;
                }
                while ( v32 );
              }
              v33 = v61;
              if ( v61 )
              {
                do
                {
                  v34 = (_QWORD *)v33[18];
                  LocalFree(v33);
                  v33 = v34;
                }
                while ( v34 );
              }
              return 1;
          }
          v28 = 0;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                4u,
                L"CheckGPOs: No GPO changes but extension %s's returned error status %d earlier.",
                *(_QWORD *)v7);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"CheckGPOs: No GPO changes but extension %s's returned error status %d earlier.",
                *(_QWORD *)v7);
            }
          }
          goto LABEL_36;
        }
        v35 = *((_QWORD *)a2 + 8);
        v36 = (const WCHAR *)v61;
        if ( v61 )
        {
          if ( v35 )
            goto LABEL_44;
        }
        else if ( !v35 )
        {
          while ( 1 )
          {
LABEL_44:
            if ( !v36 || !v35 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"CompareGPOLists:  The lists are the same.");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"CompareGPOLists:  The lists are the same.");
                }
              }
              goto LABEL_29;
            }
            if ( lstrcmpiW(v36 + 16, (LPCWSTR)(v35 + 32)) )
              break;
            if ( *((_DWORD *)v36 + 1) != *(_DWORD *)(v35 + 4) )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_157;
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"CompareGPOLists:  Different version numbers found");
                goto LABEL_157;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"CompareGPOLists:  Different version numbers found");
                v27 = 0;
                goto LABEL_30;
              }
              goto LABEL_157;
            }
            v36 = (const WCHAR *)*((_QWORD *)v36 + 18);
            v35 = *(_QWORD *)(v35 + 144);
            if ( v36 )
            {
              if ( !v35 )
                goto LABEL_165;
            }
            else if ( v35 )
            {
LABEL_165:
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"CompareGPOLists:  One list has more entries than the other");
                  goto LABEL_157;
                }
                if ( g_lpDebugMsgContextInstance && (char *)g_lpDebugMsgContext != (char *)g_lpDebugMsg )
                {
                  RedirectDebugMsg(4u, L"CompareGPOLists:  One list has more entries than the other");
                  v27 = 0;
                  goto LABEL_30;
                }
              }
              goto LABEL_157;
            }
          }
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_157;
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"CompareGPOLists:  Different entries found.");
            goto LABEL_157;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"CompareGPOLists:  Different entries found.");
            v27 = 0;
            goto LABEL_30;
          }
          goto LABEL_157;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"CompareGPOLists:  One list is empty");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"CompareGPOLists:  One list is empty");
          }
        }
LABEL_157:
        v27 = 0;
        goto LABEL_30;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CompareGPOLists:  One list is empty");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CompareGPOLists:  One list is empty");
        }
      }
      goto LABEL_119;
    }
    if ( !v8 )
    {
      if ( *((_DWORD *)a2 + 33) )
        goto LABEL_14;
      goto LABEL_22;
    }
  }
  v21 = (struct _GROUP_POLICY_OBJECTW **)hMem;
  if ( hMem )
  {
    v22 = v63;
    do
    {
      v56 = (WCHAR *)v21;
      v57 = v21 + 18;
      v21 = (struct _GROUP_POLICY_OBJECTW **)v21[18];
      if ( (v56[68] & 1) != 0 )
      {
        for ( k = *v22; k; k = k->pNext )
        {
          if ( !lstrcmpiW(v56 + 16, k->szGPOName) )
            goto LABEL_292;
        }
        *v57 = *v22;
        *((_QWORD *)v56 + 19) = 0;
        if ( *v22 )
          (*v22)->pPrev = (struct _GROUP_POLICY_OBJECTW *)v56;
        *v22 = (struct _GROUP_POLICY_OBJECTW *)v56;
      }
      else
      {
LABEL_292:
        LocalFree(v56);
      }
    }
    while ( v21 );
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetDeletedGPOList: Finished.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetDeletedGPOList: Finished.");
      }
    }
  }
  else
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetDeletedList: No old GPOs.  Leaving.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetDeletedList: No old GPOs.  Leaving.");
      }
    }
    v22 = v63;
  }
  if ( v9 && !(unsigned int)GetDeletedGPOList(v61, v22) && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CheckGPOs: GetDeletedList failed for %s.", *(_QWORD *)v7);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"CheckGPOs: GetDeletedList failed for %s.", *(_QWORD *)v7);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002530  mov     [rsp-8+arg_10], rbx
0x180002535  push    rbp
0x180002536  push    rsi
0x180002537  push    rdi
0x180002538  push    r12
0x18000253a  push    r13
0x18000253c  push    r14
0x18000253e  push    r15
0x180002540  lea     rbp, [rsp-5C0h]
0x180002548  sub     rsp, 6C0h
0x18000254f  mov     rax, cs:__security_cookie
0x180002556  xor     rax, rsp
0x180002559  mov     [rbp+5F0h+var_40], rax
0x180002560  mov     [rsp+6F0h+var_690], r9
0x180002565  mov     [rsp+6F0h+var_6A0], r8d
0x18000256a  mov     rsi, rdx
0x18000256d  mov     r13, rcx
0x180002570  mov     [rsp+6F0h+var_698], rcx
0x180002575  mov     rcx, [rbp+5F0h+arg_20]
0x18000257c  mov     [rsp+6F0h+var_688], rcx
0x180002581  mov     rax, [rbp+5F0h+arg_28]
0x180002588  mov     [rsp+6F0h+var_6A8], rax
0x18000258d  xor     edx, edx
0x18000258f  mov     [rsp+6F0h+hMem], rdx
0x180002594  mov     [rsp+6F0h+var_6B8], rdx
0x180002599  mov     r12d, edx
0x18000259c  cmp     [r13+60h], edx
0x1800025a0  jnz     loc_180002911
0x1800025a6  mov     r14d, edx
0x1800025a9  mov     dword ptr [r9], 1
0x1800025b0  mov     [rcx], edx
0x1800025b2  mov     [rax], rdx
0x1800025b5  mov     r15, [rsi+28h]
0x1800025b9  mov     rdi, [r13+8]
0x1800025bd  call    cs:__imp_GetLastError
0x1800025c3  mov     ebx, eax
0x1800025c5  mov     [rsp+6F0h+var_6B0], eax
0x1800025c9  mov     r9, rdi
0x1800025cc  lea     r8, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800025d3  mov     edx, 190h; unsigned __int64
0x1800025d8  lea     rcx, [rbp+5F0h+var_360]; unsigned __int16 *
0x1800025df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800025e4  test    eax, eax
0x1800025e6  js      loc_1800028EC
0x1800025ec  xor     r9d, r9d; struct _GPOINFO *
0x1800025ef  lea     r8, [rsp+6F0h+hMem]; struct _GROUP_POLICY_OBJECTW **
0x1800025f4  lea     rdx, [rbp+5F0h+var_360]; unsigned __int16 *
0x1800025fb  mov     rcx, r15; HKEY
0x1800025fe  call    ?ReadGPOList@@YAHPEAUHKEY__@@PEAGPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(HKEY__ *,ushort *,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x180002603  mov     edi, eax
0x180002605  mov     ecx, ebx; dwErrCode
0x180002607  call    cs:__imp_SetLastError
0x18000260d  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180002614  jnz     loc_180002925
0x18000261a  test    edi, edi
0x18000261c  jz      loc_180002996
0x180002622  test    r14d, r14d
0x180002625  jnz     loc_180002817
0x18000262b  mov     rbx, [rsi+40h]
0x18000262f  mov     rdi, [rsp+6F0h+hMem]
0x180002634  xor     r15d, r15d
0x180002637  test    rdi, rdi
0x18000263a  jnz     loc_180002AA0
0x180002640  test    r14d, r14d
0x180002643  jz      short loc_18000265A
0x180002645  mov     rbx, [rsi+40h]
0x180002649  mov     rdi, [rsp+6F0h+var_6B8]
0x18000264e  xor     r12d, r12d
0x180002651  test    rdi, rdi
0x180002654  jnz     loc_180002B43
0x18000265a  test    r15d, r15d
0x18000265d  jnz     short loc_180002675
0x18000265f  test    r14d, r14d
0x180002662  jnz     short loc_1800026CC
0x180002664  cmp     [rsi+80h], r14d
0x18000266b  jz      short loc_1800026DA
0x18000266d  mov     r15d, 1
0x180002673  jmp     short loc_1800026DD
0x180002675  mov     rbx, [rsp+6F0h+hMem]
0x18000267a  test    rbx, rbx
0x18000267d  jnz     loc_18000360D
0x180002683  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180002689  jnz     loc_1800035B6
0x18000268f  mov     r12, [rsp+6F0h+var_6A8]
0x180002694  test    r14d, r14d
0x180002697  jnz     loc_1800036E2
0x18000269d  mov     eax, 1
0x1800026a2  mov     rcx, [rbp+5F0h+var_40]
0x1800026a9  xor     rcx, rsp; StackCookie
0x1800026ac  call    __security_check_cookie
0x1800026b1  mov     rbx, [rsp+6F0h+arg_10]
0x1800026b9  add     rsp, 6C0h
0x1800026c0  pop     r15
0x1800026c2  pop     r14
0x1800026c4  pop     r13
0x1800026c6  pop     r12
0x1800026c8  pop     rdi
0x1800026c9  pop     rsi
0x1800026ca  pop     rbp
0x1800026cb  retn
0x1800026cc  test    r12d, r12d
0x1800026cf  jnz     short loc_180002675
0x1800026d1  cmp     [rsi+84h], r12d
0x1800026d8  jnz     short loc_18000266D
0x1800026da  xor     r15d, r15d
0x1800026dd  mov     rdi, [rsi+40h]
0x1800026e1  mov     rbx, [rsp+6F0h+hMem]
0x1800026e6  test    rbx, rbx
0x1800026e9  jnz     loc_180002BE6
0x1800026ef  test    rdi, rdi
0x1800026f2  jnz     loc_180002BEF
0x1800026f8  test    rbx, rbx
0x1800026fb  jnz     loc_180002C5C
0x180002701  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180002708  jnz     loc_180002DB5
0x18000270e  mov     ebx, 1
0x180002713  test    r14d, r14d
0x180002716  jnz     loc_1800027BD
0x18000271c  mov     eax, 1
0x180002721  test    ebx, ebx
0x180002723  jz      short loc_18000276C
0x180002725  test    eax, eax
0x180002727  jz      short loc_18000276C
0x180002729  test    r15d, r15d
0x18000272c  jnz     short loc_18000276C
0x18000272e  cmp     [rsi+88h], r15d
0x180002735  jnz     short loc_18000276C
0x180002737  mov     ebx, 1
0x18000273c  mov     r8d, [rsi]
0x18000273f  mov     eax, r8d
0x180002742  shr     eax, 12h
0x180002745  and     eax, ebx
0x180002747  mov     rdx, [r13+98h]
0x18000274e  cmp     [rdx+14h], r15d
0x180002752  jnz     loc_18000305F
0x180002758  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18000275f  jnz     loc_18000300E
0x180002765  mov     rax, [rsp+6F0h+var_688]
0x18000276a  mov     [rax], ebx
0x18000276c  mov     rcx, [rsp+6F0h+hMem]; hMem
0x180002771  test    rcx, rcx
0x180002774  jz      short loc_180002795
0x180002776  nop     word ptr [rax+rax+00000000h]
0x180002780  mov     rbx, [rcx+90h]
0x180002787  call    cs:__imp_LocalFree
0x18000278d  mov     rcx, rbx
0x180002790  test    rbx, rbx
0x180002793  jnz     short loc_180002780
0x180002795  mov     rcx, [rsp+6F0h+var_6B8]; hMem
0x18000279a  test    rcx, rcx
0x18000279d  jz      loc_18000269D
0x1800027a3  mov     rbx, [rcx+90h]
0x1800027aa  call    cs:__imp_LocalFree
0x1800027b0  mov     rcx, rbx
0x1800027b3  test    rbx, rbx
0x1800027b6  jnz     short loc_1800027A3
0x1800027b8  jmp     loc_18000269D
0x1800027bd  mov     r14, [rsi+40h]
0x1800027c1  mov     rdi, [rsp+6F0h+var_6B8]
0x1800027c6  test    rdi, rdi
0x1800027c9  jnz     loc_180002E0C
0x1800027cf  test    r14, r14
0x1800027d2  jnz     loc_180002E15
0x1800027d8  test    rdi, rdi
0x1800027db  jnz     loc_180002E82
0x1800027e1  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800027e8  jz      loc_18000271C
0x1800027ee  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800027f5  test    r10, r10
0x1800027f8  jz      loc_180002FDC
0x1800027fe  lea     rdx, aComparegpolist_2; "CompareGPOLists:  The lists are the sam"...
0x180002805  mov     ecx, 4
0x18000280a  mov     rax, r10
0x18000280d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002812  jmp     loc_18000271C
0x180002817  mov     rdi, [rsi+48h]
0x18000281b  mov     r12, [rsi+28h]
0x18000281f  mov     r15, [r13+8]
0x180002823  call    cs:__imp_GetLastError
0x180002829  mov     ebx, eax
0x18000282b  mov     [rsp+6F0h+var_6B0], eax
0x18000282f  mov     edx, 190h; unsigned __int64
0x180002834  lea     rcx, [rsp+6F0h+var_680]; unsigned __int16 *
0x180002839  test    rdi, rdi
0x18000283c  jnz     loc_1800028D3
0x180002842  mov     r9, r15
0x180002845  lea     r8, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000284c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002851  test    eax, eax
0x180002853  js      loc_180002900
0x180002859  mov     rax, 0FFFFFFFF80000002h
0x180002860  test    rdi, rdi
0x180002863  cmovnz  r12, rax
0x180002867  xor     r9d, r9d; struct _GPOINFO *
0x18000286a  lea     r8, [rsp+6F0h+var_6B8]; struct _GROUP_POLICY_OBJECTW **
0x18000286f  lea     rdx, [rsp+6F0h+var_680]; unsigned __int16 *
0x180002874  mov     rcx, r12; HKEY
0x180002877  call    ?ReadGPOList@@YAHPEAUHKEY__@@PEAGPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(HKEY__ *,ushort *,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x18000287c  mov     r12d, eax
0x18000287f  mov     ecx, ebx; dwErrCode
0x180002881  call    cs:__imp_SetLastError
0x180002887  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000288e  jnz     loc_1800029F4
0x180002894  test    r12d, r12d
0x180002897  jnz     loc_18000262B
0x18000289d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800028a4  jz      loc_180002A92
0x1800028aa  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800028b1  test    r10, r10
0x1800028b4  jz      loc_180002A6D
0x1800028ba  lea     rdx, aCheckgposReadg_0; "CheckGPOs: ReadGPOList for user local s"...
0x1800028c1  mov     ecx, 2
0x1800028c6  mov     rax, r10
0x1800028c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ce  jmp     loc_180002A92
0x1800028d3  mov     [rsp+6F0h+var_6D0], r15
0x1800028d8  mov     r9, rdi
0x1800028db  lea     r8, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800028e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800028e7  jmp     loc_180002851
0x1800028ec  movzx   ecx, ax; dwErrCode
0x1800028ef  mov     [rsp+6F0h+var_6B0], ecx
0x1800028f3  call    cs:__imp_SetLastError
0x1800028f9  xor     edi, edi
0x1800028fb  jmp     loc_18000260D
0x180002900  movzx   ecx, ax; dwErrCode
0x180002903  call    cs:__imp_SetLastError
0x180002909  xor     r12d, r12d
0x18000290c  jmp     loc_180002887
0x180002911  test    byte ptr [rsi], 1
0x180002914  jnz     loc_1800025A6
0x18000291a  mov     r14d, 1
0x180002920  jmp     loc_1800025A9
0x180002925  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000292c  test    r10, r10
0x18000292f  jz      short loc_180002957
0x180002931  mov     rcx, [rsp+6F0h+hMem]; struct _GROUP_POLICY_OBJECTW *
0x180002936  call    ?GetGPOCount@@YAKPEAU_GROUP_POLICY_OBJECTW@@@Z; GetGPOCount(_GROUP_POLICY_OBJECTW *)
0x18000293b  mov     r8d, eax
0x18000293e  lea     rdx, aCheckgposReadg_2; "CheckGPOs: ReadGPOList count = %d"
0x180002945  mov     ecx, 2
0x18000294a  mov     rax, r10
0x18000294d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002952  jmp     loc_18000261A
0x180002957  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000295f  jz      loc_18000261A
0x180002965  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000296d  jz      loc_18000261A
0x180002973  mov     rcx, [rsp+6F0h+hMem]; struct _GROUP_POLICY_OBJECTW *
0x180002978  call    ?GetGPOCount@@YAKPEAU_GROUP_POLICY_OBJECTW@@@Z; GetGPOCount(_GROUP_POLICY_OBJECTW *)
0x18000297d  mov     r8d, eax
0x180002980  lea     rdx, aCheckgposReadg_2; "CheckGPOs: ReadGPOList count = %d"
0x180002987  mov     ecx, 2; unsigned int
0x18000298c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180002991  jmp     loc_18000261A
0x180002996  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000299d  jz      short loc_1800029E6
0x18000299f  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800029a6  test    r10, r10
0x1800029a9  jz      short loc_1800029C1
0x1800029ab  lea     rdx, aCheckgposReadg_1; "CheckGPOs: ReadGPOList failed."
0x1800029b2  mov     ecx, 2
0x1800029b7  mov     rax, r10
0x1800029ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029bf  jmp     short loc_1800029E6
0x1800029c1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800029c9  jz      short loc_1800029E6
0x1800029cb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800029d3  jz      short loc_1800029E6
0x1800029d5  lea     rdx, aCheckgposReadg_1; "CheckGPOs: ReadGPOList failed."
0x1800029dc  mov     ecx, 2; unsigned int
0x1800029e1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800029e6  mov     [rsp+6F0h+hMem], 0
0x1800029ef  jmp     loc_180002622
0x1800029f4  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800029fb  test    r10, r10
0x1800029fe  jz      short loc_180002A2A
0x180002a00  mov     rcx, [rsp+6F0h+var_6B8]; struct _GROUP_POLICY_OBJECTW *
0x180002a05  call    ?GetGPOCount@@YAKPEAU_GROUP_POLICY_OBJECTW@@@Z; GetGPOCount(_GROUP_POLICY_OBJECTW *)
0x180002a0a  mov     r9, [rsi+48h]
0x180002a0e  mov     r8d, eax
0x180002a11  lea     rdx, aCheckgposReadg; "CheckGPOs: ReadGPOList count = %d for u"...
0x180002a18  mov     ecx, 2
0x180002a1d  mov     rax, r10
0x180002a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a25  jmp     loc_180002894
0x180002a2a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180002a32  jz      loc_180002894
0x180002a38  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180002a40  jz      loc_180002894
0x180002a46  mov     rcx, [rsp+6F0h+var_6B8]; struct _GROUP_POLICY_OBJECTW *
0x180002a4b  call    ?GetGPOCount@@YAKPEAU_GROUP_POLICY_OBJECTW@@@Z; GetGPOCount(_GROUP_POLICY_OBJECTW *)
0x180002a50  mov     r9, [rsi+48h]
0x180002a54  mov     r8d, eax
0x180002a57  lea     rdx, aCheckgposReadg; "CheckGPOs: ReadGPOList count = %d for u"...
0x180002a5e  mov     ecx, 2; unsigned int
0x180002a63  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180002a68  jmp     loc_180002894
0x180002a6d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180002a75  jz      short loc_180002A92
  ... truncated ...
```
