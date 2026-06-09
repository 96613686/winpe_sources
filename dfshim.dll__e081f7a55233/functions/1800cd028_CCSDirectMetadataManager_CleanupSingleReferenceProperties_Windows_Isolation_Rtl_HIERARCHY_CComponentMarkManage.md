# CCSDirectMetadataManager::CleanupSingleReferenceProperties(Windows::Isolation::Rtl::_HIERARCHY,CComponentMarkManager &)

- ea: `0x1800cd028`
- end: `0x1800cd4ee`
- name: `?CleanupSingleReferenceProperties@CCSDirectMetadataManager@@AEAAJU_HIERARCHY@Rtl@Isolation@Windows@@AEAVCComponentMarkManager@@@Z`
- size: `1222`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800ccb28`

## callees

- `0x180012b1c`
- `0x18002a844`
- `0x1800374a8`
- `0x18004a0dc`
- `0x18004f2dc`
- `0x1800cbcb4`
- `0x1800cc2ac`
- `0x1800cc82c`
- `0x1800cd028`
- `0x1800cdc08`
- `0x180114224`
- `0x1801142f0`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd291`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd38e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd413`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd4c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd291`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd38e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd413`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cd4c6`

## string_xrefs

- `0x1800cd087`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cd106`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall CCSDirectMetadataManager::CleanupSingleReferenceProperties(__int64 a1, __int64 a2)
{
  int v3; // edi
  __int64 v4; // r10
  unsigned int *v5; // r11
  signed int v6; // ecx
  __int64 v7; // r13
  int HierarchyEnumeratorData; // eax
  __int64 v9; // rax
  char v10; // r12
  __int64 v11; // r10
  unsigned int *v12; // r11
  signed int v13; // ecx
  __int64 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r10
  unsigned int *v17; // r11
  signed int v18; // ecx
  __int64 v19; // r10
  unsigned int *v20; // r11
  signed int v21; // ecx
  __int64 v22; // rbx
  __int64 *v23; // rax
  __int64 v24; // rcx
  __int128 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  __int128 v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h]
  _BYTE v39[8]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v40[16]; // [rsp+B0h] [rbp-50h] BYREF

  v28 = 0;
  v3 = RtlEnumerateHierarchy(1, a2, 0, &v28);
  if ( v3 < 0 )
  {
    if ( !v28 )
      return (unsigned int)v3;
    *(_QWORD *)&v26 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    LODWORD(v27) = -1073741595;
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v28) )
    {
      goto LABEL_5;
    }
    goto LABEL_55;
  }
  v7 = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  v33 = 0;
  HierarchyEnumeratorData = RtlFetchHierarchyEnumeratorData(v28, 5, v40, &v33);
LABEL_29:
  v3 = HierarchyEnumeratorData;
  if ( HierarchyEnumeratorData >= 0 )
  {
    v9 = 0;
    v38 = 0;
    if ( v33 )
    {
      while ( 1 )
      {
        v32 = 0;
        v29 = 0;
        v3 = Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(4, a2, 3221225472LL, &v40[3 * v9], &v29, &v32);
        if ( v3 < 0 )
          break;
        if ( (v32 & 1) != 0 )
        {
          v31 = 0;
          v3 = RtlEnumerateHierarchy(2, v29, 0, &v31);
          if ( v3 < 0 )
          {
LABEL_40:
            if ( v31 )
            {
              *(_QWORD *)&v26 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              LODWORD(v27) = -1073741595;
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v31) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v20 + 4))(*v20, v19);
                v21 = 0;
              }
              else
              {
                DWORD2(v26) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v26);
                v21 = v27;
              }
              if ( v21 < 0 )
                RaiseException(v21, 1u, 0, 0);
            }
            break;
          }
          v10 = 1;
          while ( 1 )
          {
            v30 = 0;
            v26 = 0;
            v27 = 0;
            v34 = 0;
            v3 = RtlFetchHierarchyEnumeratorData(v31, 1, &v26, &v34);
            if ( v3 < 0 )
            {
              if ( v31 )
              {
                LODWORD(v27) = -1073741595;
                *(_QWORD *)&v26 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
                  && (unsigned __int8)RtlIsTypeSafeHandleValid(v31) )
                {
                  (*((void (__fastcall **)(_QWORD, __int64))v12 + 4))(*v12, v11);
                  v13 = 0;
                }
                else
                {
                  DWORD2(v26) = 292;
                  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v26);
                  v13 = v27;
                }
                if ( v13 < 0 )
                  RaiseException(v13, 1u, 0, 0);
              }
              goto LABEL_46;
            }
            if ( !v34 )
              break;
            v3 = RtlCompareEncodedLBlobs(
                   (unsigned int)&v26,
                   (unsigned int)RtlDecodeUtf16LE,
                   (unsigned int)g_LUNICODE_STRING_appid,
                   (unsigned int)RtlDecodeUtf16LE,
                   0,
                   (__int64)&v30);
            if ( v3 < 0 )
              goto LABEL_40;
            if ( v30 )
            {
              v10 = 0;
              break;
            }
          }
          if ( v31 )
          {
            LODWORD(v27) = -1073741595;
            *(_QWORD *)&v26 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v31) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v17 + 4))(*v17, v16);
              v18 = 0;
            }
            else
            {
              DWORD2(v26) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v26);
              v18 = v27;
            }
            if ( v18 < 0 )
              RaiseException(v18, 1u, 0, 0);
          }
          if ( v10 )
          {
            if ( v7 != v36
              || (v3 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeBy(
                                    &v35,
                                    v39,
                                    5),
                  v3 >= 0) )
            {
              v14 = (__int64 *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](
                                 &v35,
                                 v7++);
              v15 = *v14;
              *v14 = v29;
              v29 = v15;
              goto LABEL_27;
            }
            break;
          }
        }
LABEL_27:
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v29);
        v9 = v38 + 1;
        v38 = v9;
        if ( v9 == v33 )
        {
          v33 = 0;
          HierarchyEnumeratorData = RtlFetchHierarchyEnumeratorData(v28, 5, v40, &v33);
          goto LABEL_29;
        }
      }
LABEL_46:
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v29);
    }
    else
    {
      v22 = 0;
      if ( v7 )
      {
        while ( 1 )
        {
          v23 = (__int64 *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](
                             &v35,
                             v22);
          v3 = Windows::Isolation::HierLib::Rtl::DeleteHierarchyRecursivelyByHandle(v24, *v23, 0);
          if ( v3 < 0 )
            break;
          if ( ++v22 == v7 )
            goto LABEL_51;
        }
      }
      else
      {
LABEL_51:
        v3 = 0;
      }
    }
  }
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v35);
  if ( v28 )
  {
    *(_QWORD *)&v26 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    LODWORD(v27) = -1073741595;
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v28) )
    {
LABEL_5:
      DWORD2(v26) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v26);
      v6 = v27;
      goto LABEL_56;
    }
LABEL_55:
    (*((void (__fastcall **)(_QWORD, __int64))v5 + 4))(*v5, v4);
    v6 = 0;
LABEL_56:
    if ( v6 < 0 )
      RaiseException(v6, 1u, 0, 0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800cd028  push    rbp
0x1800cd02a  push    rbx
0x1800cd02b  push    rsi
0x1800cd02c  push    rdi
0x1800cd02d  push    r12
0x1800cd02f  push    r13
0x1800cd031  push    r14
0x1800cd033  push    r15
0x1800cd035  lea     rbp, [rsp-48h]
0x1800cd03a  sub     rsp, 148h
0x1800cd041  mov     rax, cs:__security_cookie
0x1800cd048  xor     rax, rsp
0x1800cd04b  mov     [rbp+80h+var_50], rax
0x1800cd04f  xor     r8d, r8d
0x1800cd052  mov     [rsp+180h+var_138], 0
0x1800cd05b  lea     r9, [rsp+180h+var_138]
0x1800cd060  mov     rbx, rdx
0x1800cd063  lea     ecx, [r8+1]
0x1800cd067  call    RtlEnumerateHierarchy
0x1800cd06c  mov     edi, eax
0x1800cd06e  test    eax, eax
0x1800cd070  jns     short loc_1800CD0D2
0x1800cd072  mov     r10, [rsp+180h+var_138]
0x1800cd077  test    r10, r10
0x1800cd07a  jz      loc_1800CD4CC
0x1800cd080  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cd087  lea     r14, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cd08e  mov     qword ptr [rsp+180h+var_150], r14
0x1800cd093  mov     esi, 0C00000E5h
0x1800cd098  mov     dword ptr [rsp+180h+var_140], esi
0x1800cd09c  test    r11, r11
0x1800cd09f  jz      short loc_1800CD0B4
0x1800cd0a1  mov     rdx, r11
0x1800cd0a4  mov     rcx, r10
0x1800cd0a7  call    RtlIsTypeSafeHandleValid
0x1800cd0ac  test    al, al
0x1800cd0ae  jnz     loc_1800CD4A7
0x1800cd0b4  mov     r15d, 124h
0x1800cd0ba  mov     dword ptr [rsp+180h+var_150+8], r15d
0x1800cd0bf  lea     rcx, [rsp+180h+var_150]
0x1800cd0c4  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cd0c9  mov     ecx, dword ptr [rsp+180h+var_140]
0x1800cd0cd  jmp     loc_1800CD4B8
0x1800cd0d2  mov     rcx, [rsp+180h+var_138]
0x1800cd0d7  lea     r9, [rsp+180h+var_110]
0x1800cd0dc  xor     r13d, r13d
0x1800cd0df  lea     r8, [rbp+80h+var_D0]
0x1800cd0e3  xorps   xmm0, xmm0
0x1800cd0e6  mov     [rbp+80h+var_F0], r13
0x1800cd0ea  movdqu  [rbp+80h+var_100], xmm0
0x1800cd0ef  mov     [rbp+80h+var_E8], r13
0x1800cd0f3  lea     edx, [r13+5]
0x1800cd0f7  mov     [rsp+180h+var_110], r13
0x1800cd0fc  call    RtlFetchHierarchyEnumeratorData
0x1800cd101  mov     esi, 0C00000E5h
0x1800cd106  lea     r14, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cd10d  mov     r15d, 124h
0x1800cd113  jmp     loc_1800CD327
0x1800cd118  xor     eax, eax
0x1800cd11a  mov     [rbp+80h+var_E0], rax
0x1800cd11e  cmp     [rsp+180h+var_110], rax
0x1800cd123  jz      loc_1800CD43A
0x1800cd129  lea     rax, [rax+rax*2]
0x1800cd12d  mov     [rsp+180h+var_118], 0
0x1800cd135  lea     r9, [rbp+80h+var_D0]
0x1800cd139  mov     [rsp+180h+var_130], 0
0x1800cd142  lea     r9, [r9+rax*8]
0x1800cd146  mov     r8d, 0C0000000h
0x1800cd14c  lea     rax, [rsp+180h+var_118]
0x1800cd151  mov     rdx, rbx
0x1800cd154  mov     [rsp+180h+var_158], rax
0x1800cd159  mov     ecx, 4
0x1800cd15e  lea     rax, [rsp+180h+var_130]
0x1800cd163  mov     [rsp+180h+var_160], rax
0x1800cd168  call    ?RtlOpenHierarchy@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@KPEBU_LUNICODE_STRING@@PEAU5134@PEAK@Z; Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(ulong,Windows::Isolation::Rtl::_HIERARCHY,ulong,_LUNICODE_STRING const *,Windows::Isolation::Rtl::_HIERARCHY *,ulong *)
0x1800cd16d  mov     edi, eax
0x1800cd16f  test    eax, eax
0x1800cd171  js      loc_1800CD419
0x1800cd177  test    byte ptr [rsp+180h+var_118], 1
0x1800cd17c  jz      loc_1800CD2E6
0x1800cd182  mov     rdx, [rsp+180h+var_130]
0x1800cd187  lea     r9, [rsp+180h+var_120]
0x1800cd18c  xor     r8d, r8d
0x1800cd18f  mov     [rsp+180h+var_120], 0
0x1800cd198  lea     ecx, [r8+2]
0x1800cd19c  call    RtlEnumerateHierarchy
0x1800cd1a1  mov     edi, eax
0x1800cd1a3  test    eax, eax
0x1800cd1a5  js      loc_1800CD3C6
0x1800cd1ab  mov     r12b, 1
0x1800cd1ae  jmp     short loc_1800CD203
0x1800cd1b0  cmp     [rsp+180h+var_108], 0
0x1800cd1b6  jz      loc_1800CD339
0x1800cd1bc  lea     rax, [rsp+180h+var_128]
0x1800cd1c1  mov     [rsp+180h+var_158], rax
0x1800cd1c6  lea     r9, RtlDecodeUtf16LE
0x1800cd1cd  lea     r8, g_LUNICODE_STRING_appid
0x1800cd1d4  mov     [rsp+180h+var_160], 0
0x1800cd1dd  lea     rdx, RtlDecodeUtf16LE
0x1800cd1e4  lea     rcx, [rsp+180h+var_150]
0x1800cd1e9  call    RtlCompareEncodedLBlobs
0x1800cd1ee  mov     edi, eax
0x1800cd1f0  test    eax, eax
0x1800cd1f2  js      loc_1800CD3C6
0x1800cd1f8  cmp     [rsp+180h+var_128], 0
0x1800cd1fd  jnz     loc_1800CD336
0x1800cd203  mov     rcx, [rsp+180h+var_120]
0x1800cd208  lea     r9, [rsp+180h+var_108]
0x1800cd20d  xor     eax, eax
0x1800cd20f  lea     r8, [rsp+180h+var_150]
0x1800cd214  xorps   xmm0, xmm0
0x1800cd217  mov     [rsp+180h+var_128], eax
0x1800cd21b  movups  [rsp+180h+var_150], xmm0
0x1800cd220  mov     [rsp+180h+var_140], rax
0x1800cd225  lea     edx, [rax+1]
0x1800cd228  mov     [rsp+180h+var_108], rax
0x1800cd22d  call    RtlFetchHierarchyEnumeratorData
0x1800cd232  mov     edi, eax
0x1800cd234  test    eax, eax
0x1800cd236  jns     loc_1800CD1B0
0x1800cd23c  mov     r10, [rsp+180h+var_120]
0x1800cd241  test    r10, r10
0x1800cd244  jz      short loc_1800CD297
0x1800cd246  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cd24d  mov     dword ptr [rsp+180h+var_140], esi
0x1800cd251  mov     qword ptr [rsp+180h+var_150], r14
0x1800cd256  test    r11, r11
0x1800cd259  jz      loc_1800CD3AE
0x1800cd25f  mov     rdx, r11
0x1800cd262  mov     rcx, r10
0x1800cd265  call    RtlIsTypeSafeHandleValid
0x1800cd26a  test    al, al
0x1800cd26c  jz      loc_1800CD3AE
0x1800cd272  mov     ecx, [r11]
0x1800cd275  mov     rdx, r10
0x1800cd278  mov     rax, [r11+20h]
0x1800cd27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd281  xor     ecx, ecx; dwExceptionCode
0x1800cd283  test    ecx, ecx
0x1800cd285  jns     short loc_1800CD297
0x1800cd287  xor     r9d, r9d; lpArguments
0x1800cd28a  xor     r8d, r8d; nNumberOfArguments
0x1800cd28d  lea     edx, [r9+1]; dwExceptionFlags
0x1800cd291  call    cs:__imp_RaiseException
0x1800cd297  test    edi, edi
0x1800cd299  js      loc_1800CD419
0x1800cd29f  test    r12b, r12b
0x1800cd2a2  jz      short loc_1800CD2E6
0x1800cd2a4  cmp     r13, [rbp+80h+var_F0]
0x1800cd2a8  jnz     short loc_1800CD2C7
0x1800cd2aa  mov     r8d, 5
0x1800cd2b0  lea     rdx, [rbp+80h+var_D8]
0x1800cd2b4  lea     rcx, [rbp+80h+var_100]
0x1800cd2b8  call    ?EnlargeBy@?$CSmartArrayHolder@_KV?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeBy(unsigned __int64)
0x1800cd2bd  mov     edi, [rax]
0x1800cd2bf  test    edi, edi
0x1800cd2c1  js      loc_1800CD419
0x1800cd2c7  mov     rdx, r13
0x1800cd2ca  lea     rcx, [rbp+80h+var_100]
0x1800cd2ce  call    ??A?$CSmartArrayHolder@_KV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAAAEAV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800cd2d3  mov     rcx, [rsp+180h+var_130]
0x1800cd2d8  inc     r13
0x1800cd2db  mov     rdx, [rax]
0x1800cd2de  mov     [rax], rcx
0x1800cd2e1  mov     [rsp+180h+var_130], rdx
0x1800cd2e6  lea     rcx, [rsp+180h+var_130]
0x1800cd2eb  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cd2f0  mov     rax, [rbp+80h+var_E0]
0x1800cd2f4  inc     rax
0x1800cd2f7  mov     [rbp+80h+var_E0], rax
0x1800cd2fb  cmp     rax, [rsp+180h+var_110]
0x1800cd300  jnz     loc_1800CD129
0x1800cd306  mov     rcx, [rsp+180h+var_138]
0x1800cd30b  lea     r9, [rsp+180h+var_110]
0x1800cd310  lea     r8, [rbp+80h+var_D0]
0x1800cd314  mov     [rsp+180h+var_110], 0
0x1800cd31d  mov     edx, 5
0x1800cd322  call    RtlFetchHierarchyEnumeratorData
0x1800cd327  mov     edi, eax
0x1800cd329  test    eax, eax
0x1800cd32b  jns     loc_1800CD118
0x1800cd331  jmp     loc_1800CD468
0x1800cd336  xor     r12b, r12b
0x1800cd339  mov     r10, [rsp+180h+var_120]
0x1800cd33e  test    r10, r10
0x1800cd341  jz      loc_1800CD29F
0x1800cd347  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cd34e  mov     dword ptr [rsp+180h+var_140], esi
0x1800cd352  mov     qword ptr [rsp+180h+var_150], r14
0x1800cd357  test    r11, r11
0x1800cd35a  jz      short loc_1800CD399
0x1800cd35c  mov     rdx, r11
0x1800cd35f  mov     rcx, r10
0x1800cd362  call    RtlIsTypeSafeHandleValid
0x1800cd367  test    al, al
0x1800cd369  jz      short loc_1800CD399
0x1800cd36b  mov     ecx, [r11]
0x1800cd36e  mov     rdx, r10
0x1800cd371  mov     rax, [r11+20h]
0x1800cd375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd37a  xor     ecx, ecx; dwExceptionCode
0x1800cd37c  test    ecx, ecx
0x1800cd37e  jns     loc_1800CD29F
0x1800cd384  xor     r9d, r9d; lpArguments
0x1800cd387  xor     r8d, r8d; nNumberOfArguments
0x1800cd38a  lea     edx, [r9+1]; dwExceptionFlags
0x1800cd38e  call    cs:__imp_RaiseException
0x1800cd394  jmp     loc_1800CD29F
0x1800cd399  mov     dword ptr [rsp+180h+var_150+8], r15d
0x1800cd39e  lea     rcx, [rsp+180h+var_150]
0x1800cd3a3  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cd3a8  mov     ecx, dword ptr [rsp+180h+var_140]
0x1800cd3ac  jmp     short loc_1800CD37C
0x1800cd3ae  mov     dword ptr [rsp+180h+var_150+8], r15d
0x1800cd3b3  lea     rcx, [rsp+180h+var_150]
0x1800cd3b8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cd3bd  mov     ecx, dword ptr [rsp+180h+var_140]
0x1800cd3c1  jmp     loc_1800CD283
0x1800cd3c6  mov     r10, [rsp+180h+var_120]
0x1800cd3cb  test    r10, r10
0x1800cd3ce  jz      short loc_1800CD419
0x1800cd3d0  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cd3d7  mov     qword ptr [rsp+180h+var_150], r14
0x1800cd3dc  mov     dword ptr [rsp+180h+var_140], esi
0x1800cd3e0  test    r11, r11
0x1800cd3e3  jz      short loc_1800CD425
0x1800cd3e5  mov     rdx, r11
0x1800cd3e8  mov     rcx, r10
0x1800cd3eb  call    RtlIsTypeSafeHandleValid
0x1800cd3f0  test    al, al
0x1800cd3f2  jz      short loc_1800CD425
0x1800cd3f4  mov     ecx, [r11]
0x1800cd3f7  mov     rdx, r10
0x1800cd3fa  mov     rax, [r11+20h]
0x1800cd3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd403  xor     ecx, ecx; dwExceptionCode
0x1800cd405  test    ecx, ecx
0x1800cd407  jns     short loc_1800CD419
0x1800cd409  xor     r9d, r9d; lpArguments
0x1800cd40c  xor     r8d, r8d; nNumberOfArguments
0x1800cd40f  lea     edx, [r9+1]; dwExceptionFlags
0x1800cd413  call    cs:__imp_RaiseException
0x1800cd419  lea     rcx, [rsp+180h+var_130]
0x1800cd41e  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cd423  jmp     short loc_1800CD468
0x1800cd425  mov     dword ptr [rsp+180h+var_150+8], r15d
0x1800cd42a  lea     rcx, [rsp+180h+var_150]
0x1800cd42f  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cd434  mov     ecx, dword ptr [rsp+180h+var_140]
0x1800cd438  jmp     short loc_1800CD405
0x1800cd43a  xor     ebx, ebx
0x1800cd43c  test    r13, r13
0x1800cd43f  jz      short loc_1800CD466
0x1800cd441  mov     rdx, rbx
0x1800cd444  lea     rcx, [rbp+80h+var_100]
0x1800cd448  call    ??A?$CSmartArrayHolder@_KV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAAAEAV?$CTSHANDLE@VCCOMPONENT_STORE_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CCOMPONENT_STORE_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800cd44d  xor     r8d, r8d
0x1800cd450  mov     rdx, [rax]
0x1800cd453  call    ?DeleteHierarchyRecursivelyByHandle@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@PEAU_DELETE_HIERARCHY_RECURSIVELY_BY_HANDLE_DISPOSITION@1234@@Z; Windows::Isolation::HierLib::Rtl::DeleteHierarchyRecursivelyByHandle(ulong,Windows::Isolation::Rtl::_HIERARCHY,Windows::Isolation::HierLib::Rtl::_DELETE_HIERARCHY_RECURSIVELY_BY_HANDLE_DISPOSITION *)
0x1800cd458  mov     edi, eax
0x1800cd45a  test    eax, eax
0x1800cd45c  js      short loc_1800CD468
0x1800cd45e  inc     rbx
0x1800cd461  cmp     rbx, r13
0x1800cd464  jnz     short loc_1800CD441
0x1800cd466  xor     edi, edi
0x1800cd468  lea     rcx, [rbp+80h+var_100]
0x1800cd46c  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800cd471  mov     r10, [rsp+180h+var_138]
0x1800cd476  test    r10, r10
0x1800cd479  jz      short loc_1800CD4CC
0x1800cd47b  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cd482  mov     qword ptr [rsp+180h+var_150], r14
0x1800cd487  mov     dword ptr [rsp+180h+var_140], esi
0x1800cd48b  test    r11, r11
0x1800cd48e  jz      loc_1800CD0BA
0x1800cd494  mov     rdx, r11
0x1800cd497  mov     rcx, r10
0x1800cd49a  call    RtlIsTypeSafeHandleValid
0x1800cd49f  test    al, al
0x1800cd4a1  jz      loc_1800CD0BA
0x1800cd4a7  mov     ecx, [r11]
0x1800cd4aa  mov     rdx, r10
0x1800cd4ad  mov     rax, [r11+20h]
0x1800cd4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd4b6  xor     ecx, ecx; dwExceptionCode
0x1800cd4b8  test    ecx, ecx
0x1800cd4ba  jns     short loc_1800CD4CC
0x1800cd4bc  xor     r9d, r9d; lpArguments
0x1800cd4bf  xor     r8d, r8d; nNumberOfArguments
0x1800cd4c2  lea     edx, [r9+1]; dwExceptionFlags
0x1800cd4c6  call    cs:__imp_RaiseException
0x1800cd4cc  mov     eax, edi
0x1800cd4ce  mov     rcx, [rbp+80h+var_50]
0x1800cd4d2  xor     rcx, rsp; StackCookie
0x1800cd4d5  call    __security_check_cookie
0x1800cd4da  add     rsp, 148h
0x1800cd4e1  pop     r15
0x1800cd4e3  pop     r14
0x1800cd4e5  pop     r13
  ... truncated ...
```
