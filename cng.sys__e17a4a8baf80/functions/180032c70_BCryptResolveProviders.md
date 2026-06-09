# BCryptResolveProviders

- ea: `0x180032c70`
- end: `0x180033837`
- name: `BCryptResolveProviders`
- size: `3015`
- prototype: `NTSTATUS __stdcall(LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, LPCWSTR pszProvider, ULONG dwMode, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *ppBuffer)`
- caller_count: `6`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b898`
- `0x180030690`
- `0x180043cd0`
- `0x180062c60`
- `0x180063010`
- `0x180066d00`

## callees

- `0x180025ec0`
- `0x180025fb0`
- `0x180031560`
- `0x180031850`
- `0x180031d90`
- `0x180031e30`
- `0x1800325b0`
- `0x180032880`
- `0x180032b10`
- `0x180032c70`
- `0x180033840`
- `0x1800341b0`
- `0x1800360b8`
- `0x180040358`
- `0x18004058c`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180032e96`
- `ntoskrnl!ExAllocatePool2` at `0x180032e96`
- `ntoskrnl!ExFreePoolWithTag` at `0x180032f5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180032f5d`
- `ntoskrnl!ZwClose` at `0x180032fcf`
- `ntoskrnl!ZwClose` at `0x180032fcf`
- `ntoskrnl!ObfDereferenceObject` at `0x180032fc0`
- `ntoskrnl!ObfDereferenceObject` at `0x180032fc0`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180032d37`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180032d37`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180032d4c`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180032d4c`
- `ntoskrnl!ZwOpenKey` at `0x180032f28`
- `ntoskrnl!ZwOpenKey` at `0x180032f28`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180032fed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180033050`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180033608`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800336c3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180032fed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180033050`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180033608`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800336c3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18003361b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800336d6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18003361b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800336d6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180033000`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180033063`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180033000`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180033063`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800334b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800334d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180033636`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800336f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800334b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800334d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180033636`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800336f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800334c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800334e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180033642`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800336fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800334c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800334e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180033642`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800336fe`
- `ntoskrnl!SkIsSecureKernel` at `0x180033295`
- `ntoskrnl!SkIsSecureKernel` at `0x1800335d8`
- `ntoskrnl!SkIsSecureKernel` at `0x18003370f`
- `ntoskrnl!SkIsSecureKernel` at `0x180033295`
- `ntoskrnl!SkIsSecureKernel` at `0x1800335d8`
- `ntoskrnl!SkIsSecureKernel` at `0x18003370f`
- `ntoskrnl!SkAllocatePool` at `0x180033731`
- `ntoskrnl!SkAllocatePool` at `0x180033731`
- `ntoskrnl!SkFreePool` at `0x180033667`
- `ntoskrnl!SkFreePool` at `0x180033667`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180032fac`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180032fac`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032ec4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032ed7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032ec4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032ed7`
- `ntoskrnl!_wcsnicmp` at `0x1800332e1`
- `ntoskrnl!_wcsnicmp` at `0x1800332e1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180032f6b`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180032f6b`

## string_xrefs

- `0x18003300c`: `System\CurrentControlSet\Control\Cryptography\Configuration`
- `0x180032dfd`: `\Registry\Machine\`

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
  NTSTATUS v34; // eax
  NTSTATUS v35; // eax
  NTSTATUS v36; // eax
  unsigned int v37; // r9d
  int v38; // r13d
  wchar_t *v39; // r10
  __int64 v40; // rsi
  __int64 v41; // rax
  __int64 v42; // r15
  unsigned int v43; // r12d
  unsigned int i; // edi
  __int64 *v45; // rcx
  __int64 v46; // rcx
  BOOL v47; // ecx
  unsigned int v48; // r8d
  int v49; // eax
  _WORD *v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // r9
  __int64 v53; // r8
  wchar_t *v54; // r13
  __int128 *v55; // r8
  ULONG v56; // r15d
  wchar_t **p_Str1; // rdx
  __int64 v58; // r8
  unsigned int v59; // r14d
  __int64 v60; // rcx
  _QWORD *v61; // rsi
  __int128 *v62; // r8
  wchar_t **v63; // rdx
  NTSTATUS v64; // eax
  ULONG v65; // ecx
  NTSTATUS v67; // eax
  NTSTATUS v68; // eax
  BOOL v69; // esi
  NTSTATUS v70; // eax
  int Object; // [rsp+20h] [rbp-E0h]
  int Objecta; // [rsp+20h] [rbp-E0h]
  int Objectb; // [rsp+20h] [rbp-E0h]
  __int64 v74; // [rsp+60h] [rbp-A0h]
  __int64 v75; // [rsp+68h] [rbp-98h] BYREF
  ULONG v76; // [rsp+70h] [rbp-90h] BYREF
  ULONG v77; // [rsp+74h] [rbp-8Ch]
  wchar_t *Str1; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v79; // [rsp+80h] [rbp-80h]
  __int64 v80; // [rsp+88h] [rbp-78h]
  void *KeyHandle; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Destination[20]; // [rsp+98h] [rbp-68h] BYREF
  int v83; // [rsp+ACh] [rbp-54h]
  __int64 v84; // [rsp+B0h] [rbp-50h]
  void *v85; // [rsp+B8h] [rbp-48h] BYREF
  int v86[2]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG *v87; // [rsp+C8h] [rbp-38h]
  PCRYPT_PROVIDER_REFS *v88; // [rsp+D0h] [rbp-30h]
  __int128 v89; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v90; // [rsp+E8h] [rbp-18h]
  PVOID v91; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v92[20]; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR v93; // [rsp+1A0h] [rbp+A0h]
  wchar_t *Str2; // [rsp+1A8h] [rbp+A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR Source[24]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v97; // [rsp+210h] [rbp+110h] BYREF

  v9 = dwInterface;
  v77 = dwInterface;
  v93 = pszFunction;
  v87 = pcbBuffer;
  v88 = ppBuffer;
  *(_QWORD *)v86 = 0;
  v75 = 0;
  v76 = 0;
  Str2 = (wchar_t *)pszProvider;
  memset(v92, 0, sizeof(v92));
  v79 = 32;
  Str1 = (wchar_t *)&v97;
  v80 = 0;
  v90 = 0;
  LOBYTE(v13) = g_TrustedEnvironment;
  v85 = 0;
  v89 = 0;
  if ( !g_TrustedEnvironment )
  {
    v13 = ((int)SkIsSecureKernel(v12, v11) >> 31) + 2;
    g_TrustedEnvironment = v13;
  }
  if ( (v13 & 2) != 0 )
  {
    v16 = &pGlobalConfigContext;
    v85 = &pGlobalConfigContext;
  }
  else
  {
    v14 = g_SiloSlot;
    CurrentServerSilo = PsGetCurrentServerSilo();
    PsGetPermanentSiloContext(CurrentServerSilo, v14, &v85);
    v16 = v85;
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
  memset(&v92[3], 0, 0x88u);
  HIDWORD(v92[2]) = dwFlags;
  LODWORD(v92[2]) = dwMode;
  v19 = (__int64)v16 + 8;
  v20 = (__int64)v16 + 136;
  v84 = v19;
  *(_OWORD *)Destination = 0;
  v83 = 0;
  KeyHandle = 0;
  v21 = -1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v92[0] = v19;
  v74 = v20;
  v92[1] = v20;
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
    v91 = 0;
    if ( ObReferenceObjectByHandle(KeyHandle, 0, 0, 0, &v91, (POBJECT_HANDLE_INFORMATION)Destination) >= 0 )
    {
      ObfDereferenceObject(v91);
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
    v83 = 0;
    Root = VerifyRegistryAccess(v33, Destination);
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
      if ( (unsigned int)SzString_CchLength(pszFunction, &KeyHandle, 0) )
        goto LABEL_70;
      HIDWORD(v89) = (_DWORD)KeyHandle;
      *(_QWORD *)&v89 = pszFunction;
      LODWORD(v90) = 0;
      DWORD2(v89) = (_DWORD)KeyHandle + 1;
      v34 = DetermineFunctionInterface(v19, v20, &v89, &v76);
      Root = v34;
      if ( v9 )
      {
        if ( v34 && v34 != 1168 )
          goto LABEL_106;
        if ( v9 != v76 )
          goto LABEL_124;
      }
      else
      {
        if ( v34 )
          goto LABEL_106;
        v9 = v76;
        v77 = v76;
      }
    }
    if ( Str1 && (_DWORD)v79 && HIDWORD(v79) < 0x7FFFFFFF && (unsigned int)v79 >= 9 )
    {
      *Str1 = 0;
      HIDWORD(v79) = 8;
      if ( (int)StringCchPrintfW(Str1, (unsigned int)v79, L"%08X", v9) < 0 )
      {
        Root = 13;
        goto LABEL_106;
      }
      if ( !pszContext || !*pszContext )
      {
LABEL_44:
        v35 = _CfgFind(65552, (unsigned int)&v75, 0, 0, Object, v20, 1, 0, 0, 0, 0);
        Root = v35;
        if ( v35 && v35 != 1168 )
          goto LABEL_106;
        v92[4] = v75;
        v36 = _CfgFind(65552, (unsigned int)&v75, 0, 0, Objecta, v20, 2, 0, 0, 0, 0);
        Root = v36;
        if ( v36 )
        {
          if ( v36 != 1168 )
            goto LABEL_106;
        }
        v92[6] = v75;
LABEL_47:
        v37 = HIDWORD(v79);
        v38 = 0;
        v39 = Str1;
        v40 = 0;
        while ( 1 )
        {
          v41 = v92[v40 + 3];
          if ( v41 )
          {
            v42 = *(_QWORD *)(v41 + 24);
            if ( v42 )
              break;
          }
LABEL_77:
          if ( ++v40 == 4 )
          {
            v50 = v93;
            if ( v38 )
            {
              v51 = v92[5];
              if ( v92[5] && (*(_DWORD *)(v92[5] + 16LL) & 0x10000) != 0 )
              {
                v52 = v92[3];
                v53 = v92[5];
                v51 = v92[4];
                v92[5] = v92[4];
                v92[4] = v92[3];
                v92[3] = v53;
              }
              else
              {
                v52 = v92[4];
                v53 = v92[3];
              }
              if ( v92[6] && (*(_DWORD *)(v92[6] + 16LL) & 0x10000) != 0 )
              {
                if ( v53 && (*(_DWORD *)(v53 + 16) & 0x10000) != 0 )
                {
                  v92[4] = v92[6];
                }
                else
                {
                  v92[4] = v53;
                  v92[3] = v92[6];
                }
                v92[5] = v52;
                v92[6] = v51;
              }
              v54 = Str2;
              if ( Str2 && *Str2 )
              {
                v19 = v84;
                Root = _PrvFind(0, (int)v86, v53, 0, Object, v84, Str2, 0);
                if ( !Root )
                {
                  if ( v50 && *v50 )
                    v55 = &v89;
                  else
                    LODWORD(v55) = 0;
                  v56 = v77;
                  p_Str1 = &Str1;
                  if ( !v77 )
                    LODWORD(p_Str1) = 0;
                  Root = PackProviderNodeRef(v86[0], (_DWORD)p_Str1, (_DWORD)v55, 0, (__int64)v92);
                  if ( !Root )
                  {
LABEL_92:
                    v59 = v92[10];
                    v60 = (unsigned int)(8 * LODWORD(v92[10]) + LODWORD(v92[12]) + 16);
                    if ( v88 )
                    {
                      v61 = *v88;
                      if ( *v88 )
                      {
                        if ( *v87 < (unsigned int)v60 )
                        {
                          *v87 = v60;
                          Root = 122;
                        }
                        else
                        {
LABEL_95:
                          LODWORD(v92[10]) = 0;
                          LODWORD(v92[12]) = 0;
                          v92[11] = &v61[v59 + 2];
                          v92[9] = v61 + 2;
                          if ( v54 && *v54 )
                          {
                            if ( v50 && *v50 )
                              v62 = &v89;
                            else
                              LODWORD(v62) = 0;
                            v63 = &Str1;
                            if ( !v56 )
                              LODWORD(v63) = 0;
                            v64 = PackProviderNodeRef(v86[0], (_DWORD)v63, (_DWORD)v62, 0, (__int64)v92);
                          }
                          else if ( v50 && *v50 )
                          {
                            v64 = PackFunctionRefs(&Str1, &v89, 0, v92);
                          }
                          else
                          {
                            v64 = PackInterfaceRefs(&Str1, v92, v58, 0);
                          }
                          Root = v64;
                          if ( v64 )
                          {
                            if ( v61 && v61 != (_QWORD *)*v88 )
                              BCryptFree(v61);
                          }
                          else
                          {
                            v61[1] = v92[9];
                            *(_DWORD *)v61 = v92[10];
                            v65 = v59 * 8 + LODWORD(v92[12]) + 16;
                            *v88 = (PCRYPT_PROVIDER_REFS)v61;
                            *v87 = v65;
                          }
                        }
                      }
                      else
                      {
                        v61 = (_QWORD *)BCryptAlloc(v60);
                        if ( v61 )
                          goto LABEL_95;
                        Root = 8;
                      }
                    }
                    else
                    {
                      Root = 0;
                      *v87 = v60;
                    }
                  }
                }
              }
              else
              {
                if ( v93 && *v93 )
                  v67 = PackFunctionRefs(&Str1, &v89, 0, v92);
                else
                  v67 = PackInterfaceRefs(&Str1, v92, v53, v52);
                v19 = v84;
                Root = v67;
                if ( !v67 )
                {
                  v56 = v77;
                  goto LABEL_92;
                }
              }
            }
            else
            {
              v19 = v84;
              Root = 1168;
            }
            v20 = v74;
LABEL_106:
            ExReleaseResourceLite((PERESOURCE)v20);
            KeLeaveCriticalRegion();
LABEL_107:
            ExReleaseResourceLite((PERESOURCE)v19);
            KeLeaveCriticalRegion();
            return WinErrorToNtStatus(Root);
          }
        }
        v43 = *(_DWORD *)(v41 + 20);
        for ( i = 0; ; ++i )
        {
          if ( i >= v43 )
            goto LABEL_77;
          v45 = *(__int64 **)(v42 + 8LL * i);
          if ( v45 && *((_DWORD *)v45 + 2) != 2 )
          {
            v46 = *v45;
            if ( v39 && (_DWORD)v79 && v37 - 1 <= 0x7FFFFFFD )
            {
              if ( !v46 )
                continue;
              if ( !*(_QWORD *)v46 )
                continue;
              if ( !*(_DWORD *)(v46 + 8) )
                continue;
              v48 = *(_DWORD *)(v46 + 12);
              if ( v37 > 0xFFFF || v48 - 1 > 0x7FFFFFFD || v48 > 0xFFFF || v37 != v48 )
                continue;
              v49 = _wcsnicmp(v39, *(const wchar_t **)v46, v37 + 1);
              v37 = HIDWORD(v79);
              v39 = Str1;
              v47 = v49 == 0;
            }
            else
            {
              v47 = !v46
                 || !*(_QWORD *)v46
                 || !*(_DWORD *)(v46 + 8)
                 || (unsigned int)(*(_DWORD *)(v46 + 12) - 1) > 0x7FFFFFFD;
            }
            if ( v47 )
            {
              if ( *(_QWORD *)(v42 + 8LL * i) )
                v38 = 1;
              goto LABEL_77;
            }
          }
        }
      }
      v68 = _CfgFind(65552, (unsigned int)&v75, 0, 0, Object, v20, 1, (__int64)pszContext, 0, 0, 0);
      Root = v68;
      if ( v68 && v68 != 1168 )
        goto LABEL_106;
      v92[3] = v75;
      v69 = 0;
      if ( v75 )
        v69 = (*(_BYTE *)(v75 + 16) & 1) != 0;
      v70 = _CfgFind(65552, (unsigned int)&v75, 0, 0, Objectb, v20, 2, (__int64)pszContext, 0, 0, 0);
      Root = v70;
      if ( v70 )
      {
        if ( v70 != 1168 )
          goto LABEL_106;
      }
      v92[5] = v75;
      if ( v75 && (*(_BYTE *)(v75 + 16) & 1) != 0 )
        v69 = 1;
      if ( v92[3] || v75 )
      {
        if ( v69 )
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
0x180032c70  push    rbp
0x180032c72  push    rbx
0x180032c73  push    rsi
0x180032c74  push    rdi
0x180032c75  push    r13
0x180032c77  push    r14
0x180032c79  lea     rbp, [rsp-178h]
0x180032c81  sub     rsp, 278h
0x180032c88  mov     rax, cs:__security_cookie
0x180032c8f  xor     rax, rsp
0x180032c92  mov     [rbp+1A0h+var_50], rax
0x180032c99  mov     rax, [rbp+1A0h+ppBuffer]
0x180032ca0  mov     rbx, r8
0x180032ca3  mov     rsi, [rbp+1A0h+pcbBuffer]
0x180032caa  xor     edi, edi
0x180032cac  mov     r13d, edx
0x180032caf  mov     [rsp+2A0h+var_22C], edx
0x180032cb3  mov     r14, rcx
0x180032cb6  mov     [rbp+1A0h+var_100], rbx
0x180032cbd  xor     edx, edx; Val
0x180032cbf  mov     [rbp+1A0h+var_1D8], rsi
0x180032cc3  mov     r8d, 0A0h; Size
0x180032cc9  mov     [rbp+1A0h+var_1D0], rax
0x180032ccd  lea     rcx, [rbp+1A0h+var_1A0]; void *
0x180032cd1  mov     qword ptr [rbp+1A0h+var_1E0], rdi
0x180032cd5  mov     [rsp+2A0h+var_238], rdi
0x180032cda  mov     [rsp+2A0h+var_230], edi
0x180032cde  mov     [rbp+1A0h+var_F8], r9
0x180032ce5  call    memset
0x180032cea  lea     rax, [rbp+1A0h+var_90]
0x180032cf1  mov     [rbp+1A0h+var_220], 20h ; ' '
0x180032cf9  mov     [rsp+2A0h+Str1], rax
0x180032cfe  xorps   xmm0, xmm0
0x180032d01  xor     eax, eax
0x180032d03  mov     [rbp+1A0h+var_218], rdi
0x180032d07  mov     [rbp+1A0h+var_1B8], rax
0x180032d0b  mov     eax, cs:g_TrustedEnvironment
0x180032d11  mov     [rbp+1A0h+var_1E8], rdi
0x180032d15  movups  [rbp+1A0h+var_1C8], xmm0
0x180032d19  test    eax, eax
0x180032d1b  jz      loc_1800335D8
0x180032d21  mov     [rsp+2A0h+var_38], r15
0x180032d29  test    al, 2
0x180032d2b  jnz     loc_180033698
0x180032d31  mov     edi, cs:g_SiloSlot
0x180032d37  call    cs:__imp_PsGetCurrentServerSilo
0x180032d3e  nop     dword ptr [rax+rax+00h]
0x180032d43  lea     r8, [rbp+1A0h+var_1E8]
0x180032d47  mov     edx, edi
0x180032d49  mov     rcx, rax
0x180032d4c  call    cs:__imp_PsGetPermanentSiloContext
0x180032d53  nop     dword ptr [rax+rax+00h]
0x180032d58  mov     r15, [rbp+1A0h+var_1E8]
0x180032d5c  mov     [rsp+2A0h+var_30], r12
0x180032d64  test    r13d, r13d
0x180032d67  jz      short loc_180032D84
0x180032d69  lea     eax, [r13-1]
0x180032d6d  cmp     eax, 7
0x180032d70  jbe     short loc_180032D97
0x180032d72  lea     eax, [r13-10001h]
0x180032d79  cmp     eax, 3
0x180032d7c  ja      loc_180033771
0x180032d82  jmp     short loc_180032D97
0x180032d84  test    rbx, rbx
0x180032d87  jz      loc_180033771
0x180032d8d  cmp     word ptr [rbx], 0
0x180032d91  jz      loc_180033771
0x180032d97  mov     edi, [rbp+1A0h+dwMode]
0x180032d9d  cmp     edi, 2
0x180032da0  jnz     loc_180033759
0x180032da6  test    rsi, rsi
0x180032da9  jz      loc_180033771
0x180032daf  mov     esi, [rbp+1A0h+dwFlags]
0x180032db5  test    esi, 0FFFFFFFCh
0x180032dbb  jnz     loc_1800337C0
0x180032dc1  xor     edx, edx; Val
0x180032dc3  lea     rcx, [rbp+1A0h+var_188]; void *
0x180032dc7  mov     r8d, 88h; Size
0x180032dcd  call    memset
0x180032dd2  xorps   xmm1, xmm1
0x180032dd5  mov     [rbp+1A0h+var_18C], esi
0x180032dd8  xorps   xmm0, xmm0
0x180032ddb  mov     [rbp+1A0h+var_190], edi
0x180032dde  lea     r12, [r15+8]
0x180032de2  add     r15, 88h
0x180032de9  xor     eax, eax
0x180032deb  mov     [rbp+1A0h+var_1F0], r12
0x180032def  movups  xmmword ptr [rbp+1A0h+Destination], xmm0
0x180032df3  mov     [rbp+1A0h+var_1F4], eax
0x180032df6  lea     rsi, Source; "System\\CurrentControlSet\\Control\\Cry"...
0x180032dfd  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180032e04  mov     [rbp+1A0h+KeyHandle], rax
0x180032e08  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180032e0f  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.Length], xmm1
0x180032e16  mov     [rbp+1A0h+var_1A0], r12
0x180032e1a  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.ObjectName], xmm1
0x180032e21  mov     [rsp+2A0h+var_240], r15
0x180032e26  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180032e2d  mov     [rbp+1A0h+var_198], r15
0x180032e31  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180032e38  movups  xmmword ptr [rbp+1A0h+Source], xmm0
0x180032e3f  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180032e47  movups  [rbp+1A0h+var_B0], xmm1
0x180032e4e  movsd   qword ptr [rbp+1A0h+var_B0+0Eh], xmm0
0x180032e56  nop     word ptr [rax+rax+00000000h]
0x180032e60  cmp     word ptr [rsi+rax*2+2], 0
0x180032e66  lea     rax, [rax+1]
0x180032e6a  jnz     short loc_180032E60
0x180032e6c  lea     edi, ds:26h[rax*2]
0x180032e73  mov     eax, cs:g_TrustedEnvironment
0x180032e79  test    eax, eax
0x180032e7b  jz      loc_18003370F
0x180032e81  mov     edx, edi
0x180032e83  mov     r8d, 62676E43h
0x180032e89  test    al, 2
0x180032e8b  jnz     loc_18003372C
0x180032e91  mov     ecx, 40h ; '@'
0x180032e96  call    cs:__imp_ExAllocatePool2
0x180032e9d  nop     dword ptr [rax+rax+00h]
0x180032ea2  mov     qword ptr [rbp+1A0h+Destination+8], rax
0x180032ea6  test    rax, rax
0x180032ea9  jz      loc_18003382D
0x180032eaf  xor     eax, eax
0x180032eb1  mov     word ptr [rbp+1A0h+Destination+2], di
0x180032eb5  lea     rdx, [rbp+1A0h+Source]; Source
0x180032ebc  mov     word ptr [rbp+1A0h+Destination], ax
0x180032ec0  lea     rcx, [rbp+1A0h+Destination]; Destination
0x180032ec4  call    cs:__imp_RtlAppendUnicodeToString
0x180032ecb  nop     dword ptr [rax+rax+00h]
0x180032ed0  mov     rdx, rsi; Source
0x180032ed3  lea     rcx, [rbp+1A0h+Destination]; Destination
0x180032ed7  call    cs:__imp_RtlAppendUnicodeToString
0x180032ede  nop     dword ptr [rax+rax+00h]
0x180032ee3  lea     rax, [rbp+1A0h+Destination]
0x180032ee7  mov     [rbp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x180032ef1  xorps   xmm0, xmm0
0x180032ef4  mov     [rbp+1A0h+ObjectAttributes.ObjectName], rax
0x180032efb  lea     r8, [rbp+1A0h+ObjectAttributes]; ObjectAttributes
0x180032f02  mov     [rbp+1A0h+ObjectAttributes.RootDirectory], 0
0x180032f0d  mov     edx, 20019h; DesiredAccess
0x180032f12  mov     [rbp+1A0h+ObjectAttributes.Attributes], 240h
0x180032f1c  lea     rcx, [rbp+1A0h+KeyHandle]; KeyHandle
0x180032f20  movdqu  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180032f28  call    cs:__imp_ZwOpenKey
0x180032f2f  nop     dword ptr [rax+rax+00h]
0x180032f34  mov     rdi, qword ptr [rbp+1A0h+Destination+8]
0x180032f38  mov     esi, eax
0x180032f3a  test    rdi, rdi
0x180032f3d  jz      short loc_180032F69
0x180032f3f  mov     eax, cs:g_TrustedEnvironment
0x180032f45  test    eax, eax
0x180032f47  jz      loc_180033295
0x180032f4d  test    al, 2
0x180032f4f  jnz     loc_18003365F
0x180032f55  mov     edx, 62676E43h; Tag
0x180032f5a  mov     rcx, rdi; P
0x180032f5d  call    cs:__imp_ExFreePoolWithTag
0x180032f64  nop     dword ptr [rax+rax+00h]
0x180032f69  mov     ecx, esi; Status
0x180032f6b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180032f72  nop     dword ptr [rax+rax+00h]
0x180032f77  mov     edi, eax
0x180032f79  test    eax, eax
0x180032f7b  jnz     loc_1800334EC
0x180032f81  mov     rdi, [rbp+1A0h+KeyHandle]
0x180032f85  xor     eax, eax
0x180032f87  mov     qword ptr [rbp+1A0h+Destination], rax
0x180032f8b  xor     r9d, r9d; AccessMode
0x180032f8e  mov     [rbp+1A0h+var_1B0], rax
0x180032f92  xor     r8d, r8d; ObjectType
0x180032f95  lea     rax, [rbp+1A0h+Destination]
0x180032f99  xor     edx, edx; DesiredAccess
0x180032f9b  mov     [rsp+2A0h+HandleInformation], rax; HandleInformation
0x180032fa0  mov     rcx, rdi; Handle
0x180032fa3  lea     rax, [rbp+1A0h+var_1B0]
0x180032fa7  mov     [rsp+2A0h+Object], rax; int
0x180032fac  call    cs:__imp_ObReferenceObjectByHandle
0x180032fb3  nop     dword ptr [rax+rax+00h]
0x180032fb8  test    eax, eax
0x180032fba  js      short loc_180032FDB
0x180032fbc  mov     rcx, [rbp+1A0h+var_1B0]; Object
0x180032fc0  call    cs:__imp_ObfDereferenceObject
0x180032fc7  nop     dword ptr [rax+rax+00h]
0x180032fcc  mov     rcx, rdi; Handle
0x180032fcf  call    cs:__imp_ZwClose
0x180032fd6  nop     dword ptr [rax+rax+00h]
0x180032fdb  mov     eax, [r12+78h]
0x180032fe0  mov     esi, 1
0x180032fe5  test    eax, eax
0x180032fe7  jz      loc_1800336C3
0x180032fed  call    cs:__imp_KeEnterCriticalRegion
0x180032ff4  nop     dword ptr [rax+rax+00h]
0x180032ff9  movzx   edx, sil; Wait
0x180032ffd  mov     rcx, r12; Resource
0x180033000  call    cs:__imp_ExAcquireResourceSharedLite
0x180033007  nop     dword ptr [rax+rax+00h]
0x18003300c  lea     rax, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cry"...
0x180033013  mov     dword ptr [rbp+1A0h+Destination+8], 3Ch ; '<'
0x18003301a  mov     qword ptr [rbp+1A0h+Destination], rax
0x18003301e  lea     rdx, [rbp+1A0h+Destination]
0x180033022  xor     eax, eax
0x180033024  mov     qword ptr [rbp+1A0h+Destination+0Ch], 3Bh ; ';'
0x18003302c  mov     r8d, 20019h
0x180033032  mov     [rbp+1A0h+var_1F4], eax
0x180033035  call    VerifyRegistryAccess
0x18003303a  mov     edi, eax
0x18003303c  test    eax, eax
0x18003303e  jnz     loc_1800334D1
0x180033044  mov     eax, [r15+78h]
0x180033048  test    eax, eax
0x18003304a  jz      loc_180033608
0x180033050  call    cs:__imp_KeEnterCriticalRegion
0x180033057  nop     dword ptr [rax+rax+00h]
0x18003305c  movzx   edx, sil; Wait
0x180033060  mov     rcx, r15; Resource
0x180033063  call    cs:__imp_ExAcquireResourceSharedLite
0x18003306a  nop     dword ptr [rax+rax+00h]
0x18003306f  test    rbx, rbx
0x180033072  jz      short loc_1800330DA
0x180033074  cmp     word ptr [rbx], 0
0x180033078  jz      short loc_1800330DA
0x18003307a  xor     edi, edi
0x18003307c  lea     rdx, [rbp+1A0h+KeyHandle]
0x180033080  xor     r8d, r8d
0x180033083  mov     dword ptr [rbp+1A0h+KeyHandle], edi
0x180033086  mov     rcx, rbx
0x180033089  call    SzString_CchLength
0x18003308e  test    eax, eax
0x180033090  jnz     loc_1800332C2
0x180033096  mov     ecx, dword ptr [rbp+1A0h+KeyHandle]
0x180033099  lea     r9, [rsp+2A0h+var_230]
0x18003309e  mov     dword ptr [rbp+1A0h+var_1C8+0Ch], ecx
0x1800330a1  lea     r8, [rbp+1A0h+var_1C8]
0x1800330a5  mov     rdx, r15
0x1800330a8  mov     qword ptr [rbp+1A0h+var_1C8], rbx
0x1800330ac  mov     dword ptr [rbp+1A0h+var_1B8], edi
0x1800330af  lea     eax, [rcx+1]
0x1800330b2  mov     rcx, r12
0x1800330b5  mov     dword ptr [rbp+1A0h+var_1C8+8], eax
0x1800330b8  call    _DetermineFunctionInterface
0x1800330bd  mov     edi, eax
0x1800330bf  test    r13d, r13d
0x1800330c2  jnz     loc_1800335BB
0x1800330c8  test    eax, eax
0x1800330ca  jnz     loc_1800334B6
0x1800330d0  mov     r13d, [rsp+2A0h+var_230]
0x1800330d5  mov     [rsp+2A0h+var_22C], r13d
0x1800330da  mov     rcx, [rsp+2A0h+Str1]
0x1800330df  test    rcx, rcx
0x1800330e2  jz      loc_1800332C2
0x1800330e8  mov     eax, dword ptr [rbp+1A0h+var_220]
0x1800330eb  test    eax, eax
0x1800330ed  jz      loc_1800332C2
0x1800330f3  cmp     dword ptr [rbp+1A0h+var_220+4], 7FFFFFFFh
0x1800330fa  jnb     loc_1800332C2
0x180033100  cmp     eax, 9
0x180033103  jb      loc_1800332C2
0x180033109  xor     eax, eax
0x18003310b  lea     r8, a08x; "%08X"
0x180033112  mov     [rcx], ax
0x180033115  mov     r9d, r13d
0x180033118  mov     edx, dword ptr [rbp+1A0h+var_220]; unsigned __int64
0x18003311b  mov     rcx, [rsp+2A0h+Str1]; unsigned __int16 *
0x180033120  mov     dword ptr [rbp+1A0h+var_220+4], 8
0x180033127  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003312c  test    eax, eax
0x18003312e  js      loc_1800337DA
0x180033134  test    r14, r14
0x180033137  jnz     loc_1800A76D2
0x18003313d  xor     r14d, r14d
0x180033140  lea     rdx, [rsp+2A0h+var_238]
0x180033145  mov     [rsp+2A0h+var_250], r14
0x18003314a  xor     r9d, r9d
0x18003314d  mov     [rsp+2A0h+var_258], r14
0x180033152  xor     r8d, r8d
0x180033155  mov     [rsp+2A0h+var_260], r14d
0x18003315a  mov     ecx, 10010h
0x18003315f  mov     qword ptr [rsp+2A0h+var_268], r14
0x180033164  mov     dword ptr [rsp+2A0h+Str2], esi
0x180033168  mov     [rsp+2A0h+HandleInformation], r15
0x18003316d  call    __CfgFind
0x180033172  mov     edi, eax
0x180033174  test    eax, eax
0x180033176  jnz     loc_180033742
0x18003317c  mov     rax, [rsp+2A0h+var_238]
0x180033181  lea     rdx, [rsp+2A0h+var_238]
0x180033186  mov     [rsp+2A0h+var_250], r14
0x18003318b  xor     r9d, r9d
0x18003318e  mov     [rsp+2A0h+var_258], r14
0x180033193  xor     r8d, r8d
0x180033196  mov     [rsp+2A0h+var_260], r14d
0x18003319b  mov     ecx, 10010h
0x1800331a0  mov     qword ptr [rsp+2A0h+var_268], r14
0x1800331a5  mov     dword ptr [rsp+2A0h+Str2], 2
0x1800331ad  mov     [rsp+2A0h+HandleInformation], r15
0x1800331b2  mov     [rbp+1A0h+var_180], rax
0x1800331b6  call    __CfgFind
0x1800331bb  mov     edi, eax
0x1800331bd  test    eax, eax
0x1800331bf  jnz     loc_1800332B2
  ... truncated ...
```
