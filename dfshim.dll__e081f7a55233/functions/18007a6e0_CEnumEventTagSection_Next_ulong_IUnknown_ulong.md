# CEnumEventTagSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007a6e0`
- end: `0x18007adbe`
- name: `?Next@CEnumEventTagSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumEventTagSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

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
- `0x180058298`
- `0x18005b4c4`
- `0x18005df30`
- `0x180069ce8`
- `0x18007a6e0`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a7db`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a9fc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ab98`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ac11`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ad05`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a7db`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a9fc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ab98`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ac11`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ad05`

## string_xrefs

- `0x18007a849`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007a719`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a7e4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007aa05`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007aaf7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007aba4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007abc5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ac1a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ac72`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007acb9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ad0e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumEventTagSection::Next(
        CEnumEventTagSection *this,
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
    v59 = 22861;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 22862;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x594F, -2147467261, v8);
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
      (const char *)0x5953,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::Allocate(
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
            (const char *)0x595D,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>(&v57);
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
        v38 = CEventTagEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x595E,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>(&v57);
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
            (const char *)0x595F,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>(&v57);
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
            (const char *)0x5960,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>(&v57);
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
        (const char *)0x595C,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>(&v57);
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
          (const char *)0x5968,
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
      (const char *)0x5954,
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
0x18007a6e0  mov     rax, rsp
0x18007a6e3  mov     [rax+18h], rbx
0x18007a6e7  mov     [rax+20h], r9
0x18007a6eb  mov     [rax+8], rcx
0x18007a6ef  push    rbp
0x18007a6f0  push    rsi
0x18007a6f1  push    rdi
0x18007a6f2  push    r12
0x18007a6f4  push    r13
0x18007a6f6  push    r14
0x18007a6f8  push    r15
0x18007a6fa  lea     rbp, [rax-5Fh]
0x18007a6fe  sub     rsp, 90h
0x18007a705  mov     r14, r8
0x18007a708  mov     edi, edx
0x18007a70a  mov     rsi, rcx
0x18007a70d  mov     edx, edx
0x18007a70f  xor     r15d, r15d
0x18007a712  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007a719  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a720  mov     [rbp+57h+var_70], r15
0x18007a724  xorps   xmm0, xmm0
0x18007a727  mov     [rbp+57h+var_98], r11
0x18007a72b  mov     rcx, r14
0x18007a72e  mov     [rbp+57h+var_68], r15
0x18007a732  lea     r8, [rbp+57h+var_68]
0x18007a736  mov     r13, r9
0x18007a739  movdqu  [rbp+57h+var_80], xmm0
0x18007a73e  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007a743  test    r13, r13
0x18007a746  jz      short loc_18007A74C
0x18007a748  mov     [r13+0], r15d
0x18007a74c  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007a753  test    rdx, rdx
0x18007a756  jz      loc_18007AD81
0x18007a75c  mov     rcx, [rsi+18h]
0x18007a760  call    RtlIsTypeSafeHandleValid
0x18007a765  test    al, al
0x18007a767  jz      loc_18007AD81
0x18007a76d  test    r14, r14
0x18007a770  jnz     short loc_18007A790
0x18007a772  lea     rcx, [rbp+57h+var_98]
0x18007a776  mov     [rbp+57h+var_90], 594Eh
0x18007a77d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007a782  lea     rcx, [rbp+57h+var_80]
0x18007a786  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007a78b  jmp     loc_18007AD9E
0x18007a790  test    r13, r13
0x18007a793  jnz     short loc_18007A7BD
0x18007a795  cmp     edi, 1
0x18007a798  jz      short loc_18007A7BD
0x18007a79a  mov     ebx, 80004003h
0x18007a79f  mov     edx, 594Fh; char *
0x18007a7a4  mov     r8d, ebx; int
0x18007a7a7  mov     rcx, r11; this
0x18007a7aa  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007a7af  lea     rcx, [rbp+57h+var_80]
0x18007a7b3  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007a7b8  jmp     loc_18007ADA1
0x18007a7bd  mov     r8d, edi
0x18007a7c0  lea     rdx, [rbp+57h+arg_8]
0x18007a7c4  lea     rcx, [rbp+57h+var_80]
0x18007a7c8  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007a7cd  mov     ebx, [rax]
0x18007a7cf  test    ebx, ebx
0x18007a7d1  jns     short loc_18007A82C
0x18007a7d3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007a7d9  jnz     short loc_18007A7E1
0x18007a7db  call    cs:__imp_DebugBreak
0x18007a7e1  mov     r9d, ebx; int
0x18007a7e4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a7eb  mov     r8d, 5953h; char *
0x18007a7f1  lea     rcx, aStatusPropagat; "Status propagated"
0x18007a7f8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007a7fd  mov     ecx, ebx; this
0x18007a7ff  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007a804  mov     ebx, eax
0x18007a806  mov     esi, r15d
0x18007a809  test    edi, edi
0x18007a80b  jz      short loc_18007A7AF
0x18007a80d  mov     ecx, esi
0x18007a80f  mov     rcx, [r14+rcx*8]
0x18007a813  test    rcx, rcx
0x18007a816  jz      short loc_18007A824
0x18007a818  mov     rdx, [rcx]
0x18007a81b  mov     rax, [rdx+10h]
0x18007a81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a824  inc     esi
0x18007a826  cmp     esi, edi
0x18007a828  jb      short loc_18007A80D
0x18007a82a  jmp     short loc_18007A7AF
0x18007a82c  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007a82f  xorps   xmm0, xmm0
0x18007a832  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007a835  mov     r10, [rsi+18h]
0x18007a839  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007a83d  xor     esi, esi
0x18007a83f  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007a843  mov     [rbp+57h+arg_8], eax
0x18007a846  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007a849  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a850  mov     [rbp+57h+var_98], rax
0x18007a854  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007a85b  mov     [rbp+57h+var_60], rsi
0x18007a85f  movdqu  [rbp+57h+var_58], xmm0
0x18007a864  test    r15, r15
0x18007a867  jz      short loc_18007A895
0x18007a869  mov     ecx, esi
0x18007a86b  test    edi, edi
0x18007a86d  jz      short loc_18007A895
0x18007a86f  mov     rax, rcx
0x18007a872  inc     rcx
0x18007a875  shl     rax, 5
0x18007a879  mov     [rax+r15], rsi
0x18007a87d  mov     [rax+r15+8], rsi
0x18007a882  mov     [rax+r15+10h], rsi
0x18007a887  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007a890  cmp     rcx, rdi
0x18007a893  jb      short loc_18007A86F
0x18007a895  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007a89c  test    rdx, rdx
0x18007a89f  jz      loc_18007A9DD
0x18007a8a5  mov     rcx, r10
0x18007a8a8  call    RtlIsTypeSafeHandleValid
0x18007a8ad  test    al, al
0x18007a8af  jz      loc_18007A9DD
0x18007a8b5  test    r15, r15
0x18007a8b8  jnz     short loc_18007A8CA
0x18007a8ba  test    edi, edi
0x18007a8bc  jz      short loc_18007A8CA
0x18007a8be  mov     [rbp+57h+var_90], 478h
0x18007a8c5  jmp     loc_18007A9E4
0x18007a8ca  mov     rdx, r10
0x18007a8cd  lea     rcx, [rbp+57h+var_60]
0x18007a8d1  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007a8d6  mov     ebx, eax
0x18007a8d8  test    eax, eax
0x18007a8da  jns     short loc_18007A902
0x18007a8dc  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007a8e0  test    rdx, rdx
0x18007a8e3  jz      loc_18007A9F0
0x18007a8e9  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007a8f0  mov     rax, [rcx+30h]
0x18007a8f4  mov     rcx, [rbp+57h+var_60]
0x18007a8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a8fd  jmp     loc_18007A9F0
0x18007a902  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007a906  mov     rax, [rcx+20h]
0x18007a90a  cmp     [rcx+28h], rax
0x18007a90e  jbe     short loc_18007A946
0x18007a910  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007a914  mov     [rbp+57h+var_90], 47Dh
0x18007a91b  test    rdx, rdx
0x18007a91e  jz      short loc_18007A934
0x18007a920  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007a927  mov     rcx, [rbp+57h+var_60]
0x18007a92b  mov     rax, [rax+30h]
0x18007a92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a934  lea     rdx, [rbp+57h+var_98]
0x18007a938  lea     rcx, [rbp+57h+var_98]
0x18007a93c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007a941  jmp     loc_18007A9ED
0x18007a946  test    edi, edi
0x18007a948  jz      short loc_18007A9C2
0x18007a94a  mov     r9, [rcx+28h]
0x18007a94e  cmp     r9, [rcx+20h]
0x18007a952  jnb     short loc_18007A9C2
0x18007a954  mov     rdx, [rcx+30h]
0x18007a958  mov     rax, rsi
0x18007a95b  mov     rcx, [rcx+8]
0x18007a95f  shl     rax, 5
0x18007a963  add     r15, rax
0x18007a966  mov     edx, [rdx+r9*4]
0x18007a96a  mov     r8, r15
0x18007a96d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007a972  mov     ebx, eax
0x18007a974  test    eax, eax
0x18007a976  js      short loc_18007A9A1
0x18007a978  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007a97c  inc     rsi
0x18007a97f  mov     rcx, [rdx+28h]
0x18007a983  mov     rax, [rdx+38h]
0x18007a987  mov     ecx, [rax+rcx*4]
0x18007a98a  mov     [r15+18h], ecx
0x18007a98e  inc     qword ptr [rdx+28h]
0x18007a992  cmp     rsi, rdi
0x18007a995  jnb     short loc_18007A9C2
0x18007a997  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007a99b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007a99f  jmp     short loc_18007A94A
0x18007a9a1  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007a9a5  test    rdx, rdx
0x18007a9a8  jz      short loc_18007A9BE
0x18007a9aa  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007a9b1  mov     rcx, [rbp+57h+var_60]
0x18007a9b5  mov     rax, [rax+30h]
0x18007a9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a9be  xor     esi, esi
0x18007a9c0  jmp     short loc_18007A9F0
0x18007a9c2  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007a9c6  xor     ebx, ebx
0x18007a9c8  test    rdx, rdx
0x18007a9cb  jz      short loc_18007A9F0
0x18007a9cd  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007a9d4  mov     rax, [rax+30h]
0x18007a9d8  jmp     loc_18007A8F4
0x18007a9dd  mov     [rbp+57h+var_90], 477h
0x18007a9e4  lea     rcx, [rbp+57h+var_98]
0x18007a9e8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007a9ed  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007a9f0  test    ebx, ebx
0x18007a9f2  jns     short loc_18007AA51
0x18007a9f4  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007a9fa  jnz     short loc_18007AA02
0x18007a9fc  call    cs:__imp_DebugBreak
0x18007aa02  mov     r9d, ebx; int
0x18007aa05  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007aa0c  mov     r8d, 5954h; char *
0x18007aa12  lea     rcx, aStatusPropagat; "Status propagated"
0x18007aa19  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007aa1e  mov     ecx, ebx; this
0x18007aa20  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007aa25  xor     esi, esi
0x18007aa27  mov     ebx, eax
0x18007aa29  test    edi, edi
0x18007aa2b  jz      loc_18007A7AF
0x18007aa31  mov     rcx, [r14+rsi*8]
0x18007aa35  test    rcx, rcx
0x18007aa38  jz      short loc_18007AA46
0x18007aa3a  mov     rax, [rcx]
0x18007aa3d  mov     rax, [rax+10h]
0x18007aa41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa46  inc     esi
0x18007aa48  cmp     esi, edi
0x18007aa4a  jb      short loc_18007AA31
0x18007aa4c  jmp     loc_18007A7AF
0x18007aa51  xor     r15d, r15d
0x18007aa54  test    rsi, rsi
0x18007aa57  jz      loc_18007AB74
0x18007aa5d  lea     rdx, [rbp+57h+var_48]
0x18007aa61  mov     [rbp+57h+var_A0], 0
0x18007aa69  lea     rcx, [rbp+57h+var_A0]
0x18007aa6d  mov     [rbp+57h+var_68], 0
0x18007aa75  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventTagEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventTagEntry>>>::Allocate(void)
0x18007aa7a  mov     ebx, [rax]
0x18007aa7c  test    ebx, ebx
0x18007aa7e  js      loc_18007ACFD
0x18007aa84  mov     eax, [rbp+57h+arg_8]
0x18007aa87  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007aa8b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007aa8e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007aa92  mov     [rbp+57h+arg_8], eax
0x18007aa95  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007aa98  mov     eax, r15d
0x18007aa9b  shl     rax, 5
0x18007aa9f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007aaa3  mov     rcx, rax; this
0x18007aaa6  mov     [rbp+57h+var_40], rax
0x18007aaaa  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007aaaf  mov     ebx, eax
0x18007aab1  test    eax, eax
0x18007aab3  js      loc_18007ACB6
0x18007aab9  mov     eax, [rbp+57h+arg_8]
0x18007aabc  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007aabf  mov     r8, [rbp+57h+var_40]
0x18007aac3  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007aac7  mov     r9, [rbp+57h+var_68]
0x18007aacb  mov     rcx, [rbp+57h+var_A0]
0x18007aacf  mov     r8d, [r8+18h]
0x18007aad3  mov     [rbp+57h+arg_8], eax
0x18007aad6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007aad9  mov     rax, [rbp+57h+arg_0]
0x18007aadd  mov     rdx, [rax+10h]
0x18007aae1  call    ?Initialize@CEventTagEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CEventTagEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007aae6  mov     ebx, eax
0x18007aae8  test    eax, eax
0x18007aaea  js      loc_18007AC6F
0x18007aaf0  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007aaf7  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007aafe  mov     [rbp+57h+var_98], rax
0x18007ab02  cmp     r15d, edi
0x18007ab05  jb      short loc_18007AB23
0x18007ab07  xor     r13d, r13d
0x18007ab0a  mov     [rbp+57h+var_90], 28h ; '('
0x18007ab11  lea     rdx, [rbp+57h+var_98]
0x18007ab15  lea     rcx, [rbp+57h+var_98]
0x18007ab19  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007ab1e  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007ab21  jmp     short loc_18007AB29
0x18007ab23  lea     r13, [r14+r15*8]
0x18007ab27  xor     ebx, ebx
0x18007ab29  test    ebx, ebx
0x18007ab2b  js      loc_18007AC09
0x18007ab31  mov     rcx, [rbp+57h+var_A0]
0x18007ab35  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007ab3c  mov     r8, r13
0x18007ab3f  mov     rax, [rcx]
0x18007ab42  mov     rax, [rax]
0x18007ab45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab4a  mov     ebx, eax
  ... truncated ...
```
