# CEnumProgIdRedirectionSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007c780`
- end: `0x18007ce5e`
- name: `?Next@CEnumProgIdRedirectionSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumProgIdRedirectionSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x1800585a8`
- `0x18005bc58`
- `0x18005df30`
- `0x18006a76c`
- `0x18007c780`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c87b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ca9c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007cc38`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ccb1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007cda5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c87b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ca9c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007cc38`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007ccb1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007cda5`

## string_xrefs

- `0x18007c8e9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007c7b9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c884`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007caa5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007cb97`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007cc44`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007cc65`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ccba`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007cd12`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007cd59`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007cdae`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumProgIdRedirectionSection::Next(
        CEnumProgIdRedirectionSection *this,
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
    v59 = 21402;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 21403;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x539C, -2147467261, v8);
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
      (const char *)0x53A0,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::Allocate(
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
            (const char *)0x53AA,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>(&v57);
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
        v38 = CProgIdRedirectionEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x53AB,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>(&v57);
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
            (const char *)0x53AC,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>(&v57);
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
            (const char *)0x53AD,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>(&v57);
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
        (const char *)0x53A9,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>(&v57);
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
          (const char *)0x53B5,
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
      (const char *)0x53A1,
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
0x18007c780  mov     rax, rsp
0x18007c783  mov     [rax+18h], rbx
0x18007c787  mov     [rax+20h], r9
0x18007c78b  mov     [rax+8], rcx
0x18007c78f  push    rbp
0x18007c790  push    rsi
0x18007c791  push    rdi
0x18007c792  push    r12
0x18007c794  push    r13
0x18007c796  push    r14
0x18007c798  push    r15
0x18007c79a  lea     rbp, [rax-5Fh]
0x18007c79e  sub     rsp, 90h
0x18007c7a5  mov     r14, r8
0x18007c7a8  mov     edi, edx
0x18007c7aa  mov     rsi, rcx
0x18007c7ad  mov     edx, edx
0x18007c7af  xor     r15d, r15d
0x18007c7b2  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007c7b9  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c7c0  mov     [rbp+57h+var_70], r15
0x18007c7c4  xorps   xmm0, xmm0
0x18007c7c7  mov     [rbp+57h+var_98], r11
0x18007c7cb  mov     rcx, r14
0x18007c7ce  mov     [rbp+57h+var_68], r15
0x18007c7d2  lea     r8, [rbp+57h+var_68]
0x18007c7d6  mov     r13, r9
0x18007c7d9  movdqu  [rbp+57h+var_80], xmm0
0x18007c7de  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007c7e3  test    r13, r13
0x18007c7e6  jz      short loc_18007C7EC
0x18007c7e8  mov     [r13+0], r15d
0x18007c7ec  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c7f3  test    rdx, rdx
0x18007c7f6  jz      loc_18007CE21
0x18007c7fc  mov     rcx, [rsi+18h]
0x18007c800  call    RtlIsTypeSafeHandleValid
0x18007c805  test    al, al
0x18007c807  jz      loc_18007CE21
0x18007c80d  test    r14, r14
0x18007c810  jnz     short loc_18007C830
0x18007c812  lea     rcx, [rbp+57h+var_98]
0x18007c816  mov     [rbp+57h+var_90], 539Bh
0x18007c81d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007c822  lea     rcx, [rbp+57h+var_80]
0x18007c826  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007c82b  jmp     loc_18007CE3E
0x18007c830  test    r13, r13
0x18007c833  jnz     short loc_18007C85D
0x18007c835  cmp     edi, 1
0x18007c838  jz      short loc_18007C85D
0x18007c83a  mov     ebx, 80004003h
0x18007c83f  mov     edx, 539Ch; char *
0x18007c844  mov     r8d, ebx; int
0x18007c847  mov     rcx, r11; this
0x18007c84a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007c84f  lea     rcx, [rbp+57h+var_80]
0x18007c853  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007c858  jmp     loc_18007CE41
0x18007c85d  mov     r8d, edi
0x18007c860  lea     rdx, [rbp+57h+arg_8]
0x18007c864  lea     rcx, [rbp+57h+var_80]
0x18007c868  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007c86d  mov     ebx, [rax]
0x18007c86f  test    ebx, ebx
0x18007c871  jns     short loc_18007C8CC
0x18007c873  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007c879  jnz     short loc_18007C881
0x18007c87b  call    cs:__imp_DebugBreak
0x18007c881  mov     r9d, ebx; int
0x18007c884  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c88b  mov     r8d, 53A0h; char *
0x18007c891  lea     rcx, aStatusPropagat; "Status propagated"
0x18007c898  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007c89d  mov     ecx, ebx; this
0x18007c89f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007c8a4  mov     ebx, eax
0x18007c8a6  mov     esi, r15d
0x18007c8a9  test    edi, edi
0x18007c8ab  jz      short loc_18007C84F
0x18007c8ad  mov     ecx, esi
0x18007c8af  mov     rcx, [r14+rcx*8]
0x18007c8b3  test    rcx, rcx
0x18007c8b6  jz      short loc_18007C8C4
0x18007c8b8  mov     rdx, [rcx]
0x18007c8bb  mov     rax, [rdx+10h]
0x18007c8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c8c4  inc     esi
0x18007c8c6  cmp     esi, edi
0x18007c8c8  jb      short loc_18007C8AD
0x18007c8ca  jmp     short loc_18007C84F
0x18007c8cc  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007c8cf  xorps   xmm0, xmm0
0x18007c8d2  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007c8d5  mov     r10, [rsi+18h]
0x18007c8d9  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007c8dd  xor     esi, esi
0x18007c8df  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007c8e3  mov     [rbp+57h+arg_8], eax
0x18007c8e6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007c8e9  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c8f0  mov     [rbp+57h+var_98], rax
0x18007c8f4  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007c8fb  mov     [rbp+57h+var_60], rsi
0x18007c8ff  movdqu  [rbp+57h+var_58], xmm0
0x18007c904  test    r15, r15
0x18007c907  jz      short loc_18007C935
0x18007c909  mov     ecx, esi
0x18007c90b  test    edi, edi
0x18007c90d  jz      short loc_18007C935
0x18007c90f  mov     rax, rcx
0x18007c912  inc     rcx
0x18007c915  shl     rax, 5
0x18007c919  mov     [rax+r15], rsi
0x18007c91d  mov     [rax+r15+8], rsi
0x18007c922  mov     [rax+r15+10h], rsi
0x18007c927  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007c930  cmp     rcx, rdi
0x18007c933  jb      short loc_18007C90F
0x18007c935  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c93c  test    rdx, rdx
0x18007c93f  jz      loc_18007CA7D
0x18007c945  mov     rcx, r10
0x18007c948  call    RtlIsTypeSafeHandleValid
0x18007c94d  test    al, al
0x18007c94f  jz      loc_18007CA7D
0x18007c955  test    r15, r15
0x18007c958  jnz     short loc_18007C96A
0x18007c95a  test    edi, edi
0x18007c95c  jz      short loc_18007C96A
0x18007c95e  mov     [rbp+57h+var_90], 478h
0x18007c965  jmp     loc_18007CA84
0x18007c96a  mov     rdx, r10
0x18007c96d  lea     rcx, [rbp+57h+var_60]
0x18007c971  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007c976  mov     ebx, eax
0x18007c978  test    eax, eax
0x18007c97a  jns     short loc_18007C9A2
0x18007c97c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007c980  test    rdx, rdx
0x18007c983  jz      loc_18007CA90
0x18007c989  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c990  mov     rax, [rcx+30h]
0x18007c994  mov     rcx, [rbp+57h+var_60]
0x18007c998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c99d  jmp     loc_18007CA90
0x18007c9a2  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007c9a6  mov     rax, [rcx+20h]
0x18007c9aa  cmp     [rcx+28h], rax
0x18007c9ae  jbe     short loc_18007C9E6
0x18007c9b0  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007c9b4  mov     [rbp+57h+var_90], 47Dh
0x18007c9bb  test    rdx, rdx
0x18007c9be  jz      short loc_18007C9D4
0x18007c9c0  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c9c7  mov     rcx, [rbp+57h+var_60]
0x18007c9cb  mov     rax, [rax+30h]
0x18007c9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c9d4  lea     rdx, [rbp+57h+var_98]
0x18007c9d8  lea     rcx, [rbp+57h+var_98]
0x18007c9dc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007c9e1  jmp     loc_18007CA8D
0x18007c9e6  test    edi, edi
0x18007c9e8  jz      short loc_18007CA62
0x18007c9ea  mov     r9, [rcx+28h]
0x18007c9ee  cmp     r9, [rcx+20h]
0x18007c9f2  jnb     short loc_18007CA62
0x18007c9f4  mov     rdx, [rcx+30h]
0x18007c9f8  mov     rax, rsi
0x18007c9fb  mov     rcx, [rcx+8]
0x18007c9ff  shl     rax, 5
0x18007ca03  add     r15, rax
0x18007ca06  mov     edx, [rdx+r9*4]
0x18007ca0a  mov     r8, r15
0x18007ca0d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007ca12  mov     ebx, eax
0x18007ca14  test    eax, eax
0x18007ca16  js      short loc_18007CA41
0x18007ca18  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007ca1c  inc     rsi
0x18007ca1f  mov     rcx, [rdx+28h]
0x18007ca23  mov     rax, [rdx+38h]
0x18007ca27  mov     ecx, [rax+rcx*4]
0x18007ca2a  mov     [r15+18h], ecx
0x18007ca2e  inc     qword ptr [rdx+28h]
0x18007ca32  cmp     rsi, rdi
0x18007ca35  jnb     short loc_18007CA62
0x18007ca37  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007ca3b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007ca3f  jmp     short loc_18007C9EA
0x18007ca41  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007ca45  test    rdx, rdx
0x18007ca48  jz      short loc_18007CA5E
0x18007ca4a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007ca51  mov     rcx, [rbp+57h+var_60]
0x18007ca55  mov     rax, [rax+30h]
0x18007ca59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ca5e  xor     esi, esi
0x18007ca60  jmp     short loc_18007CA90
0x18007ca62  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007ca66  xor     ebx, ebx
0x18007ca68  test    rdx, rdx
0x18007ca6b  jz      short loc_18007CA90
0x18007ca6d  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007ca74  mov     rax, [rax+30h]
0x18007ca78  jmp     loc_18007C994
0x18007ca7d  mov     [rbp+57h+var_90], 477h
0x18007ca84  lea     rcx, [rbp+57h+var_98]
0x18007ca88  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007ca8d  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007ca90  test    ebx, ebx
0x18007ca92  jns     short loc_18007CAF1
0x18007ca94  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007ca9a  jnz     short loc_18007CAA2
0x18007ca9c  call    cs:__imp_DebugBreak
0x18007caa2  mov     r9d, ebx; int
0x18007caa5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007caac  mov     r8d, 53A1h; char *
0x18007cab2  lea     rcx, aStatusPropagat; "Status propagated"
0x18007cab9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007cabe  mov     ecx, ebx; this
0x18007cac0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007cac5  xor     esi, esi
0x18007cac7  mov     ebx, eax
0x18007cac9  test    edi, edi
0x18007cacb  jz      loc_18007C84F
0x18007cad1  mov     rcx, [r14+rsi*8]
0x18007cad5  test    rcx, rcx
0x18007cad8  jz      short loc_18007CAE6
0x18007cada  mov     rax, [rcx]
0x18007cadd  mov     rax, [rax+10h]
0x18007cae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cae6  inc     esi
0x18007cae8  cmp     esi, edi
0x18007caea  jb      short loc_18007CAD1
0x18007caec  jmp     loc_18007C84F
0x18007caf1  xor     r15d, r15d
0x18007caf4  test    rsi, rsi
0x18007caf7  jz      loc_18007CC14
0x18007cafd  lea     rdx, [rbp+57h+var_48]
0x18007cb01  mov     [rbp+57h+var_A0], 0
0x18007cb09  lea     rcx, [rbp+57h+var_A0]
0x18007cb0d  mov     [rbp+57h+var_68], 0
0x18007cb15  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCProgIdRedirectionEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CProgIdRedirectionEntry>>>::Allocate(void)
0x18007cb1a  mov     ebx, [rax]
0x18007cb1c  test    ebx, ebx
0x18007cb1e  js      loc_18007CD9D
0x18007cb24  mov     eax, [rbp+57h+arg_8]
0x18007cb27  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007cb2b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007cb2e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007cb32  mov     [rbp+57h+arg_8], eax
0x18007cb35  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007cb38  mov     eax, r15d
0x18007cb3b  shl     rax, 5
0x18007cb3f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007cb43  mov     rcx, rax; this
0x18007cb46  mov     [rbp+57h+var_40], rax
0x18007cb4a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007cb4f  mov     ebx, eax
0x18007cb51  test    eax, eax
0x18007cb53  js      loc_18007CD56
0x18007cb59  mov     eax, [rbp+57h+arg_8]
0x18007cb5c  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007cb5f  mov     r8, [rbp+57h+var_40]
0x18007cb63  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007cb67  mov     r9, [rbp+57h+var_68]
0x18007cb6b  mov     rcx, [rbp+57h+var_A0]
0x18007cb6f  mov     r8d, [r8+18h]
0x18007cb73  mov     [rbp+57h+arg_8], eax
0x18007cb76  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007cb79  mov     rax, [rbp+57h+arg_0]
0x18007cb7d  mov     rdx, [rax+10h]
0x18007cb81  call    ?Initialize@CProgIdRedirectionEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CProgIdRedirectionEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007cb86  mov     ebx, eax
0x18007cb88  test    eax, eax
0x18007cb8a  js      loc_18007CD0F
0x18007cb90  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007cb97  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007cb9e  mov     [rbp+57h+var_98], rax
0x18007cba2  cmp     r15d, edi
0x18007cba5  jb      short loc_18007CBC3
0x18007cba7  xor     r13d, r13d
0x18007cbaa  mov     [rbp+57h+var_90], 28h ; '('
0x18007cbb1  lea     rdx, [rbp+57h+var_98]
0x18007cbb5  lea     rcx, [rbp+57h+var_98]
0x18007cbb9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007cbbe  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007cbc1  jmp     short loc_18007CBC9
0x18007cbc3  lea     r13, [r14+r15*8]
0x18007cbc7  xor     ebx, ebx
0x18007cbc9  test    ebx, ebx
0x18007cbcb  js      loc_18007CCA9
0x18007cbd1  mov     rcx, [rbp+57h+var_A0]
0x18007cbd5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007cbdc  mov     r8, r13
0x18007cbdf  mov     rax, [rcx]
0x18007cbe2  mov     rax, [rax]
0x18007cbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cbea  mov     ebx, eax
  ... truncated ...
```
