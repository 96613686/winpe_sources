# Windows::Isolation::Implementation::Rtl::CDefaultStateManager::Scavenge(ulong,ulong *)

- ea: `0x1800b6450`
- end: `0x1800b707b`
- name: `?Scavenge@CDefaultStateManager@Rtl@Implementation@Isolation@Windows@@EEAAJKPEAK@Z`
- size: `3115`
- prototype: `__int64 __fastcall(Windows::Isolation::Implementation::Rtl::CDefaultStateManager *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800125c8`
- `0x180012950`
- `0x180012b1c`
- `0x180013de8`
- `0x180016b4c`
- `0x1800174d4`
- `0x18001766c`
- `0x18001d478`
- `0x18001ddec`
- `0x1800374a8`
- `0x18003d1a8`
- `0x18003d768`
- `0x18003eb10`
- `0x18003f260`
- `0x18003f5c0`
- `0x180040020`
- `0x18004011c`
- `0x180040f70`
- `0x180040f9c`
- `0x18004127c`
- `0x1800416a8`
- `0x18004f2dc`
- `0x180051630`
- `0x180052dec`
- `0x180052ff0`
- `0x18005310c`
- `0x1800b1fec`
- `0x1800b21d0`
- `0x1800b616c`
- `0x1800b6450`
- `0x1800b850c`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b65ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b660a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6a1e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6e7e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b65ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b660a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6a1e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6e7e`

## string_xrefs

- `0x1800b6542`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b69b6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b6dee`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b6fde`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::CDefaultStateManager::Scavenge(
        Windows::Isolation::Implementation::Rtl::CDefaultStateManager *this,
        __int64 a2,
        unsigned int *a3)
{
  __int64 v3; // rdx
  __int64 v5; // rcx
  int SystemIsolatedRegistry; // r15d
  __int64 v7; // r10
  unsigned int *v8; // r11
  signed int v9; // ecx
  __int64 v10; // r10
  unsigned int *v11; // r11
  signed int v12; // ecx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rbx
  _QWORD *v16; // rax
  int v17; // r8d
  __int64 *v18; // rbx
  _QWORD *v19; // rcx
  _QWORD *v20; // rbx
  __int64 v21; // r10
  unsigned int *v22; // r11
  signed int v23; // ecx
  __int64 v24; // rdx
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  bool v30; // bl
  __int64 *v31; // rdx
  _QWORD *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r10
  signed int v35; // ecx
  __int64 v36; // r10
  char v38[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v42; // [rsp+50h] [rbp-B0h]
  __int64 *v43; // [rsp+58h] [rbp-A8h]
  int v44; // [rsp+60h] [rbp-A0h]
  __int64 v45; // [rsp+68h] [rbp-98h]
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h]
  void *lpMem; // [rsp+80h] [rbp-80h]
  int v49; // [rsp+88h] [rbp-78h]
  __int128 v50; // [rsp+90h] [rbp-70h]
  __int64 v51; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v53; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-40h]
  _BYTE *v56; // [rsp+C8h] [rbp-38h]
  int v57; // [rsp+D0h] [rbp-30h]
  __int128 v58; // [rsp+D8h] [rbp-28h]
  __int64 v59; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v60; // [rsp+F0h] [rbp-10h]
  void *v61; // [rsp+F8h] [rbp-8h]
  _QWORD v62[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v63; // [rsp+110h] [rbp+10h]
  char v64[8]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v65; // [rsp+120h] [rbp+20h] BYREF
  __int64 v66; // [rsp+128h] [rbp+28h]
  char v67[48]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v68; // [rsp+160h] [rbp+60h] BYREF
  __int64 v69; // [rsp+168h] [rbp+68h] BYREF
  int v70; // [rsp+170h] [rbp+70h]
  unsigned int v71; // [rsp+18Ch] [rbp+8Ch]
  _BYTE v72[528]; // [rsp+190h] [rbp+90h] BYREF
  _DWORD v73[4]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v3 = *((_QWORD *)this + 1);
  v41 = (__int64)&v41;
  v52 = 0;
  v42 = &v41;
  v39 = 0;
  v43 = &v41;
  v68 = 0;
  v62[1] = v73;
  v63 = 0;
  v69 = 0;
  v70 = 0;
  v44 = 0;
  v45 = 0;
  v73[0] = -1073741766;
  v73[1] = -1073741772;
  v73[2] = -1073741444;
  v62[0] = 3;
  SystemIsolatedRegistry = RtlGetSystemIsolatedRegistry(this, v3, &v52);
  if ( SystemIsolatedRegistry < 0
    || (SystemIsolatedRegistry = RtlGetSystemIsolatedFilesystem(v5, *((_QWORD *)this + 1), &v39),
        SystemIsolatedRegistry < 0)
    || (SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CSubkeyIterator::Initialize(
                                   &v68,
                                   *((_QWORD *)this + 4)),
        SystemIsolatedRegistry < 0) )
  {
    v45 = 0;
    v41 = (__int64)&v41;
    v43 = 0;
    v42 = &v41;
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
LABEL_3:
    if ( v39 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      LODWORD(v56) = -1073741595;
      v54 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v39) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v8 + 4))(*v8, v7);
        v9 = 0;
      }
      else
      {
        LODWORD(v55) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v54);
        v9 = (int)v56;
      }
      if ( v9 < 0 )
        RaiseException(v9, 1u, 0, 0);
      v39 = 0;
    }
    if ( !v52 )
      return (unsigned int)SystemIsolatedRegistry;
    LODWORD(v56) = -1073741595;
    v54 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v52) )
    {
      LODWORD(v55) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v54);
      v12 = (int)v56;
      goto LABEL_15;
    }
    goto LABEL_13;
  }
  while ( (_BYTE)v68 )
  {
    v54 = v71;
    v55 = v71;
    v40 = 0;
    v56 = v72;
    v47 = *((_QWORD *)this + 4);
    lpMem = &v54;
    LODWORD(v63) = 0;
    v46 = 48;
    v49 = 64;
    v50 = 0;
    SystemIsolatedRegistry = RtlIsolatedRegistryOpenKey(
                               v52,
                               (unsigned int)&v40,
                               196639,
                               (unsigned int)&v46,
                               (__int64)v62);
    if ( SystemIsolatedRegistry < 0 )
      goto LABEL_57;
    if ( (int)v63 >= 0 )
    {
      v38[0] = 0;
      v47 = 0;
      v46 = 0;
      lpMem = 0;
      v51 = 0;
      SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::GetValue(
                                 v13,
                                 v40,
                                 g_LUNICODE_STRING_identity,
                                 v38,
                                 &v46);
      if ( SystemIsolatedRegistry < 0 )
        goto LABEL_53;
      if ( v38[0] )
      {
        SystemIsolatedRegistry = appid_ParseAppId<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppIdCD,Windows::Isolation::Rtl::_DEFINITION_APPID_DATA,_LUTF8_STRING>(
                                   v14,
                                   &v46,
                                   &v51);
        if ( SystemIsolatedRegistry < 0 )
          goto LABEL_53;
        v15 = 0;
        if ( *((_QWORD *)this + 9) )
        {
          do
          {
            v65 = v51;
            LODWORD(v53) = 0;
            v16 = (_QWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](
                              (char *)this + 80,
                              v15);
            SystemIsolatedRegistry = RtlGetComponentStoreApplicationState(
                                       (unsigned int)&v53,
                                       *v16,
                                       v17,
                                       (unsigned int)&v65,
                                       (__int64)&v53);
            if ( SystemIsolatedRegistry < 0 )
              goto LABEL_53;
            if ( (_DWORD)v53 )
              goto LABEL_34;
          }
          while ( ++v15 != *((_QWORD *)this + 9) );
        }
      }
      v53 = 0;
      SystemIsolatedRegistry = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::Allocate(
                                            &v53,
                                            v64);
      if ( SystemIsolatedRegistry < 0
        || (v18 = v53, SystemIsolatedRegistry = RtlDuplicateLUnicodeString(&v54, v53 + 4), SystemIsolatedRegistry < 0) )
      {
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v53);
LABEL_53:
        if ( v51 )
        {
          RtlCloseDefinitionAppIdHandle();
          v51 = 0;
        }
        if ( lpMem )
          IsolationFreeStringRoutine(lpMem);
LABEL_57:
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v40);
LABEL_58:
        v45 = 0;
        v41 = (__int64)&v41;
        v43 = 0;
        v42 = &v41;
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
        if ( v39 )
        {
          ++g_nRtlCloseIsolatedFilesystemHandle;
          v46 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          LODWORD(lpMem) = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v39) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v22 + 4))(*v22, v21);
            v23 = 0;
          }
          else
          {
            LODWORD(v47) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
            v23 = (int)lpMem;
          }
          if ( v23 < 0 )
            RaiseException(v23, 1u, 0, 0);
          v39 = 0;
        }
        if ( !v52 )
          return (unsigned int)SystemIsolatedRegistry;
        LODWORD(lpMem) = -1073741595;
        v46 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
          || !(unsigned __int8)RtlIsTypeSafeHandleValid(v52) )
        {
          goto LABEL_68;
        }
LABEL_13:
        (*((void (__fastcall **)(_QWORD, __int64))v11 + 4))(*v11, v10);
LABEL_14:
        v12 = 0;
        goto LABEL_15;
      }
      v19 = (_QWORD *)v18[7];
      v18[7] = (__int64)v40;
      v40 = v19;
      v18[1] = (__int64)v42;
      *v18 = (__int64)&v41;
      v53 = 0;
      *v42 = (__int64)v18;
      v42 = v18;
      v18[2] = (__int64)&v41;
      ++v45;
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v53);
LABEL_34:
      if ( v51 )
      {
        RtlCloseDefinitionAppIdHandle();
        v51 = 0;
      }
      if ( lpMem )
        IsolationFreeStringRoutine(lpMem);
    }
    SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CSubkeyIterator::Next((Windows::Isolation::Implementation::Rtl::CSubkeyIterator *)&v68);
    if ( SystemIsolatedRegistry < 0 )
      goto LABEL_57;
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v40);
  }
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
  v68 = 0;
  v70 = 0;
  while ( 1 )
  {
    v20 = (_QWORD *)v41;
    if ( (__int64 *)v41 == &v41 )
      break;
    v65 = 16;
    v66 = 0;
    if ( v41 && *(__int64 **)(v41 + 16) == &v41 )
    {
      **(_QWORD **)(v41 + 8) = *(_QWORD *)v41;
      *(_QWORD *)(*v20 + 8LL) = v20[1];
      --v45;
    }
    v40 = v20;
    if ( v20[4] )
    {
      v55 = *((_QWORD *)this + 2);
      v54 = 48;
      v58 = 0;
      v56 = v20 + 4;
      v57 = 64;
      SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::DeleteDirectoryRecursively(0, v39, &v54, &v65);
      if ( SystemIsolatedRegistry < 0 )
        goto LABEL_71;
    }
    if ( (_DWORD)v66 != 3 || !v20[4] )
    {
      LODWORD(v63) = 0;
      SystemIsolatedRegistry = RtlIsolatedRegistryDeleteKey(v20[7], v62);
      if ( SystemIsolatedRegistry < 0 )
      {
LABEL_71:
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v40);
        goto LABEL_72;
      }
    }
    BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v40);
  }
  v24 = *((_QWORD *)this + 5);
  v60 = 0;
  v59 = 0;
  v61 = 0;
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CSubkeyIterator::Initialize(&v68, v24);
  if ( SystemIsolatedRegistry < 0 )
  {
    v25 = v61;
    if ( v61 )
    {
      v60 = 0;
      v59 = 0;
      v61 = 0;
      IsolationFreeStringRoutine(v25);
    }
    goto LABEL_72;
  }
  SystemIsolatedRegistry = RtlAllocateLUnicodeString(280, &v59);
  if ( SystemIsolatedRegistry < 0 )
  {
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v59);
LABEL_72:
    v45 = 0;
    v41 = (__int64)&v41;
    v43 = 0;
    v42 = &v41;
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
    goto LABEL_3;
  }
  while ( 1 )
  {
    if ( !(_BYTE)v68 )
    {
      while ( (__int64 *)v41 != &v41 )
      {
        v40 = 0;
        v33 = BCL::CDeque<Windows::Isolation::Implementation::Rtl::CCellToDelete,0>::RemoveHead(&v41);
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::TakeOwnership(
          &v40,
          v33);
        LODWORD(v63) = 0;
        SystemIsolatedRegistry = RtlIsolatedRegistryDeleteKey(v40[7], v62);
        if ( SystemIsolatedRegistry < 0 )
        {
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v40);
          goto LABEL_130;
        }
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v40);
      }
      SystemIsolatedRegistry = 0;
LABEL_130:
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v59);
      v45 = 0;
      v41 = (__int64)&v41;
      v43 = 0;
      v42 = &v41;
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_Traits>::Close(&v39);
      if ( v52 )
        RtlCloseIsolatedRegistryHandle();
      return (unsigned int)SystemIsolatedRegistry;
    }
    v54 = v71;
    v55 = v71;
    v40 = 0;
    v56 = v72;
    v47 = *((_QWORD *)this + 5);
    lpMem = &v54;
    LODWORD(v63) = 0;
    v46 = 48;
    v49 = 64;
    v50 = 0;
    SystemIsolatedRegistry = RtlIsolatedRegistryOpenKey(
                               v52,
                               (unsigned int)&v40,
                               196639,
                               (unsigned int)&v46,
                               (__int64)v62);
    if ( SystemIsolatedRegistry < 0 )
      goto LABEL_118;
    if ( (int)v63 >= 0 )
      break;
LABEL_91:
    SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::CSubkeyIterator::Next((Windows::Isolation::Implementation::Rtl::CSubkeyIterator *)&v68);
    if ( SystemIsolatedRegistry < 0 )
    {
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v40);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v59);
      v45 = 0;
      v41 = (__int64)&v41;
      v43 = 0;
      v42 = &v41;
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_Traits>::Close(&v39);
      goto LABEL_125;
    }
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v40);
  }
  v38[0] = 0;
  v47 = 0;
  v46 = 0;
  lpMem = 0;
  v51 = 0;
  SystemIsolatedRegistry = Windows::Isolation::Implementation::Rtl::GetValue(
                             v26,
                             v40,
                             g_LUNICODE_STRING_LastRunVersion,
                             v38,
                             &v46);
  if ( SystemIsolatedRegistry < 0 )
    goto LABEL_115;
  if ( !v38[0] )
    goto LABEL_86;
  v53 = 0;
  SystemIsolatedRegistry = appid_ParseAppId<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppIdCD,Windows::Isolation::Rtl::_DEFINITION_APPID_DATA,_LUTF8_STRING>(
                             v27,
                             &v46,
                             &v51);
  if ( SystemIsolatedRegistry < 0 )
  {
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v53);
LABEL_115:
    if ( v51 )
    {
      RtlCloseDefinitionAppIdHandle();
      v51 = 0;
    }
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v46);
LABEL_118:
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v40);
    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v59);
    goto LABEL_58;
  }
  v59 = 0;
  SystemIsolatedRegistry = appid_GenerateUnicodeKeyForm<Windows::Isolation::Rtl::_DEFINITION_APPID,Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<CDefAppIdTraits>>(
                             v28,
                             v51,
                             &v59);
  if ( SystemIsolatedRegistry >= 0 )
  {
    v29 = Windows::Isolation::Rtl::CIsolatedObjectAttributes::CIsolatedObjectAttributes(
            v67,
            *((_QWORD *)this + 4),
            &v59);
    SystemIsolatedRegistry = RtlIsolatedRegistryOpenKey(v52, (unsigned int)&v53, 196639, v29, (__int64)v62);
    if ( SystemIsolatedRegistry >= 0 )
    {
      v30 = (int)v63 < 0;
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v53);
      if ( !v30 )
      {
LABEL_88:
        if ( v51 )
        {
          RtlCloseDefinitionAppIdHandle();
          v51 = 0;
        }
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v46);
        goto LABEL_91;
      }
LABEL_86:
      v53 = 0;
      SystemIsolatedRegistry = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::Allocate(
                                            &v53,
                                            v64);
      if ( SystemIsolatedRegistry < 0 )
      {
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v53);
        if ( v51 )
        {
          RtlCloseDefinitionAppIdHandle();
          v51 = 0;
        }
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v46);
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v40);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v59);
        v45 = 0;
        v41 = (__int64)&v41;
        v43 = 0;
        v42 = &v41;
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
        if ( v39 )
        {
          RtlCloseIsolatedFilesystemHandle();
          v39 = 0;
        }
LABEL_125:
        if ( !v52 )
          return (unsigned int)SystemIsolatedRegistry;
        v46 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        LODWORD(lpMem) = -1073741595;
        if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v52) )
          goto LABEL_112;
        goto LABEL_68;
      }
      v31 = v53;
      v53 = 0;
      v32 = (_QWORD *)v31[7];
      v31[7] = (__int64)v40;
      v40 = v32;
      v31[1] = (__int64)v42;
      *v31 = (__int64)&v41;
      *v42 = (__int64)v31;
      v42 = v31;
      v31[2] = (__int64)&v41;
      ++v45;
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(&v53);
      goto LABEL_88;
    }
  }
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v53);
  if ( v51 )
  {
    RtlCloseDefinitionAppIdHandle();
    v51 = 0;
  }
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v46);
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v40);
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v59);
  v45 = 0;
  v41 = (__int64)&v41;
  v43 = 0;
  v42 = &v41;
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v69);
  if ( v39 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    LODWORD(lpMem) = -1073741595;
    v46 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !(unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(v39) )
    {
      LODWORD(v47) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
      goto LABEL_105;
    }
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                                              + 32))(
        *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti,
        v34);
      v35 = 0;
    }
    else
    {
      LODWORD(v47) = 293;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
        &v46,
        &v46);
LABEL_105:
      v35 = (int)lpMem;
    }
    if ( v35 < 0 )
      RaiseException(v35, 1u, 0, 0);
    v39 = 0;
  }
  if ( !v52 )
    return (unsigned int)SystemIsolatedRegistry;
  v46 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
  LODWORD(lpMem) = -1073741595;
  if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v52) )
  {
LABEL_112:
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                                              + 32))(
        *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti,
        v36);
      goto LABEL_14;
    }
    LODWORD(v47) = 293;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v46,
      &v46);
    goto LABEL_69;
  }
LABEL_68:
  LODWORD(v47) = 292;
  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
LABEL_69:
  v12 = (int)lpMem;
LABEL_15:
  if ( v12 < 0 )
    RaiseException(v12, 1u, 0, 0);
  return (unsigned int)SystemIsolatedRegistry;
}

```

