# Windows::Isolation::Implementation::Rtl::CDefaultStateManager::Initialize(Windows::Isolation::Implementation::Rtl::CDefaultStateManagerCD *)

- ea: `0x1800b3b30`
- end: `0x1800b4193`
- name: `?Initialize@CDefaultStateManager@Rtl@Implementation@Isolation@Windows@@AEAAJPEAVCDefaultStateManagerCD@2345@@Z`
- size: `1635`
- prototype: `__int64 __fastcall(Windows::Isolation::Implementation::Rtl::CDefaultStateManager *__hidden this, struct Windows::Isolation::Implementation::Rtl::CDefaultStateManagerCD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b34e0`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x1800165fc`
- `0x18001766c`
- `0x18001de74`
- `0x180036e78`
- `0x180037aa4`
- `0x18003ff84`
- `0x180040020`
- `0x18004011c`
- `0x180041188`
- `0x18004f2dc`
- `0x1800504a0`
- `0x180050668`
- `0x1800b3b30`
- `0x1800fe440`
- `0x18010ce48`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b3bec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4080`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b40dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4130`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b3bec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4080`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b40dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4130`

## string_xrefs

- `0x1800b3ba3`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b3d51`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b401a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b3c91`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::CDefaultStateManager::Initialize(
        Windows::Isolation::Implementation::Rtl::CDefaultStateManager *this,
        struct Windows::Isolation::Implementation::Rtl::CDefaultStateManagerCD *a2)
{
  int v3; // eax
  int SystemIsolatedFilesystem; // r15d
  __int64 v5; // r10
  unsigned int *v6; // r11
  signed int v7; // ecx
  __int64 v8; // r13
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  __int64 v11; // rbx
  unsigned __int64 v12; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  bool v17; // zf
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r10
  unsigned int *v21; // r11
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  void *v25; // xmm2_8
  __int128 v26; // xmm0
  void *v27; // xmm3_8
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rax
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rax
  __int64 v36; // r10
  unsigned int *v37; // r11
  signed int v38; // ecx
  __int64 v39; // r10
  unsigned int *v40; // r11
  signed int v41; // ecx
  __int64 v42; // r10
  unsigned int *v43; // r11
  signed int v44; // ecx
  __int128 v46; // [rsp+50h] [rbp-79h] BYREF
  void *v47; // [rsp+60h] [rbp-69h]
  int v48; // [rsp+68h] [rbp-61h]
  __int128 v49; // [rsp+70h] [rbp-59h]
  __int64 v50; // [rsp+80h] [rbp-49h] BYREF
  __int64 v51; // [rsp+88h] [rbp-41h] BYREF
  __int64 v52; // [rsp+90h] [rbp-39h] BYREF
  __int64 v53; // [rsp+98h] [rbp-31h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v55; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int64 v56; // [rsp+B8h] [rbp-11h]
  unsigned __int64 v57; // [rsp+C0h] [rbp-9h]
  _QWORD v58[2]; // [rsp+C8h] [rbp-1h] BYREF
  void *lpMem; // [rsp+D8h] [rbp+Fh]
  __int64 v61; // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v62; // [rsp+140h] [rbp+77h] BYREF
  __int64 v63; // [rsp+148h] [rbp+7Fh] BYREF

  v56 = 0;
  v57 = 0;
  v62 = 0;
  v55 = 0;
  v3 = RtlDuplicateSystemHandle(*(_QWORD *)a2, &v62);
  SystemIsolatedFilesystem = 0;
  if ( v3 < 0 )
    SystemIsolatedFilesystem = v3;
  if ( SystemIsolatedFilesystem >= 0 )
  {
    v8 = *((_QWORD *)a2 + 2);
    SystemIsolatedFilesystem = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(
                                            &v55,
                                            &v61,
                                            v8);
    if ( SystemIsolatedFilesystem >= 0 )
    {
      v10 = v57;
      v11 = 0;
      if ( v8 )
      {
        while ( 1 )
        {
          v12 = v56;
          if ( v10 < v56 )
          {
            v13 = *((_QWORD *)&v55 + 1) + 8 * v10;
            v14 = v56 - v10;
            if ( v56 != v10 )
            {
              do
              {
                v15 = (_QWORD *)v13;
                v13 += 8;
                *v15 = 0;
                --v14;
              }
              while ( v14 );
            }
            v10 = v12;
            v57 = v12;
          }
          LODWORD(v47) = -1073741595;
          v16 = (_QWORD *)(*((_QWORD *)&v55 + 1) + 8 * v11);
          v17 = *v16 == 0;
          *(_QWORD *)&v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
          if ( v17 )
          {
            v18 = RtlDuplicateComponentStoreHandle(*(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v11), v16);
            SystemIsolatedFilesystem = 0;
            if ( v18 < 0 )
              SystemIsolatedFilesystem = v18;
          }
          else
          {
            DWORD2(v46) = 142;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
              &v46,
              &v46);
            SystemIsolatedFilesystem = (int)v47;
          }
          if ( SystemIsolatedFilesystem < 0 )
            break;
          if ( ++v11 == v8 )
            goto LABEL_24;
        }
        if ( v62 )
        {
          LODWORD(v47) = -1073741595;
          *(_QWORD *)&v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v62) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v21 + 4))(*v21, v20);
            v7 = 0;
          }
          else
          {
            DWORD2(v46) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
            v7 = (int)v47;
          }
          if ( v7 >= 0 )
            goto LABEL_10;
          goto LABEL_9;
        }
        goto LABEL_75;
      }
LABEL_24:
      v63 = 0;
      v50 = 0;
      v51 = 0;
      v61 = 0;
      v58[1] = 0;
      v58[0] = 0;
      lpMem = 0;
      SystemIsolatedFilesystem = RtlGetSystemIsolatedFilesystem(v9, v62, &v50);
      if ( SystemIsolatedFilesystem < 0
        || (SystemIsolatedFilesystem = RtlGetSystemIsolatedRegistry(v19, v62, &v63), SystemIsolatedFilesystem < 0)
        || (v54 = *((_QWORD *)a2 + 1),
            SystemIsolatedFilesystem = Windows::Isolation::Implementation::Rtl::GetUserStateStoreRootKey(
                                         v63,
                                         &v54,
                                         v22,
                                         &v51),
            SystemIsolatedFilesystem < 0) )
      {
LABEL_54:
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v51);
        if ( v50 )
        {
          ++g_nRtlCloseIsolatedFilesystemHandle;
          *(_QWORD *)&v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          LODWORD(v47) = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v50) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v37 + 4))(*v37, v36);
            v38 = 0;
          }
          else
          {
            DWORD2(v46) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
            v38 = (int)v47;
          }
          if ( v38 < 0 )
            RaiseException(v38, 1u, 0, 0);
          v50 = 0;
        }
        if ( v63 )
        {
          *(_QWORD *)&v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          LODWORD(v47) = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v63) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v40 + 4))(*v40, v39);
            v41 = 0;
          }
          else
          {
            DWORD2(v46) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
            v41 = (int)v47;
          }
          if ( v41 < 0 )
            RaiseException(v41, 1u, 0, 0);
          v63 = 0;
        }
        if ( v62 )
        {
          *(_QWORD *)&v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          LODWORD(v47) = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v62) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v43 + 4))(*v43, v42);
            v44 = 0;
          }
          else
          {
            DWORD2(v46) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
            v44 = (int)v47;
          }
          if ( v44 < 0 )
            RaiseException(v44, 1u, 0, 0);
          v62 = 0;
        }
        goto LABEL_75;
      }
      v54 = *((_QWORD *)a2 + 1);
      SystemIsolatedFilesystem = Windows::Isolation::Implementation::Rtl::GetUserStateStoreRootFilesystemObject(
                                   v63,
                                   v50,
                                   &v54);
      if ( SystemIsolatedFilesystem >= 0 )
      {
        *((_QWORD *)&v46 + 1) = v51;
        v47 = g_LUNICODE_STRING_Applications;
        v52 = 0;
        *(_QWORD *)&v46 = 48;
        v48 = 64;
        v49 = 0;
        SystemIsolatedFilesystem = RtlIsolatedRegistryCreateKey(v63, (unsigned int)&v52, 131103, (unsigned int)&v46);
        if ( SystemIsolatedFilesystem >= 0 )
        {
          *((_QWORD *)&v46 + 1) = v51;
          v47 = g_LUNICODE_STRING_Families;
          v53 = 0;
          *(_QWORD *)&v46 = 48;
          v48 = 64;
          v49 = 0;
          SystemIsolatedFilesystem = RtlIsolatedRegistryCreateKey(v63, (unsigned int)&v53, 131103, (unsigned int)&v46);
          if ( SystemIsolatedFilesystem >= 0 )
          {
            v46 = 0u;
            v47 = 0;
            SystemIsolatedFilesystem = CNtAbsoluteDirPath::TrySwap(
                                         (CNtAbsoluteDirPath *)&v46,
                                         (struct Windows::Rtl::CLUNICODE_STRING *)v58);
            if ( SystemIsolatedFilesystem >= 0 )
            {
              SystemIsolatedFilesystem = 0;
              v24 = v61;
              v25 = v47;
              v26 = *((_OWORD *)this + 3);
              v27 = (void *)*((_QWORD *)this + 8);
              *((_OWORD *)this + 3) = v46;
              *((_QWORD *)this + 8) = v25;
              v28 = *((_QWORD *)this + 2);
              *((_QWORD *)this + 2) = v24;
              v29 = *((_QWORD *)this + 3);
              *((_QWORD *)this + 3) = v51;
              v51 = v29;
              v30 = *((_QWORD *)this + 4);
              *((_QWORD *)this + 4) = v52;
              v52 = v30;
              v31 = *((_QWORD *)this + 5);
              *((_QWORD *)this + 5) = v53;
              v53 = v31;
              v32 = *((_QWORD *)this + 1);
              *((_QWORD *)this + 1) = v62;
              v33 = *((_QWORD *)this + 11);
              v62 = v32;
              *((_QWORD *)this + 11) = *((_QWORD *)&v55 + 1);
              *((_QWORD *)&v55 + 1) = v33;
              v34 = *((_QWORD *)this + 12);
              *((_QWORD *)this + 12) = v56;
              v56 = v34;
              v35 = *((_QWORD *)this + 13);
              *((_QWORD *)this + 13) = v10;
              v57 = v35;
              *((_QWORD *)this + 9) = v8;
              v46 = v26;
              if ( v27 )
                IsolationFreeStringRoutine(v27);
              Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v53);
              Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v52);
              if ( lpMem )
                IsolationFreeStringRoutine(lpMem);
              if ( !v28 )
                goto LABEL_54;
              v23 = v28;
LABEL_53:
              RtlCloseIsolatedFilesystemObjectHandle(v23);
              goto LABEL_54;
            }
            if ( v47 )
              IsolationFreeStringRoutine(v47);
          }
          Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v53);
        }
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v52);
      }
      if ( lpMem )
        IsolationFreeStringRoutine(lpMem);
      v23 = v61;
      if ( !v61 )
        goto LABEL_54;
      goto LABEL_53;
    }
  }
  if ( v62 )
  {
    *(_QWORD *)&v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    LODWORD(v47) = -1073741595;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v62) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v6 + 4))(*v6, v5);
      v7 = 0;
    }
    else
    {
      DWORD2(v46) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
      v7 = (int)v47;
    }
    if ( v7 >= 0 )
      goto LABEL_10;
LABEL_9:
    RaiseException(v7, 1u, 0, 0);
LABEL_10:
    v62 = 0;
  }
LABEL_75:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v55);
  return (unsigned int)SystemIsolatedFilesystem;
}

```

