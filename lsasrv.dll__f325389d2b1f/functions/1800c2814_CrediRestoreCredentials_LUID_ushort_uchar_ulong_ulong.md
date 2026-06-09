# CrediRestoreCredentials(_LUID *,ushort *,uchar *,ulong,ulong)

- ea: `0x1800c2814`
- end: `0x1800c346a`
- name: `?CrediRestoreCredentials@@YAJPEAU_LUID@@PEAGPEAEKK@Z`
- size: `3158`
- prototype: `__int64 __fastcall(struct _LUID *, LPCWSTR lpFileName, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f4650`

## callees

- `0x18000124c`
- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x1800284d4`
- `0x18003a804`
- `0x18003a880`
- `0x18003ff10`
- `0x180040814`
- `0x18004091c`
- `0x180040af0`
- `0x180041e80`
- `0x1800422f0`
- `0x180044a90`
- `0x180077ffc`
- `0x18008d1a8`
- `0x18008e360`
- `0x180097c3c`
- `0x1800ada18`
- `0x1800b01fc`
- `0x1800b1db8`
- `0x1800bc2c4`
- `0x1800c2814`
- `0x1800c4064`
- `0x1800c7f78`
- `0x1800d2960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c29c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c29c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c2bfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c28d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c28d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c33c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c33c3`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800c2a5a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800c2a5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c295e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c295e`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c29e2`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c2a1f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c29e2`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c2a1f`
- `ntdll!NtSetInformationThread` at `0x1800c2924`
- `ntdll!NtSetInformationThread` at `0x1800c2b51`
- `ntdll!NtSetInformationThread` at `0x1800c2cce`
- `ntdll!NtSetInformationThread` at `0x1800c2924`
- `ntdll!NtSetInformationThread` at `0x1800c2b51`
- `ntdll!NtSetInformationThread` at `0x1800c2cce`
- `ntdll!NtOpenThreadToken` at `0x1800c28f3`
- `ntdll!NtOpenThreadToken` at `0x1800c28f3`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsBackupRestore` at `0x1800c33a1`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsBackupRestore` at `0x1800c33a1`

## pseudocode

```c
__int64 __fastcall CrediRestoreCredentials(
        struct _LUID *a1,
        LPCWSTR lpFileName,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5)
{
  void *v5; // rdi
  struct _RTL_BALANCED_NODE *v6; // rsi
  LsaHandleCache **v11; // rdx
  NTSTATUS Use; // ebx
  struct _RTL_BALANCED_NODE *v13; // r14
  unsigned int v14; // r15d
  HANDLE CurrentThread; // rax
  HANDLE FileW; // rax
  char LastError; // al
  DWORD v18; // ecx
  char FileType; // al
  DWORD v20; // eax
  char v21; // al
  DWORD LowPart; // ebx
  __int64 v23; // rdi
  struct _RTL_BALANCED_NODE *v24; // rax
  int v25; // esi
  void *v26; // rdx
  DWORD v27; // edi
  int v28; // r8d
  int v29; // r9d
  int v30; // ecx
  struct _RTL_BALANCED_NODE *v31; // rcx
  struct _RTL_BALANCED_NODE *v32; // rsi
  struct _RTL_BALANCED_NODE *i; // rax
  __int64 v34; // r8
  char *v35; // rdx
  struct _RTL_BALANCED_NODE *v36; // rax
  struct _RTL_BALANCED_NODE *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  struct _RTL_BALANCED_NODE *v40; // rax
  __int64 *v41; // rcx
  __int64 *v42; // rax
  int Right; // ecx
  __int64 Left_high; // rbx
  unsigned __int8 *v45; // rdi
  int v46; // ecx
  int v47; // eax
  struct _RTL_BALANCED_NODE *v48; // rcx
  __int64 v49; // rax
  unsigned __int8 *v50; // rsi
  struct _RTL_BALANCED_NODE *v51; // rcx
  ULONG_PTR *p_ParentValue; // rax
  unsigned int j; // ebx
  __int64 v54; // rsi
  _QWORD **v55; // rdi
  _QWORD *v56; // r8
  _QWORD *v57; // rax
  struct _RTL_BALANCED_NODE *PromptData; // rax
  struct _RTL_BALANCED_NODE *v59; // rdx
  struct _RTL_BALANCED_NODE *v60; // rcx
  int v61; // eax
  LsaHandleCache **v62; // rdx
  LsaHandleCache *v63; // rcx
  LsaHandleCache **v64; // r8
  __int64 *v65; // rax
  __int64 **v66; // rdx
  __int64 *v67; // rcx
  void *v68; // rdx
  int v69; // ebx
  unsigned int v71; // [rsp+60h] [rbp-A0h] BYREF
  void *v72; // [rsp+68h] [rbp-98h]
  char v73; // [rsp+70h] [rbp-90h]
  struct _RTL_BALANCED_NODE *v74; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v75; // [rsp+80h] [rbp-80h] BYREF
  struct _RTL_BALANCED_NODE *v76; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v77; // [rsp+90h] [rbp-70h] BYREF
  struct _RTL_BALANCED_NODE *v78; // [rsp+98h] [rbp-68h]
  DWORD v79; // [rsp+A0h] [rbp-60h]
  struct _RTL_BALANCED_NODE *v80; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v81; // [rsp+B0h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+B8h] [rbp-48h] BYREF
  struct _RTL_BALANCED_NODE *v83; // [rsp+C0h] [rbp-40h]
  union _LARGE_INTEGER FileSize; // [rsp+C8h] [rbp-38h] BYREF
  DWORD v85; // [rsp+D0h] [rbp-30h] BYREF
  int v86; // [rsp+D4h] [rbp-2Ch] BYREF
  _OWORD v87[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 ThreadInformation; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR v89[10]; // [rsp+100h] [rbp+0h] BYREF

  v73 = 0;
  v5 = 0;
  ThreadInformation = 0;
  v6 = 0;
  TokenHandle = 0;
  v76 = 0;
  v83 = 0;
  v74 = 0;
  v80 = 0;
  v79 = 0;
  v71 = 0;
  v75 = 0;
  v81 = 0;
  FileSize.QuadPart = 0;
  v78 = (struct _RTL_BALANCED_NODE *)&v77;
  v77 = (__int64 *)&v77;
  memset(v87, 0, sizeof(v87));
  Use = CredpLoadOnFirstUse(a1);
  if ( Use < 0 )
    goto LABEL_5;
  if ( a5 && (a5 & 0xFFFFFFFE) != 0 )
  {
    Use = -1073741581;
LABEL_5:
    v13 = v74;
    v14 = v71;
LABEL_55:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( v13 )
    {
      v35 = (char *)v14;
      v36 = v13;
      if ( v14 )
      {
        do
        {
          LOBYTE(v36->Children[0]) = 0;
          v36 = (struct _RTL_BALANCED_NODE *)((char *)v36 + 1);
          --v35;
        }
        while ( v35 );
      }
      LsapSubProv_FreeRoutine(v13, v35);
    }
    v6 = v83;
    goto LABEL_62;
  }
  if ( !lpFileName )
  {
    Use = -1073741585;
    goto LABEL_5;
  }
  Use = CredpReferenceCredSets(a1, 0, (struct _CREDENTIAL_SETS *)v87);
  if ( Use < 0 )
    goto LABEL_5;
  CurrentThread = GetCurrentThread();
  Use = NtOpenThreadToken(CurrentThread, 0xCu, 1u, &TokenHandle);
  if ( Use < 0 )
    goto LABEL_5;
  if ( TokenHandle )
  {
    Use = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( Use < 0 )
      goto LABEL_5;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
    v72 = FileW;
    v5 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v5 = 0;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          420,
          (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
          (_DWORD)lpFileName,
          LastError);
      }
      v18 = GetLastError();
LABEL_17:
      Use = CredpWinStatusToNtStatus(v18);
LABEL_34:
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
      goto LABEL_5;
    }
    if ( GetFileType(FileW) != 1 )
    {
      Use = -1073741811;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        FileType = GetFileType(v5);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          421,
          (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
          (_DWORD)lpFileName,
          FileType);
      }
      goto LABEL_34;
    }
    if ( !GetFileSizeEx(v5, &FileSize) )
    {
      v20 = GetLastError();
      Use = CredpWinStatusToNtStatus(v20);
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v21 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          422,
          (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
          (_DWORD)lpFileName,
          v21);
      }
      goto LABEL_34;
    }
    if ( FileSize.HighPart )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 423, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, lpFileName);
      }
      v18 = 1462;
      goto LABEL_17;
    }
    LowPart = FileSize.LowPart;
    v79 = FileSize.LowPart;
    v23 = FileSize.LowPart;
    v24 = (struct _RTL_BALANCED_NODE *)LsapAllocate(FileSize.LowPart);
    v83 = v24;
    v25 = (int)v24;
    if ( !v24 )
    {
      Use = -1073741801;
LABEL_33:
      v5 = v72;
      goto LABEL_34;
    }
    Use = CredpReadFile(v72, (unsigned __int8 *)v24, LowPart);
    if ( Use < 0 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          424,
          (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
          (_DWORD)lpFileName,
          Use);
      }
      goto LABEL_33;
    }
    if ( !(unsigned __int8)LsaICryptUnprotectDataEx(v25, v23, 0, 0, 0, 0, 1, 0, 0, 0, (__int64)&v80, (__int64)&v75) )
    {
      v27 = GetLastError();
      v30 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          425,
          (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
          (_DWORD)lpFileName,
          v27);
      }
      Use = -1073741762;
      if ( (unsigned int)dword_18019A2B0 > 2 )
      {
        v86 = (unsigned __int8)byte_1801A0BC9;
        v89[0] = lpFileName;
        v85 = v27;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v30,
          (unsigned int)byte_18017ECB9,
          v28,
          v29,
          (__int64)&v86,
          (__int64)&v85,
          (__int64)v89);
      }
      goto LABEL_33;
    }
    v31 = v83;
    v32 = v80;
    for ( i = v83; v23; --v23 )
    {
      LOBYTE(i->Children[0]) = 0;
      i = (struct _RTL_BALANCED_NODE *)((char *)i + 1);
    }
    LsapSubProv_FreeRoutine(v31, v26);
    v83 = 0;
    Use = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    if ( Use < 0 )
      goto LABEL_33;
    if ( LODWORD(v32->Children[0]) != 1 )
    {
      v11 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_Sll(*((_QWORD *)WPP_GLOBAL_Control + 2), 426, v34, (_DWORD)lpFileName, (char)v32->Children[0], 1);
      }
