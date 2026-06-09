# LsarLookupPrivilegeValue

- ea: `0x18000f8f0`
- end: `0x18000fecd`
- name: `LsarLookupPrivilegeValue`
- size: `1501`
- prototype: `__int64 __fastcall(struct _LSAP_DB_HANDLE *, PCUNICODE_STRING SearchString)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180074dd0`
- `0x180111848`
- `0x180149354`

## callees

- `0x18000f8f0`
- `0x18000fee0`
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

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fa35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fa35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fcbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fcbc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fc9a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fc9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fc2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fc2b`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000fa82`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000fd94`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000fdb0`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000fa82`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000fd94`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000fdb0`
- `ntdll!RtlAllocateHeap` at `0x18000fce9`
- `ntdll!RtlAllocateHeap` at `0x18000fce9`
- `ntdll!RtlLeaveCriticalSection` at `0x18000fc48`
- `ntdll!RtlLeaveCriticalSection` at `0x18000fc48`
- `ntdll!RtlEnterCriticalSection` at `0x18000fbde`
- `ntdll!RtlEnterCriticalSection` at `0x18000fbde`
- `ntdll!RtlEqualUnicodeString` at `0x18000fb16`
- `ntdll!RtlEqualUnicodeString` at `0x18000fb16`

## string_xrefs

- `0x18000fc1f`: `SYSTEM\CurrentControlSet\Services\NTDS`
- `0x18000fcb2`: `InitializeLsaDbExtension`

## pseudocode

```c
__int64 __fastcall LsarLookupPrivilegeValue(struct _LSAP_DB_HANDLE *a1, PCUNICODE_STRING SearchString, _QWORD *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r9
  int v8; // ebx
  HMODULE v9; // rbx
  char v10; // r14
  void *v11; // r15
  int v12; // ebp
  LsaHandleCache *v13; // rcx
  __int64 result; // rax
  unsigned int i; // ebx
  __int64 v16; // rdi
  char v17; // al
  __int64 v18; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbp
  PVOID Heap; // rax
  int v22; // eax
  DWORD pcbData; // [rsp+40h] [rbp-268h] BYREF
  struct _LSAP_DB_HANDLE *v24; // [rsp+48h] [rbp-260h] BYREF
  WCHAR LibFileName[264]; // [rsp+50h] [rbp-258h] BYREF

  v24 = a1;
  if ( !LsapValidateUnicodeStringWorker(SearchString, 1u, 1u, 0, 0xFFFFu, 0) )
    return 3221225485LL;
  if ( *((char *)WPP_GLOBAL_Control + 108) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_a4460d1628133fae75acd305f64a6828_Traceguids);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
  {
    if ( gpLsaHandleCache )
    {
      v22 = LsaHandleCache::VerifyHandle(v6, a1, 0, 1, 1);
      v8 = v22;
      if ( v22 < 0 && *((char *)WPP_GLOBAL_Control + 108) < 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          64,
          &WPP_27dc9bbfa4593641296446d8de402159_Traceguids,
          (unsigned int)v22);
    }
    else
    {
      v8 = -1073741595;
    }
  }
  else
  {
    LOBYTE(v7) = 1;
    v8 = LsapDbVerifyHandleOld(a1, 0, 1, v7);
  }
  if ( v8 < 0 )
    goto LABEL_41;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids);
  memset_0(LibFileName, 0, 0x208u);
  pcbData = 520;
  if ( g_pLsaExtensionTableLsaDb )
  {
    LsaDbShouldReadExtPtKey = 0;
    LocalFree(0);
LABEL_49:
    v12 = (*((__int64 (__fastcall **)(__int64))g_pLsaExtensionTableLsaDb + 31))(83886080);
    goto LABEL_15;
  }
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1073741637;
  if ( !LsaDbShouldReadExtPtKey )
  {
LABEL_11:
    LsaDbShouldReadExtPtKey = 0;
    if ( !v10 )
      goto LABEL_12;
    goto LABEL_47;
  }
  RtlEnterCriticalSection(&g_LsaExtensionTableLsaDbLock);
  if ( g_pLsaExtensionTableLsaDb )
  {
    v12 = 0;
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
    v9 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "InitializeLsaDbExtension");
      if ( ProcAddress )
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x2E0u);
        v11 = Heap;
        if ( Heap )
        {
          v10 = 1;
          v12 = ((__int64 (__fastcall *)(PVOID))ProcAddress)(Heap);
          if ( v12 < 0 )
            goto LABEL_11;
          if ( !_InterlockedCompareExchange64(
                  (volatile signed __int64 *)&g_pLsaExtensionTableLsaDb,
                  (signed __int64)v11,
                  0) )
          {
            v11 = 0;
            *(_QWORD *)g_pLsaExtensionTableLsaDb = v9;
            v9 = 0;
          }
          v12 = 0;
          LsaDbShouldReadExtPtKey = 0;
        }
        else
        {
          v12 = -1073741801;
          LsaDbShouldReadExtPtKey = 0;
        }
      }
      else
      {
        v12 = -1073741511;
        LsaDbShouldReadExtPtKey = 0;
      }
    }
    else
    {
      LsaDbShouldReadExtPtKey = 0;
    }
  }
