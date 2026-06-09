# Windows::Isolation::Implementation::Rtl::CDefaultStateManager::SetApplicationRunningState(ulong,Windows::Isolation::Rtl::_APPLICATION_CONTEXT,ulong,ulong *)

- ea: `0x1800b7090`
- end: `0x1800b8506`
- name: `?SetApplicationRunningState@CDefaultStateManager@Rtl@Implementation@Isolation@Windows@@EEAAJKU_APPLICATION_CONTEXT@245@KPEAK@Z`
- size: `5238`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x180013d68`
- `0x180013da4`
- `0x180013de8`
- `0x18001531c`
- `0x18001766c`
- `0x180028930`
- `0x18002ba9c`
- `0x18003c39c`
- `0x18003e9c4`
- `0x18003f260`
- `0x18004011c`
- `0x180040f70`
- `0x180040f9c`
- `0x18004115c`
- `0x180041188`
- `0x1800418c0`
- `0x180041a48`
- `0x18004f2dc`
- `0x180052dec`
- `0x1800b1ed8`
- `0x1800b1f4c`
- `0x1800b2304`
- `0x1800b2750`
- `0x1800b2b08`
- `0x1800b2ed4`
- `0x1800b3598`
- `0x1800b50c4`
- `0x1800b7090`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b75fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b7805`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b7bb1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b7cef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b8351`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b75fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b7805`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b7bb1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b7cef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b8351`

## string_xrefs

- `0x1800b7287`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b77c2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b78fd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b7b65`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b7ca3`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b7db7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b7ef1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b7fd0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b80c1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b81be`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b82c5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b70d1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\sm_default.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::CDefaultStateManager::SetApplicationRunningState(
        _QWORD *a1,
        int a2,
        __int64 a3,
        int a4,
        int *a5)
{
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int SystemIsolatedRegistry; // esi
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // r10
  unsigned int *v16; // r11
  signed int v17; // ecx
  __int64 v18; // rbx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  __int64 v22; // r10
  int v23; // r12d
  int v24; // r8d
  int v25; // r8d
  int v26; // r8d
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  __int64 v30; // r10
  unsigned int *v31; // r11
  signed int v32; // ecx
  int v33; // r8d
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  __int64 v37; // r10
  unsigned int *v38; // r11
  __int64 v39; // rcx
  unsigned int v40; // r15d
  __int64 v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  void *v44; // rcx
  void *v45; // rcx
  char v46; // al
  __int64 v47; // rcx
  bool v48; // al
  __int64 v49; // r10
  unsigned int *v50; // r11
  signed int v51; // ecx
  _QWORD *LeafIdentity; // rax
  _QWORD *v53; // rax
  __int64 v54; // r10
  unsigned int *v55; // r11
  signed int v56; // ecx
  __int64 v57; // r10
  unsigned int *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // r10
  unsigned int *v62; // r11
  _QWORD *v63; // rax
  _QWORD *v64; // rax
  __int64 v65; // r10
  unsigned int *v66; // r11
  __int64 v67; // rcx
  __int64 v68; // r10
  signed int v69; // ecx
  _QWORD *v70; // rax
  _QWORD *v71; // rax
  bool v73[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+68h] [rbp-98h]
  void *lpMem; // [rsp+70h] [rbp-90h]
  __int64 v78; // [rsp+78h] [rbp-88h] BYREF
  __int64 v79; // [rsp+80h] [rbp-80h]
  void *v80; // [rsp+88h] [rbp-78h]
  __int64 v81; // [rsp+90h] [rbp-70h] BYREF
  __int64 v82; // [rsp+98h] [rbp-68h]
  void *v83; // [rsp+A0h] [rbp-60h]
  const char *v84; // [rsp+A8h] [rbp-58h] BYREF
  int v85; // [rsp+B0h] [rbp-50h]
  unsigned int v86; // [rsp+B8h] [rbp-48h]
  __int128 *v87; // [rsp+C0h] [rbp-40h] BYREF
  char v88; // [rsp+C8h] [rbp-38h]
  __int64 v89; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v90; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v91; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v92; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v93; // [rsp+F0h] [rbp-10h] BYREF
  int v94; // [rsp+F8h] [rbp-8h]
  _BYTE v95[16]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v96[3]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v97; // [rsp+128h] [rbp+28h]
  _QWORD v98[6]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v99; // [rsp+170h] [rbp+70h]
  __int64 v100; // [rsp+178h] [rbp+78h]
  __int64 v101; // [rsp+180h] [rbp+80h]
  _QWORD *v102; // [rsp+190h] [rbp+90h]
  int *v103; // [rsp+198h] [rbp+98h]
  __int64 v104; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v105; // [rsp+1A8h] [rbp+A8h]
  int v106; // [rsp+1B8h] [rbp+B8h]
  __int128 v107; // [rsp+1C0h] [rbp+C0h]
  __int128 v108; // [rsp+1D0h] [rbp+D0h] BYREF
  void *v109; // [rsp+1E0h] [rbp+E0h] BYREF
  _QWORD v110[15]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v111[15]; // [rsp+268h] [rbp+168h] BYREF
  _QWORD v112[16]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v103 = a5;
  v84 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\sm_default.cpp";
  v102 = a1;
  v86 = -1073741595;
  if ( a2 )
  {
    v85 = 1178;
LABEL_198:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v84,
      &v84);
    return v86;
  }
  if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(a3) )
  {
    v85 = 1179;
    goto LABEL_198;
  }
  if ( (unsigned int)(a4 - 1) > 1 )
  {
    v85 = 1180;
    goto LABEL_198;
  }
  if ( !(unsigned __int8)RtlIsIsolatedRegistryKeyHandleValid(a1[4]) )
  {
    v85 = 1182;
    goto LABEL_198;
  }
  if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(a1[1]) )
  {
    v85 = 1183;
    goto LABEL_198;
  }
  if ( !(unsigned __int8)RtlIsIsolatedRegistryKeyHandleValid(a1[5]) )
  {
    v85 = 1184;
    goto LABEL_198;
  }
  v9 = a1[1];
  v92 = 0;
  v91 = 0;
  v90 = 0;
  v89 = 0;
  v74 = 0;
  v82 = 0;
  v81 = 0;
  v83 = 0;
  v79 = 0;
  v78 = 0;
  v80 = 0;
  v76 = 0;
  v75 = 0;
  lpMem = 0;
  v96[0] = 0;
  memset(v98, 0, sizeof(v98));
  v100 = 0;
  v99 = 0;
  v101 = 0;
  v94 = 0;
  SystemIsolatedRegistry = RtlGetSystemIsolatedRegistry(v8, v9, &v74);
  if ( SystemIsolatedRegistry < 0
    || (v104 = 24,
        v105 = 0,
        SystemIsolatedRegistry = RtlQueryInformationApplicationContext(v10, a3, &v104),
        SystemIsolatedRegistry < 0)
    || (SystemIsolatedRegistry = RtlAllocateLUnicodeString(280, &v81), SystemIsolatedRegistry < 0) )
  {
    CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
    v12 = lpMem;
    if ( lpMem )
    {
      v76 = 0;
      v75 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v12);
    }
    v13 = v80;
    if ( v80 )
    {
      v79 = 0;
      v78 = 0;
      v80 = 0;
      IsolationFreeStringRoutine(v13);
    }
    v14 = v83;
    if ( v83 )
    {
      v82 = 0;
      v81 = 0;
      v83 = 0;
      IsolationFreeStringRoutine(v14);
    }
    if ( !v74 )
      goto LABEL_52;
    DWORD2(v105) = -1073741595;
    v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v74) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
      v17 = 0;
    }
    else
    {
      LODWORD(v105) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v104);
      v17 = DWORD2(v105);
    }
    if ( v17 >= 0 )
      goto LABEL_51;
    goto LABEL_50;
  }
  v18 = *((_QWORD *)&v105 + 1);
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CreateFamilyKeyForm(*((_QWORD *)&v105 + 1), &v81);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  SystemIsolatedRegistry = RtlAllocateLUnicodeString(280, &v78);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CreateLocationGroupKeyForm(v18, &v78);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  SystemIsolatedRegistry = RtlAllocateLUnicodeString(280, &v75);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CreateIdentityGroupKeyForm(v18, &v75);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  SystemIsolatedRegistry = CApplicationAccessor::Attach(v96, v18);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  *(_QWORD *)&v105 = a1[4];
  *((_QWORD *)&v105 + 1) = v98;
  v104 = 48;
  v106 = 64;
  v107 = 0;
  SystemIsolatedRegistry = RtlIsolatedRegistryCreateKey(v74, (unsigned int)&v92, 131103, (unsigned int)&v104);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  *(_QWORD *)&v105 = a1[5];
  *((_QWORD *)&v105 + 1) = &v81;
  v104 = 48;
  v106 = 64;
  v107 = 0;
  SystemIsolatedRegistry = RtlIsolatedRegistryCreateKey(v74, (unsigned int)&v91, 131103, (unsigned int)&v104);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_39;
  *(_QWORD *)&v105 = a1[5];
  *((_QWORD *)&v105 + 1) = &v78;
  v104 = 48;
  v106 = 64;
  v107 = 0;
  SystemIsolatedRegistry = RtlIsolatedRegistryCreateKey(v74, (unsigned int)&v90, 131103, (unsigned int)&v104);
  if ( SystemIsolatedRegistry < 0
    || (*(_QWORD *)&v105 = a1[5],
        *((_QWORD *)&v105 + 1) = &v75,
        v104 = 48,
        v106 = 64,
        v107 = 0,
        SystemIsolatedRegistry = RtlIsolatedRegistryCreateKey(v74, (unsigned int)&v89, 131103, (unsigned int)&v104),
        SystemIsolatedRegistry < 0) )
  {
LABEL_39:
    CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
    v19 = lpMem;
    if ( lpMem )
    {
      v76 = 0;
      v75 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v19);
    }
    v20 = v80;
    if ( v80 )
    {
      v79 = 0;
      v78 = 0;
      v80 = 0;
      IsolationFreeStringRoutine(v20);
    }
    v21 = v83;
    if ( v83 )
    {
      v82 = 0;
      v81 = 0;
      v83 = 0;
      IsolationFreeStringRoutine(v21);
    }
    v22 = v74;
    if ( !v74 )
      goto LABEL_52;
    DWORD2(v105) = -1073741595;