LABEL_52:
      Use = -1073741811;
LABEL_53:
      v13 = v74;
      v14 = v71;
LABEL_54:
      v5 = v72;
      goto LABEL_55;
    }
    Right = (int)v32->Right;
    if ( Right == 1 )
    {
      if ( !a3 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            428,
            WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
            lpFileName);
        }
        goto LABEL_87;
      }
    }
    else if ( Right != 2 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 427, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, lpFileName);
      }
      goto LABEL_52;
    }
    Left_high = HIDWORD(v32->Left);
    if ( Left_high != v75 - 12LL )
    {
      v11 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_lP(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v34, (unsigned int)Left_high, v75 - 12LL);
      }
      Use = -1073741762;
      goto LABEL_53;
    }
    v45 = (unsigned __int8 *)&v32->Right + 4;
    v46 = Right - 1;
    if ( v46 )
    {
      if ( v46 != 1 )
      {
        Use = -1073741811;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            432,
            WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
            lpFileName);
        }
        goto LABEL_53;
      }
      if ( a3 && a4 )
      {
        Use = -1073741811;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 431, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids);
        }
        goto LABEL_53;
      }
      v13 = v74;
      v14 = v71;
LABEL_113:
      v50 = &v45[(unsigned int)Left_high];
      while ( v45 < v50 )
      {
        if ( v50 - v45 > 0xFFFFFFFFLL )
        {
          Use = -2147483643;
          goto LABEL_54;
        }
        Use = CredpUnmarshalCredential(v45, (int)v50 - (int)v45, &v81, (struct _CANONICAL_CREDENTIAL **)&v76);
        if ( Use < 0 )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              433,
              WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
              (unsigned int)Use);
          }
          goto LABEL_54;
        }
        v51 = v78;
        if ( (__int64 **)v78->Children[0] != &v77 )
