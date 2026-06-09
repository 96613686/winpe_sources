# CEnumSubcategoryMembershipSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007dd90`
- end: `0x18007e46e`
- name: `?Next@CEnumSubcategoryMembershipSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumSubcategoryMembershipSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b1c`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x1800195e0`
- `0x18004f2dc`
- `0x1800569a8`
- `0x18005775c`
- `0x1800586f8`
- `0x18005c020`
- `0x18005df30`
- `0x18006acb8`
- `0x18007dd90`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007de8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e0ac`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e248`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e2c1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e3b5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007de8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e0ac`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e248`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e2c1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e3b5`

## string_xrefs

- `0x18007def9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007ddc9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007de94`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e0b5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e1a7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e254`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e275`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e2ca`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e322`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e369`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e3be`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumSubcategoryMembershipSection::Next(
        CEnumSubcategoryMembershipSection *this,
        unsigned int a2,
        struct IUnknown **a3,
        unsigned int *a4)
{
  unsigned __int64 v5; // rdi
  unsigned int *v7; // r13
  int v8; // r9d
  Windows::ErrorHandling::COM *v9; // r11
  unsigned int jj; // ebx
  int v11; // ebx
  int v12; // edx
  unsigned int i; // esi
  struct IUnknown *v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // r10
  unsigned __int64 v17; // rsi
  __int64 v18; // r15
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v21; // r10
  int v22; // ebx
  _QWORD *v23; // rcx
  unsigned __int64 v24; // r9
  __int64 v25; // r15
  __int64 v26; // rdx
  int v27; // edx
  __int64 v28; // rsi
  struct IUnknown *v29; // rcx
  __int64 v30; // r15
  int v31; // ebx
  unsigned __int16 **v32; // r8
  unsigned int v33; // eax
  int v34; // eax
  int v35; // r9d
  unsigned int v36; // eax
  __int64 v37; // r8
  int v38; // eax
  int v39; // r9d
  struct IUnknown **v40; // r13
  int v41; // ebx
  int v42; // eax
  int v43; // r9d
  __int64 n; // rsi
  struct IUnknown *v45; // rcx
  int v46; // edx
  __int64 m; // rsi
  struct IUnknown *v48; // rcx
  __int64 k; // rsi
  struct IUnknown *v50; // rcx
  __int64 j; // rsi
  struct IUnknown *v52; // rcx
  int v53; // edx
  __int64 ii; // rsi
  struct IUnknown *v55; // rcx
  __int64 (__fastcall ***v57)(_QWORD, GUID *, struct IUnknown **); // [rsp+28h] [rbp-49h] BYREF
  const char *v58; // [rsp+30h] [rbp-41h] BYREF
  int v59; // [rsp+38h] [rbp-39h]
  Windows::ErrorHandling::COM *v60; // [rsp+40h] [rbp-31h]
  __int128 v61; // [rsp+48h] [rbp-29h] BYREF
  __int64 v62; // [rsp+58h] [rbp-19h]
  __int64 v63; // [rsp+60h] [rbp-11h] BYREF
  __int64 v64; // [rsp+68h] [rbp-9h] BYREF
  __int128 v65; // [rsp+70h] [rbp-1h]
  char v66[8]; // [rsp+80h] [rbp+Fh] BYREF
  IsolationImplementation::Com *v67; // [rsp+88h] [rbp+17h]
  unsigned int v69; // [rsp+E0h] [rbp+6Fh] BYREF
  unsigned int *v70; // [rsp+F0h] [rbp+7Fh]

  v70 = a4;
  v5 = a2;
  LODWORD(v60) = -2147023537;
  v62 = 0;
  v58 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v63 = 0;
  v7 = a4;
  v61 = 0;
  IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(a3, a2, &v63);
  if ( v7 )
    *v7 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    v59 = 21066;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 21067;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x524C, -2147467261, v8);
    goto LABEL_10;
  }
  v11 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned long,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>>::EnlargeNoPreserve(
                     &v61,
                     &v69,
                     (unsigned int)v5);
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5250,
      v11,
      (unsigned int)v57);
    jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v11, v12);
    for ( i = 0; i < (unsigned int)v5; ++i )
    {
      v14 = a3[i];
      if ( v14 )
        ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
    }
    goto LABEL_10;
  }
  v15 = HIDWORD(v62);
  v16 = *((_QWORD *)this + 3);
  if ( HIDWORD(v62) < (unsigned int)v62 )
    v15 = v62;
  v17 = 0;
  v18 = *((_QWORD *)&v61 + 1);
  v69 = v15;
  HIDWORD(v62) = v15;
  v58 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
  LODWORD(v60) = -1073741595;
  v64 = 0;
  v65 = 0;
  if ( *((_QWORD *)&v61 + 1) )
  {
    v19 = 0;
    if ( (_DWORD)v5 )
    {
      do
      {
        v20 = v19++;
        v20 *= 32LL;
        *(_QWORD *)(v20 + v18) = 0;
        *(_QWORD *)(v20 + v18 + 8) = 0;
        *(_QWORD *)(v20 + v18 + 16) = 0;
        *(_DWORD *)(v20 + v18 + 24) = -1;
      }
      while ( v19 < v5 );
    }
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(v16) )
  {
    v59 = 1143;
    goto LABEL_47;
  }
  if ( !v18 && (_DWORD)v5 )
  {
    v59 = 1144;
LABEL_47:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v58);
LABEL_48:
    v22 = (int)v60;
    goto LABEL_49;
  }
  v22 = Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(
          &v64,
          v21);
  if ( v22 < 0 )
  {
    if ( !*((_QWORD *)&v65 + 1) )
      goto LABEL_49;
    goto LABEL_31;
  }
  v23 = (_QWORD *)v65;
  if ( *(_QWORD *)(v65 + 40) > *(_QWORD *)(v65 + 32) )
  {
    v59 = 1149;
    if ( *((_QWORD *)&v65 + 1) )
      (*(void (__fastcall **)(__int64))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                      + 48))(v64);
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    goto LABEL_48;
  }
  if ( (_DWORD)v5 )
  {
    while ( 1 )
    {
      v24 = v23[5];
      if ( v24 >= v23[4] )
        break;
      v25 = 32 * v17 + v18;
      v22 = pcm_Fetch(v23[1], *(unsigned int *)(v23[6] + 4 * v24), v25);
      if ( v22 < 0 )
      {
        if ( *((_QWORD *)&v65 + 1) )
          (*(void (__fastcall **)(__int64))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                          + 48))(v64);
        v17 = 0;
        goto LABEL_49;
      }
      v26 = v65;
      ++v17;
      *(_DWORD *)(v25 + 24) = *(_DWORD *)(*(_QWORD *)(v65 + 56) + 4LL * *(_QWORD *)(v65 + 40));
      ++*(_QWORD *)(v26 + 40);
      if ( v17 >= v5 )
        break;
      v23 = (_QWORD *)v65;
      v18 = *((_QWORD *)&v61 + 1);
    }
  }
  v22 = 0;
  if ( *((_QWORD *)&v65 + 1) )
