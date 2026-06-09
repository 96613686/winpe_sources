# CDplUser::EnumRefEnterpriseCredentials(ushort const *,ushort const *,ushort *,ulong,uchar const *,ulong,CDplAccount * * *,CDplKeyPair * * *,int * *,unsigned __int64 *)

- ea: `0x1800af128`
- end: `0x1800afdcf`
- name: `?EnumRefEnterpriseCredentials@CDplUser@@AEAAJPEBG0PEAGKPEBEKPEAPEAPEAVCDplAccount@@PEAPEAPEAVCDplKeyPair@@PEAPEAHPEA_K@Z`
- size: `3239`
- prototype: `int(CDplUser *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, const unsigned __int8 *, unsigned int, struct CDplAccount ***, struct CDplKeyPair ***, int **, unsigned __int64 *)`
- caller_count: `18`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18008a018`
- `0x18008a6b0`
- `0x18008b678`
- `0x18008c200`
- `0x18008d804`
- `0x18008e3a4`
- `0x180090228`
- `0x18009153c`
- `0x1800ad698`
- `0x1800ae330`
- `0x1800ae9f4`
- `0x1800b0088`
- `0x1800b2174`
- `0x1800b2918`
- `0x1800b6834`
- `0x1800b7880`
- `0x1800bab94`
- `0x1800bd4b8`

## callees

- `0x180005045`
- `0x18000efb8`
- `0x1800124a8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180088190`
- `0x1800a1c38`
- `0x1800af128`
- `0x1800b3e5c`
- `0x1800b5a5c`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afa1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afa62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afa1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afa62`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af54e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af630`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af54e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800af630`
- `RPCRT4!UuidFromStringW` at `0x1800af344`
- `RPCRT4!UuidFromStringW` at `0x1800af344`

## pseudocode