LABEL_161:
          __fastfail(3u);
        v11 = (LsaHandleCache **)&v77;
        v45 += (v81 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL;
        p_ParentValue = &v76[3].ParentValue;
        v76[4].Children[0] = v78;
        *p_ParentValue = (ULONG_PTR)&v77;
        v51->Children[0] = (struct _RTL_BALANCED_NODE *)p_ParentValue;
        v78 = (struct _RTL_BALANCED_NODE *)p_ParentValue;
      }
      CredpLockAndRefreshCredSets((struct _CREDENTIAL_SETS *)v87, a1, 0, 0);
      v73 = 1;
      if ( *(_BYTE *)(*((_QWORD *)&v87[0] + 1) + 308LL) )
      {
        for ( j = 1; j <= 3; ++j )
        {
          if ( j != 1 )
          {
            if ( j == 2 )
              v54 = *(_QWORD *)(*(_QWORD *)&v87[0] + 32LL);
            else
              v54 = *(_QWORD *)(*(_QWORD *)&v87[0] + 24LL);
            v55 = (_QWORD **)(v54 + 8);
            while ( 1 )
            {
              v56 = *v55;
              if ( *v55 == v55 )
                break;
              if ( (_QWORD **)v56[1] != v55 )
                goto LABEL_161;
              v57 = (_QWORD *)*v56;
              if ( *(_QWORD **)(*v56 + 8LL) != v56 )
                goto LABEL_161;
              *v55 = v57;
              v57[1] = v55;
              v76 = (struct _RTL_BALANCED_NODE *)(v56 - 11);
              PromptData = (struct _RTL_BALANCED_NODE *)CredpFindPromptData(
                                                          v87,
                                                          v56 + 4,
                                                          *((unsigned int *)v56 + 12),
                                                          v56 + 7,
                                                          *((_DWORD *)v56 - 21),
                                                          j);
              if ( PromptData )
              {
                v59 = PromptData->Children[0];
                if ( PromptData->Children[0]->Children[1] != PromptData )
                  goto LABEL_161;
                v60 = PromptData->Children[1];
                if ( v60->Children[0] != PromptData )
                  goto LABEL_161;
                v60->Children[0] = v59;
                v59->Children[1] = v60;
                LsapSubProv_FreeRoutine(PromptData, v59);
              }
              v61 = CredpDeleteCredentialFile((struct _CREDENTIAL_SETS *)v87, (struct _CANONICAL_CREDENTIAL *)v76);
              if ( v61 < 0 )
              {
                v62 = &WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    435,
                    WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
                    (unsigned int)v61);
                }
              }
              LsapSubProv_FreeRoutine(v76, v62);
            }
            *(_DWORD *)(v54 + 564) = 0;
          }
        }