LABEL_31:
    (*(void (__fastcall **)(__int64))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                    + 48))(v64);
LABEL_49:
  if ( v22 >= 0 )
  {
    v30 = 0;
    if ( v17 )
    {
      while ( 1 )
      {
        v57 = 0;
        v63 = 0;
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::Allocate(
                           &v57,
                           v66);
        if ( v31 < 0 )
          break;
        v33 = v69;
        if ( v69 < (unsigned int)v62 )
          v33 = v62;
        v69 = v33;
        HIDWORD(v62) = v33;
        v67 = (IsolationImplementation::Com *)(*((_QWORD *)&v61 + 1) + 32LL * (unsigned int)v30);
        v34 = IsolationImplementation::Com::CopyOut(v67, (const struct _LUTF8_STRING *)&v63, v32);
        jj = v34;
        if ( v34 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x525A,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>(&v57);
          for ( j = 0; (unsigned int)j < (unsigned int)v5; j = (unsigned int)(j + 1) )
          {
            v52 = a3[j];
            if ( v52 )
              ((void (__fastcall *)(struct IUnknown *))v52->lpVtbl->Release)(v52);
          }
          goto LABEL_10;
        }
        v36 = v69;
        if ( v69 < (unsigned int)v62 )
          v36 = v62;
        v37 = *((unsigned int *)v67 + 6);
        v69 = v36;
        HIDWORD(v62) = v36;
        v38 = CSubcategoryMembershipEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x525B,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>(&v57);
          for ( k = 0; (unsigned int)k < (unsigned int)v5; k = (unsigned int)(k + 1) )
          {
            v50 = a3[k];
            if ( v50 )
              ((void (__fastcall *)(struct IUnknown *))v50->lpVtbl->Release)(v50);
          }
          goto LABEL_10;
        }
        LODWORD(v60) = -1073741595;
        v58 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
        if ( (unsigned int)v30 < (unsigned int)v5 )
        {
          v40 = &a3[v30];
          v41 = 0;
        }
        else
        {
          v40 = 0;
          v59 = 40;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
            &v58,
            &v58);
          v41 = (int)v60;
        }
        if ( v41 < 0 )
        {
          if ( v41 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x525C,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>(&v57);
          for ( m = 0; (unsigned int)m < (unsigned int)v5; m = (unsigned int)(m + 1) )
          {
            v48 = a3[m];
            if ( v48 )
              ((void (__fastcall *)(struct IUnknown *))v48->lpVtbl->Release)(v48);
          }
          goto LABEL_10;
        }
        v42 = (**v57)(v57, &GUID_00000000_0000_0000_c000_000000000046, v40);
        jj = v42;
        if ( v42 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x525D,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>(&v57);
        v30 = (unsigned int)(v30 + 1);
        if ( (unsigned int)v30 >= v17 )
        {
          v7 = v70;
          goto LABEL_72;
        }
      }
      if ( v31 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x5259,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>(&v57);
      for ( ii = 0; (unsigned int)ii < (unsigned int)v5; ii = (unsigned int)(ii + 1) )
      {
        v55 = a3[ii];
        if ( v55 )
          ((void (__fastcall *)(struct IUnknown *))v55->lpVtbl->Release)(v55);
      }
      goto LABEL_10;
    }
LABEL_72:
    if ( v7 )
    {
      if ( v17 > 0xFFFFFFFF )
      {
        jj = -805306219;
        if ( g_HRESULT_to_break_on == -805306219 )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"HR originated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
          (const char *)0x5265,
          -805306219,
          (unsigned int)v57);
        goto LABEL_10;
      }
      *v7 = v17;
    }
    jj = v17 != v5;
  }
  else
  {
    if ( v22 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5251,
      v22,
      (unsigned int)v57);
    v28 = 0;
    for ( jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v22,
                 v27); (unsigned int)v28 < (unsigned int)v5; v28 = (unsigned int)(v28 + 1) )
    {
      v29 = a3[v28];
      if ( v29 )
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
    }
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
  return jj;
}