## disassembly

```asm
0x1800b3b30  mov     [rsp-8+arg_0], rcx
0x1800b3b35  push    rbp
0x1800b3b36  push    rbx
0x1800b3b37  push    rsi
0x1800b3b38  push    rdi
0x1800b3b39  push    r12
0x1800b3b3b  push    r13
0x1800b3b3d  push    r14
0x1800b3b3f  push    r15
0x1800b3b41  lea     rbp, [rsp-1Fh]
0x1800b3b46  sub     rsp, 0E8h
0x1800b3b4d  mov     r12, rdx
0x1800b3b50  mov     [rbp+57h+var_68], 0
0x1800b3b58  xorps   xmm0, xmm0
0x1800b3b5b  mov     [rbp+57h+var_60], 0
0x1800b3b63  lea     rdx, [rbp+57h+arg_10]
0x1800b3b67  mov     [rbp+57h+arg_10], 0
0x1800b3b6f  movdqu  [rbp+57h+var_78], xmm0
0x1800b3b74  mov     rcx, [r12]
0x1800b3b78  call    RtlDuplicateSystemHandle
0x1800b3b7d  xor     r15d, r15d
0x1800b3b80  test    eax, eax
0x1800b3b82  cmovs   r15d, eax
0x1800b3b86  test    r15d, r15d
0x1800b3b89  jns     loc_1800B3C15
0x1800b3b8f  mov     r10, [rbp+57h+arg_10]
0x1800b3b93  test    r10, r10
0x1800b3b96  jz      loc_1800B413A
0x1800b3b9c  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_SYSTEM@Rtl@Isolation@Windows@@VCSystem@2Implementation@34@VCSystemCD@2634@VCSystemImplTraits@2634@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
0x1800b3ba3  lea     rbx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800b3baa  mov     qword ptr [rbp+57h+var_D0], rbx
0x1800b3bae  mov     r14d, 0C00000E5h
0x1800b3bb4  mov     dword ptr [rbp+57h+var_C0], r14d
0x1800b3bb8  test    r11, r11
0x1800b3bbb  jz      short loc_1800B3BFF
0x1800b3bbd  mov     rdx, r11
0x1800b3bc0  mov     rcx, r10
0x1800b3bc3  call    RtlIsTypeSafeHandleValid
0x1800b3bc8  test    al, al
0x1800b3bca  jz      short loc_1800B3BFF
0x1800b3bcc  mov     ecx, [r11]
0x1800b3bcf  mov     rdx, r10
0x1800b3bd2  mov     rax, [r11+20h]
0x1800b3bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3bdb  xor     ecx, ecx; dwExceptionCode
0x1800b3bdd  test    ecx, ecx
0x1800b3bdf  jns     short loc_1800B3BF2
0x1800b3be1  mov     edx, 1; dwExceptionFlags
0x1800b3be6  xor     r9d, r9d; lpArguments
0x1800b3be9  xor     r8d, r8d; nNumberOfArguments
0x1800b3bec  call    cs:__imp_RaiseException
0x1800b3bf2  mov     [rbp+57h+arg_10], 0
0x1800b3bfa  jmp     loc_1800B413A
0x1800b3bff  mov     edi, 124h
0x1800b3c04  mov     dword ptr [rbp+57h+var_D0+8], edi
0x1800b3c07  lea     rcx, [rbp+57h+var_D0]
0x1800b3c0b  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800b3c10  mov     ecx, dword ptr [rbp+57h+var_C0]
0x1800b3c13  jmp     short loc_1800B3BDD
0x1800b3c15  mov     r13, [r12+10h]
0x1800b3c1a  lea     rdx, [rbp+57h+arg_8]
0x1800b3c1e  mov     r8, r13
0x1800b3c21  lea     rcx, [rbp+57h+var_78]
0x1800b3c25  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@_KV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(unsigned __int64)
0x1800b3c2a  mov     r15d, [rax]
0x1800b3c2d  test    r15d, r15d
0x1800b3c30  js      loc_1800B3B8F
0x1800b3c36  mov     rdi, [rbp+57h+var_60]
0x1800b3c3a  xor     ebx, ebx
0x1800b3c3c  mov     r14d, 0C00000E5h
0x1800b3c42  lea     esi, [rbx+1]
0x1800b3c45  test    r13, r13
0x1800b3c48  jz      loc_1800B3CE0
0x1800b3c4e  mov     r8, [rbp+57h+var_68]
0x1800b3c52  cmp     rdi, r8
0x1800b3c55  jnb     short loc_1800B3C81
0x1800b3c57  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x1800b3c5b  lea     rdx, [rcx+rdi*8]
0x1800b3c5f  mov     rcx, r8
0x1800b3c62  sub     rcx, rdi
0x1800b3c65  jz      short loc_1800B3C7A
0x1800b3c67  mov     rax, rdx
0x1800b3c6a  add     rdx, 8
0x1800b3c6e  mov     qword ptr [rax], 0
0x1800b3c75  sub     rcx, rsi
0x1800b3c78  jnz     short loc_1800B3C67
0x1800b3c7a  mov     rdi, r8
0x1800b3c7d  mov     [rbp+57h+var_60], r8
0x1800b3c81  mov     rax, qword ptr [rbp+57h+var_78+8]
0x1800b3c85  mov     dword ptr [rbp+57h+var_C0], r14d
0x1800b3c89  lea     rdx, [rax+rbx*8]
0x1800b3c8d  cmp     qword ptr [rdx], 0
0x1800b3c91  lea     rax, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800b3c98  mov     qword ptr [rbp+57h+var_D0], rax
0x1800b3c9c  jz      short loc_1800B3CB8
0x1800b3c9e  mov     dword ptr [rbp+57h+var_D0+8], 8Eh
0x1800b3ca5  lea     rdx, [rbp+57h+var_D0]
0x1800b3ca9  lea     rcx, [rbp+57h+var_D0]
0x1800b3cad  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800b3cb2  mov     r15d, dword ptr [rbp+57h+var_C0]
0x1800b3cb6  jmp     short loc_1800B3CCF
0x1800b3cb8  mov     rcx, [r12+18h]
0x1800b3cbd  mov     rcx, [rcx+rbx*8]
0x1800b3cc1  call    RtlDuplicateComponentStoreHandle
0x1800b3cc6  xor     r15d, r15d
0x1800b3cc9  test    eax, eax
0x1800b3ccb  cmovs   r15d, eax
0x1800b3ccf  test    r15d, r15d
0x1800b3cd2  js      short loc_1800B3D3D
0x1800b3cd4  add     rbx, rsi
0x1800b3cd7  cmp     rbx, r13
0x1800b3cda  jnz     loc_1800B3C4E
0x1800b3ce0  mov     rdx, [rbp+57h+arg_10]
0x1800b3ce4  lea     r8, [rbp+57h+var_A0]
0x1800b3ce8  mov     [rbp+57h+arg_18], 0
0x1800b3cf0  mov     [rbp+57h+var_A0], 0
0x1800b3cf8  mov     [rbp+57h+var_98], 0
0x1800b3d00  mov     [rbp+57h+arg_8], 0
0x1800b3d08  mov     [rbp+57h+var_50], 0
0x1800b3d10  mov     [rbp+57h+var_58], 0
0x1800b3d18  mov     [rbp+57h+lpMem], 0
0x1800b3d20  call    RtlGetSystemIsolatedFilesystem
0x1800b3d25  mov     r15d, eax
0x1800b3d28  test    eax, eax
0x1800b3d2a  jns     short loc_1800B3DAA
0x1800b3d2c  lea     rcx, [rbp+57h+var_98]
0x1800b3d30  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800b3d35  xor     r12d, r12d
0x1800b3d38  jmp     loc_1800B4016
0x1800b3d3d  mov     r10, [rbp+57h+arg_10]
0x1800b3d41  test    r10, r10
0x1800b3d44  jz      loc_1800B413A
0x1800b3d4a  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_SYSTEM@Rtl@Isolation@Windows@@VCSystem@2Implementation@34@VCSystemCD@2634@VCSystemImplTraits@2634@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
0x1800b3d51  lea     rbx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800b3d58  mov     dword ptr [rbp+57h+var_C0], r14d
0x1800b3d5c  mov     qword ptr [rbp+57h+var_D0], rbx
0x1800b3d60  test    r11, r11
0x1800b3d63  jz      short loc_1800B3D94
0x1800b3d65  mov     rdx, r11
0x1800b3d68  mov     rcx, r10
0x1800b3d6b  call    RtlIsTypeSafeHandleValid
0x1800b3d70  test    al, al
0x1800b3d72  jz      short loc_1800B3D94
0x1800b3d74  mov     ecx, [r11]
0x1800b3d77  mov     rdx, r10
0x1800b3d7a  mov     rax, [r11+20h]
0x1800b3d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d83  xor     ecx, ecx
0x1800b3d85  test    ecx, ecx
0x1800b3d87  jns     loc_1800B3BF2
0x1800b3d8d  mov     edx, esi
0x1800b3d8f  jmp     loc_1800B3BE6
0x1800b3d94  mov     edi, 124h
0x1800b3d99  mov     dword ptr [rbp+57h+var_D0+8], edi
0x1800b3d9c  lea     rcx, [rbp+57h+var_D0]
0x1800b3da0  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800b3da5  mov     ecx, dword ptr [rbp+57h+var_C0]
0x1800b3da8  jmp     short loc_1800B3D85
0x1800b3daa  mov     rdx, [rbp+57h+arg_10]
0x1800b3dae  lea     r8, [rbp+57h+arg_18]
0x1800b3db2  call    RtlGetSystemIsolatedRegistry
0x1800b3db7  mov     r15d, eax
0x1800b3dba  test    eax, eax
0x1800b3dbc  js      loc_1800B3D2C
0x1800b3dc2  mov     rax, [r12+8]
0x1800b3dc7  lea     r9, [rbp+57h+var_98]
0x1800b3dcb  mov     rcx, [rbp+57h+arg_18]
0x1800b3dcf  lea     rdx, [rbp+57h+var_80]
0x1800b3dd3  mov     [rbp+57h+var_80], rax
0x1800b3dd7  call    ?GetUserStateStoreRootKey@Rtl@Implementation@Isolation@Windows@@YAJU_ISOLATED_REGISTRY@134@AEBVCToken@@KAEAU_ISOLATED_KEY@134@@Z; Windows::Isolation::Implementation::Rtl::GetUserStateStoreRootKey(Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CToken const &,ulong,Windows::Isolation::Rtl::_ISOLATED_KEY &)
0x1800b3ddc  mov     r15d, eax
0x1800b3ddf  test    eax, eax
0x1800b3de1  js      loc_1800B3D2C
0x1800b3de7  mov     rax, [r12+8]
0x1800b3dec  lea     r8, [rbp+57h+var_80]
0x1800b3df0  mov     rdx, [rbp+57h+var_A0]
0x1800b3df4  mov     rcx, [rbp+57h+arg_18]
0x1800b3df8  mov     [rbp+57h+var_80], rax
0x1800b3dfc  lea     rax, [rbp+57h+var_58]
0x1800b3e00  mov     [rsp+120h+var_F8], rax
0x1800b3e05  lea     rax, [rbp+57h+arg_8]
0x1800b3e09  mov     [rsp+120h+var_100], rax
0x1800b3e0e  call    ?GetUserStateStoreRootFilesystemObject@Rtl@Implementation@Isolation@Windows@@YAJU_ISOLATED_REGISTRY@134@U_ISOLATED_FILESYSTEM@134@AEBVCToken@@KAEAU_ISOLATED_FILESYSTEM_OBJECT@134@AEAU_LUNICODE_STRING@@@Z; Windows::Isolation::Implementation::Rtl::GetUserStateStoreRootFilesystemObject(Windows::Isolation::Rtl::_ISOLATED_REGISTRY,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,CToken const &,ulong,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &,_LUNICODE_STRING &)
0x1800b3e13  xor     r12d, r12d
0x1800b3e16  mov     r15d, eax
0x1800b3e19  test    eax, eax
0x1800b3e1b  jns     short loc_1800B3E3D
0x1800b3e1d  mov     rcx, [rbp+57h+lpMem]; lpMem
0x1800b3e21  test    rcx, rcx
0x1800b3e24  jz      short loc_1800B3E2B
0x1800b3e26  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b3e2b  mov     rcx, [rbp+57h+arg_8]
0x1800b3e2f  test    rcx, rcx
0x1800b3e32  jz      loc_1800B400D
0x1800b3e38  jmp     loc_1800B4008
0x1800b3e3d  mov     rax, [rbp+57h+var_98]
0x1800b3e41  lea     r9, [rbp+57h+var_D0]
0x1800b3e45  mov     rcx, [rbp+57h+arg_18]
0x1800b3e49  lea     rdx, [rbp+57h+var_90]
0x1800b3e4d  mov     qword ptr [rbp+57h+var_D0+8], rax
0x1800b3e51  xorps   xmm0, xmm0
0x1800b3e54  lea     rax, g_LUNICODE_STRING_Applications
0x1800b3e5b  mov     [rsp+120h+var_E0], r12
0x1800b3e60  mov     ebx, 30h ; '0'
0x1800b3e65  mov     [rbp+57h+var_C0], rax
0x1800b3e69  mov     r8d, 2001Fh
0x1800b3e6f  mov     [rbp+57h+var_90], r12
0x1800b3e73  mov     qword ptr [rbp+57h+var_D0], rbx
0x1800b3e77  mov     [rbp+57h+var_B8], 40h ; '@'
0x1800b3e7e  movdqu  [rbp+57h+var_B0], xmm0
0x1800b3e83  mov     [rsp+120h+var_E8], r12
0x1800b3e88  call    RtlIsolatedRegistryCreateKey
0x1800b3e8d  mov     r15d, eax
0x1800b3e90  test    eax, eax
0x1800b3e92  jns     short loc_1800B3EA2
0x1800b3e94  lea     rcx, [rbp+57h+var_90]
0x1800b3e98  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800b3e9d  jmp     loc_1800B3E1D
0x1800b3ea2  mov     rax, [rbp+57h+var_98]
0x1800b3ea6  lea     r9, [rbp+57h+var_D0]
0x1800b3eaa  mov     rcx, [rbp+57h+arg_18]
0x1800b3eae  lea     rdx, [rbp+57h+var_88]
0x1800b3eb2  mov     qword ptr [rbp+57h+var_D0+8], rax
0x1800b3eb6  xorps   xmm0, xmm0
0x1800b3eb9  lea     rax, g_LUNICODE_STRING_Families
0x1800b3ec0  mov     [rsp+120h+var_E0], r12
0x1800b3ec5  mov     r8d, 2001Fh
0x1800b3ecb  mov     [rbp+57h+var_C0], rax
0x1800b3ecf  mov     [rbp+57h+var_88], r12
0x1800b3ed3  mov     qword ptr [rbp+57h+var_D0], rbx
0x1800b3ed7  mov     [rbp+57h+var_B8], 40h ; '@'
0x1800b3ede  movdqu  [rbp+57h+var_B0], xmm0
0x1800b3ee3  mov     [rsp+120h+var_E8], r12
0x1800b3ee8  call    RtlIsolatedRegistryCreateKey
0x1800b3eed  mov     r15d, eax
0x1800b3ef0  test    eax, eax
0x1800b3ef2  jns     short loc_1800B3EFF
0x1800b3ef4  lea     rcx, [rbp+57h+var_88]
0x1800b3ef8  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800b3efd  jmp     short loc_1800B3E94
0x1800b3eff  lea     rdx, [rbp+57h+var_58]; struct Windows::Rtl::CLUNICODE_STRING *
0x1800b3f03  mov     qword ptr [rbp+57h+var_D0+8], r12
0x1800b3f07  lea     rcx, [rbp+57h+var_D0]; this
0x1800b3f0b  mov     qword ptr [rbp+57h+var_D0], r12
0x1800b3f0f  mov     [rbp+57h+var_C0], r12
0x1800b3f13  call    ?TrySwap@CNtAbsoluteDirPath@@QEAAJAEAVCLUNICODE_STRING@Rtl@Windows@@@Z; CNtAbsoluteDirPath::TrySwap(Windows::Rtl::CLUNICODE_STRING &)
0x1800b3f18  mov     r15d, eax
0x1800b3f1b  test    eax, eax
0x1800b3f1d  jns     short loc_1800B3F2F
0x1800b3f1f  mov     rcx, [rbp+57h+var_C0]; lpMem
0x1800b3f23  test    rcx, rcx
0x1800b3f26  jz      short loc_1800B3EF4
0x1800b3f28  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b3f2d  jmp     short loc_1800B3EF4
0x1800b3f2f  mov     rdx, [rbp+57h+arg_0]
0x1800b3f33  mov     r15d, r12d
0x1800b3f36  movups  xmm1, [rbp+57h+var_D0]
0x1800b3f3a  mov     rax, [rbp+57h+arg_8]
0x1800b3f3e  movsd   xmm2, [rbp+57h+var_C0]
0x1800b3f43  movups  xmm0, xmmword ptr [rdx+30h]
0x1800b3f47  movsd   xmm3, qword ptr [rdx+40h]
0x1800b3f4c  movups  xmmword ptr [rdx+30h], xmm1
0x1800b3f50  movsd   qword ptr [rdx+40h], xmm2
0x1800b3f55  mov     rbx, [rdx+10h]
0x1800b3f59  mov     [rdx+10h], rax
0x1800b3f5d  mov     rcx, [rdx+18h]
0x1800b3f61  mov     rax, [rbp+57h+var_98]
0x1800b3f65  mov     [rdx+18h], rax
0x1800b3f69  mov     rax, [rbp+57h+var_90]
0x1800b3f6d  mov     [rbp+57h+var_98], rcx
0x1800b3f71  mov     rcx, [rdx+20h]
0x1800b3f75  mov     [rdx+20h], rax
0x1800b3f79  mov     rax, [rbp+57h+var_88]
0x1800b3f7d  mov     [rbp+57h+var_90], rcx
0x1800b3f81  mov     rcx, [rdx+28h]
0x1800b3f85  mov     [rdx+28h], rax
0x1800b3f89  mov     rax, [rbp+57h+arg_10]
0x1800b3f8d  mov     [rbp+57h+var_88], rcx
0x1800b3f91  mov     rcx, [rdx+8]
0x1800b3f95  mov     [rdx+8], rax
0x1800b3f99  mov     rax, [rdx+58h]
0x1800b3f9d  mov     [rbp+57h+arg_10], rcx
0x1800b3fa1  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x1800b3fa5  mov     [rdx+58h], rcx
0x1800b3fa9  mov     rcx, [rbp+57h+var_68]
0x1800b3fad  mov     qword ptr [rbp+57h+var_78+8], rax
0x1800b3fb1  mov     rax, [rdx+60h]
0x1800b3fb5  mov     [rdx+60h], rcx
0x1800b3fb9  movq    rcx, xmm3; lpMem
0x1800b3fbe  mov     [rbp+57h+var_68], rax
0x1800b3fc2  mov     rax, [rdx+68h]
0x1800b3fc6  mov     [rdx+68h], rdi
0x1800b3fca  mov     [rbp+57h+var_60], rax
0x1800b3fce  mov     [rdx+48h], r13
0x1800b3fd2  movups  [rbp+57h+var_D0], xmm0
0x1800b3fd6  test    rcx, rcx
0x1800b3fd9  jz      short loc_1800B3FE0
0x1800b3fdb  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800b3fe0  lea     rcx, [rbp+57h+var_88]
0x1800b3fe4  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
  ... truncated ...
```
