# CCSDirectMetadataManager::CleanupPropertyStore(CComponentMarkManager &)

- ea: `0x1800ccb28`
- end: `0x1800cd01f`
- name: `?CleanupPropertyStore@CCSDirectMetadataManager@@QEAAJAEAVCComponentMarkManager@@@Z`
- size: `1271`
- prototype: `__int64 __fastcall(CCSDirectMetadataManager *__hidden this, struct CComponentMarkManager *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800d4808`

## callees

- `0x180012b1c`
- `0x18002a844`
- `0x1800374a8`
- `0x18004f2dc`
- `0x1800cbcb4`
- `0x1800cc2ac`
- `0x1800cc82c`
- `0x1800ccb28`
- `0x1800cd028`
- `0x1800cdc08`
- `0x180114224`
- `0x1801142f0`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ccd64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ccf1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ccf9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ccd64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ccf1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ccf9f`

## string_xrefs

- `0x1800ccd14`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ccd9e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall CCSDirectMetadataManager::CleanupPropertyStore(
        CCSDirectMetadataManager *this,
        struct CComponentMarkManager *a2)
{
  __int64 v2; // rdx
  unsigned __int64 v3; // r15
  unsigned __int64 v4; // r14
  int HierarchyEnumeratorData; // r12d
  __int64 v6; // rsi
  unsigned __int64 v7; // rcx
  __int64 v8; // r13
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // r8
  _QWORD *v12; // rdx
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r10
  unsigned int *v17; // r11
  signed int v18; // ecx
  __int64 v20; // rax
  bool i; // zf
  _QWORD *v22; // rdx
  _QWORD *v23; // rax
  _QWORD *v24; // rdx
  unsigned __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r10
  unsigned int *v30; // r11
  __int64 v31; // r10
  unsigned int *v32; // r11
  signed int v33; // ecx
  const char *v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+38h] [rbp-C8h]
  unsigned int v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v42; // [rsp+78h] [rbp-88h]
  unsigned __int64 v43; // [rsp+80h] [rbp-80h]
  __int64 v44; // [rsp+88h] [rbp-78h]
  CCSDirectMetadataManager *v45; // [rsp+90h] [rbp-70h]
  _QWORD v46[16]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = *(_QWORD *)this;
  v3 = 0;
  v45 = this;
  v39 = 0;
  v4 = 0;
  v42 = 0;
  v43 = 0;
  v41 = 0;
  HierarchyEnumeratorData = RtlEnumerateHierarchy(1, v2, 0, &v39);
  if ( HierarchyEnumeratorData < 0 )
    goto LABEL_17;
  v6 = 0;
  v44 = 0;
  v37 = 0;
  HierarchyEnumeratorData = RtlFetchHierarchyEnumeratorData(v39, 5, v46, &v37);
  if ( HierarchyEnumeratorData < 0 )
    goto LABEL_17;
  v8 = *((_QWORD *)&v41 + 1);
  while ( 2 )
  {
    v9 = v37;
    v10 = 0;
    if ( v37 )
    {
      do
      {
        LODWORD(v40) = 0;
        v37 = 0;
        HierarchyEnumeratorData = Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(
                                    4,
                                    *(_QWORD *)v45,
                                    3221225472LL,
                                    &v46[3 * v10],
                                    &v37,
                                    &v40);
        if ( HierarchyEnumeratorData < 0 )
        {
LABEL_24:
          Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v37);
          goto LABEL_17;
        }
        if ( (v40 & 1) != 0 )
        {
          if ( v6 == v3 )
          {
            HierarchyEnumeratorData = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeBy(
                                                   &v41,
                                                   &v38,
                                                   20);
            if ( HierarchyEnumeratorData < 0 )
              goto LABEL_24;
            v4 = v43;
            v3 = v42;
            v8 = *((_QWORD *)&v41 + 1);
          }
          v11 = v6;
          if ( v4 < v3 )
          {
            v12 = (_QWORD *)(v8 + 8 * v4);
            v13 = v3 - v4;
            if ( v3 != v4 )
            {
              do
              {
                v14 = v12++;
                *v14 = 0;
                --v13;
              }
              while ( v13 );
            }
            v4 = v3;
            v43 = v3;
          }
          ++v6;
          v15 = *(_QWORD *)(v8 + 8 * v11);
          *(_QWORD *)(v8 + 8 * v11) = v37;
          v37 = v15;
          v44 = v6;
        }
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v37);
        ++v10;
      }
      while ( v10 != v9 );
      v37 = 0;
      HierarchyEnumeratorData = RtlFetchHierarchyEnumeratorData(v39, 5, v46, &v37);
      if ( HierarchyEnumeratorData >= 0 )
        continue;
LABEL_17:
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v41);
      if ( !v39 )
        return (unsigned int)HierarchyEnumeratorData;
      v34 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      v36 = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v39) )
      {
        goto LABEL_20;
      }
      goto LABEL_63;
    }
    break;
  }
  v20 = 0;
  for ( i = v44 == 0; ; i = v37 + 1 == v44 )
  {
    v37 = v20;
    if ( i )
    {
      HierarchyEnumeratorData = 0;
      goto LABEL_58;
    }
    v40 = 0;
    v38 = 0;
    if ( v4 < v3 )
    {
      v22 = (_QWORD *)(v8 + 8 * v4);
      v7 = v3 - v4;
      if ( v3 != v4 )
      {
        do
        {
          v23 = v22++;
          *v23 = 0;
          --v7;
        }
        while ( v7 );
        v20 = v37;
      }
      v4 = v3;
      v43 = v3;
    }
    HierarchyEnumeratorData = CCSDirectMetadataManager::CleanupSingleReferenceProperties(v7, *(_QWORD *)(v8 + 8 * v20));
    if ( HierarchyEnumeratorData < 0 )
      break;
    if ( v4 < v3 )
    {
      v24 = (_QWORD *)(v8 + 8 * v4);
      v25 = v3 - v4;
      if ( v3 != v4 )
      {
        do
        {
          v26 = v24++;
          *v26 = 0;
          --v25;
        }
        while ( v25 );
      }
      v4 = v3;
      v43 = v3;
    }
    HierarchyEnumeratorData = RtlEnumerateHierarchy(1, *(_QWORD *)(v8 + 8 * v37), 0, &v38);
    if ( HierarchyEnumeratorData < 0 )
      break;
    HierarchyEnumeratorData = RtlFetchHierarchyEnumeratorData(v38, 1, &v34, &v40);
    if ( HierarchyEnumeratorData < 0 )
      break;
    if ( !v40 )
    {
      v27 = (__int64 *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](
                         &v41,
                         v37);
      HierarchyEnumeratorData = Windows::Isolation::HierLib::Rtl::DeleteHierarchyRecursivelyByHandle(v28, *v27, 0);
      if ( HierarchyEnumeratorData < 0 )
        break;
      v4 = v43;
      v3 = v42;
      v8 = *((_QWORD *)&v41 + 1);
    }
    if ( v38 )
    {
      v36 = -1073741595;
      v34 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v38) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v30 + 4))(*v30, v29);
        v7 = 0;
      }
      else
      {
        v35 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v34);
        v7 = v36;
      }
      if ( (v7 & 0x80000000) != 0LL )
        RaiseException(v7, 1u, 0, 0);
    }
    v20 = v37 + 1;
  }
  if ( v38 )
  {
    v34 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    v36 = -1073741595;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v38) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v32 + 4))(*v32, v31);
      v33 = 0;
    }
    else
    {
      v35 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v34);
      v33 = v36;
    }
    if ( v33 < 0 )
      RaiseException(v33, 1u, 0, 0);
    v38 = 0;
  }
LABEL_58:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v41);
  if ( v39 )
  {
    v36 = -1073741595;
    v34 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v39) )
    {
LABEL_20:
      (*((void (__fastcall **)(_QWORD, __int64))v17 + 4))(*v17, v16);
      v18 = 0;
      goto LABEL_21;
    }
LABEL_63:
    v35 = 292;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v34);
    v18 = v36;
LABEL_21:
    if ( v18 < 0 )
      RaiseException(v18, 1u, 0, 0);
  }
  return (unsigned int)HierarchyEnumeratorData;
}

```