```

## disassembly

```asm
0x18007dd90  mov     rax, rsp
0x18007dd93  mov     [rax+18h], rbx
0x18007dd97  mov     [rax+20h], r9
0x18007dd9b  mov     [rax+8], rcx
0x18007dd9f  push    rbp
0x18007dda0  push    rsi
0x18007dda1  push    rdi
0x18007dda2  push    r12
0x18007dda4  push    r13
0x18007dda6  push    r14
0x18007dda8  push    r15
0x18007ddaa  lea     rbp, [rax-5Fh]
0x18007ddae  sub     rsp, 90h
0x18007ddb5  mov     r14, r8
0x18007ddb8  mov     edi, edx
0x18007ddba  mov     rsi, rcx
0x18007ddbd  mov     edx, edx
0x18007ddbf  xor     r15d, r15d
0x18007ddc2  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007ddc9  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007ddd0  mov     [rbp+57h+var_70], r15
0x18007ddd4  xorps   xmm0, xmm0
0x18007ddd7  mov     [rbp+57h+var_98], r11
0x18007dddb  mov     rcx, r14
0x18007ddde  mov     [rbp+57h+var_68], r15
0x18007dde2  lea     r8, [rbp+57h+var_68]
0x18007dde6  mov     r13, r9
0x18007dde9  movdqu  [rbp+57h+var_80], xmm0
0x18007ddee  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007ddf3  test    r13, r13
0x18007ddf6  jz      short loc_18007DDFC
0x18007ddf8  mov     [r13+0], r15d
0x18007ddfc  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007de03  test    rdx, rdx
0x18007de06  jz      loc_18007E431
0x18007de0c  mov     rcx, [rsi+18h]
0x18007de10  call    RtlIsTypeSafeHandleValid
0x18007de15  test    al, al
0x18007de17  jz      loc_18007E431
0x18007de1d  test    r14, r14
0x18007de20  jnz     short loc_18007DE40
0x18007de22  lea     rcx, [rbp+57h+var_98]
0x18007de26  mov     [rbp+57h+var_90], 524Bh
0x18007de2d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007de32  lea     rcx, [rbp+57h+var_80]
0x18007de36  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007de3b  jmp     loc_18007E44E
0x18007de40  test    r13, r13
0x18007de43  jnz     short loc_18007DE6D
0x18007de45  cmp     edi, 1
0x18007de48  jz      short loc_18007DE6D
0x18007de4a  mov     ebx, 80004003h
0x18007de4f  mov     edx, 524Ch; char *
0x18007de54  mov     r8d, ebx; int
0x18007de57  mov     rcx, r11; this
0x18007de5a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007de5f  lea     rcx, [rbp+57h+var_80]
0x18007de63  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007de68  jmp     loc_18007E451
0x18007de6d  mov     r8d, edi
0x18007de70  lea     rdx, [rbp+57h+arg_8]
0x18007de74  lea     rcx, [rbp+57h+var_80]
0x18007de78  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007de7d  mov     ebx, [rax]
0x18007de7f  test    ebx, ebx
0x18007de81  jns     short loc_18007DEDC
0x18007de83  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007de89  jnz     short loc_18007DE91
0x18007de8b  call    cs:__imp_DebugBreak
0x18007de91  mov     r9d, ebx; int
0x18007de94  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007de9b  mov     r8d, 5250h; char *
0x18007dea1  lea     rcx, aStatusPropagat; "Status propagated"
0x18007dea8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007dead  mov     ecx, ebx; this
0x18007deaf  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007deb4  mov     ebx, eax
0x18007deb6  mov     esi, r15d
0x18007deb9  test    edi, edi
0x18007debb  jz      short loc_18007DE5F
0x18007debd  mov     ecx, esi
0x18007debf  mov     rcx, [r14+rcx*8]
0x18007dec3  test    rcx, rcx
0x18007dec6  jz      short loc_18007DED4
0x18007dec8  mov     rdx, [rcx]
0x18007decb  mov     rax, [rdx+10h]
0x18007decf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ded4  inc     esi
0x18007ded6  cmp     esi, edi
0x18007ded8  jb      short loc_18007DEBD
0x18007deda  jmp     short loc_18007DE5F
0x18007dedc  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007dedf  xorps   xmm0, xmm0
0x18007dee2  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007dee5  mov     r10, [rsi+18h]
0x18007dee9  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007deed  xor     esi, esi
0x18007deef  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007def3  mov     [rbp+57h+arg_8], eax
0x18007def6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007def9  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007df00  mov     [rbp+57h+var_98], rax
0x18007df04  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007df0b  mov     [rbp+57h+var_60], rsi
0x18007df0f  movdqu  [rbp+57h+var_58], xmm0
0x18007df14  test    r15, r15
0x18007df17  jz      short loc_18007DF45
0x18007df19  mov     ecx, esi
0x18007df1b  test    edi, edi
0x18007df1d  jz      short loc_18007DF45
0x18007df1f  mov     rax, rcx
0x18007df22  inc     rcx
0x18007df25  shl     rax, 5
0x18007df29  mov     [rax+r15], rsi
0x18007df2d  mov     [rax+r15+8], rsi
0x18007df32  mov     [rax+r15+10h], rsi
0x18007df37  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007df40  cmp     rcx, rdi
0x18007df43  jb      short loc_18007DF1F
0x18007df45  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007df4c  test    rdx, rdx
0x18007df4f  jz      loc_18007E08D
0x18007df55  mov     rcx, r10
0x18007df58  call    RtlIsTypeSafeHandleValid
0x18007df5d  test    al, al
0x18007df5f  jz      loc_18007E08D
0x18007df65  test    r15, r15
0x18007df68  jnz     short loc_18007DF7A
0x18007df6a  test    edi, edi
0x18007df6c  jz      short loc_18007DF7A
0x18007df6e  mov     [rbp+57h+var_90], 478h
0x18007df75  jmp     loc_18007E094
0x18007df7a  mov     rdx, r10
0x18007df7d  lea     rcx, [rbp+57h+var_60]
0x18007df81  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007df86  mov     ebx, eax
0x18007df88  test    eax, eax
0x18007df8a  jns     short loc_18007DFB2
0x18007df8c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007df90  test    rdx, rdx
0x18007df93  jz      loc_18007E0A0
0x18007df99  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007dfa0  mov     rax, [rcx+30h]
0x18007dfa4  mov     rcx, [rbp+57h+var_60]
0x18007dfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dfad  jmp     loc_18007E0A0
0x18007dfb2  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007dfb6  mov     rax, [rcx+20h]
0x18007dfba  cmp     [rcx+28h], rax
0x18007dfbe  jbe     short loc_18007DFF6
0x18007dfc0  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007dfc4  mov     [rbp+57h+var_90], 47Dh
0x18007dfcb  test    rdx, rdx
0x18007dfce  jz      short loc_18007DFE4
0x18007dfd0  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007dfd7  mov     rcx, [rbp+57h+var_60]
0x18007dfdb  mov     rax, [rax+30h]
0x18007dfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dfe4  lea     rdx, [rbp+57h+var_98]
0x18007dfe8  lea     rcx, [rbp+57h+var_98]
0x18007dfec  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007dff1  jmp     loc_18007E09D
0x18007dff6  test    edi, edi
0x18007dff8  jz      short loc_18007E072
0x18007dffa  mov     r9, [rcx+28h]
0x18007dffe  cmp     r9, [rcx+20h]
0x18007e002  jnb     short loc_18007E072
0x18007e004  mov     rdx, [rcx+30h]
0x18007e008  mov     rax, rsi
0x18007e00b  mov     rcx, [rcx+8]
0x18007e00f  shl     rax, 5
0x18007e013  add     r15, rax
0x18007e016  mov     edx, [rdx+r9*4]
0x18007e01a  mov     r8, r15
0x18007e01d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007e022  mov     ebx, eax
0x18007e024  test    eax, eax
0x18007e026  js      short loc_18007E051
0x18007e028  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007e02c  inc     rsi
0x18007e02f  mov     rcx, [rdx+28h]
0x18007e033  mov     rax, [rdx+38h]
0x18007e037  mov     ecx, [rax+rcx*4]
0x18007e03a  mov     [r15+18h], ecx
0x18007e03e  inc     qword ptr [rdx+28h]
0x18007e042  cmp     rsi, rdi
0x18007e045  jnb     short loc_18007E072
0x18007e047  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007e04b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007e04f  jmp     short loc_18007DFFA
0x18007e051  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007e055  test    rdx, rdx
0x18007e058  jz      short loc_18007E06E
0x18007e05a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e061  mov     rcx, [rbp+57h+var_60]
0x18007e065  mov     rax, [rax+30h]
0x18007e069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e06e  xor     esi, esi
0x18007e070  jmp     short loc_18007E0A0
0x18007e072  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007e076  xor     ebx, ebx
0x18007e078  test    rdx, rdx
0x18007e07b  jz      short loc_18007E0A0
0x18007e07d  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e084  mov     rax, [rax+30h]
0x18007e088  jmp     loc_18007DFA4
0x18007e08d  mov     [rbp+57h+var_90], 477h
0x18007e094  lea     rcx, [rbp+57h+var_98]
0x18007e098  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007e09d  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007e0a0  test    ebx, ebx
0x18007e0a2  jns     short loc_18007E101
0x18007e0a4  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007e0aa  jnz     short loc_18007E0B2
0x18007e0ac  call    cs:__imp_DebugBreak
0x18007e0b2  mov     r9d, ebx; int
0x18007e0b5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007e0bc  mov     r8d, 5251h; char *
0x18007e0c2  lea     rcx, aStatusPropagat; "Status propagated"
0x18007e0c9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007e0ce  mov     ecx, ebx; this
0x18007e0d0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007e0d5  xor     esi, esi
0x18007e0d7  mov     ebx, eax
0x18007e0d9  test    edi, edi
0x18007e0db  jz      loc_18007DE5F
0x18007e0e1  mov     rcx, [r14+rsi*8]
0x18007e0e5  test    rcx, rcx
0x18007e0e8  jz      short loc_18007E0F6
0x18007e0ea  mov     rax, [rcx]
0x18007e0ed  mov     rax, [rax+10h]
0x18007e0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e0f6  inc     esi
0x18007e0f8  cmp     esi, edi
0x18007e0fa  jb      short loc_18007E0E1
0x18007e0fc  jmp     loc_18007DE5F
0x18007e101  xor     r15d, r15d
0x18007e104  test    rsi, rsi
0x18007e107  jz      loc_18007E224
0x18007e10d  lea     rdx, [rbp+57h+var_48]
0x18007e111  mov     [rbp+57h+var_A0], 0
0x18007e119  lea     rcx, [rbp+57h+var_A0]
0x18007e11d  mov     [rbp+57h+var_68], 0
0x18007e125  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCSubcategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CSubcategoryMembershipEntry>>>::Allocate(void)
0x18007e12a  mov     ebx, [rax]
0x18007e12c  test    ebx, ebx
0x18007e12e  js      loc_18007E3AD
0x18007e134  mov     eax, [rbp+57h+arg_8]
0x18007e137  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007e13b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007e13e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007e142  mov     [rbp+57h+arg_8], eax
0x18007e145  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007e148  mov     eax, r15d
0x18007e14b  shl     rax, 5
0x18007e14f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007e153  mov     rcx, rax; this
0x18007e156  mov     [rbp+57h+var_40], rax
0x18007e15a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007e15f  mov     ebx, eax
0x18007e161  test    eax, eax
0x18007e163  js      loc_18007E366
0x18007e169  mov     eax, [rbp+57h+arg_8]
0x18007e16c  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007e16f  mov     r8, [rbp+57h+var_40]
0x18007e173  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007e177  mov     r9, [rbp+57h+var_68]
0x18007e17b  mov     rcx, [rbp+57h+var_A0]
0x18007e17f  mov     r8d, [r8+18h]
0x18007e183  mov     [rbp+57h+arg_8], eax
0x18007e186  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007e189  mov     rax, [rbp+57h+arg_0]
0x18007e18d  mov     rdx, [rax+10h]
0x18007e191  call    ?Initialize@CSubcategoryMembershipEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CSubcategoryMembershipEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007e196  mov     ebx, eax
0x18007e198  test    eax, eax
0x18007e19a  js      loc_18007E31F
0x18007e1a0  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007e1a7  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007e1ae  mov     [rbp+57h+var_98], rax
0x18007e1b2  cmp     r15d, edi
0x18007e1b5  jb      short loc_18007E1D3
0x18007e1b7  xor     r13d, r13d
0x18007e1ba  mov     [rbp+57h+var_90], 28h ; '('
0x18007e1c1  lea     rdx, [rbp+57h+var_98]
0x18007e1c5  lea     rcx, [rbp+57h+var_98]
0x18007e1c9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007e1ce  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007e1d1  jmp     short loc_18007E1D9
0x18007e1d3  lea     r13, [r14+r15*8]
0x18007e1d7  xor     ebx, ebx
0x18007e1d9  test    ebx, ebx
0x18007e1db  js      loc_18007E2B9
0x18007e1e1  mov     rcx, [rbp+57h+var_A0]
0x18007e1e5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007e1ec  mov     r8, r13
0x18007e1ef  mov     rax, [rcx]
0x18007e1f2  mov     rax, [rax]
0x18007e1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e1fa  mov     ebx, eax
  ... truncated ...
```
