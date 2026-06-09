# CompareStringA

- ea: `0x18001cd50`
- end: `0x18001e3cc`
- name: `CompareStringA`
- size: `5756`
- prototype: `int __stdcall(LCID Locale, DWORD dwCmpFlags, PCNZCH lpString1, int cchCount1, PCNZCH lpString2, int cchCount2)`
- caller_count: `11`
- callee_count: `35`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800202d0`
- `0x180040c2c`
- `0x1800417e0`
- `0x1800418a0`
- `0x1800b2f74`
- `0x1800b6b10`
- `0x1800ce280`
- `0x180101780`
- `0x180108850`
- `0x180113e80`
- `0x180148100`

## callees

- `0x18001cd34`
- `0x18001cd50`
- `0x18001e3e0`
- `0x180020ad0`
- `0x180021e08`
- `0x180024c80`
- `0x180024ed0`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x1800294a0`
- `0x180029660`
- `0x180029ec0`
- `0x18002aabc`
- `0x1800461b0`
- `0x180046520`
- `0x180046ac0`
- `0x1800486a0`
- `0x180048f20`
- `0x18004a310`
- `0x18004a820`
- `0x18004b408`
- `0x18007ab80`
- `0x18007cf00`
- `0x1800813ec`
- `0x180081460`
- `0x180083140`
- `0x1801035c4`
- `0x18012c3ac`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194eb9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001df92`
- `ntdll!RtlInitUnicodeString` at `0x18001df92`
- `ntdll!NtOpenKey` at `0x18001dfdb`
- `ntdll!NtOpenKey` at `0x18001dfdb`
- `ntdll!NtCreateKey` at `0x18001e019`
- `ntdll!NtCreateKey` at `0x18001e019`
- `ntdll!RtlLcidToLocaleName` at `0x18001de0f`
- `ntdll!RtlLcidToLocaleName` at `0x18001de0f`
- `ntdll!RtlOpenCurrentUser` at `0x18001d9e1`
- `ntdll!RtlOpenCurrentUser` at `0x18001d9e1`
- `ntdll!CsrClientCallServer` at `0x18001d7d0`
- `ntdll!CsrClientCallServer` at `0x18001d7d0`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001d7a4`
- `ntdll!CsrCaptureMessageBuffer` at `0x18001d7a4`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001d7fe`
- `ntdll!CsrFreeCaptureBuffer` at `0x18001d7fe`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001d492`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18001d492`
- `ntdll!NtClose` at `0x18001d50b`
- `ntdll!NtClose` at `0x18001da94`
- `ntdll!NtClose` at `0x18001e031`
- `ntdll!NtClose` at `0x18001e072`
- `ntdll!NtClose` at `0x18001d50b`
- `ntdll!NtClose` at `0x18001da94`
- `ntdll!NtClose` at `0x18001e031`
- `ntdll!NtClose` at `0x18001e072`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001cf76`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d0c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d447`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d58b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d725`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d8e0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001de54`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001cf76`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d0c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d447`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d58b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d725`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d8e0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001de54`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d062`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d1b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d677`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d6b2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d755`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d940`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001de7f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d062`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d1b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d677`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d6b2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d755`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d940`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001de7f`
- `ntdll!RtlFreeHeap` at `0x18001df4a`
- `ntdll!RtlFreeHeap` at `0x18001df76`
- `ntdll!RtlFreeHeap` at `0x18001e349`
- `ntdll!RtlFreeHeap` at `0x18001e398`
- `ntdll!RtlFreeHeap` at `0x18001e3bb`
- `ntdll!RtlFreeHeap` at `0x18001df4a`
- `ntdll!RtlFreeHeap` at `0x18001df76`
- `ntdll!RtlFreeHeap` at `0x18001e349`
- `ntdll!RtlFreeHeap` at `0x18001e398`
- `ntdll!RtlFreeHeap` at `0x18001e3bb`
- `ntdll!RtlAllocateHeap` at `0x18001dedf`
- `ntdll!RtlAllocateHeap` at `0x18001e2ca`
- `ntdll!RtlAllocateHeap` at `0x18001e303`
- `ntdll!RtlAllocateHeap` at `0x18001dedf`
- `ntdll!RtlAllocateHeap` at `0x18001e2ca`
- `ntdll!RtlAllocateHeap` at `0x18001e303`

## pseudocode