LABEL_147:
        v63 = WPP_GLOBAL_Control;
        v64 = &WPP_GLOBAL_Control;
        while ( 1 )
        {
          v65 = v77;
          v66 = &v77;
          if ( v77 == (__int64 *)&v77 )
            break;
          if ( (__int64 **)v77[1] != &v77 )
            goto LABEL_161;
          v67 = (__int64 *)*v77;
          if ( *(__int64 **)(*v77 + 8) != v77 )
            goto LABEL_161;
          v77 = (__int64 *)*v77;
          v67[1] = (__int64)&v77;
          v76 = (struct _RTL_BALANCED_NODE *)(v65 - 11);
          *((_BYTE *)v65 + 157) = 1;
          v69 = CredpWriteCredential(
                  0,
                  (struct _CREDENTIAL_SETS *)v87,
                  (struct _CANONICAL_CREDENTIAL **)&v76,
                  1u,
                  0,
                  0,
                  0,
                  0);
          if ( v69 >= 0 )
            goto LABEL_147;
          LsapSubProv_FreeRoutine(v76, v68);
          v63 = WPP_GLOBAL_Control;
          v64 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              436,
              WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
              (unsigned int)v69);
            goto LABEL_147;
          }
        }
        if ( v63 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v63 + 7) & 0x400000) != 0 )
          WPP_SF_S(*((_QWORD *)v63 + 2), 437, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, lpFileName);
        if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v63, v66, v64) )
          LsapAdtAuditCredentialsBackupRestore(a1, lpFileName, 0);
        Use = 0;
      }
      else
      {
        Use = -1073741729;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 434, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids);
        }
      }
      goto LABEL_54;
    }
    v47 = CredpDecryptDataBySecret(
            (unsigned __int8 *)&v32->Right + 4,
            Left_high,
            a3,
            a4,
            (unsigned __int8 **)&v74,
            &v71);
    if ( v47 >= 0 )
    {
      v48 = v80;
      v13 = v74;
      v14 = v71;
      v45 = (unsigned __int8 *)v74;
      LODWORD(Left_high) = v71;
      if ( v80 )
      {
        v49 = v75;
        if ( v75 )
        {
          do
          {
            LOBYTE(v48->Children[0]) = 0;
            v48 = (struct _RTL_BALANCED_NODE *)((char *)v48 + 1);
            --v49;
          }
          while ( v49 );
          v48 = v80;
        }
        LsapSubProv_FreeRoutine(v48, v11);
        v80 = 0;
      }
      goto LABEL_113;
    }
    v11 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        430,
        WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
        (unsigned int)v47);
    }
LABEL_87:
    Use = -1073741718;
    goto LABEL_53;
  }
LABEL_62:
  v37 = v80;
  if ( v80 )
  {
    v38 = v75;
    if ( v75 )
    {
      do
      {
        LOBYTE(v37->Children[0]) = 0;
        v37 = (struct _RTL_BALANCED_NODE *)((char *)v37 + 1);
        --v38;
      }
      while ( v38 );
      v37 = v80;
    }
    LsapSubProv_FreeRoutine(v37, v11);
  }
  if ( v6 )
  {
    v39 = v79;
    v40 = v6;
    if ( v79 )
    {
      do
      {
        LOBYTE(v40->Children[0]) = 0;
        v40 = (struct _RTL_BALANCED_NODE *)((char *)v40 + 1);
        --v39;
      }
      while ( v39 );
    }
    LsapSubProv_FreeRoutine(v6, v11);
  }
  if ( v73 )
    CredpUnlockAndFlushCredSets(a1, (struct _CREDENTIAL_SETS *)v87);
  CredpDereferenceCredSets((struct _CREDENTIAL_SETS *)v87);
  while ( 1 )
  {
    v41 = v77;
    if ( v77 == (__int64 *)&v77 )
      break;
    if ( (__int64 **)v77[1] != &v77 )
      goto LABEL_161;
    v42 = (__int64 *)*v77;
    if ( *(__int64 **)(*v77 + 8) != v77 )
      goto LABEL_161;
    v77 = (__int64 *)*v77;
    v42[1] = (__int64)&v77;
    v76 = (struct _RTL_BALANCED_NODE *)(v41 - 11);
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)(v41 - 11), &v77);
  }
  if ( v5 )
    CloseHandle(v5);
  if ( Use >= 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        439,
        WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
        a1->LowPart,
        a1->HighPart);
    }
  }
  else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_DDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      438,
      WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
      a1->LowPart,
      a1->HighPart,
      Use);
  }
  return (unsigned int)Use;
}

