# LsapDbReferenceObject

- ea: `0x18000ddc0`
- end: `0x18000e524`
- name: `LsapDbReferenceObject`
- size: `1892`
- prototype: `__int64 __usercall@<rax>(struct _LSAP_DB_HANDLE *@<rcx>, ACCESS_MASK DesiredAccess@<edx>, int)`
- caller_count: `49`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ee50`
- `0x18001ecf0`
- `0x1800204c0`
- `0x180020f00`
- `0x180021230`
- `0x180021580`
- `0x180052990`
- `0x180074dd0`
- `0x18008e95c`
- `0x18008ec0c`
- `0x18009380c`
- `0x180093a84`
- `0x1800ffc40`
- `0x1800ffdd0`
- `0x1800fffe0`
- `0x180101050`
- `0x180103f2c`
- `0x18010411c`
- `0x1801046ec`
- `0x180107d28`
- `0x180108d30`
- `0x180108dc0`
- `0x1801091f0`
- `0x180109fc8`
- `0x18010a07c`
- `0x18010a46c`
- `0x18010c5f0`
- `0x18010c870`
- `0x18010dc20`
- `0x18010ddc0`
- `0x18010e4f0`
- `0x18010e820`
- `0x18010f05c`
- `0x18010f5d4`
- `0x18010fb30`
- `0x18010fe78`
- `0x1801100f0`
- `0x180110410`
- `0x1801108a0`
- `0x180110c60`
- `0x180111670`
- `0x180111790`
- `0x180117f34`
- `0x180118124`
- `0x18011aea0`
- `0x18011b79c`
- `0x18011bfd0`
- `0x18011c210`
- `0x18011ff64`

## callees

- `0x18000ddc0`
- `0x180011278`
- `0x1800112c0`
- `0x1800270c0`
- `0x1800284d4`
- `0x180054838`
- `0x1800a03f4`
- `0x1800a0cd8`
- `0x1800a104c`
- `0x1800a1dc4`
- `0x1800ada18`
- `0x1800b30dc`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18010b518`
- `0x18011f3a8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dfdb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dfdb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e204`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e204`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e1e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e1e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dfbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dfbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e170`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e170`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000e062`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000e3ef`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000e40b`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000e062`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000e3ef`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000e40b`
- `ntdll!RtlAllocateHeap` at `0x18000e231`
- `ntdll!RtlAllocateHeap` at `0x18000e231`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e302`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e339`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e475`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e302`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e339`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e475`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e18d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e18d`
- `ntdll!RtlEnterCriticalSection` at `0x18000ded5`
- `ntdll!RtlEnterCriticalSection` at `0x18000deef`
- `ntdll!RtlEnterCriticalSection` at `0x18000e123`
- `ntdll!RtlEnterCriticalSection` at `0x18000e460`
- `ntdll!RtlEnterCriticalSection` at `0x18000e488`
- `ntdll!RtlEnterCriticalSection` at `0x18000ded5`
- `ntdll!RtlEnterCriticalSection` at `0x18000deef`
- `ntdll!RtlEnterCriticalSection` at `0x18000e123`
- `ntdll!RtlEnterCriticalSection` at `0x18000e460`
- `ntdll!RtlEnterCriticalSection` at `0x18000e488`

## string_xrefs

