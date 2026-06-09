# LsapDbLookupAccessCheck(void *)

- ea: `0x1800101e0`
- end: `0x18001070e`
- name: `?LsapDbLookupAccessCheck@@YAJPEAX@Z`
- size: `1326`
- prototype: `__int64 __fastcall(struct _LSAP_DB_HANDLE *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180011cdc`
- `0x180012da4`

## callees

- `0x1800101e0`
- `0x180010ba0`
- `0x180011278`
- `0x1800112c0`
- `0x1800a03f4`
- `0x1800a0cd8`
- `0x1800a104c`
- `0x1800a1dc4`
- `0x1800ada18`
- `0x1800b30dc`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18010b518`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010304`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010304`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010526`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010526`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010504`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010504`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800104ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800104ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010493`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010493`
- `ntdll!RtlAreAllAccessesGranted` at `0x180010358`
- `ntdll!RtlAreAllAccessesGranted` at `0x180010604`
- `ntdll!RtlAreAllAccessesGranted` at `0x180010620`
- `ntdll!RtlAreAllAccessesGranted` at `0x180010358`
- `ntdll!RtlAreAllAccessesGranted` at `0x180010604`
- `ntdll!RtlAreAllAccessesGranted` at `0x180010620`
- `ntdll!RtlAllocateHeap` at `0x180010553`
- `ntdll!RtlAllocateHeap` at `0x180010553`
- `ntdll!RtlLeaveCriticalSection` at `0x1800104b0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800104b0`
- `ntdll!RtlEnterCriticalSection` at `0x180010446`
- `ntdll!RtlEnterCriticalSection` at `0x180010446`

## string_xrefs

- `0x180010487`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x18001051c`: `InitializeLsaDbExtension`

## pseudocode

