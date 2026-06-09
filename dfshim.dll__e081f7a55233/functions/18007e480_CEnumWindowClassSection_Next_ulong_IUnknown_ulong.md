# CEnumWindowClassSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007e480`
- end: `0x18007eb5e`
- name: `?Next@CEnumWindowClassSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumWindowClassSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180058768`
- `0x18005c164`
- `0x18005df30`
- `0x18006ae7c`
- `0x18007e480`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e57b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e79c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e938`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e9b1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007eaa5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e57b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e79c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e938`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007e9b1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007eaa5`

## string_xrefs

- `0x18007e5e9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007e4b9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e584`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e7a5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e897`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e944`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e965`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007e9ba`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ea12`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007ea59`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007eaae`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumWindowClassSection::Next(
        CEnumWindowClassSection *this,
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
    v59 = 21738;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 21739;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x54EC, -2147467261, v8);
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
      (const char *)0x54F0,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::Allocate(
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
            (const char *)0x54FA,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>(&v57);
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
        v38 = CWindowClassEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x54FB,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>(&v57);
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
            (const char *)0x54FC,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>(&v57);
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
            (const char *)0x54FD,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>(&v57);
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
        (const char *)0x54F9,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>(&v57);
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
          (const char *)0x5505,
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
      (const char *)0x54F1,
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
0x18007e480  mov     rax, rsp
0x18007e483  mov     [rax+18h], rbx
0x18007e487  mov     [rax+20h], r9
0x18007e48b  mov     [rax+8], rcx
0x18007e48f  push    rbp
0x18007e490  push    rsi
0x18007e491  push    rdi
0x18007e492  push    r12
0x18007e494  push    r13
0x18007e496  push    r14
0x18007e498  push    r15
0x18007e49a  lea     rbp, [rax-5Fh]
0x18007e49e  sub     rsp, 90h
0x18007e4a5  mov     r14, r8
0x18007e4a8  mov     edi, edx
0x18007e4aa  mov     rsi, rcx
0x18007e4ad  mov     edx, edx
0x18007e4af  xor     r15d, r15d
0x18007e4b2  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007e4b9  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007e4c0  mov     [rbp+57h+var_70], r15
0x18007e4c4  xorps   xmm0, xmm0
0x18007e4c7  mov     [rbp+57h+var_98], r11
0x18007e4cb  mov     rcx, r14
0x18007e4ce  mov     [rbp+57h+var_68], r15
0x18007e4d2  lea     r8, [rbp+57h+var_68]
0x18007e4d6  mov     r13, r9
0x18007e4d9  movdqu  [rbp+57h+var_80], xmm0
0x18007e4de  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007e4e3  test    r13, r13
0x18007e4e6  jz      short loc_18007E4EC
0x18007e4e8  mov     [r13+0], r15d
0x18007e4ec  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e4f3  test    rdx, rdx
0x18007e4f6  jz      loc_18007EB21
0x18007e4fc  mov     rcx, [rsi+18h]
0x18007e500  call    RtlIsTypeSafeHandleValid
0x18007e505  test    al, al
0x18007e507  jz      loc_18007EB21
0x18007e50d  test    r14, r14
0x18007e510  jnz     short loc_18007E530
0x18007e512  lea     rcx, [rbp+57h+var_98]
0x18007e516  mov     [rbp+57h+var_90], 54EBh
0x18007e51d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007e522  lea     rcx, [rbp+57h+var_80]
0x18007e526  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007e52b  jmp     loc_18007EB3E
0x18007e530  test    r13, r13
0x18007e533  jnz     short loc_18007E55D
0x18007e535  cmp     edi, 1
0x18007e538  jz      short loc_18007E55D
0x18007e53a  mov     ebx, 80004003h
0x18007e53f  mov     edx, 54ECh; char *
0x18007e544  mov     r8d, ebx; int
0x18007e547  mov     rcx, r11; this
0x18007e54a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007e54f  lea     rcx, [rbp+57h+var_80]
0x18007e553  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007e558  jmp     loc_18007EB41
0x18007e55d  mov     r8d, edi
0x18007e560  lea     rdx, [rbp+57h+arg_8]
0x18007e564  lea     rcx, [rbp+57h+var_80]
0x18007e568  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007e56d  mov     ebx, [rax]
0x18007e56f  test    ebx, ebx
0x18007e571  jns     short loc_18007E5CC
0x18007e573  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007e579  jnz     short loc_18007E581
0x18007e57b  call    cs:__imp_DebugBreak
0x18007e581  mov     r9d, ebx; int
0x18007e584  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007e58b  mov     r8d, 54F0h; char *
0x18007e591  lea     rcx, aStatusPropagat; "Status propagated"
0x18007e598  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007e59d  mov     ecx, ebx; this
0x18007e59f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007e5a4  mov     ebx, eax
0x18007e5a6  mov     esi, r15d
0x18007e5a9  test    edi, edi
0x18007e5ab  jz      short loc_18007E54F
0x18007e5ad  mov     ecx, esi
0x18007e5af  mov     rcx, [r14+rcx*8]
0x18007e5b3  test    rcx, rcx
0x18007e5b6  jz      short loc_18007E5C4
0x18007e5b8  mov     rdx, [rcx]
0x18007e5bb  mov     rax, [rdx+10h]
0x18007e5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e5c4  inc     esi
0x18007e5c6  cmp     esi, edi
0x18007e5c8  jb      short loc_18007E5AD
0x18007e5ca  jmp     short loc_18007E54F
0x18007e5cc  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007e5cf  xorps   xmm0, xmm0
0x18007e5d2  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007e5d5  mov     r10, [rsi+18h]
0x18007e5d9  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007e5dd  xor     esi, esi
0x18007e5df  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007e5e3  mov     [rbp+57h+arg_8], eax
0x18007e5e6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007e5e9  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007e5f0  mov     [rbp+57h+var_98], rax
0x18007e5f4  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007e5fb  mov     [rbp+57h+var_60], rsi
0x18007e5ff  movdqu  [rbp+57h+var_58], xmm0
0x18007e604  test    r15, r15
0x18007e607  jz      short loc_18007E635
0x18007e609  mov     ecx, esi
0x18007e60b  test    edi, edi
0x18007e60d  jz      short loc_18007E635
0x18007e60f  mov     rax, rcx
0x18007e612  inc     rcx
0x18007e615  shl     rax, 5
0x18007e619  mov     [rax+r15], rsi
0x18007e61d  mov     [rax+r15+8], rsi
0x18007e622  mov     [rax+r15+10h], rsi
0x18007e627  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007e630  cmp     rcx, rdi
0x18007e633  jb      short loc_18007E60F
0x18007e635  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e63c  test    rdx, rdx
0x18007e63f  jz      loc_18007E77D
0x18007e645  mov     rcx, r10
0x18007e648  call    RtlIsTypeSafeHandleValid
0x18007e64d  test    al, al
0x18007e64f  jz      loc_18007E77D
0x18007e655  test    r15, r15
0x18007e658  jnz     short loc_18007E66A
0x18007e65a  test    edi, edi
0x18007e65c  jz      short loc_18007E66A
0x18007e65e  mov     [rbp+57h+var_90], 478h
0x18007e665  jmp     loc_18007E784
0x18007e66a  mov     rdx, r10
0x18007e66d  lea     rcx, [rbp+57h+var_60]
0x18007e671  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007e676  mov     ebx, eax
0x18007e678  test    eax, eax
0x18007e67a  jns     short loc_18007E6A2
0x18007e67c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007e680  test    rdx, rdx
0x18007e683  jz      loc_18007E790
0x18007e689  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e690  mov     rax, [rcx+30h]
0x18007e694  mov     rcx, [rbp+57h+var_60]
0x18007e698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e69d  jmp     loc_18007E790
0x18007e6a2  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007e6a6  mov     rax, [rcx+20h]
0x18007e6aa  cmp     [rcx+28h], rax
0x18007e6ae  jbe     short loc_18007E6E6
0x18007e6b0  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007e6b4  mov     [rbp+57h+var_90], 47Dh
0x18007e6bb  test    rdx, rdx
0x18007e6be  jz      short loc_18007E6D4
0x18007e6c0  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e6c7  mov     rcx, [rbp+57h+var_60]
0x18007e6cb  mov     rax, [rax+30h]
0x18007e6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6d4  lea     rdx, [rbp+57h+var_98]
0x18007e6d8  lea     rcx, [rbp+57h+var_98]
0x18007e6dc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007e6e1  jmp     loc_18007E78D
0x18007e6e6  test    edi, edi
0x18007e6e8  jz      short loc_18007E762
0x18007e6ea  mov     r9, [rcx+28h]
0x18007e6ee  cmp     r9, [rcx+20h]
0x18007e6f2  jnb     short loc_18007E762
0x18007e6f4  mov     rdx, [rcx+30h]
0x18007e6f8  mov     rax, rsi
0x18007e6fb  mov     rcx, [rcx+8]
0x18007e6ff  shl     rax, 5
0x18007e703  add     r15, rax
0x18007e706  mov     edx, [rdx+r9*4]
0x18007e70a  mov     r8, r15
0x18007e70d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007e712  mov     ebx, eax
0x18007e714  test    eax, eax
0x18007e716  js      short loc_18007E741
0x18007e718  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007e71c  inc     rsi
0x18007e71f  mov     rcx, [rdx+28h]
0x18007e723  mov     rax, [rdx+38h]
0x18007e727  mov     ecx, [rax+rcx*4]
0x18007e72a  mov     [r15+18h], ecx
0x18007e72e  inc     qword ptr [rdx+28h]
0x18007e732  cmp     rsi, rdi
0x18007e735  jnb     short loc_18007E762
0x18007e737  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007e73b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007e73f  jmp     short loc_18007E6EA
0x18007e741  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007e745  test    rdx, rdx
0x18007e748  jz      short loc_18007E75E
0x18007e74a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e751  mov     rcx, [rbp+57h+var_60]
0x18007e755  mov     rax, [rax+30h]
0x18007e759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e75e  xor     esi, esi
0x18007e760  jmp     short loc_18007E790
0x18007e762  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007e766  xor     ebx, ebx
0x18007e768  test    rdx, rdx
0x18007e76b  jz      short loc_18007E790
0x18007e76d  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007e774  mov     rax, [rax+30h]
0x18007e778  jmp     loc_18007E694
0x18007e77d  mov     [rbp+57h+var_90], 477h
0x18007e784  lea     rcx, [rbp+57h+var_98]
0x18007e788  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007e78d  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007e790  test    ebx, ebx
0x18007e792  jns     short loc_18007E7F1
0x18007e794  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007e79a  jnz     short loc_18007E7A2
0x18007e79c  call    cs:__imp_DebugBreak
0x18007e7a2  mov     r9d, ebx; int
0x18007e7a5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007e7ac  mov     r8d, 54F1h; char *
0x18007e7b2  lea     rcx, aStatusPropagat; "Status propagated"
0x18007e7b9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007e7be  mov     ecx, ebx; this
0x18007e7c0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007e7c5  xor     esi, esi
0x18007e7c7  mov     ebx, eax
0x18007e7c9  test    edi, edi
0x18007e7cb  jz      loc_18007E54F
0x18007e7d1  mov     rcx, [r14+rsi*8]
0x18007e7d5  test    rcx, rcx
0x18007e7d8  jz      short loc_18007E7E6
0x18007e7da  mov     rax, [rcx]
0x18007e7dd  mov     rax, [rax+10h]
0x18007e7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e7e6  inc     esi
0x18007e7e8  cmp     esi, edi
0x18007e7ea  jb      short loc_18007E7D1
0x18007e7ec  jmp     loc_18007E54F
0x18007e7f1  xor     r15d, r15d
0x18007e7f4  test    rsi, rsi
0x18007e7f7  jz      loc_18007E914
0x18007e7fd  lea     rdx, [rbp+57h+var_48]
0x18007e801  mov     [rbp+57h+var_A0], 0
0x18007e809  lea     rcx, [rbp+57h+var_A0]
0x18007e80d  mov     [rbp+57h+var_68], 0
0x18007e815  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCWindowClassEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CWindowClassEntry>>>::Allocate(void)
0x18007e81a  mov     ebx, [rax]
0x18007e81c  test    ebx, ebx
0x18007e81e  js      loc_18007EA9D
0x18007e824  mov     eax, [rbp+57h+arg_8]
0x18007e827  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007e82b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007e82e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007e832  mov     [rbp+57h+arg_8], eax
0x18007e835  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007e838  mov     eax, r15d
0x18007e83b  shl     rax, 5
0x18007e83f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007e843  mov     rcx, rax; this
0x18007e846  mov     [rbp+57h+var_40], rax
0x18007e84a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007e84f  mov     ebx, eax
0x18007e851  test    eax, eax
0x18007e853  js      loc_18007EA56
0x18007e859  mov     eax, [rbp+57h+arg_8]
0x18007e85c  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007e85f  mov     r8, [rbp+57h+var_40]
0x18007e863  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007e867  mov     r9, [rbp+57h+var_68]
0x18007e86b  mov     rcx, [rbp+57h+var_A0]
0x18007e86f  mov     r8d, [r8+18h]
0x18007e873  mov     [rbp+57h+arg_8], eax
0x18007e876  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007e879  mov     rax, [rbp+57h+arg_0]
0x18007e87d  mov     rdx, [rax+10h]
0x18007e881  call    ?Initialize@CWindowClassEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CWindowClassEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007e886  mov     ebx, eax
0x18007e888  test    eax, eax
0x18007e88a  js      loc_18007EA0F
0x18007e890  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007e897  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007e89e  mov     [rbp+57h+var_98], rax
0x18007e8a2  cmp     r15d, edi
0x18007e8a5  jb      short loc_18007E8C3
0x18007e8a7  xor     r13d, r13d
0x18007e8aa  mov     [rbp+57h+var_90], 28h ; '('
0x18007e8b1  lea     rdx, [rbp+57h+var_98]
0x18007e8b5  lea     rcx, [rbp+57h+var_98]
0x18007e8b9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007e8be  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007e8c1  jmp     short loc_18007E8C9
0x18007e8c3  lea     r13, [r14+r15*8]
0x18007e8c7  xor     ebx, ebx
0x18007e8c9  test    ebx, ebx
0x18007e8cb  js      loc_18007E9A9
0x18007e8d1  mov     rcx, [rbp+57h+var_A0]
0x18007e8d5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007e8dc  mov     r8, r13
0x18007e8df  mov     rax, [rcx]
0x18007e8e2  mov     rax, [rax]
0x18007e8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e8ea  mov     ebx, eax
  ... truncated ...
```