- `0x18000e164`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x18000e1fa`: `InitializeLsaDbExtension`

## pseudocode

```c
__int64 __fastcall LsapDbReferenceObject(
        struct _LSAP_DB_HANDLE *a1,
        ACCESS_MASK DesiredAccess,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  unsigned int v5; // r14d
  ACCESS_MASK v7; // r12d
  __int64 v9; // rcx
  __int64 v10; // r9
  HMODULE v11; // rbx
  char v12; // r15
  unsigned int v13; // ebp
  int v14; // edx
  unsigned int v15; // r12d
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  void *v17; // rax
  char v18; // r13
  int v19; // r14d
  int v20; // eax
  LsaHandleCache *v21; // rcx
  int v22; // ecx
  LsaHandleCache *v23; // rcx
  __int64 v25; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // r14
  PVOID Heap; // rax
  int v29; // eax
  char v30; // [rsp+40h] [rbp-288h]
  int v32; // [rsp+48h] [rbp-280h]
  signed __int64 v33; // [rsp+50h] [rbp-278h]
  DWORD pcbData; // [rsp+58h] [rbp-270h] BYREF
  ACCESS_MASK v35; // [rsp+5Ch] [rbp-26Ch]
  WCHAR LibFileName[264]; // [rsp+60h] [rbp-268h] BYREF

  v5 = a4;
  v35 = DesiredAccess;
  v7 = DesiredAccess;
  if ( *((char *)WPP_GLOBAL_Control + 108) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_a4460d1628133fae75acd305f64a6828_Traceguids);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
  {
    if ( gpLsaHandleCache )
    {
      v29 = LsaHandleCache::VerifyHandle(v9, a1, 0, a3, 1);
      LODWORD(v11) = v29;
      if ( v29 < 0 && *((char *)WPP_GLOBAL_Control + 108) < 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          64,
          &WPP_27dc9bbfa4593641296446d8de402159_Traceguids,
          (unsigned int)v29);
    }
    else
    {
      LODWORD(v11) = -1073741595;
    }
  }
  else
  {
    LOBYTE(v10) = 1;
    LODWORD(v11) = LsapDbVerifyHandleOld(a1, 0, a3, v10);
  }
  if ( (int)v11 < 0 )
  {
LABEL_56:
    v23 = WPP_GLOBAL_Control;
    if ( *((char *)WPP_GLOBAL_Control + 108) < 0 )
    {
      v25 = 18;
LABEL_58:
      WPP_SF_d(*((_QWORD *)v23 + 12), v25, WPP_a4460d1628133fae75acd305f64a6828_Traceguids, (unsigned int)v11);
      return (unsigned int)v11;
    }
    return (unsigned int)v11;
  }
  v12 = 0;
  v13 = a5 & 0x3000000;
  if ( (a5 & 0x700101B) == 0 )
    goto LABEL_48;
  v11 = 0;
  v32 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids);
  v14 = a5 & 0x700101B;
  if ( ((v5 - 1) & 0xFFFFFFFD) == 0 )
    v14 = a5 & 0x300101B | 0x4000000;
  v15 = v14 | 0x1000000;
  if ( v5 != 2 )
    v15 = v14;
  if ( (v15 & 1) != 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids, v5, v15);
    if ( v5 == 1 )
    {
      v16 = &CriticalSection;
      goto LABEL_18;
    }
    if ( v5 )
    {
      switch ( v5 )
      {
        case 2u:
          RtlAcquireResourceExclusive(&Resource, 1u);
          goto LABEL_25;
        case 3u:
          v16 = &stru_18019F1B0;
          break;
        case 4u:
          RtlAcquireResourceExclusive(&Resource, 1u);
          v16 = &stru_18019F1E0;
          break;
        case 5u:
          RtlEnterCriticalSection(&CriticalSection);
          RtlAcquireResourceExclusive(&Resource, 1u);
          RtlEnterCriticalSection(&stru_18019F1B0);
          v16 = &stru_18019F1E0;
          break;
        default:
          goto LABEL_25;
      }
LABEL_18:
      RtlEnterCriticalSection(v16);
      if ( (v15 & 0x1000000) == 0 )
        RtlEnterCriticalSection(&stru_18019F210);
    }
