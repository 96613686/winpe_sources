# ExtractProcessorFeaturesFromRepository(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &)

- ea: `0x18003f7f0`
- end: `0x18003ff7c`
- name: `?ExtractProcessorFeaturesFromRepository@@YA?AU_PROCESSOR_FEATURES@@AEBV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@@Z`
- size: `1932`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004011c`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180007fc9`
- `0x180007fe1`
- `0x18000995c`
- `0x18001587c`
- `0x180020604`
- `0x18003509c`
- `0x180039338`
- `0x18003a140`
- `0x18003aa98`
- `0x18003f178`
- `0x18003f7f0`
- `0x1800405e0`
- `0x1800926f0`
- `0x18009280c`
- `0x18009298c`
- `0x180092a50`
- `0x1800a3010`

## string_xrefs

- `0x18003fd78`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fd9b`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fdbe`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fde1`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fe04`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fe27`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fe4a`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fe6d`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fe90`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003ff0d`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x18003fd55`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003fea5`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003feba`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003fed2`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003feea`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003ff25`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003ff3d`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003ff55`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003ff6a`: `onecore\vm\common\processor\ProcessorFeatures.h`
- `0x18003f93e`: `/savedVM/processor/features/cache/line_flush_size`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ExtractProcessorFeaturesFromRepository(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r14
  const struct type_info *v5; // rdx
  int v6; // eax
  int v7; // eax
  int SavedProcessorFeaturesFromRepository; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int SavedSyntheticProcessorFeaturesFromRepository; // eax
  void *v13; // rdx
  __int64 v14; // rax
  int SavedAssignableSyntheticPFFromRepository; // eax
  __int64 v16; // rax
  int SavedVmmCapabilitiesFromRepository; // eax
  int v18; // eax
  int v19; // eax
  _QWORD *v20; // rdi
  int v21; // eax
  int v22; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  __int64 Buf1; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v35; // [rsp+28h] [rbp-D8h]
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  void *v37[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h]
  unsigned int v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 Buf2; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  void *v45[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h]
  void *v47[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-50h]
  void *Src[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-38h]
  __int128 v51; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int128 v53; // [rsp+F0h] [rbp-10h]
  __int128 v54; // [rsp+100h] [rbp+0h] BYREF
  __int128 v55; // [rsp+110h] [rbp+10h] BYREF
  __int128 v56; // [rsp+120h] [rbp+20h]
  __int64 v57; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  memset_0(&v51, 0, 0x68u);
  v35 = 0;
  v4 = *a2;
  *(_QWORD *)&v35 = v4;
  Vml::VmSharableObject::AddUserInternal((Vml::VmSharableObject *)(v4 + 8), v5);
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 344LL))(v4, 0);
  DWORD2(v35) = v6;
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8DF,
      (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
      (const char *)(unsigned int)v6,
      Buf1);
  v41 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)*a2 + 120LL))(
         *a2,
         L"/savedVM/processor/vendor",
         &v41);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E2,
      (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
      (const char *)(unsigned int)v7,
      Buf1);
  if ( v41 == 16 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E7,
      (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
      (const char *)0x80004001LL,
      Buf1);
  *(_OWORD *)Src = 0;
  v50 = 0;
  v42 = 0;
  SavedProcessorFeaturesFromRepository = VmUtilities::GetSavedProcessorFeaturesFromRepository(*a2, Src, &v42);
  if ( SavedProcessorFeaturesFromRepository >= 0 )
  {
    *((_QWORD *)&v52 + 1) = v42;
    if ( (unsigned __int64)(((char *)Src[1] - (char *)Src[0]) >> 3) > 3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D6,
        (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
        (const char *)0x8007000DLL,
        Buf1);
    memmove_0(&v51, Src[0], (char *)Src[1] - (char *)Src[0]);
  }
  else if ( SavedProcessorFeaturesFromRepository != -2147024894 && SavedProcessorFeaturesFromRepository != -2147188715 )
  {
    v24 = wil::verify_hresult<long>((unsigned int)SavedProcessorFeaturesFromRepository);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
      (const char *)v24,
      Buf1);
  }
  v43 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)*a2 + 120LL))(
         *a2,
         L"/savedVM/processor/features/cache/line_flush_size",
         &v43);
  if ( v9 >= 0 )
  {
    *(_QWORD *)&v53 = v43;
  }
  else if ( v9 != -2147024894 && v9 != -2147188715 )
  {
    v25 = wil::verify_hresult<long>((unsigned int)v9);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
      (const char *)v25,
      Buf1);
  }
  if ( v41 != 16 )
  {
    Buf2 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)*a2 + 120LL))(
            *a2,
            L"/savedVM/implemented_physical_address_bits",
            &Buf2);
    if ( v10 >= 0 )
    {
      *((_QWORD *)&v53 + 1) = Buf2;
    }
    else if ( v10 != -2147024894 && v10 != -2147188715 )
    {
      v26 = wil::verify_hresult<long>((unsigned int)v10);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
        (const char *)v26,
        Buf1);
    }
    v36 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)*a2 + 120LL))(
            *a2,
            L"/savedVM/non_architectural_core_sharing",
            &v36);
    if ( v11 >= 0 )
    {
      *(_QWORD *)&v54 = v36;
    }
    else
    {
      if ( v11 != -2147024894 && v11 != -2147188715 )
      {
        v33 = wil::verify_hresult<long>((unsigned int)v11);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x24,
          (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
          (const char *)v33,
          Buf1);
      }
      *(_QWORD *)&v54 = 0;
    }
  }
  *(_OWORD *)v47 = 0;
  v48 = 0;
  SavedSyntheticProcessorFeaturesFromRepository = VmUtilities::GetSavedSyntheticProcessorFeaturesFromRepository(
                                                    *a2,
                                                    v47);
  if ( SavedSyntheticProcessorFeaturesFromRepository >= 0 )
  {
    v13 = v47[0];
    if ( v47[0] != v47[1] )
    {
      if ( (unsigned __int64)(((char *)v47[1] - (char *)v47[0]) >> 3) > 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D6,
          (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
          (const char *)0x8007000DLL,
          Buf1);
      memmove_0((char *)&v54 + 8, v47[0], (char *)v47[1] - (char *)v47[0]);
    }
  }
  else if ( SavedSyntheticProcessorFeaturesFromRepository != -2147024894
         && SavedSyntheticProcessorFeaturesFromRepository != -2147188715 )
  {
    v27 = wil::verify_hresult<long>((unsigned int)SavedSyntheticProcessorFeaturesFromRepository);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
      (const char *)v27,
      Buf1);
  }
  LOBYTE(v13) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
    v13);
  *(_OWORD *)v45 = 0;
  v46 = 0;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v14 = Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(
          &v36,
          a2);
  SavedAssignableSyntheticPFFromRepository = VmUtilities::GetSavedAssignableSyntheticPFFromRepository(v14, v45);
  if ( SavedAssignableSyntheticPFFromRepository >= 0 )
  {
    if ( v45[0] != v45[1] )
    {
      if ( (unsigned __int64)(((char *)v45[1] - (char *)v45[0]) >> 3) > 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D6,
          (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
          (const char *)0x8007000DLL,
          Buf1);
      memmove_0(&v55, v45[0], (char *)v45[1] - (char *)v45[0]);
    }
  }
  else if ( SavedAssignableSyntheticPFFromRepository != -2147024894
         && SavedAssignableSyntheticPFFromRepository != -2147188715 )
  {
    v28 = wil::verify_hresult<long>((unsigned int)SavedAssignableSyntheticPFFromRepository);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
      (const char *)v28,
      Buf1);
  }
  v16 = Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(
          &v36,
          a2);
  SavedVmmCapabilitiesFromRepository = VmUtilities::GetSavedVmmCapabilitiesFromRepository(v16, v37);
  if ( SavedVmmCapabilitiesFromRepository >= 0 )
  {
    if ( v37[0] != v37[1] )
    {
      if ( (unsigned __int64)(((char *)v37[1] - (char *)v37[0]) >> 3) > 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D6,
          (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
          (const char *)0x8007000DLL,
          Buf1);
      memmove_0((char *)&v55 + 8, v37[0], (char *)v37[1] - (char *)v37[0]);
    }
  }
  else if ( SavedVmmCapabilitiesFromRepository != -2147024894 && SavedVmmCapabilitiesFromRepository != -2147188715 )
  {
    v29 = wil::verify_hresult<long>((unsigned int)SavedVmmCapabilitiesFromRepository);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
      (const char *)v29,
      Buf1);
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v37);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v45);
  v44 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)*a2 + 120LL))(
          *a2,
          L"/savedVM/processor/physical_address_width",
          &v44);
  if ( v18 >= 0 )
  {
    *(_QWORD *)&v56 = v44;
  }
  else if ( v18 != -2147024894 && v18 != -2147188715 )
  {
    v30 = wil::verify_hresult<long>((unsigned int)v18);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
      (const char *)v30,
      Buf1);
  }
  v39 = 0;
  v19 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*a2 + 288LL))(*a2, &v39);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x939,
      (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
      (const char *)(unsigned int)v19,
      Buf1);
  if ( v39 >= 0xB01 )
  {
    Buf1 = 0;
    *(_OWORD *)v37 = 0;
    v38 = 0;
    std::vector<unsigned __int64>::_Buy_nonzero(v37, 1);
    v20 = v37[0];
    Buf2 = 0;
    memcmp_0(&Buf1, &Buf2, 8u);
    *v20 = 0;
    v37[1] = v20 + 1;
    Buf1 = 0;
    std::_Tidy_guard<std::vector<Schema::Version>>::~_Tidy_guard<std::vector<Schema::Version>>(&Buf1);
    v21 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void *))(*(_QWORD *)*a2 + 120LL))(
            *a2,
            L"/savedVM/enlightenment_modifications",
            v37[0]);
    if ( v21 >= 0 )
    {
      if ( (unsigned __int64)(((char *)v37[1] - (char *)v37[0]) >> 3) > 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D6,
          (unsigned int)"onecore\\vm\\common\\processor\\ProcessorFeatures.h",
          (const char *)0x8007000DLL,
          Buf1);
      memmove_0(&v57, v37[0], (char *)v37[1] - (char *)v37[0]);
    }
    else if ( v21 != -2147024894 && v21 != -2147188715 )
    {
      v31 = wil::verify_hresult<long>((unsigned int)v21);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
        (const char *)v31,
        Buf1);
    }
    v36 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)*a2 + 120LL))(
            *a2,
            L"/savedVM/guest_feature_set",
            &v36);
    if ( v22 >= 0 )
    {
      *((_QWORD *)&v56 + 1) = v36;
    }
    else if ( v22 != -2147024894 && v22 != -2147188715 )
    {
      v32 = wil::verify_hresult<long>((unsigned int)v22);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
        (const char *)v32,
        Buf1);
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v37);
  }
  *(_OWORD *)a1 = v51;
  *(_OWORD *)(a1 + 16) = v52;
  *(_OWORD *)(a1 + 32) = v53;
  *(_OWORD *)(a1 + 48) = v54;
  *(_OWORD *)(a1 + 64) = v55;
  *(_OWORD *)(a1 + 80) = v56;
  *(_QWORD *)(a1 + 96) = v57;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v47);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(Src);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
  Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v4 + 8));
  return a1;
}