```c
__int64 __fastcall LsapDbLookupAccessCheck(struct _LSAP_DB_HANDLE *a1)
{
  __int64 v2; // rcx
  __int64 v3; // r9
  int v4; // ebx
  HMODULE v5; // rbx
  char v6; // r14
  void *v7; // r15
  int v8; // ebp
  LsaHandleCache *v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbp
  PVOID Heap; // rax
  int v16; // eax
  DWORD pcbData; // [rsp+40h] [rbp-248h] BYREF
  struct _LSAP_DB_HANDLE *v18; // [rsp+48h] [rbp-240h] BYREF
  WCHAR LibFileName[264]; // [rsp+50h] [rbp-238h] BYREF

  v18 = a1;
  if ( !a1 )
    return LsapDbLookupAccessCheckNoPolicyHandle();
  if ( *((char *)WPP_GLOBAL_Control + 108) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_a4460d1628133fae75acd305f64a6828_Traceguids);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
  {
    if ( gpLsaHandleCache )
    {
      v16 = LsaHandleCache::VerifyHandle(v2, a1, 0, 1, 1);
      v4 = v16;
      if ( v16 < 0 && *((char *)WPP_GLOBAL_Control + 108) < 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          64,
          &WPP_27dc9bbfa4593641296446d8de402159_Traceguids,
          (unsigned int)v16);
    }
    else
    {
      v4 = -1073741595;
    }
  }
  else
  {
    LOBYTE(v3) = 1;
    v4 = LsapDbVerifyHandleOld(a1, 0, 1, v3);
  }
  if ( v4 < 0 )
    goto LABEL_31;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids);
  memset_0(LibFileName, 0, 0x208u);
  pcbData = 520;
  if ( g_pLsaExtensionTableLsaDb )
  {
    LsaDbShouldReadExtPtKey = 0;
    LocalFree(0);
LABEL_39:
    v8 = (*((__int64 (__fastcall **)(__int64))g_pLsaExtensionTableLsaDb + 31))(83886080);
    goto LABEL_15;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = -1073741637;
  if ( !LsaDbShouldReadExtPtKey )
  {
LABEL_11:
    LsaDbShouldReadExtPtKey = 0;
    if ( !v6 )
      goto LABEL_12;
    goto LABEL_37;
  }
  RtlEnterCriticalSection(&g_LsaExtensionTableLsaDbLock);
  if ( g_pLsaExtensionTableLsaDb )
  {
    v8 = 0;
    LsaDbShouldReadExtPtKey = 0;
  }
  else if ( RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\NTDS",
              L"LsaDbExtPt",
              6u,
              0,
              LibFileName,
              &pcbData) )
  {
    LsaDbShouldReadExtPtKey = 0;
  }
  else
  {
    Library = LoadLibraryExW(LibFileName, 0, 8u);
    v5 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "InitializeLsaDbExtension");
      if ( ProcAddress )
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x2E0u);
        v7 = Heap;
        if ( Heap )
        {
          v6 = 1;
          v8 = ((__int64 (__fastcall *)(PVOID))ProcAddress)(Heap);
          if ( v8 < 0 )
            goto LABEL_11;
          if ( !_InterlockedCompareExchange64(
                  (volatile signed __int64 *)&g_pLsaExtensionTableLsaDb,
                  (signed __int64)v7,
                  0) )
          {
            v7 = 0;
            *(_QWORD *)g_pLsaExtensionTableLsaDb = v5;
            v5 = 0;
          }
          v8 = 0;
          LsaDbShouldReadExtPtKey = 0;
        }
        else
        {
          v8 = -1073741801;
          LsaDbShouldReadExtPtKey = 0;
        }
      }
      else
      {
        v8 = -1073741511;
        LsaDbShouldReadExtPtKey = 0;
      }
    }
    else
    {
      LsaDbShouldReadExtPtKey = 0;
    }
  }
LABEL_37:
  RtlLeaveCriticalSection(&g_LsaExtensionTableLsaDbLock);
LABEL_12:
  LocalFree(v7);
  if ( v5 )
    FreeLibrary(v5);
  if ( v8 >= 0 )
    goto LABEL_39;
LABEL_15:
  v4 = 0;
  if ( v8 != -1073741637 )
    v4 = v8;
  v9 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      11,
      WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids,
      (unsigned int)v4);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v4 < 0 )
    goto LABEL_29;
  if ( *((_BYTE *)a1 + 133) )
  {
LABEL_23:
    if ( *((char *)v9 + 108) >= 0 )
      goto LABEL_24;
    v12 = 17;
    goto LABEL_33;
  }
  if ( RtlAreAllAccessesGranted(*((_DWORD *)a1 + 31), 0x800u) )
    goto LABEL_22;
  v4 = -1073741790;
  if ( *((_DWORD *)a1 + 26) == 1
    && RtlAreAllAccessesGranted(0x800u, 0x800u)
    && !RtlAreAllAccessesGranted(*((_DWORD *)a1 + 31), 0x800u) )
  {
    v4 = LsapDbLookupAccessCheckNoPolicyHandle();
  }
  if ( v4 >= 0 )
  {
LABEL_22:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  LsapDbResetStates(v10, 0x1000000, 0);
LABEL_29:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
    LsapDbDereferenceHandleNew(a1, 0);
  else
    LsapDbDereferenceHandleOld(a1, 0);
LABEL_31:
  v9 = WPP_GLOBAL_Control;
  if ( *((char *)WPP_GLOBAL_Control + 108) >= 0 )
    goto LABEL_24;
  v12 = 18;
LABEL_33:
  WPP_SF_d(*((_QWORD *)v9 + 12), v12, WPP_a4460d1628133fae75acd305f64a6828_Traceguids, (unsigned int)v4);
LABEL_24:
  if ( v4 < 0 )
    return (unsigned int)v4;
  else
    return LsapDbDereferenceObject((unsigned int)&v18, 1, 0, 83886080, 0, v4);
}

```

## disassembly

