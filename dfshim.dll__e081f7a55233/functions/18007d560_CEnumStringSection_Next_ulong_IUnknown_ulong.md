# CEnumStringSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007d560`
- end: `0x18007dd85`
- name: `?Next@CEnumStringSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `2085`
- prototype: `__int64 __fastcall(CEnumStringSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012910`
- `0x180012950`
- `0x180012b1c`
- `0x180012b38`
- `0x180013fd4`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x1800300b4`
- `0x18004f2dc`
- `0x1800569a8`
- `0x180056ee8`
- `0x18005775c`
- `0x18005ad38`
- `0x18005df30`
- `0x180067a48`
- `0x18007d560`
- `0x1800d711c`
- `0x1800d7ff4`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d66a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d88c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007da3a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007dad2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007dc1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007dca5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d66a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007d88c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007da3a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007dad2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007dc1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007dca5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d92a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d92a`

## string_xrefs

- `0x18007d6d3`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18007d599`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d895`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007d99f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007da46`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007da67`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007dadb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007db52`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007dc24`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007dcae`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumStringSection::Next(
        CEnumStringSection *this,
        unsigned int a2,
        struct IUnknown **a3,
        unsigned int *a4)
{
  unsigned __int64 v6; // rdi
  unsigned int v7; // r12d
  unsigned __int64 v8; // r13
  _DWORD *v9; // r11
  int v10; // r9d
  __int64 v11; // r11
  unsigned int v12; // ebx
  int v13; // ebx
  int v14; // edx
  unsigned int i; // esi
  struct IUnknown *v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // r14
  __int64 v19; // r10
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // r10
  int v23; // ebx
  _QWORD *v24; // rcx
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // r9
  __int64 v27; // r14
  __int64 v28; // rdx
  int v29; // edx
  unsigned int kk; // esi
  struct IUnknown *v31; // rcx
  int v32; // ebx
  unsigned int v33; // eax
  CEnumStringSection *v34; // r14
  int Value; // ebx
  __int64 v36; // rdx
  __int64 (__fastcall ***v37)(void *, GUID *, struct IUnknown **); // r14
  int v38; // eax
  int v39; // r9d
  struct IUnknown **v40; // r13
  int v41; // ebx
  int v42; // eax
  int v43; // r9d
  HANDLE v44; // rax
  __int64 ii; // rsi
  struct IUnknown *v46; // rcx
  int v47; // edx
  HANDLE v48; // rax
  __int64 n; // rsi
  struct IUnknown *v50; // rcx
  HANDLE v51; // rax
  __int64 m; // rsi
  struct IUnknown *v53; // rcx
  void *v54; // rbx
  HANDLE v55; // rax
  __int64 k; // rbx
  struct IUnknown *v57; // rcx
  int v58; // edx
  void *v59; // rsi
  HANDLE ProcessHeap_0; // rax
  __int64 j; // rsi
  struct IUnknown *v62; // rcx
  int v63; // edx
  void *v64; // rsi
  HANDLE v65; // rax
  __int64 jj; // rsi
  struct IUnknown *v67; // rcx
  unsigned int v69; // [rsp+20h] [rbp-89h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-81h] BYREF
  __int128 v71; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v72[2]; // [rsp+40h] [rbp-69h]
  const char *v73; // [rsp+48h] [rbp-61h] BYREF
  int v74; // [rsp+50h] [rbp-59h]
  Windows::ErrorHandling::COM *v75; // [rsp+58h] [rbp-51h]
  const char *v76; // [rsp+60h] [rbp-49h] BYREF
  int v77; // [rsp+68h] [rbp-41h]
  unsigned int v78; // [rsp+70h] [rbp-39h]
  char v79[8]; // [rsp+78h] [rbp-31h] BYREF
  CEnumStringSection *v80; // [rsp+80h] [rbp-29h]
  unsigned int *v81; // [rsp+90h] [rbp-19h]
  _BYTE v82[24]; // [rsp+98h] [rbp-11h] BYREF

  v80 = this;
  v6 = a2;
  v7 = 0;
  v8 = a2;
  v81 = a4;
  v78 = -2147023537;
  v76 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  *(_QWORD *)v72 = 0;
  v71 = 0;
  lpMem = 0;
  IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(a3, a2, &lpMem);
  if ( v9 )
    *v9 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    v77 = 21850;
LABEL_129:
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v71);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v76,
      &v76);
    return v78;
  }
  if ( !a3 )
  {
    v77 = 21851;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v76);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v71);
    return v78;
  }
  if ( !v11 && (_DWORD)v6 != 1 )
  {
    v12 = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfr"
                                     "e\\amd64\\com_cms.cpp",
      (const char *)0x555C,
      -2147467261,
      v10);
    goto LABEL_10;
  }
  v13 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned long,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>>::EnlargeNoPreserve(
                     &v71,
                     &v69,
                     (unsigned int)v6);
  if ( v13 < 0 )
  {
    if ( v13 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5560,
      v13,
      v69);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v13, v14);
    for ( i = 0; i < (unsigned int)v6; ++i )
    {
      v16 = a3[i];
      if ( v16 )
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
    }
    goto LABEL_10;
  }
  v17 = v72[1];
  v18 = *((_QWORD *)&v71 + 1);
  if ( v72[1] < v72[0] )
    v17 = v72[0];
  v19 = *((_QWORD *)this + 3);
  v69 = v17;
  v72[1] = v17;
  v73 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
  LODWORD(v75) = -1073741595;
  memset(v82, 0, sizeof(v82));
  if ( *((_QWORD *)&v71 + 1) )
  {
    v20 = 0;
    if ( (_DWORD)v6 )
    {
      do
      {
        v21 = v20++;
        v21 *= 32LL;
        *(_QWORD *)(v21 + v18) = 0;
        *(_QWORD *)(v21 + v18 + 8) = 0;
        *(_QWORD *)(v21 + v18 + 16) = 0;
        *(_DWORD *)(v21 + v18 + 24) = -1;
      }
      while ( v20 < v6 );
    }
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(v19) )
  {
    v74 = 1143;
    goto LABEL_46;
  }
  if ( !v18 && (_DWORD)v6 )
  {
    v74 = 1144;
LABEL_46:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v73);
LABEL_47:
    v23 = (int)v75;
