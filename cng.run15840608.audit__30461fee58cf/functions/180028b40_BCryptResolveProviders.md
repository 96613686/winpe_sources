# BCryptResolveProviders

- ea: `0x180028b40`
- end: `0x180029707`
- name: `BCryptResolveProviders`
- size: `3015`
- prototype: `NTSTATUS __stdcall(LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, LPCWSTR pszProvider, ULONG dwMode, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *ppBuffer)`
- caller_count: `6`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001770`
- `0x180026560`
- `0x180039c40`
- `0x180058a90`
- `0x180058e40`
- `0x18005cb30`

## callees

- `0x18001bd90`
- `0x18001be80`
- `0x180027430`
- `0x180027720`
- `0x180027c60`
- `0x180027d00`
- `0x180028480`
- `0x180028750`
- `0x1800289e0`
- `0x180028b40`
- `0x180029710`
- `0x18002a080`
- `0x18002bf88`
- `0x1800362e8`
- `0x18003651c`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180028d66`
- `ntoskrnl!ExAllocatePool2` at `0x180028d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x180028e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180028e2d`
- `ntoskrnl!ZwClose` at `0x180028e9f`
- `ntoskrnl!ZwClose` at `0x180028e9f`
- `ntoskrnl!ObfDereferenceObject` at `0x180028e90`
- `ntoskrnl!ObfDereferenceObject` at `0x180028e90`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180028c07`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180028c07`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180028c1c`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180028c1c`
- `ntoskrnl!ZwOpenKey` at `0x180028df8`
- `ntoskrnl!ZwOpenKey` at `0x180028df8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180028ebd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180028f20`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800294d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180029593`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180028ebd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180028f20`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800294d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180029593`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800294eb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800295a6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800294eb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800295a6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180028ed0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180028f33`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180028ed0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180028f33`
- `ntoskrnl!ExReleaseResourceLite` at `0x180029389`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800293a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180029506`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800295c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x180029389`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800293a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180029506`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800295c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180029395`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800293b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180029512`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800295ce`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180029395`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800293b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180029512`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800295ce`
- `ntoskrnl!SkIsSecureKernel` at `0x180029165`
- `ntoskrnl!SkIsSecureKernel` at `0x1800294a8`
- `ntoskrnl!SkIsSecureKernel` at `0x1800295df`
- `ntoskrnl!SkIsSecureKernel` at `0x180029165`
- `ntoskrnl!SkIsSecureKernel` at `0x1800294a8`
- `ntoskrnl!SkIsSecureKernel` at `0x1800295df`
- `ntoskrnl!SkAllocatePool` at `0x180029601`
- `ntoskrnl!SkAllocatePool` at `0x180029601`
- `ntoskrnl!SkFreePool` at `0x180029537`
- `ntoskrnl!SkFreePool` at `0x180029537`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180028e7c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180028e7c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028d94`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028da7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028d94`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028da7`
- `ntoskrnl!_wcsnicmp` at `0x1800291b1`
- `ntoskrnl!_wcsnicmp` at `0x1800291b1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180028e3b`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180028e3b`

## string_xrefs

