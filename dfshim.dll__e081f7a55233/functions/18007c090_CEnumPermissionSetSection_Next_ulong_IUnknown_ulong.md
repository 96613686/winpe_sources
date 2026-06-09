# CEnumPermissionSetSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007c090`
- end: `0x18007c76e`
- name: `?Next@CEnumPermissionSetSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CEnumPermissionSetSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180058538`
- `0x18005bb14`
- `0x18005df30`
- `0x18006a5a8`
- `0x18007c090`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c18b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c3ac`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c548`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c5c1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c6b5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c18b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c3ac`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c548`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c5c1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007c6b5`

## string_xrefs

- `0x18007c1f9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007c0c9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c194`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c3b5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c4a7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c554`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c575`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c5ca`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c622`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c669`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007c6be`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumPermissionSetSection::Next(
        CEnumPermissionSetSection *this,
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
    v59 = 22189;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v58,
      &v58);
    return (unsigned int)v60;
  }
  if ( !a3 )
  {
    v59 = 22190;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v61);
    return (unsigned int)v60;
  }
  if ( !v7 && (_DWORD)v5 != 1 )
  {
    jj = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x56AF, -2147467261, v8);
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
      (const char *)0x56B3,
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
        v31 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::Allocate(
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
            (const char *)0x56BD,
            v34,
            v35);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>(&v57);
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
        v38 = CPermissionSetEntry::Initialize(v57, *((_QWORD *)this + 2), v37, v63);
        jj = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x56BE,
            v38,
            v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>(&v57);
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
            (const char *)0x56BF,
            v41,
            (unsigned int)v57);
          jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v41,
                 v46);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>(&v57);
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
            (const char *)0x56C0,
            v42,
            v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>(&v57);
          for ( n = 0; (unsigned int)n < (unsigned int)v5; n = (unsigned int)(n + 1) )
          {
            v45 = a3[n];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v57 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>(&v57);
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
        (const char *)0x56BC,
        v31,
        (unsigned int)v57);
      jj = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v31, v53);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>(&v57);
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
          (const char *)0x56C8,
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
      (const char *)0x56B4,
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
0x18007c090  mov     rax, rsp
0x18007c093  mov     [rax+18h], rbx
0x18007c097  mov     [rax+20h], r9
0x18007c09b  mov     [rax+8], rcx
0x18007c09f  push    rbp
0x18007c0a0  push    rsi
0x18007c0a1  push    rdi
0x18007c0a2  push    r12
0x18007c0a4  push    r13
0x18007c0a6  push    r14
0x18007c0a8  push    r15
0x18007c0aa  lea     rbp, [rax-5Fh]
0x18007c0ae  sub     rsp, 90h
0x18007c0b5  mov     r14, r8
0x18007c0b8  mov     edi, edx
0x18007c0ba  mov     rsi, rcx
0x18007c0bd  mov     edx, edx
0x18007c0bf  xor     r15d, r15d
0x18007c0c2  mov     dword ptr [rbp+57h+var_88], 8007054Fh
0x18007c0c9  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c0d0  mov     [rbp+57h+var_70], r15
0x18007c0d4  xorps   xmm0, xmm0
0x18007c0d7  mov     [rbp+57h+var_98], r11
0x18007c0db  mov     rcx, r14
0x18007c0de  mov     [rbp+57h+var_68], r15
0x18007c0e2  lea     r8, [rbp+57h+var_68]
0x18007c0e6  mov     r13, r9
0x18007c0e9  movdqu  [rbp+57h+var_80], xmm0
0x18007c0ee  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007c0f3  test    r13, r13
0x18007c0f6  jz      short loc_18007C0FC
0x18007c0f8  mov     [r13+0], r15d
0x18007c0fc  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c103  test    rdx, rdx
0x18007c106  jz      loc_18007C731
0x18007c10c  mov     rcx, [rsi+18h]
0x18007c110  call    RtlIsTypeSafeHandleValid
0x18007c115  test    al, al
0x18007c117  jz      loc_18007C731
0x18007c11d  test    r14, r14
0x18007c120  jnz     short loc_18007C140
0x18007c122  lea     rcx, [rbp+57h+var_98]
0x18007c126  mov     [rbp+57h+var_90], 56AEh
0x18007c12d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007c132  lea     rcx, [rbp+57h+var_80]
0x18007c136  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007c13b  jmp     loc_18007C74E
0x18007c140  test    r13, r13
0x18007c143  jnz     short loc_18007C16D
0x18007c145  cmp     edi, 1
0x18007c148  jz      short loc_18007C16D
0x18007c14a  mov     ebx, 80004003h
0x18007c14f  mov     edx, 56AFh; char *
0x18007c154  mov     r8d, ebx; int
0x18007c157  mov     rcx, r11; this
0x18007c15a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007c15f  lea     rcx, [rbp+57h+var_80]
0x18007c163  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007c168  jmp     loc_18007C751
0x18007c16d  mov     r8d, edi
0x18007c170  lea     rdx, [rbp+57h+arg_8]
0x18007c174  lea     rcx, [rbp+57h+var_80]
0x18007c178  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007c17d  mov     ebx, [rax]
0x18007c17f  test    ebx, ebx
0x18007c181  jns     short loc_18007C1DC
0x18007c183  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007c189  jnz     short loc_18007C191
0x18007c18b  call    cs:__imp_DebugBreak
0x18007c191  mov     r9d, ebx; int
0x18007c194  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c19b  mov     r8d, 56B3h; char *
0x18007c1a1  lea     rcx, aStatusPropagat; "Status propagated"
0x18007c1a8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007c1ad  mov     ecx, ebx; this
0x18007c1af  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007c1b4  mov     ebx, eax
0x18007c1b6  mov     esi, r15d
0x18007c1b9  test    edi, edi
0x18007c1bb  jz      short loc_18007C15F
0x18007c1bd  mov     ecx, esi
0x18007c1bf  mov     rcx, [r14+rcx*8]
0x18007c1c3  test    rcx, rcx
0x18007c1c6  jz      short loc_18007C1D4
0x18007c1c8  mov     rdx, [rcx]
0x18007c1cb  mov     rax, [rdx+10h]
0x18007c1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c1d4  inc     esi
0x18007c1d6  cmp     esi, edi
0x18007c1d8  jb      short loc_18007C1BD
0x18007c1da  jmp     short loc_18007C15F
0x18007c1dc  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18007c1df  xorps   xmm0, xmm0
0x18007c1e2  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007c1e5  mov     r10, [rsi+18h]
0x18007c1e9  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007c1ed  xor     esi, esi
0x18007c1ef  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007c1f3  mov     [rbp+57h+arg_8], eax
0x18007c1f6  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007c1f9  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c200  mov     [rbp+57h+var_98], rax
0x18007c204  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007c20b  mov     [rbp+57h+var_60], rsi
0x18007c20f  movdqu  [rbp+57h+var_58], xmm0
0x18007c214  test    r15, r15
0x18007c217  jz      short loc_18007C245
0x18007c219  mov     ecx, esi
0x18007c21b  test    edi, edi
0x18007c21d  jz      short loc_18007C245
0x18007c21f  mov     rax, rcx
0x18007c222  inc     rcx
0x18007c225  shl     rax, 5
0x18007c229  mov     [rax+r15], rsi
0x18007c22d  mov     [rax+r15+8], rsi
0x18007c232  mov     [rax+r15+10h], rsi
0x18007c237  mov     dword ptr [rax+r15+18h], 0FFFFFFFFh
0x18007c240  cmp     rcx, rdi
0x18007c243  jb      short loc_18007C21F
0x18007c245  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c24c  test    rdx, rdx
0x18007c24f  jz      loc_18007C38D
0x18007c255  mov     rcx, r10
0x18007c258  call    RtlIsTypeSafeHandleValid
0x18007c25d  test    al, al
0x18007c25f  jz      loc_18007C38D
0x18007c265  test    r15, r15
0x18007c268  jnz     short loc_18007C27A
0x18007c26a  test    edi, edi
0x18007c26c  jz      short loc_18007C27A
0x18007c26e  mov     [rbp+57h+var_90], 478h
0x18007c275  jmp     loc_18007C394
0x18007c27a  mov     rdx, r10
0x18007c27d  lea     rcx, [rbp+57h+var_60]
0x18007c281  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007c286  mov     ebx, eax
0x18007c288  test    eax, eax
0x18007c28a  jns     short loc_18007C2B2
0x18007c28c  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007c290  test    rdx, rdx
0x18007c293  jz      loc_18007C3A0
0x18007c299  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c2a0  mov     rax, [rcx+30h]
0x18007c2a4  mov     rcx, [rbp+57h+var_60]
0x18007c2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c2ad  jmp     loc_18007C3A0
0x18007c2b2  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007c2b6  mov     rax, [rcx+20h]
0x18007c2ba  cmp     [rcx+28h], rax
0x18007c2be  jbe     short loc_18007C2F6
0x18007c2c0  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007c2c4  mov     [rbp+57h+var_90], 47Dh
0x18007c2cb  test    rdx, rdx
0x18007c2ce  jz      short loc_18007C2E4
0x18007c2d0  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c2d7  mov     rcx, [rbp+57h+var_60]
0x18007c2db  mov     rax, [rax+30h]
0x18007c2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c2e4  lea     rdx, [rbp+57h+var_98]
0x18007c2e8  lea     rcx, [rbp+57h+var_98]
0x18007c2ec  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007c2f1  jmp     loc_18007C39D
0x18007c2f6  test    edi, edi
0x18007c2f8  jz      short loc_18007C372
0x18007c2fa  mov     r9, [rcx+28h]
0x18007c2fe  cmp     r9, [rcx+20h]
0x18007c302  jnb     short loc_18007C372
0x18007c304  mov     rdx, [rcx+30h]
0x18007c308  mov     rax, rsi
0x18007c30b  mov     rcx, [rcx+8]
0x18007c30f  shl     rax, 5
0x18007c313  add     r15, rax
0x18007c316  mov     edx, [rdx+r9*4]
0x18007c31a  mov     r8, r15
0x18007c31d  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007c322  mov     ebx, eax
0x18007c324  test    eax, eax
0x18007c326  js      short loc_18007C351
0x18007c328  mov     rdx, qword ptr [rbp+57h+var_58]
0x18007c32c  inc     rsi
0x18007c32f  mov     rcx, [rdx+28h]
0x18007c333  mov     rax, [rdx+38h]
0x18007c337  mov     ecx, [rax+rcx*4]
0x18007c33a  mov     [r15+18h], ecx
0x18007c33e  inc     qword ptr [rdx+28h]
0x18007c342  cmp     rsi, rdi
0x18007c345  jnb     short loc_18007C372
0x18007c347  mov     rcx, qword ptr [rbp+57h+var_58]
0x18007c34b  mov     r15, qword ptr [rbp+57h+var_80+8]
0x18007c34f  jmp     short loc_18007C2FA
0x18007c351  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007c355  test    rdx, rdx
0x18007c358  jz      short loc_18007C36E
0x18007c35a  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c361  mov     rcx, [rbp+57h+var_60]
0x18007c365  mov     rax, [rax+30h]
0x18007c369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c36e  xor     esi, esi
0x18007c370  jmp     short loc_18007C3A0
0x18007c372  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x18007c376  xor     ebx, ebx
0x18007c378  test    rdx, rdx
0x18007c37b  jz      short loc_18007C3A0
0x18007c37d  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007c384  mov     rax, [rax+30h]
0x18007c388  jmp     loc_18007C2A4
0x18007c38d  mov     [rbp+57h+var_90], 477h
0x18007c394  lea     rcx, [rbp+57h+var_98]
0x18007c398  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007c39d  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007c3a0  test    ebx, ebx
0x18007c3a2  jns     short loc_18007C401
0x18007c3a4  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007c3aa  jnz     short loc_18007C3B2
0x18007c3ac  call    cs:__imp_DebugBreak
0x18007c3b2  mov     r9d, ebx; int
0x18007c3b5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c3bc  mov     r8d, 56B4h; char *
0x18007c3c2  lea     rcx, aStatusPropagat; "Status propagated"
0x18007c3c9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007c3ce  mov     ecx, ebx; this
0x18007c3d0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007c3d5  xor     esi, esi
0x18007c3d7  mov     ebx, eax
0x18007c3d9  test    edi, edi
0x18007c3db  jz      loc_18007C15F
0x18007c3e1  mov     rcx, [r14+rsi*8]
0x18007c3e5  test    rcx, rcx
0x18007c3e8  jz      short loc_18007C3F6
0x18007c3ea  mov     rax, [rcx]
0x18007c3ed  mov     rax, [rax+10h]
0x18007c3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c3f6  inc     esi
0x18007c3f8  cmp     esi, edi
0x18007c3fa  jb      short loc_18007C3E1
0x18007c3fc  jmp     loc_18007C15F
0x18007c401  xor     r15d, r15d
0x18007c404  test    rsi, rsi
0x18007c407  jz      loc_18007C524
0x18007c40d  lea     rdx, [rbp+57h+var_48]
0x18007c411  mov     [rbp+57h+var_A0], 0
0x18007c419  lea     rcx, [rbp+57h+var_A0]
0x18007c41d  mov     [rbp+57h+var_68], 0
0x18007c425  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCPermissionSetEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CPermissionSetEntry>>>::Allocate(void)
0x18007c42a  mov     ebx, [rax]
0x18007c42c  test    ebx, ebx
0x18007c42e  js      loc_18007C6AD
0x18007c434  mov     eax, [rbp+57h+arg_8]
0x18007c437  lea     rdx, [rbp+57h+var_68]; struct _LUTF8_STRING *
0x18007c43b  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007c43e  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007c442  mov     [rbp+57h+arg_8], eax
0x18007c445  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007c448  mov     eax, r15d
0x18007c44b  shl     rax, 5
0x18007c44f  add     rax, qword ptr [rbp+57h+var_80+8]
0x18007c453  mov     rcx, rax; this
0x18007c456  mov     [rbp+57h+var_40], rax
0x18007c45a  call    ?CopyOut@Com@IsolationImplementation@@YAJPEBU_LUTF8_STRING@@PEAPEAG@Z; IsolationImplementation::Com::CopyOut(_LUTF8_STRING const *,ushort * *)
0x18007c45f  mov     ebx, eax
0x18007c461  test    eax, eax
0x18007c463  js      loc_18007C666
0x18007c469  mov     eax, [rbp+57h+arg_8]
0x18007c46c  cmp     eax, dword ptr [rbp+57h+var_70]
0x18007c46f  mov     r8, [rbp+57h+var_40]
0x18007c473  cmovb   eax, dword ptr [rbp+57h+var_70]
0x18007c477  mov     r9, [rbp+57h+var_68]
0x18007c47b  mov     rcx, [rbp+57h+var_A0]
0x18007c47f  mov     r8d, [r8+18h]
0x18007c483  mov     [rbp+57h+arg_8], eax
0x18007c486  mov     dword ptr [rbp+57h+var_70+4], eax
0x18007c489  mov     rax, [rbp+57h+arg_0]
0x18007c48d  mov     rdx, [rax+10h]
0x18007c491  call    ?Initialize@CPermissionSetEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEBG@Z; CPermissionSetEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ushort const *)
0x18007c496  mov     ebx, eax
0x18007c498  test    eax, eax
0x18007c49a  js      loc_18007C61F
0x18007c4a0  mov     dword ptr [rbp+57h+var_88], 0C00000E5h
0x18007c4a7  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007c4ae  mov     [rbp+57h+var_98], rax
0x18007c4b2  cmp     r15d, edi
0x18007c4b5  jb      short loc_18007C4D3
0x18007c4b7  xor     r13d, r13d
0x18007c4ba  mov     [rbp+57h+var_90], 28h ; '('
0x18007c4c1  lea     rdx, [rbp+57h+var_98]
0x18007c4c5  lea     rcx, [rbp+57h+var_98]
0x18007c4c9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007c4ce  mov     ebx, dword ptr [rbp+57h+var_88]
0x18007c4d1  jmp     short loc_18007C4D9
0x18007c4d3  lea     r13, [r14+r15*8]
0x18007c4d7  xor     ebx, ebx
0x18007c4d9  test    ebx, ebx
0x18007c4db  js      loc_18007C5B9
0x18007c4e1  mov     rcx, [rbp+57h+var_A0]
0x18007c4e5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007c4ec  mov     r8, r13
0x18007c4ef  mov     rax, [rcx]
0x18007c4f2  mov     rax, [rax]
0x18007c4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4fa  mov     ebx, eax
  ... truncated ...
```