LABEL_48:
    v25 = 0;
    goto LABEL_49;
  }
  v23 = Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(
          v82,
          v22);
  if ( v23 < 0 )
  {
    if ( *(_QWORD *)&v82[16] )
LABEL_31:
      (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                     + 48))(*(_QWORD *)v82);
    goto LABEL_48;
  }
  v24 = *(_QWORD **)&v82[8];
  if ( *(_QWORD *)(*(_QWORD *)&v82[8] + 40LL) > *(_QWORD *)(*(_QWORD *)&v82[8] + 32LL) )
  {
    v74 = 1149;
    if ( *(_QWORD *)&v82[16] )
      (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                     + 48))(*(_QWORD *)v82);
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v73,
      &v73);
    goto LABEL_47;
  }
  v25 = 0;
  if ( (_DWORD)v6 )
  {
    while ( 1 )
    {
      v26 = v24[5];
      if ( v26 >= v24[4] )
        break;
      v27 = 32 * v25 + v18;
      v23 = pcm_Fetch(v24[1], *(unsigned int *)(v24[6] + 4 * v26), v27);
      if ( v23 < 0 )
      {
        if ( !*(_QWORD *)&v82[16] )
          goto LABEL_48;
        goto LABEL_31;
      }
      v28 = *(_QWORD *)&v82[8];
      ++v25;
      *(_DWORD *)(v27 + 24) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v82[8] + 56LL)
                                        + 4LL * *(_QWORD *)(*(_QWORD *)&v82[8] + 40LL));
      ++*(_QWORD *)(v28 + 40);
      if ( v25 >= v6 )
        break;
      v24 = *(_QWORD **)&v82[8];
      v18 = *((_QWORD *)&v71 + 1);
    }
  }
  v23 = 0;
  if ( *(_QWORD *)&v82[16] )
    (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                   + 48))(*(_QWORD *)v82);
