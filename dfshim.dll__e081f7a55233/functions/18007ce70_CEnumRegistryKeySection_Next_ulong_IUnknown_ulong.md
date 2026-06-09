# CEnumRegistryKeySection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007ce70`
- end: `0x18007d54e`
- name: `?Next@CEnumRegistryKeySection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumRegistryKeySection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

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
- `0x180058618`
- `0x18005bd9c`
- `0x18005df30`
- `0x18006a930`
- `0x18007ce70`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007cf6b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d18c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d328`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d3a1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d495`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007cf6b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d18c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d328`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d3a1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d495`

## string_xrefs

- `0x18007cfd9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007cea9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007cf74`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d195`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d287`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d334`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d355`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d3aa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d402`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d449`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d49e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumRegistryKeySection::Next(
        CEnumRegistryKeySection *this,
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
    v59 = 23085;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 23086;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x5A2F, -2147467261, v8);
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
      (const char *)0x5A33,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::Allocate(
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
            (const char *)0x5A3D,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>(&v57);
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
        v38 = CRegistryKeyEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x5A3E,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>(&v57);
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
            (const char *)0x5A3F,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>(&v57);
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
            (const char *)0x5A40,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>(&v57);
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
        (const char *)0x5A3C,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>(&v57);
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
          (const char *)0x5A48,
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
      (const char *)0x5A34,
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
0x18007ce70  mov     rax, rsp
0x18007ce73  mov     [rax+18h], rbx
0x18007ce77  mov     [rax+20h], r9
0x18007ce7b  mov     [rax+8], rcx
0x18007ce7f  push    rbp
0x18007ce80  push    rsi
0x18007ce81  push    rdi
0x18007ce82  push    r12
0x18007ce84  push    r13
0x18007ce86  push    r14
0x18007ce88  push    r15
0x18007ce8a  lea     rbp, [rax-5Fh]
0x18007ce8e  sub     rsp, 90h
0x18007ce95  mov     r14, r8
0x18007ce98  mov     edi, edx
0x18007ce9a  mov     rsi, rcx
0x18007ce9d  mov     edx, edx
0x18007ce9f  xor     r15d, r15d
0x18007cea2  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007cea9  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007ceb0  mov     [rbp+57h+var_70], r15
0x18007ceb4  xorps   xmm0, xmm0
0x18007ceb7  mov     [rbp+57h+var_98], r11
0x18007cebb  mov     rcx, r14
0x18007cebe  mov     [rbp+57h+var_68], r15
0x18007cec2  lea     r8, [rbp+57h+var_68]
0x18007cec6  mov     r13, r9
0x18007cec9  movdqu  [rbp+57h+var_80], xmm0
0x18007cece  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007ced3  test    r13, r13
0x18007ced6  jz      short loc_18007CEDC
0x18007ced8  mov     [r13+0], r15d
0x18007cedc  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007cee3  test    rdx, rdx
0x18007cee6  jz      loc_18007D511
0x18007ceec  mov     rcx, [rsi+18h]
0x18007cef0  call    RtlIsTypeSafeHandleValid
0x18007cef5  test    al, al
0x18007cef7  jz      loc_18007D511
0x18007cefd  test    r14, r14
0x18007cf00  jnz     short loc_18007CF20
0x18007cf02  lea     rcx, [rbp+57h+var_98]
0x18007cf06  mov     [rbp+57h+var_90], 5A2Eh
0x18007cf0d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007cf12  lea     rcx, [rbp+57h+var_80]
0x18007cf16  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007cf1b  jmp     loc_18007D52E
0x18007cf20  test    r13, r13
0x18007cf23  jnz     short loc_18007CF4D
0x18007cf25  cmp     edi, 1
0x18007cf28  jz      short loc_18007CF4D
0x18007cf2a  mov     ebx, 80004003h
0x18007cf2f  mov     edx, 5A2Fh; char *
0x18007cf34  mov     r8d, ebx; int
0x18007cf37  mov     rcx, r11; this
0x18007cf3a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007cf3f  lea     rcx, [rbp+57h+var_80]
0x18007cf43  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007cf48  jmp     loc_18007D531
0x18007cf4d  mov     r8d, edi
0x18007cf50  lea     rdx, [rbp+57h+arg_8]
0x18007cf54  lea     rcx, [rbp+57h+var_80]
0x18007cf58  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007cf5d  mov     ebx, [rax]
0x18007cf5f  test    ebx, ebx
0x18007cf61  jns     short loc_18007CFBC
0x18007cf63  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007cf69  jnz     short loc_18007CF71
0x18007cf6b  call    cs:__imp_DebugBreak
0x18007cf71  mov     r9d, ebx; int
0x18007cf74  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007cf7b  mov     r8d, 5A33h; char *
0x18007cf81  lea     rcx, aStatusPropagat; "Status propagated"
0x18007cf88  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007cf8d  mov     ecx, ebx; this
0x18007cf8f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007cf94  mov     ebx, eax
0x18007cf96  mov     esi, r15d
0x18007cf99  test    edi, edi
0x18007cf9b  jz      short loc_18007CF3F
0x18007cf9d  mov     ecx, esi
0x18007cf9f  mov     rcx, [r14+rcx*8]
0x18007cfa3  test    rcx, rcx
0x18007cfa6  jz      short loc_18007CFB4
0x18007cfa8  mov     rdx, [rcx]
0x18007cfab  mov     rax, [rdx+10h]
0x18007cfaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfb4  inc     esi
0x18007cfb6  cmp     esi, edi
0x18007cfb8  jb      short loc_18007CF9D
0x18007cfba  jmp     short loc_18007CF3F
0x18007cfbc  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007cfbf  xorps   xmm0, xmm0
0x18007cfc2  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007cfc5  mov     r10, [rsi+18h]
0x18007cfc9  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007cfcd  xor     esi, esi
0x18007cfcf  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007cfd3  mov     [rbp+57h+arg_8], eax
0x18007cfd6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007cfd9  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007cfe0  mov     [rbp+57h+var_98], rax
0x18007cfe4  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007cfeb  mov     [rbp+57h+var_60], rsi
0x18007cfef  movdqu  [rbp+57h+var_58], xmm0
0x18007cff4  test    r15, r15
0x18007cff7  jz      short loc_18007D025
0x18007cff9  mov     ecx, esi
0x18007cffb  test    edi, edi
0x18007cffd  jz      short loc_18007D025
0x18007cfff  mov     rax, rcx
0x18007d002  inc     rcx
0x18007d005  shl     rax, 5
0x18007d009  mov     [rax+r15], rsi
0x18007d00d  mov     [rax+r15+8], rsi
0x18007d012  mov     [rax+r15+10h], rsi
0x18007d017  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007d020  cmp     rcx, rdi
0x18007d023  jb      short loc_18007CFFF
0x18007d025  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d02c  test    rdx, rdx
0x18007d02f  jz      loc_18007D16D
0x18007d035  mov     rcx, r10
0x18007d038  call    RtlIsTypeSafeHandleValid
0x18007d03d  test    al, al
0x18007d03f  jz      loc_18007D16D
0x18007d045  test    r15, r15
0x18007d048  jnz     short loc_18007D05A
0x18007d04a  test    edi, edi
0x18007d04c  jz      short loc_18007D05A
0x18007d04e  mov     [rbp+57h+var_90], 478h
0x18007d055  jmp     loc_18007D174
0x18007d05a  mov     rdx, r10
0x18007d05d  lea     rcx, [rbp+57h+var_60]
0x18007d061  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007d066  mov     ebx, eax
0x18007d068  test    eax, eax
0x18007d06a  jns     short loc_18007D092
0x18007d06c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007d070  test    rdx, rdx
0x18007d073  jz      loc_18007D180
0x18007d079  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d080  mov     rax, [rcx+30h]
0x18007d084  mov     rcx, [rbp+57h+var_60]
0x18007d088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d08d  jmp     loc_18007D180
0x18007d092  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007d096  mov     rax, [rcx+20h]
0x18007d09a  cmp     [rcx+28h], rax
0x18007d09e  jbe     short loc_18007D0D6
0x18007d0a0  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007d0a4  mov     [rbp+57h+var_90], 47Dh
0x18007d0ab  test    rdx, rdx
0x18007d0ae  jz      short loc_18007D0C4
0x18007d0b0  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d0b7  mov     rcx, [rbp+57h+var_60]
0x18007d0bb  mov     rax, [rax+30h]
0x18007d0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d0c4  lea     rdx, [rbp+57h+var_98]
0x18007d0c8  lea     rcx, [rbp+57h+var_98]
0x18007d0cc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007d0d1  jmp     loc_18007D17D
0x18007d0d6  test    edi, edi
0x18007d0d8  jz      short loc_18007D152
0x18007d0da  mov     r9, [rcx+28h]
0x18007d0de  cmp     r9, [rcx+20h]
0x18007d0e2  jnb     short loc_18007D152
0x18007d0e4  mov     rdx, [rcx+30h]
0x18007d0e8  mov     rax, rsi
0x18007d0eb  mov     rcx, [rcx+8]
0x18007d0ef  shl     rax, 5
0x18007d0f3  add     r15, rax
0x18007d0f6  mov     edx, [rdx+r9*4]
0x18007d0fa  mov     r8, r15
0x18007d0fd  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007d102  mov     ebx, eax
0x18007d104  test    eax, eax
0x18007d106  js      short loc_18007D131
0x18007d108  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007d10c  inc     rsi
0x18007d10f  mov     rcx, [rdx+28h]
0x18007d113  mov     rax, [rdx+38h]
0x18007d117  mov     ecx, [rax+rcx*4]
0x18007d11a  mov     [r15+18h], ecx
0x18007d11e  inc     qword ptr [rdx+28h]
0x18007d122  cmp     rsi, rdi
0x18007d125  jnb     short loc_18007D152
0x18007d127  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007d12b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007d12f  jmp     short loc_18007D0DA
0x18007d131  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007d135  test    rdx, rdx
0x18007d138  jz      short loc_18007D14E
0x18007d13a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d141  mov     rcx, [rbp+57h+var_60]
0x18007d145  mov     rax, [rax+30h]
0x18007d149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d14e  xor     esi, esi
0x18007d150  jmp     short loc_18007D180
0x18007d152  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007d156  xor     ebx, ebx
0x18007d158  test    rdx, rdx
0x18007d15b  jz      short loc_18007D180
0x18007d15d  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d164  mov     rax, [rax+30h]
0x18007d168  jmp     loc_18007D084
0x18007d16d  mov     [rbp+57h+var_90], 477h
0x18007d174  lea     rcx, [rbp+57h+var_98]
0x18007d178  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007d17d  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007d180  test    ebx, ebx
0x18007d182  jns     short loc_18007D1E1
0x18007d184  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007d18a  jnz     short loc_18007D192
0x18007d18c  call    cs:__imp_DebugBreak
0x18007d192  mov     r9d, ebx; int
0x18007d195  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007d19c  mov     r8d, 5A34h; char *
0x18007d1a2  lea     rcx, aStatusPropagat; "Status propagated"
0x18007d1a9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007d1ae  mov     ecx, ebx; this
0x18007d1b0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007d1b5  xor     esi, esi
0x18007d1b7  mov     ebx, eax
0x18007d1b9  test    edi, edi
0x18007d1bb  jz      loc_18007CF3F
0x18007d1c1  mov     rcx, [r14+rsi*8]
0x18007d1c5  test    rcx, rcx
0x18007d1c8  jz      short loc_18007D1D6
0x18007d1ca  mov     rax, [rcx]
0x18007d1cd  mov     rax, [rax+10h]
0x18007d1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d1d6  inc     esi
0x18007d1d8  cmp     esi, edi
0x18007d1da  jb      short loc_18007D1C1
0x18007d1dc  jmp     loc_18007CF3F
0x18007d1e1  xor     r15d, r15d
0x18007d1e4  test    rsi, rsi
0x18007d1e7  jz      loc_18007D304
0x18007d1ed  lea     rdx, [rbp+57h+var_48]
0x18007d1f1  mov     [rbp+57h+var_A0], 0
0x18007d1f9  lea     rcx, [rbp+57h+var_A0]
0x18007d1fd  mov     [rbp+57h+var_68], 0
0x18007d205  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCRegistryKeyEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CRegistryKeyEntry>>>::Allocate(void)
0x18007d20a  mov     ebx, [rax]
0x18007d20c  test    ebx, ebx
0x18007d20e  js      loc_18007D48D
0x18007d214  mov     eax, [rbp+57h+arg_8]
0x18007d217  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007d21b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007d21e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007d222  mov     [rbp+57h+arg_8], eax
0x18007d225  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007d228  mov     eax, r15d
0x18007d22b  shl     rax, 5
0x18007d22f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007d233  mov     rcx, rax; this
0x18007d236  mov     [rbp+57h+var_40], rax
0x18007d23a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007d23f  mov     ebx, eax
0x18007d241  test    eax, eax
0x18007d243  js      loc_18007D446
0x18007d249  mov     eax, [rbp+57h+arg_8]
0x18007d24c  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007d24f  mov     r8, [rbp+57h+var_40]
0x18007d253  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007d257  mov     r9, [rbp+57h+var_68]
0x18007d25b  mov     rcx, [rbp+57h+var_A0]
0x18007d25f  mov     r8d, [r8+18h]
0x18007d263  mov     [rbp+57h+arg_8], eax
0x18007d266  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007d269  mov     rax, [rbp+57h+arg_0]
0x18007d26d  mov     rdx, [rax+10h]
0x18007d271  call    ?Initialize@CRegistryKeyEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CRegistryKeyEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007d276  mov     ebx, eax
0x18007d278  test    eax, eax
0x18007d27a  js      loc_18007D3FF
0x18007d280  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007d287  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007d28e  mov     [rbp+57h+var_98], rax
0x18007d292  cmp     r15d, edi
0x18007d295  jb      short loc_18007D2B3
0x18007d297  xor     r13d, r13d
0x18007d29a  mov     [rbp+57h+var_90], 28h ; '('
0x18007d2a1  lea     rdx, [rbp+57h+var_98]
0x18007d2a5  lea     rcx, [rbp+57h+var_98]
0x18007d2a9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007d2ae  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007d2b1  jmp     short loc_18007D2B9
0x18007d2b3  lea     r13, [r14+r15*8]
0x18007d2b7  xor     ebx, ebx
0x18007d2b9  test    ebx, ebx
0x18007d2bb  js      loc_18007D399
0x18007d2c1  mov     rcx, [rbp+57h+var_A0]
0x18007d2c5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007d2cc  mov     r8, r13
0x18007d2cf  mov     rax, [rcx]
0x18007d2d2  mov     rax, [rax]
0x18007d2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d2da  mov     ebx, eax
  ... truncated ...
```