```

## disassembly

```asm
0x1800c2814  push    rbp
0x1800c2816  push    rbx
0x1800c2817  push    rsi
0x1800c2818  push    rdi
0x1800c2819  push    r12
0x1800c281b  push    r13
0x1800c281d  push    r14
0x1800c281f  push    r15
0x1800c2821  lea     rbp, [rsp-18h]
0x1800c2826  sub     rsp, 118h
0x1800c282d  xor     eax, eax
0x1800c282f  xorps   xmm0, xmm0
0x1800c2832  mov     [rsp+150h+var_E0], al
0x1800c2836  mov     edi, eax
0x1800c2838  mov     [rbp+50h+ThreadInformation], rax
0x1800c283c  mov     esi, eax
0x1800c283e  mov     [rbp+50h+TokenHandle], rax
0x1800c2842  mov     r15d, r9d
0x1800c2845  mov     [rbp+50h+var_C8], rax
0x1800c2849  mov     r14, r8
0x1800c284c  mov     [rbp+50h+var_90], rax
0x1800c2850  mov     r12, rdx
0x1800c2853  mov     [rsp+150h+var_D8], rax
0x1800c2858  mov     r13, rcx
0x1800c285b  mov     [rbp+50h+var_A8], rax
0x1800c285f  mov     [rbp+50h+var_B0], eax
0x1800c2862  mov     [rsp+150h+var_F0], eax
0x1800c2866  mov     [rbp+50h+var_D0], eax
0x1800c2869  mov     [rbp+50h+var_A0], eax
0x1800c286c  mov     qword ptr [rbp+50h+FileSize], rax
0x1800c2870  lea     rax, [rbp+50h+var_C0]
0x1800c2874  mov     [rbp+50h+var_B8], rax
0x1800c2878  lea     rax, [rbp+50h+var_C0]
0x1800c287c  mov     [rbp+50h+var_C0], rax
0x1800c2880  movups  [rbp+50h+var_78], xmm0
0x1800c2884  movups  [rbp+50h+var_68], xmm0
0x1800c2888  call    ?CredpLoadOnFirstUse@@YAJPEAU_LUID@@@Z; CredpLoadOnFirstUse(_LUID *)
0x1800c288d  mov     ebx, eax
0x1800c288f  test    eax, eax
0x1800c2891  js      short loc_1800C28A9
0x1800c2893  mov     eax, [rbp+50h+arg_20]
0x1800c2899  test    eax, eax
0x1800c289b  jz      short loc_1800C28B8
0x1800c289d  test    eax, 0FFFFFFFEh
0x1800c28a2  jz      short loc_1800C28B8
0x1800c28a4  mov     ebx, 0C00000F3h
0x1800c28a9  mov     r14, [rsp+150h+var_D8]
0x1800c28ae  mov     r15d, [rsp+150h+var_F0]
0x1800c28b3  jmp     loc_1800C2D3C
0x1800c28b8  test    r12, r12
0x1800c28bb  jnz     short loc_1800C28C4
0x1800c28bd  mov     ebx, 0C00000EFh
0x1800c28c2  jmp     short loc_1800C28A9
0x1800c28c4  lea     r8, [rbp+50h+var_78]; struct _CREDENTIAL_SETS *
0x1800c28c8  xor     edx, edx; unsigned __int8
0x1800c28ca  mov     rcx, r13; struct _LUID *
0x1800c28cd  call    ?CredpReferenceCredSets@@YAJPEAU_LUID@@EPEAU_CREDENTIAL_SETS@@@Z; CredpReferenceCredSets(_LUID *,uchar,_CREDENTIAL_SETS *)
0x1800c28d2  mov     ebx, eax
0x1800c28d4  test    eax, eax
0x1800c28d6  js      short loc_1800C28A9
0x1800c28d8  call    cs:__imp_GetCurrentThread
0x1800c28df  nop     dword ptr [rax+rax+00h]
0x1800c28e4  lea     r9, [rbp+50h+TokenHandle]; TokenHandle
0x1800c28e8  mov     r8b, 1; OpenAsSelf
0x1800c28eb  mov     rcx, rax; ThreadHandle
0x1800c28ee  mov     edx, 0Ch; DesiredAccess
0x1800c28f3  call    cs:__imp_NtOpenThreadToken
0x1800c28fa  nop     dword ptr [rax+rax+00h]
0x1800c28ff  mov     ebx, eax
0x1800c2901  test    eax, eax
0x1800c2903  js      short loc_1800C28A9
0x1800c2905  cmp     [rbp+50h+TokenHandle], rsi
0x1800c2909  jz      loc_1800C2D79
0x1800c290f  mov     r9d, 8; ThreadInformationLength
0x1800c2915  lea     r8, [rbp+50h+ThreadInformation]; ThreadInformation
0x1800c2919  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c2920  lea     edx, [r9-3]; ThreadInformationClass
0x1800c2924  call    cs:__imp_NtSetInformationThread
0x1800c292b  nop     dword ptr [rax+rax+00h]
0x1800c2930  mov     ebx, eax
0x1800c2932  test    eax, eax
0x1800c2934  js      loc_1800C28A9
0x1800c293a  xor     r9d, r9d; lpSecurityAttributes
0x1800c293d  mov     [rsp+150h+hTemplateFile], rsi; hTemplateFile
0x1800c2942  mov     [rsp+150h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800c294a  mov     edx, 80000000h; dwDesiredAccess
0x1800c294f  mov     rcx, r12; lpFileName
0x1800c2952  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c295a  lea     r8d, [r9+1]; dwShareMode
0x1800c295e  call    cs:__imp_CreateFileW
0x1800c2965  nop     dword ptr [rax+rax+00h]
0x1800c296a  mov     [rsp+150h+var_E8], rax
0x1800c296f  mov     rdi, rax
0x1800c2972  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c2976  jnz     short loc_1800C29DF
0x1800c2978  xor     edi, edi
0x1800c297a  mov     rax, cs:WPP_GLOBAL_Control
0x1800c2981  lea     rcx, WPP_GLOBAL_Control
0x1800c2988  cmp     rax, rcx
0x1800c298b  jz      short loc_1800C29C5
0x1800c298d  test    dword ptr [rax+1Ch], 200h
0x1800c2994  jz      short loc_1800C29C5
0x1800c2996  call    cs:__imp_GetLastError
0x1800c299d  nop     dword ptr [rax+rax+00h]
0x1800c29a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c29a9  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c29b0  mov     edx, 1A4h
0x1800c29b5  mov     [rsp+150h+dwCreationDisposition], eax
0x1800c29b9  mov     r9, r12
0x1800c29bc  mov     rcx, [rcx+10h]
0x1800c29c0  call    WPP_SF_Sd
0x1800c29c5  call    cs:__imp_GetLastError
0x1800c29cc  nop     dword ptr [rax+rax+00h]
0x1800c29d1  mov     ecx, eax; unsigned int
0x1800c29d3  call    ?CredpWinStatusToNtStatus@@YAJK@Z; CredpWinStatusToNtStatus(ulong)
0x1800c29d8  mov     ebx, eax
0x1800c29da  jmp     loc_1800C2B3C
0x1800c29df  mov     rcx, rdi; hFile
0x1800c29e2  call    cs:__imp_GetFileType
0x1800c29e9  nop     dword ptr [rax+rax+00h]
0x1800c29ee  cmp     eax, 1
0x1800c29f1  jz      short loc_1800C2A53
0x1800c29f3  mov     ebx, 0C000000Dh
0x1800c29f8  mov     rax, cs:WPP_GLOBAL_Control
0x1800c29ff  lea     rcx, WPP_GLOBAL_Control
0x1800c2a06  cmp     rax, rcx
0x1800c2a09  jz      loc_1800C2B3C
0x1800c2a0f  test    dword ptr [rax+1Ch], 200h
0x1800c2a16  jz      loc_1800C2B3C
0x1800c2a1c  mov     rcx, rdi; hFile
0x1800c2a1f  call    cs:__imp_GetFileType
0x1800c2a26  nop     dword ptr [rax+rax+00h]
0x1800c2a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2a32  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c2a39  mov     edx, 1A5h
0x1800c2a3e  mov     [rsp+150h+dwCreationDisposition], eax
0x1800c2a42  mov     r9, r12
0x1800c2a45  mov     rcx, [rcx+10h]
0x1800c2a49  call    WPP_SF_Sd
0x1800c2a4e  jmp     loc_1800C2B3C
0x1800c2a53  lea     rdx, [rbp+50h+FileSize]; lpFileSize
0x1800c2a57  mov     rcx, rdi; hFile
0x1800c2a5a  call    cs:__imp_GetFileSizeEx
0x1800c2a61  nop     dword ptr [rax+rax+00h]
0x1800c2a66  test    eax, eax
0x1800c2a68  jnz     short loc_1800C2AD4
0x1800c2a6a  call    cs:__imp_GetLastError
0x1800c2a71  nop     dword ptr [rax+rax+00h]
0x1800c2a76  mov     ecx, eax; unsigned int
0x1800c2a78  call    ?CredpWinStatusToNtStatus@@YAJK@Z; CredpWinStatusToNtStatus(ulong)
0x1800c2a7d  mov     ebx, eax
0x1800c2a7f  mov     rax, cs:WPP_GLOBAL_Control
0x1800c2a86  lea     rcx, WPP_GLOBAL_Control
0x1800c2a8d  cmp     rax, rcx
0x1800c2a90  jz      loc_1800C2B3C
0x1800c2a96  test    dword ptr [rax+1Ch], 200h
0x1800c2a9d  jz      loc_1800C2B3C
0x1800c2aa3  call    cs:__imp_GetLastError
0x1800c2aaa  nop     dword ptr [rax+rax+00h]
0x1800c2aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2ab6  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c2abd  mov     edx, 1A6h
0x1800c2ac2  mov     [rsp+150h+dwCreationDisposition], eax
0x1800c2ac6  mov     r9, r12
0x1800c2ac9  mov     rcx, [rcx+10h]
0x1800c2acd  call    WPP_SF_Sd
0x1800c2ad2  jmp     short loc_1800C2B3C
0x1800c2ad4  cmp     dword ptr [rbp+50h+FileSize+4], esi
0x1800c2ad7  jz      short loc_1800C2B17
0x1800c2ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2ae0  lea     rax, WPP_GLOBAL_Control
0x1800c2ae7  cmp     rcx, rax
0x1800c2aea  jz      short loc_1800C2B0D
0x1800c2aec  test    dword ptr [rcx+1Ch], 200h
0x1800c2af3  jz      short loc_1800C2B0D
0x1800c2af5  mov     rcx, [rcx+10h]
0x1800c2af9  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c2b00  mov     edx, 1A7h
0x1800c2b05  mov     r9, r12
0x1800c2b08  call    WPP_SF_S
0x1800c2b0d  mov     ecx, 5B6h
0x1800c2b12  jmp     loc_1800C29D3
0x1800c2b17  mov     ebx, dword ptr [rbp+50h+FileSize]
0x1800c2b1a  mov     ecx, ebx
0x1800c2b1c  mov     [rbp+50h+var_B0], ebx
0x1800c2b1f  mov     edi, ebx
0x1800c2b21  call    LsapAllocate
0x1800c2b26  mov     [rbp+50h+var_90], rax
0x1800c2b2a  mov     rsi, rax
0x1800c2b2d  test    rax, rax
0x1800c2b30  jnz     short loc_1800C2B62
0x1800c2b32  mov     ebx, 0C0000017h
0x1800c2b37  mov     rdi, [rsp+150h+var_E8]
0x1800c2b3c  mov     r9d, 8; ThreadInformationLength
0x1800c2b42  lea     r8, [rbp+50h+TokenHandle]; ThreadInformation
0x1800c2b46  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c2b4d  lea     edx, [r9-3]; ThreadInformationClass
0x1800c2b51  call    cs:__imp_NtSetInformationThread
0x1800c2b58  nop     dword ptr [rax+rax+00h]
0x1800c2b5d  jmp     loc_1800C28A9
0x1800c2b62  mov     rcx, [rsp+150h+var_E8]; void *
0x1800c2b67  mov     r8d, ebx; unsigned int
0x1800c2b6a  mov     rdx, rsi; unsigned __int8 *
0x1800c2b6d  call    ?CredpReadFile@@YAKPEAXPEAEK@Z; CredpReadFile(void *,uchar *,ulong)
0x1800c2b72  mov     ebx, eax
0x1800c2b74  test    eax, eax
0x1800c2b76  jns     short loc_1800C2BB2
0x1800c2b78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2b7f  lea     rax, WPP_GLOBAL_Control
0x1800c2b86  cmp     rcx, rax
0x1800c2b89  jz      short loc_1800C2B37
0x1800c2b8b  test    dword ptr [rcx+1Ch], 200h
0x1800c2b92  jz      short loc_1800C2B37
0x1800c2b94  mov     rcx, [rcx+10h]
0x1800c2b98  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c2b9f  mov     edx, 1A8h
0x1800c2ba4  mov     [rsp+150h+dwCreationDisposition], ebx
0x1800c2ba8  mov     r9, r12
0x1800c2bab  call    WPP_SF_Sd
0x1800c2bb0  jmp     short loc_1800C2B37
0x1800c2bb2  xor     ebx, ebx
0x1800c2bb4  lea     rax, [rbp+50h+var_D0]
0x1800c2bb8  mov     [rsp+150h+var_F8], rax
0x1800c2bbd  xor     r9d, r9d
0x1800c2bc0  lea     rax, [rbp+50h+var_A8]
0x1800c2bc4  xor     r8d, r8d
0x1800c2bc7  mov     [rsp+150h+var_100], rax
0x1800c2bcc  mov     edx, edi
0x1800c2bce  mov     [rsp+150h+var_108], rbx
0x1800c2bd3  mov     rcx, rsi
0x1800c2bd6  mov     [rsp+150h+var_110], ebx
0x1800c2bda  mov     [rsp+150h+var_118], rbx
0x1800c2bdf  mov     dword ptr [rsp+150h+hTemplateFile], 1
0x1800c2be7  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rbx
0x1800c2bec  mov     qword ptr [rsp+150h+dwCreationDisposition], rbx
0x1800c2bf1  call    LsaICryptUnprotectDataEx
0x1800c2bf6  test    al, al
0x1800c2bf8  jnz     loc_1800C2C95
0x1800c2bfe  call    cs:__imp_GetLastError
0x1800c2c05  nop     dword ptr [rax+rax+00h]
0x1800c2c0a  mov     edi, eax
0x1800c2c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2c13  lea     rax, WPP_GLOBAL_Control
0x1800c2c1a  cmp     rcx, rax
0x1800c2c1d  jz      short loc_1800C2C44
0x1800c2c1f  test    dword ptr [rcx+1Ch], 200h
0x1800c2c26  jz      short loc_1800C2C44
0x1800c2c28  mov     rcx, [rcx+10h]
0x1800c2c2c  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c2c33  mov     edx, 1A9h
0x1800c2c38  mov     [rsp+150h+dwCreationDisposition], edi
0x1800c2c3c  mov     r9, r12
0x1800c2c3f  call    WPP_SF_Sd
0x1800c2c44  mov     eax, cs:dword_18019A2B0
0x1800c2c4a  mov     ebx, 0C000003Eh
0x1800c2c4f  cmp     eax, 2
0x1800c2c52  jbe     loc_1800C2B37
0x1800c2c58  movzx   eax, cs:byte_1801A0BC9
0x1800c2c5f  lea     rdx, byte_18017ECB9
0x1800c2c66  mov     [rbp+50h+var_7C], eax
0x1800c2c69  lea     rax, [rbp+50h+var_50]
0x1800c2c6d  mov     [rsp+150h+hTemplateFile], rax
0x1800c2c72  lea     rax, [rbp+50h+var_80]
0x1800c2c76  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x1800c2c7b  lea     rax, [rbp+50h+var_7C]
0x1800c2c7f  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x1800c2c84  mov     [rbp+50h+var_50], r12
0x1800c2c88  mov     [rbp+50h+var_80], edi
0x1800c2c8b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800c2c90  jmp     loc_1800C2B37
0x1800c2c95  mov     rcx, [rbp+50h+var_90]; struct _RTL_BALANCED_NODE *
0x1800c2c99  mov     rsi, [rbp+50h+var_A8]
0x1800c2c9d  mov     rax, rcx
0x1800c2ca0  test    rdi, rdi
0x1800c2ca3  jz      short loc_1800C2CB0
0x1800c2ca5  mov     [rax], bl
0x1800c2ca7  inc     rax
0x1800c2caa  sub     rdi, 1
0x1800c2cae  jnz     short loc_1800C2CA5
0x1800c2cb0  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800c2cb5  mov     r9d, 8; ThreadInformationLength
0x1800c2cbb  mov     [rbp+50h+var_90], rbx
0x1800c2cbf  lea     r8, [rbp+50h+TokenHandle]; ThreadInformation
0x1800c2cc3  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c2cca  lea     edx, [r9-3]; ThreadInformationClass
0x1800c2cce  call    cs:__imp_NtSetInformationThread
0x1800c2cd5  nop     dword ptr [rax+rax+00h]
0x1800c2cda  mov     ebx, eax
0x1800c2cdc  test    eax, eax
0x1800c2cde  js      loc_1800C2B37
0x1800c2ce4  mov     eax, [rsi]
0x1800c2ce6  cmp     eax, 1
0x1800c2ce9  jz      loc_1800C2E29
0x1800c2cef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2cf6  lea     rdx, WPP_GLOBAL_Control
0x1800c2cfd  cmp     rcx, rdx
0x1800c2d00  jz      short loc_1800C2D28
0x1800c2d02  test    dword ptr [rcx+1Ch], 200h
0x1800c2d09  jz      short loc_1800C2D28
0x1800c2d0b  mov     rcx, [rcx+10h]
  ... truncated ...
```