LABEL_152:
    v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v22) )
    {
LABEL_53:
      LODWORD(v105) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v104);
LABEL_54:
      v17 = DWORD2(v105);
      goto LABEL_49;
    }
    (*((void (__fastcall **)(_QWORD, __int64))v66 + 4))(*v66, v65);
LABEL_48:
    v17 = 0;
    goto LABEL_49;
  }
  v23 = 2;
  if ( a4 == 2 )
  {
    *(_QWORD *)&v105 = &v93;
    v104 = 1;
    v109 = 0;
    *((_QWORD *)&v105 + 1) = 0;
    v87 = 0;
    LODWORD(v93) = -1073741772;
    v108 = 0;
    SystemIsolatedRegistry = RtlIsolatedRegistryQueryValue(
                               v92,
                               (unsigned int)g_LUNICODE_STRING_HasRunBefore,
                               2,
                               (unsigned int)&v108,
                               24,
                               (__int64)&v87,
                               (__int64)&v104);
    if ( SystemIsolatedRegistry < 0 )
      goto LABEL_77;
    if ( DWORD2(v105) == -1073741772 )
      v23 = 131074;
    SystemIsolatedRegistry = RtlIsolatedRegistrySetValue(
                               v91,
                               (unsigned int)g_LUNICODE_STRING_LastRunVersion,
                               v24,
                               3,
                               v101,
                               v99);
    if ( SystemIsolatedRegistry < 0
      || (SystemIsolatedRegistry = RtlIsolatedRegistrySetValue(
                                     v90,
                                     (unsigned int)g_LUNICODE_STRING_LastRunVersion,
                                     v25,
                                     3,
                                     v101,
                                     v99),
          SystemIsolatedRegistry < 0) )
    {
      CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
      v27 = lpMem;
      if ( lpMem )
      {
        v76 = 0;
        v75 = 0;
        lpMem = 0;
        IsolationFreeStringRoutine(v27);
      }
      v28 = v80;
      if ( v80 )
      {
        v79 = 0;
        v78 = 0;
        v80 = 0;
        IsolationFreeStringRoutine(v28);
      }
      v29 = v83;
      if ( v83 )
      {
        v82 = 0;
        v81 = 0;
        v83 = 0;
        IsolationFreeStringRoutine(v29);
      }
      if ( v74 )
      {
        v84 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        v86 = -1073741595;
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v74) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v31 + 4))(*v31, v30);
          v32 = 0;
        }
        else
        {
          v85 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v84);
          v32 = v86;
        }
        if ( v32 < 0 )
          RaiseException(v32, 1u, 0, 0);
        v74 = 0;
      }
      goto LABEL_52;
    }
    SystemIsolatedRegistry = RtlIsolatedRegistrySetValue(
                               v89,
                               (unsigned int)g_LUNICODE_STRING_LastRunVersion,
                               v26,
                               3,
                               v101,
                               v99);
    if ( SystemIsolatedRegistry < 0
      || (LOBYTE(v109) = 1,
          SystemIsolatedRegistry = RtlIsolatedRegistrySetValue(
                                     v92,
                                     (unsigned int)g_LUNICODE_STRING_HasRunBefore,
                                     v33,
                                     3,
                                     (__int64)&v109,
                                     1),
          SystemIsolatedRegistry < 0) )
    {
LABEL_77:
      CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
      v34 = lpMem;
      if ( lpMem )
      {
        v76 = 0;
        v75 = 0;
        lpMem = 0;
        IsolationFreeStringRoutine(v34);
      }
      v35 = v80;
      if ( v80 )
      {
        v79 = 0;
        v78 = 0;
        v80 = 0;
        IsolationFreeStringRoutine(v35);
      }
      v36 = v83;
      if ( v83 )
      {
        v82 = 0;
        v81 = 0;
        v83 = 0;
        IsolationFreeStringRoutine(v36);
      }
      if ( !v74 )
        goto LABEL_52;
      v86 = -1073741595;
      v84 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v74) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v38 + 4))(*v38, v37);
        v17 = 0;
      }
      else
      {
        v85 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v84);
        v17 = v86;
      }
      if ( v17 >= 0 )
        goto LABEL_51;
      goto LABEL_50;
    }