```

## disassembly

```asm
0x18003f7f0  push    rbp
0x18003f7f2  push    rbx
0x18003f7f3  push    rsi
0x18003f7f4  push    rdi
0x18003f7f5  push    r12
0x18003f7f7  push    r13
0x18003f7f9  push    r14
0x18003f7fb  push    r15
0x18003f7fd  lea     rbp, [rsp-58h]
0x18003f802  sub     rsp, 158h
0x18003f809  mov     rax, cs:__security_cookie
0x18003f810  xor     rax, rsp
0x18003f813  mov     [rbp+90h+var_50], rax
0x18003f817  mov     rbx, rdx
0x18003f81a  mov     rsi, rcx
0x18003f81d  xor     edx, edx; Val
0x18003f81f  lea     r8d, [rdx+68h]; Size
0x18003f823  lea     rcx, [rbp+90h+var_C0]; void *
0x18003f827  call    memset_0
0x18003f82c  xorps   xmm0, xmm0
0x18003f82f  movups  [rsp+190h+var_168], xmm0
0x18003f834  mov     r14, [rbx]
0x18003f837  mov     qword ptr [rsp+190h+var_168], r14
0x18003f83c  lea     rcx, [r14+8]; this
0x18003f840  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x18003f845  mov     rax, [r14]
0x18003f848  xor     edx, edx
0x18003f84a  mov     rcx, r14
0x18003f84d  mov     rax, [rax+158h]
0x18003f854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f859  mov     dword ptr [rsp+190h+var_168+8], eax
0x18003f85d  mov     rcx, [rbp+98h]; this
0x18003f864  xor     r12d, r12d
0x18003f867  test    eax, eax
0x18003f869  js      loc_18003FEA2
0x18003f86f  mov     [rsp+190h+var_128], r12
0x18003f874  mov     rcx, [rbx]
0x18003f877  mov     rax, [rcx]
0x18003f87a  lea     r8, [rsp+190h+var_128]
0x18003f87f  lea     rdx, ?SAVED_VM_PROCESSOR_VENDOR_XPATH@@3QBGB; "/savedVM/processor/vendor"
0x18003f886  mov     rax, [rax+78h]
0x18003f88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f88f  mov     rcx, [rbp+98h]; this
0x18003f896  test    eax, eax
0x18003f898  js      loc_18003FEB7
0x18003f89e  cmp     [rsp+190h+var_128], 10h
0x18003f8a4  setz    al
0x18003f8a7  mov     rcx, [rbp+98h]; this
0x18003f8ae  test    al, al
0x18003f8b0  jnz     loc_18003FECC
0x18003f8b6  xorps   xmm1, xmm1
0x18003f8b9  movdqu  xmmword ptr [rbp+90h+Src], xmm1
0x18003f8be  mov     [rbp+90h+var_C8], r12
0x18003f8c2  mov     [rsp+190h+var_120], r12
0x18003f8c7  lea     r8, [rsp+190h+var_120]
0x18003f8cc  lea     rdx, [rbp+90h+Src]
0x18003f8d0  mov     rcx, [rbx]
0x18003f8d3  call    ?GetSavedProcessorFeaturesFromRepository@VmUtilities@@YAJPEAVVmRepository@@AEAV?$vector@_KV?$allocator@_K@std@@@std@@AEA_K@Z; VmUtilities::GetSavedProcessorFeaturesFromRepository(VmRepository *,std::vector<unsigned __int64> &,unsigned __int64 &)
0x18003f8d8  mov     edi, 80070002h
0x18003f8dd  mov     r13d, 80048015h
0x18003f8e3  test    eax, eax
0x18003f8e5  jns     short loc_18003F8F6
0x18003f8e7  cmp     eax, edi
0x18003f8e9  jz      short loc_18003F92E
0x18003f8eb  cmp     eax, r13d
0x18003f8ee  jnz     loc_18003FD67
0x18003f8f4  jmp     short loc_18003F92E
0x18003f8f6  mov     rax, [rsp+190h+var_120]
0x18003f8fb  mov     [rbp+90h+var_A8], rax
0x18003f8ff  mov     r8, [rbp+90h+Src+8]
0x18003f903  mov     rcx, [rbp+98h]; this
0x18003f90a  mov     rax, r8
0x18003f90d  mov     rdx, [rbp+90h+Src]; Src
0x18003f911  sub     rax, rdx
0x18003f914  sar     rax, 3
0x18003f918  cmp     rax, 3
0x18003f91c  ja      loc_18003FEE4
0x18003f922  sub     r8, rdx; Size
0x18003f925  lea     rcx, [rbp+90h+var_C0]; void *
0x18003f929  call    memmove_0
0x18003f92e  mov     [rsp+190h+var_118], r12
0x18003f933  mov     rcx, [rbx]
0x18003f936  mov     rax, [rcx]
0x18003f939  lea     r8, [rsp+190h+var_118]
0x18003f93e  lea     rdx, ?SAVED_VM_PROCESSOR_CLFLUSH_SIZE_XPATH@@3QBGB; "/savedVM/processor/features/cache/line_"...
0x18003f945  mov     rax, [rax+78h]
0x18003f949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f94e  test    eax, eax
0x18003f950  jns     short loc_18003F961
0x18003f952  cmp     eax, edi
0x18003f954  jz      short loc_18003F96A
0x18003f956  cmp     eax, r13d
0x18003f959  jnz     loc_18003FD8A
0x18003f95f  jmp     short loc_18003F96A
0x18003f961  mov     rax, [rsp+190h+var_118]
0x18003f966  mov     qword ptr [rbp+90h+var_A0], rax
0x18003f96a  cmp     [rsp+190h+var_128], 10h
0x18003f970  jz      short loc_18003F9EE
0x18003f972  mov     [rsp+190h+Buf2], r12
0x18003f977  mov     rcx, [rbx]
0x18003f97a  mov     rax, [rcx]
0x18003f97d  lea     r8, [rsp+190h+Buf2]
0x18003f982  lea     rdx, ?SAVED_VM_IMPLEMENTED_PHYSICAL_ADDRESS_BITS_XPATH@@3QBGB; "/savedVM/implemented_physical_address_b"...
0x18003f989  mov     rax, [rax+78h]
0x18003f98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f992  test    eax, eax
0x18003f994  jns     short loc_18003F9A5
0x18003f996  cmp     eax, edi
0x18003f998  jz      short loc_18003F9AE
0x18003f99a  cmp     eax, r13d
0x18003f99d  jnz     loc_18003FDAD
0x18003f9a3  jmp     short loc_18003F9AE
0x18003f9a5  mov     rax, [rsp+190h+Buf2]
0x18003f9aa  mov     qword ptr [rbp+90h+var_A0+8], rax
0x18003f9ae  mov     [rsp+190h+var_158], r12
0x18003f9b3  mov     rcx, [rbx]
0x18003f9b6  mov     rax, [rcx]
0x18003f9b9  lea     r8, [rsp+190h+var_158]
0x18003f9be  lea     rdx, ?SAVED_VM_NON_ARCHITECURAL_CORE_SHARING_XPATH@@3QBGB; "/savedVM/non_architectural_core_sharing"
0x18003f9c5  mov     rax, [rax+78h]
0x18003f9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9ce  test    eax, eax
0x18003f9d0  jns     short loc_18003F9E5
0x18003f9d2  cmp     eax, edi
0x18003f9d4  jz      short loc_18003F9DF
0x18003f9d6  cmp     eax, r13d
0x18003f9d9  jnz     loc_18003FEFC
0x18003f9df  mov     qword ptr [rbp+90h+var_90], r12
0x18003f9e3  jmp     short loc_18003F9EE
0x18003f9e5  mov     rax, [rsp+190h+var_158]
0x18003f9ea  mov     qword ptr [rbp+90h+var_90], rax
0x18003f9ee  xorps   xmm1, xmm1
0x18003f9f1  movdqu  xmmword ptr [rbp+90h+var_F0], xmm1
0x18003f9f6  mov     [rbp+90h+var_E0], r12
0x18003f9fa  lea     rdx, [rbp+90h+var_F0]
0x18003f9fe  mov     rcx, [rbx]
0x18003fa01  call    ?GetSavedSyntheticProcessorFeaturesFromRepository@VmUtilities@@YAJPEAVVmRepository@@AEAV?$vector@_KV?$allocator@_K@std@@@std@@@Z; VmUtilities::GetSavedSyntheticProcessorFeaturesFromRepository(VmRepository *,std::vector<unsigned __int64> &)
0x18003fa06  test    eax, eax
0x18003fa08  jns     short loc_18003FA19
0x18003fa0a  cmp     eax, edi
0x18003fa0c  jz      short loc_18003FA4A
0x18003fa0e  cmp     eax, r13d
0x18003fa11  jnz     loc_18003FDD0
0x18003fa17  jmp     short loc_18003FA4A
0x18003fa19  mov     r8, [rbp+90h+var_F0+8]
0x18003fa1d  mov     rdx, [rbp+90h+var_F0]; Src
0x18003fa21  cmp     rdx, r8
0x18003fa24  jz      short loc_18003FA4A
0x18003fa26  sub     r8, rdx; Size
0x18003fa29  mov     rcx, [rbp+98h]; this
0x18003fa30  mov     rax, r8
0x18003fa33  sar     rax, 3
0x18003fa37  cmp     rax, 1
0x18003fa3b  ja      loc_18003FF1F
0x18003fa41  lea     rcx, [rbp+90h+var_90+8]; void *
0x18003fa45  call    memmove_0
0x18003fa4a  mov     dl, 1
0x18003fa4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x18003fa53  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003fa58  xorps   xmm1, xmm1
0x18003fa5b  movdqu  xmmword ptr [rbp+90h+var_108], xmm1
0x18003fa60  mov     [rbp+90h+var_F8], r12
0x18003fa64  movdqu  xmmword ptr [rsp+190h+var_150], xmm1
0x18003fa6a  mov     [rsp+190h+var_140], r12
0x18003fa6f  mov     rdx, rbx
0x18003fa72  lea     rcx, [rsp+190h+var_158]
0x18003fa77  call    ??0?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@AEBV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &)
0x18003fa7c  lea     rdx, [rbp+90h+var_108]
0x18003fa80  mov     rcx, rax
0x18003fa83  call    ?GetSavedAssignableSyntheticPFFromRepository@VmUtilities@@YAJV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@AEAV?$vector@_KV?$allocator@_K@std@@@std@@@Z; VmUtilities::GetSavedAssignableSyntheticPFFromRepository(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>,std::vector<unsigned __int64> &)
0x18003fa88  test    eax, eax
0x18003fa8a  jns     short loc_18003FA9B
0x18003fa8c  cmp     eax, edi
0x18003fa8e  jz      short loc_18003FACC
0x18003fa90  cmp     eax, r13d
0x18003fa93  jnz     loc_18003FDF3
0x18003fa99  jmp     short loc_18003FACC
0x18003fa9b  mov     r8, [rbp+90h+var_108+8]
0x18003fa9f  mov     rdx, [rbp+90h+var_108]; Src
0x18003faa3  cmp     rdx, r8
0x18003faa6  jz      short loc_18003FACC
0x18003faa8  sub     r8, rdx; Size
0x18003faab  mov     rcx, [rbp+98h]; this
0x18003fab2  mov     rax, r8
0x18003fab5  sar     rax, 3
0x18003fab9  cmp     rax, 1
0x18003fabd  ja      loc_18003FF37
0x18003fac3  lea     rcx, [rbp+90h+var_80]; void *
0x18003fac7  call    memmove_0
0x18003facc  mov     rdx, rbx
0x18003facf  lea     rcx, [rsp+190h+var_158]
0x18003fad4  call    ??0?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@AEBV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &)
0x18003fad9  lea     rdx, [rsp+190h+var_150]
0x18003fade  mov     rcx, rax
0x18003fae1  call    ?GetSavedVmmCapabilitiesFromRepository@VmUtilities@@YAJV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@AEAV?$vector@_KV?$allocator@_K@std@@@std@@@Z; VmUtilities::GetSavedVmmCapabilitiesFromRepository(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>,std::vector<unsigned __int64> &)
0x18003fae6  test    eax, eax
0x18003fae8  jns     short loc_18003FAF9
0x18003faea  cmp     eax, edi
0x18003faec  jz      short loc_18003FB2D
0x18003faee  cmp     eax, r13d
0x18003faf1  jnz     loc_18003FE16
0x18003faf7  jmp     short loc_18003FB2D
0x18003faf9  mov     r8, [rsp+190h+var_150+8]
0x18003fafe  mov     rdx, [rsp+190h+var_150]; Src
0x18003fb03  cmp     rdx, r8
0x18003fb06  jz      short loc_18003FB2D
0x18003fb08  sub     r8, rdx; Size
0x18003fb0b  mov     rcx, [rbp+98h]; this
0x18003fb12  mov     rax, r8
0x18003fb15  sar     rax, 3
0x18003fb19  cmp     rax, 1
0x18003fb1d  ja      loc_18003FF4F
0x18003fb23  lea     rcx, [rbp+90h+var_80+8]; void *
0x18003fb27  call    memmove_0
0x18003fb2c  nop
0x18003fb2d  lea     rcx, [rsp+190h+var_150]
0x18003fb32  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
0x18003fb37  nop
0x18003fb38  lea     rcx, [rbp+90h+var_108]
0x18003fb3c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
0x18003fb41  mov     [rbp+90h+var_110], r12
0x18003fb45  mov     rcx, [rbx]
0x18003fb48  mov     rax, [rcx]
0x18003fb4b  lea     r8, [rbp+90h+var_110]
0x18003fb4f  lea     rdx, ?SAVED_VM_PHYSICAL_ADDRESS_WIDTH_XPATH@@3QBGB; "/savedVM/processor/physical_address_wid"...
0x18003fb56  mov     rax, [rax+78h]
0x18003fb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb5f  test    eax, eax
0x18003fb61  jns     short loc_18003FB72
0x18003fb63  cmp     eax, edi
0x18003fb65  jz      short loc_18003FB7A
0x18003fb67  cmp     eax, r13d
0x18003fb6a  jnz     loc_18003FE39
0x18003fb70  jmp     short loc_18003FB7A
0x18003fb72  mov     rax, [rbp+90h+var_110]
0x18003fb76  mov     qword ptr [rbp+90h+var_70], rax
0x18003fb7a  mov     [rsp+190h+var_138], r12d
0x18003fb7f  mov     rcx, [rbx]
0x18003fb82  mov     rax, [rcx]
0x18003fb85  lea     rdx, [rsp+190h+var_138]
0x18003fb8a  mov     rax, [rax+120h]
0x18003fb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb96  mov     rcx, [rbp+98h]; this
0x18003fb9d  test    eax, eax
0x18003fb9f  js      loc_18003FF67
0x18003fba5  cmp     [rsp+190h+var_138], 0B01h
0x18003fbad  jb      loc_18003FCC6
0x18003fbb3  xorps   xmm0, xmm0
0x18003fbb6  mov     [rsp+190h+Buf1], r12
0x18003fbbb  movdqu  xmmword ptr [rsp+190h+var_150], xmm0
0x18003fbc1  mov     [rsp+190h+var_140], r12
0x18003fbc6  mov     edx, 1
0x18003fbcb  lea     rcx, [rsp+190h+var_150]
0x18003fbd0  call    ?_Buy_nonzero@?$vector@_KV?$allocator@_K@std@@@std@@AEAAX_K@Z; std::vector<unsigned __int64>::_Buy_nonzero(unsigned __int64)
0x18003fbd5  mov     rdi, [rsp+190h+var_150]
0x18003fbda  mov     [rsp+190h+Buf2], r12
0x18003fbdf  mov     r8d, 8; Size
0x18003fbe5  lea     rdx, [rsp+190h+Buf2]; Buf2
0x18003fbea  lea     rcx, [rsp+190h+Buf1]; Buf1
0x18003fbef  call    memcmp_0
0x18003fbf4  test    eax, eax
0x18003fbf6  jnz     short loc_18003FBFF
0x18003fbf8  xor     eax, eax
0x18003fbfa  mov     [rdi], rax
0x18003fbfd  jmp     short loc_18003FC02
0x18003fbff  mov     [rdi], r12
0x18003fc02  add     rdi, 8
0x18003fc06  mov     [rsp+190h+var_150+8], rdi
0x18003fc0b  mov     [rsp+190h+Buf1], r12; int
0x18003fc10  lea     rcx, [rsp+190h+Buf1]
0x18003fc15  call    ??1?$_Tidy_guard@V?$vector@UVersion@Schema@@V?$allocator@UVersion@Schema@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<Schema::Version>>::~_Tidy_guard<std::vector<Schema::Version>>(void)
0x18003fc1a  nop
0x18003fc1b  mov     rcx, [rbx]
0x18003fc1e  mov     rax, [rcx]
0x18003fc21  mov     r8, [rsp+190h+var_150]
0x18003fc26  lea     rdx, ?SAVED_VM_ENLIGHTENMENT_MODIFICATIONS_XPATH@@3QBGB; "/savedVM/enlightenment_modifications"
0x18003fc2d  mov     rax, [rax+78h]
0x18003fc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc36  test    eax, eax
0x18003fc38  jns     short loc_18003FC4C
0x18003fc3a  cmp     eax, 80070002h
0x18003fc3f  jz      short loc_18003FC7D
0x18003fc41  cmp     eax, r13d
0x18003fc44  jnz     loc_18003FE5C
0x18003fc4a  jmp     short loc_18003FC7D
0x18003fc4c  mov     r8, [rsp+190h+var_150+8]
0x18003fc51  mov     rcx, [rbp+98h]; this
0x18003fc58  mov     rax, r8
0x18003fc5b  mov     rdx, [rsp+190h+var_150]; Src
0x18003fc60  sub     rax, rdx
0x18003fc63  sar     rax, 3
0x18003fc67  cmp     rax, 1
0x18003fc6b  ja      loc_18003FD4F
0x18003fc71  sub     r8, rdx; Size
0x18003fc74  lea     rcx, [rbp+90h+var_60]; void *
0x18003fc78  call    memmove_0
0x18003fc7d  mov     [rsp+190h+var_158], r12
0x18003fc82  mov     rcx, [rbx]
0x18003fc85  mov     rax, [rcx]
0x18003fc88  lea     r8, [rsp+190h+var_158]
  ... truncated ...
```
