# BCryptResolveProviders

- ea: `0x180025c00`
- end: `0x1800267c7`
- name: `BCryptResolveProviders`
- size: `3015`
- prototype: `NTSTATUS __stdcall(LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, LPCWSTR pszProvider, ULONG dwMode, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *ppBuffer)`
- caller_count: `6`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001770`
- `0x180023620`
- `0x18003a740`
- `0x180059380`
- `0x180059730`
- `0x18005d420`

## callees

- `0x180018e40`
- `0x180018f30`
- `0x1800244f0`
- `0x1800247e0`
- `0x180024d20`
- `0x180024dc0`
- `0x180025540`
- `0x180025810`
- `0x180025aa0`
- `0x180025c00`
- `0x1800267d0`
- `0x180027140`
- `0x180029048`
- `0x180036de8`
- `0x18003701c`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180025e26`
- `ntoskrnl!ExAllocatePool2` at `0x180025e26`
- `ntoskrnl!ExFreePoolWithTag` at `0x180025eed`
- `ntoskrnl!ExFreePoolWithTag` at `0x180025eed`
- `ntoskrnl!ZwClose` at `0x180025f5f`
- `ntoskrnl!ZwClose` at `0x180025f5f`
- `ntoskrnl!ObfDereferenceObject` at `0x180025f50`
- `ntoskrnl!ObfDereferenceObject` at `0x180025f50`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180025cc7`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180025cc7`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180025cdc`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180025cdc`
- `ntoskrnl!ZwOpenKey` at `0x180025eb8`
- `ntoskrnl!ZwOpenKey` at `0x180025eb8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025f7d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025fe0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180026598`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180026653`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025f7d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025fe0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180026598`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180026653`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800265ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180026666`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800265ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180026666`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025f90`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025ff3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025f90`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025ff3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180026449`
- `ntoskrnl!ExReleaseResourceLite` at `0x180026464`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800265c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x180026682`
- `ntoskrnl!ExReleaseResourceLite` at `0x180026449`
- `ntoskrnl!ExReleaseResourceLite` at `0x180026464`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800265c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x180026682`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180026455`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180026470`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800265d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18002668e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180026455`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180026470`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800265d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18002668e`
- `ntoskrnl!SkIsSecureKernel` at `0x180026225`
- `ntoskrnl!SkIsSecureKernel` at `0x180026568`
- `ntoskrnl!SkIsSecureKernel` at `0x18002669f`
- `ntoskrnl!SkIsSecureKernel` at `0x180026225`
- `ntoskrnl!SkIsSecureKernel` at `0x180026568`
- `ntoskrnl!SkIsSecureKernel` at `0x18002669f`
- `ntoskrnl!SkAllocatePool` at `0x1800266c1`
- `ntoskrnl!SkAllocatePool` at `0x1800266c1`
- `ntoskrnl!SkFreePool` at `0x1800265f7`
- `ntoskrnl!SkFreePool` at `0x1800265f7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180025f3c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180025f3c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025e54`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025e67`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025e54`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025e67`
- `ntoskrnl!_wcsnicmp` at `0x180026271`
- `ntoskrnl!_wcsnicmp` at `0x180026271`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180025efb`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180025efb`

## string_xrefs