LABEL_190:
    if ( v103 )
      *v103 = v23;
    SystemIsolatedRegistry = 0;
    CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
    if ( !v74 )
      goto LABEL_52;
    RtlCloseIsolatedRegistryHandle();
    goto LABEL_51;
  }
  if ( a4 != 1 )
  {
    v85 = 1609;
    CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
    if ( !v74 )
      goto LABEL_112;
    RtlCloseIsolatedRegistryHandle();
    goto LABEL_179;
  }
  v73[0] = 0;
  v108 = 0u;
  v109 = 0;
  `vector constructor iterator'(v110, 0x78u, 3u, (void *(*)(void *))CApplicationAccessor::CApplicationAccessor);
  v40 = 0;
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::GetValue(
                             v39,
                             v91,
                             g_LUNICODE_STRING_LastRunVersion,
                             v73,
                             &v108);
  if ( SystemIsolatedRegistry < 0 )
  {
LABEL_92:
    `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
    v42 = v109;
    if ( v109 )
    {
      v108 = 0u;
      v109 = 0;
      IsolationFreeStringRoutine(v42);
    }
    CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
    v43 = lpMem;
    if ( lpMem )
    {
      v76 = 0;
      v75 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v43);
    }
    v44 = v80;
    if ( v80 )
    {
      v79 = 0;
      v78 = 0;
      v80 = 0;
      IsolationFreeStringRoutine(v44);
    }
    v45 = v83;
    if ( v83 )
    {
      v82 = 0;
      v81 = 0;
      v83 = 0;
      IsolationFreeStringRoutine(v45);
    }
