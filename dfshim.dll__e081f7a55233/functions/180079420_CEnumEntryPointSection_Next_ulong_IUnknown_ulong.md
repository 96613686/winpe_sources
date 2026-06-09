# CEnumEntryPointSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180079420`
- end: `0x180079afe`
- name: `?Next@CEnumEntryPointSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumEntryPointSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180058148`
- `0x18005b0f8`
- `0x18005df30`
- `0x180067fa8`
- `0x180079420`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007951b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007973c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800798d8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079951`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079a45`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007951b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007973c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800798d8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079951`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180079a45`

## string_xrefs

- `0x180079589`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180079459`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079524`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079745`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079837`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800798e4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079905`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007995a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800799b2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800799f9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180079a4e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumEntryPointSection::Next(
        CEnumEntryPointSection *this,
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
    v59 = 22077;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 22078;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x563F, -2147467261, v8);
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
      (const char *)0x5643,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::Allocate(
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
            (const char *)0x564D,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>(&v57);
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
        v38 = CEntryPointEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x564E,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>(&v57);
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
            (const char *)0x564F,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>(&v57);
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
            (const char *)0x5650,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>(&v57);
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
        (const char *)0x564C,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>(&v57);
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
          (const char *)0x5658,
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
      (const char *)0x5644,
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
0x180079420  mov     rax, rsp
0x180079423  mov     [rax+18h], rbx
0x180079427  mov     [rax+20h], r9
0x18007942b  mov     [rax+8], rcx
0x18007942f  push    rbp
0x180079430  push    rsi
0x180079431  push    rdi
0x180079432  push    r12
0x180079434  push    r13
0x180079436  push    r14
0x180079438  push    r15
0x18007943a  lea     rbp, [rax-5Fh]
0x18007943e  sub     rsp, 90h
0x180079445  mov     r14, r8
0x180079448  mov     edi, edx
0x18007944a  mov     rsi, rcx
0x18007944d  mov     edx, edx
0x18007944f  xor     r15d, r15d
0x180079452  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x180079459  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180079460  mov     [rbp+57h+var_70], r15
0x180079464  xorps   xmm0, xmm0
0x180079467  mov     [rbp+57h+var_98], r11
0x18007946b  mov     rcx, r14
0x18007946e  mov     [rbp+57h+var_68], r15
0x180079472  lea     r8, [rbp+57h+var_68]
0x180079476  mov     r13, r9
0x180079479  movdqu  [rbp+57h+var_80], xmm0
0x18007947e  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x180079483  test    r13, r13
0x180079486  jz      short loc_18007948C
0x180079488  mov     [r13+0], r15d
0x18007948c  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079493  test    rdx, rdx
0x180079496  jz      loc_180079AC1
0x18007949c  mov     rcx, [rsi+18h]
0x1800794a0  call    RtlIsTypeSafeHandleValid
0x1800794a5  test    al, al
0x1800794a7  jz      loc_180079AC1
0x1800794ad  test    r14, r14
0x1800794b0  jnz     short loc_1800794D0
0x1800794b2  lea     rcx, [rbp+57h+var_98]
0x1800794b6  mov     [rbp+57h+var_90], 563Eh
0x1800794bd  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800794c2  lea     rcx, [rbp+57h+var_80]
0x1800794c6  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x1800794cb  jmp     loc_180079ADE
0x1800794d0  test    r13, r13
0x1800794d3  jnz     short loc_1800794FD
0x1800794d5  cmp     edi, 1
0x1800794d8  jz      short loc_1800794FD
0x1800794da  mov     ebx, 80004003h
0x1800794df  mov     edx, 563Fh; char *
0x1800794e4  mov     r8d, ebx; int
0x1800794e7  mov     rcx, r11; this
0x1800794ea  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x1800794ef  lea     rcx, [rbp+57h+var_80]
0x1800794f3  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x1800794f8  jmp     loc_180079AE1
0x1800794fd  mov     r8d, edi
0x180079500  lea     rdx, [rbp+57h+arg_8]
0x180079504  lea     rcx, [rbp+57h+var_80]
0x180079508  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007950d  mov     ebx, [rax]
0x18007950f  test    ebx, ebx
0x180079511  jns     short loc_18007956C
0x180079513  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180079519  jnz     short loc_180079521
0x18007951b  call    cs:__imp_DebugBreak
0x180079521  mov     r9d, ebx; int
0x180079524  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007952b  mov     r8d, 5643h; char *
0x180079531  lea     rcx, aStatusPropagat; "Status propagated"
0x180079538  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007953d  mov     ecx, ebx; this
0x18007953f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180079544  mov     ebx, eax
0x180079546  mov     esi, r15d
0x180079549  test    edi, edi
0x18007954b  jz      short loc_1800794EF
0x18007954d  mov     ecx, esi
0x18007954f  mov     rcx, [r14+rcx*8]
0x180079553  test    rcx, rcx
0x180079556  jz      short loc_180079564
0x180079558  mov     rdx, [rcx]
0x18007955b  mov     rax, [rdx+10h]
0x18007955f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079564  inc     esi
0x180079566  cmp     esi, edi
0x180079568  jb      short loc_18007954D
0x18007956a  jmp     short loc_1800794EF
0x18007956c  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007956f  xorps   xmm0, xmm0
0x180079572  cmp     eax, dword ptr [rbp+57h+var_70]
0x180079575  mov     r10, [rsi+18h]
0x180079579  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007957d  xor     esi, esi
0x18007957f  mov     r15, qword ptr [rbp+57h+var_80+8]
0x180079583  mov     [rbp+57h+arg_8], eax
0x180079586  mov     dword ptr [rbp+57h+var_70+4], eax
0x180079589  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180079590  mov     [rbp+57h+var_98], rax
0x180079594  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007959b  mov     [rbp+57h+var_60], rsi
0x18007959f  movdqu  [rbp+57h+var_58], xmm0
0x1800795a4  test    r15, r15
0x1800795a7  jz      short loc_1800795D5
0x1800795a9  mov     ecx, esi
0x1800795ab  test    edi, edi
0x1800795ad  jz      short loc_1800795D5
0x1800795af  mov     rax, rcx
0x1800795b2  inc     rcx
0x1800795b5  shl     rax, 5
0x1800795b9  mov     [rax+r15], rsi
0x1800795bd  mov     [rax+r15+8], rsi
0x1800795c2  mov     [rax+r15+10h], rsi
0x1800795c7  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x1800795d0  cmp     rcx, rdi
0x1800795d3  jb      short loc_1800795AF
0x1800795d5  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800795dc  test    rdx, rdx
0x1800795df  jz      loc_18007971D
0x1800795e5  mov     rcx, r10
0x1800795e8  call    RtlIsTypeSafeHandleValid
0x1800795ed  test    al, al
0x1800795ef  jz      loc_18007971D
0x1800795f5  test    r15, r15
0x1800795f8  jnz     short loc_18007960A
0x1800795fa  test    edi, edi
0x1800795fc  jz      short loc_18007960A
0x1800795fe  mov     [rbp+57h+var_90], 478h
0x180079605  jmp     loc_180079724
0x18007960a  mov     rdx, r10
0x18007960d  lea     rcx, [rbp+57h+var_60]
0x180079611  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x180079616  mov     ebx, eax
0x180079618  test    eax, eax
0x18007961a  jns     short loc_180079642
0x18007961c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180079620  test    rdx, rdx
0x180079623  jz      loc_180079730
0x180079629  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079630  mov     rax, [rcx+30h]
0x180079634  mov     rcx, [rbp+57h+var_60]
0x180079638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007963d  jmp     loc_180079730
0x180079642  mov     rcx, qword ptr [rbp+57h+var_58]
0x180079646  mov     rax, [rcx+20h]
0x18007964a  cmp     [rcx+28h], rax
0x18007964e  jbe     short loc_180079686
0x180079650  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180079654  mov     [rbp+57h+var_90], 47Dh
0x18007965b  test    rdx, rdx
0x18007965e  jz      short loc_180079674
0x180079660  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079667  mov     rcx, [rbp+57h+var_60]
0x18007966b  mov     rax, [rax+30h]
0x18007966f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079674  lea     rdx, [rbp+57h+var_98]
0x180079678  lea     rcx, [rbp+57h+var_98]
0x18007967c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180079681  jmp     loc_18007972D
0x180079686  test    edi, edi
0x180079688  jz      short loc_180079702
0x18007968a  mov     r9, [rcx+28h]
0x18007968e  cmp     r9, [rcx+20h]
0x180079692  jnb     short loc_180079702
0x180079694  mov     rdx, [rcx+30h]
0x180079698  mov     rax, rsi
0x18007969b  mov     rcx, [rcx+8]
0x18007969f  shl     rax, 5
0x1800796a3  add     r15, rax
0x1800796a6  mov     edx, [rdx+r9*4]
0x1800796aa  mov     r8, r15
0x1800796ad  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x1800796b2  mov     ebx, eax
0x1800796b4  test    eax, eax
0x1800796b6  js      short loc_1800796E1
0x1800796b8  mov     rdx, qword ptr [rbp+57h+var_58]
0x1800796bc  inc     rsi
0x1800796bf  mov     rcx, [rdx+28h]
0x1800796c3  mov     rax, [rdx+38h]
0x1800796c7  mov     ecx, [rax+rcx*4]
0x1800796ca  mov     [r15+18h], ecx
0x1800796ce  inc     qword ptr [rdx+28h]
0x1800796d2  cmp     rsi, rdi
0x1800796d5  jnb     short loc_180079702
0x1800796d7  mov     rcx, qword ptr [rbp+57h+var_58]
0x1800796db  mov     r15, qword ptr [rbp+57h+var_80+8]
0x1800796df  jmp     short loc_18007968A
0x1800796e1  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x1800796e5  test    rdx, rdx
0x1800796e8  jz      short loc_1800796FE
0x1800796ea  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800796f1  mov     rcx, [rbp+57h+var_60]
0x1800796f5  mov     rax, [rax+30h]
0x1800796f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800796fe  xor     esi, esi
0x180079700  jmp     short loc_180079730
0x180079702  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180079706  xor     ebx, ebx
0x180079708  test    rdx, rdx
0x18007970b  jz      short loc_180079730
0x18007970d  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180079714  mov     rax, [rax+30h]
0x180079718  jmp     loc_180079634
0x18007971d  mov     [rbp+57h+var_90], 477h
0x180079724  lea     rcx, [rbp+57h+var_98]
0x180079728  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007972d  mov     ebx, dword ptr [rbp+57h+var_88]
0x180079730  test    ebx, ebx
0x180079732  jns     short loc_180079791
0x180079734  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007973a  jnz     short loc_180079742
0x18007973c  call    cs:__imp_DebugBreak
0x180079742  mov     r9d, ebx; int
0x180079745  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007974c  mov     r8d, 5644h; char *
0x180079752  lea     rcx, aStatusPropagat; "Status propagated"
0x180079759  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007975e  mov     ecx, ebx; this
0x180079760  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180079765  xor     esi, esi
0x180079767  mov     ebx, eax
0x180079769  test    edi, edi
0x18007976b  jz      loc_1800794EF
0x180079771  mov     rcx, [r14+rsi*8]
0x180079775  test    rcx, rcx
0x180079778  jz      short loc_180079786
0x18007977a  mov     rax, [rcx]
0x18007977d  mov     rax, [rax+10h]
0x180079781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079786  inc     esi
0x180079788  cmp     esi, edi
0x18007978a  jb      short loc_180079771
0x18007978c  jmp     loc_1800794EF
0x180079791  xor     r15d, r15d
0x180079794  test    rsi, rsi
0x180079797  jz      loc_1800798B4
0x18007979d  lea     rdx, [rbp+57h+var_48]
0x1800797a1  mov     [rbp+57h+var_A0], 0
0x1800797a9  lea     rcx, [rbp+57h+var_A0]
0x1800797ad  mov     [rbp+57h+var_68], 0
0x1800797b5  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEntryPointEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEntryPointEntry>>>::Allocate(void)
0x1800797ba  mov     ebx, [rax]
0x1800797bc  test    ebx, ebx
0x1800797be  js      loc_180079A3D
0x1800797c4  mov     eax, [rbp+57h+arg_8]
0x1800797c7  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x1800797cb  cmp     eax, dword ptr [rbp+57h+var_70]
0x1800797ce  cmovb   eax, dword ptr [rbp+57h+var_70]
0x1800797d2  mov     [rbp+57h+arg_8], eax
0x1800797d5  mov     dword ptr [rbp+57h+var_70+4], eax
0x1800797d8  mov     eax, r15d
0x1800797db  shl     rax, 5
0x1800797df  add     rax, qword ptr [rbp+57h+var_80+8]
0x1800797e3  mov     rcx, rax; this
0x1800797e6  mov     [rbp+57h+var_40], rax
0x1800797ea  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x1800797ef  mov     ebx, eax
0x1800797f1  test    eax, eax
0x1800797f3  js      loc_1800799F6
0x1800797f9  mov     eax, [rbp+57h+arg_8]
0x1800797fc  cmp     eax, dword ptr [rbp+57h+var_70]
0x1800797ff  mov     r8, [rbp+57h+var_40]
0x180079803  cmovb   eax, dword ptr [rbp+57h+var_70]
0x180079807  mov     r9, [rbp+57h+var_68]
0x18007980b  mov     rcx, [rbp+57h+var_A0]
0x18007980f  mov     r8d, [r8+18h]
0x180079813  mov     [rbp+57h+arg_8], eax
0x180079816  mov     dword ptr [rbp+57h+var_70+4], eax
0x180079819  mov     rax, [rbp+57h+arg_0]
0x18007981d  mov     rdx, [rax+10h]
0x180079821  call    ?Initialize@CEntryPointEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CEntryPointEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x180079826  mov     ebx, eax
0x180079828  test    eax, eax
0x18007982a  js      loc_1800799AF
0x180079830  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x180079837  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007983e  mov     [rbp+57h+var_98], rax
0x180079842  cmp     r15d, edi
0x180079845  jb      short loc_180079863
0x180079847  xor     r13d, r13d
0x18007984a  mov     [rbp+57h+var_90], 28h ; '('
0x180079851  lea     rdx, [rbp+57h+var_98]
0x180079855  lea     rcx, [rbp+57h+var_98]
0x180079859  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007985e  mov     ebx, dword ptr [rbp+57h+var_88]
0x180079861  jmp     short loc_180079869
0x180079863  lea     r13, [r14+r15*8]
0x180079867  xor     ebx, ebx
0x180079869  test    ebx, ebx
0x18007986b  js      loc_180079949
0x180079871  mov     rcx, [rbp+57h+var_A0]
0x180079875  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007987c  mov     r8, r13
0x18007987f  mov     rax, [rcx]
0x180079882  mov     rax, [rax]
0x180079885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007988a  mov     ebx, eax
  ... truncated ...
```
