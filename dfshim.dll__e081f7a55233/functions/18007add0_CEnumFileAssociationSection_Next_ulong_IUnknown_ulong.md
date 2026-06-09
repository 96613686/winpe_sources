# CEnumFileAssociationSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007add0`
- end: `0x18007b4ae`
- name: `?Next@CEnumFileAssociationSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumFileAssociationSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180058308`
- `0x18005b608`
- `0x18005df30`
- `0x180069eac`
- `0x18007add0`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007aecb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b0ec`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b288`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b301`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b3f5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007aecb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b0ec`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b288`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b301`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007b3f5`

## string_xrefs

- `0x18007af39`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007ae09`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007aed4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b0f5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b1e7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b294`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b2b5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b30a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b362`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b3a9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007b3fe`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumFileAssociationSection::Next(
        CEnumFileAssociationSection *this,
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
    v59 = 20842;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 20843;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x516C, -2147467261, v8);
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
      (const char *)0x5170,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::Allocate(
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
            (const char *)0x517A,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>(&v57);
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
        v38 = CFileAssociationEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x517B,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>(&v57);
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
            (const char *)0x517C,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>(&v57);
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
            (const char *)0x517D,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>(&v57);
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
        (const char *)0x5179,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>(&v57);
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
          (const char *)0x5185,
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
      (const char *)0x5171,
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
0x18007add0  mov     rax, rsp
0x18007add3  mov     [rax+18h], rbx
0x18007add7  mov     [rax+20h], r9
0x18007addb  mov     [rax+8], rcx
0x18007addf  push    rbp
0x18007ade0  push    rsi
0x18007ade1  push    rdi
0x18007ade2  push    r12
0x18007ade4  push    r13
0x18007ade6  push    r14
0x18007ade8  push    r15
0x18007adea  lea     rbp, [rax-5Fh]
0x18007adee  sub     rsp, 90h
0x18007adf5  mov     r14, r8
0x18007adf8  mov     edi, edx
0x18007adfa  mov     rsi, rcx
0x18007adfd  mov     edx, edx
0x18007adff  xor     r15d, r15d
0x18007ae02  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007ae09  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007ae10  mov     [rbp+57h+var_70], r15
0x18007ae14  xorps   xmm0, xmm0
0x18007ae17  mov     [rbp+57h+var_98], r11
0x18007ae1b  mov     rcx, r14
0x18007ae1e  mov     [rbp+57h+var_68], r15
0x18007ae22  lea     r8, [rbp+57h+var_68]
0x18007ae26  mov     r13, r9
0x18007ae29  movdqu  [rbp+57h+var_80], xmm0
0x18007ae2e  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007ae33  test    r13, r13
0x18007ae36  jz      short loc_18007AE3C
0x18007ae38  mov     [r13+0], r15d
0x18007ae3c  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007ae43  test    rdx, rdx
0x18007ae46  jz      loc_18007B471
0x18007ae4c  mov     rcx, [rsi+18h]
0x18007ae50  call    RtlIsTypeSafeHandleValid
0x18007ae55  test    al, al
0x18007ae57  jz      loc_18007B471
0x18007ae5d  test    r14, r14
0x18007ae60  jnz     short loc_18007AE80
0x18007ae62  lea     rcx, [rbp+57h+var_98]
0x18007ae66  mov     [rbp+57h+var_90], 516Bh
0x18007ae6d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007ae72  lea     rcx, [rbp+57h+var_80]
0x18007ae76  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007ae7b  jmp     loc_18007B48E
0x18007ae80  test    r13, r13
0x18007ae83  jnz     short loc_18007AEAD
0x18007ae85  cmp     edi, 1
0x18007ae88  jz      short loc_18007AEAD
0x18007ae8a  mov     ebx, 80004003h
0x18007ae8f  mov     edx, 516Ch; char *
0x18007ae94  mov     r8d, ebx; int
0x18007ae97  mov     rcx, r11; this
0x18007ae9a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007ae9f  lea     rcx, [rbp+57h+var_80]
0x18007aea3  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007aea8  jmp     loc_18007B491
0x18007aead  mov     r8d, edi
0x18007aeb0  lea     rdx, [rbp+57h+arg_8]
0x18007aeb4  lea     rcx, [rbp+57h+var_80]
0x18007aeb8  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007aebd  mov     ebx, [rax]
0x18007aebf  test    ebx, ebx
0x18007aec1  jns     short loc_18007AF1C
0x18007aec3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007aec9  jnz     short loc_18007AED1
0x18007aecb  call    cs:__imp_DebugBreak
0x18007aed1  mov     r9d, ebx; int
0x18007aed4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007aedb  mov     r8d, 5170h; char *
0x18007aee1  lea     rcx, aStatusPropagat; "Status propagated"
0x18007aee8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007aeed  mov     ecx, ebx; this
0x18007aeef  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007aef4  mov     ebx, eax
0x18007aef6  mov     esi, r15d
0x18007aef9  test    edi, edi
0x18007aefb  jz      short loc_18007AE9F
0x18007aefd  mov     ecx, esi
0x18007aeff  mov     rcx, [r14+rcx*8]
0x18007af03  test    rcx, rcx
0x18007af06  jz      short loc_18007AF14
0x18007af08  mov     rdx, [rcx]
0x18007af0b  mov     rax, [rdx+10h]
0x18007af0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af14  inc     esi
0x18007af16  cmp     esi, edi
0x18007af18  jb      short loc_18007AEFD
0x18007af1a  jmp     short loc_18007AE9F
0x18007af1c  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007af1f  xorps   xmm0, xmm0
0x18007af22  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007af25  mov     r10, [rsi+18h]
0x18007af29  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007af2d  xor     esi, esi
0x18007af2f  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007af33  mov     [rbp+57h+arg_8], eax
0x18007af36  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007af39  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007af40  mov     [rbp+57h+var_98], rax
0x18007af44  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007af4b  mov     [rbp+57h+var_60], rsi
0x18007af4f  movdqu  [rbp+57h+var_58], xmm0
0x18007af54  test    r15, r15
0x18007af57  jz      short loc_18007AF85
0x18007af59  mov     ecx, esi
0x18007af5b  test    edi, edi
0x18007af5d  jz      short loc_18007AF85
0x18007af5f  mov     rax, rcx
0x18007af62  inc     rcx
0x18007af65  shl     rax, 5
0x18007af69  mov     [rax+r15], rsi
0x18007af6d  mov     [rax+r15+8], rsi
0x18007af72  mov     [rax+r15+10h], rsi
0x18007af77  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007af80  cmp     rcx, rdi
0x18007af83  jb      short loc_18007AF5F
0x18007af85  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007af8c  test    rdx, rdx
0x18007af8f  jz      loc_18007B0CD
0x18007af95  mov     rcx, r10
0x18007af98  call    RtlIsTypeSafeHandleValid
0x18007af9d  test    al, al
0x18007af9f  jz      loc_18007B0CD
0x18007afa5  test    r15, r15
0x18007afa8  jnz     short loc_18007AFBA
0x18007afaa  test    edi, edi
0x18007afac  jz      short loc_18007AFBA
0x18007afae  mov     [rbp+57h+var_90], 478h
0x18007afb5  jmp     loc_18007B0D4
0x18007afba  mov     rdx, r10
0x18007afbd  lea     rcx, [rbp+57h+var_60]
0x18007afc1  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007afc6  mov     ebx, eax
0x18007afc8  test    eax, eax
0x18007afca  jns     short loc_18007AFF2
0x18007afcc  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007afd0  test    rdx, rdx
0x18007afd3  jz      loc_18007B0E0
0x18007afd9  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007afe0  mov     rax, [rcx+30h]
0x18007afe4  mov     rcx, [rbp+57h+var_60]
0x18007afe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007afed  jmp     loc_18007B0E0
0x18007aff2  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007aff6  mov     rax, [rcx+20h]
0x18007affa  cmp     [rcx+28h], rax
0x18007affe  jbe     short loc_18007B036
0x18007b000  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007b004  mov     [rbp+57h+var_90], 47Dh
0x18007b00b  test    rdx, rdx
0x18007b00e  jz      short loc_18007B024
0x18007b010  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b017  mov     rcx, [rbp+57h+var_60]
0x18007b01b  mov     rax, [rax+30h]
0x18007b01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b024  lea     rdx, [rbp+57h+var_98]
0x18007b028  lea     rcx, [rbp+57h+var_98]
0x18007b02c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007b031  jmp     loc_18007B0DD
0x18007b036  test    edi, edi
0x18007b038  jz      short loc_18007B0B2
0x18007b03a  mov     r9, [rcx+28h]
0x18007b03e  cmp     r9, [rcx+20h]
0x18007b042  jnb     short loc_18007B0B2
0x18007b044  mov     rdx, [rcx+30h]
0x18007b048  mov     rax, rsi
0x18007b04b  mov     rcx, [rcx+8]
0x18007b04f  shl     rax, 5
0x18007b053  add     r15, rax
0x18007b056  mov     edx, [rdx+r9*4]
0x18007b05a  mov     r8, r15
0x18007b05d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007b062  mov     ebx, eax
0x18007b064  test    eax, eax
0x18007b066  js      short loc_18007B091
0x18007b068  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007b06c  inc     rsi
0x18007b06f  mov     rcx, [rdx+28h]
0x18007b073  mov     rax, [rdx+38h]
0x18007b077  mov     ecx, [rax+rcx*4]
0x18007b07a  mov     [r15+18h], ecx
0x18007b07e  inc     qword ptr [rdx+28h]
0x18007b082  cmp     rsi, rdi
0x18007b085  jnb     short loc_18007B0B2
0x18007b087  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007b08b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007b08f  jmp     short loc_18007B03A
0x18007b091  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007b095  test    rdx, rdx
0x18007b098  jz      short loc_18007B0AE
0x18007b09a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b0a1  mov     rcx, [rbp+57h+var_60]
0x18007b0a5  mov     rax, [rax+30h]
0x18007b0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b0ae  xor     esi, esi
0x18007b0b0  jmp     short loc_18007B0E0
0x18007b0b2  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007b0b6  xor     ebx, ebx
0x18007b0b8  test    rdx, rdx
0x18007b0bb  jz      short loc_18007B0E0
0x18007b0bd  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007b0c4  mov     rax, [rax+30h]
0x18007b0c8  jmp     loc_18007AFE4
0x18007b0cd  mov     [rbp+57h+var_90], 477h
0x18007b0d4  lea     rcx, [rbp+57h+var_98]
0x18007b0d8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007b0dd  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007b0e0  test    ebx, ebx
0x18007b0e2  jns     short loc_18007B141
0x18007b0e4  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007b0ea  jnz     short loc_18007B0F2
0x18007b0ec  call    cs:__imp_DebugBreak
0x18007b0f2  mov     r9d, ebx; int
0x18007b0f5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007b0fc  mov     r8d, 5171h; char *
0x18007b102  lea     rcx, aStatusPropagat; "Status propagated"
0x18007b109  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007b10e  mov     ecx, ebx; this
0x18007b110  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007b115  xor     esi, esi
0x18007b117  mov     ebx, eax
0x18007b119  test    edi, edi
0x18007b11b  jz      loc_18007AE9F
0x18007b121  mov     rcx, [r14+rsi*8]
0x18007b125  test    rcx, rcx
0x18007b128  jz      short loc_18007B136
0x18007b12a  mov     rax, [rcx]
0x18007b12d  mov     rax, [rax+10h]
0x18007b131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b136  inc     esi
0x18007b138  cmp     esi, edi
0x18007b13a  jb      short loc_18007B121
0x18007b13c  jmp     loc_18007AE9F
0x18007b141  xor     r15d, r15d
0x18007b144  test    rsi, rsi
0x18007b147  jz      loc_18007B264
0x18007b14d  lea     rdx, [rbp+57h+var_48]
0x18007b151  mov     [rbp+57h+var_A0], 0
0x18007b159  lea     rcx, [rbp+57h+var_A0]
0x18007b15d  mov     [rbp+57h+var_68], 0
0x18007b165  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCFileAssociationEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CFileAssociationEntry>>>::Allocate(void)
0x18007b16a  mov     ebx, [rax]
0x18007b16c  test    ebx, ebx
0x18007b16e  js      loc_18007B3ED
0x18007b174  mov     eax, [rbp+57h+arg_8]
0x18007b177  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007b17b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007b17e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007b182  mov     [rbp+57h+arg_8], eax
0x18007b185  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007b188  mov     eax, r15d
0x18007b18b  shl     rax, 5
0x18007b18f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007b193  mov     rcx, rax; this
0x18007b196  mov     [rbp+57h+var_40], rax
0x18007b19a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007b19f  mov     ebx, eax
0x18007b1a1  test    eax, eax
0x18007b1a3  js      loc_18007B3A6
0x18007b1a9  mov     eax, [rbp+57h+arg_8]
0x18007b1ac  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007b1af  mov     r8, [rbp+57h+var_40]
0x18007b1b3  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007b1b7  mov     r9, [rbp+57h+var_68]
0x18007b1bb  mov     rcx, [rbp+57h+var_A0]
0x18007b1bf  mov     r8d, [r8+18h]
0x18007b1c3  mov     [rbp+57h+arg_8], eax
0x18007b1c6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007b1c9  mov     rax, [rbp+57h+arg_0]
0x18007b1cd  mov     rdx, [rax+10h]
0x18007b1d1  call    ?Initialize@CFileAssociationEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CFileAssociationEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007b1d6  mov     ebx, eax
0x18007b1d8  test    eax, eax
0x18007b1da  js      loc_18007B35F
0x18007b1e0  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007b1e7  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007b1ee  mov     [rbp+57h+var_98], rax
0x18007b1f2  cmp     r15d, edi
0x18007b1f5  jb      short loc_18007B213
0x18007b1f7  xor     r13d, r13d
0x18007b1fa  mov     [rbp+57h+var_90], 28h ; '('
0x18007b201  lea     rdx, [rbp+57h+var_98]
0x18007b205  lea     rcx, [rbp+57h+var_98]
0x18007b209  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007b20e  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007b211  jmp     short loc_18007B219
0x18007b213  lea     r13, [r14+r15*8]
0x18007b217  xor     ebx, ebx
0x18007b219  test    ebx, ebx
0x18007b21b  js      loc_18007B2F9
0x18007b221  mov     rcx, [rbp+57h+var_A0]
0x18007b225  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007b22c  mov     r8, r13
0x18007b22f  mov     rax, [rcx]
0x18007b232  mov     rax, [rax]
0x18007b235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b23a  mov     ebx, eax
  ... truncated ...
```