LABEL_117:
    if ( !v74 )
      goto LABEL_52;
    DWORD2(v105) = -1073741595;
    v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v74) )
    {
      goto LABEL_120;
    }
    goto LABEL_124;
  }
  v46 = 1;
  v88 = 1;
  if ( v73[0] )
  {
    v87 = &v108;
    SystemIsolatedRegistry = CApplicationAccessor::AttachAndParse<_LUTF8_STRING const *>(v110, &v87);
    if ( SystemIsolatedRegistry < 0 )
      goto LABEL_92;
    v73[0] = 0;
    SystemIsolatedRegistry = RtlAreDefinitionAppIdsEqual(v47, v110[0], v96[0], v73);
    v48 = v73[0];
    v73[0] = v73[0];
    if ( SystemIsolatedRegistry < 0 )
      goto LABEL_116;
    if ( v48 )
    {
      v46 = v88;
    }
    else
    {
      v93 = 0;
      v87 = 0;
      if ( *(_QWORD *)v110[3] != *v97 )
      {
        v85 = 1436;
        `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
        CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
        if ( v74 )
        {
          DWORD2(v105) = -1073741595;
          v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v74) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v50 + 4))(*v50, v49);
            v51 = 0;
          }
          else
          {
            LODWORD(v105) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v104);
            v51 = DWORD2(v105);
          }
          if ( v51 < 0 )
            RaiseException(v51, 1u, 0, 0);
          v74 = 0;
        }
        goto LABEL_112;
      }
      LeafIdentity = (_QWORD *)CApplicationAccessor::GetLeafIdentity(v110, v95);
      SystemIsolatedRegistry = Windows::Isolation::Rtl::GetAttribute_version<Windows::Isolation::Rtl::_DEFINITION_IDENTITY>(
                                 *LeafIdentity,
                                 &v93);
      if ( SystemIsolatedRegistry < 0
        || (v53 = (_QWORD *)CApplicationAccessor::GetLeafIdentity(v96, v95),
            SystemIsolatedRegistry = Windows::Isolation::Rtl::GetAttribute_version<Windows::Isolation::Rtl::_DEFINITION_IDENTITY>(
                                       *v53,
                                       &v87),
            SystemIsolatedRegistry < 0) )
      {
LABEL_116:
        `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
        CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
        goto LABEL_117;
      }
      if ( (unsigned __int64)v87 >= v93 )
        goto LABEL_126;
      v46 = 0;
    }
  }
  if ( !v46 )
    goto LABEL_186;
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::GetValue(
                             v41,
                             v90,
                             g_LUNICODE_STRING_LastRunVersion,
                             v73,
                             &v108);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_138;
  if ( v73[0] )
  {
    v87 = &v108;
    SystemIsolatedRegistry = CApplicationAccessor::AttachAndParse<_LUTF8_STRING const *>(v111, &v87);
    if ( SystemIsolatedRegistry < 0
      || (SystemIsolatedRegistry = Windows::Isolation::Rtl::AreEqual(v60, v111[0], v96[0], v73),
          SystemIsolatedRegistry < 0) )
    {
LABEL_138:
      `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
      CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
      if ( !v74 )
        goto LABEL_52;
      v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      DWORD2(v105) = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v74) )
      {
LABEL_120:
        (*((void (__fastcall **)(_QWORD, __int64))v55 + 4))(*v55, v54);
        v56 = 0;
LABEL_121:
        if ( v56 < 0 )
          RaiseException(v56, 1u, 0, 0);
        v74 = 0;
        goto LABEL_52;
      }
LABEL_124:
      LODWORD(v105) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v104);
      v56 = DWORD2(v105);
      goto LABEL_121;
    }
    if ( !v73[0] )
    {
      v87 = 0;
      v93 = 0;
      if ( *(_QWORD *)v111[3] != *v97 )
      {
        v85 = 1497;
        `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
        CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
        if ( v74 )
        {
          DWORD2(v105) = -1073741595;
          v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v74) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v62 + 4))(*v62, v61);
LABEL_176:
            v69 = 0;
LABEL_177:
            if ( v69 < 0 )
              RaiseException(v69, 1u, 0, 0);
LABEL_179:
            v74 = 0;
            goto LABEL_112;
          }
          goto LABEL_171;
        }
        goto LABEL_112;
      }
      v63 = (_QWORD *)CApplicationAccessor::GetLeafIdentity(v111, v95);
      SystemIsolatedRegistry = Windows::Isolation::Rtl::GetAttribute_version<Windows::Isolation::Rtl::_DEFINITION_IDENTITY>(
                                 *v63,
                                 &v87);
      if ( SystemIsolatedRegistry < 0
        || (v64 = (_QWORD *)CApplicationAccessor::GetLeafIdentity(v96, v95),
            SystemIsolatedRegistry = Windows::Isolation::Rtl::GetAttribute_version<Windows::Isolation::Rtl::_DEFINITION_IDENTITY>(
                                       *v64,
                                       &v93),
            SystemIsolatedRegistry < 0) )
      {
LABEL_150:
        `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
        CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
        v22 = v74;
        if ( !v74 )
          goto LABEL_52;
        DWORD2(v105) = -1073741595;
        goto LABEL_152;
      }
      if ( v93 >= (unsigned __int64)v87 )
      {
        v40 = 1;
LABEL_126:
        SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CDefaultStateManager::PerformMigration(
                                   v102,
                                   a3,
                                   &v110[15 * v40],
                                   v96);
        if ( SystemIsolatedRegistry < 0 )
        {
LABEL_127:
          `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
          CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
          if ( !v74 )
            goto LABEL_52;
          DWORD2(v105) = -1073741595;
          v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( !(unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v74) )
            goto LABEL_53;
          v58 = (unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti;
          if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
          {
            LODWORD(v105) = 293;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
              &v104,
              &v104);
            goto LABEL_54;
          }
          goto LABEL_187;
        }
        v23 = 65537;
LABEL_189:
        `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
        goto LABEL_190;
      }
      goto LABEL_186;
    }
  }
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::GetValue(
                             v59,
                             v89,
                             g_LUNICODE_STRING_LastRunVersion,
                             v73,
                             &v108);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_150;
  if ( !v73[0] )
    goto LABEL_186;
  v87 = &v108;
  SystemIsolatedRegistry = CApplicationAccessor::AttachAndParse<_LUTF8_STRING const *>(v112, &v87);
  if ( SystemIsolatedRegistry >= 0 )
  {
    SystemIsolatedRegistry = Windows::Isolation::Rtl::AreEqual(v67, v112[0], v96[0], v73);
    if ( SystemIsolatedRegistry >= 0 )
    {
      if ( !v73[0] )
      {
        v87 = 0;
        v93 = 0;
        if ( *(_QWORD *)v112[3] != *v97 )
        {
          v85 = 1559;
          `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
          CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
          if ( v74 )
          {
            DWORD2(v105) = -1073741595;
            v104 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v74) )
            {
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
              {
                (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                                                        + 32))(
                  *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti,
                  v68);
                goto LABEL_176;
              }
              LODWORD(v105) = 293;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                &v104,
                &v104);
