# CEnumFileSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007b4c0`
- end: `0x18007bb9e`
- name: `?Next@CEnumFileSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumFileSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180058378`
- `0x18005b74c`
- `0x18005df30`
- `0x18006a070`
- `0x18007b4c0`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b5bb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b7dc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b978`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b9f1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bae5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b5bb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b7dc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b978`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b9f1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bae5`

## string_xrefs

- `0x18007b629`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007b4f9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b5c4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b7e5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b8d7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b984`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b9a5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b9fa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ba52`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ba99`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007baee`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumFileSection::Next(
        CEnumFileSection *this,
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
    v59 = 20730;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 20731;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x50FC, -2147467261, v8);
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
      (const char *)0x5100,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::Allocate(
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
            (const char *)0x510A,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>(&v57);
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
        v38 = CFileEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x510B,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>(&v57);
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
            (const char *)0x510C,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>(&v57);
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
            (const char *)0x510D,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>(&v57);
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
        (const char *)0x5109,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>(&v57);
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
          (const char *)0x5115,
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
      (const char *)0x5101,
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
0x18007b4c0  mov     rax, rsp
0x18007b4c3  mov     [rax+18h], rbx
0x18007b4c7  mov     [rax+20h], r9
0x18007b4cb  mov     [rax+8], rcx
0x18007b4cf  push    rbp
0x18007b4d0  push    rsi
0x18007b4d1  push    rdi
0x18007b4d2  push    r12
0x18007b4d4  push    r13
0x18007b4d6  push    r14
0x18007b4d8  push    r15
0x18007b4da  lea     rbp, [rax-5Fh]
0x18007b4de  sub     rsp, 90h
0x18007b4e5  mov     r14, r8
0x18007b4e8  mov     edi, edx
0x18007b4ea  mov     rsi, rcx
0x18007b4ed  mov     edx, edx
0x18007b4ef  xor     r15d, r15d
0x18007b4f2  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007b4f9  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007b500  mov     [rbp+57h+var_70], r15
0x18007b504  xorps   xmm0, xmm0
0x18007b507  mov     [rbp+57h+var_98], r11
0x18007b50b  mov     rcx, r14
0x18007b50e  mov     [rbp+57h+var_68], r15
0x18007b512  lea     r8, [rbp+57h+var_68]
0x18007b516  mov     r13, r9
0x18007b519  movdqu  [rbp+57h+var_80], xmm0
0x18007b51e  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007b523  test    r13, r13
0x18007b526  jz      short loc_18007B52C
0x18007b528  mov     [r13+0], r15d
0x18007b52c  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b533  test    rdx, rdx
0x18007b536  jz      loc_18007BB61
0x18007b53c  mov     rcx, [rsi+18h]
0x18007b540  call    RtlIsTypeSafeHandleValid
0x18007b545  test    al, al
0x18007b547  jz      loc_18007BB61
0x18007b54d  test    r14, r14
0x18007b550  jnz     short loc_18007B570
0x18007b552  lea     rcx, [rbp+57h+var_98]
0x18007b556  mov     [rbp+57h+var_90], 50FBh
0x18007b55d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007b562  lea     rcx, [rbp+57h+var_80]
0x18007b566  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007b56b  jmp     loc_18007BB7E
0x18007b570  test    r13, r13
0x18007b573  jnz     short loc_18007B59D
0x18007b575  cmp     edi, 1
0x18007b578  jz      short loc_18007B59D
0x18007b57a  mov     ebx, 80004003h
0x18007b57f  mov     edx, 50FCh; char *
0x18007b584  mov     r8d, ebx; int
0x18007b587  mov     rcx, r11; this
0x18007b58a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007b58f  lea     rcx, [rbp+57h+var_80]
0x18007b593  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007b598  jmp     loc_18007BB81
0x18007b59d  mov     r8d, edi
0x18007b5a0  lea     rdx, [rbp+57h+arg_8]
0x18007b5a4  lea     rcx, [rbp+57h+var_80]
0x18007b5a8  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007b5ad  mov     ebx, [rax]
0x18007b5af  test    ebx, ebx
0x18007b5b1  jns     short loc_18007B60C
0x18007b5b3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007b5b9  jnz     short loc_18007B5C1
0x18007b5bb  call    cs:__imp_DebugBreak
0x18007b5c1  mov     r9d, ebx; int
0x18007b5c4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007b5cb  mov     r8d, 5100h; char *
0x18007b5d1  lea     rcx, aStatusPropagat; "Status propagated"
0x18007b5d8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007b5dd  mov     ecx, ebx; this
0x18007b5df  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007b5e4  mov     ebx, eax
0x18007b5e6  mov     esi, r15d
0x18007b5e9  test    edi, edi
0x18007b5eb  jz      short loc_18007B58F
0x18007b5ed  mov     ecx, esi
0x18007b5ef  mov     rcx, [r14+rcx*8]
0x18007b5f3  test    rcx, rcx
0x18007b5f6  jz      short loc_18007B604
0x18007b5f8  mov     rdx, [rcx]
0x18007b5fb  mov     rax, [rdx+10h]
0x18007b5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b604  inc     esi
0x18007b606  cmp     esi, edi
0x18007b608  jb      short loc_18007B5ED
0x18007b60a  jmp     short loc_18007B58F
0x18007b60c  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007b60f  xorps   xmm0, xmm0
0x18007b612  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007b615  mov     r10, [rsi+18h]
0x18007b619  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007b61d  xor     esi, esi
0x18007b61f  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007b623  mov     [rbp+57h+arg_8], eax
0x18007b626  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007b629  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007b630  mov     [rbp+57h+var_98], rax
0x18007b634  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007b63b  mov     [rbp+57h+var_60], rsi
0x18007b63f  movdqu  [rbp+57h+var_58], xmm0
0x18007b644  test    r15, r15
0x18007b647  jz      short loc_18007B675
0x18007b649  mov     ecx, esi
0x18007b64b  test    edi, edi
0x18007b64d  jz      short loc_18007B675
0x18007b64f  mov     rax, rcx
0x18007b652  inc     rcx
0x18007b655  shl     rax, 5
0x18007b659  mov     [rax+r15], rsi
0x18007b65d  mov     [rax+r15+8], rsi
0x18007b662  mov     [rax+r15+10h], rsi
0x18007b667  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007b670  cmp     rcx, rdi
0x18007b673  jb      short loc_18007B64F
0x18007b675  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b67c  test    rdx, rdx
0x18007b67f  jz      loc_18007B7BD
0x18007b685  mov     rcx, r10
0x18007b688  call    RtlIsTypeSafeHandleValid
0x18007b68d  test    al, al
0x18007b68f  jz      loc_18007B7BD
0x18007b695  test    r15, r15
0x18007b698  jnz     short loc_18007B6AA
0x18007b69a  test    edi, edi
0x18007b69c  jz      short loc_18007B6AA
0x18007b69e  mov     [rbp+57h+var_90], 478h
0x18007b6a5  jmp     loc_18007B7C4
0x18007b6aa  mov     rdx, r10
0x18007b6ad  lea     rcx, [rbp+57h+var_60]
0x18007b6b1  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007b6b6  mov     ebx, eax
0x18007b6b8  test    eax, eax
0x18007b6ba  jns     short loc_18007B6E2
0x18007b6bc  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007b6c0  test    rdx, rdx
0x18007b6c3  jz      loc_18007B7D0
0x18007b6c9  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b6d0  mov     rax, [rcx+30h]
0x18007b6d4  mov     rcx, [rbp+57h+var_60]
0x18007b6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6dd  jmp     loc_18007B7D0
0x18007b6e2  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007b6e6  mov     rax, [rcx+20h]
0x18007b6ea  cmp     [rcx+28h], rax
0x18007b6ee  jbe     short loc_18007B726
0x18007b6f0  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007b6f4  mov     [rbp+57h+var_90], 47Dh
0x18007b6fb  test    rdx, rdx
0x18007b6fe  jz      short loc_18007B714
0x18007b700  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b707  mov     rcx, [rbp+57h+var_60]
0x18007b70b  mov     rax, [rax+30h]
0x18007b70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b714  lea     rdx, [rbp+57h+var_98]
0x18007b718  lea     rcx, [rbp+57h+var_98]
0x18007b71c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007b721  jmp     loc_18007B7CD
0x18007b726  test    edi, edi
0x18007b728  jz      short loc_18007B7A2
0x18007b72a  mov     r9, [rcx+28h]
0x18007b72e  cmp     r9, [rcx+20h]
0x18007b732  jnb     short loc_18007B7A2
0x18007b734  mov     rdx, [rcx+30h]
0x18007b738  mov     rax, rsi
0x18007b73b  mov     rcx, [rcx+8]
0x18007b73f  shl     rax, 5
0x18007b743  add     r15, rax
0x18007b746  mov     edx, [rdx+r9*4]
0x18007b74a  mov     r8, r15
0x18007b74d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007b752  mov     ebx, eax
0x18007b754  test    eax, eax
0x18007b756  js      short loc_18007B781
0x18007b758  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007b75c  inc     rsi
0x18007b75f  mov     rcx, [rdx+28h]
0x18007b763  mov     rax, [rdx+38h]
0x18007b767  mov     ecx, [rax+rcx*4]
0x18007b76a  mov     [r15+18h], ecx
0x18007b76e  inc     qword ptr [rdx+28h]
0x18007b772  cmp     rsi, rdi
0x18007b775  jnb     short loc_18007B7A2
0x18007b777  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007b77b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007b77f  jmp     short loc_18007B72A
0x18007b781  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007b785  test    rdx, rdx
0x18007b788  jz      short loc_18007B79E
0x18007b78a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b791  mov     rcx, [rbp+57h+var_60]
0x18007b795  mov     rax, [rax+30h]
0x18007b799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b79e  xor     esi, esi
0x18007b7a0  jmp     short loc_18007B7D0
0x18007b7a2  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007b7a6  xor     ebx, ebx
0x18007b7a8  test    rdx, rdx
0x18007b7ab  jz      short loc_18007B7D0
0x18007b7ad  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b7b4  mov     rax, [rax+30h]
0x18007b7b8  jmp     loc_18007B6D4
0x18007b7bd  mov     [rbp+57h+var_90], 477h
0x18007b7c4  lea     rcx, [rbp+57h+var_98]
0x18007b7c8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007b7cd  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007b7d0  test    ebx, ebx
0x18007b7d2  jns     short loc_18007B831
0x18007b7d4  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007b7da  jnz     short loc_18007B7E2
0x18007b7dc  call    cs:__imp_DebugBreak
0x18007b7e2  mov     r9d, ebx; int
0x18007b7e5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007b7ec  mov     r8d, 5101h; char *
0x18007b7f2  lea     rcx, aStatusPropagat; "Status propagated"
0x18007b7f9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007b7fe  mov     ecx, ebx; this
0x18007b800  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007b805  xor     esi, esi
0x18007b807  mov     ebx, eax
0x18007b809  test    edi, edi
0x18007b80b  jz      loc_18007B58F
0x18007b811  mov     rcx, [r14+rsi*8]
0x18007b815  test    rcx, rcx
0x18007b818  jz      short loc_18007B826
0x18007b81a  mov     rax, [rcx]
0x18007b81d  mov     rax, [rax+10h]
0x18007b821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b826  inc     esi
0x18007b828  cmp     esi, edi
0x18007b82a  jb      short loc_18007B811
0x18007b82c  jmp     loc_18007B58F
0x18007b831  xor     r15d, r15d
0x18007b834  test    rsi, rsi
0x18007b837  jz      loc_18007B954
0x18007b83d  lea     rdx, [rbp+57h+var_48]
0x18007b841  mov     [rbp+57h+var_A0], 0
0x18007b849  lea     rcx, [rbp+57h+var_A0]
0x18007b84d  mov     [rbp+57h+var_68], 0
0x18007b855  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCFileEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileEntry>>>::Allocate(void)
0x18007b85a  mov     ebx, [rax]
0x18007b85c  test    ebx, ebx
0x18007b85e  js      loc_18007BADD
0x18007b864  mov     eax, [rbp+57h+arg_8]
0x18007b867  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007b86b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007b86e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007b872  mov     [rbp+57h+arg_8], eax
0x18007b875  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007b878  mov     eax, r15d
0x18007b87b  shl     rax, 5
0x18007b87f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007b883  mov     rcx, rax; this
0x18007b886  mov     [rbp+57h+var_40], rax
0x18007b88a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007b88f  mov     ebx, eax
0x18007b891  test    eax, eax
0x18007b893  js      loc_18007BA96
0x18007b899  mov     eax, [rbp+57h+arg_8]
0x18007b89c  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007b89f  mov     r8, [rbp+57h+var_40]
0x18007b8a3  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007b8a7  mov     r9, [rbp+57h+var_68]
0x18007b8ab  mov     rcx, [rbp+57h+var_A0]
0x18007b8af  mov     r8d, [r8+18h]
0x18007b8b3  mov     [rbp+57h+arg_8], eax
0x18007b8b6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007b8b9  mov     rax, [rbp+57h+arg_0]
0x18007b8bd  mov     rdx, [rax+10h]
0x18007b8c1  call    ?Initialize@CFileEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CFileEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007b8c6  mov     ebx, eax
0x18007b8c8  test    eax, eax
0x18007b8ca  js      loc_18007BA4F
0x18007b8d0  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007b8d7  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007b8de  mov     [rbp+57h+var_98], rax
0x18007b8e2  cmp     r15d, edi
0x18007b8e5  jb      short loc_18007B903
0x18007b8e7  xor     r13d, r13d
0x18007b8ea  mov     [rbp+57h+var_90], 28h ; '('
0x18007b8f1  lea     rdx, [rbp+57h+var_98]
0x18007b8f5  lea     rcx, [rbp+57h+var_98]
0x18007b8f9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007b8fe  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007b901  jmp     short loc_18007B909
0x18007b903  lea     r13, [r14+r15*8]
0x18007b907  xor     ebx, ebx
0x18007b909  test    ebx, ebx
0x18007b90b  js      loc_18007B9E9
0x18007b911  mov     rcx, [rbp+57h+var_A0]
0x18007b915  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007b91c  mov     r8, r13
0x18007b91f  mov     rax, [rcx]
0x18007b922  mov     rax, [rax]
0x18007b925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b92a  mov     ebx, eax
  ... truncated ...
```