```c
int __stdcall CompareStringA(
        LCID Locale,
        DWORD dwCmpFlags,
        PCNZCH lpString1,
        int cchCount1,
        PCNZCH lpString2,
        int cchCount2)
{
  int v6; // edi
  DWORD v8; // eax
  unsigned __int64 v9; // r13
  UINT v10; // r14d
  DWORD v11; // r12d
  __int64 v12; // rdx
  int v13; // ecx
  WCHAR *lpWideCharStr; // r12
  int cchWideChar; // r14d
  int v16; // eax
  __int64 v17; // r8
  int v18; // ebx
  WCHAR *Heap; // rdi
  int v20; // eax
  int v21; // r14d
  HANDLE NamedLocaleHashNode; // rcx
  DWORD v23; // ebx
  __int64 j; // rdx
  unsigned int *v25; // rax
  __int64 v26; // r8
  DWORD v27; // ebx
  _WORD *v28; // rcx
  __int64 v29; // rax
  DWORD v30; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v33; // r8
  DWORD v34; // ebx
  _WORD *v35; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  __int64 v37; // rcx
  __int64 v38; // rbx
  __int64 v39; // rsi
  __int16 *v40; // rbx
  int v41; // ebx
  __int64 v43; // rax
  bool v44; // zf
  __int64 v45; // rax
  DWORD v46; // ecx
  __int64 SortNode; // rax
  __int64 v48; // rdx
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v51; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v53; // rbx
  NTSTATUS v54; // esi
  HANDLE v55; // rbx
  __int64 v56; // rbx
  __int64 v57; // rax
  DWORD v58; // ebx
  __int64 k; // rdx
  unsigned int *v60; // rax
  __int64 v61; // r8
  DWORD v62; // ebx
  _WORD *v63; // rcx
  __int64 v64; // rax
  HANDLE *NlsCache; // rbx
  __int64 v66; // rdx
  __int64 v67; // rdx
  int v68; // eax
  int GlobalizationUserModelType; // eax
  int v70; // eax
  __int64 v71; // rcx
  WCHAR *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  const WCHAR *v75; // rcx
  WCHAR *v76; // rdx
  __int64 v77; // r9
  WCHAR *v78; // rcx
  __int64 v79; // rdx
  int v80; // ecx
  int v81; // r15d
  _DWORD *v82; // rax
  __int64 LocaleHashNode; // r14
  int v84; // eax
  __int64 NlsTebCache; // rax
  HANDLE *v86; // rax
  NTSTATUS v87; // ebx
  HANDLE v88; // rcx
  void *v89; // rbx
  unsigned int *v90; // rcx
  __int64 v91; // r8
  _WORD *v92; // rcx
  __int64 TransientLocale; // rax
  unsigned __int64 v94; // r12
  int v95; // r14d
  wchar_t *v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rcx
  const WCHAR *v99; // r9
  __int64 v100; // r8
  wchar_t *v101; // rax
  wchar_t *v102; // rcx
  __int64 v103; // rax
  UINT CodePage[2]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Disposition; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v106; // [rsp+5Ch] [rbp-A4h]
  unsigned int v107; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle[2]; // [rsp+68h] [rbp-98h] BYREF
  UINT v109; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int64 v111; // [rsp+90h] [rbp-70h]
  __int64 v112; // [rsp+98h] [rbp-68h]
  __int64 v113; // [rsp+A0h] [rbp-60h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR WideCharStr[128]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR P[128]; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t ApiMessage[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  PVOID CapturedData; // [rsp+320h] [rbp+220h] BYREF
  int v119; // [rsp+328h] [rbp+228h]
  wchar_t pszDest[512]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v6 = cchCount1;
  v106 = dwCmpFlags;
  v8 = dwCmpFlags;
  v9 = Locale;
  Disposition = cchCount1 < 0 && cchCount2 < 0;
  v109 = 0;
  if ( (dwCmpFlags & 0x60000000) != 0 )
    goto LABEL_257;
  if ( Locale == 1033 || Locale == 127 )
  {
    v10 = dword_1803A6B50;
    CodePage[0] = dword_1803A6B50;
    if ( !dword_1803A6B50 )
    {
      v10 = 1252;
      CodePage[0] = 1252;
      if ( gAnsiCodePage != 1252 && gOemCodePage != 1252 && (unsigned int)IsCPHashNodeLoaded(1252) != 1 )
      {
        if ( !(unsigned int)GetCPFileNameFromRegistry(1252, ApiMessage, 64) )
          goto LABEL_323;
        v94 = (unsigned __int16)qword_1803AAD58;
        v95 = (unsigned __int16)qword_1803AAD58 >> 1;
        if ( (unsigned __int64)(unsigned __int16)qword_1803AAD58 + 2 <= 0x400 )
        {
          memcpy_0(pszDest, Src, (unsigned __int16)qword_1803AAD58);
          pszDest[v94 >> 1] = 0;
        }
        else
        {
          ++v95;
        }
        if ( !v95 )
          goto LABEL_323;
        v96 = pszDest;
        v97 = 512;
        do
        {
          if ( !*v96 )
            break;
          ++v96;
          --v97;
        }
        while ( v97 );
        v98 = 512 - v97;
        if ( !v97 )
          goto LABEL_323;
        v99 = L"\\";
        v100 = 2147483646;
        v101 = &pszDest[v98];
        if ( v98 != 512 )
        {
          do
          {
            if ( !v100 )
              break;
            if ( !*v99 )
              break;
            *v101++ = *v99++;
            --v100;
            --v97;
          }
          while ( v97 );
        }
        v102 = v101 - 1;
        if ( v97 )
          v102 = v101;
        *v102 = 0;
        if ( !v97 || StringCchCatW(pszDest, 0x200u, ApiMessage) < 0 || GetFileAttributesW(pszDest) == -1 )
        {
LABEL_323:
          v10 = 65001;
          CodePage[0] = 65001;
          dword_1803A6B50 = 65001;
          goto LABEL_7;
        }
        v10 = CodePage[0];
      }
      dword_1803A6B50 = v10;
    }
LABEL_7:
    v8 = v106;
    v11 = 87;
    goto LABEL_8;
  }
  if ( Locale == 2048 )
  {
LABEL_257:
    v11 = 87;
LABEL_238:
    v10 = gAnsiCodePage;
    CodePage[0] = gAnsiCodePage;
    goto LABEL_8;
  }
  v82 = CheckSpecialLocales(Locale);
  v11 = 87;
  if ( !v82 )
  {
    LocaleHashNode = *((_QWORD *)::P + (((unsigned __int8)v9 ^ (unsigned __int8)((v9 ^ (v9 >> 7)) >> 7)) & 0x7F));
    if ( LocaleHashNode )
    {
      while ( *(_DWORD *)LocaleHashNode != (_DWORD)v9 )
      {
        LocaleHashNode = *(_QWORD *)(LocaleHashNode + 88);
        if ( !LocaleHashNode )
          goto LABEL_273;
      }
    }
    else
    {
LABEL_273:
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      LocaleHashNode = FindLocaleHashNode((unsigned int)v9);
      if ( !LocaleHashNode )
        LocaleHashNode = MakeLocHashNode();
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    }
    if ( (!LocaleHashNode || (v82 = *(_DWORD **)(LocaleHashNode + 104)) == 0)
      && (!(unsigned int)IsUnspecifiedLcid((unsigned int)v9) || (v82 = GetCurrentNlsCache()[2]) == 0) )
    {
      SetLastError_0(0x57u);
      goto LABEL_263;
    }
  }
  if ( !(unsigned int)GetLocaleInfoHelper(v82, 2684358660LL, &v109, 2) )
  {
LABEL_263:
    SetLastError_0(0x57u);
    SetLastError_0(0x57u);
    return 0;
  }
  v10 = v109;
  v8 = v106;
  CodePage[0] = v109;
  if ( !v109 )
    goto LABEL_238;
LABEL_8:
  if ( !v10 || !lpString1 || !lpString2 )
    goto LABEL_89;
  if ( (v8 & 0xA7FCEFC8) != 0 )
  {
    SetLastError_0(0x3ECu);
    return 0;
  }
  v12 = -1;
  v113 = -1;
  if ( v6 < 0 )
  {
    v43 = -1;
    do
      v44 = lpString1[++v43] == 0;
    while ( !v44 );
    v6 = v43 + 1;
    if ( (unsigned __int64)(v43 + 1) > 0x7FFFFFFF )
      goto LABEL_89;
  }
  v13 = 127;
  LODWORD(Handle[0]) = 127;
  if ( v6 > 127 )
  {
    lpWideCharStr = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v6 + 1));
    if ( !lpWideCharStr )
    {
      v11 = 14;
      goto LABEL_89;
    }
    cchWideChar = v6;
LABEL_16:
    v16 = MultiByteToWideChar(CodePage[0], 0, lpString1, v6, lpWideCharStr, cchWideChar);
    v17 = v16;
    v107 = v16;
    if ( v16 && v16 <= cchWideChar )
    {
      v10 = CodePage[0];
      lpWideCharStr[v16] = 0;
      v12 = -1;
      v13 = 127;
      goto LABEL_19;
    }
    if ( lpWideCharStr != WideCharStr && lpWideCharStr )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpWideCharStr);
    v11 = 87;
LABEL_89:
    SetLastError_0(v11);
    return 0;
  }
  lpWideCharStr = WideCharStr;
  if ( v6 )
  {
    cchWideChar = 127;
    goto LABEL_16;
  }
  v17 = 0;
  WideCharStr[0] = 0;
  v107 = 0;
LABEL_19:
  if ( cchCount2 < 0 )
  {
    v45 = -1;
    do
      v44 = lpString2[++v45] == 0;
    while ( !v44 );
    v18 = v45 + 1;
    if ( (unsigned __int64)(v45 + 1) > 0x7FFFFFFF )
    {
      v46 = 87;
      goto LABEL_338;
    }
  }
  else
  {
    v18 = cchCount2;
  }
  if ( v18 > 127 )
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v18 + 1));
    if ( Heap )
    {
      v13 = v18;
      LODWORD(Handle[0]) = v18;
LABEL_23:
      v20 = MultiByteToWideChar(v10, 0, lpString2, v18, Heap, v13);
      v21 = v20;
      if ( v20 && v20 <= SLODWORD(Handle[0]) )
      {
        v17 = v107;
        Heap[v20] = 0;
        v12 = v20;
        goto LABEL_26;
      }
      if ( Heap != P && Heap )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v46 = 87;
      goto LABEL_338;
    }
    v46 = 14;
LABEL_338:
    SetLastError_0(v46);
    if ( lpWideCharStr != WideCharStr && lpWideCharStr )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpWideCharStr);
      return 0;
    }
    return 0;
  }
  Heap = P;
  if ( v18 )
    goto LABEL_23;
  P[0] = 0;
  v21 = 0;
LABEL_26:
  if ( Disposition )
    v21 = -1;
  else
    LODWORD(v113) = v17;
  if ( (_DWORD)v9 == 127 )
  {
    NamedLocaleHashNode = (HANDLE)gpInvLocHashN;
    goto LABEL_72;
  }
  if ( (unsigned int)v9 > 0xC00 )
  {
    if ( (_DWORD)v9 == 4096 )
    {
      NamedLocaleHashNode = (HANDLE)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        goto LABEL_77;
    }
    else if ( (_DWORD)v9 != 5120 )
    {
      goto LABEL_54;
    }
    Handle[0] = (HANDLE)11141120;
    Handle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName((unsigned int)v9, Handle, 0, 0) >= 0 )
    {
      NamedLocaleHashNode = (HANDLE)GetNamedLocaleHashNode(Handle[1], 0);
      if ( NamedLocaleHashNode )
        goto LABEL_77;
    }
LABEL_54:
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_71:
      if ( (_DWORD)v9 != *(_DWORD *)NamedLocaleHashNode )
        goto LABEL_73;
      goto LABEL_72;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_70;
    v30 = gSystemLocale;
    for ( i = *((_QWORD *)::P
              + (((unsigned __int8)gSystemLocale
                ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
               & 0x7F)); i; i = *(_QWORD *)(i + 88) )
    {
      if ( *(_DWORD *)i == gSystemLocale )
        break;
    }
    gpSysLocHashN = i;
    if ( i )
      goto LABEL_70;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_158;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v30 != 127 )
      {
        v34 = HIWORD(v30);
        if ( (v34 & 0xF) == 0 )
        {
          v35 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_66:
          LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v35, 0);
          goto LABEL_67;
        }
        v66 = WindowsLocaleData[54];
        v35 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v66 )
          v35 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v66 + 2LL * (v34 & 0xF)) - 2)
                        + 2);
        if ( v35 && *v35 )
          goto LABEL_66;
LABEL_158:
        gpSysLocHashN = 0;
LABEL_68:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_70;
      }
      LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v30, v33, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_158;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        LocHashNodeFromSystemLocale = FindLocaleHashNode(v30);
      }
      else
      {
        LocHashNodeFromSystemLocale = 0;
      }
    }
LABEL_67:
    gpSysLocHashN = LocHashNodeFromSystemLocale;
    if ( !LocHashNodeFromSystemLocale )
      goto LABEL_68;
LABEL_70:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    goto LABEL_71;
  }
  if ( (_DWORD)v9 != 3072 && (_DWORD)v9 && (_DWORD)v9 != 1024 )
  {
    if ( (_DWORD)v9 == 2048 )
    {
      NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
      if ( gpSysLocHashN )
        goto LABEL_77;
      if ( BasepIsSecureProcess )
        goto LABEL_72;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_50;
      v23 = gSystemLocale;
      for ( j = *((_QWORD *)::P
                + (((unsigned __int8)gSystemLocale
                  ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                 & 0x7F)); j; j = *(_QWORD *)(j + 88) )
      {
        if ( *(_DWORD *)j == gSystemLocale )
          break;
      }
      gpSysLocHashN = j;
      if ( j )
        goto LABEL_50;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_183;
      v25 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v25 )
      {
        if ( (_WORD)v23 != 127 )
        {
          v27 = HIWORD(v23);
          if ( (v27 & 0xF) == 0 )
          {
            v28 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v25);
LABEL_46:
            v29 = MakeNamedLocaleHashNode(v28, 0);
            goto LABEL_47;
          }
          v67 = v25[54];
          v28 = (_WORD *)qword_1803A6BD0;
          if ( (_DWORD)v67 )
            v28 = (_WORD *)(qword_1803A6BD0
                          + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v67 + 2LL * (v27 & 0xF)) - 2)
                          + 2);
          if ( v28 && *v28 )
            goto LABEL_46;
LABEL_183:
          gpSysLocHashN = 0;
          goto LABEL_48;
        }
        v29 = MakeLocHashNodeFromSystemLocale(v25, v23, v26, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_183;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          v29 = FindLocaleHashNode(v23);
        }
        else
        {
          v29 = 0;
        }
      }
LABEL_47:
      gpSysLocHashN = v29;
      if ( v29 )
      {
LABEL_50:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
        goto LABEL_72;
      }
LABEL_48:
      gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
      if ( !gpSysLocHashN )
        gpSysLocHashN = gpInvLocHashN;
      goto LABEL_50;
    }
    goto LABEL_54;
  }
  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  if ( !(_DWORD)IsImpersonating )
  {
    IsInteractiveUserProcess = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
      IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, v12, v17);
    if ( !IsInteractiveUserProcess )
    {
      NlsCheckStaleCache();
      goto LABEL_152;
    }
    if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803AC296 = 1;
    if ( !word_1803AC296 )
      goto LABEL_152;
    v51 = word_1803AC294;
    if ( word_1803AC294 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v51 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        if ( !word_1803AC296 )
          goto LABEL_151;
        v51 = word_1803AC294;
      }
    }
    word_1803AC296 = 2;
    if ( v51 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v53 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v119 = 1660;
        v54 = CsrClientCallServer(ApiMessage, v53, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v54 >= 0 )
          memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v53);
      }
      else
      {
        v54 = -1073741801;
      }
      if ( word_1803AC294 == 1 && v54 >= 0 )
      {
LABEL_127:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
        }
        else
        {
          v56 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
          if ( !v56 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803ABC10 )
          {
LABEL_150:
            _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
            if ( word_1803AC294 != 3 )
LABEL_151:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_152:
            NlsCache = &gNlsProcessLocalCache;
LABEL_153:
            NamedLocaleHashNode = NlsCache[2];
            goto LABEL_72;
          }
        }
        v57 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_149:
          qword_1803ABC10 = v57;
          goto LABEL_150;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_148;
        v58 = gSystemLocale;
        for ( k = *((_QWORD *)::P
                  + (((unsigned __int8)gSystemLocale
                    ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                   & 0x7F)); k; k = *(_QWORD *)(k + 88) )
        {
          if ( *(_DWORD *)k == gSystemLocale )
            break;
        }
        gpSysLocHashN = k;
        if ( k )
          goto LABEL_148;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_218;
        v60 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v60 )
        {
          if ( (_WORD)v58 != 127 )
          {
            v62 = HIWORD(v58);
            if ( (v62 & 0xF) == 0 )
            {
              v63 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v60);
LABEL_144:
              v64 = MakeNamedLocaleHashNode(v63, 0);
              goto LABEL_145;
            }
            v79 = v60[54];
            v63 = (_WORD *)qword_1803A6BD0;
            if ( (_DWORD)v79 )
              v63 = (_WORD *)(qword_1803A6BD0
                            + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v79 + 2LL * (v62 & 0xF)) - 2)
                            + 2);
            if ( v63 && *v63 )
              goto LABEL_144;
LABEL_218:
            gpSysLocHashN = 0;
LABEL_146:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_148;
          }
          v64 = MakeLocHashNodeFromSystemLocale(v60, v58, v61, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_218;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            v64 = FindLocaleHashNode(v58);
          }
          else
          {
            v64 = 0;
          }
        }
LABEL_145:
        gpSysLocHashN = v64;
        if ( !v64 )
          goto LABEL_146;
LABEL_148:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v57 = gpSysLocHashN;
        goto LABEL_149;
      }
    }
    Handle[0] = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle[0] = gNlsProcessLocalCache;
LABEL_124:
      v55 = Handle[0];
      NlsUpdateCacheInfo(&word_1803ABC18, Handle[0], 1);
      if ( word_1803AC294 == 3 && v55 )
        NtClose(v55);
      goto LABEL_127;
    }
    *(_QWORD *)CodePage = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, v12, v17);
    if ( GlobalizationUserModelType == 1 )
    {
      v70 = RtlOpenCurrentUser(0x2000000u, (PHANDLE)CodePage);
    }
    else
    {
      v84 = GlobalizationUserModelType - 2;
      if ( v84 )
      {
        if ( v84 != 1 )
        {
LABEL_213:
          SetLastError_0(0x3F1u);
          goto LABEL_124;
        }
        v107 = 0;
        v70 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, (PHANDLE)CodePage, &v107);
      }
      else
      {
        v70 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, (PHANDLE)CodePage);
      }
    }
    if ( v70 >= 0 )
    {
      ApiMessage[0] = 0;
      v71 = 512;
      v72 = ApiMessage;
      do
      {
        if ( !*v72 )
          break;
        ++v72;
        --v71;
      }
      while ( v71 );
      v73 = 512 - v71;
      if ( !v71 )
        goto LABEL_211;
      v74 = v71;
      v75 = L"Control Panel\\International";
      v76 = &ApiMessage[v73];
      v77 = 2147483646;
      do
      {
        if ( !v77 )
          break;
        if ( !*v75 )
          break;
        *v76++ = *v75++;
        --v77;
        --v74;
      }
      while ( v74 );
      v78 = v76 - 1;
      if ( v74 )
        v78 = v76;
      *v78 = 0;
      if ( v74 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = *(HANDLE *)CodePage;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v87 = NtOpenKey(Handle, 0x20019u, &ObjectAttributes);
        if ( v87 < 0 )
          v87 = NtCreateKey(Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( *(_QWORD *)CodePage )
          NtClose(*(HANDLE *)CodePage);
        if ( v87 >= 0 )
        {
          v88 = Handle[0];
        }
        else
        {
          v88 = 0;
          Handle[0] = 0;
        }
        if ( v87 >= 0 )
        {
          v89 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v88,
                          0);
          if ( v89 )
          {
            if ( Handle[0] )
              NtClose(Handle[0]);
            Handle[0] = v89;
          }
          goto LABEL_124;
        }
      }
      else
      {
LABEL_211:
        if ( *(_QWORD *)CodePage )
          NtClose(*(HANDLE *)CodePage);
      }
    }
    goto LABEL_213;
  }
  NlsCache = 0;
  v80 = IsImpersonating - 1;
  if ( v80 )
  {
    if ( v80 != 1 )
      goto LABEL_153;
    if ( BasepIsSecureProcess )
      goto LABEL_152;
    v81 = 0;
    NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
    if ( !NlsCache )
    {
      v86 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
      NlsCache = v86;
      LOWORD(v80) = 1;
      if ( v86 )
      {
        *v86 = 0;
        v86[1] = 0;
        v86[2] = 0;
        v81 = 1;
        *((_WORD *)v86 + 842) = 3;
        *((_WORD *)v86 + 843) = 1;
      }
      else
      {
        NlsCache = &gNlsProcessLocalCache;
      }
      NtCurrentTeb()->NlsCache = NlsCache;
    }
    if ( NlsCache == &gNlsProcessLocalCache || !v81 && *((_WORD *)NlsCache + 843) != 1 )
      goto LABEL_153;
    *((_WORD *)NlsCache + 843) = v80;
    UpdateNlsInfoCache(NlsCache, 0);
    NamedLocaleHashNode = NlsCache[2];
  }
  else
  {
    NlsTebCache = GetNlsTebCache(1, v12, v17);
    NtCurrentTeb()->IsImpersonating = 2;
    NamedLocaleHashNode = *(HANDLE *)(NlsTebCache + 16);
  }
LABEL_72:
  if ( NamedLocaleHashNode )
    goto LABEL_77;
LABEL_73:
  v37 = ((unsigned __int8)v9 ^ (unsigned __int8)((v9 ^ (v9 >> 7)) >> 7)) & 0x7F;
  v38 = *((_QWORD *)::P + v37);
  v39 = 8 * v37;
  if ( v38 )
  {
    while ( *(_DWORD *)v38 != (_DWORD)v9 )
    {
      v38 = *(_QWORD *)(v38 + 88);
      if ( !v38 )
        goto LABEL_160;
    }
    goto LABEL_75;
  }
LABEL_160:
  RtlAcquireSRWLockExclusive(&gTblPtrsLock);
  v38 = *(_QWORD *)((char *)::P + v39);
  if ( v38 )
  {
    while ( *(_DWORD *)v38 != (_DWORD)v9 )
    {
      v38 = *(_QWORD *)(v38 + 88);
      if ( !v38 )
        goto LABEL_298;
    }
    goto LABEL_162;
  }
LABEL_298:
  if ( (v9 & 0xFFF00000) != 0 || BasepIsSecureProcess )
    goto LABEL_329;
  v90 = (unsigned int *)GetWindowsLocaleData((unsigned int)v9);
  if ( !v90 )
  {
    if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
    {
      TransientLocale = GetTransientLocale((unsigned int)v9);
      goto LABEL_305;
    }
    goto LABEL_329;
  }
  if ( (_WORD)v9 == 127 )
  {
    v38 = MakeLocHashNodeFromSystemLocale(v90, (unsigned int)v9, v91, 0);
    goto LABEL_162;
  }
  if ( (v9 & 0xF0000) != 0 )
  {
    v103 = v90[54];
    v92 = (_WORD *)qword_1803A6BD0;
    if ( (_DWORD)v103 )
      v92 = (_WORD *)(qword_1803A6BD0
                    + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v103 + 2LL * (BYTE2(v9) & 0xF)) - 2)
                    + 2);
    if ( v92 && *v92 )
      goto LABEL_304;
LABEL_329:
    v38 = 0;
    goto LABEL_162;
  }
  v92 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v90);
LABEL_304:
  TransientLocale = MakeNamedLocaleHashNode(v92, 0);
LABEL_305:
  v38 = TransientLocale;
LABEL_162:
  RtlReleaseSRWLockExclusive(&gTblPtrsLock);
LABEL_75:
  if ( v38 )
  {
    NamedLocaleHashNode = *(HANDLE *)(v38 + 104);
    if ( NamedLocaleHashNode )
      goto LABEL_77;
  }
  else
  {
    NamedLocaleHashNode = 0;
  }
  if ( (_DWORD)v9 == 4096 || (v9 & 0x3FF) == 0 && (unsigned int)(v9 - 0x2000) <= 0x2C00 )
    NamedLocaleHashNode = GetCurrentNlsCache()[2];
  if ( !NamedLocaleHashNode )
    goto LABEL_78;
LABEL_77:
  v40 = (__int16 *)*((_QWORD *)NamedLocaleHashNode + 4);
  if ( !v40 )
    goto LABEL_78;
  if ( !g_definedDefaultSortVersion )
  {
    *(_QWORD *)&DestinationString.Length = 32;
    DestinationString.Buffer = 0;
    v111 = 0;
    v112 = 0;
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( !g_definedDefaultSortVersion )
    {
      if ( (unsigned int)QueryRegDefaultSortingVersion(&DestinationString)
        && (unsigned int)QueryRegSortVersionDll(&DestinationString, 0, 0) )
      {
        v68 = *(_DWORD *)(&DestinationString.MaximumLength + 1);
      }
      else
      {
        v68 = 256;
      }
      dword_1803A52B4 = v68 | 0xFF;
      dword_1803A52B8 = v68 | 0xFF;
      _InterlockedExchange(&g_definedDefaultSortVersion, 1);
    }
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
  }
  SortNode = GetSortNode(v40, (__int64)g_defaultSortVersion, 0);
  if ( !SortNode )
  {
LABEL_78:
    SetLastError_0(0x57u);
    v41 = 0;
    goto LABEL_79;
  }
  v48 = v106;
  LODWORD(v48) = v106 ^ 0x8000000;
  v41 = (*(__int64 (__fastcall **)(__int64, __int64, WCHAR *, _QWORD, WCHAR *, int, _QWORD, _QWORD))(SortNode + 240))(
          SortNode,
          v48,
          lpWideCharStr,
          (unsigned int)v113,
          Heap,
          v21,
          0,
          0);
LABEL_79:
  if ( lpWideCharStr != WideCharStr && lpWideCharStr )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpWideCharStr);
  if ( Heap != P )
  {
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  return v41;
}

```