## disassembly

```asm
0x1800ccb28  push    rbp
0x1800ccb2a  push    rbx
0x1800ccb2b  push    rsi
0x1800ccb2c  push    rdi
0x1800ccb2d  push    r12
0x1800ccb2f  push    r13
0x1800ccb31  push    r14
0x1800ccb33  push    r15
0x1800ccb35  lea     rbp, [rsp-38h]
0x1800ccb3a  sub     rsp, 138h
0x1800ccb41  mov     rax, cs:__security_cookie
0x1800ccb48  xor     rax, rsp
0x1800ccb4b  mov     [rbp+70h+var_50], rax
0x1800ccb4f  mov     rdx, [rcx]
0x1800ccb52  lea     r9, [rsp+170h+var_118]
0x1800ccb57  xor     r15d, r15d
0x1800ccb5a  mov     [rbp+70h+var_E0], rcx
0x1800ccb5e  xorps   xmm0, xmm0
0x1800ccb61  mov     [rsp+170h+var_118], 0
0x1800ccb6a  xor     r14d, r14d
0x1800ccb6d  mov     [rsp+170h+var_F8], r15
0x1800ccb72  xor     r8d, r8d
0x1800ccb75  mov     [rbp+70h+var_F0], r14
0x1800ccb79  lea     ecx, [r15+1]
0x1800ccb7d  movdqu  [rsp+170h+var_108], xmm0
0x1800ccb83  call    RtlEnumerateHierarchy
0x1800ccb88  mov     r12d, eax
0x1800ccb8b  test    eax, eax
0x1800ccb8d  js      loc_1800CCCF9
0x1800ccb93  mov     rcx, [rsp+170h+var_118]
0x1800ccb98  lea     r9, [rsp+170h+var_128]
0x1800ccb9d  xor     esi, esi
0x1800ccb9f  lea     r8, [rbp+70h+var_D0]
0x1800ccba3  mov     [rbp+70h+var_E8], rsi
0x1800ccba7  mov     [rsp+170h+var_128], rsi
0x1800ccbac  lea     edx, [rsi+5]
0x1800ccbaf  call    RtlFetchHierarchyEnumeratorData
0x1800ccbb4  mov     r12d, eax
0x1800ccbb7  test    eax, eax
0x1800ccbb9  js      loc_1800CCCF9
0x1800ccbbf  mov     r13, qword ptr [rsp+170h+var_108+8]
0x1800ccbc4  mov     rdi, [rsp+170h+var_128]
0x1800ccbc9  xor     ebx, ebx
0x1800ccbcb  test    rdi, rdi
0x1800ccbce  jz      loc_1800CCD9C
0x1800ccbd4  lea     rax, [rbx+rbx*2]
0x1800ccbd8  mov     dword ptr [rsp+170h+var_110], 0
0x1800ccbe0  lea     r9, [rbp+70h+var_D0]
0x1800ccbe4  mov     [rsp+170h+var_128], 0
0x1800ccbed  lea     r9, [r9+rax*8]
0x1800ccbf1  mov     r8d, 0C0000000h
0x1800ccbf7  lea     rax, [rsp+170h+var_110]
0x1800ccbfc  mov     ecx, 4
0x1800ccc01  mov     [rsp+170h+var_148], rax
0x1800ccc06  lea     rax, [rsp+170h+var_128]
0x1800ccc0b  mov     [rsp+170h+var_150], rax
0x1800ccc10  mov     rax, [rbp+70h+var_E0]
0x1800ccc14  mov     rdx, [rax]
0x1800ccc17  call    ?RtlOpenHierarchy@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@KPEBU_LUNICODE_STRING@@PEAU5134@PEAK@Z; Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(ulong,Windows::Isolation::Rtl::_HIERARCHY,ulong,_LUNICODE_STRING const *,Windows::Isolation::Rtl::_HIERARCHY *,ulong *)
0x1800ccc1c  mov     r12d, eax
0x1800ccc1f  test    eax, eax
0x1800ccc21  js      loc_1800CCD8D
0x1800ccc27  test    byte ptr [rsp+170h+var_110], 1
0x1800ccc2c  jz      loc_1800CCCB7
0x1800ccc32  cmp     rsi, r15
0x1800ccc35  jnz     short loc_1800CCC66
0x1800ccc37  mov     r8d, 14h
0x1800ccc3d  lea     rdx, [rsp+170h+var_120]
0x1800ccc42  lea     rcx, [rsp+170h+var_108]
0x1800ccc47  call    ?EnlargeBy@?$CSmartArrayHolder@_KV?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeBy(unsigned __int64)
0x1800ccc4c  mov     r12d, [rax]
0x1800ccc4f  test    r12d, r12d
0x1800ccc52  js      loc_1800CCD8D
0x1800ccc58  mov     r14, [rbp+70h+var_F0]
0x1800ccc5c  mov     r15, [rsp+170h+var_F8]
0x1800ccc61  mov     r13, qword ptr [rsp+170h+var_108+8]
0x1800ccc66  mov     r8, rsi
0x1800ccc69  cmp     r14, r15
0x1800ccc6c  jnb     short loc_1800CCC9C
0x1800ccc6e  lea     rdx, ds:0[r14*8]
0x1800ccc76  mov     rcx, r15
0x1800ccc79  add     rdx, r13
0x1800ccc7c  sub     rcx, r14
0x1800ccc7f  jz      short loc_1800CCC95
0x1800ccc81  mov     rax, rdx
0x1800ccc84  add     rdx, 8
0x1800ccc88  mov     qword ptr [rax], 0
0x1800ccc8f  sub     rcx, 1
0x1800ccc93  jnz     short loc_1800CCC81
0x1800ccc95  mov     r14, r15
0x1800ccc98  mov     [rbp+70h+var_F0], r15
0x1800ccc9c  mov     rax, [rsp+170h+var_128]
0x1800ccca1  inc     rsi
0x1800ccca4  mov     rcx, [r13+r8*8+0]
0x1800ccca9  mov     [r13+r8*8+0], rax
0x1800cccae  mov     [rsp+170h+var_128], rcx
0x1800cccb3  mov     [rbp+70h+var_E8], rsi
0x1800cccb7  lea     rcx, [rsp+170h+var_128]
0x1800cccbc  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cccc1  inc     rbx
0x1800cccc4  cmp     rbx, rdi
0x1800cccc7  jnz     loc_1800CCBD4
0x1800ccccd  mov     rcx, [rsp+170h+var_118]
0x1800cccd2  lea     r9, [rsp+170h+var_128]
0x1800cccd7  lea     r8, [rbp+70h+var_D0]
0x1800cccdb  mov     [rsp+170h+var_128], 0
0x1800ccce4  mov     edx, 5
0x1800ccce9  call    RtlFetchHierarchyEnumeratorData
0x1800cccee  mov     r12d, eax
0x1800cccf1  test    eax, eax
0x1800cccf3  jns     loc_1800CCBC4
0x1800cccf9  lea     rcx, [rsp+170h+var_108]
0x1800cccfe  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ccd03  mov     r10, [rsp+170h+var_118]
0x1800ccd08  test    r10, r10
0x1800ccd0b  jz      short loc_1800CCD6A
0x1800ccd0d  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800ccd14  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ccd1b  mov     [rsp+170h+var_140], rsi
0x1800ccd20  mov     edi, 0C00000E5h
0x1800ccd25  mov     [rsp+170h+var_130], edi
0x1800ccd29  test    r11, r11
0x1800ccd2c  jz      loc_1800CD003
0x1800ccd32  mov     rdx, r11
0x1800ccd35  mov     rcx, r10
0x1800ccd38  call    RtlIsTypeSafeHandleValid
0x1800ccd3d  test    al, al
0x1800ccd3f  jz      loc_1800CD003
0x1800ccd45  mov     ecx, [r11]
0x1800ccd48  mov     rdx, r10
0x1800ccd4b  mov     rax, [r11+20h]
0x1800ccd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccd54  xor     ecx, ecx; dwExceptionCode
0x1800ccd56  test    ecx, ecx
0x1800ccd58  jns     short loc_1800CCD6A
0x1800ccd5a  xor     r9d, r9d; lpArguments
0x1800ccd5d  xor     r8d, r8d; nNumberOfArguments
0x1800ccd60  lea     edx, [r9+1]; dwExceptionFlags
0x1800ccd64  call    cs:__imp_RaiseException
0x1800ccd6a  mov     eax, r12d
0x1800ccd6d  mov     rcx, [rbp+70h+var_50]
0x1800ccd71  xor     rcx, rsp; StackCookie
0x1800ccd74  call    __security_check_cookie
0x1800ccd79  add     rsp, 138h
0x1800ccd80  pop     r15
0x1800ccd82  pop     r14
0x1800ccd84  pop     r13
0x1800ccd86  pop     r12
0x1800ccd88  pop     rdi
0x1800ccd89  pop     rsi
0x1800ccd8a  pop     rbx
0x1800ccd8b  pop     rbp
0x1800ccd8c  retn
0x1800ccd8d  lea     rcx, [rsp+170h+var_128]
0x1800ccd92  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800ccd97  jmp     loc_1800CCCF9
0x1800ccd9c  xor     eax, eax
0x1800ccd9e  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ccda5  cmp     [rbp+70h+var_E8], rax
0x1800ccda9  mov     edi, 0C00000E5h
0x1800ccdae  mov     ebx, 124h
0x1800ccdb3  jmp     loc_1800CCF2E
0x1800ccdb8  mov     [rsp+170h+var_110], 0
0x1800ccdc1  mov     [rsp+170h+var_120], 0
0x1800ccdca  cmp     r14, r15
0x1800ccdcd  jnb     short loc_1800CCE02
0x1800ccdcf  lea     rdx, ds:0[r14*8]
0x1800ccdd7  mov     rcx, r15
0x1800ccdda  add     rdx, r13
0x1800ccddd  sub     rcx, r14
0x1800ccde0  jz      short loc_1800CCDFB
0x1800ccde2  mov     rax, rdx
0x1800ccde5  add     rdx, 8
0x1800ccde9  mov     qword ptr [rax], 0
0x1800ccdf0  sub     rcx, 1
0x1800ccdf4  jnz     short loc_1800CCDE2
0x1800ccdf6  mov     rax, [rsp+170h+var_128]
0x1800ccdfb  mov     r14, r15
0x1800ccdfe  mov     [rbp+70h+var_F0], r15
0x1800cce02  mov     rdx, [r13+rax*8+0]
0x1800cce07  call    ?CleanupSingleReferenceProperties@CCSDirectMetadataManager@@AEAAJU_HIERARCHY@Rtl@Isolation@Windows@@AEAVCComponentMarkManager@@@Z; CCSDirectMetadataManager::CleanupSingleReferenceProperties(Windows::Isolation::Rtl::_HIERARCHY,CComponentMarkManager &)
0x1800cce0c  mov     r12d, eax
0x1800cce0f  test    eax, eax
0x1800cce11  js      loc_1800CCF52
0x1800cce17  cmp     r14, r15
0x1800cce1a  jnb     short loc_1800CCE4A
0x1800cce1c  lea     rdx, ds:0[r14*8]
0x1800cce24  mov     rcx, r15
0x1800cce27  add     rdx, r13
0x1800cce2a  sub     rcx, r14
0x1800cce2d  jz      short loc_1800CCE43
0x1800cce2f  mov     rax, rdx
0x1800cce32  add     rdx, 8
0x1800cce36  mov     qword ptr [rax], 0
0x1800cce3d  sub     rcx, 1
0x1800cce41  jnz     short loc_1800CCE2F
0x1800cce43  mov     r14, r15
0x1800cce46  mov     [rbp+70h+var_F0], r15
0x1800cce4a  mov     rdx, [rsp+170h+var_128]
0x1800cce4f  lea     r9, [rsp+170h+var_120]
0x1800cce54  xor     r8d, r8d
0x1800cce57  mov     rdx, [r13+rdx*8+0]
0x1800cce5c  lea     ecx, [r8+1]
0x1800cce60  call    RtlEnumerateHierarchy
0x1800cce65  mov     r12d, eax
0x1800cce68  test    eax, eax
0x1800cce6a  js      loc_1800CCF52
0x1800cce70  mov     rcx, [rsp+170h+var_120]
0x1800cce75  lea     r9, [rsp+170h+var_110]
0x1800cce7a  lea     r8, [rsp+170h+var_140]
0x1800cce7f  mov     edx, 1
0x1800cce84  call    RtlFetchHierarchyEnumeratorData
0x1800cce89  mov     r12d, eax
0x1800cce8c  test    eax, eax
0x1800cce8e  js      loc_1800CCF52
0x1800cce94  cmp     [rsp+170h+var_110], 0
0x1800cce9a  jnz     short loc_1800CCECF
0x1800cce9c  mov     rdx, [rsp+170h+var_128]
0x1800ccea1  lea     rcx, [rsp+170h+var_108]
0x1800ccea6  call    ??A?$CSmartArrayHolder@_KV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAAAEAV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800cceab  xor     r8d, r8d
0x1800cceae  mov     rdx, [rax]
0x1800cceb1  call    ?DeleteHierarchyRecursivelyByHandle@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@PEAU_DELETE_HIERARCHY_RECURSIVELY_BY_HANDLE_DISPOSITION@1234@@Z; Windows::Isolation::HierLib::Rtl::DeleteHierarchyRecursivelyByHandle(ulong,Windows::Isolation::Rtl::_HIERARCHY,Windows::Isolation::HierLib::Rtl::_DELETE_HIERARCHY_RECURSIVELY_BY_HANDLE_DISPOSITION *)
0x1800cceb6  mov     r12d, eax
0x1800cceb9  test    eax, eax
0x1800ccebb  js      loc_1800CCF52
0x1800ccec1  mov     r14, [rbp+70h+var_F0]
0x1800ccec5  mov     r15, [rsp+170h+var_F8]
0x1800cceca  mov     r13, qword ptr [rsp+170h+var_108+8]
0x1800ccecf  mov     r10, [rsp+170h+var_120]
0x1800cced4  test    r10, r10
0x1800cced7  jz      short loc_1800CCF22
0x1800cced9  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800ccee0  mov     [rsp+170h+var_130], edi
0x1800ccee4  mov     [rsp+170h+var_140], rsi
0x1800ccee9  test    r11, r11
0x1800cceec  jz      short loc_1800CCF3E
0x1800cceee  mov     rdx, r11
0x1800ccef1  mov     rcx, r10
0x1800ccef4  call    RtlIsTypeSafeHandleValid
0x1800ccef9  test    al, al
0x1800ccefb  jz      short loc_1800CCF3E
0x1800ccefd  mov     ecx, [r11]
0x1800ccf00  mov     rdx, r10
0x1800ccf03  mov     rax, [r11+20h]
0x1800ccf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccf0c  xor     ecx, ecx; dwExceptionCode
0x1800ccf0e  test    ecx, ecx
0x1800ccf10  jns     short loc_1800CCF22
0x1800ccf12  xor     r9d, r9d; lpArguments
0x1800ccf15  xor     r8d, r8d; nNumberOfArguments
0x1800ccf18  lea     edx, [r9+1]; dwExceptionFlags
0x1800ccf1c  call    cs:__imp_RaiseException
0x1800ccf22  mov     rax, [rsp+170h+var_128]
0x1800ccf27  inc     rax
0x1800ccf2a  cmp     rax, [rbp+70h+var_E8]
0x1800ccf2e  mov     [rsp+170h+var_128], rax
0x1800ccf33  jnz     loc_1800CCDB8
0x1800ccf39  xor     r12d, r12d
0x1800ccf3c  jmp     short loc_1800CCFAE
0x1800ccf3e  mov     [rsp+170h+var_138], ebx
0x1800ccf42  lea     rcx, [rsp+170h+var_140]
0x1800ccf47  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800ccf4c  mov     ecx, [rsp+170h+var_130]
0x1800ccf50  jmp     short loc_1800CCF0E
0x1800ccf52  mov     r10, [rsp+170h+var_120]
0x1800ccf57  test    r10, r10
0x1800ccf5a  jz      short loc_1800CCFAE
0x1800ccf5c  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800ccf63  mov     [rsp+170h+var_140], rsi
0x1800ccf68  mov     [rsp+170h+var_130], edi
0x1800ccf6c  test    r11, r11
0x1800ccf6f  jz      short loc_1800CCFEF
0x1800ccf71  mov     rdx, r11
0x1800ccf74  mov     rcx, r10
0x1800ccf77  call    RtlIsTypeSafeHandleValid
0x1800ccf7c  test    al, al
0x1800ccf7e  jz      short loc_1800CCFEF
0x1800ccf80  mov     ecx, [r11]
0x1800ccf83  mov     rdx, r10
0x1800ccf86  mov     rax, [r11+20h]
0x1800ccf8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccf8f  xor     ecx, ecx; dwExceptionCode
0x1800ccf91  test    ecx, ecx
0x1800ccf93  jns     short loc_1800CCFA5
0x1800ccf95  xor     r9d, r9d; lpArguments
0x1800ccf98  xor     r8d, r8d; nNumberOfArguments
0x1800ccf9b  lea     edx, [r9+1]; dwExceptionFlags
0x1800ccf9f  call    cs:__imp_RaiseException
0x1800ccfa5  mov     [rsp+170h+var_120], 0
0x1800ccfae  lea     rcx, [rsp+170h+var_108]
0x1800ccfb3  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ccfb8  mov     r10, [rsp+170h+var_118]
0x1800ccfbd  test    r10, r10
0x1800ccfc0  jz      loc_1800CCD6A
0x1800ccfc6  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800ccfcd  mov     [rsp+170h+var_130], edi
0x1800ccfd1  mov     [rsp+170h+var_140], rsi
0x1800ccfd6  test    r11, r11
0x1800ccfd9  jz      short loc_1800CD008
  ... truncated ...
```