LABEL_47:
  RtlLeaveCriticalSection(&g_LsaExtensionTableLsaDbLock);
LABEL_12:
  LocalFree(v11);
  if ( v9 )
    FreeLibrary(v9);
  if ( v12 >= 0 )
    goto LABEL_49;
LABEL_15:
  v8 = 0;
  if ( v12 != -1073741637 )
    v8 = v12;
  v13 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      11,
      WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids,
      (unsigned int)v8);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v8 >= 0 )
  {
    if ( !*((_BYTE *)a1 + 133) )
    {
      if ( !RtlAreAllAccessesGranted(*((_DWORD *)a1 + 31), 0x800u) )
      {
        v8 = -1073741790;
        if ( *((_DWORD *)a1 + 26) == 1
          && RtlAreAllAccessesGranted(0x800u, 0x800u)
          && !RtlAreAllAccessesGranted(*((_DWORD *)a1 + 31), 0x800u) )
        {
          v8 = LsapDbLookupAccessCheckNoPolicyHandle();
        }
        if ( v8 < 0 )
        {
          v17 = 1;
          goto LABEL_38;
        }
      }
      v13 = WPP_GLOBAL_Control;
    }
    if ( *((char *)v13 + 108) >= 0 )
      goto LABEL_24;
    v18 = 17;
    goto LABEL_43;
  }
  v17 = 0;
LABEL_38:
  if ( a1 && v17 )
    LsapDbResetStates(v13, 0x1000000, 0);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
    LsapDbDereferenceHandleNew(a1, 0);
  else
    LsapDbDereferenceHandleOld(a1, 0);
LABEL_41:
  v13 = WPP_GLOBAL_Control;
  if ( *((char *)WPP_GLOBAL_Control + 108) >= 0 )
    goto LABEL_24;
  v18 = 18;
LABEL_43:
  WPP_SF_d(*((_QWORD *)v13 + 12), v18, WPP_a4460d1628133fae75acd305f64a6828_Traceguids, (unsigned int)v8);