- `0x180025f9c`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x180025d8d`: `\Registry\Machine\`

## pseudocode

```c
NTSTATUS __stdcall BCryptResolveProviders(
        LPCWSTR pszContext,
        ULONG dwInterface,
        LPCWSTR pszFunction,
        LPCWSTR pszProvider,
        ULONG dwMode,
        ULONG dwFlags,
        ULONG *pcbBuffer,
        PCRYPT_PROVIDER_REFS *ppBuffer)
{
  ULONG v9; // r13d
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  __int64 CurrentServerSilo; // rax
  char *v16; // r15
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r12
  struct _ERESOURCE *v20; // r15
  __int64 v21; // rax
  unsigned int v23; // edi
  __int64 Pool; // rax
  NTSTATUS v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  void *v28; // rdi
  NTSTATUS v29; // esi
  int v30; // eax
  NTSTATUS Root; // edi
  void *v32; // rdi
  __int64 v33; // rcx
  __int64 v34; // r9
  NTSTATUS v35; // eax
  NTSTATUS v36; // eax
  NTSTATUS v37; // eax
  unsigned int v38; // r9d
  int v39; // r13d
  wchar_t *v40; // r10
  __int64 v41; // rsi
  __int64 v42; // rax
  __int64 v43; // r15
  unsigned int v44; // r12d
  unsigned int i; // edi
  __int64 *v46; // rcx
  __int64 v47; // rcx
  BOOL v48; // ecx
  unsigned int v49; // r8d
  int v50; // eax
  _WORD *v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // r9
  __int64 v54; // r8
  wchar_t *v55; // r13
  __int128 *v56; // r8
  ULONG v57; // r15d
  wchar_t **p_Str1; // rdx
  __int64 v59; // r8
  unsigned int v60; // r14d
  __int64 v61; // rcx
  _QWORD *v62; // rsi
  __int128 *v63; // r8
  wchar_t **v64; // rdx
  NTSTATUS v65; // eax
  ULONG v66; // ecx
  NTSTATUS v68; // eax
  NTSTATUS v69; // eax
  BOOL v70; // esi
  NTSTATUS v71; // eax
  int Object; // [rsp+20h] [rbp-E0h]
  struct _ERESOURCE *v73; // [rsp+60h] [rbp-A0h]
  __int64 v74; // [rsp+68h] [rbp-98h] BYREF
  ULONG v75; // [rsp+70h] [rbp-90h] BYREF
  ULONG v76; // [rsp+74h] [rbp-8Ch]
  wchar_t *Str1; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v78; // [rsp+80h] [rbp-80h]
  __int64 v79; // [rsp+88h] [rbp-78h]
  void *KeyHandle; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Destination[20]; // [rsp+98h] [rbp-68h] BYREF
  int v82; // [rsp+ACh] [rbp-54h]
  __int64 v83; // [rsp+B0h] [rbp-50h]
  char *v84; // [rsp+B8h] [rbp-48h] BYREF
  int v85[2]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG *v86; // [rsp+C8h] [rbp-38h]
  PCRYPT_PROVIDER_REFS *v87; // [rsp+D0h] [rbp-30h]
  __int128 v88; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v89; // [rsp+E8h] [rbp-18h]
  PVOID v90; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v91[20]; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR v92; // [rsp+1A0h] [rbp+A0h]
  wchar_t *Str2; // [rsp+1A8h] [rbp+A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR Source[24]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v96; // [rsp+210h] [rbp+110h] BYREF

  v9 = dwInterface;
  v76 = dwInterface;
  v92 = pszFunction;
  v86 = pcbBuffer;
  v87 = ppBuffer;
  *(_QWORD *)v85 = 0;
  v74 = 0;
  v75 = 0;
  Str2 = (wchar_t *)pszProvider;
  memset(v91, 0, sizeof(v91));
  v78 = 32;
  Str1 = (wchar_t *)&v96;
  v79 = 0;
  v89 = 0;
  LOBYTE(v13) = g_TrustedEnvironment;
  v84 = 0;
  v88 = 0;
  if ( !g_TrustedEnvironment )
  {
    v13 = ((int)SkIsSecureKernel(v12, v11) >> 31) + 2;
    g_TrustedEnvironment = v13;
  }
  if ( (v13 & 2) != 0 )
  {
    v16 = (char *)&pGlobalConfigContext;
    v84 = (char *)&pGlobalConfigContext;
  }
  else
  {
    v14 = g_SiloSlot;
    CurrentServerSilo = PsGetCurrentServerSilo();
    PsGetPermanentSiloContext(CurrentServerSilo, v14, &v84);
    v16 = v84;
  }
  if ( !v9 )
  {
    if ( pszFunction && *pszFunction )
      goto LABEL_11;
LABEL_144:
    Root = 87;
    return WinErrorToNtStatus(Root);
  }
  if ( v9 - 1 > 7 && v9 - 65537 > 3 )
    goto LABEL_144;
LABEL_11:
  if ( dwMode != 2 && (!dwMode || dwMode != 1 && dwMode != 3) || !pcbBuffer )
    goto LABEL_144;
  if ( (dwFlags & 0xFFFFFFFC) != 0 )
  {
    Root = 1004;
    return WinErrorToNtStatus(Root);
  }
  memset(&v91[3], 0, 0x88u);
  HIDWORD(v91[2]) = dwFlags;
  LODWORD(v91[2]) = dwMode;
  v19 = (__int64)(v16 + 8);
  v20 = (struct _ERESOURCE *)(v16 + 136);
  v83 = v19;
  *(_OWORD *)Destination = 0;
  v82 = 0;
  KeyHandle = 0;
  v21 = -1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v91[0] = v19;
  v73 = v20;
  v91[1] = v20;
  wcscpy(Source, L"\\Registry\\Machne\\");
  while ( ::Source[++v21] != 0 )
    ;
  v23 = 2 * v21 + 38;
  LOBYTE(v21) = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
  {
    LODWORD(v21) = ((int)SkIsSecureKernel(v18, v17) >> 31) + 2;
    g_TrustedEnvironment = v21;
  }
  if ( (v21 & 2) != 0 )
    Pool = SkAllocatePool(512, v23, 1650945603);
  else
    Pool = ExAllocatePool2(64, v23, 1650945603);
  *(_QWORD *)&Destination[8] = Pool;
  if ( !Pool )
  {
    Root = 8;
    return WinErrorToNtStatus(Root);
  }
  *(_WORD *)&Destination[2] = v23;
  *(_WORD *)Destination = 0;
  RtlAppendUnicodeToString((PUNICODE_STRING)Destination, Source);
  RtlAppendUnicodeToString((PUNICODE_STRING)Destination, L"System\\CurrentControlSet\\Control\\Cryptography\\Providers");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v25 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v28 = *(void **)&Destination[8];
  v29 = v25;
  if ( *(_QWORD *)&Destination[8] )
  {
    LOBYTE(v30) = g_TrustedEnvironment;
    if ( !g_TrustedEnvironment )
    {
      v30 = ((int)SkIsSecureKernel(v27, v26) >> 31) + 2;
      g_TrustedEnvironment = v30;
    }
    if ( (v30 & 2) != 0 )
      SkFreePool(512, v28);
    else
      ExFreePoolWithTag(v28, 0x62676E43u);
  }
  Root = RtlNtStatusToDosErrorNoTeb(v29);
  if ( !Root )
  {
    v32 = KeyHandle;
    *(_QWORD *)Destination = 0;
    v90 = 0;
    if ( ObReferenceObjectByHandle(KeyHandle, 0, 0, 0, &v90, (POBJECT_HANDLE_INFORMATION)Destination) >= 0 )
    {
      ObfDereferenceObject(v90);
      ZwClose(v32);
    }
    if ( !*(_DWORD *)(v19 + 120) )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)v19, 1u);
      if ( !*(_DWORD *)(v19 + 120) )
      {
        Root = PrvReg_LoadRoot(v19);
        if ( Root )
          goto LABEL_107;
        *(_DWORD *)(v19 + 120) = 1;
      }
      ExReleaseResourceLite((PERESOURCE)v19);
      KeLeaveCriticalRegion();
    }
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)v19, 1u);
    *(_DWORD *)&Destination[8] = 60;
    *(_QWORD *)Destination = L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration";
    *(_QWORD *)&Destination[12] = 59;
    v82 = 0;
    Root = VerifyRegistryAccess(v33, (const WCHAR **)Destination, 0x20019u);
    if ( Root )
      goto LABEL_107;
    if ( !LODWORD(v20[1].OwnerTable) )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(v20, 1u);
      if ( !LODWORD(v20[1].OwnerTable) )
      {
        Root = CfgReg_LoadRoot(v20);
        if ( Root )
          goto LABEL_106;
        LODWORD(v20[1].OwnerTable) = 1;
      }
      ExReleaseResourceLite(v20);
      KeLeaveCriticalRegion();
    }
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(v20, 1u);
    if ( pszFunction && *pszFunction )
    {
      LODWORD(KeyHandle) = 0;
      if ( (unsigned int)SzString_CchLength(pszFunction, &KeyHandle, 0, v34) )
        goto LABEL_70;
      HIDWORD(v88) = (_DWORD)KeyHandle;
      *(_QWORD *)&v88 = pszFunction;
      LODWORD(v89) = 0;
      DWORD2(v88) = (_DWORD)KeyHandle + 1;
      v35 = DetermineFunctionInterface(v19, v20, &v88, &v75);
      Root = v35;
      if ( v9 )
      {
        if ( v35 && v35 != 1168 )
          goto LABEL_106;
        if ( v9 != v75 )
          goto LABEL_124;
      }
      else
      {
        if ( v35 )
          goto LABEL_106;
        v9 = v75;
        v76 = v75;
      }
    }
    if ( Str1 && (_DWORD)v78 && HIDWORD(v78) < 0x7FFFFFFF && (unsigned int)v78 >= 9 )
    {
      *Str1 = 0;
      HIDWORD(v78) = 8;
      if ( (int)StringCchPrintfW(Str1, (unsigned int)v78, L"%08X", v9) < 0 )
      {
        Root = 13;
        goto LABEL_106;
      }
      if ( !pszContext || !*pszContext )
      {
LABEL_44:
        v36 = _CfgFind(65552, (unsigned int)&v74, 0, 0);
        Root = v36;
        if ( v36 && v36 != 1168 )
          goto LABEL_106;
        v91[4] = v74;
        v37 = _CfgFind(65552, (unsigned int)&v74, 0, 0);
        Root = v37;
        if ( v37 )
        {
          if ( v37 != 1168 )
            goto LABEL_106;
        }
        v91[6] = v74;
LABEL_47:
        v38 = HIDWORD(v78);
        v39 = 0;
        v40 = Str1;
        v41 = 0;
        while ( 1 )
        {
          v42 = v91[v41 + 3];
          if ( v42 )
          {
            v43 = *(_QWORD *)(v42 + 24);
            if ( v43 )
              break;
          }
LABEL_77:
          if ( ++v41 == 4 )
          {
            v51 = v92;
            if ( v39 )
            {
              v52 = v91[5];
              if ( v91[5] && (*(_DWORD *)(v91[5] + 16LL) & 0x10000) != 0 )
              {
                v53 = v91[3];
                v54 = v91[5];
                v52 = v91[4];
                v91[5] = v91[4];
                v91[4] = v91[3];
                v91[3] = v54;
              }
              else
              {
                v53 = v91[4];
                v54 = v91[3];
              }
              if ( v91[6] && (*(_DWORD *)(v91[6] + 16LL) & 0x10000) != 0 )
              {
                if ( v54 && (*(_DWORD *)(v54 + 16) & 0x10000) != 0 )
                {
                  v91[4] = v91[6];
                }
                else
                {
                  v91[4] = v54;
                  v91[3] = v91[6];
                }
                v91[5] = v53;
                v91[6] = v52;
              }
              v55 = Str2;
              if ( Str2 && *Str2 )
              {
                v19 = v83;
                Root = _PrvFind(0, (int)v85, v54, 0, Object, v83, Str2, 0);
                if ( !Root )
                {
                  if ( v51 && *v51 )
                    v56 = &v88;
                  else
                    LODWORD(v56) = 0;
                  v57 = v76;
                  p_Str1 = &Str1;
                  if ( !v76 )
                    LODWORD(p_Str1) = 0;
                  Root = PackProviderNodeRef(v85[0], (_DWORD)p_Str1, (_DWORD)v56, 0, (__int64)v91);
                  if ( !Root )
                  {
LABEL_92:
                    v60 = v91[10];
                    v61 = (unsigned int)(8 * LODWORD(v91[10]) + LODWORD(v91[12]) + 16);
                    if ( v87 )
                    {
                      v62 = *v87;
                      if ( *v87 )
                      {
                        if ( *v86 < (unsigned int)v61 )
                        {
                          *v86 = v61;
                          Root = 122;
                        }
                        else
                        {
LABEL_95:
                          LODWORD(v91[10]) = 0;
                          LODWORD(v91[12]) = 0;
                          v91[11] = &v62[v60 + 2];
                          v91[9] = v62 + 2;
                          if ( v55 && *v55 )
                          {
                            if ( v51 && *v51 )
                              v63 = &v88;
                            else
                              LODWORD(v63) = 0;
                            v64 = &Str1;
                            if ( !v57 )
                              LODWORD(v64) = 0;
                            v65 = PackProviderNodeRef(v85[0], (_DWORD)v64, (_DWORD)v63, 0, (__int64)v91);
                          }
                          else if ( v51 && *v51 )
                          {
                            v65 = PackFunctionRefs(&Str1, &v88, 0, v91);
                          }
                          else
                          {
                            v65 = PackInterfaceRefs(&Str1, v91, v59, 0);
                          }
                          Root = v65;
                          if ( v65 )
                          {
                            if ( v62 && v62 != (_QWORD *)*v87 )
                              BCryptFree(v62);
                          }
                          else
                          {
                            v62[1] = v91[9];
                            *(_DWORD *)v62 = v91[10];
                            v66 = v60 * 8 + LODWORD(v91[12]) + 16;
                            *v87 = (PCRYPT_PROVIDER_REFS)v62;
                            *v86 = v66;
                          }
                        }
                      }
                      else
                      {
                        v62 = (_QWORD *)BCryptAlloc(v61);
                        if ( v62 )
                          goto LABEL_95;
                        Root = 8;
                      }
                    }
                    else
                    {
                      Root = 0;
                      *v86 = v61;
                    }
                  }
                }
              }
              else
              {
                if ( v92 && *v92 )
                  v68 = PackFunctionRefs(&Str1, &v88, 0, v91);
                else
                  v68 = PackInterfaceRefs(&Str1, v91, v54, v53);
                v19 = v83;
                Root = v68;
                if ( !v68 )
                {
                  v57 = v76;
                  goto LABEL_92;
                }
              }
            }
            else
            {
              v19 = v83;
              Root = 1168;
            }
            v20 = v73;
LABEL_106:
            ExReleaseResourceLite(v20);
            KeLeaveCriticalRegion();
LABEL_107:
            ExReleaseResourceLite((PERESOURCE)v19);
            KeLeaveCriticalRegion();
            return WinErrorToNtStatus(Root);
          }
        }
        v44 = *(_DWORD *)(v42 + 20);
        for ( i = 0; ; ++i )
        {
          if ( i >= v44 )
            goto LABEL_77;
          v46 = *(__int64 **)(v43 + 8LL * i);
          if ( v46 && *((_DWORD *)v46 + 2) != 2 )
          {
            v47 = *v46;
            if ( v40 && (_DWORD)v78 && v38 - 1 <= 0x7FFFFFFD )
            {
              if ( !v47 )
                continue;
              if ( !*(_QWORD *)v47 )
                continue;
              if ( !*(_DWORD *)(v47 + 8) )
                continue;
              v49 = *(_DWORD *)(v47 + 12);
              if ( v38 > 0xFFFF || v49 - 1 > 0x7FFFFFFD || v49 > 0xFFFF || v38 != v49 )
                continue;
              v50 = _wcsnicmp(v40, *(const wchar_t **)v47, v38 + 1);
              v38 = HIDWORD(v78);
              v40 = Str1;
              v48 = v50 == 0;
            }
            else
            {
              v48 = !v47
                 || !*(_QWORD *)v47
                 || !*(_DWORD *)(v47 + 8)
                 || (unsigned int)(*(_DWORD *)(v47 + 12) - 1) > 0x7FFFFFFD;
            }
            if ( v48 )
            {
              if ( *(_QWORD *)(v43 + 8LL * i) )
                v39 = 1;
              goto LABEL_77;
            }
          }
        }
      }
      v69 = _CfgFind(65552, (unsigned int)&v74, 0, 0);
      Root = v69;
      if ( v69 && v69 != 1168 )
        goto LABEL_106;
      v91[3] = v74;
      v70 = 0;
      if ( v74 )
        v70 = (*(_BYTE *)(v74 + 16) & 1) != 0;
      v71 = _CfgFind(65552, (unsigned int)&v74, 0, 0);
      Root = v71;
      if ( v71 )
      {
        if ( v71 != 1168 )
          goto LABEL_106;
      }
      v91[5] = v74;
      if ( v74 && (*(_BYTE *)(v74 + 16) & 1) != 0 )
        v70 = 1;
      if ( v91[3] || v74 )
      {
        if ( v70 )
          goto LABEL_47;
        goto LABEL_44;
      }
LABEL_124:
      Root = 1168;
      goto LABEL_106;
    }