## disassembly

```asm
0x18001cd50  push    rbp
0x18001cd52  push    rbx
0x18001cd53  push    rsi
0x18001cd54  push    rdi
0x18001cd55  push    r13
0x18001cd57  push    r15
0x18001cd59  lea     rbp, [rsp-0A08h]
0x18001cd61  sub     rsp, 0B08h
0x18001cd68  mov     rax, cs:__security_cookie
0x18001cd6f  xor     rax, rsp
0x18001cd72  mov     [rbp+0A30h+var_50], rax
0x18001cd79  mov     r15, [rbp+0A30h+lpString2]
0x18001cd80  mov     edi, r9d
0x18001cd83  mov     esi, [rbp+0A30h+cchCount2]
0x18001cd89  mov     rbx, r8
0x18001cd8c  mov     [rsp+0B30h+var_AD4], edx
0x18001cd90  mov     eax, edx
0x18001cd92  mov     r13d, ecx
0x18001cd95  test    r9d, r9d
0x18001cd98  jns     loc_18001D07A
0x18001cd9e  test    esi, esi
0x18001cda0  jns     loc_18001D07A
0x18001cda6  mov     [rsp+0B30h+var_AD8], 1
0x18001cdae  mov     [rsp+0B30h+var_30], r12
0x18001cdb6  mov     [rsp+0B30h+var_38], r14
0x18001cdbe  mov     [rsp+0B30h+var_AB8], 0
0x18001cdc6  test    eax, 60000000h
0x18001cdcb  jnz     loc_18001DD11
0x18001cdd1  cmp     r13d, 409h
0x18001cdd8  jnz     loc_18001DB84
0x18001cdde  mov     r14d, cs:dword_1803A6B50
0x18001cde5  mov     [rsp+0B30h+CodePage], r14d
0x18001cdea  test    r14d, r14d
0x18001cded  jz      loc_18001DC7D
0x18001cdf3  mov     eax, [rsp+0B30h+var_AD4]
0x18001cdf7  mov     r12d, 57h ; 'W'
0x18001cdfd  test    r14d, r14d
0x18001ce00  jz      loc_18001D2BC
0x18001ce06  test    rbx, rbx
0x18001ce09  jz      loc_18001D2BC
0x18001ce0f  test    r15, r15
0x18001ce12  jz      loc_18001D2BC
0x18001ce18  test    eax, 0A7FCEFC8h
0x18001ce1d  jnz     loc_18001D356
0x18001ce23  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18001ce2a  mov     [rbp+0A30h+var_A90], rdx
0x18001ce2e  test    edi, edi
0x18001ce30  js      loc_18001D284
0x18001ce36  mov     ecx, 7Fh
0x18001ce3b  mov     dword ptr [rsp+0B30h+Handle], ecx
0x18001ce3f  cmp     edi, ecx
0x18001ce41  jg      loc_18001E2B1
0x18001ce47  lea     r12, [rbp+0A30h+WideCharStr]
0x18001ce4b  test    edi, edi
0x18001ce4d  jz      loc_18001D332
0x18001ce53  mov     r14d, ecx
0x18001ce56  mov     ecx, [rsp+0B30h+CodePage]; CodePage
0x18001ce5a  mov     r9d, edi; cbMultiByte
0x18001ce5d  mov     [rsp+0B30h+cchWideChar], r14d; cchWideChar
0x18001ce62  mov     r8, rbx; lpMultiByteStr
0x18001ce65  xor     edx, edx; dwFlags
0x18001ce67  mov     [rsp+0B30h+lpWideCharStr], r12; lpWideCharStr
0x18001ce6c  call    MultiByteToWideChar
0x18001ce71  movsxd  r8, eax
0x18001ce74  mov     [rsp+0B30h+var_AD0], r8d
0x18001ce79  test    eax, eax
0x18001ce7b  jz      loc_18001D324
0x18001ce81  cmp     r8d, r14d
0x18001ce84  jg      loc_18001D324
0x18001ce8a  mov     r14d, [rsp+0B30h+CodePage]
0x18001ce8f  xor     ecx, ecx
0x18001ce91  mov     [r12+r8*2], cx
0x18001ce96  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18001ce9d  mov     ecx, 7Fh
0x18001cea2  test    esi, esi
0x18001cea4  js      loc_18001D2C8
0x18001ceaa  mov     ebx, esi
0x18001ceac  cmp     ebx, 7Fh
0x18001ceaf  jg      loc_18001E2EA
0x18001ceb5  lea     rdi, [rbp+0A30h+P]
0x18001cebc  test    ebx, ebx
0x18001cebe  jz      loc_18001D345
0x18001cec4  mov     [rsp+0B30h+cchWideChar], ecx; cchWideChar
0x18001cec8  mov     r9d, ebx; cbMultiByte
0x18001cecb  mov     ecx, r14d; CodePage
0x18001cece  mov     [rsp+0B30h+lpWideCharStr], rdi; lpWideCharStr
0x18001ced3  mov     r8, r15; lpMultiByteStr
0x18001ced6  xor     edx, edx; dwFlags
0x18001ced8  call    MultiByteToWideChar
0x18001cedd  movsxd  r14, eax
0x18001cee0  test    eax, eax
0x18001cee2  jz      loc_18001D316
0x18001cee8  cmp     r14d, dword ptr [rsp+0B30h+Handle]
0x18001ceed  jg      loc_18001D316
0x18001cef3  mov     r8d, [rsp+0B30h+var_AD0]
0x18001cef8  xor     ecx, ecx
0x18001cefa  mov     [rdi+r14*2], cx
0x18001ceff  mov     rdx, r14
0x18001cf02  cmp     [rsp+0B30h+var_AD8], 0
0x18001cf07  jz      loc_18001D766
0x18001cf0d  mov     r14d, 0FFFFFFFFh
0x18001cf13  cmp     r13d, 7Fh
0x18001cf17  jz      loc_18001D2F7
0x18001cf1d  cmp     r13d, 0C00h
0x18001cf24  ja      loc_18001D087
0x18001cf2a  jz      loc_18001D3D0
0x18001cf30  test    r13d, r13d
0x18001cf33  jz      loc_18001D3D0
0x18001cf39  cmp     r13d, 400h
0x18001cf40  jz      loc_18001D3D0
0x18001cf46  cmp     r13d, 800h
0x18001cf4d  jnz     loc_18001D0A1
0x18001cf53  mov     rcx, cs:gpSysLocHashN
0x18001cf5a  test    rcx, rcx
0x18001cf5d  jnz     loc_18001D21C
0x18001cf63  cmp     cs:BasepIsSecureProcess, cl
0x18001cf69  jnz     loc_18001D1C8
0x18001cf6f  lea     rcx, gTblPtrsLock
0x18001cf76  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001cf7d  nop     dword ptr [rax+rax+00h]
0x18001cf82  cmp     cs:gpSysLocHashN, 0
0x18001cf8a  jnz     loc_18001D05B
0x18001cf90  mov     ebx, cs:gSystemLocale
0x18001cf96  mov     rax, cs:P
0x18001cf9d  mov     ecx, ebx
0x18001cf9f  shr     rcx, 7
0x18001cfa3  xor     rcx, rbx
0x18001cfa6  shr     rcx, 7
0x18001cfaa  xor     rcx, rbx
0x18001cfad  and     ecx, 7Fh
0x18001cfb0  mov     rdx, [rax+rcx*8]
0x18001cfb4  test    rdx, rdx
0x18001cfb7  jz      short loc_18001CFC1
0x18001cfb9  cmp     [rdx], ebx
0x18001cfbb  jnz     loc_18001DC3D
0x18001cfc1  mov     cs:gpSysLocHashN, rdx
0x18001cfc8  test    rdx, rdx
0x18001cfcb  jnz     loc_18001D05B
0x18001cfd1  test    ebx, 0FFF00000h
0x18001cfd7  jnz     loc_18001D8A9
0x18001cfdd  cmp     cs:BasepIsSecureProcess, dl
0x18001cfe3  jnz     loc_18001D8A9
0x18001cfe9  mov     ecx, ebx
0x18001cfeb  call    GetWindowsLocaleData
0x18001cff0  test    rax, rax
0x18001cff3  jz      loc_18001DC4F
0x18001cff9  cmp     bx, 7Fh
0x18001cffd  jz      loc_18001DCD1
0x18001d003  shr     ebx, 10h
0x18001d006  test    bl, 0Fh
0x18001d009  jnz     loc_18001D876
0x18001d00f  mov     ecx, [rax]
0x18001d011  mov     rax, cs:qword_1803A6BD0
0x18001d018  add     rax, 2
0x18001d01c  lea     rcx, [rax+rcx*2]
0x18001d020  xor     edx, edx
0x18001d022  call    MakeNamedLocaleHashNode
0x18001d027  mov     cs:gpSysLocHashN, rax
0x18001d02e  test    rax, rax
0x18001d031  jnz     short loc_18001D05B
0x18001d033  xor     edx, edx
0x18001d035  lea     rcx, aEnUs; "en-US"
0x18001d03c  call    MakeNamedLocaleHashNode
0x18001d041  mov     cs:gpSysLocHashN, rax
0x18001d048  test    rax, rax
0x18001d04b  jnz     short loc_18001D05B
0x18001d04d  mov     rax, cs:gpInvLocHashN
0x18001d054  mov     cs:gpSysLocHashN, rax
0x18001d05b  lea     rcx, gTblPtrsLock
0x18001d062  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001d069  nop     dword ptr [rax+rax+00h]
0x18001d06e  mov     rcx, cs:gpSysLocHashN
0x18001d075  jmp     loc_18001D1C8
0x18001d07a  mov     [rsp+0B30h+var_AD8], 0
0x18001d082  jmp     loc_18001CDAE
0x18001d087  cmp     r13d, 1000h
0x18001d08e  jz      loc_18001DDD3
0x18001d094  cmp     r13d, 1400h
0x18001d09b  jz      loc_18001DDE3
0x18001d0a1  mov     rcx, cs:gpSysLocHashN
0x18001d0a8  test    rcx, rcx
0x18001d0ab  jnz     loc_18001D1C3
0x18001d0b1  cmp     cs:BasepIsSecureProcess, cl
0x18001d0b7  jnz     loc_18001D1C3
0x18001d0bd  lea     rcx, gTblPtrsLock
0x18001d0c4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001d0cb  nop     dword ptr [rax+rax+00h]
0x18001d0d0  cmp     cs:gpSysLocHashN, 0
0x18001d0d8  jnz     loc_18001D1A9
0x18001d0de  mov     ebx, cs:gSystemLocale
0x18001d0e4  mov     rax, cs:P
0x18001d0eb  mov     ecx, ebx
0x18001d0ed  shr     rcx, 7
0x18001d0f1  xor     rcx, rbx
0x18001d0f4  shr     rcx, 7
0x18001d0f8  xor     rcx, rbx
0x18001d0fb  and     ecx, 7Fh
0x18001d0fe  mov     rdx, [rax+rcx*8]
0x18001d102  test    rdx, rdx
0x18001d105  jz      short loc_18001D10F
0x18001d107  cmp     [rdx], ebx
0x18001d109  jnz     loc_18001D780
0x18001d10f  mov     cs:gpSysLocHashN, rdx
0x18001d116  test    rdx, rdx
0x18001d119  jnz     loc_18001D1A9
0x18001d11f  test    ebx, 0FFF00000h
0x18001d125  jnz     loc_18001D701
0x18001d12b  cmp     cs:BasepIsSecureProcess, dl
0x18001d131  jnz     loc_18001D701
0x18001d137  mov     ecx, ebx
0x18001d139  call    GetWindowsLocaleData
0x18001d13e  test    rax, rax
0x18001d141  jz      loc_18001D848
0x18001d147  cmp     bx, 7Fh
0x18001d14b  jz      loc_18001D98B
0x18001d151  shr     ebx, 10h
0x18001d154  test    bl, 0Fh
0x18001d157  jnz     loc_18001D6CE
0x18001d15d  mov     ecx, [rax]
0x18001d15f  mov     rax, cs:qword_1803A6BD0
0x18001d166  add     rax, 2
0x18001d16a  lea     rcx, [rax+rcx*2]
0x18001d16e  xor     edx, edx
0x18001d170  call    MakeNamedLocaleHashNode
0x18001d175  mov     cs:gpSysLocHashN, rax
0x18001d17c  test    rax, rax
0x18001d17f  jnz     short loc_18001D1A9
0x18001d181  xor     edx, edx
0x18001d183  lea     rcx, aEnUs; "en-US"
0x18001d18a  call    MakeNamedLocaleHashNode
0x18001d18f  mov     cs:gpSysLocHashN, rax
0x18001d196  test    rax, rax
0x18001d199  jnz     short loc_18001D1A9
0x18001d19b  mov     rax, cs:gpInvLocHashN
0x18001d1a2  mov     cs:gpSysLocHashN, rax
0x18001d1a9  lea     rcx, gTblPtrsLock
0x18001d1b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001d1b7  nop     dword ptr [rax+rax+00h]
0x18001d1bc  mov     rcx, cs:gpSysLocHashN
0x18001d1c3  cmp     r13d, [rcx]
0x18001d1c6  jnz     short loc_18001D1CD
0x18001d1c8  test    rcx, rcx
0x18001d1cb  jnz     short loc_18001D21C
0x18001d1cd  mov     rax, cs:P
0x18001d1d4  mov     rcx, r13
0x18001d1d7  shr     rcx, 7
0x18001d1db  xor     rcx, r13
0x18001d1de  shr     rcx, 7
0x18001d1e2  xor     rcx, r13
0x18001d1e5  and     ecx, 7Fh
0x18001d1e8  mov     rbx, [rax+rcx*8]
0x18001d1ec  lea     rsi, ds:0[rcx*8]
0x18001d1f4  test    rbx, rbx
0x18001d1f7  jz      loc_18001D71E
0x18001d1fd  cmp     [rbx], r13d
0x18001d200  jnz     loc_18001D711
0x18001d206  test    rbx, rbx
0x18001d209  jz      loc_18001D951
0x18001d20f  mov     rcx, [rbx+68h]
0x18001d213  test    rcx, rcx
0x18001d216  jz      loc_18001D953
0x18001d21c  mov     rbx, [rcx+20h]
0x18001d220  test    rbx, rbx
0x18001d223  jnz     loc_18001D367
0x18001d229  mov     ecx, 57h ; 'W'; dwErrCode
0x18001d22e  call    SetLastError_0
0x18001d233  xor     ebx, ebx
0x18001d235  lea     rax, [rbp+0A30h+WideCharStr]
0x18001d239  cmp     r12, rax
0x18001d23c  jnz     loc_18001DF5B
0x18001d242  lea     rax, [rbp+0A30h+P]
0x18001d249  cmp     rdi, rax
0x18001d24c  jnz     loc_18001DF2F
0x18001d252  mov     eax, ebx
0x18001d254  mov     r14, [rsp+0B30h+var_38]
0x18001d25c  mov     r12, [rsp+0B30h+var_30]
0x18001d264  mov     rcx, [rbp+0A30h+var_50]
0x18001d26b  xor     rcx, rsp; StackCookie
0x18001d26e  call    __security_check_cookie
0x18001d273  add     rsp, 0B08h
0x18001d27a  pop     r15
0x18001d27c  pop     r13
0x18001d27e  pop     rdi
0x18001d27f  pop     rsi
0x18001d280  pop     rbx
0x18001d281  pop     rbp
0x18001d282  retn
0x18001d284  mov     rax, rdx
0x18001d287  nop     word ptr [rax+rax+00000000h]
0x18001d290  cmp     byte ptr [rbx+rax+1], 0
0x18001d295  lea     rax, [rax+1]
0x18001d299  jnz     short loc_18001D290
0x18001d29b  lea     rdi, [rax+1]
0x18001d29f  cmp     rdi, 7FFFFFFFh
0x18001d2a6  ja      short loc_18001D2BC
0x18001d2a8  jmp     loc_18001CE36
0x18001d2ad  test    r12, r12
0x18001d2b0  jnz     loc_18001E3A9
0x18001d2b6  mov     r12d, 57h ; 'W'
0x18001d2bc  mov     ecx, r12d; dwErrCode
  ... truncated ...
```