LABEL_174:
              v69 = DWORD2(v105);
              goto LABEL_177;
            }
LABEL_171:
            LODWORD(v105) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v104);
            goto LABEL_174;
          }
LABEL_112:
          Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v89);
          Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v90);
          Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v91);
          Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v92);
          goto LABEL_198;
        }
        v70 = (_QWORD *)CApplicationAccessor::GetLeafIdentity(v112, v95);
        SystemIsolatedRegistry = Windows::Isolation::Rtl::GetAttribute_version<Windows::Isolation::Rtl::_DEFINITION_IDENTITY>(
                                   *v70,
                                   &v87);
        if ( SystemIsolatedRegistry < 0 )
          goto LABEL_127;
        v71 = (_QWORD *)CApplicationAccessor::GetLeafIdentity(v96, v95);
        SystemIsolatedRegistry = Windows::Isolation::Rtl::GetAttribute_version<Windows::Isolation::Rtl::_DEFINITION_IDENTITY>(
                                   *v71,
                                   &v93);
        if ( SystemIsolatedRegistry < 0 )
          goto LABEL_127;
        if ( v93 >= (unsigned __int64)v87 )
        {
          v73[0] = 0;
          SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::DoesDeploymentManifestIncludeDeploymentProvider(
                                     a3,
                                     v18,
                                     v73);
          if ( SystemIsolatedRegistry < 0 )
            goto LABEL_127;
          if ( v73[0] )
          {
            v40 = 2;
            goto LABEL_126;
          }
        }
      }
LABEL_186:
      v23 = 1;
      goto LABEL_189;
    }
  }
  `vector destructor iterator'(v110, 0x78u, 3u, (void (*)(void *))CApplicationAccessor::~CApplicationAccessor);
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v108);
  CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v96);
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v75);
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v78);
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v81);
  if ( !v74 )
    goto LABEL_52;
  v86 = -1073741595;
  v84 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
  if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v74) )
  {
    v58 = (unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
    {
LABEL_187:
      (*((void (__fastcall **)(_QWORD, __int64))v58 + 4))(*v58, v57);
      goto LABEL_48;
    }
    v85 = 293;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v84,
      &v84);
  }
  else
  {
    v85 = 292;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v84);
  }
  v17 = v86;
LABEL_49:
  if ( v17 < 0 )
LABEL_50:
    RaiseException(v17, 1u, 0, 0);
LABEL_51:
  v74 = 0;
LABEL_52:
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v89);
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v90);
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v91);
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v92);
  return (unsigned int)SystemIsolatedRegistry;
}

```

## disassembly