LABEL_49:
  if ( v23 >= 0 )
  {
    if ( v25 )
    {
      while ( 1 )
      {
        lpMem = 0;
        *(_OWORD *)v82 = 0;
        v32 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCultureSection>>>::Allocate(
                           &lpMem,
                           v79);
        if ( v32 < 0 )
          break;
        if ( *(_DWORD *)v82 )
          RaiseException(0xC00000E5, 1u, 0, 0);
        v33 = v69;
        v34 = v80;
        if ( v69 < v72[0] )
          v33 = v72[0];
        v69 = v33;
        v72[1] = v33;
        Value = CdfGetValue(*((_QWORD *)v80 + 2), *(unsigned int *)(32LL * v7 + *((_QWORD *)&v71 + 1) + 24), v82);
        if ( Value < 0 )
        {
          if ( Value == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x556B,
            Value,
            v69);
          v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                  (Windows::ErrorHandling::COM *)(unsigned int)Value,
                  v58);
          Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)v82);
          v59 = lpMem;
          if ( lpMem )
          {
            IsolationImplementation::Com::CComObject<CCultureSection>::~CComObject<CCultureSection>(lpMem);
            ProcessHeap_0 = GetProcessHeap_0();
            HeapFree_0(ProcessHeap_0, 0, v59);
          }
          for ( j = 0; (unsigned int)j < (unsigned int)v6; j = (unsigned int)(j + 1) )
          {
            v62 = a3[j];
            if ( v62 )
              ((void (__fastcall *)(struct IUnknown *))v62->lpVtbl->Release)(v62);
          }
          goto LABEL_10;
        }
        if ( *(_DWORD *)v82 != 2 )
        {
          v77 = 21868;
          Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)v82);
          v54 = lpMem;
          if ( lpMem )
          {
            IsolationImplementation::Com::CComObject<CCultureSection>::~CComObject<CCultureSection>(lpMem);
            v55 = GetProcessHeap_0();
            HeapFree_0(v55, 0, v54);
          }
          for ( k = 0; (unsigned int)k < (unsigned int)v6; k = (unsigned int)(k + 1) )
          {
            v57 = a3[k];
            if ( v57 )
              ((void (__fastcall *)(struct IUnknown *))v57->lpVtbl->Release)(v57);
          }
          goto LABEL_129;
        }
        v36 = *((_QWORD *)v34 + 2);
        v37 = (__int64 (__fastcall ***)(void *, GUID *, struct IUnknown **))lpMem;
        v38 = CCultureSection::Initialize(lpMem, v36, *(_QWORD *)&v82[8]);
        v12 = v38;
        if ( v38 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x556D,
            v38,
            v39);
          Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)v82);
          if ( v37 )
          {
            IsolationImplementation::Com::CComObject<CCultureSection>::~CComObject<CCultureSection>(v37);
            v51 = GetProcessHeap_0();
            HeapFree_0(v51, 0, v37);
          }
          for ( m = 0; (unsigned int)m < (unsigned int)v6; m = (unsigned int)(m + 1) )
          {
            v53 = a3[m];
            if ( v53 )
              ((void (__fastcall *)(struct IUnknown *))v53->lpVtbl->Release)(v53);
          }
          goto LABEL_10;
        }
        LODWORD(v75) = -1073741595;
        v73 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
        if ( v7 < (unsigned int)v6 )
        {
          v40 = &a3[v7];
          v41 = 0;
        }
        else
        {
          v40 = 0;
          v74 = 40;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
            &v73,
            &v73);
          v41 = (int)v75;
        }
        if ( v41 < 0 )
        {
          if ( v41 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x556F,
            v41,
            v69);
          v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                  (Windows::ErrorHandling::COM *)(unsigned int)v41,
                  v47);
          Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)v82);
          if ( v37 )
          {
            IsolationImplementation::Com::CComObject<CCultureSection>::~CComObject<CCultureSection>(v37);
            v48 = GetProcessHeap_0();
            HeapFree_0(v48, 0, v37);
          }
          for ( n = 0; (unsigned int)n < (unsigned int)v6; n = (unsigned int)(n + 1) )
          {
            v50 = a3[n];
            if ( v50 )
              ((void (__fastcall *)(struct IUnknown *))v50->lpVtbl->Release)(v50);
          }
          goto LABEL_10;
        }
        v42 = (**v37)(v37, &GUID_00000000_0000_0000_c000_000000000046, v40);
        v12 = v42;
        if ( v42 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x5570,
            v42,
            v43);
          Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)v82);
          if ( v37 )
          {
            IsolationImplementation::Com::CComObject<CCultureSection>::~CComObject<CCultureSection>(v37);
            v44 = GetProcessHeap_0();
            HeapFree_0(v44, 0, v37);
          }
          for ( ii = 0; (unsigned int)ii < (unsigned int)v6; ii = (unsigned int)(ii + 1) )
          {
            v46 = a3[ii];
            if ( v46 )
              ((void (__fastcall *)(struct IUnknown *))v46->lpVtbl->Release)(v46);
          }
          goto LABEL_10;
        }
        Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)v82);
        if ( ++v7 >= v25 )
        {
          v8 = v6;
          goto LABEL_73;
        }
      }
      if ( v32 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x5569,
        v32,
        v69);
      v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v32, v63);
      Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)v82);
      v64 = lpMem;
      if ( lpMem )
      {
        IsolationImplementation::Com::CComObject<CCultureSection>::~CComObject<CCultureSection>(lpMem);
        v65 = GetProcessHeap_0();
        HeapFree_0(v65, 0, v64);
      }
      for ( jj = 0; (unsigned int)jj < (unsigned int)v6; jj = (unsigned int)(jj + 1) )
      {
        v67 = a3[jj];
        if ( v67 )
          ((void (__fastcall *)(struct IUnknown *))v67->lpVtbl->Release)(v67);
      }
      goto LABEL_10;
    }