LABEL_70:
    Root = 87;
    goto LABEL_106;
  }
  return WinErrorToNtStatus(Root);
}

```

## disassembly

```asm
0x180025c00  push    rbp
0x180025c02  push    rbx
0x180025c03  push    rsi
0x180025c04  push    rdi
0x180025c05  push    r13
0x180025c07  push    r14
0x180025c09  lea     rbp, [rsp-178h]
0x180025c11  sub     rsp, 278h
0x180025c18  mov     rax, cs:__security_cookie
0x180025c1f  xor     rax, rsp
0x180025c22  mov     [rbp+1A0h+var_50], rax
0x180025c29  mov     rax, [rbp+1A0h+ppBuffer]
0x180025c30  mov     rbx, r8
0x180025c33  mov     rsi, [rbp+1A0h+pcbBuffer]
0x180025c3a  xor     edi, edi
0x180025c3c  mov     r13d, edx
0x180025c3f  mov     [rsp+2A0h+var_22C], edx
0x180025c43  mov     r14, rcx
0x180025c46  mov     [rbp+1A0h+var_100], rbx
0x180025c4d  xor     edx, edx; Val
0x180025c4f  mov     [rbp+1A0h+var_1D8], rsi
0x180025c53  mov     r8d, 0A0h; Size
0x180025c59  mov     [rbp+1A0h+var_1D0], rax
0x180025c5d  lea     rcx, [rbp+1A0h+var_1A0]; void *
0x180025c61  mov     qword ptr [rbp+1A0h+var_1E0], rdi
0x180025c65  mov     [rsp+2A0h+var_238], rdi
0x180025c6a  mov     [rsp+2A0h+var_230], edi
0x180025c6e  mov     [rbp+1A0h+var_F8], r9
0x180025c75  call    memset
0x180025c7a  lea     rax, [rbp+1A0h+var_90]
0x180025c81  mov     [rbp+1A0h+var_220], 20h ; ' '
0x180025c89  mov     [rsp+2A0h+Str1], rax
0x180025c8e  xorps   xmm0, xmm0
0x180025c91  xor     eax, eax
0x180025c93  mov     [rbp+1A0h+var_218], rdi
0x180025c97  mov     [rbp+1A0h+var_1B8], rax
0x180025c9b  mov     eax, cs:g_TrustedEnvironment
0x180025ca1  mov     [rbp+1A0h+var_1E8], rdi
0x180025ca5  movups  [rbp+1A0h+var_1C8], xmm0
0x180025ca9  test    eax, eax
0x180025cab  jz      loc_180026568
0x180025cb1  mov     [rsp+2A0h+var_38], r15
0x180025cb9  test    al, 2
0x180025cbb  jnz     loc_180026628
0x180025cc1  mov     edi, cs:g_SiloSlot
0x180025cc7  call    cs:__imp_PsGetCurrentServerSilo
0x180025cce  nop     dword ptr [rax+rax+00h]
0x180025cd3  lea     r8, [rbp+1A0h+var_1E8]
0x180025cd7  mov     edx, edi
0x180025cd9  mov     rcx, rax
0x180025cdc  call    cs:__imp_PsGetPermanentSiloContext
0x180025ce3  nop     dword ptr [rax+rax+00h]
0x180025ce8  mov     r15, [rbp+1A0h+var_1E8]
0x180025cec  mov     [rsp+2A0h+var_30], r12
0x180025cf4  test    r13d, r13d
0x180025cf7  jz      short loc_180025D14
0x180025cf9  lea     eax, [r13-1]
0x180025cfd  cmp     eax, 7
0x180025d00  jbe     short loc_180025D27
0x180025d02  lea     eax, [r13-10001h]
0x180025d09  cmp     eax, 3
0x180025d0c  ja      loc_180026701
0x180025d12  jmp     short loc_180025D27
0x180025d14  test    rbx, rbx
0x180025d17  jz      loc_180026701
0x180025d1d  cmp     word ptr [rbx], 0
0x180025d21  jz      loc_180026701
0x180025d27  mov     edi, [rbp+1A0h+dwMode]
0x180025d2d  cmp     edi, 2
0x180025d30  jnz     loc_1800266E9
0x180025d36  test    rsi, rsi
0x180025d39  jz      loc_180026701
0x180025d3f  mov     esi, [rbp+1A0h+dwFlags]
0x180025d45  test    esi, 0FFFFFFFCh
0x180025d4b  jnz     loc_180026750
0x180025d51  xor     edx, edx; Val
0x180025d53  lea     rcx, [rbp+1A0h+var_188]; void *
0x180025d57  mov     r8d, 88h; Size
0x180025d5d  call    memset
0x180025d62  xorps   xmm1, xmm1
0x180025d65  mov     [rbp+1A0h+var_18C], esi
0x180025d68  xorps   xmm0, xmm0
0x180025d6b  mov     [rbp+1A0h+var_190], edi
0x180025d6e  lea     r12, [r15+8]
0x180025d72  add     r15, 88h
0x180025d79  xor     eax, eax
0x180025d7b  mov     [rbp+1A0h+var_1F0], r12
0x180025d7f  movups  xmmword ptr [rbp+1A0h+Destination], xmm0
0x180025d83  mov     [rbp+1A0h+var_1F4], eax
0x180025d86  lea     rsi, Source; "System\\CurrentControlSet\\Control\\Cry"...
0x180025d8d  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180025d94  mov     [rbp+1A0h+KeyHandle], rax
0x180025d98  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180025d9f  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.Length], xmm1
0x180025da6  mov     [rbp+1A0h+var_1A0], r12
0x180025daa  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.ObjectName], xmm1
0x180025db1  mov     [rsp+2A0h+var_240], r15
0x180025db6  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180025dbd  mov     [rbp+1A0h+var_198], r15
0x180025dc1  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180025dc8  movups  xmmword ptr [rbp+1A0h+Source], xmm0
0x180025dcf  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180025dd7  movups  [rbp+1A0h+var_B0], xmm1
0x180025dde  movsd   qword ptr [rbp+1A0h+var_B0+0Eh], xmm0
0x180025de6  nop     word ptr [rax+rax+00000000h]
0x180025df0  cmp     word ptr [rsi+rax*2+2], 0
0x180025df6  lea     rax, [rax+1]
0x180025dfa  jnz     short loc_180025DF0
0x180025dfc  lea     edi, ds:26h[rax*2]
0x180025e03  mov     eax, cs:g_TrustedEnvironment
0x180025e09  test    eax, eax
0x180025e0b  jz      loc_18002669F
0x180025e11  mov     edx, edi
0x180025e13  mov     r8d, 62676E43h
0x180025e19  test    al, 2
0x180025e1b  jnz     loc_1800266BC
0x180025e21  mov     ecx, 40h ; '@'
0x180025e26  call    cs:__imp_ExAllocatePool2
0x180025e2d  nop     dword ptr [rax+rax+00h]
0x180025e32  mov     qword ptr [rbp+1A0h+Destination+8], rax
0x180025e36  test    rax, rax
0x180025e39  jz      loc_1800267BD
0x180025e3f  xor     eax, eax
0x180025e41  mov     word ptr [rbp+1A0h+Destination+2], di
0x180025e45  lea     rdx, [rbp+1A0h+Source]; Source
0x180025e4c  mov     word ptr [rbp+1A0h+Destination], ax
0x180025e50  lea     rcx, [rbp+1A0h+Destination]; Destination
0x180025e54  call    cs:__imp_RtlAppendUnicodeToString
0x180025e5b  nop     dword ptr [rax+rax+00h]
0x180025e60  mov     rdx, rsi; Source
0x180025e63  lea     rcx, [rbp+1A0h+Destination]; Destination
0x180025e67  call    cs:__imp_RtlAppendUnicodeToString
0x180025e6e  nop     dword ptr [rax+rax+00h]
0x180025e73  lea     rax, [rbp+1A0h+Destination]
0x180025e77  mov     [rbp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x180025e81  xorps   xmm0, xmm0
0x180025e84  mov     [rbp+1A0h+ObjectAttributes.ObjectName], rax
0x180025e8b  lea     r8, [rbp+1A0h+ObjectAttributes]; ObjectAttributes
0x180025e92  mov     [rbp+1A0h+ObjectAttributes.RootDirectory], 0
0x180025e9d  mov     edx, 20019h; DesiredAccess
0x180025ea2  mov     [rbp+1A0h+ObjectAttributes.Attributes], 240h
0x180025eac  lea     rcx, [rbp+1A0h+KeyHandle]; KeyHandle
0x180025eb0  movdqu  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025eb8  call    cs:__imp_ZwOpenKey
0x180025ebf  nop     dword ptr [rax+rax+00h]
0x180025ec4  mov     rdi, qword ptr [rbp+1A0h+Destination+8]
0x180025ec8  mov     esi, eax
0x180025eca  test    rdi, rdi
0x180025ecd  jz      short loc_180025EF9
0x180025ecf  mov     eax, cs:g_TrustedEnvironment
0x180025ed5  test    eax, eax
0x180025ed7  jz      loc_180026225
0x180025edd  test    al, 2
0x180025edf  jnz     loc_1800265EF
0x180025ee5  mov     edx, 62676E43h; Tag
0x180025eea  mov     rcx, rdi; P
0x180025eed  call    cs:__imp_ExFreePoolWithTag
0x180025ef4  nop     dword ptr [rax+rax+00h]
0x180025ef9  mov     ecx, esi; Status
0x180025efb  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180025f02  nop     dword ptr [rax+rax+00h]
0x180025f07  mov     edi, eax
0x180025f09  test    eax, eax
0x180025f0b  jnz     loc_18002647C
0x180025f11  mov     rdi, [rbp+1A0h+KeyHandle]
0x180025f15  xor     eax, eax
0x180025f17  mov     qword ptr [rbp+1A0h+Destination], rax
0x180025f1b  xor     r9d, r9d; AccessMode
0x180025f1e  mov     [rbp+1A0h+var_1B0], rax
0x180025f22  xor     r8d, r8d; ObjectType
0x180025f25  lea     rax, [rbp+1A0h+Destination]
0x180025f29  xor     edx, edx; DesiredAccess
0x180025f2b  mov     [rsp+2A0h+HandleInformation], rax; HandleInformation
0x180025f30  mov     rcx, rdi; Handle
0x180025f33  lea     rax, [rbp+1A0h+var_1B0]
0x180025f37  mov     [rsp+2A0h+Object], rax; int
0x180025f3c  call    cs:__imp_ObReferenceObjectByHandle
0x180025f43  nop     dword ptr [rax+rax+00h]
0x180025f48  test    eax, eax
0x180025f4a  js      short loc_180025F6B
0x180025f4c  mov     rcx, [rbp+1A0h+var_1B0]; Object
0x180025f50  call    cs:__imp_ObfDereferenceObject
0x180025f57  nop     dword ptr [rax+rax+00h]
0x180025f5c  mov     rcx, rdi; Handle
0x180025f5f  call    cs:__imp_ZwClose
0x180025f66  nop     dword ptr [rax+rax+00h]
0x180025f6b  mov     eax, [r12+78h]
0x180025f70  mov     esi, 1
0x180025f75  test    eax, eax
0x180025f77  jz      loc_180026653
0x180025f7d  call    cs:__imp_KeEnterCriticalRegion
0x180025f84  nop     dword ptr [rax+rax+00h]
0x180025f89  movzx   edx, sil; Wait
0x180025f8d  mov     rcx, r12; Resource
0x180025f90  call    cs:__imp_ExAcquireResourceSharedLite
0x180025f97  nop     dword ptr [rax+rax+00h]
0x180025f9c  lea     rax, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180025fa3  mov     dword ptr [rbp+1A0h+Destination+8], 3Ch ; '<'
0x180025faa  mov     qword ptr [rbp+1A0h+Destination], rax
0x180025fae  lea     rdx, [rbp+1A0h+Destination]
0x180025fb2  xor     eax, eax
0x180025fb4  mov     qword ptr [rbp+1A0h+Destination+0Ch], 3Bh ; ';'
0x180025fbc  mov     r8d, 20019h
0x180025fc2  mov     [rbp+1A0h+var_1F4], eax
0x180025fc5  call    VerifyRegistryAccess
0x180025fca  mov     edi, eax
0x180025fcc  test    eax, eax
0x180025fce  jnz     loc_180026461
0x180025fd4  mov     eax, [r15+78h]
0x180025fd8  test    eax, eax
0x180025fda  jz      loc_180026598
0x180025fe0  call    cs:__imp_KeEnterCriticalRegion
0x180025fe7  nop     dword ptr [rax+rax+00h]
0x180025fec  movzx   edx, sil; Wait
0x180025ff0  mov     rcx, r15; Resource
0x180025ff3  call    cs:__imp_ExAcquireResourceSharedLite
0x180025ffa  nop     dword ptr [rax+rax+00h]
0x180025fff  test    rbx, rbx
0x180026002  jz      short loc_18002606A
0x180026004  cmp     word ptr [rbx], 0
0x180026008  jz      short loc_18002606A
0x18002600a  xor     edi, edi
0x18002600c  lea     rdx, [rbp+1A0h+KeyHandle]
0x180026010  xor     r8d, r8d
0x180026013  mov     dword ptr [rbp+1A0h+KeyHandle], edi
0x180026016  mov     rcx, rbx
0x180026019  call    SzString_CchLength
0x18002601e  test    eax, eax
0x180026020  jnz     loc_180026252
0x180026026  mov     ecx, dword ptr [rbp+1A0h+KeyHandle]
0x180026029  lea     r9, [rsp+2A0h+var_230]
0x18002602e  mov     dword ptr [rbp+1A0h+var_1C8+0Ch], ecx
0x180026031  lea     r8, [rbp+1A0h+var_1C8]
0x180026035  mov     rdx, r15
0x180026038  mov     qword ptr [rbp+1A0h+var_1C8], rbx
0x18002603c  mov     dword ptr [rbp+1A0h+var_1B8], edi
0x18002603f  lea     eax, [rcx+1]
0x180026042  mov     rcx, r12
0x180026045  mov     dword ptr [rbp+1A0h+var_1C8+8], eax
0x180026048  call    _DetermineFunctionInterface
0x18002604d  mov     edi, eax
0x18002604f  test    r13d, r13d
0x180026052  jnz     loc_18002654B
0x180026058  test    eax, eax
0x18002605a  jnz     loc_180026446
0x180026060  mov     r13d, [rsp+2A0h+var_230]
0x180026065  mov     [rsp+2A0h+var_22C], r13d
0x18002606a  mov     rcx, [rsp+2A0h+Str1]
0x18002606f  test    rcx, rcx
0x180026072  jz      loc_180026252
0x180026078  mov     eax, dword ptr [rbp+1A0h+var_220]
0x18002607b  test    eax, eax
0x18002607d  jz      loc_180026252
0x180026083  cmp     dword ptr [rbp+1A0h+var_220+4], 7FFFFFFFh
0x18002608a  jnb     loc_180026252
0x180026090  cmp     eax, 9
0x180026093  jb      loc_180026252
0x180026099  xor     eax, eax
0x18002609b  lea     r8, a08x; "%08X"
0x1800260a2  mov     [rcx], ax
0x1800260a5  mov     r9d, r13d
0x1800260a8  mov     edx, dword ptr [rbp+1A0h+var_220]; unsigned __int64
0x1800260ab  mov     rcx, [rsp+2A0h+Str1]; unsigned __int16 *
0x1800260b0  mov     dword ptr [rbp+1A0h+var_220+4], 8
0x1800260b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800260bc  test    eax, eax
0x1800260be  js      loc_18002676A
0x1800260c4  test    r14, r14
0x1800260c7  jnz     loc_1800A24EA
0x1800260cd  xor     r14d, r14d
0x1800260d0  lea     rdx, [rsp+2A0h+var_238]
0x1800260d5  mov     [rsp+2A0h+var_250], r14
0x1800260da  xor     r9d, r9d
0x1800260dd  mov     [rsp+2A0h+var_258], r14
0x1800260e2  xor     r8d, r8d
0x1800260e5  mov     [rsp+2A0h+var_260], r14d
0x1800260ea  mov     ecx, 10010h
0x1800260ef  mov     qword ptr [rsp+2A0h+var_268], r14
0x1800260f4  mov     dword ptr [rsp+2A0h+Str2], esi
0x1800260f8  mov     [rsp+2A0h+HandleInformation], r15
0x1800260fd  call    __CfgFind
0x180026102  mov     edi, eax
0x180026104  test    eax, eax
0x180026106  jnz     loc_1800266D2
0x18002610c  mov     rax, [rsp+2A0h+var_238]
0x180026111  lea     rdx, [rsp+2A0h+var_238]
0x180026116  mov     [rsp+2A0h+var_250], r14
0x18002611b  xor     r9d, r9d
0x18002611e  mov     [rsp+2A0h+var_258], r14
0x180026123  xor     r8d, r8d
0x180026126  mov     [rsp+2A0h+var_260], r14d
0x18002612b  mov     ecx, 10010h
0x180026130  mov     qword ptr [rsp+2A0h+var_268], r14
0x180026135  mov     dword ptr [rsp+2A0h+Str2], 2
0x18002613d  mov     [rsp+2A0h+HandleInformation], r15
0x180026142  mov     [rbp+1A0h+var_180], rax
0x180026146  call    __CfgFind
0x18002614b  mov     edi, eax
0x18002614d  test    eax, eax
0x18002614f  jnz     loc_180026242
  ... truncated ...
```