```asm
0x1800101e0  push    rdi
0x1800101e2  sub     rsp, 280h
0x1800101e9  mov     rax, cs:__security_cookie
0x1800101f0  xor     rax, rsp
0x1800101f3  mov     [rsp+288h+var_28], rax
0x1800101fb  mov     [rsp+288h+var_240], rcx
0x180010200  mov     rdi, rcx
0x180010203  test    rcx, rcx
0x180010206  jz      loc_1800105AE
0x18001020c  mov     [rsp+288h+arg_8], rbx
0x180010214  mov     rcx, cs:WPP_GLOBAL_Control
0x18001021b  test    byte ptr [rcx+6Ch], 80h
0x18001021f  jnz     loc_1800105BF
0x180010225  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18001022c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x180010231  test    al, al
0x180010233  jnz     loc_180010671
0x180010239  mov     r9b, 1
0x18001023c  xor     edx, edx
0x18001023e  mov     r8d, 1
0x180010244  mov     rcx, rdi
0x180010247  call    ?LsapDbVerifyHandleOld@@YAJPEAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsapDbVerifyHandleOld(void *,ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x18001024c  mov     ebx, eax
0x18001024e  mov     [rsp+288h+arg_18], rsi
0x180010256  test    ebx, ebx
0x180010258  js      loc_18001040F
0x18001025e  mov     [rsp+288h+arg_10], rbp
0x180010266  mov     rcx, cs:WPP_GLOBAL_Control
0x18001026d  test    dword ptr [rcx+6Ch], 800h
0x180010274  jnz     loc_1800105E3
0x18001027a  xor     edx, edx; Val
0x18001027c  lea     rcx, [rsp+288h+LibFileName]; void *
0x180010281  mov     r8d, 208h; Size
0x180010287  call    memset_0
0x18001028c  cmp     cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, 0; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x180010294  mov     [rsp+288h+var_248], 208h
0x18001029c  jnz     loc_1800104C1
0x1800102a2  xor     esi, esi
0x1800102a4  mov     [rsp+288h+var_10], r14
0x1800102ac  mov     ebx, esi
0x1800102ae  mov     [rsp+288h+var_18], r15
0x1800102b6  xor     r14b, r14b
0x1800102b9  mov     r15d, esi
0x1800102bc  cmp     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x1800102c2  mov     ebp, 0C00000BBh
0x1800102c7  jnz     loc_18001043F
0x1800102cd  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, sil; uchar LsaDbShouldReadExtPtKey
0x1800102d4  test    r14b, r14b
0x1800102d7  jnz     loc_1800104A9
0x1800102dd  mov     rcx, r15; hMem
0x1800102e0  call    cs:__imp_LocalFree
0x1800102e7  nop     dword ptr [rax+rax+00h]
0x1800102ec  mov     r15, [rsp+288h+var_18]
0x1800102f4  mov     r14, [rsp+288h+var_10]
0x1800102fc  test    rbx, rbx
0x1800102ff  jz      short loc_180010310
0x180010301  mov     rcx, rbx; hLibModule
0x180010304  call    cs:__imp_FreeLibrary
0x18001030b  nop     dword ptr [rax+rax+00h]
0x180010310  test    ebp, ebp
0x180010312  jns     loc_1800104D8
0x180010318  cmp     ebp, 0C00000BBh
0x18001031e  mov     ebx, esi
0x180010320  cmovnz  ebx, ebp
0x180010323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001032a  mov     rbp, [rsp+288h+arg_10]
0x180010332  test    dword ptr [rcx+6Ch], 800h
0x180010339  jnz     loc_180010640
0x18001033f  test    ebx, ebx
0x180010341  js      loc_1800103EF
0x180010347  cmp     byte ptr [rdi+85h], 0
0x18001034e  jnz     short loc_18001036F
0x180010350  mov     ecx, [rdi+7Ch]; GrantedAccess
0x180010353  mov     edx, 800h; DesiredAccess
0x180010358  call    cs:__imp_RtlAreAllAccessesGranted
0x18001035f  nop     dword ptr [rax+rax+00h]
0x180010364  test    al, al
0x180010366  jz      short loc_1800103CB
0x180010368  mov     rcx, cs:WPP_GLOBAL_Control
0x18001036f  test    byte ptr [rcx+6Ch], 80h
0x180010373  jnz     loc_1800105D9
0x180010379  test    ebx, ebx
0x18001037b  js      loc_1800105B8
0x180010381  mov     dword ptr [rsp+288h+pvData], ebx
0x180010385  lea     rcx, [rsp+288h+var_240]
0x18001038a  mov     r9d, 5000000h
0x180010390  mov     dword ptr [rsp+288h+pdwType], esi
0x180010394  xor     r8d, r8d
0x180010397  mov     edx, 1
0x18001039c  call    LsapDbDereferenceObject
0x1800103a1  mov     rsi, [rsp+288h+arg_18]
0x1800103a9  mov     rbx, [rsp+288h+arg_8]
0x1800103b1  mov     rcx, [rsp+288h+var_28]
0x1800103b9  xor     rcx, rsp; StackCookie
0x1800103bc  call    __security_check_cookie
0x1800103c1  add     rsp, 280h
0x1800103c8  pop     rdi
0x1800103c9  retn
0x1800103cb  cmp     dword ptr [rdi+68h], 1
0x1800103cf  mov     ebx, 0C0000022h
0x1800103d4  jz      loc_1800105FD
0x1800103da  test    ebx, ebx
0x1800103dc  jns     short loc_180010368
0x1800103de  xor     r8d, r8d
0x1800103e1  mov     dword ptr [rsp+288h+pdwType], ebx
0x1800103e5  mov     edx, 1000000h
0x1800103ea  call    ?LsapDbResetStates@@YAJPEAXKW4_LSAP_DB_OBJECT_TYPE_ID@@W4_SECURITY_DB_DELTA_TYPE@@J@Z; LsapDbResetStates(void *,ulong,_LSAP_DB_OBJECT_TYPE_ID,_SECURITY_DB_DELTA_TYPE,long)
0x1800103ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x1800103f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x1800103fb  xor     edx, edx; unsigned __int8
0x1800103fd  mov     rcx, rdi; struct _LSAP_DB_HANDLE *
0x180010400  test    al, al
0x180010402  jnz     loc_180010704
0x180010408  call    ?LsapDbDereferenceHandleOld@@YAEPEAXE@Z; LsapDbDereferenceHandleOld(void *,uchar)
0x18001040d  jmp     short loc_180010411
0x18001040f  xor     esi, esi
0x180010411  mov     rcx, cs:WPP_GLOBAL_Control
0x180010418  test    byte ptr [rcx+6Ch], 80h
0x18001041c  jz      loc_180010379
0x180010422  mov     edx, 12h
0x180010427  mov     rcx, [rcx+60h]
0x18001042b  lea     r8, WPP_a4460d1628133fae75acd305f64a6828_Traceguids
0x180010432  mov     r9d, ebx
0x180010435  call    WPP_SF_d
0x18001043a  jmp     loc_180010379
0x18001043f  lea     rcx, ?g_LsaExtensionTableLsaDbLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180010446  call    cs:__imp_RtlEnterCriticalSection
0x18001044d  nop     dword ptr [rax+rax+00h]
0x180010452  cmp     cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, rbx; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x180010459  jnz     loc_180010664
0x18001045f  lea     rax, [rsp+288h+var_248]
0x180010464  mov     r9d, 6; dwFlags
0x18001046a  mov     [rsp+288h+pcbData], rax; pcbData
0x18001046f  lea     r8, aLsadbextpt; "LsaDbExtPt"
0x180010476  lea     rax, [rsp+288h+LibFileName]
0x18001047b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180010482  mov     [rsp+288h+pvData], rax; pvData
0x180010487  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18001048e  mov     [rsp+288h+pdwType], rsi; pdwType
0x180010493  call    cs:__imp_RegGetValueW
0x18001049a  nop     dword ptr [rax+rax+00h]
0x18001049f  test    eax, eax
0x1800104a1  jz      short loc_1800104F7
0x1800104a3  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x1800104a9  lea     rcx, ?g_LsaExtensionTableLsaDbLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800104b0  call    cs:__imp_RtlLeaveCriticalSection
0x1800104b7  nop     dword ptr [rax+rax+00h]
0x1800104bc  jmp     loc_1800102DD
0x1800104c1  xor     ecx, ecx; hMem
0x1800104c3  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, 0; uchar LsaDbShouldReadExtPtKey
0x1800104ca  call    cs:__imp_LocalFree
0x1800104d1  nop     dword ptr [rax+rax+00h]
0x1800104d6  xor     esi, esi
0x1800104d8  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x1800104df  mov     ecx, 5000000h
0x1800104e4  mov     rax, [rax+0F8h]
0x1800104eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f0  mov     ebp, eax
0x1800104f2  jmp     loc_180010318
0x1800104f7  xor     edx, edx; hFile
0x1800104f9  lea     rcx, [rsp+288h+LibFileName]; lpLibFileName
0x1800104fe  mov     r8d, 8; dwFlags
0x180010504  call    cs:__imp_LoadLibraryExW
0x18001050b  nop     dword ptr [rax+rax+00h]
0x180010510  mov     rbx, rax
0x180010513  test    rax, rax
0x180010516  jz      loc_1800106D6
0x18001051c  lea     rdx, aInitializelsad; "InitializeLsaDbExtension"
0x180010523  mov     rcx, rax; hModule
0x180010526  call    cs:__imp_GetProcAddress
0x18001052d  nop     dword ptr [rax+rax+00h]
0x180010532  mov     rbp, rax
0x180010535  test    rax, rax
0x180010538  jz      loc_1800106E2
0x18001053e  mov     rcx, gs:60h
0x180010547  xor     edx, edx; Flags
0x180010549  mov     r8d, 2E0h; Size
0x18001054f  mov     rcx, [rcx+30h]; HeapHandle
0x180010553  call    cs:__imp_RtlAllocateHeap
0x18001055a  nop     dword ptr [rax+rax+00h]
0x18001055f  mov     r15, rax
0x180010562  test    rax, rax
0x180010565  jz      loc_1800106F3
0x18001056b  mov     rcx, rax
0x18001056e  mov     r14b, 1
0x180010571  mov     rax, rbp
0x180010574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010579  mov     ebp, eax
0x18001057b  test    eax, eax
0x18001057d  js      loc_1800102CD
0x180010583  xor     eax, eax
0x180010585  lock cmpxchg cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, r15; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18001058e  jnz     short loc_1800105A0
0x180010590  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x180010597  mov     r15, rsi
0x18001059a  mov     [rax], rbx
0x18001059d  mov     rbx, rsi
0x1800105a0  mov     ebp, esi
0x1800105a2  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, sil; uchar LsaDbShouldReadExtPtKey
0x1800105a9  jmp     loc_1800104A9
0x1800105ae  call    ?LsapDbLookupAccessCheckNoPolicyHandle@@YAJXZ; LsapDbLookupAccessCheckNoPolicyHandle(void)
0x1800105b3  jmp     loc_1800103B1
0x1800105b8  mov     eax, ebx
0x1800105ba  jmp     loc_1800103A1
0x1800105bf  mov     rcx, [rcx+60h]
0x1800105c3  lea     r8, WPP_a4460d1628133fae75acd305f64a6828_Traceguids
0x1800105ca  mov     edx, 10h
0x1800105cf  call    WPP_SF_
0x1800105d4  jmp     loc_180010225
0x1800105d9  mov     edx, 11h
0x1800105de  jmp     loc_180010427
0x1800105e3  mov     rcx, [rcx+60h]
0x1800105e7  lea     r8, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids
0x1800105ee  mov     edx, 0Ah
0x1800105f3  call    WPP_SF_
0x1800105f8  jmp     loc_18001027A
0x1800105fd  mov     edx, 800h; DesiredAccess
0x180010602  mov     ecx, edx; GrantedAccess
0x180010604  call    cs:__imp_RtlAreAllAccessesGranted
0x18001060b  nop     dword ptr [rax+rax+00h]
0x180010610  test    al, al
0x180010612  jz      loc_1800103DA
0x180010618  mov     ecx, [rdi+7Ch]; GrantedAccess
0x18001061b  mov     edx, 800h; DesiredAccess
0x180010620  call    cs:__imp_RtlAreAllAccessesGranted
0x180010627  nop     dword ptr [rax+rax+00h]
0x18001062c  test    al, al
0x18001062e  jnz     loc_1800103DA
0x180010634  call    ?LsapDbLookupAccessCheckNoPolicyHandle@@YAJXZ; LsapDbLookupAccessCheckNoPolicyHandle(void)
0x180010639  mov     ebx, eax
0x18001063b  jmp     loc_1800103DA
0x180010640  mov     rcx, [rcx+60h]
0x180010644  lea     r8, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids
0x18001064b  mov     edx, 0Bh
0x180010650  mov     r9d, ebx
0x180010653  call    WPP_SF_d
0x180010658  mov     rcx, cs:WPP_GLOBAL_Control
0x18001065f  jmp     loc_18001033F
0x180010664  mov     ebp, esi
0x180010666  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x18001066c  jmp     loc_1800104A9
0x180010671  cmp     cs:?gpLsaHandleCache@@3PEAVLsaHandleCache@@EA, 0; LsaHandleCache * gpLsaHandleCache
0x180010679  jz      short loc_1800106CC
0x18001067b  mov     r9d, 1
0x180010681  mov     dword ptr [rsp+288h+pdwType], 1
0x180010689  xor     r8d, r8d
0x18001068c  mov     rdx, rdi
0x18001068f  call    ?VerifyHandle@LsaHandleCache@@QEAAJPEAU_LSAP_DB_HANDLE@@KW4_LSAP_DB_OBJECT_TYPE_ID@@H@Z; LsaHandleCache::VerifyHandle(_LSAP_DB_HANDLE *,ulong,_LSAP_DB_OBJECT_TYPE_ID,int)
0x180010694  mov     ebx, eax
0x180010696  test    eax, eax
0x180010698  jns     loc_18001024E
0x18001069e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106a5  test    byte ptr [rcx+6Ch], 80h
0x1800106a9  jz      loc_18001024E
0x1800106af  mov     rcx, [rcx+60h]
0x1800106b3  lea     r8, WPP_27dc9bbfa4593641296446d8de402159_Traceguids
0x1800106ba  mov     edx, 40h ; '@'
0x1800106bf  mov     r9d, eax
0x1800106c2  call    WPP_SF_d
0x1800106c7  jmp     loc_18001024E
0x1800106cc  mov     ebx, 0C00000E5h
0x1800106d1  jmp     loc_18001024E
0x1800106d6  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, sil; uchar LsaDbShouldReadExtPtKey
0x1800106dd  jmp     loc_1800104A9
0x1800106e2  mov     ebp, 0C0000139h
0x1800106e7  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, sil; uchar LsaDbShouldReadExtPtKey
0x1800106ee  jmp     loc_1800104A9
0x1800106f3  mov     ebp, 0C0000017h
0x1800106f8  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, sil; uchar LsaDbShouldReadExtPtKey
0x1800106ff  jmp     loc_1800104A9
0x180010704  call    ?LsapDbDereferenceHandleNew@@YAEPEAXE@Z; LsapDbDereferenceHandleNew(void *,uchar)
0x180010709  jmp     loc_180010411
```