```asm
0x1800b7090  mov     [rsp-8+arg_8], rbx
0x1800b7095  push    rbp
0x1800b7096  push    rsi
0x1800b7097  push    rdi
0x1800b7098  push    r12
0x1800b709a  push    r13
0x1800b709c  push    r14
0x1800b709e  push    r15
0x1800b70a0  lea     rbp, [rsp-270h]
0x1800b70a8  sub     rsp, 370h
0x1800b70af  mov     rax, cs:__security_cookie
0x1800b70b6  xor     rax, rsp
0x1800b70b9  mov     [rbp+2A0h+var_40], rax
0x1800b70c0  mov     rax, [rbp+2A0h+arg_20]
0x1800b70c7  xor     r13d, r13d
0x1800b70ca  mov     [rbp+2A0h+var_208], rax
0x1800b70d1  lea     rax, aOnecoreComNetf_22; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800b70d8  mov     [rbp+2A0h+var_2F8], rax
0x1800b70dc  mov     r12d, 0C00000E5h
0x1800b70e2  mov     [rbp+2A0h+var_210], rcx
0x1800b70e9  mov     r14d, r9d
0x1800b70ec  mov     [rbp+2A0h+var_2E8], r12d
0x1800b70f0  mov     rdi, r8
0x1800b70f3  mov     r15, rcx
0x1800b70f6  test    edx, edx
0x1800b70f8  jz      short loc_1800B7106
0x1800b70fa  mov     [rbp+2A0h+var_2F0], 49Ah
0x1800b7101  jmp     loc_1800B84CA
0x1800b7106  mov     rdx, cs:?ms_ptti@?$CTsObjectTraits@U_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@VCApplicationContext@2IsolationImplementation@@VCApplicationContextCD@26@VCApplicationContextImplTraits@26@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
0x1800b710d  test    rdx, rdx
0x1800b7110  jz      loc_1800B84C3
0x1800b7116  mov     rcx, rdi
0x1800b7119  call    RtlIsTypeSafeHandleValid
0x1800b711e  test    al, al
0x1800b7120  jz      loc_1800B84C3
0x1800b7126  lea     eax, [r14-1]
0x1800b712a  mov     ebx, 1
0x1800b712f  cmp     eax, ebx
0x1800b7131  jbe     short loc_1800B713F
0x1800b7133  mov     [rbp+2A0h+var_2F0], 49Ch
0x1800b713a  jmp     loc_1800B84CA
0x1800b713f  mov     rcx, [r15+20h]
0x1800b7143  call    RtlIsIsolatedRegistryKeyHandleValid
0x1800b7148  test    al, al
0x1800b714a  jnz     short loc_1800B7158
0x1800b714c  mov     [rbp+2A0h+var_2F0], 49Eh
0x1800b7153  jmp     loc_1800B84CA
0x1800b7158  mov     rdx, cs:?ms_ptti@?$CTsObjectTraits@U_SYSTEM@Rtl@Isolation@Windows@@VCSystem@2Implementation@34@VCSystemCD@2634@VCSystemImplTraits@2634@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
0x1800b715f  test    rdx, rdx
0x1800b7162  jz      loc_1800B84BA
0x1800b7168  mov     rcx, [r15+8]
0x1800b716c  call    RtlIsTypeSafeHandleValid
0x1800b7171  test    al, al
0x1800b7173  jz      loc_1800B84BA
0x1800b7179  mov     rcx, [r15+28h]
0x1800b717d  call    RtlIsIsolatedRegistryKeyHandleValid
0x1800b7182  test    al, al
0x1800b7184  jnz     short loc_1800B7192
0x1800b7186  mov     [rbp+2A0h+var_2F0], 4A0h
0x1800b718d  jmp     loc_1800B84CA
0x1800b7192  mov     rdx, [r15+8]
0x1800b7196  lea     r8, [rsp+3A0h+var_348]
0x1800b719b  mov     [rbp+2A0h+var_2B8], r13
0x1800b719f  mov     [rbp+2A0h+var_2C0], r13
0x1800b71a3  mov     [rbp+2A0h+var_2C8], r13
0x1800b71a7  mov     [rbp+2A0h+var_2D0], r13
0x1800b71ab  mov     [rsp+3A0h+var_348], r13
0x1800b71b0  mov     [rbp+2A0h+var_308], r13
0x1800b71b4  mov     [rbp+2A0h+var_310], r13
0x1800b71b8  mov     [rbp+2A0h+var_300], r13
0x1800b71bc  mov     [rbp+2A0h+var_320], r13
0x1800b71c0  mov     [rsp+3A0h+var_328], r13
0x1800b71c5  mov     [rbp+2A0h+var_318], r13
0x1800b71c9  mov     [rsp+3A0h+var_338], r13
0x1800b71ce  mov     [rsp+3A0h+var_340], r13
0x1800b71d3  mov     [rsp+3A0h+lpMem], r13
0x1800b71d8  mov     [rbp+2A0h+var_290], r13
0x1800b71dc  mov     [rbp+2A0h+var_258], r13
0x1800b71e0  mov     [rbp+2A0h+var_260], r13
0x1800b71e4  mov     [rbp+2A0h+var_250], r13
0x1800b71e8  mov     [rbp+2A0h+var_240], r13
0x1800b71ec  mov     [rbp+2A0h+var_248], r13
0x1800b71f0  mov     [rbp+2A0h+var_238], r13
0x1800b71f4  mov     [rbp+2A0h+var_228], r13
0x1800b71f8  mov     [rbp+2A0h+var_230], r13
0x1800b71fc  mov     [rbp+2A0h+var_220], r13
0x1800b7203  mov     [rbp+2A0h+var_2A8], r13d
0x1800b7207  call    RtlGetSystemIsolatedRegistry
0x1800b720c  mov     esi, eax
0x1800b720e  test    eax, eax
0x1800b7210  jns     loc_1800B72EF
0x1800b7216  lea     rcx, [rbp+2A0h+var_290]; this
0x1800b721a  call    ??1CApplicationAccessor@@QEAA@XZ; CApplicationAccessor::~CApplicationAccessor(void)
0x1800b721f  mov     rcx, [rsp+3A0h+lpMem]; lpMem
0x1800b7224  test    rcx, rcx
0x1800b7227  jz      short loc_1800B723D
0x1800b7229  mov     [rsp+3A0h+var_338], r13
0x1800b722e  mov     [rsp+3A0h+var_340], r13
0x1800b7233  mov     [rsp+3A0h+lpMem], r13
0x1800b7238  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b723d  mov     rcx, [rbp+2A0h+var_318]; lpMem
0x1800b7241  test    rcx, rcx
0x1800b7244  jz      short loc_1800B7258
0x1800b7246  mov     [rbp+2A0h+var_320], r13
0x1800b724a  mov     [rsp+3A0h+var_328], r13
0x1800b724f  mov     [rbp+2A0h+var_318], r13
0x1800b7253  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b7258  mov     rcx, [rbp+2A0h+var_300]; lpMem
0x1800b725c  test    rcx, rcx
0x1800b725f  jz      short loc_1800B7272
0x1800b7261  mov     [rbp+2A0h+var_308], r13
0x1800b7265  mov     [rbp+2A0h+var_310], r13
0x1800b7269  mov     [rbp+2A0h+var_300], r13
0x1800b726d  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b7272  mov     r10, [rsp+3A0h+var_348]
0x1800b7277  test    r10, r10
0x1800b727a  jz      loc_1800B7608
0x1800b7280  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x1800b7287  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800b728e  mov     dword ptr [rbp+2A0h+var_1F8+8], r12d
0x1800b7295  mov     [rbp+2A0h+var_200], rax
0x1800b729c  test    r11, r11
0x1800b729f  jz      short loc_1800B72D1
0x1800b72a1  mov     rdx, r11
0x1800b72a4  mov     rcx, r10
0x1800b72a7  call    RtlIsTypeSafeHandleValid
0x1800b72ac  test    al, al
0x1800b72ae  jz      short loc_1800B72D1
0x1800b72b0  mov     ecx, [r11]
0x1800b72b3  mov     rdx, r10
0x1800b72b6  mov     rax, [r11+20h]
0x1800b72ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b72bf  mov     ecx, r13d
0x1800b72c2  test    ecx, ecx
0x1800b72c4  jns     loc_1800B7603
0x1800b72ca  mov     edx, ebx
0x1800b72cc  jmp     loc_1800B75F7
0x1800b72d1  mov     dword ptr [rbp+2A0h+var_1F8], 124h
0x1800b72db  lea     rcx, [rbp+2A0h+var_200]
0x1800b72e2  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800b72e7  mov     ecx, dword ptr [rbp+2A0h+var_1F8+8]
0x1800b72ed  jmp     short loc_1800B72C2
0x1800b72ef  xorps   xmm0, xmm0
0x1800b72f2  mov     [rbp+2A0h+var_200], 18h
0x1800b72fd  lea     r8, [rbp+2A0h+var_200]
0x1800b7304  mov     rdx, rdi
0x1800b7307  movups  [rbp+2A0h+var_1F8], xmm0
0x1800b730e  call    RtlQueryInformationApplicationContext
0x1800b7313  mov     esi, eax
0x1800b7315  test    eax, eax
0x1800b7317  js      loc_1800B7216
0x1800b731d  lea     rdx, [rbp+2A0h+var_310]
0x1800b7321  mov     ecx, 118h
0x1800b7326  call    RtlAllocateLUnicodeString
0x1800b732b  mov     esi, eax
0x1800b732d  test    eax, eax
0x1800b732f  js      loc_1800B7216
0x1800b7335  mov     rbx, qword ptr [rbp+2A0h+var_1F8+8]
0x1800b733c  lea     rdx, [rbp+2A0h+var_310]
0x1800b7340  mov     rcx, rbx
0x1800b7343  call    ?CreateFamilyKeyForm@Rtl@Implementation@Isolation@Windows@@YAJU_DEFINITION_APPID@134@PEAU_LUNICODE_STRING@@@Z; Windows::Isolation::Implementation::Rtl::CreateFamilyKeyForm(Windows::Isolation::Rtl::_DEFINITION_APPID,_LUNICODE_STRING *)
0x1800b7348  mov     esi, eax
0x1800b734a  test    eax, eax
0x1800b734c  js      loc_1800B756A
0x1800b7352  lea     rdx, [rsp+3A0h+var_328]
0x1800b7357  mov     ecx, 118h
0x1800b735c  call    RtlAllocateLUnicodeString
0x1800b7361  mov     esi, eax
0x1800b7363  test    eax, eax
0x1800b7365  js      loc_1800B756A
0x1800b736b  lea     rdx, [rsp+3A0h+var_328]
0x1800b7370  mov     rcx, rbx
0x1800b7373  call    ?CreateLocationGroupKeyForm@Rtl@Implementation@Isolation@Windows@@YAJU_DEFINITION_APPID@134@PEAU_LUNICODE_STRING@@@Z; Windows::Isolation::Implementation::Rtl::CreateLocationGroupKeyForm(Windows::Isolation::Rtl::_DEFINITION_APPID,_LUNICODE_STRING *)
0x1800b7378  mov     esi, eax
0x1800b737a  test    eax, eax
0x1800b737c  js      loc_1800B756A
0x1800b7382  lea     rdx, [rsp+3A0h+var_340]
0x1800b7387  mov     ecx, 118h
0x1800b738c  call    RtlAllocateLUnicodeString
0x1800b7391  mov     esi, eax
0x1800b7393  test    eax, eax
0x1800b7395  js      loc_1800B756A
0x1800b739b  lea     rdx, [rsp+3A0h+var_340]
0x1800b73a0  mov     rcx, rbx
0x1800b73a3  call    ?CreateIdentityGroupKeyForm@Rtl@Implementation@Isolation@Windows@@YAJU_DEFINITION_APPID@134@PEAU_LUNICODE_STRING@@@Z; Windows::Isolation::Implementation::Rtl::CreateIdentityGroupKeyForm(Windows::Isolation::Rtl::_DEFINITION_APPID,_LUNICODE_STRING *)
0x1800b73a8  lea     rcx, [rbp+2A0h+var_290]
0x1800b73ac  mov     esi, eax
0x1800b73ae  test    eax, eax
0x1800b73b0  js      loc_1800B756E
0x1800b73b6  mov     rdx, rbx
0x1800b73b9  call    ?Attach@CApplicationAccessor@@QEAAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; CApplicationAccessor::Attach(Windows::Isolation::Rtl::_DEFINITION_APPID)
0x1800b73be  mov     esi, eax
0x1800b73c0  test    eax, eax
0x1800b73c2  js      loc_1800B756A
0x1800b73c8  mov     rax, [r15+20h]
0x1800b73cc  lea     r9, [rbp+2A0h+var_200]
0x1800b73d3  mov     rcx, [rsp+3A0h+var_348]
0x1800b73d8  lea     rdx, [rbp+2A0h+var_2B8]
0x1800b73dc  mov     qword ptr [rbp+2A0h+var_1F8], rax
0x1800b73e3  xorps   xmm0, xmm0
0x1800b73e6  lea     rax, [rbp+2A0h+var_260]
0x1800b73ea  mov     [rsp+3A0h+var_360], r13
0x1800b73ef  mov     qword ptr [rbp+2A0h+var_1F8+8], rax
0x1800b73f6  mov     r8d, 2001Fh
0x1800b73fc  lea     rax, [rbp+2A0h+var_2A8]
0x1800b7400  mov     [rbp+2A0h+var_200], 30h ; '0'
0x1800b740b  mov     [rsp+3A0h+var_368], rax
0x1800b7410  mov     [rbp+2A0h+var_1E8], 40h ; '@'
0x1800b741a  movdqu  [rbp+2A0h+var_1E0], xmm0
0x1800b7422  call    RtlIsolatedRegistryCreateKey
0x1800b7427  mov     esi, eax
0x1800b7429  test    eax, eax
0x1800b742b  js      loc_1800B756A
0x1800b7431  mov     rax, [r15+28h]
0x1800b7435  lea     r9, [rbp+2A0h+var_200]
0x1800b743c  mov     rcx, [rsp+3A0h+var_348]
0x1800b7441  lea     rdx, [rbp+2A0h+var_2C0]
0x1800b7445  mov     qword ptr [rbp+2A0h+var_1F8], rax
0x1800b744c  xorps   xmm0, xmm0
0x1800b744f  lea     rax, [rbp+2A0h+var_310]
0x1800b7453  mov     [rsp+3A0h+var_360], r13
0x1800b7458  mov     qword ptr [rbp+2A0h+var_1F8+8], rax
0x1800b745f  mov     r8d, 2001Fh
0x1800b7465  lea     rax, [rbp+2A0h+var_2A8]
0x1800b7469  mov     [rbp+2A0h+var_200], 30h ; '0'
0x1800b7474  mov     [rsp+3A0h+var_368], rax
0x1800b7479  mov     [rbp+2A0h+var_1E8], 40h ; '@'
0x1800b7483  movdqu  [rbp+2A0h+var_1E0], xmm0
0x1800b748b  call    RtlIsolatedRegistryCreateKey
0x1800b7490  mov     esi, eax
0x1800b7492  test    eax, eax
0x1800b7494  js      loc_1800B756A
0x1800b749a  mov     rax, [r15+28h]
0x1800b749e  lea     r9, [rbp+2A0h+var_200]
0x1800b74a5  mov     rcx, [rsp+3A0h+var_348]
0x1800b74aa  lea     rdx, [rbp+2A0h+var_2C8]
0x1800b74ae  mov     qword ptr [rbp+2A0h+var_1F8], rax
0x1800b74b5  xorps   xmm0, xmm0
0x1800b74b8  lea     rax, [rsp+3A0h+var_328]
0x1800b74bd  mov     [rsp+3A0h+var_360], r13
0x1800b74c2  mov     qword ptr [rbp+2A0h+var_1F8+8], rax
0x1800b74c9  mov     r8d, 2001Fh
0x1800b74cf  lea     rax, [rbp+2A0h+var_2A8]
0x1800b74d3  mov     [rbp+2A0h+var_200], 30h ; '0'
0x1800b74de  mov     [rsp+3A0h+var_368], rax
0x1800b74e3  mov     [rbp+2A0h+var_1E8], 40h ; '@'
0x1800b74ed  movdqu  [rbp+2A0h+var_1E0], xmm0
0x1800b74f5  call    RtlIsolatedRegistryCreateKey
0x1800b74fa  mov     esi, eax
0x1800b74fc  test    eax, eax
0x1800b74fe  js      short loc_1800B756A
0x1800b7500  mov     rax, [r15+28h]
0x1800b7504  lea     r9, [rbp+2A0h+var_200]
0x1800b750b  mov     rcx, [rsp+3A0h+var_348]
0x1800b7510  lea     rdx, [rbp+2A0h+var_2D0]
0x1800b7514  mov     qword ptr [rbp+2A0h+var_1F8], rax
0x1800b751b  xorps   xmm0, xmm0
0x1800b751e  lea     rax, [rsp+3A0h+var_340]
0x1800b7523  mov     [rsp+3A0h+var_360], r13
0x1800b7528  mov     qword ptr [rbp+2A0h+var_1F8+8], rax
0x1800b752f  mov     r8d, 2001Fh
0x1800b7535  lea     rax, [rbp+2A0h+var_2A8]
0x1800b7539  mov     [rbp+2A0h+var_200], 30h ; '0'
0x1800b7544  mov     [rsp+3A0h+var_368], rax
0x1800b7549  mov     [rbp+2A0h+var_1E8], 40h ; '@'
0x1800b7553  movdqu  [rbp+2A0h+var_1E0], xmm0
0x1800b755b  call    RtlIsolatedRegistryCreateKey
0x1800b7560  mov     esi, eax
0x1800b7562  test    eax, eax
0x1800b7564  jns     loc_1800B764F
0x1800b756a  lea     rcx, [rbp+2A0h+var_290]; this
0x1800b756e  call    ??1CApplicationAccessor@@QEAA@XZ; CApplicationAccessor::~CApplicationAccessor(void)
0x1800b7573  mov     rcx, [rsp+3A0h+lpMem]; lpMem
0x1800b7578  test    rcx, rcx
0x1800b757b  jz      short loc_1800B7591
0x1800b757d  mov     [rsp+3A0h+var_338], r13
0x1800b7582  mov     [rsp+3A0h+var_340], r13
0x1800b7587  mov     [rsp+3A0h+lpMem], r13
0x1800b758c  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b7591  mov     rcx, [rbp+2A0h+var_318]; lpMem
0x1800b7595  test    rcx, rcx
0x1800b7598  jz      short loc_1800B75AC
0x1800b759a  mov     [rbp+2A0h+var_320], r13
0x1800b759e  mov     [rsp+3A0h+var_328], r13
0x1800b75a3  mov     [rbp+2A0h+var_318], r13
0x1800b75a7  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b75ac  mov     rcx, [rbp+2A0h+var_300]; lpMem
0x1800b75b0  test    rcx, rcx
0x1800b75b3  jz      short loc_1800B75C6
0x1800b75b5  mov     [rbp+2A0h+var_308], r13
0x1800b75b9  mov     [rbp+2A0h+var_310], r13
0x1800b75bd  mov     [rbp+2A0h+var_300], r13
0x1800b75c1  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b75c6  mov     r10, [rsp+3A0h+var_348]
0x1800b75cb  test    r10, r10
0x1800b75ce  jz      short loc_1800B7608
0x1800b75d0  mov     dword ptr [rbp+2A0h+var_1F8+8], r12d
0x1800b75d7  jmp     loc_1800B80BA
0x1800b75dc  mov     rax, [r11+20h]
0x1800b75e0  mov     ecx, [r11]
  ... truncated ...
```
