# CCSDirectMetadataManager::CreateEnumerationForDeployments(Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const &,Windows::Isolation::Rtl::_REFERENCE_APPID,CCSDirectDeploymentMetadataEnumerator * *)

- ea: `0x1800cd8a8`
- end: `0x1800cdc02`
- name: `?CreateEnumerationForDeployments@CCSDirectMetadataManager@@QEAAJAEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@U_REFERENCE_APPID@345@PEAPEAVCCSDirectDeploymentMetadataEnumerator@@@Z`
- size: `858`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800cdd80`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x180012b1c`
- `0x18002a844`
- `0x180042f10`
- `0x18004f2dc`
- `0x1800cc2ac`
- `0x1800cc59c`
- `0x1800cc94c`
- `0x1800cd8a8`
- `0x1800ceb28`
- `0x1800cee24`
- `0x1800fe440`
- `0x180114224`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cdaef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cdbaa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cdaef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cdbaa`

## string_xrefs

- `0x1800cd93e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cdaa9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cdb64`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall CCSDirectMetadataManager::CreateEnumerationForDeployments(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        CCSDirectDeploymentMetadataEnumerator **a4)
{
  int v7; // r14d
  __int64 *v8; // r8
  void *v9; // rcx
  int v10; // eax
  HANDLE ProcessHeap_0; // rax
  CCSDirectDeploymentMetadataEnumerator *v12; // rax
  CCSDirectDeploymentMetadataEnumerator *v13; // rsi
  int v14; // eax
  __int64 v15; // r10
  __int64 v16; // r10
  unsigned int *v17; // r11
  signed int v18; // ecx
  void *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r10
  unsigned int *v23; // r11
  signed int v24; // ecx
  void *v25; // rcx
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
  __int64 v28; // [rsp+38h] [rbp-31h] BYREF
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+48h] [rbp-21h]
  void *v31; // [rsp+50h] [rbp-19h]
  __int64 v32; // [rsp+58h] [rbp-11h] BYREF
  __int64 v33; // [rsp+60h] [rbp-9h]
  void *lpMem; // [rsp+68h] [rbp-1h]
  const char *v35; // [rsp+70h] [rbp+7h] BYREF
  int v36; // [rsp+78h] [rbp+Fh]
  int v37; // [rsp+80h] [rbp+17h]
  _DWORD v38[14]; // [rsp+88h] [rbp+1Fh] BYREF

  v30 = 0;
  v29 = 0;
  v31 = 0;
  v28 = 0;
  v27 = 0;
  v38[0] = 0;
  v7 = anonymous_namespace_::IsopFormatInstallerReference(a2, &v29);
  if ( v7 < 0
    || (v7 = Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(4, *a1, 0x80000000LL, &v29, &v28, v38), v7 < 0) )
  {
LABEL_37:
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v28);
    v25 = v31;
    if ( v31 )
    {
      v31 = 0;
      v29 = 0;
      v30 = 0;
      IsolationFreeStringRoutine(v25);
    }
    return (unsigned int)v7;
  }
  if ( v38[0] != 4 )
  {
    v33 = 0;
    v8 = 0;
    v32 = 0;
    lpMem = 0;
    if ( a3 )
    {
      v7 = IdentityToKeyFormWithLessStack<Windows::Isolation::Rtl::_REFERENCE_APPID,Windows::Rtl::CLUNICODE_STRING>(
             a3,
             &v32,
             0);
      if ( v7 < 0 )
      {
        v9 = lpMem;
        goto LABEL_10;
      }
      v8 = &v32;
    }
    v10 = RtlEnumerateHierarchy(1, v28, v8, &v27);
    v9 = lpMem;
    v7 = v10;
    if ( v10 < 0 )
    {
LABEL_10:
      if ( v9 )
      {
        v33 = 0;
        v32 = 0;
        lpMem = 0;
        IsolationFreeStringRoutine(v9);
      }
      goto LABEL_29;
    }
    if ( lpMem )
    {
      v33 = 0;
      v32 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v9);
    }
  }
  ProcessHeap_0 = GetProcessHeap_0();
  v12 = (CCSDirectDeploymentMetadataEnumerator *)HeapAlloc_0(ProcessHeap_0, 0, 0x80u);
  v13 = v12;
  if ( !v12 )
  {
    v7 = -1073741801;
LABEL_29:
    v15 = v27;
LABEL_30:
    if ( v15 )
    {
      v37 = -1073741595;
      v35 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v15) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v23 + 4))(*v23, v22);
        v24 = 0;
      }
      else
      {
        v36 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v35);
        v24 = v37;
      }
      if ( v24 < 0 )
        RaiseException(v24, 1u, 0, 0);
      v27 = 0;
    }
    goto LABEL_37;
  }
  *((_QWORD *)v12 + 11) = 0;
  *((_DWORD *)v12 + 8) = 0;
  *((_QWORD *)v12 + 5) = 0;
  *((_QWORD *)v12 + 1) = (char *)v12 + 8;
  *((_QWORD *)v12 + 2) = (char *)v12 + 8;
  *((_QWORD *)v12 + 3) = (char *)v12 + 8;
  *(_QWORD *)v12 = &CCSDirectDeploymentMetadataEnumerator::`vftable';
  *((_DWORD *)v12 + 18) = 0;
  *((_QWORD *)v12 + 10) = 0;
  *((_QWORD *)v12 + 6) = (char *)v12 + 48;
  *((_QWORD *)v12 + 7) = (char *)v12 + 48;
  *((_QWORD *)v12 + 8) = (char *)v12 + 48;
  *((_QWORD *)v12 + 12) = 0;
  *((_QWORD *)v12 + 13) = 0;
  *((_QWORD *)v12 + 14) = 0;
  v14 = CCSDirectDeploymentMetadataEnumerator::Initialize(v12, a1, v28, v27, a3);
  v15 = v27;
  v7 = v14;
  if ( v14 >= 0 )
  {
    *a4 = v13;
    v7 = 0;
    goto LABEL_30;
  }
  if ( v27 )
  {
    v37 = -1073741595;
    v35 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v27) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v17 + 4))(*v17, v16);
      v18 = 0;
    }
    else
    {
      v36 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v35);
      v18 = v37;
    }
    if ( v18 < 0 )
      RaiseException(v18, 1u, 0, 0);
    v27 = 0;
  }
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v28);
  v19 = v31;
  if ( v31 )
  {
    v30 = 0;
    v29 = 0;
    v31 = 0;
    IsolationFreeStringRoutine(v19);
  }
  CCSDirectDeploymentMetadataEnumerator::~CCSDirectDeploymentMetadataEnumerator(v13);
  RtlFreeHeap(v21, v20, v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800cd8a8  push    rbp
0x1800cd8aa  push    rbx
0x1800cd8ab  push    rsi
0x1800cd8ac  push    r12
0x1800cd8ae  push    r13
0x1800cd8b0  push    r14
0x1800cd8b2  push    r15
0x1800cd8b4  lea     rbp, [rsp-27h]
0x1800cd8b9  sub     rsp, 90h
0x1800cd8c0  xor     r13d, r13d
0x1800cd8c3  mov     rax, rdx
0x1800cd8c6  mov     r12, rcx
0x1800cd8c9  mov     [rbp+57h+var_78], r13
0x1800cd8cd  mov     rcx, rax
0x1800cd8d0  mov     [rbp+57h+var_80], r13
0x1800cd8d4  lea     rdx, [rbp+57h+var_80]
0x1800cd8d8  mov     [rbp+57h+var_70], r13
0x1800cd8dc  mov     r15, r9
0x1800cd8df  mov     [rbp+57h+var_88], r13
0x1800cd8e3  mov     rbx, r8
0x1800cd8e6  mov     [rbp+57h+var_90], r13
0x1800cd8ea  mov     [rbp+57h+var_38], r13d
0x1800cd8ee  call    _anonymous_namespace___IsopFormatInstallerReference
0x1800cd8f3  mov     r14d, eax
0x1800cd8f6  test    eax, eax
0x1800cd8f8  js      short loc_1800CD92A
0x1800cd8fa  mov     rdx, [r12]
0x1800cd8fe  lea     rax, [rbp+57h+var_38]
0x1800cd902  mov     [rsp+0C0h+var_98], rax
0x1800cd907  lea     r9, [rbp+57h+var_80]
0x1800cd90b  lea     rax, [rbp+57h+var_88]
0x1800cd90f  mov     r8d, 80000000h
0x1800cd915  lea     ecx, [r13+4]
0x1800cd919  mov     [rsp+0C0h+var_A0], rax
0x1800cd91e  call    ?RtlOpenHierarchy@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@KPEBU_LUNICODE_STRING@@PEAU5134@PEAK@Z; Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(ulong,Windows::Isolation::Rtl::_HIERARCHY,ulong,_LUNICODE_STRING const *,Windows::Isolation::Rtl::_HIERARCHY *,ulong *)
0x1800cd923  mov     r14d, eax
0x1800cd926  test    eax, eax
0x1800cd928  jns     short loc_1800CD980
0x1800cd92a  mov     r10, [rbp+57h+var_90]
0x1800cd92e  test    r10, r10
0x1800cd931  jz      loc_1800CDBB4
0x1800cd937  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cd93e  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cd945  mov     [rbp+57h+var_68], rax
0x1800cd949  mov     dword ptr [rbp+57h+lpMem], 0C00000E5h
0x1800cd950  test    r11, r11
0x1800cd953  jz      short loc_1800CD968
0x1800cd955  mov     rdx, r11
0x1800cd958  mov     rcx, r10
0x1800cd95b  call    RtlIsTypeSafeHandleValid
0x1800cd960  test    al, al
0x1800cd962  jnz     loc_1800CDB8A
0x1800cd968  mov     dword ptr [rbp+57h+var_60], 124h
0x1800cd96f  lea     rcx, [rbp+57h+var_68]
0x1800cd973  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cd978  mov     ecx, dword ptr [rbp+57h+lpMem]
0x1800cd97b  jmp     loc_1800CDB9C
0x1800cd980  cmp     [rbp+57h+var_38], 4
0x1800cd984  jz      loc_1800CDA0D
0x1800cd98a  mov     [rbp+57h+var_60], r13
0x1800cd98e  mov     r8, r13
0x1800cd991  mov     [rbp+57h+var_68], r13
0x1800cd995  mov     [rbp+57h+lpMem], r13
0x1800cd999  test    rbx, rbx
0x1800cd99c  jz      short loc_1800CD9BB
0x1800cd99e  lea     rdx, [rbp+57h+var_68]
0x1800cd9a2  mov     rcx, rbx
0x1800cd9a5  call    ??$IdentityToKeyFormWithLessStack@U_REFERENCE_APPID@Rtl@Isolation@Windows@@VCLUNICODE_STRING@24@@@YAJU_REFERENCE_APPID@Rtl@Isolation@Windows@@AEAVCLUNICODE_STRING@13@@Z; IdentityToKeyFormWithLessStack<Windows::Isolation::Rtl::_REFERENCE_APPID,Windows::Rtl::CLUNICODE_STRING>(Windows::Isolation::Rtl::_REFERENCE_APPID,Windows::Rtl::CLUNICODE_STRING &)
0x1800cd9aa  mov     r14d, eax
0x1800cd9ad  test    eax, eax
0x1800cd9af  jns     short loc_1800CD9B7
0x1800cd9b1  mov     rcx, [rbp+57h+lpMem]
0x1800cd9b5  jmp     short loc_1800CD9D8
0x1800cd9b7  lea     r8, [rbp+57h+var_68]
0x1800cd9bb  mov     rdx, [rbp+57h+var_88]
0x1800cd9bf  lea     r9, [rbp+57h+var_90]
0x1800cd9c3  mov     ecx, 1
0x1800cd9c8  call    RtlEnumerateHierarchy
0x1800cd9cd  mov     rcx, [rbp+57h+lpMem]; lpMem
0x1800cd9d1  mov     r14d, eax
0x1800cd9d4  test    eax, eax
0x1800cd9d6  jns     short loc_1800CD9F7
0x1800cd9d8  test    rcx, rcx
0x1800cd9db  jz      loc_1800CDB54
0x1800cd9e1  mov     [rbp+57h+var_60], r13
0x1800cd9e5  mov     [rbp+57h+var_68], r13
0x1800cd9e9  mov     [rbp+57h+lpMem], r13
0x1800cd9ed  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800cd9f2  jmp     loc_1800CDB54
0x1800cd9f7  test    rcx, rcx
0x1800cd9fa  jz      short loc_1800CDA0D
0x1800cd9fc  mov     [rbp+57h+var_60], r13
0x1800cda00  mov     [rbp+57h+var_68], r13
0x1800cda04  mov     [rbp+57h+lpMem], r13
0x1800cda08  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800cda0d  call    GetProcessHeap_0
0x1800cda12  mov     rcx, rax; hHeap
0x1800cda15  xor     edx, edx; dwFlags
0x1800cda17  mov     r8d, 80h; dwBytes
0x1800cda1d  call    HeapAlloc_0
0x1800cda22  mov     rsi, rax
0x1800cda25  test    rax, rax
0x1800cda28  jz      loc_1800CDB4E
0x1800cda2e  lea     rcx, [rax+8]
0x1800cda32  mov     [rsi+58h], r13
0x1800cda36  mov     [rcx+18h], r13d
0x1800cda3a  lea     rax, ??_7CCSDirectDeploymentMetadataEnumerator@@6B@; const CCSDirectDeploymentMetadataEnumerator::`vftable'
0x1800cda41  mov     [rcx+20h], r13
0x1800cda45  mov     [rcx], rcx
0x1800cda48  mov     [rcx+8], rcx
0x1800cda4c  mov     [rcx+10h], rcx
0x1800cda50  add     rcx, 28h ; '('
0x1800cda54  mov     [rsi], rax
0x1800cda57  mov     [rcx+18h], r13d
0x1800cda5b  mov     [rcx+20h], r13
0x1800cda5f  mov     [rcx], rcx
0x1800cda62  mov     [rcx+8], rcx
0x1800cda66  mov     [rcx+10h], rcx
0x1800cda6a  mov     [rsi+60h], r13
0x1800cda6e  mov     [rsi+68h], r13
0x1800cda72  mov     [rsi+70h], r13
0x1800cda76  mov     r9, [rbp+57h+var_90]
0x1800cda7a  mov     rdx, r12
0x1800cda7d  mov     r8, [rbp+57h+var_88]
0x1800cda81  mov     rcx, rsi
0x1800cda84  mov     [rsp+0C0h+var_A0], rbx
0x1800cda89  call    ?Initialize@CCSDirectDeploymentMetadataEnumerator@@QEAAJPEAVCCSDirectMetadataManager@@U_HIERARCHY@Rtl@Isolation@Windows@@U_HIERARCHY_ENUMERATOR@456@U_REFERENCE_APPID@456@@Z; CCSDirectDeploymentMetadataEnumerator::Initialize(CCSDirectMetadataManager *,Windows::Isolation::Rtl::_HIERARCHY,Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Rtl::_REFERENCE_APPID)
0x1800cda8e  mov     r10, [rbp+57h+var_90]
0x1800cda92  mov     r14d, eax
0x1800cda95  test    eax, eax
0x1800cda97  jns     loc_1800CDB46
0x1800cda9d  test    r10, r10
0x1800cdaa0  jz      short loc_1800CDAF9
0x1800cdaa2  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cdaa9  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cdab0  mov     [rbp+57h+var_40], 0C00000E5h
0x1800cdab7  mov     [rbp+57h+var_50], rax
0x1800cdabb  test    r11, r11
0x1800cdabe  jz      short loc_1800CDB31
0x1800cdac0  mov     rdx, r11
0x1800cdac3  mov     rcx, r10
0x1800cdac6  call    RtlIsTypeSafeHandleValid
0x1800cdacb  test    al, al
0x1800cdacd  jz      short loc_1800CDB31
0x1800cdacf  mov     ecx, [r11]
0x1800cdad2  mov     rdx, r10
0x1800cdad5  mov     rax, [r11+20h]
0x1800cdad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdade  mov     ecx, r13d; dwExceptionCode
0x1800cdae1  test    ecx, ecx
0x1800cdae3  jns     short loc_1800CDAF5
0x1800cdae5  xor     r9d, r9d; lpArguments
0x1800cdae8  xor     r8d, r8d; nNumberOfArguments
0x1800cdaeb  lea     edx, [r9+1]; dwExceptionFlags
0x1800cdaef  call    cs:__imp_RaiseException
0x1800cdaf5  mov     [rbp+57h+var_90], r13
0x1800cdaf9  lea     rcx, [rbp+57h+var_88]
0x1800cdafd  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cdb02  mov     rcx, [rbp+57h+var_70]; lpMem
0x1800cdb06  test    rcx, rcx
0x1800cdb09  jz      short loc_1800CDB1C
0x1800cdb0b  mov     [rbp+57h+var_78], r13
0x1800cdb0f  mov     [rbp+57h+var_80], r13
0x1800cdb13  mov     [rbp+57h+var_70], r13
0x1800cdb17  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800cdb1c  mov     rcx, rsi; this
0x1800cdb1f  call    ??1CCSDirectDeploymentMetadataEnumerator@@QEAA@XZ; CCSDirectDeploymentMetadataEnumerator::~CCSDirectDeploymentMetadataEnumerator(void)
0x1800cdb24  mov     r8, rsi
0x1800cdb27  call    RtlFreeHeap
0x1800cdb2c  jmp     loc_1800CDBD7
0x1800cdb31  mov     [rbp+57h+var_48], 124h
0x1800cdb38  lea     rcx, [rbp+57h+var_50]
0x1800cdb3c  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cdb41  mov     ecx, [rbp+57h+var_40]
0x1800cdb44  jmp     short loc_1800CDAE1
0x1800cdb46  mov     [r15], rsi
0x1800cdb49  mov     r14d, r13d
0x1800cdb4c  jmp     short loc_1800CDB58
0x1800cdb4e  mov     r14d, 0C0000017h
0x1800cdb54  mov     r10, [rbp+57h+var_90]
0x1800cdb58  test    r10, r10
0x1800cdb5b  jz      short loc_1800CDBB4
0x1800cdb5d  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cdb64  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cdb6b  mov     [rbp+57h+var_40], 0C00000E5h
0x1800cdb72  mov     [rbp+57h+var_50], rax
0x1800cdb76  test    r11, r11
0x1800cdb79  jz      short loc_1800CDBED
0x1800cdb7b  mov     rdx, r11
0x1800cdb7e  mov     rcx, r10
0x1800cdb81  call    RtlIsTypeSafeHandleValid
0x1800cdb86  test    al, al
0x1800cdb88  jz      short loc_1800CDBED
0x1800cdb8a  mov     ecx, [r11]
0x1800cdb8d  mov     rdx, r10
0x1800cdb90  mov     rax, [r11+20h]
0x1800cdb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdb99  mov     ecx, r13d; dwExceptionCode
0x1800cdb9c  test    ecx, ecx
0x1800cdb9e  jns     short loc_1800CDBB0
0x1800cdba0  xor     r9d, r9d; lpArguments
0x1800cdba3  xor     r8d, r8d; nNumberOfArguments
0x1800cdba6  lea     edx, [r9+1]; dwExceptionFlags
0x1800cdbaa  call    cs:__imp_RaiseException
0x1800cdbb0  mov     [rbp+57h+var_90], r13
0x1800cdbb4  lea     rcx, [rbp+57h+var_88]
0x1800cdbb8  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cdbbd  mov     rcx, [rbp+57h+var_70]; lpMem
0x1800cdbc1  test    rcx, rcx
0x1800cdbc4  jz      short loc_1800CDBD7
0x1800cdbc6  mov     [rbp+57h+var_70], r13
0x1800cdbca  mov     [rbp+57h+var_80], r13
0x1800cdbce  mov     [rbp+57h+var_78], r13
0x1800cdbd2  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800cdbd7  mov     eax, r14d
0x1800cdbda  add     rsp, 90h
0x1800cdbe1  pop     r15
0x1800cdbe3  pop     r14
0x1800cdbe5  pop     r13
0x1800cdbe7  pop     r12
0x1800cdbe9  pop     rsi
0x1800cdbea  pop     rbx
0x1800cdbeb  pop     rbp
0x1800cdbec  retn
0x1800cdbed  mov     [rbp+57h+var_48], 124h
0x1800cdbf4  lea     rcx, [rbp+57h+var_50]
0x1800cdbf8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cdbfd  mov     ecx, [rbp+57h+var_40]
0x1800cdc00  jmp     short loc_1800CDB9C
```