LABEL_73:
    if ( v81 )
    {
      if ( v25 > 0xFFFFFFFF )
      {
        v12 = -805306219;
        if ( g_HRESULT_to_break_on == -805306219 )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"HR originated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
          (const char *)0x5578,
          -805306219,
          v69);
        goto LABEL_10;
      }
      *v81 = v25;
    }
    v12 = v25 != v8;
  }
  else
  {
    if ( v23 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5561,
      v23,
      v69);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v23, v29);
    for ( kk = 0; kk < (unsigned int)v6; ++kk )
    {
      v31 = a3[kk];
      if ( v31 )
        ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
    }
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v71);
  return v12;
}

```

## disassembly

```asm
0x18007d560  push    rbp
0x18007d562  push    rbx
0x18007d563  push    rsi
0x18007d564  push    rdi
0x18007d565  push    r12
0x18007d567  push    r13
0x18007d569  push    r14
0x18007d56b  push    r15
0x18007d56d  lea     rbp, [rsp-1Fh]
0x18007d572  sub     rsp, 0C8h
0x18007d579  mov     rax, cs:__security_cookie
0x18007d580  xor     rax, rsp
0x18007d583  mov     [rbp+57h+var_50], rax
0x18007d587  mov     r15, r8
0x18007d58a  mov     [rbp+57h+var_80], rcx
0x18007d58e  mov     rsi, rcx
0x18007d591  mov     edi, edx
0x18007d593  xor     r12d, r12d
0x18007d596  mov     r13d, edx
0x18007d599  lea     r14, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007d5a0  mov     edx, edx
0x18007d5a2  xorps   xmm0, xmm0
0x18007d5a5  mov     [rbp+57h+var_70], r9
0x18007d5a9  mov     rcx, r15
0x18007d5ac  mov     [rbp+57h+var_90], 8007054Fh
0x18007d5b3  lea     r8, [rsp+100h+lpMem]
0x18007d5b8  mov     [rbp+57h+var_A0], r14
0x18007d5bc  mov     r11, r9
0x18007d5bf  mov     qword ptr [rbp+57h+var_C0], r12
0x18007d5c3  movdqu  [rbp+57h+var_D0], xmm0
0x18007d5c8  mov     [rsp+100h+lpMem], r12
0x18007d5cd  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007d5d2  test    r11, r11
0x18007d5d5  jz      short loc_18007D5DA
0x18007d5d7  mov     [r11], r12d
0x18007d5da  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d5e1  test    rdx, rdx
0x18007d5e4  jz      loc_18007DD43
0x18007d5ea  mov     rcx, [rsi+18h]
0x18007d5ee  call    RtlIsTypeSafeHandleValid
0x18007d5f3  test    al, al
0x18007d5f5  jz      loc_18007DD43
0x18007d5fb  test    r15, r15
0x18007d5fe  jnz     short loc_18007D61E
0x18007d600  lea     rcx, [rbp+57h+var_A0]
0x18007d604  mov     [rbp+57h+var_98], 555Bh
0x18007d60b  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007d610  lea     rcx, [rbp+57h+var_D0]
0x18007d614  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007d619  jmp     loc_18007DD60
0x18007d61e  test    r11, r11
0x18007d621  jnz     short loc_18007D64B
0x18007d623  cmp     edi, 1
0x18007d626  jz      short loc_18007D64B
0x18007d628  mov     ebx, 80004003h
0x18007d62d  mov     edx, 555Ch; char *
0x18007d632  mov     r8d, ebx; int
0x18007d635  mov     rcx, r14; this
0x18007d638  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007d63d  lea     rcx, [rbp+57h+var_D0]
0x18007d641  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007d646  jmp     loc_18007DD63
0x18007d64b  mov     r8d, edi
0x18007d64e  lea     rdx, [rsp+100h+var_E0]
0x18007d653  lea     rcx, [rbp+57h+var_D0]
0x18007d657  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007d65c  mov     ebx, [rax]
0x18007d65e  test    ebx, ebx
0x18007d660  jns     short loc_18007D6B7
0x18007d662  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007d668  jnz     short loc_18007D670
0x18007d66a  call    cs:__imp_DebugBreak
0x18007d670  mov     r9d, ebx; int
0x18007d673  lea     rcx, aStatusPropagat; "Status propagated"
0x18007d67a  mov     r8d, 5560h; char *
0x18007d680  mov     rdx, r14; char *
0x18007d683  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007d688  mov     ecx, ebx; this
0x18007d68a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007d68f  mov     ebx, eax
0x18007d691  mov     esi, r12d
0x18007d694  test    edi, edi
0x18007d696  jz      short loc_18007D63D
0x18007d698  mov     ecx, esi
0x18007d69a  mov     rcx, [r15+rcx*8]
0x18007d69e  test    rcx, rcx
0x18007d6a1  jz      short loc_18007D6AF
0x18007d6a3  mov     rdx, [rcx]
0x18007d6a6  mov     rax, [rdx+10h]
0x18007d6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6af  inc     esi
0x18007d6b1  cmp     esi, edi
0x18007d6b3  jb      short loc_18007D698
0x18007d6b5  jmp     short loc_18007D63D
0x18007d6b7  mov     eax, [rbp+57h+var_C0+4]
0x18007d6ba  xorps   xmm0, xmm0
0x18007d6bd  cmp     eax, [rbp+57h+var_C0]
0x18007d6c0  mov     r14, qword ptr [rbp+57h+var_D0+8]
0x18007d6c4  cmovb   eax, [rbp+57h+var_C0]
0x18007d6c8  mov     r10, [rsi+18h]
0x18007d6cc  mov     [rsp+100h+var_E0], eax; unsigned int
0x18007d6d0  mov     [rbp+57h+var_C0+4], eax
0x18007d6d3  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007d6da  mov     [rbp+57h+var_B8], rax
0x18007d6de  mov     dword ptr [rbp+57h+var_A8], 0C00000E5h
0x18007d6e5  mov     qword ptr [rbp+57h+var_68], r12
0x18007d6e9  movdqu  xmmword ptr [rbp+57h+var_68+8], xmm0
0x18007d6ee  test    r14, r14
0x18007d6f1  jz      short loc_18007D720
0x18007d6f3  mov     rcx, r12
0x18007d6f6  test    edi, edi
0x18007d6f8  jz      short loc_18007D720
0x18007d6fa  mov     rax, rcx
0x18007d6fd  inc     rcx
0x18007d700  shl     rax, 5
0x18007d704  mov     [rax+r14], r12
0x18007d708  mov     [rax+r14+8], r12
0x18007d70d  mov     [rax+r14+10h], r12
0x18007d712  mov     dword ptr [rax+r14+18h], 0FFFFFFFFh
0x18007d71b  cmp     rcx, rdi
0x18007d71e  jb      short loc_18007D6FA
0x18007d720  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d727  test    rdx, rdx
0x18007d72a  jz      loc_18007D86A
0x18007d730  mov     rcx, r10
0x18007d733  call    RtlIsTypeSafeHandleValid
0x18007d738  test    al, al
0x18007d73a  jz      loc_18007D86A
0x18007d740  test    r14, r14
0x18007d743  jnz     short loc_18007D755
0x18007d745  test    edi, edi
0x18007d747  jz      short loc_18007D755
0x18007d749  mov     [rbp+57h+var_B0], 478h
0x18007d750  jmp     loc_18007D871
0x18007d755  mov     rdx, r10
0x18007d758  lea     rcx, [rbp+57h+var_68]
0x18007d75c  call    ?Attach@?$CTypeSafeHandlePointer@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_CDF_STRING_TABLE_ENUMERATOR@2Cdf@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_STRING_TABLE_ENUMERATOR>::Attach(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR)
0x18007d761  mov     ebx, eax
0x18007d763  test    eax, eax
0x18007d765  jns     short loc_18007D78D
0x18007d767  mov     rdx, qword ptr [rbp+57h+var_68+10h]
0x18007d76b  test    rdx, rdx
0x18007d76e  jz      loc_18007D87D
0x18007d774  mov     rcx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d77b  mov     rax, [rcx+30h]
0x18007d77f  mov     rcx, qword ptr [rbp+57h+var_68]
0x18007d783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d788  jmp     loc_18007D87D
0x18007d78d  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x18007d791  mov     rax, [rcx+20h]
0x18007d795  cmp     [rcx+28h], rax
0x18007d799  jbe     short loc_18007D7D1
0x18007d79b  mov     rdx, qword ptr [rbp+57h+var_68+10h]
0x18007d79f  mov     [rbp+57h+var_B0], 47Dh
0x18007d7a6  test    rdx, rdx
0x18007d7a9  jz      short loc_18007D7BF
0x18007d7ab  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d7b2  mov     rcx, qword ptr [rbp+57h+var_68]
0x18007d7b6  mov     rax, [rax+30h]
0x18007d7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7bf  lea     rdx, [rbp+57h+var_B8]
0x18007d7c3  lea     rcx, [rbp+57h+var_B8]
0x18007d7c7  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007d7cc  jmp     loc_18007D87A
0x18007d7d1  mov     rsi, r12
0x18007d7d4  test    edi, edi
0x18007d7d6  jz      short loc_18007D848
0x18007d7d8  mov     r9, [rcx+28h]
0x18007d7dc  cmp     r9, [rcx+20h]
0x18007d7e0  jnb     short loc_18007D848
0x18007d7e2  mov     rdx, [rcx+30h]
0x18007d7e6  mov     rax, rsi
0x18007d7e9  mov     rcx, [rcx+8]
0x18007d7ed  shl     rax, 5
0x18007d7f1  add     r14, rax
0x18007d7f4  mov     edx, [rdx+r9*4]
0x18007d7f8  mov     r8, r14
0x18007d7fb  call    ?pcm_Fetch@@YAJPEBU_CDF_HEADER@@U_CDF_STRINGID@Rtl@Cdf@Windows@@AEAU_LUTF8_STRING@@@Z; pcm_Fetch(_CDF_HEADER const *,Windows::Cdf::Rtl::_CDF_STRINGID,_LUTF8_STRING &)
0x18007d800  mov     ebx, eax
0x18007d802  test    eax, eax
0x18007d804  js      short loc_18007D82F
0x18007d806  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x18007d80a  inc     rsi
0x18007d80d  mov     rcx, [rdx+28h]
0x18007d811  mov     rax, [rdx+38h]
0x18007d815  mov     ecx, [rax+rcx*4]
0x18007d818  mov     [r14+18h], ecx
0x18007d81c  inc     qword ptr [rdx+28h]
0x18007d820  cmp     rsi, rdi
0x18007d823  jnb     short loc_18007D848
0x18007d825  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x18007d829  mov     r14, qword ptr [rbp+57h+var_D0+8]
0x18007d82d  jmp     short loc_18007D7D8
0x18007d82f  mov     rdx, qword ptr [rbp+57h+var_68+10h]
0x18007d833  test    rdx, rdx
0x18007d836  jz      short loc_18007D87D
0x18007d838  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d83f  mov     rax, [rax+30h]
0x18007d843  jmp     loc_18007D77F
0x18007d848  mov     rdx, qword ptr [rbp+57h+var_68+10h]
0x18007d84c  mov     ebx, r12d
0x18007d84f  test    rdx, rdx
0x18007d852  jz      short loc_18007D880
0x18007d854  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007d85b  mov     rcx, qword ptr [rbp+57h+var_68]
0x18007d85f  mov     rax, [rax+30h]
0x18007d863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d868  jmp     short loc_18007D880
0x18007d86a  mov     [rbp+57h+var_B0], 477h
0x18007d871  lea     rcx, [rbp+57h+var_B8]
0x18007d875  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18007d87a  mov     ebx, dword ptr [rbp+57h+var_A8]
0x18007d87d  mov     rsi, r12
0x18007d880  test    ebx, ebx
0x18007d882  jns     short loc_18007D8E4
0x18007d884  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007d88a  jnz     short loc_18007D892
0x18007d88c  call    cs:__imp_DebugBreak
0x18007d892  mov     r9d, ebx; int
0x18007d895  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007d89c  mov     r8d, 5561h; char *
0x18007d8a2  lea     rcx, aStatusPropagat; "Status propagated"
0x18007d8a9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007d8ae  mov     ecx, ebx; this
0x18007d8b0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007d8b5  mov     ebx, eax
0x18007d8b7  mov     esi, r12d
0x18007d8ba  test    edi, edi
0x18007d8bc  jz      loc_18007D63D
0x18007d8c2  mov     eax, esi
0x18007d8c4  mov     rcx, [r15+rax*8]
0x18007d8c8  test    rcx, rcx
0x18007d8cb  jz      short loc_18007D8D9
0x18007d8cd  mov     rax, [rcx]
0x18007d8d0  mov     rax, [rax+10h]
0x18007d8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8d9  inc     esi
0x18007d8db  cmp     esi, edi
0x18007d8dd  jb      short loc_18007D8C2
0x18007d8df  jmp     loc_18007D63D
0x18007d8e4  test    rsi, rsi
0x18007d8e7  jz      loc_18007DA12
0x18007d8ed  xorps   xmm0, xmm0
0x18007d8f0  mov     [rsp+100h+lpMem], 0
0x18007d8f9  lea     rdx, [rbp+57h+var_88]
0x18007d8fd  lea     rcx, [rsp+100h+lpMem]
0x18007d902  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18007d906  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCultureSection@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCultureSection>>>::Allocate(void)
0x18007d90b  mov     ebx, [rax]
0x18007d90d  test    ebx, ebx
0x18007d90f  js      loc_18007DC9D
0x18007d915  cmp     dword ptr [rbp+57h+var_68], 0
0x18007d919  jz      short loc_18007D930
0x18007d91b  xor     r9d, r9d; lpArguments
0x18007d91e  xor     r8d, r8d; nNumberOfArguments
0x18007d921  mov     ecx, 0C00000E5h; dwExceptionCode
0x18007d926  lea     edx, [r9+1]; dwExceptionFlags
0x18007d92a  call    cs:__imp_RaiseException
0x18007d930  mov     eax, [rsp+100h+var_E0]
0x18007d934  lea     r8, [rbp+57h+var_68]
0x18007d938  cmp     eax, [rbp+57h+var_C0]
0x18007d93b  mov     r14, [rbp+57h+var_80]
0x18007d93f  cmovb   eax, [rbp+57h+var_C0]
0x18007d943  mov     [rsp+100h+var_E0], eax; unsigned int
0x18007d947  mov     [rbp+57h+var_C0+4], eax
0x18007d94a  mov     rax, qword ptr [rbp+57h+var_D0+8]
0x18007d94e  mov     rcx, [r14+10h]
0x18007d952  mov     edx, r12d
0x18007d955  shl     rdx, 5
0x18007d959  mov     r13d, r12d
0x18007d95c  mov     edx, [rdx+rax+18h]
0x18007d960  call    CdfGetValue
0x18007d965  mov     ebx, eax
0x18007d967  test    eax, eax
0x18007d969  js      loc_18007DC13
0x18007d96f  cmp     dword ptr [rbp+57h+var_68], 2
0x18007d973  jnz     loc_18007DBB5
0x18007d979  mov     rdx, [r14+10h]
0x18007d97d  mov     r14, [rsp+100h+lpMem]
0x18007d982  mov     r8, qword ptr [rbp+57h+var_68+8]
0x18007d986  mov     rcx, r14
0x18007d989  call    ?Initialize@CCultureSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z; CCultureSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)
0x18007d98e  mov     ebx, eax
0x18007d990  test    eax, eax
0x18007d992  js      loc_18007DB4F
0x18007d998  mov     dword ptr [rbp+57h+var_A8], 0C00000E5h
0x18007d99f  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007d9a6  mov     [rbp+57h+var_B8], rax
0x18007d9aa  cmp     r12d, edi
0x18007d9ad  jb      short loc_18007D9CB
0x18007d9af  xor     r13d, r13d
0x18007d9b2  mov     [rbp+57h+var_B0], 28h ; '('
0x18007d9b9  lea     rdx, [rbp+57h+var_B8]
0x18007d9bd  lea     rcx, [rbp+57h+var_B8]
0x18007d9c1  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007d9c6  mov     ebx, dword ptr [rbp+57h+var_A8]
0x18007d9c9  jmp     short loc_18007D9D1
0x18007d9cb  lea     r13, [r15+r13*8]
0x18007d9cf  xor     ebx, ebx
0x18007d9d1  test    ebx, ebx
  ... truncated ...
```