LABEL_24:
  if ( v8 < 0 )
    return (unsigned int)v8;
  result = LsapDbDereferenceObject((unsigned int)&v24, 1, 0, 83886080, 0, v8);
  if ( (int)result >= 0 )
  {
    if ( SearchString->Buffer && SearchString->Length )
    {
      for ( i = 0; i < LsapWellKnownPrivilegeCount; ++i )
      {
        v16 = 3LL * i;
        if ( RtlEqualUnicodeString(SearchString, (PCUNICODE_STRING)&(&LsapKnownPrivilege)[v16], 1u) )
        {
          *a3 = *(&LsapKnownPrivilege + v16 + 2);
          return 0;
        }
      }
    }
    return 3221225568LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000f8f0  push    rsi
0x18000f8f2  push    rdi
0x18000f8f3  push    r12
0x18000f8f5  push    r13
0x18000f8f7  sub     rsp, 288h
0x18000f8fe  mov     rax, cs:__security_cookie
0x18000f905  xor     rax, rsp
0x18000f908  mov     [rsp+2A8h+var_48], rax
0x18000f910  mov     rsi, rdx
0x18000f913  mov     [rsp+2A8h+var_260], rcx
0x18000f918  mov     r12, r8
0x18000f91b  mov     rdi, rcx
0x18000f91e  mov     r8b, 1; unsigned __int8
0x18000f921  xor     r13d, r13d
0x18000f924  movzx   edx, r8b; unsigned __int8
0x18000f928  mov     [rsp+2A8h+pvData], r13; unsigned __int16 *
0x18000f92d  xor     r9d, r9d; unsigned __int8
0x18000f930  mov     word ptr [rsp+2A8h+pdwType], 0FFFFh; unsigned __int16
0x18000f937  mov     rcx, rsi; SearchString
0x18000f93a  call    ?LsapValidateUnicodeStringWorker@@YAEPEAU_UNICODE_STRING@@EEEGPEAG@Z; LsapValidateUnicodeStringWorker(_UNICODE_STRING *,uchar,uchar,uchar,ushort,ushort *)
0x18000f93f  test    al, al
0x18000f941  jz      loc_18000FE02
0x18000f947  mov     [rsp+2A8h+arg_18], rbx
0x18000f94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f956  test    byte ptr [rcx+6Ch], 80h
0x18000f95a  jnz     loc_18000FD4F
0x18000f960  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18000f967  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18000f96c  test    al, al
0x18000f96e  jnz     loc_18000FE0C
0x18000f974  mov     r9b, 1
0x18000f977  xor     edx, edx
0x18000f979  mov     r8d, 1
0x18000f97f  mov     rcx, rdi
0x18000f982  call    ?LsapDbVerifyHandleOld@@YAJPEAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsapDbVerifyHandleOld(void *,ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x18000f987  mov     ebx, eax
0x18000f989  mov     [rsp+2A8h+var_28], rbp
0x18000f991  test    ebx, ebx
0x18000f993  js      loc_18000FBA9
0x18000f999  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9a0  test    dword ptr [rcx+6Ch], 800h
0x18000f9a7  jnz     loc_18000FD73
0x18000f9ad  xor     edx, edx; Val
0x18000f9af  lea     rcx, [rsp+2A8h+LibFileName]; void *
0x18000f9b4  mov     r8d, 208h; Size
0x18000f9ba  call    memset_0
0x18000f9bf  cmp     cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, r13; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000f9c6  mov     [rsp+2A8h+var_268], 208h
0x18000f9ce  jnz     loc_18000FC59
0x18000f9d4  mov     [rsp+2A8h+var_30], r14
0x18000f9dc  mov     rbx, r13
0x18000f9df  xor     r14b, r14b
0x18000f9e2  mov     [rsp+2A8h+var_38], r15
0x18000f9ea  cmp     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x18000f9f0  mov     r15, r13
0x18000f9f3  mov     ebp, 0C00000BBh
0x18000f9f8  jnz     loc_18000FBD7
0x18000f9fe  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, r13b; uchar LsaDbShouldReadExtPtKey
0x18000fa05  test    r14b, r14b
0x18000fa08  jnz     loc_18000FC41
0x18000fa0e  mov     rcx, r15; hMem
0x18000fa11  call    cs:__imp_LocalFree
0x18000fa18  nop     dword ptr [rax+rax+00h]
0x18000fa1d  mov     r15, [rsp+2A8h+var_38]
0x18000fa25  mov     r14, [rsp+2A8h+var_30]
0x18000fa2d  test    rbx, rbx
0x18000fa30  jz      short loc_18000FA41
0x18000fa32  mov     rcx, rbx; hLibModule
0x18000fa35  call    cs:__imp_FreeLibrary
0x18000fa3c  nop     dword ptr [rax+rax+00h]
0x18000fa41  test    ebp, ebp
0x18000fa43  jns     loc_18000FC6E
0x18000fa49  cmp     ebp, 0C00000BBh
0x18000fa4f  mov     ebx, r13d
0x18000fa52  cmovnz  ebx, ebp
0x18000fa55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa5c  test    dword ptr [rcx+6Ch], 800h
0x18000fa63  jnz     loc_18000FDD0
0x18000fa69  test    ebx, ebx
0x18000fa6b  js      loc_18000FB80
0x18000fa71  cmp     [rdi+85h], r13b
0x18000fa78  jnz     short loc_18000FA9D
0x18000fa7a  mov     ecx, [rdi+7Ch]; GrantedAccess
0x18000fa7d  mov     edx, 800h; DesiredAccess
0x18000fa82  call    cs:__imp_RtlAreAllAccessesGranted
0x18000fa89  nop     dword ptr [rax+rax+00h]
0x18000fa8e  test    al, al
0x18000fa90  jz      loc_18000FB65
0x18000fa96  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa9d  test    byte ptr [rcx+6Ch], 80h
0x18000faa1  jnz     loc_18000FD69
0x18000faa7  test    ebx, ebx
0x18000faa9  js      loc_18000FEC6
0x18000faaf  mov     dword ptr [rsp+2A8h+pvData], ebx
0x18000fab3  lea     rcx, [rsp+2A8h+var_260]
0x18000fab8  mov     r9d, 5000000h
0x18000fabe  mov     dword ptr [rsp+2A8h+pdwType], r13d
0x18000fac3  xor     r8d, r8d
0x18000fac6  mov     edx, 1
0x18000facb  call    LsapDbDereferenceObject
0x18000fad0  test    eax, eax
0x18000fad2  js      short loc_18000FB36
0x18000fad4  cmp     [rsi+8], r13
0x18000fad8  jz      loc_18000FD45
0x18000fade  cmp     [rsi], r13w
0x18000fae2  jz      loc_18000FD45
0x18000fae8  mov     ebx, r13d
0x18000faeb  lea     rbp, ?LsapKnownPrivilege@@3PAU_POLICY_PRIVILEGE_DEFINITION@@A; _POLICY_PRIVILEGE_DEFINITION near * LsapKnownPrivilege
0x18000faf2  cmp     ebx, cs:?LsapWellKnownPrivilegeCount@@3KA; ulong LsapWellKnownPrivilegeCount
0x18000faf8  jnb     loc_18000FD45
0x18000fafe  mov     eax, ebx
0x18000fb00  mov     r8b, 1; CaseInsensitive
0x18000fb03  lea     rcx, [rax+rax*2]
0x18000fb07  lea     rdi, ds:0[rcx*8]
0x18000fb0f  mov     rcx, rsi; String1
0x18000fb12  lea     rdx, [rdi+rbp]; String2
0x18000fb16  call    cs:__imp_RtlEqualUnicodeString
0x18000fb1d  nop     dword ptr [rax+rax+00h]
0x18000fb22  test    al, al
0x18000fb24  jnz     short loc_18000FB2A
0x18000fb26  inc     ebx
0x18000fb28  jmp     short loc_18000FAF2
0x18000fb2a  mov     rax, [rdi+rbp+10h]
0x18000fb2f  mov     [r12], rax
0x18000fb33  mov     eax, r13d
0x18000fb36  mov     rbp, [rsp+2A8h+var_28]
0x18000fb3e  mov     rbx, [rsp+2A8h+arg_18]
0x18000fb46  mov     rcx, [rsp+2A8h+var_48]
0x18000fb4e  xor     rcx, rsp; StackCookie
0x18000fb51  call    __security_check_cookie
0x18000fb56  add     rsp, 288h
0x18000fb5d  pop     r13
0x18000fb5f  pop     r12
0x18000fb61  pop     rdi
0x18000fb62  pop     rsi
0x18000fb63  retn
0x18000fb65  cmp     dword ptr [rdi+68h], 1
0x18000fb69  mov     ebx, 0C0000022h
0x18000fb6e  jz      loc_18000FD8D
0x18000fb74  test    ebx, ebx
0x18000fb76  jns     loc_18000FA96
0x18000fb7c  mov     al, 1
0x18000fb7e  jmp     short loc_18000FB82
0x18000fb80  xor     al, al
0x18000fb82  test    rdi, rdi
0x18000fb85  jnz     loc_18000FE66
0x18000fb8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18000fb92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18000fb97  xor     edx, edx; unsigned __int8
0x18000fb99  mov     rcx, rdi; struct _LSAP_DB_HANDLE *
0x18000fb9c  test    al, al
0x18000fb9e  jnz     loc_18000FEBC
0x18000fba4  call    ?LsapDbDereferenceHandleOld@@YAEPEAXE@Z; LsapDbDereferenceHandleOld(void *,uchar)
0x18000fba9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbb0  test    byte ptr [rcx+6Ch], 80h
0x18000fbb4  jz      loc_18000FAA7
0x18000fbba  mov     edx, 12h
0x18000fbbf  mov     rcx, [rcx+60h]
0x18000fbc3  lea     r8, WPP_a4460d1628133fae75acd305f64a6828_Traceguids
0x18000fbca  mov     r9d, ebx
0x18000fbcd  call    WPP_SF_d
0x18000fbd2  jmp     loc_18000FAA7
0x18000fbd7  lea     rcx, ?g_LsaExtensionTableLsaDbLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000fbde  call    cs:__imp_RtlEnterCriticalSection
0x18000fbe5  nop     dword ptr [rax+rax+00h]
0x18000fbea  cmp     cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, rbx; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000fbf1  jnz     loc_18000FDF4
0x18000fbf7  lea     rax, [rsp+2A8h+var_268]
0x18000fbfc  mov     r9d, 6; dwFlags
0x18000fc02  mov     [rsp+2A8h+pcbData], rax; pcbData
0x18000fc07  lea     r8, aLsadbextpt; "LsaDbExtPt"
0x18000fc0e  lea     rax, [rsp+2A8h+LibFileName]
0x18000fc13  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000fc1a  mov     [rsp+2A8h+pvData], rax; pvData
0x18000fc1f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18000fc26  mov     [rsp+2A8h+pdwType], r13; pdwType
0x18000fc2b  call    cs:__imp_RegGetValueW
0x18000fc32  nop     dword ptr [rax+rax+00h]
0x18000fc37  test    eax, eax
0x18000fc39  jz      short loc_18000FC8D
0x18000fc3b  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x18000fc41  lea     rcx, ?g_LsaExtensionTableLsaDbLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000fc48  call    cs:__imp_RtlLeaveCriticalSection
0x18000fc4f  nop     dword ptr [rax+rax+00h]
0x18000fc54  jmp     loc_18000FA0E
0x18000fc59  xor     ecx, ecx; hMem
0x18000fc5b  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, r13b; uchar LsaDbShouldReadExtPtKey
0x18000fc62  call    cs:__imp_LocalFree
0x18000fc69  nop     dword ptr [rax+rax+00h]
0x18000fc6e  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000fc75  mov     ecx, 5000000h
0x18000fc7a  mov     rax, [rax+0F8h]
0x18000fc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc86  mov     ebp, eax
0x18000fc88  jmp     loc_18000FA49
0x18000fc8d  xor     edx, edx; hFile
0x18000fc8f  lea     rcx, [rsp+2A8h+LibFileName]; lpLibFileName
0x18000fc94  mov     r8d, 8; dwFlags
0x18000fc9a  call    cs:__imp_LoadLibraryExW
0x18000fca1  nop     dword ptr [rax+rax+00h]
0x18000fca6  mov     rbx, rax
0x18000fca9  test    rax, rax
0x18000fcac  jz      loc_18000FE8E
0x18000fcb2  lea     rdx, aInitializelsad; "InitializeLsaDbExtension"
0x18000fcb9  mov     rcx, rax; hModule
0x18000fcbc  call    cs:__imp_GetProcAddress
0x18000fcc3  nop     dword ptr [rax+rax+00h]
0x18000fcc8  mov     rbp, rax
0x18000fccb  test    rax, rax
0x18000fcce  jz      loc_18000FE9A
0x18000fcd4  mov     rcx, gs:60h
0x18000fcdd  xor     edx, edx; Flags
0x18000fcdf  mov     r8d, 2E0h; Size
0x18000fce5  mov     rcx, [rcx+30h]; HeapHandle
0x18000fce9  call    cs:__imp_RtlAllocateHeap
0x18000fcf0  nop     dword ptr [rax+rax+00h]
0x18000fcf5  mov     r15, rax
0x18000fcf8  test    rax, rax
0x18000fcfb  jz      loc_18000FEAB
0x18000fd01  mov     rcx, rax
0x18000fd04  mov     r14b, 1
0x18000fd07  mov     rax, rbp
0x18000fd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd0f  mov     ebp, eax
0x18000fd11  test    eax, eax
0x18000fd13  js      loc_18000F9FE
0x18000fd19  xor     eax, eax
0x18000fd1b  lock cmpxchg cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA, r15; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000fd24  jnz     short loc_18000FD36
0x18000fd26  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x18000fd2d  mov     r15, r13
0x18000fd30  mov     [rax], rbx
0x18000fd33  mov     rbx, r13
0x18000fd36  mov     ebp, r13d
0x18000fd39  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, bpl; uchar LsaDbShouldReadExtPtKey
0x18000fd40  jmp     loc_18000FC41
0x18000fd45  mov     eax, 0C0000060h
0x18000fd4a  jmp     loc_18000FB36
0x18000fd4f  mov     rcx, [rcx+60h]
0x18000fd53  lea     r8, WPP_a4460d1628133fae75acd305f64a6828_Traceguids
0x18000fd5a  mov     edx, 10h
0x18000fd5f  call    WPP_SF_
0x18000fd64  jmp     loc_18000F960
0x18000fd69  mov     edx, 11h
0x18000fd6e  jmp     loc_18000FBBF
0x18000fd73  mov     rcx, [rcx+60h]
0x18000fd77  lea     r8, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids
0x18000fd7e  mov     edx, 0Ah
0x18000fd83  call    WPP_SF_
0x18000fd88  jmp     loc_18000F9AD
0x18000fd8d  mov     edx, 800h; DesiredAccess
0x18000fd92  mov     ecx, edx; GrantedAccess
0x18000fd94  call    cs:__imp_RtlAreAllAccessesGranted
0x18000fd9b  nop     dword ptr [rax+rax+00h]
0x18000fda0  test    al, al
0x18000fda2  jz      loc_18000FB74
0x18000fda8  mov     ecx, [rdi+7Ch]; GrantedAccess
0x18000fdab  mov     edx, 800h; DesiredAccess
0x18000fdb0  call    cs:__imp_RtlAreAllAccessesGranted
0x18000fdb7  nop     dword ptr [rax+rax+00h]
0x18000fdbc  test    al, al
0x18000fdbe  jnz     loc_18000FB74
0x18000fdc4  call    ?LsapDbLookupAccessCheckNoPolicyHandle@@YAJXZ; LsapDbLookupAccessCheckNoPolicyHandle(void)
0x18000fdc9  mov     ebx, eax
0x18000fdcb  jmp     loc_18000FB74
0x18000fdd0  mov     rcx, [rcx+60h]
0x18000fdd4  lea     r8, WPP_8a5bf7e3574a37043972e3a5e06d9b6d_Traceguids
0x18000fddb  mov     edx, 0Bh
0x18000fde0  mov     r9d, ebx
0x18000fde3  call    WPP_SF_d
0x18000fde8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdef  jmp     loc_18000FA69
0x18000fdf4  mov     ebp, r13d
0x18000fdf7  mov     cs:?LsaDbShouldReadExtPtKey@@3EA, bl; uchar LsaDbShouldReadExtPtKey
0x18000fdfd  jmp     loc_18000FC41
0x18000fe02  mov     eax, 0C000000Dh
0x18000fe07  jmp     loc_18000FB46
0x18000fe0c  cmp     cs:?gpLsaHandleCache@@3PEAVLsaHandleCache@@EA, r13; LsaHandleCache * gpLsaHandleCache
0x18000fe13  jz      short loc_18000FE84
0x18000fe15  mov     r9d, 1
0x18000fe1b  mov     dword ptr [rsp+2A8h+pdwType], 1
0x18000fe23  xor     r8d, r8d
0x18000fe26  mov     rdx, rdi
0x18000fe29  call    ?VerifyHandle@LsaHandleCache@@QEAAJPEAU_LSAP_DB_HANDLE@@KW4_LSAP_DB_OBJECT_TYPE_ID@@H@Z; LsaHandleCache::VerifyHandle(_LSAP_DB_HANDLE *,ulong,_LSAP_DB_OBJECT_TYPE_ID,int)
0x18000fe2e  mov     ebx, eax
0x18000fe30  test    eax, eax
0x18000fe32  jns     loc_18000F989
0x18000fe38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe3f  test    byte ptr [rcx+6Ch], 80h
0x18000fe43  jz      loc_18000F989
0x18000fe49  mov     rcx, [rcx+60h]
0x18000fe4d  lea     r8, WPP_27dc9bbfa4593641296446d8de402159_Traceguids
0x18000fe54  mov     edx, 40h ; '@'
0x18000fe59  mov     r9d, eax
0x18000fe5c  call    WPP_SF_d
0x18000fe61  jmp     loc_18000F989
0x18000fe66  test    al, al
0x18000fe68  jz      loc_18000FB8B
0x18000fe6e  xor     r8d, r8d
0x18000fe71  mov     dword ptr [rsp+2A8h+pdwType], ebx
  ... truncated ...
```