LABEL_25:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids);
    v32 = 1;
  }
  if ( (v15 & 0x7000008) == 0 )
    goto LABEL_41;
  v30 = 0;
  if ( (v15 & 0x1000000) != 0 )
  {
LABEL_30:
    memset_0(LibFileName, 0, 0x208u);
    pcbData = 520;
    if ( g_pLsaExtensionTableLsaDb )
    {
      LsaDbShouldReadExtPtKey = 0;
      LocalFree(0);
LABEL_64:
      v19 = (*((__int64 (__fastcall **)(_QWORD))g_pLsaExtensionTableLsaDb + 31))(v15);
LABEL_36:
      LODWORD(v11) = 0;
      if ( v19 != -1073741637 )
        LODWORD(v11) = v19;
      v20 = (int)v11;
      if ( (int)v11 < 0 && v30 )
      {
        LsapRegAbortTransaction();
        v5 = a4;
LABEL_97:
        if ( v32 )
          LsapDbReleaseLockEx(v5, v15);
        goto LABEL_41;
      }
      v5 = a4;
      goto LABEL_40;
    }
    v17 = 0;
    v18 = 0;
    v33 = 0;
    v19 = -1073741637;
    if ( !LsaDbShouldReadExtPtKey )
    {
LABEL_32:
      LsaDbShouldReadExtPtKey = 0;
      if ( !v18 )
        goto LABEL_33;
      goto LABEL_62;
    }
    RtlEnterCriticalSection(&g_LsaExtensionTableLsaDbLock);
    if ( g_pLsaExtensionTableLsaDb )
    {
      v19 = 0;
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
      v11 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "InitializeLsaDbExtension");
        if ( ProcAddress )
        {
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x2E0u);
          v33 = (signed __int64)Heap;
          if ( Heap )
          {
            v18 = 1;
            v19 = ((__int64 (__fastcall *)(PVOID))ProcAddress)(Heap);
            if ( v19 < 0 )
            {
              v17 = (void *)v33;
              goto LABEL_32;
            }
            if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&g_pLsaExtensionTableLsaDb, v33, 0) )
            {
              *(_QWORD *)g_pLsaExtensionTableLsaDb = v11;
              v11 = 0;
              v33 = 0;
            }
            v19 = 0;
            LsaDbShouldReadExtPtKey = 0;
          }
          else
          {
            v19 = -1073741801;
            LsaDbShouldReadExtPtKey = 0;
          }
        }
        else
        {
          v19 = -1073741511;
          LsaDbShouldReadExtPtKey = 0;
        }
      }
      else
      {
        LsaDbShouldReadExtPtKey = 0;
      }
    }
LABEL_62:
    RtlLeaveCriticalSection(&g_LsaExtensionTableLsaDbLock);
    v17 = (void *)v33;
LABEL_33:
    LocalFree(v17);
    if ( v11 )
      FreeLibrary(v11);
    if ( v19 < 0 )
      goto LABEL_36;
    goto LABEL_64;
  }
  v20 = LsapRegOpenTransaction();
  if ( v20 >= 0 )
  {
    v30 = 1;
    goto LABEL_30;
  }
LABEL_40:
  LODWORD(v11) = v20;
  if ( v20 < 0 )
    goto LABEL_97;
LABEL_41:
  v21 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      11,
      WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids,
      (unsigned int)v11);
  if ( (int)v11 < 0 )
    goto LABEL_53;
  v7 = v35;
  v22 = v13 | 0x10;
  v12 = 1;
  if ( (a5 & 8) == 0 )
    v22 = a5 & 0x3000000;
  v13 = v22;
  if ( (a5 & 1) != 0 )
    v13 = v22 | 1;