```c
__int64 __fastcall CDplUser::EnumRefEnterpriseCredentials(
        CDplUser *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        struct CDplAccount ***a8,
        struct CDplKeyPair ***a9,
        int **a10,
        unsigned __int64 *a11)
{
  unsigned __int16 *v11; // rbx
  _QWORD *v12; // r12
  struct CDplAccount **v13; // r13
  struct CDplKeyPair **v14; // r15
  unsigned __int64 v15; // r14
  int v16; // ecx
  signed int DplAccountsAndPolicies; // edi
  RPC_STATUS v18; // ebx
  int v19; // ecx
  CDplUser *v20; // rsi
  int v21; // ecx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rsi
  _QWORD *v25; // rbx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rax
  bool v29; // zf
  unsigned __int64 v30; // rdx
  int v31; // ecx
  size_t v32; // rbx
  int v33; // eax
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // eax
  int v38; // ecx
  int v39; // ecx
  int v40; // eax
  signed int LastError; // eax
  signed int v42; // eax
  struct CDplKeyPair *v43; // rsi
  unsigned __int64 v44; // r8
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // r9
  unsigned __int64 v47; // rcx
  unsigned __int64 v48; // rax
  unsigned __int64 v49; // r15
  __int64 v50; // rcx
  unsigned __int64 v51; // rdi
  __int64 v52; // r9
  struct CDplKeyPair *v53; // rbx
  __int64 v54; // r8
  __int64 v55; // rcx
  struct CDplKeyPair *v56; // rdx
  __int64 v57; // rax
  struct CDplKeyPair ***v58; // r12
  unsigned __int64 v59; // rsi
  struct CDplAccount ***v60; // rdi
  __int64 v61; // rbx
  struct CDplAccount ***v62; // rax
  signed int v64; // [rsp+40h] [rbp-C0h]
  char *v65; // [rsp+48h] [rbp-B8h]
  int v66; // [rsp+50h] [rbp-B0h]
  size_t Size; // [rsp+58h] [rbp-A8h] BYREF
  void *v68; // [rsp+60h] [rbp-A0h]
  int v69; // [rsp+68h] [rbp-98h]
  unsigned __int64 v70; // [rsp+70h] [rbp-90h]
  struct CDplKeyPair **v71; // [rsp+78h] [rbp-88h]
  void *v72; // [rsp+80h] [rbp-80h] BYREF
  LPCWCH lpString1; // [rsp+88h] [rbp-78h]
  LPCWCH v74; // [rsp+90h] [rbp-70h]
  void *v75; // [rsp+98h] [rbp-68h] BYREF
  void *v76; // [rsp+A0h] [rbp-60h] BYREF
  void *v77; // [rsp+A8h] [rbp-58h] BYREF
  struct CDplAccount ***v78; // [rsp+B0h] [rbp-50h]
  struct CDplKeyPair ***v79; // [rsp+B8h] [rbp-48h]
  CDplUser *v80; // [rsp+C0h] [rbp-40h]
  int cchCount2[2]; // [rsp+C8h] [rbp-38h] BYREF
  int cchCount1[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v83; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v84; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v85; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v86; // [rsp+F0h] [rbp-10h]
  int **v87; // [rsp+F8h] [rbp-8h]
  unsigned __int64 *v88; // [rsp+100h] [rbp+0h]
  _QWORD *i; // [rsp+108h] [rbp+8h]
  UUID Uuid; // [rsp+110h] [rbp+10h] BYREF

  v11 = a4;
  v78 = a8;
  v79 = a9;
  v88 = a11;
  v80 = this;
  v12 = 0;
  v13 = 0;
  v74 = a3;
  v14 = 0;
  lpString1 = a2;
  v85 = a4;
  v87 = a10;
  v64 = 0;
  v15 = 0;
  v69 = 0;
  *(_QWORD *)cchCount1 = 0;
  v84 = 0;
  Uuid = 0;
  v72 = 0;
  v65 = 0;
  v77 = 0;
  v71 = 0;
  v76 = 0;
  v68 = 0;
  v75 = 0;
  v70 = 0;
  Size = 0;
  fnEfsLogTrace1Strings((_DWORD)a10, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 45);
  if ( a8 )
  {
    v16 = 0;
    *v78 = 0;
  }
  if ( v79 )
  {
    v16 = 0;
    *v79 = 0;
  }
  if ( v87 )
  {
    v16 = 0;
    *v87 = 0;
  }
  if ( v88 )
  {
    v16 = 0;
    *v88 = 0;
  }
  if ( lpString1 )
  {
    fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 64);
    DplAccountsAndPolicies = StringCchLengthW(lpString1, 0x7FFFFFFFu, (unsigned __int64 *)cchCount1);
    v64 = DplAccountsAndPolicies;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                DplAccountsAndPolicies,
                40,
                64) < 0 )
      goto LABEL_115;
  }
  if ( (unsigned __int64)v74 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 69);
    DplAccountsAndPolicies = StringCchLengthW(v74, 0x7FFFFFFFu, &v84);
    v64 = DplAccountsAndPolicies;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                DplAccountsAndPolicies,
                40,
                69) < 0 )
      goto LABEL_115;
  }
  if ( v11 )
  {
    v18 = UuidFromStringW(v11, &Uuid);
    fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 76);
    DplAccountsAndPolicies = 0;
    if ( v18 )
      DplAccountsAndPolicies = v18 | 0x80010000;
    v64 = DplAccountsAndPolicies;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                DplAccountsAndPolicies,
                40,
                76) < 0 )
      goto LABEL_115;
    v11 = v85;
  }
  v20 = v80;
  v69 = CDplUser::UserSvcLock(v80);
  if ( *((_DWORD *)v80 + 59) && *((_DWORD *)v80 + 58) && !CDplUser::HasAccountDecryptionFailed(v80, v11)
    || (fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 87),
        DplAccountsAndPolicies = CDplUser::LoadDplAccountsAndPolicies(v80, v11),
        v64 = DplAccountsAndPolicies,
        (int)fnEfsLogTrace1String1Dword(
               g_hPublisher,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
               (unsigned int)&sourceString,
               DplAccountsAndPolicies,
               40,
               87) >= 0) )
  {
    v86 = 0;
    v22 = 0;
LABEL_23:
    v66 = v22;
    if ( (unsigned int)v22 < 2 )
    {
      v23 = (_QWORD *)((char *)v20 + 200);
      v24 = (_QWORD *)*((_QWORD *)v20 + 25);
      for ( i = v23; ; v23 = i )
      {
        if ( v24 == v23 )
        {
          if ( (_DWORD)v22 )
            goto LABEL_68;
          if ( !v13 )
          {
            DplAccountsAndPolicies = a6 != 0 ? -2147024894 : 1;
            v64 = DplAccountsAndPolicies;
            fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_MSG_TRACE_EVENT,
              (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
              (unsigned int)L"EDP credential was not found",
              DplAccountsAndPolicies,
              40,
              92);
            goto LABEL_114;
          }
          fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 103);
          DplAccountsAndPolicies = ULongLongMult((unsigned __int64)v13, 8u, &Size);
          v64 = DplAccountsAndPolicies;
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      DplAccountsAndPolicies,
                      40,
                      103) < 0
            || (fnEfsLogTrace1Strings(v31, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 108),
                v32 = Size,
                DplAccountsAndPolicies = DplibpMemAllocEx(Size, 0, 0, &v72),
                v64 = DplAccountsAndPolicies,
                v33 = fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        DplAccountsAndPolicies,
                        40,
                        108),
                v12 = v72,
                v33 < 0) )
          {
LABEL_114:
            v13 = (struct CDplAccount **)v65;
          }
          else
          {
            memset_0(v72, 0, v32);
            fnEfsLogTrace1Strings(v34, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 115);
            DplAccountsAndPolicies = DplibpMemAllocEx(v32, 0, 0, &v77);
            v64 = DplAccountsAndPolicies;
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        DplAccountsAndPolicies,
                        40,
                        115) >= 0 )
            {
              v65 = (char *)v77;
              memset_0(v77, 0, v32);
              fnEfsLogTrace1Strings(v35, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 121);
              DplAccountsAndPolicies = ULongLongMult((unsigned __int64)v13, 8u, &Size);
              v64 = DplAccountsAndPolicies;
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          DplAccountsAndPolicies,
                          40,
                          121) < 0 )
                goto LABEL_114;
              fnEfsLogTrace1Strings(v36, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 126);
              DplAccountsAndPolicies = DplibpMemAllocEx(Size, 0, 0, &v76);
              v64 = DplAccountsAndPolicies;
              v37 = fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      DplAccountsAndPolicies,
                      40,
                      126);
              v14 = (struct CDplKeyPair **)v76;
              if ( v37 < 0 )
                goto LABEL_114;
              v71 = (struct CDplKeyPair **)v76;
              memset_0(v76, 0, Size);
              fnEfsLogTrace1Strings(v38, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 132);
              DplAccountsAndPolicies = ULongLongMult((unsigned __int64)v13, 4u, &Size);
              v64 = DplAccountsAndPolicies;
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          DplAccountsAndPolicies,
                          40,
                          132) < 0 )
                goto LABEL_114;
              fnEfsLogTrace1Strings(v39, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 137);
              DplAccountsAndPolicies = DplibpMemAllocEx(Size, 0, 0, &v75);
              v64 = DplAccountsAndPolicies;
              v40 = fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      DplAccountsAndPolicies,
                      40,
                      137);
              v68 = v75;
              if ( v40 < 0 )
                goto LABEL_114;
              memset_0(v75, 0, Size);
              LODWORD(v22) = v66;
LABEL_68:
              v20 = v80;
              v22 = (unsigned int)(v22 + 1);
              goto LABEL_23;
            }
            v13 = (struct CDplAccount **)v77;
            v65 = (char *)v77;
          }
          goto LABEL_115;
        }
        v25 = v24 - 11;
        *(_QWORD *)cchCount2 = 0;
        v83 = 0;
        if ( !*((_DWORD *)v24 + 14) )
          break;
LABEL_57:
        v24 = (_QWORD *)*v24;
      }
      if ( lpString1 )
      {
        if ( !v25[8] )
          goto LABEL_57;
        fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 140);
        DplAccountsAndPolicies = StringCchLengthW(
                                   (const unsigned __int16 *)v25[8],
                                   0x7FFFFFFFu,
                                   (unsigned __int64 *)cchCount2);
        v64 = DplAccountsAndPolicies;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    DplAccountsAndPolicies,
                    40,
                    140) < 0 )
          goto LABEL_114;
        if ( *(_QWORD *)cchCount1 != *(_QWORD *)cchCount2 )
          goto LABEL_56;
        v26 = CompareStringOrdinal(lpString1, cchCount1[0], (LPCWCH)v25[8], cchCount2[0], 1);
        if ( !v26 )
        {
          LastError = GetLastError();
          v64 = LastError;
          DplAccountsAndPolicies = LastError;
          if ( LastError > 0 )
          {
            DplAccountsAndPolicies = (unsigned __int16)LastError | 0x80070000;
            v64 = DplAccountsAndPolicies;
          }
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, DplAccountsAndPolicies, 40, 167);
          goto LABEL_114;
        }
        if ( v26 != 2 )
          goto LABEL_56;
        LODWORD(v22) = v66;
      }
      if ( v74 )
      {
        if ( v74 != (LPCWCH)-1LL )
        {
          if ( !v25[10] )
            goto LABEL_57;
          fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 216);
          DplAccountsAndPolicies = StringCchLengthW((const unsigned __int16 *)v25[10], 0x7FFFFFFFu, &v83);
          v64 = DplAccountsAndPolicies;
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      DplAccountsAndPolicies,
                      40,
                      216) < 0 )
            goto LABEL_114;
          if ( v84 != v83 )
            goto LABEL_56;
          v27 = CompareStringOrdinal(v74, v84, (LPCWCH)v25[10], v83, 1);
          if ( !v27 )
          {
            v42 = GetLastError();
            v64 = v42;
            DplAccountsAndPolicies = v42;
            if ( v42 > 0 )
            {
              DplAccountsAndPolicies = (unsigned __int16)v42 | 0x80070000;
              v64 = DplAccountsAndPolicies;
            }
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, DplAccountsAndPolicies, 40, 243);
            goto LABEL_114;
          }
          if ( v27 != 2 )
          {
LABEL_56:
            LODWORD(v22) = v66;
            goto LABEL_57;
          }
        }
      }
      else if ( v25[10] )
      {
        goto LABEL_57;
      }
      if ( v85 )
      {
        v28 = *(_QWORD *)&Uuid.Data1 - v25[3];
        if ( *(_QWORD *)&Uuid.Data1 == v25[3] )
          v28 = *(_QWORD *)Uuid.Data4 - v25[4];
        if ( v28 )
          goto LABEL_56;
      }
      if ( a5 == -1 )
      {
        v29 = *((_DWORD *)v25 + 51) == 0;
      }
      else
      {
        if ( !a5 )
        {
LABEL_52:
          LODWORD(v22) = v66;
          if ( v66 )
          {
            v30 = v86;
            if ( v86 >= (unsigned __int64)v13 )
            {
              DplAccountsAndPolicies = -2147418113;
              fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 40, 60);
              goto LABEL_131;
            }
            v12[v86] = v25;
            v86 = v30 + 1;
          }
          else
          {
            v13 = (struct CDplAccount **)((char *)v13 + 1);
          }
          goto LABEL_57;
        }
        v29 = a5 == *((_DWORD *)v25 + 52);
      }
      if ( !v29 )
        goto LABEL_56;
      goto LABEL_52;
    }
    v43 = 0;
    if ( !v13 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v22);
    if ( a6 || (unsigned __int64)v13 <= 1 )
      goto LABEL_91;
    v44 = 1;
    v45 = 0;
    v46 = *(_QWORD *)(*v12 + 8LL);
    do
    {
      v47 = *(_QWORD *)(v12[v44] + 8LL);
      v48 = v44;
      if ( v46 >= v47 )
        v48 = v45;
      ++v44;
      v45 = v48;
      if ( v46 >= v47 )
        v47 = v46;
      v46 = v47;
    }
    while ( v44 < (unsigned __int64)v13 );
    if ( !v48 )
    {
LABEL_91:
      v49 = 0;
      if ( !v13 )
        goto LABEL_112;
    }
    else
    {
      v49 = 0;
      v50 = *v12;
      *v12 = v12[v48];
      v12[v48] = v50;
    }
    v51 = 0;
    do
    {
      v52 = v12[v49];
      v53 = 0;
      v54 = v52 + 104;
      v55 = *(_QWORD *)(v52 + 112);
      while ( v55 != v54 )
      {
        v43 = (struct CDplKeyPair *)(v55 - 80);
        v56 = (struct CDplKeyPair *)(v55 - 80);
        if ( v53 )
          v56 = v53;
        v53 = v56;
        if ( !a6 )
          goto LABEL_105;
        if ( a7 == 24 )
        {
          v57 = *(_QWORD *)a6 - *((_QWORD *)v43 + 5);
          if ( *(_QWORD *)a6 == *((_QWORD *)v43 + 5) )
          {
            v57 = *((_QWORD *)a6 + 1) - *((_QWORD *)v43 + 6);
            if ( !v57 )
              v57 = *((_QWORD *)a6 + 2) - *((_QWORD *)v43 + 7);
          }
          if ( !v57 )
            break;
        }
        v55 = *(_QWORD *)(v55 + 8);
        v53 = v56;
      }
      if ( v55 != v54 )
      {
LABEL_105:
        *(_QWORD *)&v65[8 * v51] = v52;
        v71[v51] = v43;
        if ( !v53 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v55);
        if ( v43 != v53 )
          *((_DWORD *)v68 + v51) = 1;
        ++v51;
      }
      ++v49;
    }
    while ( v49 < (unsigned __int64)v13 );
    v70 = v51;
    v29 = v51 == 0;
    DplAccountsAndPolicies = v64;
    if ( !v29 )
    {
LABEL_113:
      v14 = v71;
      v15 = v70;
      goto LABEL_114;
    }
LABEL_112:
    DplAccountsAndPolicies = a6 != 0 ? -2147024894 : 1;
    v64 = DplAccountsAndPolicies;
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_TRACE_EVENT,
      (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
      (unsigned int)L"EDP credential was not found",
      DplAccountsAndPolicies,
      40,
      11);
    goto LABEL_113;
  }
LABEL_115:
  if ( DplAccountsAndPolicies >= 0 && v15 )
  {
    v58 = v79;
    v59 = 0;
    v60 = v78;
    do
    {
      v61 = v59;
      if ( v60 )
        CDplAccount::AddRef(v13[v61]);
      if ( v58 )
        CDplProtectorBase::AddRef(v14[v61]);
      ++v59;
    }
    while ( v59 < v15 );
    v12 = v72;
    v62 = v60;
    DplAccountsAndPolicies = v64;
    if ( v62 )
    {
      *v62 = v13;
      v65 = 0;
    }
    if ( v79 )
    {
      *v79 = v14;
      v14 = 0;
    }
    if ( v87 )
    {
      *v87 = (int *)v68;
      v68 = 0;
    }
    if ( v88 )
      *v88 = v15;
  }
LABEL_131:
  CDplUser::UserSvcUnlock(v80, v69);
  if ( v12 )
    DplibMemFree(v12);
  if ( v65 )
    DplibMemFree(v65);
  if ( v14 )
    DplibMemFree(v14);
  if ( v68 )
    DplibMemFree(v68);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    DplAccountsAndPolicies,
    40,
    74);
  return (unsigned int)DplAccountsAndPolicies;
}

```

