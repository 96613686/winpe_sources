# CEnumEventMapSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180079b10`
- end: `0x18007a1ee`
- name: `?Next@CEnumEventMapSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumEventMapSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180058228`
- `0x18005b2e0`
- `0x18005df30`
- `0x180069a10`
- `0x180079b10`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079c0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079e2c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079fc8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a041`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a135`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079c0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079e2c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079fc8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a041`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a135`

## string_xrefs

- `0x180079c79`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180079b49`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079c14`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079e35`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079f27`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079fd4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079ff5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a04a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a0a2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a0e9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a13e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumEventMapSection::Next(
        CEnumEventMapSection *this,
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
    v59 = 22749;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 22750;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x58DF, -2147467261, v8);
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
      (const char *)0x58E3,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::Allocate(
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
            (const char *)0x58ED,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>(&v57);
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
        v38 = CEventMapEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x58EE,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>(&v57);
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
            (const char *)0x58EF,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>(&v57);
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
            (const char *)0x58F0,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>(&v57);
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
        (const char *)0x58EC,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>(&v57);
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
          (const char *)0x58F8,
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
      (const char *)0x58E4,
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
0x180079b10  mov     rax, rsp
0x180079b13  mov     [rax+18h], rbx
0x180079b17  mov     [rax+20h], r9
0x180079b1b  mov     [rax+8], rcx
0x180079b1f  push    rbp
0x180079b20  push    rsi
0x180079b21  push    rdi
0x180079b22  push    r12
0x180079b24  push    r13
0x180079b26  push    r14
0x180079b28  push    r15
0x180079b2a  lea     rbp, [rax-5Fh]
0x180079b2e  sub     rsp, 90h
0x180079b35  mov     r14, r8
0x180079b38  mov     edi, edx
0x180079b3a  mov     rsi, rcx
0x180079b3d  mov     edx, edx
0x180079b3f  xor     r15d, r15d
0x180079b42  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x180079b49  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180079b50  mov     [rbp+57h+var_70], r15
0x180079b54  xorps   xmm0, xmm0
0x180079b57  mov     [rbp+57h+var_98], r11
0x180079b5b  mov     rcx, r14
0x180079b5e  mov     [rbp+57h+var_68], r15
0x180079b62  lea     r8, [rbp+57h+var_68]
0x180079b66  mov     r13, r9
0x180079b69  movdqu  [rbp+57h+var_80], xmm0
0x180079b6e  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x180079b73  test    r13, r13
0x180079b76  jz      short loc_180079B7C
0x180079b78  mov     [r13+0], r15d
0x180079b7c  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079b83  test    rdx, rdx
0x180079b86  jz      loc_18007A1B1
0x180079b8c  mov     rcx, [rsi+18h]
0x180079b90  call    RtlIsTypeSafeHandleValid
0x180079b95  test    al, al
0x180079b97  jz      loc_18007A1B1
0x180079b9d  test    r14, r14
0x180079ba0  jnz     short loc_180079BC0
0x180079ba2  lea     rcx, [rbp+57h+var_98]
0x180079ba6  mov     [rbp+57h+var_90], 58DEh
0x180079bad  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180079bb2  lea     rcx, [rbp+57h+var_80]
0x180079bb6  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180079bbb  jmp     loc_18007A1CE
0x180079bc0  test    r13, r13
0x180079bc3  jnz     short loc_180079BED
0x180079bc5  cmp     edi, 1
0x180079bc8  jz      short loc_180079BED
0x180079bca  mov     ebx, 80004003h
0x180079bcf  mov     edx, 58DFh; char *
0x180079bd4  mov     r8d, ebx; int
0x180079bd7  mov     rcx, r11; this
0x180079bda  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180079bdf  lea     rcx, [rbp+57h+var_80]
0x180079be3  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180079be8  jmp     loc_18007A1D1
0x180079bed  mov     r8d, edi
0x180079bf0  lea     rdx, [rbp+57h+arg_8]
0x180079bf4  lea     rcx, [rbp+57h+var_80]
0x180079bf8  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180079bfd  mov     ebx, [rax]
0x180079bff  test    ebx, ebx
0x180079c01  jns     short loc_180079C5C
0x180079c03  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180079c09  jnz     short loc_180079C11
0x180079c0b  call    cs:__imp_DebugBreak
0x180079c11  mov     r9d, ebx; int
0x180079c14  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180079c1b  mov     r8d, 58E3h; char *
0x180079c21  lea     rcx, aStatusPropagat; "Status propagated"
0x180079c28  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180079c2d  mov     ecx, ebx; this
0x180079c2f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180079c34  mov     ebx, eax
0x180079c36  mov     esi, r15d
0x180079c39  test    edi, edi
0x180079c3b  jz      short loc_180079BDF
0x180079c3d  mov     ecx, esi
0x180079c3f  mov     rcx, [r14+rcx*8]
0x180079c43  test    rcx, rcx
0x180079c46  jz      short loc_180079C54
0x180079c48  mov     rdx, [rcx]
0x180079c4b  mov     rax, [rdx+10h]
0x180079c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c54  inc     esi
0x180079c56  cmp     esi, edi
0x180079c58  jb      short loc_180079C3D
0x180079c5a  jmp     short loc_180079BDF
0x180079c5c  mov     eax, dword ptr [rbp+57h+var_70+4]
0x180079c5f  xorps   xmm0, xmm0
0x180079c62  cmp     eax, dword ptr [rbp+57h+var_70]
0x180079c65  mov     r10, [rsi+18h]
0x180079c69  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180079c6d  xor     esi, esi
0x180079c6f  mov     r15, qword ptr [rbp+57h+var_80+8]
0x180079c73  mov     [rbp+57h+arg_8], eax
0x180079c76  mov     dword ptr [rbp+57h+var_70+4], eax
0x180079c79  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180079c80  mov     [rbp+57h+var_98], rax
0x180079c84  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x180079c8b  mov     [rbp+57h+var_60], rsi
0x180079c8f  movdqu  [rbp+57h+var_58], xmm0
0x180079c94  test    r15, r15
0x180079c97  jz      short loc_180079CC5
0x180079c99  mov     ecx, esi
0x180079c9b  test    edi, edi
0x180079c9d  jz      short loc_180079CC5
0x180079c9f  mov     rax, rcx
0x180079ca2  inc     rcx
0x180079ca5  shl     rax, 5
0x180079ca9  mov     [rax+r15], rsi
0x180079cad  mov     [rax+r15+8], rsi
0x180079cb2  mov     [rax+r15+10h], rsi
0x180079cb7  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x180079cc0  cmp     rcx, rdi
0x180079cc3  jb      short loc_180079C9F
0x180079cc5  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079ccc  test    rdx, rdx
0x180079ccf  jz      loc_180079E0D
0x180079cd5  mov     rcx, r10
0x180079cd8  call    RtlIsTypeSafeHandleValid
0x180079cdd  test    al, al
0x180079cdf  jz      loc_180079E0D
0x180079ce5  test    r15, r15
0x180079ce8  jnz     short loc_180079CFA
0x180079cea  test    edi, edi
0x180079cec  jz      short loc_180079CFA
0x180079cee  mov     [rbp+57h+var_90], 478h
0x180079cf5  jmp     loc_180079E14
0x180079cfa  mov     rdx, r10
0x180079cfd  lea     rcx, [rbp+57h+var_60]
0x180079d01  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x180079d06  mov     ebx, eax
0x180079d08  test    eax, eax
0x180079d0a  jns     short loc_180079D32
0x180079d0c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180079d10  test    rdx, rdx
0x180079d13  jz      loc_180079E20
0x180079d19  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079d20  mov     rax, [rcx+30h]
0x180079d24  mov     rcx, [rbp+57h+var_60]
0x180079d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d2d  jmp     loc_180079E20
0x180079d32  mov     rcx, qword ptr [rbp+57h+var_58]
0x180079d36  mov     rax, [rcx+20h]
0x180079d3a  cmp     [rcx+28h], rax
0x180079d3e  jbe     short loc_180079D76
0x180079d40  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180079d44  mov     [rbp+57h+var_90], 47Dh
0x180079d4b  test    rdx, rdx
0x180079d4e  jz      short loc_180079D64
0x180079d50  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079d57  mov     rcx, [rbp+57h+var_60]
0x180079d5b  mov     rax, [rax+30h]
0x180079d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d64  lea     rdx, [rbp+57h+var_98]
0x180079d68  lea     rcx, [rbp+57h+var_98]
0x180079d6c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180079d71  jmp     loc_180079E1D
0x180079d76  test    edi, edi
0x180079d78  jz      short loc_180079DF2
0x180079d7a  mov     r9, [rcx+28h]
0x180079d7e  cmp     r9, [rcx+20h]
0x180079d82  jnb     short loc_180079DF2
0x180079d84  mov     rdx, [rcx+30h]
0x180079d88  mov     rax, rsi
0x180079d8b  mov     rcx, [rcx+8]
0x180079d8f  shl     rax, 5
0x180079d93  add     r15, rax
0x180079d96  mov     edx, [rdx+r9*4]
0x180079d9a  mov     r8, r15
0x180079d9d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x180079da2  mov     ebx, eax
0x180079da4  test    eax, eax
0x180079da6  js      short loc_180079DD1
0x180079da8  mov     rdx, qword ptr [rbp+57h+var_58]
0x180079dac  inc     rsi
0x180079daf  mov     rcx, [rdx+28h]
0x180079db3  mov     rax, [rdx+38h]
0x180079db7  mov     ecx, [rax+rcx*4]
0x180079dba  mov     [r15+18h], ecx
0x180079dbe  inc     qword ptr [rdx+28h]
0x180079dc2  cmp     rsi, rdi
0x180079dc5  jnb     short loc_180079DF2
0x180079dc7  mov     rcx, qword ptr [rbp+57h+var_58]
0x180079dcb  mov     r15, qword ptr [rbp+57h+var_80+8]
0x180079dcf  jmp     short loc_180079D7A
0x180079dd1  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180079dd5  test    rdx, rdx
0x180079dd8  jz      short loc_180079DEE
0x180079dda  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079de1  mov     rcx, [rbp+57h+var_60]
0x180079de5  mov     rax, [rax+30h]
0x180079de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079dee  xor     esi, esi
0x180079df0  jmp     short loc_180079E20
0x180079df2  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180079df6  xor     ebx, ebx
0x180079df8  test    rdx, rdx
0x180079dfb  jz      short loc_180079E20
0x180079dfd  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079e04  mov     rax, [rax+30h]
0x180079e08  jmp     loc_180079D24
0x180079e0d  mov     [rbp+57h+var_90], 477h
0x180079e14  lea     rcx, [rbp+57h+var_98]
0x180079e18  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180079e1d  mov     ebx, dword ptr [rbp+57h+var_88]
0x180079e20  test    ebx, ebx
0x180079e22  jns     short loc_180079E81
0x180079e24  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180079e2a  jnz     short loc_180079E32
0x180079e2c  call    cs:__imp_DebugBreak
0x180079e32  mov     r9d, ebx; int
0x180079e35  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180079e3c  mov     r8d, 58E4h; char *
0x180079e42  lea     rcx, aStatusPropagat; "Status propagated"
0x180079e49  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180079e4e  mov     ecx, ebx; this
0x180079e50  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180079e55  xor     esi, esi
0x180079e57  mov     ebx, eax
0x180079e59  test    edi, edi
0x180079e5b  jz      loc_180079BDF
0x180079e61  mov     rcx, [r14+rsi*8]
0x180079e65  test    rcx, rcx
0x180079e68  jz      short loc_180079E76
0x180079e6a  mov     rax, [rcx]
0x180079e6d  mov     rax, [rax+10h]
0x180079e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e76  inc     esi
0x180079e78  cmp     esi, edi
0x180079e7a  jb      short loc_180079E61
0x180079e7c  jmp     loc_180079BDF
0x180079e81  xor     r15d, r15d
0x180079e84  test    rsi, rsi
0x180079e87  jz      loc_180079FA4
0x180079e8d  lea     rdx, [rbp+57h+var_48]
0x180079e91  mov     [rbp+57h+var_A0], 0
0x180079e99  lea     rcx, [rbp+57h+var_A0]
0x180079e9d  mov     [rbp+57h+var_68], 0
0x180079ea5  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventMapEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventMapEntry>>>::Allocate(void)
0x180079eaa  mov     ebx, [rax]
0x180079eac  test    ebx, ebx
0x180079eae  js      loc_18007A12D
0x180079eb4  mov     eax, [rbp+57h+arg_8]
0x180079eb7  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x180079ebb  cmp     eax, dword ptr [rbp+57h+var_70]
0x180079ebe  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180079ec2  mov     [rbp+57h+arg_8], eax
0x180079ec5  mov     dword ptr [rbp+57h+var_70+4], eax
0x180079ec8  mov     eax, r15d
0x180079ecb  shl     rax, 5
0x180079ecf  add     rax, qword ptr [rbp+57h+var_80+8]
0x180079ed3  mov     rcx, rax; this
0x180079ed6  mov     [rbp+57h+var_40], rax
0x180079eda  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x180079edf  mov     ebx, eax
0x180079ee1  test    eax, eax
0x180079ee3  js      loc_18007A0E6
0x180079ee9  mov     eax, [rbp+57h+arg_8]
0x180079eec  cmp     eax, dword ptr [rbp+57h+var_70]
0x180079eef  mov     r8, [rbp+57h+var_40]
0x180079ef3  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180079ef7  mov     r9, [rbp+57h+var_68]
0x180079efb  mov     rcx, [rbp+57h+var_A0]
0x180079eff  mov     r8d, [r8+18h]
0x180079f03  mov     [rbp+57h+arg_8], eax
0x180079f06  mov     dword ptr [rbp+57h+var_70+4], eax
0x180079f09  mov     rax, [rbp+57h+arg_0]
0x180079f0d  mov     rdx, [rax+10h]
0x180079f11  call    ?Initialize@CEventMapEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CEventMapEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x180079f16  mov     ebx, eax
0x180079f18  test    eax, eax
0x180079f1a  js      loc_18007A09F
0x180079f20  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x180079f27  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180079f2e  mov     [rbp+57h+var_98], rax
0x180079f32  cmp     r15d, edi
0x180079f35  jb      short loc_180079F53
0x180079f37  xor     r13d, r13d
0x180079f3a  mov     [rbp+57h+var_90], 28h ; '('
0x180079f41  lea     rdx, [rbp+57h+var_98]
0x180079f45  lea     rcx, [rbp+57h+var_98]
0x180079f49  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180079f4e  mov     ebx, dword ptr [rbp+57h+var_88]
0x180079f51  jmp     short loc_180079F59
0x180079f53  lea     r13, [r14+r15*8]
0x180079f57  xor     ebx, ebx
0x180079f59  test    ebx, ebx
0x180079f5b  js      loc_18007A039
0x180079f61  mov     rcx, [rbp+57h+var_A0]
0x180079f65  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180079f6c  mov     r8, r13
0x180079f6f  mov     rax, [rcx]
0x180079f72  mov     rax, [rax]
0x180079f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f7a  mov     ebx, eax
  ... truncated ...
```
