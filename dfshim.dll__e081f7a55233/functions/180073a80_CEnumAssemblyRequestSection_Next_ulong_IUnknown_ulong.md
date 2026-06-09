# CEnumAssemblyRequestSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180073a80`
- end: `0x18007415e`
- name: `?Next@CEnumAssemblyRequestSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumAssemblyRequestSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180057b98`
- `0x18005a278`
- `0x18005df30`
- `0x180066b30`
- `0x180073a80`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073b7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073d9c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073f38`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073fb1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800740a5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073b7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073d9c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073f38`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180073fb1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800740a5`

## string_xrefs

- `0x180073be9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180073ab9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073b84`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073da5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073e97`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073f44`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073f65`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073fba`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180074012`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180074059`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800740ae`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumAssemblyRequestSection::Next(
        CEnumAssemblyRequestSection *this,
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
    v59 = 22301;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 22302;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x571F, -2147467261, v8);
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
      (const char *)0x5723,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::Allocate(
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
            (const char *)0x572D,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>(&v57);
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
        v38 = CAssemblyRequestEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x572E,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>(&v57);
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
            (const char *)0x572F,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>(&v57);
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
            (const char *)0x5730,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>(&v57);
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
        (const char *)0x572C,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>(&v57);
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
          (const char *)0x5738,
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
      (const char *)0x5724,
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
0x180073a80  mov     rax, rsp
0x180073a83  mov     [rax+18h], rbx
0x180073a87  mov     [rax+20h], r9
0x180073a8b  mov     [rax+8], rcx
0x180073a8f  push    rbp
0x180073a90  push    rsi
0x180073a91  push    rdi
0x180073a92  push    r12
0x180073a94  push    r13
0x180073a96  push    r14
0x180073a98  push    r15
0x180073a9a  lea     rbp, [rax-5Fh]
0x180073a9e  sub     rsp, 90h
0x180073aa5  mov     r14, r8
0x180073aa8  mov     edi, edx
0x180073aaa  mov     rsi, rcx
0x180073aad  mov     edx, edx
0x180073aaf  xor     r15d, r15d
0x180073ab2  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x180073ab9  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073ac0  mov     [rbp+57h+var_70], r15
0x180073ac4  xorps   xmm0, xmm0
0x180073ac7  mov     [rbp+57h+var_98], r11
0x180073acb  mov     rcx, r14
0x180073ace  mov     [rbp+57h+var_68], r15
0x180073ad2  lea     r8, [rbp+57h+var_68]
0x180073ad6  mov     r13, r9
0x180073ad9  movdqu  [rbp+57h+var_80], xmm0
0x180073ade  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x180073ae3  test    r13, r13
0x180073ae6  jz      short loc_180073AEC
0x180073ae8  mov     [r13+0], r15d
0x180073aec  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180073af3  test    rdx, rdx
0x180073af6  jz      loc_180074121
0x180073afc  mov     rcx, [rsi+18h]
0x180073b00  call    RtlIsTypeSafeHandleValid
0x180073b05  test    al, al
0x180073b07  jz      loc_180074121
0x180073b0d  test    r14, r14
0x180073b10  jnz     short loc_180073B30
0x180073b12  lea     rcx, [rbp+57h+var_98]
0x180073b16  mov     [rbp+57h+var_90], 571Eh
0x180073b1d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180073b22  lea     rcx, [rbp+57h+var_80]
0x180073b26  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180073b2b  jmp     loc_18007413E
0x180073b30  test    r13, r13
0x180073b33  jnz     short loc_180073B5D
0x180073b35  cmp     edi, 1
0x180073b38  jz      short loc_180073B5D
0x180073b3a  mov     ebx, 80004003h
0x180073b3f  mov     edx, 571Fh; char *
0x180073b44  mov     r8d, ebx; int
0x180073b47  mov     rcx, r11; this
0x180073b4a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180073b4f  lea     rcx, [rbp+57h+var_80]
0x180073b53  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180073b58  jmp     loc_180074141
0x180073b5d  mov     r8d, edi
0x180073b60  lea     rdx, [rbp+57h+arg_8]
0x180073b64  lea     rcx, [rbp+57h+var_80]
0x180073b68  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180073b6d  mov     ebx, [rax]
0x180073b6f  test    ebx, ebx
0x180073b71  jns     short loc_180073BCC
0x180073b73  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180073b79  jnz     short loc_180073B81
0x180073b7b  call    cs:__imp_DebugBreak
0x180073b81  mov     r9d, ebx; int
0x180073b84  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073b8b  mov     r8d, 5723h; char *
0x180073b91  lea     rcx, aStatusPropagat; "Status propagated"
0x180073b98  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180073b9d  mov     ecx, ebx; this
0x180073b9f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180073ba4  mov     ebx, eax
0x180073ba6  mov     esi, r15d
0x180073ba9  test    edi, edi
0x180073bab  jz      short loc_180073B4F
0x180073bad  mov     ecx, esi
0x180073baf  mov     rcx, [r14+rcx*8]
0x180073bb3  test    rcx, rcx
0x180073bb6  jz      short loc_180073BC4
0x180073bb8  mov     rdx, [rcx]
0x180073bbb  mov     rax, [rdx+10h]
0x180073bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073bc4  inc     esi
0x180073bc6  cmp     esi, edi
0x180073bc8  jb      short loc_180073BAD
0x180073bca  jmp     short loc_180073B4F
0x180073bcc  mov     eax, dword ptr [rbp+57h+var_70+4]
0x180073bcf  xorps   xmm0, xmm0
0x180073bd2  cmp     eax, dword ptr [rbp+57h+var_70]
0x180073bd5  mov     r10, [rsi+18h]
0x180073bd9  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180073bdd  xor     esi, esi
0x180073bdf  mov     r15, qword ptr [rbp+57h+var_80+8]
0x180073be3  mov     [rbp+57h+arg_8], eax
0x180073be6  mov     dword ptr [rbp+57h+var_70+4], eax
0x180073be9  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073bf0  mov     [rbp+57h+var_98], rax
0x180073bf4  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x180073bfb  mov     [rbp+57h+var_60], rsi
0x180073bff  movdqu  [rbp+57h+var_58], xmm0
0x180073c04  test    r15, r15
0x180073c07  jz      short loc_180073C35
0x180073c09  mov     ecx, esi
0x180073c0b  test    edi, edi
0x180073c0d  jz      short loc_180073C35
0x180073c0f  mov     rax, rcx
0x180073c12  inc     rcx
0x180073c15  shl     rax, 5
0x180073c19  mov     [rax+r15], rsi
0x180073c1d  mov     [rax+r15+8], rsi
0x180073c22  mov     [rax+r15+10h], rsi
0x180073c27  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x180073c30  cmp     rcx, rdi
0x180073c33  jb      short loc_180073C0F
0x180073c35  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180073c3c  test    rdx, rdx
0x180073c3f  jz      loc_180073D7D
0x180073c45  mov     rcx, r10
0x180073c48  call    RtlIsTypeSafeHandleValid
0x180073c4d  test    al, al
0x180073c4f  jz      loc_180073D7D
0x180073c55  test    r15, r15
0x180073c58  jnz     short loc_180073C6A
0x180073c5a  test    edi, edi
0x180073c5c  jz      short loc_180073C6A
0x180073c5e  mov     [rbp+57h+var_90], 478h
0x180073c65  jmp     loc_180073D84
0x180073c6a  mov     rdx, r10
0x180073c6d  lea     rcx, [rbp+57h+var_60]
0x180073c71  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x180073c76  mov     ebx, eax
0x180073c78  test    eax, eax
0x180073c7a  jns     short loc_180073CA2
0x180073c7c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180073c80  test    rdx, rdx
0x180073c83  jz      loc_180073D90
0x180073c89  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180073c90  mov     rax, [rcx+30h]
0x180073c94  mov     rcx, [rbp+57h+var_60]
0x180073c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073c9d  jmp     loc_180073D90
0x180073ca2  mov     rcx, qword ptr [rbp+57h+var_58]
0x180073ca6  mov     rax, [rcx+20h]
0x180073caa  cmp     [rcx+28h], rax
0x180073cae  jbe     short loc_180073CE6
0x180073cb0  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180073cb4  mov     [rbp+57h+var_90], 47Dh
0x180073cbb  test    rdx, rdx
0x180073cbe  jz      short loc_180073CD4
0x180073cc0  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180073cc7  mov     rcx, [rbp+57h+var_60]
0x180073ccb  mov     rax, [rax+30h]
0x180073ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cd4  lea     rdx, [rbp+57h+var_98]
0x180073cd8  lea     rcx, [rbp+57h+var_98]
0x180073cdc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180073ce1  jmp     loc_180073D8D
0x180073ce6  test    edi, edi
0x180073ce8  jz      short loc_180073D62
0x180073cea  mov     r9, [rcx+28h]
0x180073cee  cmp     r9, [rcx+20h]
0x180073cf2  jnb     short loc_180073D62
0x180073cf4  mov     rdx, [rcx+30h]
0x180073cf8  mov     rax, rsi
0x180073cfb  mov     rcx, [rcx+8]
0x180073cff  shl     rax, 5
0x180073d03  add     r15, rax
0x180073d06  mov     edx, [rdx+r9*4]
0x180073d0a  mov     r8, r15
0x180073d0d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x180073d12  mov     ebx, eax
0x180073d14  test    eax, eax
0x180073d16  js      short loc_180073D41
0x180073d18  mov     rdx, qword ptr [rbp+57h+var_58]
0x180073d1c  inc     rsi
0x180073d1f  mov     rcx, [rdx+28h]
0x180073d23  mov     rax, [rdx+38h]
0x180073d27  mov     ecx, [rax+rcx*4]
0x180073d2a  mov     [r15+18h], ecx
0x180073d2e  inc     qword ptr [rdx+28h]
0x180073d32  cmp     rsi, rdi
0x180073d35  jnb     short loc_180073D62
0x180073d37  mov     rcx, qword ptr [rbp+57h+var_58]
0x180073d3b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x180073d3f  jmp     short loc_180073CEA
0x180073d41  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180073d45  test    rdx, rdx
0x180073d48  jz      short loc_180073D5E
0x180073d4a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180073d51  mov     rcx, [rbp+57h+var_60]
0x180073d55  mov     rax, [rax+30h]
0x180073d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d5e  xor     esi, esi
0x180073d60  jmp     short loc_180073D90
0x180073d62  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180073d66  xor     ebx, ebx
0x180073d68  test    rdx, rdx
0x180073d6b  jz      short loc_180073D90
0x180073d6d  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180073d74  mov     rax, [rax+30h]
0x180073d78  jmp     loc_180073C94
0x180073d7d  mov     [rbp+57h+var_90], 477h
0x180073d84  lea     rcx, [rbp+57h+var_98]
0x180073d88  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180073d8d  mov     ebx, dword ptr [rbp+57h+var_88]
0x180073d90  test    ebx, ebx
0x180073d92  jns     short loc_180073DF1
0x180073d94  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180073d9a  jnz     short loc_180073DA2
0x180073d9c  call    cs:__imp_DebugBreak
0x180073da2  mov     r9d, ebx; int
0x180073da5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073dac  mov     r8d, 5724h; char *
0x180073db2  lea     rcx, aStatusPropagat; "Status propagated"
0x180073db9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180073dbe  mov     ecx, ebx; this
0x180073dc0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180073dc5  xor     esi, esi
0x180073dc7  mov     ebx, eax
0x180073dc9  test    edi, edi
0x180073dcb  jz      loc_180073B4F
0x180073dd1  mov     rcx, [r14+rsi*8]
0x180073dd5  test    rcx, rcx
0x180073dd8  jz      short loc_180073DE6
0x180073dda  mov     rax, [rcx]
0x180073ddd  mov     rax, [rax+10h]
0x180073de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073de6  inc     esi
0x180073de8  cmp     esi, edi
0x180073dea  jb      short loc_180073DD1
0x180073dec  jmp     loc_180073B4F
0x180073df1  xor     r15d, r15d
0x180073df4  test    rsi, rsi
0x180073df7  jz      loc_180073F14
0x180073dfd  lea     rdx, [rbp+57h+var_48]
0x180073e01  mov     [rbp+57h+var_A0], 0
0x180073e09  lea     rcx, [rbp+57h+var_A0]
0x180073e0d  mov     [rbp+57h+var_68], 0
0x180073e15  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyRequestEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyRequestEntry>>>::Allocate(void)
0x180073e1a  mov     ebx, [rax]
0x180073e1c  test    ebx, ebx
0x180073e1e  js      loc_18007409D
0x180073e24  mov     eax, [rbp+57h+arg_8]
0x180073e27  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x180073e2b  cmp     eax, dword ptr [rbp+57h+var_70]
0x180073e2e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180073e32  mov     [rbp+57h+arg_8], eax
0x180073e35  mov     dword ptr [rbp+57h+var_70+4], eax
0x180073e38  mov     eax, r15d
0x180073e3b  shl     rax, 5
0x180073e3f  add     rax, qword ptr [rbp+57h+var_80+8]
0x180073e43  mov     rcx, rax; this
0x180073e46  mov     [rbp+57h+var_40], rax
0x180073e4a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x180073e4f  mov     ebx, eax
0x180073e51  test    eax, eax
0x180073e53  js      loc_180074056
0x180073e59  mov     eax, [rbp+57h+arg_8]
0x180073e5c  cmp     eax, dword ptr [rbp+57h+var_70]
0x180073e5f  mov     r8, [rbp+57h+var_40]
0x180073e63  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180073e67  mov     r9, [rbp+57h+var_68]
0x180073e6b  mov     rcx, [rbp+57h+var_A0]
0x180073e6f  mov     r8d, [r8+18h]
0x180073e73  mov     [rbp+57h+arg_8], eax
0x180073e76  mov     dword ptr [rbp+57h+var_70+4], eax
0x180073e79  mov     rax, [rbp+57h+arg_0]
0x180073e7d  mov     rdx, [rax+10h]
0x180073e81  call    ?Initialize@CAssemblyRequestEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CAssemblyRequestEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x180073e86  mov     ebx, eax
0x180073e88  test    eax, eax
0x180073e8a  js      loc_18007400F
0x180073e90  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x180073e97  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073e9e  mov     [rbp+57h+var_98], rax
0x180073ea2  cmp     r15d, edi
0x180073ea5  jb      short loc_180073EC3
0x180073ea7  xor     r13d, r13d
0x180073eaa  mov     [rbp+57h+var_90], 28h ; '('
0x180073eb1  lea     rdx, [rbp+57h+var_98]
0x180073eb5  lea     rcx, [rbp+57h+var_98]
0x180073eb9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180073ebe  mov     ebx, dword ptr [rbp+57h+var_88]
0x180073ec1  jmp     short loc_180073EC9
0x180073ec3  lea     r13, [r14+r15*8]
0x180073ec7  xor     ebx, ebx
0x180073ec9  test    ebx, ebx
0x180073ecb  js      loc_180073FA9
0x180073ed1  mov     rcx, [rbp+57h+var_A0]
0x180073ed5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180073edc  mov     r8, r13
0x180073edf  mov     rax, [rcx]
0x180073ee2  mov     rax, [rax]
0x180073ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073eea  mov     ebx, eax
  ... truncated ...
```