## disassembly

```asm
0x1800b6450  push    rbp
0x1800b6452  push    rbx
0x1800b6453  push    rsi
0x1800b6454  push    rdi
0x1800b6455  push    r12
0x1800b6457  push    r13
0x1800b6459  push    r14
0x1800b645b  push    r15
0x1800b645d  lea     rbp, [rsp-2C8h]
0x1800b6465  sub     rsp, 3C8h
0x1800b646c  mov     rax, cs:__security_cookie
0x1800b6473  xor     rax, rsp
0x1800b6476  mov     [rbp+300h+var_50], rax
0x1800b647d  mov     rdx, [rcx+8]
0x1800b6481  lea     rax, [rsp+400h+var_3B8]
0x1800b6486  xor     r12d, r12d
0x1800b6489  mov     [rsp+400h+var_3B8], rax
0x1800b648e  lea     rax, [rsp+400h+var_3B8]
0x1800b6493  mov     [rbp+300h+var_358], r12
0x1800b6497  mov     [rsp+400h+var_3B0], rax
0x1800b649c  lea     r8, [rbp+300h+var_358]
0x1800b64a0  lea     rax, [rsp+400h+var_3B8]
0x1800b64a5  mov     [rsp+400h+var_3C8], r12
0x1800b64aa  mov     [rsp+400h+var_3A8], rax
0x1800b64af  mov     rdi, rcx
0x1800b64b2  lea     rax, [rbp+300h+var_60]
0x1800b64b9  mov     [rbp+300h+var_2A0], r12w
0x1800b64be  mov     [rbp+300h+var_2F8], rax
0x1800b64c2  xor     eax, eax
0x1800b64c4  mov     [rbp+300h+var_2F0], rax
0x1800b64c8  mov     [rbp+300h+var_298], r12
0x1800b64cc  mov     [rbp+300h+var_290], r12d
0x1800b64d0  mov     [rsp+400h+var_3A0], r12d
0x1800b64d5  mov     [rsp+400h+var_398], r12
0x1800b64da  mov     [rbp+300h+var_60], 0C000003Ah
0x1800b64e4  mov     [rbp+300h+var_5C], 0C0000034h
0x1800b64ee  mov     [rbp+300h+var_58], 0C000017Ch
0x1800b64f8  mov     [rbp+300h+var_300], 3
0x1800b6500  call    RtlGetSystemIsolatedRegistry
0x1800b6505  mov     r15d, eax
0x1800b6508  test    eax, eax
0x1800b650a  jns     loc_1800B663A
0x1800b6510  lea     rax, [rsp+400h+var_3B8]
0x1800b6515  mov     [rsp+400h+var_398], r12
0x1800b651a  mov     [rsp+400h+var_3B8], rax
0x1800b651f  lea     rcx, [rbp+300h+var_298]
0x1800b6523  lea     rax, [rsp+400h+var_3B8]
0x1800b6528  mov     [rsp+400h+var_3A8], r12
0x1800b652d  mov     [rsp+400h+var_3B0], rax
0x1800b6532  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800b6537  mov     r14d, 1
0x1800b653d  mov     r10, [rsp+400h+var_3C8]
0x1800b6542  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800b6549  mov     ebx, 0C00000E5h
0x1800b654e  mov     esi, 124h
0x1800b6553  test    r10, r10
0x1800b6556  jz      short loc_1800B65B8
0x1800b6558  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r14; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800b655f  mov     dword ptr [rbp+300h+var_338], ebx
0x1800b6562  mov     [rbp+300h+var_348], rdi
0x1800b6566  test    r10, r10
0x1800b6569  jz      short loc_1800B659D
0x1800b656b  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800b6572  test    r11, r11
0x1800b6575  jz      loc_1800B6615
0x1800b657b  mov     rdx, r11
0x1800b657e  mov     rcx, r10
0x1800b6581  call    RtlIsTypeSafeHandleValid
0x1800b6586  test    al, al
0x1800b6588  jz      loc_1800B6615
0x1800b658e  mov     ecx, [r11]
0x1800b6591  mov     rdx, r10
0x1800b6594  mov     rax, [r11+20h]
0x1800b6598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b659d  mov     ecx, r12d; dwExceptionCode
0x1800b65a0  test    ecx, ecx
0x1800b65a2  jns     short loc_1800B65B3
0x1800b65a4  xor     r9d, r9d; lpArguments
0x1800b65a7  xor     r8d, r8d; nNumberOfArguments
0x1800b65aa  mov     edx, r14d; dwExceptionFlags
0x1800b65ad  call    cs:__imp_RaiseException
0x1800b65b3  mov     [rsp+400h+var_3C8], r12
0x1800b65b8  mov     r10, [rbp+300h+var_358]
0x1800b65bc  test    r10, r10
0x1800b65bf  jz      loc_1800B7055
0x1800b65c5  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x1800b65cc  mov     dword ptr [rbp+300h+var_338], ebx
0x1800b65cf  mov     [rbp+300h+var_348], rdi
0x1800b65d3  test    r11, r11
0x1800b65d6  jz      short loc_1800B6629
0x1800b65d8  mov     rdx, r11
0x1800b65db  mov     rcx, r10
0x1800b65de  call    RtlIsTypeSafeHandleValid
0x1800b65e3  test    al, al
0x1800b65e5  jz      short loc_1800B6629
0x1800b65e7  mov     ecx, [r11]
0x1800b65ea  mov     rax, [r11+20h]
0x1800b65ee  mov     rdx, r10
0x1800b65f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b65f6  mov     ecx, r12d; dwExceptionCode
0x1800b65f9  test    ecx, ecx
0x1800b65fb  jns     loc_1800B7055
0x1800b6601  xor     r9d, r9d; lpArguments
0x1800b6604  xor     r8d, r8d; nNumberOfArguments
0x1800b6607  mov     edx, r14d; dwExceptionFlags
0x1800b660a  call    cs:__imp_RaiseException
0x1800b6610  jmp     loc_1800B7055
0x1800b6615  mov     dword ptr [rbp+300h+var_340], esi
0x1800b6618  lea     rcx, [rbp+300h+var_348]
0x1800b661c  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800b6621  mov     ecx, dword ptr [rbp+300h+var_338]
0x1800b6624  jmp     loc_1800B65A0
0x1800b6629  mov     dword ptr [rbp+300h+var_340], esi
0x1800b662c  lea     rcx, [rbp+300h+var_348]
0x1800b6630  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800b6635  mov     ecx, dword ptr [rbp+300h+var_338]
0x1800b6638  jmp     short loc_1800B65F9
0x1800b663a  mov     rdx, [rdi+8]
0x1800b663e  lea     r8, [rsp+400h+var_3C8]
0x1800b6643  call    RtlGetSystemIsolatedFilesystem
0x1800b6648  mov     r15d, eax
0x1800b664b  test    eax, eax
0x1800b664d  js      loc_1800B6510
0x1800b6653  mov     rdx, [rdi+20h]
0x1800b6657  lea     rcx, [rbp+300h+var_2A0]
0x1800b665b  call    ?Initialize@CSubkeyIterator@Rtl@Implementation@Isolation@Windows@@QEAAJU_ISOLATED_KEY@245@@Z; Windows::Isolation::Implementation::Rtl::CSubkeyIterator::Initialize(Windows::Isolation::Rtl::_ISOLATED_KEY)
0x1800b6660  mov     r15d, eax
0x1800b6663  test    eax, eax
0x1800b6665  js      loc_1800B6510
0x1800b666b  mov     r14d, 1
0x1800b6671  lea     r13d, [r14+2Fh]
0x1800b6675  jmp     loc_1800B6870
0x1800b667a  mov     eax, [rbp+300h+var_274]
0x1800b6680  lea     r9, [rsp+400h+var_390]
0x1800b6685  mov     rcx, [rbp+300h+var_358]
0x1800b6689  lea     rdx, [rsp+400h+var_3C0]
0x1800b668e  mov     [rbp+300h+var_348], rax
0x1800b6692  xorps   xmm0, xmm0
0x1800b6695  mov     [rbp+300h+var_340], rax
0x1800b6699  mov     r8d, 3001Fh
0x1800b669f  lea     rax, [rbp+300h+var_270]
0x1800b66a6  mov     [rsp+400h+var_3C0], r12
0x1800b66ab  mov     [rbp+300h+var_338], rax
0x1800b66af  mov     rax, [rdi+20h]
0x1800b66b3  mov     [rsp+400h+var_388], rax
0x1800b66b8  lea     rax, [rbp+300h+var_348]
0x1800b66bc  mov     [rbp+300h+lpMem], rax
0x1800b66c0  lea     rax, [rbp+300h+var_300]
0x1800b66c4  mov     [rsp+400h+var_3E0], rax
0x1800b66c9  mov     dword ptr [rbp+300h+var_2F0], r12d
0x1800b66cd  mov     [rsp+400h+var_390], r13
0x1800b66d2  mov     [rbp+300h+var_378], 40h ; '@'
0x1800b66d9  movdqu  [rbp+300h+var_370], xmm0
0x1800b66de  call    RtlIsolatedRegistryOpenKey
0x1800b66e3  mov     r15d, eax
0x1800b66e6  test    eax, eax
0x1800b66e8  js      loc_1800B6980
0x1800b66ee  cmp     dword ptr [rbp+300h+var_2F0], r12d
0x1800b66f2  jl      loc_1800B6852
0x1800b66f8  mov     rdx, [rsp+400h+var_3C0]
0x1800b66fd  lea     rax, [rsp+400h+var_390]
0x1800b6702  lea     r9, [rsp+400h+var_3D0]
0x1800b6707  mov     [rsp+400h+var_3E0], rax
0x1800b670c  lea     r8, g_LUNICODE_STRING_identity
0x1800b6713  mov     [rsp+400h+var_3D0], r12b
0x1800b6718  mov     [rsp+400h+var_388], r12
0x1800b671d  mov     [rsp+400h+var_390], r12
0x1800b6722  mov     [rbp+300h+lpMem], r12
0x1800b6726  mov     [rbp+300h+var_360], r12
0x1800b672a  call    ?GetValue@Rtl@Implementation@Isolation@Windows@@YAJKU_ISOLATED_KEY@134@AEBU_LUNICODE_STRING@@AEA_NAEAU_LBLOB@@@Z; Windows::Isolation::Implementation::Rtl::GetValue(ulong,Windows::Isolation::Rtl::_ISOLATED_KEY,_LUNICODE_STRING const &,bool &,_LBLOB &)
0x1800b672f  mov     r15d, eax
0x1800b6732  test    eax, eax
0x1800b6734  js      loc_1800B6960
0x1800b673a  cmp     [rsp+400h+var_3D0], r12b
0x1800b673f  jz      short loc_1800B67AE
0x1800b6741  lea     r8, [rbp+300h+var_360]
0x1800b6745  lea     rdx, [rsp+400h+var_390]
0x1800b674a  call    ??$appid_ParseAppId@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCDefAppIdCD@@U_DEFINITION_APPID_DATA@234@U_LUTF8_STRING@@@@YAJKPEBU_LUTF8_STRING@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; appid_ParseAppId<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppIdCD,Windows::Isolation::Rtl::_DEFINITION_APPID_DATA,_LUTF8_STRING>(ulong,_LUTF8_STRING const *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800b674f  mov     r15d, eax
0x1800b6752  test    eax, eax
0x1800b6754  js      loc_1800B6960
0x1800b675a  mov     rbx, r12
0x1800b675d  cmp     [rdi+48h], r12
0x1800b6761  jz      short loc_1800B67AE
0x1800b6763  mov     rax, [rbp+300h+var_360]
0x1800b6767  lea     rcx, [rdi+50h]
0x1800b676b  mov     rdx, rbx
0x1800b676e  mov     [rbp+300h+var_2E0], rax
0x1800b6772  mov     dword ptr [rbp+300h+var_350], r12d
0x1800b6776  call    ??A?$CSmartArrayHolder@_KV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAAAEAV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800b677b  lea     rcx, [rbp+300h+var_350]
0x1800b677f  lea     r9, [rbp+300h+var_2E0]
0x1800b6783  mov     [rsp+400h+var_3E0], rcx
0x1800b6788  mov     rdx, [rax]
0x1800b678b  call    RtlGetComponentStoreApplicationState
0x1800b6790  mov     r15d, eax
0x1800b6793  test    eax, eax
0x1800b6795  js      loc_1800B6960
0x1800b679b  cmp     dword ptr [rbp+300h+var_350], r12d
0x1800b679f  jnz     loc_1800B6832
0x1800b67a5  add     rbx, r14
0x1800b67a8  cmp     rbx, [rdi+48h]
0x1800b67ac  jnz     short loc_1800B6763
0x1800b67ae  lea     rdx, [rbp+300h+var_2E8]
0x1800b67b2  mov     [rbp+300h+var_350], r12
0x1800b67b6  lea     rcx, [rbp+300h+var_350]
0x1800b67ba  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@VCCellToDelete@Rtl@Implementation@Isolation@Windows@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::Allocate(void)
0x1800b67bf  mov     r15d, [rax]
0x1800b67c2  test    r15d, r15d
0x1800b67c5  js      loc_1800B6957
0x1800b67cb  mov     rbx, [rbp+300h+var_350]
0x1800b67cf  lea     rcx, [rbp+300h+var_348]
0x1800b67d3  lea     rdx, [rbx+20h]
0x1800b67d7  call    RtlDuplicateLUnicodeString
0x1800b67dc  mov     r15d, eax
0x1800b67df  test    eax, eax
0x1800b67e1  js      loc_1800B6957
0x1800b67e7  mov     rcx, [rbx+38h]
0x1800b67eb  mov     rax, [rsp+400h+var_3C0]
0x1800b67f0  mov     [rbx+38h], rax
0x1800b67f4  mov     rax, [rsp+400h+var_3B0]
0x1800b67f9  mov     [rsp+400h+var_3C0], rcx
0x1800b67fe  lea     rcx, [rbp+300h+var_350]
0x1800b6802  mov     [rbx+8], rax
0x1800b6806  lea     rax, [rsp+400h+var_3B8]
0x1800b680b  mov     [rbx], rax
0x1800b680e  mov     rax, [rsp+400h+var_3B0]
0x1800b6813  mov     [rbp+300h+var_350], r12
0x1800b6817  mov     [rax], rbx
0x1800b681a  lea     rax, [rsp+400h+var_3B8]
0x1800b681f  mov     [rsp+400h+var_3B0], rbx
0x1800b6824  mov     [rbx+10h], rax
0x1800b6828  add     [rsp+400h+var_398], r14
0x1800b682d  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@VCCellToDelete@Rtl@Implementation@Isolation@Windows@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<Windows::Isolation::Implementation::Rtl::CCellToDelete>>(void)
0x1800b6832  mov     rcx, [rbp+300h+var_360]
0x1800b6836  test    rcx, rcx
0x1800b6839  jz      short loc_1800B6844
0x1800b683b  call    RtlCloseDefinitionAppIdHandle
0x1800b6840  mov     [rbp+300h+var_360], r12
0x1800b6844  mov     rcx, [rbp+300h+lpMem]; lpMem
0x1800b6848  test    rcx, rcx
0x1800b684b  jz      short loc_1800B6852
0x1800b684d  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b6852  lea     rcx, [rbp+300h+var_2A0]; this
0x1800b6856  call    ?Next@CSubkeyIterator@Rtl@Implementation@Isolation@Windows@@QEAAJXZ; Windows::Isolation::Implementation::Rtl::CSubkeyIterator::Next(void)
0x1800b685b  lea     rcx, [rsp+400h+var_3C0]
0x1800b6860  mov     r15d, eax
0x1800b6863  test    eax, eax
0x1800b6865  js      loc_1800B6985
0x1800b686b  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800b6870  cmp     byte ptr [rbp+300h+var_2A0], r12b
0x1800b6874  jnz     loc_1800B667A
0x1800b687a  lea     rcx, [rbp+300h+var_298]
0x1800b687e  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800b6883  mov     [rbp+300h+var_2A0], r12w
0x1800b6888  mov     [rbp+300h+var_290], r12d
0x1800b688c  mov     rbx, [rsp+400h+var_3B8]
0x1800b6891  lea     rax, [rsp+400h+var_3B8]
0x1800b6896  cmp     rbx, rax
0x1800b6899  jz      loc_1800B6ABC
0x1800b689f  mov     [rbp+300h+var_2E0], 10h
0x1800b68a7  mov     [rbp+300h+var_2D8], r12
0x1800b68ab  test    rbx, rbx
0x1800b68ae  jz      short loc_1800B68D5
0x1800b68b0  lea     rax, [rsp+400h+var_3B8]
0x1800b68b5  cmp     [rbx+10h], rax
0x1800b68b9  jnz     short loc_1800B68D5
0x1800b68bb  mov     rcx, [rbx+8]
0x1800b68bf  mov     rax, [rbx]
0x1800b68c2  mov     [rcx], rax
0x1800b68c5  mov     rcx, [rbx]
0x1800b68c8  mov     rax, [rbx+8]
0x1800b68cc  mov     [rcx+8], rax
0x1800b68d0  sub     [rsp+400h+var_398], r14
0x1800b68d5  lea     rsi, [rbx+20h]
0x1800b68d9  mov     [rsp+400h+var_3C0], rbx
0x1800b68de  cmp     [rsi], r12
0x1800b68e1  jz      short loc_1800B6921
0x1800b68e3  mov     rax, [rdi+10h]
0x1800b68e7  lea     r9, [rbp+300h+var_2E0]
0x1800b68eb  mov     rdx, [rsp+400h+var_3C8]
0x1800b68f0  lea     r8, [rbp+300h+var_348]
0x1800b68f4  xorps   xmm0, xmm0
0x1800b68f7  mov     [rbp+300h+var_340], rax
0x1800b68fb  xor     ecx, ecx
0x1800b68fd  mov     [rbp+300h+var_348], r13
0x1800b6901  movdqu  [rbp+300h+var_328], xmm0
0x1800b6906  mov     [rbp+300h+var_338], rsi
0x1800b690a  mov     [rbp+300h+var_330], 40h ; '@'
0x1800b6911  call    ?DeleteDirectoryRecursively@Rtl@Implementation@Isolation@Windows@@YAJKU_ISOLATED_FILESYSTEM@134@PEBU_ISOLATED_OBJECT_ATTRIBUTES@134@PEAVCDeleteDirectoryRecursivelyDisposition@1234@@Z; Windows::Isolation::Implementation::Rtl::DeleteDirectoryRecursively(ulong,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *,Windows::Isolation::Implementation::Rtl::CDeleteDirectoryRecursivelyDisposition *)
0x1800b6916  mov     r15d, eax
0x1800b6919  test    eax, eax
0x1800b691b  js      loc_1800B6A86
0x1800b6921  cmp     dword ptr [rbp+300h+var_2D8], 3
0x1800b6925  jnz     short loc_1800B692C
0x1800b6927  cmp     [rsi], r12
0x1800b692a  jnz     short loc_1800B6948
0x1800b692c  mov     dword ptr [rbp+300h+var_2F0], r12d
0x1800b6930  lea     rdx, [rbp+300h+var_300]
0x1800b6934  mov     rcx, [rbx+38h]
  ... truncated ...
```