## disassembly

```asm
0x1800af128  push    rbp
0x1800af12a  push    rbx
0x1800af12b  push    rsi
0x1800af12c  push    rdi
0x1800af12d  push    r12
0x1800af12f  push    r13
0x1800af131  push    r14
0x1800af133  push    r15
0x1800af135  lea     rbp, [rsp-38h]
0x1800af13a  sub     rsp, 138h
0x1800af141  mov     rax, cs:__security_cookie
0x1800af148  xor     rax, rsp
0x1800af14b  mov     [rbp+70h+var_50], rax
0x1800af14f  mov     rax, [rbp+70h+arg_38]
0x1800af156  mov     rbx, r9
0x1800af159  mov     [rbp+70h+var_C0], rax
0x1800af15d  xorps   xmm0, xmm0
0x1800af160  mov     rax, [rbp+70h+arg_40]
0x1800af167  mov     [rbp+70h+var_B8], rax
0x1800af16b  mov     rax, [rbp+70h+arg_50]
0x1800af172  mov     [rbp+70h+var_70], rax
0x1800af176  xor     eax, eax
0x1800af178  mov     [rbp+70h+var_B0], rcx
0x1800af17c  mov     r12d, eax
0x1800af17f  mov     rcx, [rbp+70h+arg_48]
0x1800af186  mov     r13d, eax
0x1800af189  mov     [rbp+70h+var_E0], r8
0x1800af18d  mov     r15d, eax
0x1800af190  mov     [rbp+70h+lpString1], rdx
0x1800af194  lea     r9d, [rax+28h]
0x1800af198  lea     r8, sourceString
0x1800af19f  mov     [rbp+70h+var_88], rbx
0x1800af1a3  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800af1aa  mov     [rbp+70h+var_78], rcx
0x1800af1ae  mov     [rsp+170h+var_130], eax
0x1800af1b2  mov     r14d, eax
0x1800af1b5  mov     [rsp+170h+var_108], eax
0x1800af1b9  mov     qword ptr [rbp+70h+cchCount1], rax
0x1800af1bd  mov     [rbp+70h+var_90], rax
0x1800af1c1  movups  xmmword ptr [rbp+70h+Uuid.Data1], xmm0
0x1800af1c5  mov     [rbp+70h+var_F0], rax
0x1800af1c9  mov     [rsp+170h+var_128], rax
0x1800af1ce  mov     [rbp+70h+var_C8], rax
0x1800af1d2  mov     [rsp+170h+var_F8], rax
0x1800af1d7  mov     [rbp+70h+var_D0], rax
0x1800af1db  mov     [rsp+170h+var_110], rax
0x1800af1e0  mov     [rbp+70h+var_D8], rax
0x1800af1e4  mov     [rsp+170h+var_100], rax
0x1800af1e9  mov     [rsp+170h+Size], rax
0x1800af1ee  mov     [rsp+170h+bIgnoreCase], 0B2Dh
0x1800af1f6  call    fnEfsLogTrace1Strings
0x1800af1fb  mov     rax, [rbp+70h+var_C0]
0x1800af1ff  test    rax, rax
0x1800af202  jz      short loc_1800AF209
0x1800af204  xor     ecx, ecx
0x1800af206  mov     [rax], rcx
0x1800af209  mov     rax, [rbp+70h+var_B8]
0x1800af20d  test    rax, rax
0x1800af210  jz      short loc_1800AF217
0x1800af212  xor     ecx, ecx
0x1800af214  mov     [rax], rcx
0x1800af217  mov     rax, [rbp+70h+var_78]
0x1800af21b  test    rax, rax
0x1800af21e  jz      short loc_1800AF225
0x1800af220  xor     ecx, ecx
0x1800af222  mov     [rax], rcx
0x1800af225  mov     rax, [rbp+70h+var_70]
0x1800af229  test    rax, rax
0x1800af22c  jz      short loc_1800AF233
0x1800af22e  xor     ecx, ecx
0x1800af230  mov     [rax], rcx
0x1800af233  mov     rsi, [rbp+70h+lpString1]
0x1800af237  test    rsi, rsi
0x1800af23a  jz      short loc_1800AF2B1
0x1800af23c  mov     r9d, 28h ; '('
0x1800af242  mov     [rsp+170h+bIgnoreCase], 0B40h
0x1800af24a  lea     r8, sourceString
0x1800af251  lea     rdx, EFS_TRACE_START_EVENT
0x1800af258  call    fnEfsLogTrace1Strings
0x1800af25d  lea     r8, [rbp+70h+cchCount1]; unsigned __int64 *
0x1800af261  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800af266  mov     rcx, rsi; unsigned __int16 *
0x1800af269  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800af26e  mov     rcx, cs:g_hPublisher
0x1800af275  lea     r9, sourceString
0x1800af27c  mov     [rsp+170h+var_140], 0B40h
0x1800af284  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800af28b  mov     [rsp+170h+var_148], 28h ; '('
0x1800af293  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800af29a  mov     [rsp+170h+bIgnoreCase], eax
0x1800af29e  mov     edi, eax
0x1800af2a0  mov     [rsp+170h+var_130], eax
0x1800af2a4  call    fnEfsLogTrace1String1Dword
0x1800af2a9  test    eax, eax
0x1800af2ab  js      loc_1800AFC95
0x1800af2b1  mov     rsi, [rbp+70h+var_E0]
0x1800af2b5  lea     rax, [rsi-1]
0x1800af2b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800af2bd  ja      short loc_1800AF334
0x1800af2bf  mov     r9d, 28h ; '('
0x1800af2c5  mov     [rsp+170h+bIgnoreCase], 0B45h
0x1800af2cd  lea     r8, sourceString
0x1800af2d4  lea     rdx, EFS_TRACE_START_EVENT
0x1800af2db  call    fnEfsLogTrace1Strings
0x1800af2e0  lea     r8, [rbp+70h+var_90]; unsigned __int64 *
0x1800af2e4  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800af2e9  mov     rcx, rsi; unsigned __int16 *
0x1800af2ec  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800af2f1  mov     rcx, cs:g_hPublisher
0x1800af2f8  lea     r9, sourceString
0x1800af2ff  mov     [rsp+170h+var_140], 0B45h
0x1800af307  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800af30e  mov     [rsp+170h+var_148], 28h ; '('
0x1800af316  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800af31d  mov     [rsp+170h+bIgnoreCase], eax
0x1800af321  mov     edi, eax
0x1800af323  mov     [rsp+170h+var_130], eax
0x1800af327  call    fnEfsLogTrace1String1Dword
0x1800af32c  test    eax, eax
0x1800af32e  js      loc_1800AFC95
0x1800af334  test    rbx, rbx
0x1800af337  jz      loc_1800AF3BE
0x1800af33d  lea     rdx, [rbp+70h+Uuid]; Uuid
0x1800af341  mov     rcx, rbx; StringUuid
0x1800af344  call    cs:__imp_UuidFromStringW
0x1800af34a  mov     esi, 0B4Ch
0x1800af34f  lea     r8, sourceString
0x1800af356  mov     r9d, 28h ; '('
0x1800af35c  mov     [rsp+170h+bIgnoreCase], esi
0x1800af360  lea     rdx, EFS_TRACE_START_EVENT
0x1800af367  mov     ebx, eax
0x1800af369  call    fnEfsLogTrace1Strings
0x1800af36e  mov     ecx, ebx
0x1800af370  mov     [rsp+170h+var_140], esi
0x1800af374  or      ecx, 80010000h
0x1800af37a  mov     [rsp+170h+var_148], 28h ; '('
0x1800af382  xor     edi, edi
0x1800af384  lea     r9, sourceString
0x1800af38b  test    ebx, ebx
0x1800af38d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800af394  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800af39b  cmovnz  edi, ecx
0x1800af39e  mov     rcx, cs:g_hPublisher
0x1800af3a5  mov     [rsp+170h+var_130], edi
0x1800af3a9  mov     [rsp+170h+bIgnoreCase], edi
0x1800af3ad  call    fnEfsLogTrace1String1Dword
0x1800af3b2  test    eax, eax
0x1800af3b4  js      loc_1800AFC95
0x1800af3ba  mov     rbx, [rbp+70h+var_88]
0x1800af3be  mov     rsi, [rbp+70h+var_B0]
0x1800af3c2  mov     rcx, rsi; this
0x1800af3c5  call    ?UserSvcLock@CDplUser@@AEAAHXZ; CDplUser::UserSvcLock(void)
0x1800af3ca  mov     [rsp+170h+var_108], eax
0x1800af3ce  cmp     [rsi+0ECh], r12d
0x1800af3d5  jz      short loc_1800AF3F0
0x1800af3d7  cmp     [rsi+0E8h], r12d
0x1800af3de  jz      short loc_1800AF3F0
0x1800af3e0  mov     rdx, rbx; unsigned __int16 *
0x1800af3e3  mov     rcx, rsi; this
0x1800af3e6  call    ?HasAccountDecryptionFailed@CDplUser@@AEAAPEAU_GUID_ENTRY@@PEAG@Z; CDplUser::HasAccountDecryptionFailed(ushort *)
0x1800af3eb  test    rax, rax
0x1800af3ee  jz      short loc_1800AF45F
0x1800af3f0  mov     r9d, 28h ; '('
0x1800af3f6  mov     [rsp+170h+bIgnoreCase], 0B57h
0x1800af3fe  lea     r8, sourceString
0x1800af405  lea     rdx, EFS_TRACE_START_EVENT
0x1800af40c  call    fnEfsLogTrace1Strings
0x1800af411  mov     rdx, rbx; unsigned __int16 *
0x1800af414  mov     rcx, rsi; this
0x1800af417  call    ?LoadDplAccountsAndPolicies@CDplUser@@AEAAJPEAG@Z; CDplUser::LoadDplAccountsAndPolicies(ushort *)
0x1800af41c  mov     rcx, cs:g_hPublisher
0x1800af423  lea     r9, sourceString
0x1800af42a  mov     [rsp+170h+var_140], 0B57h
0x1800af432  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800af439  mov     [rsp+170h+var_148], 28h ; '('
0x1800af441  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800af448  mov     [rsp+170h+bIgnoreCase], eax
0x1800af44c  mov     edi, eax
0x1800af44e  mov     [rsp+170h+var_130], eax
0x1800af452  call    fnEfsLogTrace1String1Dword
0x1800af457  test    eax, eax
0x1800af459  js      loc_1800AFC95
0x1800af45f  mov     [rbp+70h+var_80], r12
0x1800af463  xor     ecx, ecx
0x1800af465  mov     [rsp+170h+var_120], ecx
0x1800af469  cmp     ecx, 2
0x1800af46c  jnb     loc_1800AFB1A
0x1800af472  lea     rax, [rsi+0C8h]
0x1800af479  mov     rsi, [rax]
0x1800af47c  mov     [rbp+70h+var_68], rax
0x1800af480  cmp     rsi, rax
0x1800af483  jz      loc_1800AF6B8
0x1800af489  lea     rbx, [rsi-58h]
0x1800af48d  mov     qword ptr [rbp+70h+cchCount2], r14
0x1800af491  xor     edx, edx
0x1800af493  mov     [rbp+70h+var_98], r14
0x1800af497  cmp     [rbx+90h], edx
0x1800af49d  jnz     loc_1800AF6AC
0x1800af4a3  cmp     [rbp+70h+lpString1], rdx
0x1800af4a7  jz      loc_1800AF56B
0x1800af4ad  cmp     [rbx+40h], rdx
0x1800af4b1  jz      loc_1800AF6AC
0x1800af4b7  lea     r9d, [rdx+28h]
0x1800af4bb  mov     [rsp+170h+bIgnoreCase], 0B8Ch
0x1800af4c3  lea     rdx, EFS_TRACE_START_EVENT
0x1800af4ca  lea     r8, sourceString
0x1800af4d1  call    fnEfsLogTrace1Strings
0x1800af4d6  mov     rcx, [rbx+40h]; unsigned __int16 *
0x1800af4da  lea     r8, [rbp+70h+cchCount2]; unsigned __int64 *
0x1800af4de  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800af4e3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800af4e8  mov     rcx, cs:g_hPublisher
0x1800af4ef  lea     r9, sourceString
0x1800af4f6  mov     [rsp+170h+var_140], 0B8Ch
0x1800af4fe  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800af505  mov     [rsp+170h+var_148], 28h ; '('
0x1800af50d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800af514  mov     [rsp+170h+bIgnoreCase], eax
0x1800af518  mov     edi, eax
0x1800af51a  mov     [rsp+170h+var_130], eax
0x1800af51e  call    fnEfsLogTrace1String1Dword
0x1800af523  test    eax, eax
0x1800af525  js      loc_1800AFC90
0x1800af52b  mov     r9, qword ptr [rbp+70h+cchCount2]; cchCount2
0x1800af52f  mov     rax, qword ptr [rbp+70h+cchCount1]
0x1800af533  cmp     rax, r9
0x1800af536  jnz     loc_1800AF6A8
0x1800af53c  mov     r8, [rbx+40h]; lpString2
0x1800af540  mov     edx, eax; cchCount1
0x1800af542  mov     rcx, [rbp+70h+lpString1]; lpString1
0x1800af546  mov     [rsp+170h+bIgnoreCase], 1; bIgnoreCase
0x1800af54e  call    cs:__imp_CompareStringOrdinal
0x1800af554  xor     edx, edx
0x1800af556  test    eax, eax
0x1800af558  jz      loc_1800AFA1C
0x1800af55e  cmp     eax, 2
0x1800af561  jnz     loc_1800AF6A8
0x1800af567  mov     ecx, [rsp+170h+var_120]
0x1800af56b  mov     rax, [rbp+70h+var_E0]
0x1800af56f  test    rax, rax
0x1800af572  jnz     short loc_1800AF583
0x1800af574  cmp     [rbx+50h], rdx
0x1800af578  jnz     loc_1800AF6AC
0x1800af57e  jmp     loc_1800AF645
0x1800af583  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800af587  jz      loc_1800AF645
0x1800af58d  cmp     [rbx+50h], rdx
0x1800af591  jz      loc_1800AF6AC
0x1800af597  mov     r9d, 28h ; '('
0x1800af59d  mov     [rsp+170h+bIgnoreCase], 0BD8h
0x1800af5a5  lea     r8, sourceString
0x1800af5ac  lea     rdx, EFS_TRACE_START_EVENT
0x1800af5b3  call    fnEfsLogTrace1Strings
0x1800af5b8  mov     rcx, [rbx+50h]; unsigned __int16 *
0x1800af5bc  lea     r8, [rbp+70h+var_98]; unsigned __int64 *
0x1800af5c0  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800af5c5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800af5ca  mov     rcx, cs:g_hPublisher
0x1800af5d1  lea     r9, sourceString
0x1800af5d8  mov     [rsp+170h+var_140], 0BD8h
0x1800af5e0  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800af5e7  mov     [rsp+170h+var_148], 28h ; '('
0x1800af5ef  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800af5f6  mov     [rsp+170h+bIgnoreCase], eax
0x1800af5fa  mov     edi, eax
0x1800af5fc  mov     [rsp+170h+var_130], eax
0x1800af600  call    fnEfsLogTrace1String1Dword
0x1800af605  test    eax, eax
0x1800af607  js      loc_1800AFC90
0x1800af60d  mov     r9, [rbp+70h+var_98]; cchCount2
0x1800af611  mov     rax, [rbp+70h+var_90]
0x1800af615  cmp     rax, r9
0x1800af618  jnz     loc_1800AF6A8
0x1800af61e  mov     r8, [rbx+50h]; lpString2
0x1800af622  mov     edx, eax; cchCount1
0x1800af624  mov     rcx, [rbp+70h+var_E0]; lpString1
0x1800af628  mov     [rsp+170h+bIgnoreCase], 1; bIgnoreCase
0x1800af630  call    cs:__imp_CompareStringOrdinal
0x1800af636  xor     edx, edx
0x1800af638  test    eax, eax
0x1800af63a  jz      loc_1800AFA62
0x1800af640  cmp     eax, 2
0x1800af643  jnz     short loc_1800AF6A8
0x1800af645  cmp     [rbp+70h+var_88], rdx
0x1800af649  jz      short loc_1800AF662
0x1800af64b  mov     rax, qword ptr [rbp+70h+Uuid.Data1]
0x1800af64f  sub     rax, [rbx+18h]
0x1800af653  jnz     short loc_1800AF65D
0x1800af655  mov     rax, qword ptr [rbp+70h+Uuid.Data4]
0x1800af659  sub     rax, [rbx+20h]
0x1800af65d  test    rax, rax
0x1800af660  jnz     short loc_1800AF6A8
0x1800af662  mov     eax, [rbp+70h+arg_20]
0x1800af668  cmp     eax, 0FFFFFFFFh
0x1800af66b  jz      short loc_1800AF679
0x1800af66d  test    eax, eax
0x1800af66f  jz      short loc_1800AF681
0x1800af671  cmp     eax, [rbx+0D0h]
0x1800af677  jmp     short loc_1800AF67F
0x1800af679  cmp     [rbx+0CCh], edx
  ... truncated ...
```