LABEL_48:
  if ( !*((_BYTE *)a1 + 133) && !RtlAreAllAccessesGranted(*((_DWORD *)a1 + 31), v7) )
  {
    LODWORD(v11) = -1073741790;
    if ( *((_DWORD *)a1 + 26) != 1
      || !RtlAreAllAccessesGranted(0x800u, v7)
      || RtlAreAllAccessesGranted(*((_DWORD *)a1 + 31), 0x800u)
      || (LODWORD(v11) = LsapDbLookupAccessCheckNoPolicyHandle(), (int)v11 < 0) )
    {
LABEL_53:
      if ( a1 && v12 )
        LsapDbResetStates(v21, v13, v5);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
        LsapDbDereferenceHandleNew(a1, 0);
      else
        LsapDbDereferenceHandleOld(a1, 0);
      goto LABEL_56;
    }
  }
  v23 = WPP_GLOBAL_Control;
  if ( *((char *)WPP_GLOBAL_Control + 108) < 0 )
  {
    v25 = 17;
    goto LABEL_58;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000ddc0  push    rbx
0x18000ddc2  push    rsi
0x18000ddc3  push    r12
0x18000ddc5  push    r14
0x18000ddc7  sub     rsp, 2A8h
0x18000ddce  mov     rax, cs:__security_cookie
0x18000ddd5  xor     rax, rsp
0x18000ddd8  mov     [rsp+2C8h+var_58], rax
0x18000dde0  mov     r14d, r9d
0x18000dde3  mov     [rsp+2C8h+var_284], r9d
0x18000dde8  mov     ebx, r8d
0x18000ddeb  mov     [rsp+2C8h+var_26C], edx
0x18000ddef  mov     r12d, edx
0x18000ddf2  mov     rsi, rcx
0x18000ddf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddfc  test    byte ptr [rcx+6Ch], 80h
0x18000de00  jnz     loc_18000E2AF
0x18000de06  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18000de0d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18000de12  test    al, al
0x18000de14  jnz     loc_18000E38B
0x18000de1a  mov     r9b, 1
0x18000de1d  mov     r8d, ebx
0x18000de20  xor     edx, edx
0x18000de22  mov     rcx, rsi
0x18000de25  call    ?LsapDbVerifyHandleOld@@YAJPEAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsapDbVerifyHandleOld(void *,ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x18000de2a  mov     ebx, eax
0x18000de2c  mov     [rsp+2C8h+var_28], rbp
0x18000de34  mov     [rsp+2C8h+var_30], rdi
0x18000de3c  mov     [rsp+2C8h+var_40], r15
0x18000de44  test    ebx, ebx
0x18000de46  js      loc_18000E0F2
0x18000de4c  mov     edi, [rsp+2C8h+arg_20]
0x18000de53  xor     r15b, r15b
0x18000de56  and     edi, 700101Bh
0x18000de5c  mov     ebp, edi
0x18000de5e  and     ebp, 3000000h
0x18000de64  test    edi, edi
0x18000de66  jz      loc_18000E053
0x18000de6c  xor     ebx, ebx
0x18000de6e  mov     [rsp+2C8h+var_280], ebx
0x18000de72  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de79  test    dword ptr [rcx+6Ch], 800h
0x18000de80  jnz     loc_18000E2DF
0x18000de86  mov     ecx, edi
0x18000de88  lea     eax, [r14-1]
0x18000de8c  bts     ecx, 1Ah
0x18000de90  mov     edx, edi
0x18000de92  test    eax, 0FFFFFFFDh
0x18000de97  cmovz   edx, ecx
0x18000de9a  mov     r12d, edx
0x18000de9d  bts     r12d, 18h
0x18000dea2  cmp     r14d, 2
0x18000dea6  cmovnz  r12d, edx
0x18000deaa  test    r12b, 1
0x18000deae  jz      loc_18000DF45
0x18000deb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000debb  test    dword ptr [rcx+6Ch], 800h
0x18000dec2  jnz     loc_18000E369
0x18000dec8  cmp     r14d, 1
0x18000decc  jnz     short loc_18000DEFD
0x18000dece  lea     rcx, CriticalSection; CriticalSection
0x18000ded5  call    cs:__imp_RtlEnterCriticalSection
0x18000dedc  nop     dword ptr [rax+rax+00h]
0x18000dee1  bt      r12d, 18h
0x18000dee6  jb      short loc_18000DF29
0x18000dee8  lea     rcx, stru_18019F210; CriticalSection
0x18000deef  call    cs:__imp_RtlEnterCriticalSection
0x18000def6  nop     dword ptr [rax+rax+00h]
0x18000defb  jmp     short loc_18000DF29
0x18000defd  mov     ecx, r14d
0x18000df00  test    r14d, r14d
0x18000df03  jz      short loc_18000DF29
0x18000df05  sub     ecx, 2
0x18000df08  jz      loc_18000E2F9
0x18000df0e  sub     ecx, 1
0x18000df11  jz      loc_18000E2C9
0x18000df17  sub     ecx, 1
0x18000df1a  jz      loc_18000E330
0x18000df20  cmp     ecx, 1
0x18000df23  jz      loc_18000E459
0x18000df29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df30  test    dword ptr [rcx+6Ch], 800h
0x18000df37  jnz     loc_18000E4A0
0x18000df3d  mov     [rsp+2C8h+var_280], 1
0x18000df45  test    r12d, 7000008h
0x18000df4c  jz      loc_18000E016
0x18000df52  mov     [rsp+2C8h+var_288], bl
0x18000df56  bt      r12d, 18h
0x18000df5b  jnb     loc_18000E298
0x18000df61  xor     edx, edx; Val
0x18000df63  lea     rcx, [rsp+2C8h+LibFileName]; void *
0x18000df68  mov     r8d, 208h; Size
0x18000df6e  call    memset_0
0x18000df73  cmp     cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, rbx; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000df7a  mov     [rsp+2C8h+var_270], 208h
0x18000df82  jnz     loc_18000E1A3
0x18000df88  xor     eax, eax
0x18000df8a  mov     [rsp+2C8h+var_38], r13
0x18000df92  xor     r13b, r13b
0x18000df95  mov     [rsp+2C8h+var_278], rax
0x18000df9a  cmp     cs:?LsaDbShouldReadExtPtKey@@3EA, al; uchar LsaDbShouldReadExtPtKey
0x18000dfa0  mov     r14d, 0C00000BBh
0x18000dfa6  jnz     loc_18000E11C
0x18000dfac  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, r15b; uchar LsaDbShouldReadExtPtKey
0x18000dfb3  test    r13b, r13b
0x18000dfb6  jnz     loc_18000E186
0x18000dfbc  mov     rcx, rax; hMem
0x18000dfbf  call    cs:__imp_LocalFree
0x18000dfc6  nop     dword ptr [rax+rax+00h]
0x18000dfcb  mov     r13, [rsp+2C8h+var_38]
0x18000dfd3  test    rbx, rbx
0x18000dfd6  jz      short loc_18000DFE7
0x18000dfd8  mov     rcx, rbx; hLibModule
0x18000dfdb  call    cs:__imp_FreeLibrary
0x18000dfe2  nop     dword ptr [rax+rax+00h]
0x18000dfe7  test    r14d, r14d
0x18000dfea  jns     loc_18000E1B7
0x18000dff0  xor     ebx, ebx
0x18000dff2  cmp     r14d, 0C00000BBh
0x18000dff9  cmovnz  ebx, r14d
0x18000dffd  mov     eax, ebx
0x18000dfff  test    ebx, ebx
0x18000e001  js      loc_18000E4EA
0x18000e007  mov     r14d, [rsp+2C8h+var_284]
0x18000e00c  mov     ebx, eax
0x18000e00e  test    eax, eax
0x18000e010  js      loc_18000E4FF
0x18000e016  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e01d  test    dword ptr [rcx+6Ch], 800h
0x18000e024  jnz     loc_18000E313
0x18000e02a  test    ebx, ebx
0x18000e02c  js      loc_18000E0CB
0x18000e032  mov     r12d, [rsp+2C8h+var_26C]
0x18000e037  mov     ecx, ebp
0x18000e039  or      ecx, 10h
0x18000e03c  mov     r15b, 1
0x18000e03f  test    dil, 8
0x18000e043  cmovz   ecx, ebp
0x18000e046  mov     eax, ecx
0x18000e048  mov     ebp, ecx
0x18000e04a  or      eax, 1
0x18000e04d  test    r15b, dil
0x18000e050  cmovnz  ebp, eax
0x18000e053  cmp     byte ptr [rsi+85h], 0
0x18000e05a  jnz     short loc_18000E072
0x18000e05c  mov     ecx, [rsi+7Ch]; GrantedAccess
0x18000e05f  mov     edx, r12d; DesiredAccess
0x18000e062  call    cs:__imp_RtlAreAllAccessesGranted
0x18000e069  nop     dword ptr [rax+rax+00h]
0x18000e06e  test    al, al
0x18000e070  jz      short loc_18000E0BC
0x18000e072  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e079  test    byte ptr [rcx+6Ch], 80h
0x18000e07d  jnz     loc_18000E2D5
0x18000e083  mov     r15, [rsp+2C8h+var_40]
0x18000e08b  mov     eax, ebx
0x18000e08d  mov     rdi, [rsp+2C8h+var_30]
0x18000e095  mov     rbp, [rsp+2C8h+var_28]
0x18000e09d  mov     rcx, [rsp+2C8h+var_58]
0x18000e0a5  xor     rcx, rsp; StackCookie
0x18000e0a8  call    __security_check_cookie
0x18000e0ad  add     rsp, 2A8h
0x18000e0b4  pop     r14
0x18000e0b6  pop     r12
0x18000e0b8  pop     rsi
0x18000e0b9  pop     rbx
0x18000e0ba  retn
0x18000e0bc  cmp     dword ptr [rsi+68h], 1
0x18000e0c0  mov     ebx, 0C0000022h
0x18000e0c5  jz      loc_18000E3E7
0x18000e0cb  test    rsi, rsi
0x18000e0ce  jnz     loc_18000E433
0x18000e0d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18000e0db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18000e0e0  xor     edx, edx; unsigned __int8
0x18000e0e2  mov     rcx, rsi; struct _LSAP_DB_HANDLE *
0x18000e0e5  test    al, al
0x18000e0e7  jnz     loc_18000E51A
0x18000e0ed  call    ?LsapDbDereferenceHandleOld@@YAEPEAXE@Z; LsapDbDereferenceHandleOld(void *,uchar)
0x18000e0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0f9  test    byte ptr [rcx+6Ch], 80h
0x18000e0fd  jz      short loc_18000E083
0x18000e0ff  mov     edx, 12h
0x18000e104  mov     rcx, [rcx+60h]
0x18000e108  lea     r8, WPP_a4460d1628133fae75acd305f64a6828_Traceguids
0x18000e10f  mov     r9d, ebx
0x18000e112  call    WPP_SF_d
0x18000e117  jmp     loc_18000E083
0x18000e11c  lea     rcx, ?g_LsaExtensionTableLsaDbLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000e123  call    cs:__imp_RtlEnterCriticalSection
0x18000e12a  nop     dword ptr [rax+rax+00h]
0x18000e12f  cmp     cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, rbx; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000e136  jnz     loc_18000E351
0x18000e13c  lea     rax, [rsp+2C8h+var_270]
0x18000e141  mov     r9d, 6; dwFlags
0x18000e147  mov     [rsp+2C8h+pcbData], rax; pcbData
0x18000e14c  lea     r8, aLsadbextpt; "LsaDbExtPt"
0x18000e153  lea     rax, [rsp+2C8h+LibFileName]
0x18000e158  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000e15f  mov     [rsp+2C8h+pvData], rax; pvData
0x18000e164  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18000e16b  mov     [rsp+2C8h+pdwType], rbx; pdwType
0x18000e170  call    cs:__imp_RegGetValueW
0x18000e177  nop     dword ptr [rax+rax+00h]
0x18000e17c  test    eax, eax
0x18000e17e  jz      short loc_18000E1D5
0x18000e180  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x18000e186  lea     rcx, ?g_LsaExtensionTableLsaDbLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000e18d  call    cs:__imp_RtlLeaveCriticalSection
0x18000e194  nop     dword ptr [rax+rax+00h]
0x18000e199  mov     rax, [rsp+2C8h+var_278]
0x18000e19e  jmp     loc_18000DFBC
0x18000e1a3  xor     ecx, ecx; hMem
0x18000e1a5  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x18000e1ab  call    cs:__imp_LocalFree
0x18000e1b2  nop     dword ptr [rax+rax+00h]
0x18000e1b7  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000e1be  mov     ecx, r12d
0x18000e1c1  mov     rax, [rax+0F8h]
0x18000e1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1cd  mov     r14d, eax
0x18000e1d0  jmp     loc_18000DFF0
0x18000e1d5  xor     edx, edx; hFile
0x18000e1d7  lea     rcx, [rsp+2C8h+LibFileName]; lpLibFileName
0x18000e1dc  mov     r8d, 8; dwFlags
0x18000e1e2  call    cs:__imp_LoadLibraryExW
0x18000e1e9  nop     dword ptr [rax+rax+00h]
0x18000e1ee  mov     rbx, rax
0x18000e1f1  test    rax, rax
0x18000e1f4  jz      loc_18000E4BA
0x18000e1fa  lea     rdx, aInitializelsad; "InitializeLsaDbExtension"
0x18000e201  mov     rcx, rax; hModule
0x18000e204  call    cs:__imp_GetProcAddress
0x18000e20b  nop     dword ptr [rax+rax+00h]
0x18000e210  mov     r14, rax
0x18000e213  test    rax, rax
0x18000e216  jz      loc_18000E4C6
0x18000e21c  mov     rcx, gs:60h
0x18000e225  xor     edx, edx; Flags
0x18000e227  mov     r8d, 2E0h; Size
0x18000e22d  mov     rcx, [rcx+30h]; HeapHandle
0x18000e231  call    cs:__imp_RtlAllocateHeap
0x18000e238  nop     dword ptr [rax+rax+00h]
0x18000e23d  mov     [rsp+2C8h+var_278], rax
0x18000e242  test    rax, rax
0x18000e245  jz      loc_18000E4D8
0x18000e24b  mov     rcx, rax
0x18000e24e  mov     r13b, 1
0x18000e251  mov     rax, r14
0x18000e254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e259  mov     r14d, eax
0x18000e25c  test    eax, eax
0x18000e25e  js      loc_18000E35F
0x18000e264  mov     rcx, [rsp+2C8h+var_278]
0x18000e269  xor     eax, eax
0x18000e26b  lock cmpxchg cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, rcx; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000e274  jnz     short loc_18000E289
0x18000e276  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000e27d  mov     [rax], rbx
0x18000e280  xor     ebx, ebx
0x18000e282  xor     ecx, ecx
0x18000e284  mov     [rsp+2C8h+var_278], rcx
0x18000e289  xor     r14d, r14d
0x18000e28c  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, r14b; uchar LsaDbShouldReadExtPtKey
0x18000e293  jmp     loc_18000E186
0x18000e298  call    ?LsapRegOpenTransaction@@YAJXZ; LsapRegOpenTransaction(void)
0x18000e29d  test    eax, eax
0x18000e29f  js      loc_18000E00C
0x18000e2a5  mov     [rsp+2C8h+var_288], 1
0x18000e2aa  jmp     loc_18000DF61
0x18000e2af  mov     rcx, [rcx+60h]
0x18000e2b3  lea     r8, WPP_a4460d1628133fae75acd305f64a6828_Traceguids
0x18000e2ba  mov     edx, 10h
0x18000e2bf  call    WPP_SF_
0x18000e2c4  jmp     loc_18000DE06
0x18000e2c9  lea     rcx, stru_18019F1B0
0x18000e2d0  jmp     loc_18000DED5
0x18000e2d5  mov     edx, 11h
0x18000e2da  jmp     loc_18000E104
0x18000e2df  mov     rcx, [rcx+60h]
0x18000e2e3  lea     r8, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids
0x18000e2ea  mov     edx, 0Ah
0x18000e2ef  call    WPP_SF_
0x18000e2f4  jmp     loc_18000DE86
0x18000e2f9  mov     dl, 1; Wait
0x18000e2fb  lea     rcx, Resource; Resource
0x18000e302  call    cs:__imp_RtlAcquireResourceExclusive
0x18000e309  nop     dword ptr [rax+rax+00h]
0x18000e30e  jmp     loc_18000DF29
0x18000e313  mov     rcx, [rcx+60h]
0x18000e317  lea     r8, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids
0x18000e31e  mov     edx, 0Bh
0x18000e323  mov     r9d, ebx
0x18000e326  call    WPP_SF_d
0x18000e32b  jmp     loc_18000E02A
0x18000e330  mov     dl, 1; Wait
0x18000e332  lea     rcx, Resource; Resource
0x18000e339  call    cs:__imp_RtlAcquireResourceExclusive
0x18000e340  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