- `0x180028edc`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x180028ccd`: `\Registry\Machine\`

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
  void *v16; // r15
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r12
  __int64 v20; // r15
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
  int Objecta; // [rsp+20h] [rbp-E0h]
  int Objectb; // [rsp+20h] [rbp-E0h]
  __int64 v75; // [rsp+60h] [rbp-A0h]
  __int64 v76; // [rsp+68h] [rbp-98h] BYREF
  ULONG v77; // [rsp+70h] [rbp-90h] BYREF
  ULONG v78; // [rsp+74h] [rbp-8Ch]
  wchar_t *Str1; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v80; // [rsp+80h] [rbp-80h]
  __int64 v81; // [rsp+88h] [rbp-78h]
  void *KeyHandle; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Destination[20]; // [rsp+98h] [rbp-68h] BYREF
  int v84; // [rsp+ACh] [rbp-54h]
  __int64 v85; // [rsp+B0h] [rbp-50h]
  void *v86; // [rsp+B8h] [rbp-48h] BYREF
  int v87[2]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG *v88; // [rsp+C8h] [rbp-38h]
  PCRYPT_PROVIDER_REFS *v89; // [rsp+D0h] [rbp-30h]
  __int128 v90; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v91; // [rsp+E8h] [rbp-18h]
  PVOID v92; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v93[20]; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR v94; // [rsp+1A0h] [rbp+A0h]
  wchar_t *Str2; // [rsp+1A8h] [rbp+A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR Source[24]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v98; // [rsp+210h] [rbp+110h] BYREF

  v9 = dwInterface;
  v78 = dwInterface;
  v94 = pszFunction;
  v88 = pcbBuffer;
  v89 = ppBuffer;
  *(_QWORD *)v87 = 0;
  v76 = 0;
  v77 = 0;
  Str2 = (wchar_t *)pszProvider;
  memset(v93, 0, sizeof(v93));
  v80 = 32;
  Str1 = (wchar_t *)&v98;
  v81 = 0;
  v91 = 0;
  LOBYTE(v13) = g_TrustedEnvironment;
  v86 = 0;
  v90 = 0;
  if ( !g_TrustedEnvironment )
  {
    v13 = ((int)SkIsSecureKernel(v12, v11) >> 31) + 2;
    g_TrustedEnvironment = v13;
  }
  if ( (v13 & 2) != 0 )
  {
    v16 = &pGlobalConfigContext;
    v86 = &pGlobalConfigContext;
  }
  else
  {
    v14 = g_SiloSlot;
    CurrentServerSilo = PsGetCurrentServerSilo();
    PsGetPermanentSiloContext(CurrentServerSilo, v14, &v86);
    v16 = v86;
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
  memset(&v93[3], 0, 0x88u);
  HIDWORD(v93[2]) = dwFlags;
  LODWORD(v93[2]) = dwMode;
  v19 = (__int64)v16 + 8;
  v20 = (__int64)v16 + 136;
  v85 = v19;
  *(_OWORD *)Destination = 0;
  v84 = 0;
  KeyHandle = 0;
  v21 = -1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v93[0] = v19;
  v75 = v20;
  v93[1] = v20;
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
    v92 = 0;
    if ( ObReferenceObjectByHandle(KeyHandle, 0, 0, 0, &v92, (POBJECT_HANDLE_INFORMATION)Destination) >= 0 )
    {
      ObfDereferenceObject(v92);
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
    v84 = 0;
    Root = VerifyRegistryAccess(v33, (const WCHAR **)Destination, 0x20019u);
    if ( Root )
      goto LABEL_107;
    if ( !*(_DWORD *)(v20 + 120) )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)v20, 1u);
      if ( !*(_DWORD *)(v20 + 120) )
      {
        Root = CfgReg_LoadRoot(v20);
        if ( Root )
          goto LABEL_106;
        *(_DWORD *)(v20 + 120) = 1;
      }
      ExReleaseResourceLite((PERESOURCE)v20);
      KeLeaveCriticalRegion();
    }
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)v20, 1u);
    if ( pszFunction && *pszFunction )
    {
      LODWORD(KeyHandle) = 0;
      if ( (unsigned int)SzString_CchLength(pszFunction, &KeyHandle, 0, v34) )
        goto LABEL_70;
      HIDWORD(v90) = (_DWORD)KeyHandle;
      *(_QWORD *)&v90 = pszFunction;
      LODWORD(v91) = 0;
      DWORD2(v90) = (_DWORD)KeyHandle + 1;
      v35 = DetermineFunctionInterface(v19, v20, &v90, &v77);
      Root = v35;
      if ( v9 )
      {
        if ( v35 && v35 != 1168 )
          goto LABEL_106;
        if ( v9 != v77 )
          goto LABEL_124;
      }
      else
      {
        if ( v35 )
          goto LABEL_106;
        v9 = v77;
        v78 = v77;
      }
    }
    if ( Str1 && (_DWORD)v80 && HIDWORD(v80) < 0x7FFFFFFF && (unsigned int)v80 >= 9 )
    {
      *Str1 = 0;
      HIDWORD(v80) = 8;
      if ( (int)StringCchPrintfW(Str1, (unsigned int)v80, L"%08X", v9) < 0 )
      {
        Root = 13;
        goto LABEL_106;
      }
      if ( !pszContext || !*pszContext )
      {
LABEL_44:
        v36 = _CfgFind(65552, (unsigned int)&v76, 0, 0, Object, v20, 1, 0, 0, 0, 0);
        Root = v36;
        if ( v36 && v36 != 1168 )
          goto LABEL_106;
        v93[4] = v76;
        v37 = _CfgFind(65552, (unsigned int)&v76, 0, 0, Objecta, v20, 2, 0, 0, 0, 0);
        Root = v37;
        if ( v37 )
        {
          if ( v37 != 1168 )
            goto LABEL_106;
        }
        v93[6] = v76;
LABEL_47:
        v38 = HIDWORD(v80);
        v39 = 0;
        v40 = Str1;
        v41 = 0;
        while ( 1 )
        {
          v42 = v93[v41 + 3];
          if ( v42 )
          {
            v43 = *(_QWORD *)(v42 + 24);
            if ( v43 )
              break;
          }
LABEL_77:
          if ( ++v41 == 4 )
          {
            v51 = v94;
            if ( v39 )
            {
              v52 = v93[5];
              if ( v93[5] && (*(_DWORD *)(v93[5] + 16LL) & 0x10000) != 0 )
              {
                v53 = v93[3];
                v54 = v93[5];
                v52 = v93[4];
                v93[5] = v93[4];
                v93[4] = v93[3];
                v93[3] = v54;
              }
              else
              {
                v53 = v93[4];
                v54 = v93[3];
              }
              if ( v93[6] && (*(_DWORD *)(v93[6] + 16LL) & 0x10000) != 0 )
              {
                if ( v54 && (*(_DWORD *)(v54 + 16) & 0x10000) != 0 )
                {
                  v93[4] = v93[6];
                }
                else
                {
                  v93[4] = v54;
                  v93[3] = v93[6];
                }
                v93[5] = v53;
                v93[6] = v52;
              }
              v55 = Str2;
              if ( Str2 && *Str2 )
              {
                v19 = v85;
                Root = _PrvFind(0, (int)v87, v54, 0, Object, v85, Str2, 0);
                if ( !Root )
                {
                  if ( v51 && *v51 )
                    v56 = &v90;
                  else
                    LODWORD(v56) = 0;
                  v57 = v78;
                  p_Str1 = &Str1;
                  if ( !v78 )
                    LODWORD(p_Str1) = 0;
                  Root = PackProviderNodeRef(v87[0], (_DWORD)p_Str1, (_DWORD)v56, 0, (__int64)v93);
                  if ( !Root )
                  {
LABEL_92:
                    v60 = v93[10];
                    v61 = (unsigned int)(8 * LODWORD(v93[10]) + LODWORD(v93[12]) + 16);
                    if ( v89 )
                    {
                      v62 = *v89;
                      if ( *v89 )
                      {
                        if ( *v88 < (unsigned int)v61 )
                        {
                          *v88 = v61;
                          Root = 122;
                        }
                        else
                        {
LABEL_95:
                          LODWORD(v93[10]) = 0;
                          LODWORD(v93[12]) = 0;
                          v93[11] = &v62[v60 + 2];
                          v93[9] = v62 + 2;
                          if ( v55 && *v55 )
                          {
                            if ( v51 && *v51 )
                              v63 = &v90;
                            else
                              LODWORD(v63) = 0;
                            v64 = &Str1;
                            if ( !v57 )
                              LODWORD(v64) = 0;
                            v65 = PackProviderNodeRef(v87[0], (_DWORD)v64, (_DWORD)v63, 0, (__int64)v93);
                          }
                          else if ( v51 && *v51 )
                          {
                            v65 = PackFunctionRefs(&Str1, &v90, 0, v93);
                          }
                          else
                          {
                            v65 = PackInterfaceRefs(&Str1, v93, v59, 0);
                          }
                          Root = v65;
                          if ( v65 )
                          {
                            if ( v62 && v62 != (_QWORD *)*v89 )
                              BCryptFree(v62);
                          }
                          else
                          {
                            v62[1] = v93[9];
                            *(_DWORD *)v62 = v93[10];
                            v66 = v60 * 8 + LODWORD(v93[12]) + 16;
                            *v89 = (PCRYPT_PROVIDER_REFS)v62;
                            *v88 = v66;
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
                      *v88 = v61;
                    }
                  }
                }
              }
              else
              {
                if ( v94 && *v94 )
                  v68 = PackFunctionRefs(&Str1, &v90, 0, v93);
                else
                  v68 = PackInterfaceRefs(&Str1, v93, v54, v53);
                v19 = v85;
                Root = v68;
                if ( !v68 )
                {
                  v57 = v78;
                  goto LABEL_92;
                }
              }
            }
            else
            {
              v19 = v85;
              Root = 1168;
            }
            v20 = v75;
LABEL_106:
            ExReleaseResourceLite((PERESOURCE)v20);
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
            if ( v40 && (_DWORD)v80 && v38 - 1 <= 0x7FFFFFFD )
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
              v38 = HIDWORD(v80);
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
      v69 = _CfgFind(65552, (unsigned int)&v76, 0, 0, Object, v20, 1, (__int64)pszContext, 0, 0, 0);
      Root = v69;
      if ( v69 && v69 != 1168 )
        goto LABEL_106;
      v93[3] = v76;
      v70 = 0;
      if ( v76 )
        v70 = (*(_BYTE *)(v76 + 16) & 1) != 0;
      v71 = _CfgFind(65552, (unsigned int)&v76, 0, 0, Objectb, v20, 2, (__int64)pszContext, 0, 0, 0);
      Root = v71;
      if ( v71 )
      {
        if ( v71 != 1168 )
          goto LABEL_106;
      }
      v93[5] = v76;
      if ( v76 && (*(_BYTE *)(v76 + 16) & 1) != 0 )
        v70 = 1;
      if ( v93[3] || v76 )
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
0x180028b40  push    rbp
0x180028b42  push    rbx
0x180028b43  push    rsi
0x180028b44  push    rdi
0x180028b45  push    r13
0x180028b47  push    r14
0x180028b49  lea     rbp, [rsp-178h]
0x180028b51  sub     rsp, 278h
0x180028b58  mov     rax, cs:__security_cookie
0x180028b5f  xor     rax, rsp
0x180028b62  mov     [rbp+1A0h+var_50], rax
0x180028b69  mov     rax, [rbp+1A0h+ppBuffer]
0x180028b70  mov     rbx, r8
0x180028b73  mov     rsi, [rbp+1A0h+pcbBuffer]
0x180028b7a  xor     edi, edi
0x180028b7c  mov     r13d, edx
0x180028b7f  mov     [rsp+2A0h+var_22C], edx
0x180028b83  mov     r14, rcx
0x180028b86  mov     [rbp+1A0h+var_100], rbx
0x180028b8d  xor     edx, edx; Val
0x180028b8f  mov     [rbp+1A0h+var_1D8], rsi
0x180028b93  mov     r8d, 0A0h; Size
0x180028b99  mov     [rbp+1A0h+var_1D0], rax
0x180028b9d  lea     rcx, [rbp+1A0h+var_1A0]; void *
0x180028ba1  mov     qword ptr [rbp+1A0h+var_1E0], rdi
0x180028ba5  mov     [rsp+2A0h+var_238], rdi
0x180028baa  mov     [rsp+2A0h+var_230], edi
0x180028bae  mov     [rbp+1A0h+var_F8], r9
0x180028bb5  call    memset
0x180028bba  lea     rax, [rbp+1A0h+var_90]
0x180028bc1  mov     [rbp+1A0h+var_220], 20h ; ' '
0x180028bc9  mov     [rsp+2A0h+Str1], rax
0x180028bce  xorps   xmm0, xmm0
0x180028bd1  xor     eax, eax
0x180028bd3  mov     [rbp+1A0h+var_218], rdi
0x180028bd7  mov     [rbp+1A0h+var_1B8], rax
0x180028bdb  mov     eax, cs:g_TrustedEnvironment
0x180028be1  mov     [rbp+1A0h+var_1E8], rdi
0x180028be5  movups  [rbp+1A0h+var_1C8], xmm0
0x180028be9  test    eax, eax
0x180028beb  jz      loc_1800294A8
0x180028bf1  mov     [rsp+2A0h+var_38], r15
0x180028bf9  test    al, 2
0x180028bfb  jnz     loc_180029568
0x180028c01  mov     edi, cs:g_SiloSlot
0x180028c07  call    cs:__imp_PsGetCurrentServerSilo
0x180028c0e  nop     dword ptr [rax+rax+00h]
0x180028c13  lea     r8, [rbp+1A0h+var_1E8]
0x180028c17  mov     edx, edi
0x180028c19  mov     rcx, rax
0x180028c1c  call    cs:__imp_PsGetPermanentSiloContext
0x180028c23  nop     dword ptr [rax+rax+00h]
0x180028c28  mov     r15, [rbp+1A0h+var_1E8]
0x180028c2c  mov     [rsp+2A0h+var_30], r12
0x180028c34  test    r13d, r13d
0x180028c37  jz      short loc_180028C54
0x180028c39  lea     eax, [r13-1]
0x180028c3d  cmp     eax, 7
0x180028c40  jbe     short loc_180028C67
0x180028c42  lea     eax, [r13-10001h]
0x180028c49  cmp     eax, 3
0x180028c4c  ja      loc_180029641
0x180028c52  jmp     short loc_180028C67
0x180028c54  test    rbx, rbx
0x180028c57  jz      loc_180029641
0x180028c5d  cmp     word ptr [rbx], 0
0x180028c61  jz      loc_180029641
0x180028c67  mov     edi, [rbp+1A0h+dwMode]
0x180028c6d  cmp     edi, 2
0x180028c70  jnz     loc_180029629
0x180028c76  test    rsi, rsi
0x180028c79  jz      loc_180029641
0x180028c7f  mov     esi, [rbp+1A0h+dwFlags]
0x180028c85  test    esi, 0FFFFFFFCh
0x180028c8b  jnz     loc_180029690
0x180028c91  xor     edx, edx; Val
0x180028c93  lea     rcx, [rbp+1A0h+var_188]; void *
0x180028c97  mov     r8d, 88h; Size
0x180028c9d  call    memset
0x180028ca2  xorps   xmm1, xmm1
0x180028ca5  mov     [rbp+1A0h+var_18C], esi
0x180028ca8  xorps   xmm0, xmm0
0x180028cab  mov     [rbp+1A0h+var_190], edi
0x180028cae  lea     r12, [r15+8]
0x180028cb2  add     r15, 88h
0x180028cb9  xor     eax, eax
0x180028cbb  mov     [rbp+1A0h+var_1F0], r12
0x180028cbf  movups  xmmword ptr [rbp+1A0h+Destination], xmm0
0x180028cc3  mov     [rbp+1A0h+var_1F4], eax
0x180028cc6  lea     rsi, Source; "System\\CurrentControlSet\\Control\\Cry"...
0x180028ccd  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180028cd4  mov     [rbp+1A0h+KeyHandle], rax
0x180028cd8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028cdf  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.Length], xmm1
0x180028ce6  mov     [rbp+1A0h+var_1A0], r12
0x180028cea  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.ObjectName], xmm1
0x180028cf1  mov     [rsp+2A0h+var_240], r15
0x180028cf6  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180028cfd  mov     [rbp+1A0h+var_198], r15
0x180028d01  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180028d08  movups  xmmword ptr [rbp+1A0h+Source], xmm0
0x180028d0f  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180028d17  movups  [rbp+1A0h+var_B0], xmm1
0x180028d1e  movsd   qword ptr [rbp+1A0h+var_B0+0Eh], xmm0
0x180028d26  nop     word ptr [rax+rax+00000000h]
0x180028d30  cmp     word ptr [rsi+rax*2+2], 0
0x180028d36  lea     rax, [rax+1]
0x180028d3a  jnz     short loc_180028D30
0x180028d3c  lea     edi, ds:26h[rax*2]
0x180028d43  mov     eax, cs:g_TrustedEnvironment
0x180028d49  test    eax, eax
0x180028d4b  jz      loc_1800295DF
0x180028d51  mov     edx, edi
0x180028d53  mov     r8d, 62676E43h
0x180028d59  test    al, 2
0x180028d5b  jnz     loc_1800295FC
0x180028d61  mov     ecx, 40h ; '@'
0x180028d66  call    cs:__imp_ExAllocatePool2
0x180028d6d  nop     dword ptr [rax+rax+00h]
0x180028d72  mov     qword ptr [rbp+1A0h+Destination+8], rax
0x180028d76  test    rax, rax
0x180028d79  jz      loc_1800296FD
0x180028d7f  xor     eax, eax
0x180028d81  mov     word ptr [rbp+1A0h+Destination+2], di
0x180028d85  lea     rdx, [rbp+1A0h+Source]; Source
0x180028d8c  mov     word ptr [rbp+1A0h+Destination], ax
0x180028d90  lea     rcx, [rbp+1A0h+Destination]; Destination
0x180028d94  call    cs:__imp_RtlAppendUnicodeToString
0x180028d9b  nop     dword ptr [rax+rax+00h]
0x180028da0  mov     rdx, rsi; Source
0x180028da3  lea     rcx, [rbp+1A0h+Destination]; Destination
0x180028da7  call    cs:__imp_RtlAppendUnicodeToString
0x180028dae  nop     dword ptr [rax+rax+00h]
0x180028db3  lea     rax, [rbp+1A0h+Destination]
0x180028db7  mov     [rbp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x180028dc1  xorps   xmm0, xmm0
0x180028dc4  mov     [rbp+1A0h+ObjectAttributes.ObjectName], rax
0x180028dcb  lea     r8, [rbp+1A0h+ObjectAttributes]; ObjectAttributes
0x180028dd2  mov     [rbp+1A0h+ObjectAttributes.RootDirectory], 0
0x180028ddd  mov     edx, 20019h; DesiredAccess
0x180028de2  mov     [rbp+1A0h+ObjectAttributes.Attributes], 240h
0x180028dec  lea     rcx, [rbp+1A0h+KeyHandle]; KeyHandle
0x180028df0  movdqu  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028df8  call    cs:__imp_ZwOpenKey
0x180028dff  nop     dword ptr [rax+rax+00h]
0x180028e04  mov     rdi, qword ptr [rbp+1A0h+Destination+8]
0x180028e08  mov     esi, eax
0x180028e0a  test    rdi, rdi
0x180028e0d  jz      short loc_180028E39
0x180028e0f  mov     eax, cs:g_TrustedEnvironment
0x180028e15  test    eax, eax
0x180028e17  jz      loc_180029165
0x180028e1d  test    al, 2
0x180028e1f  jnz     loc_18002952F
0x180028e25  mov     edx, 62676E43h; Tag
0x180028e2a  mov     rcx, rdi; P
0x180028e2d  call    cs:__imp_ExFreePoolWithTag
0x180028e34  nop     dword ptr [rax+rax+00h]
0x180028e39  mov     ecx, esi; Status
0x180028e3b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180028e42  nop     dword ptr [rax+rax+00h]
0x180028e47  mov     edi, eax
0x180028e49  test    eax, eax
0x180028e4b  jnz     loc_1800293BC
0x180028e51  mov     rdi, [rbp+1A0h+KeyHandle]
0x180028e55  xor     eax, eax
0x180028e57  mov     qword ptr [rbp+1A0h+Destination], rax
0x180028e5b  xor     r9d, r9d; AccessMode
0x180028e5e  mov     [rbp+1A0h+var_1B0], rax
0x180028e62  xor     r8d, r8d; ObjectType
0x180028e65  lea     rax, [rbp+1A0h+Destination]
0x180028e69  xor     edx, edx; DesiredAccess
0x180028e6b  mov     [rsp+2A0h+HandleInformation], rax; HandleInformation
0x180028e70  mov     rcx, rdi; Handle
0x180028e73  lea     rax, [rbp+1A0h+var_1B0]
0x180028e77  mov     [rsp+2A0h+Object], rax; int
0x180028e7c  call    cs:__imp_ObReferenceObjectByHandle
0x180028e83  nop     dword ptr [rax+rax+00h]
0x180028e88  test    eax, eax
0x180028e8a  js      short loc_180028EAB
0x180028e8c  mov     rcx, [rbp+1A0h+var_1B0]; Object
0x180028e90  call    cs:__imp_ObfDereferenceObject
0x180028e97  nop     dword ptr [rax+rax+00h]
0x180028e9c  mov     rcx, rdi; Handle
0x180028e9f  call    cs:__imp_ZwClose
0x180028ea6  nop     dword ptr [rax+rax+00h]
0x180028eab  mov     eax, [r12+78h]
0x180028eb0  mov     esi, 1
0x180028eb5  test    eax, eax
0x180028eb7  jz      loc_180029593
0x180028ebd  call    cs:__imp_KeEnterCriticalRegion
0x180028ec4  nop     dword ptr [rax+rax+00h]
0x180028ec9  movzx   edx, sil; Wait
0x180028ecd  mov     rcx, r12; Resource
0x180028ed0  call    cs:__imp_ExAcquireResourceSharedLite
0x180028ed7  nop     dword ptr [rax+rax+00h]
0x180028edc  lea     rax, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180028ee3  mov     dword ptr [rbp+1A0h+Destination+8], 3Ch ; '<'
0x180028eea  mov     qword ptr [rbp+1A0h+Destination], rax
0x180028eee  lea     rdx, [rbp+1A0h+Destination]
0x180028ef2  xor     eax, eax
0x180028ef4  mov     qword ptr [rbp+1A0h+Destination+0Ch], 3Bh ; ';'
0x180028efc  mov     r8d, 20019h
0x180028f02  mov     [rbp+1A0h+var_1F4], eax
0x180028f05  call    VerifyRegistryAccess
0x180028f0a  mov     edi, eax
0x180028f0c  test    eax, eax
0x180028f0e  jnz     loc_1800293A1
0x180028f14  mov     eax, [r15+78h]
0x180028f18  test    eax, eax
0x180028f1a  jz      loc_1800294D8
0x180028f20  call    cs:__imp_KeEnterCriticalRegion
0x180028f27  nop     dword ptr [rax+rax+00h]
0x180028f2c  movzx   edx, sil; Wait
0x180028f30  mov     rcx, r15; Resource
0x180028f33  call    cs:__imp_ExAcquireResourceSharedLite
0x180028f3a  nop     dword ptr [rax+rax+00h]
0x180028f3f  test    rbx, rbx
0x180028f42  jz      short loc_180028FAA
0x180028f44  cmp     word ptr [rbx], 0
0x180028f48  jz      short loc_180028FAA
0x180028f4a  xor     edi, edi
0x180028f4c  lea     rdx, [rbp+1A0h+KeyHandle]
0x180028f50  xor     r8d, r8d
0x180028f53  mov     dword ptr [rbp+1A0h+KeyHandle], edi
0x180028f56  mov     rcx, rbx
0x180028f59  call    SzString_CchLength
0x180028f5e  test    eax, eax
0x180028f60  jnz     loc_180029192
0x180028f66  mov     ecx, dword ptr [rbp+1A0h+KeyHandle]
0x180028f69  lea     r9, [rsp+2A0h+var_230]
0x180028f6e  mov     dword ptr [rbp+1A0h+var_1C8+0Ch], ecx
0x180028f71  lea     r8, [rbp+1A0h+var_1C8]
0x180028f75  mov     rdx, r15
0x180028f78  mov     qword ptr [rbp+1A0h+var_1C8], rbx
0x180028f7c  mov     dword ptr [rbp+1A0h+var_1B8], edi
0x180028f7f  lea     eax, [rcx+1]
0x180028f82  mov     rcx, r12
0x180028f85  mov     dword ptr [rbp+1A0h+var_1C8+8], eax
0x180028f88  call    _DetermineFunctionInterface
0x180028f8d  mov     edi, eax
0x180028f8f  test    r13d, r13d
0x180028f92  jnz     loc_18002948B
0x180028f98  test    eax, eax
0x180028f9a  jnz     loc_180029386
0x180028fa0  mov     r13d, [rsp+2A0h+var_230]
0x180028fa5  mov     [rsp+2A0h+var_22C], r13d
0x180028faa  mov     rcx, [rsp+2A0h+Str1]
0x180028faf  test    rcx, rcx
0x180028fb2  jz      loc_180029192
0x180028fb8  mov     eax, dword ptr [rbp+1A0h+var_220]
0x180028fbb  test    eax, eax
0x180028fbd  jz      loc_180029192
0x180028fc3  cmp     dword ptr [rbp+1A0h+var_220+4], 7FFFFFFFh
0x180028fca  jnb     loc_180029192
0x180028fd0  cmp     eax, 9
0x180028fd3  jb      loc_180029192
0x180028fd9  xor     eax, eax
0x180028fdb  lea     r8, a08x; "%08X"
0x180028fe2  mov     [rcx], ax
0x180028fe5  mov     r9d, r13d
0x180028fe8  mov     edx, dword ptr [rbp+1A0h+var_220]; unsigned __int64
0x180028feb  mov     rcx, [rsp+2A0h+Str1]; unsigned __int16 *
0x180028ff0  mov     dword ptr [rbp+1A0h+var_220+4], 8
0x180028ff7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028ffc  test    eax, eax
0x180028ffe  js      loc_1800296AA
0x180029004  test    r14, r14
0x180029007  jnz     loc_1800A0934
0x18002900d  xor     r14d, r14d
0x180029010  lea     rdx, [rsp+2A0h+var_238]
0x180029015  mov     [rsp+2A0h+var_250], r14
0x18002901a  xor     r9d, r9d
0x18002901d  mov     [rsp+2A0h+var_258], r14
0x180029022  xor     r8d, r8d
0x180029025  mov     [rsp+2A0h+var_260], r14d
0x18002902a  mov     ecx, 10010h
0x18002902f  mov     qword ptr [rsp+2A0h+var_268], r14
0x180029034  mov     dword ptr [rsp+2A0h+Str2], esi
0x180029038  mov     [rsp+2A0h+HandleInformation], r15
0x18002903d  call    __CfgFind
0x180029042  mov     edi, eax
0x180029044  test    eax, eax
0x180029046  jnz     loc_180029612
0x18002904c  mov     rax, [rsp+2A0h+var_238]
0x180029051  lea     rdx, [rsp+2A0h+var_238]
0x180029056  mov     [rsp+2A0h+var_250], r14
0x18002905b  xor     r9d, r9d
0x18002905e  mov     [rsp+2A0h+var_258], r14
0x180029063  xor     r8d, r8d
0x180029066  mov     [rsp+2A0h+var_260], r14d
0x18002906b  mov     ecx, 10010h
0x180029070  mov     qword ptr [rsp+2A0h+var_268], r14
0x180029075  mov     dword ptr [rsp+2A0h+Str2], 2
0x18002907d  mov     [rsp+2A0h+HandleInformation], r15
0x180029082  mov     [rbp+1A0h+var_180], rax
0x180029086  call    __CfgFind
0x18002908b  mov     edi, eax
0x18002908d  test    eax, eax
0x18002908f  jnz     loc_180029182
  ... truncated ...
```
