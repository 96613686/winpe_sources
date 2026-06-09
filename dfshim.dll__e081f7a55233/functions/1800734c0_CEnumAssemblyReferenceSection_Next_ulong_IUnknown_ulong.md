# CEnumAssemblyReferenceSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x1800734c0`
- end: `0x180073a6f`
- name: `?Next@CEnumAssemblyReferenceSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1455`
- prototype: `__int64 __fastcall(CEnumAssemblyReferenceSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x180013e50`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18001a578`
- `0x180033b0c`
- `0x18004f2dc`
- `0x1800569a8`
- `0x180057b28`
- `0x18005a134`
- `0x18005e2a8`
- `0x18006696c`
- `0x1800734c0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800735fe`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007369b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007383d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800738b9`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800739b6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800735fe`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007369b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007383d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800738b9`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800739b6`

## string_xrefs

- `0x1800734f0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073584`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073607`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800736a4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073794`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073849`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007386a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800738c2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007391d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180073967`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800739bf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumAssemblyReferenceSection::Next(
        CEnumAssemblyReferenceSection *this,
        unsigned int a2,
        struct IUnknown **a3,
        unsigned int *a4)
{
  __int64 v4; // rdi
  __int64 v8; // r14
  int v9; // r9d
  int v10; // r11d
  unsigned int ii; // ebx
  unsigned int v12; // ebx
  __int64 v13; // rbx
  HANDLE ProcessHeap_0; // rax
  unsigned int *v15; // rax
  unsigned int *v16; // r15
  int v17; // edx
  struct IUnknown *v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // edx
  __int64 v23; // r14
  struct IUnknown *v24; // rcx
  unsigned __int64 v25; // r14
  __int64 v26; // r12
  int v27; // ebx
  unsigned int v28; // ecx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // r9d
  unsigned int v32; // ecx
  __int64 v33; // r8
  __int64 v34; // rdx
  int v35; // eax
  int v36; // r9d
  struct IUnknown **v37; // rcx
  int v38; // ebx
  int v39; // eax
  int v40; // r9d
  __int64 m; // r14
  struct IUnknown *v42; // rcx
  int v43; // edx
  __int64 k; // r14
  struct IUnknown *v45; // rcx
  __int64 j; // r14
  struct IUnknown *v47; // rcx
  __int64 i; // r14
  struct IUnknown *v49; // rcx
  int v50; // edx
  __int64 n; // r14
  struct IUnknown *v52; // rcx
  __int64 (__fastcall ***v54)(_QWORD, GUID *, struct IUnknown **); // [rsp+20h] [rbp-50h] BYREF
  __int64 v55; // [rsp+28h] [rbp-48h] BYREF
  struct IUnknown **v56; // [rsp+30h] [rbp-40h]
  __int128 v57; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v58; // [rsp+50h] [rbp-20h]
  unsigned int v59; // [rsp+54h] [rbp-1Ch]
  const char *v60; // [rsp+58h] [rbp-18h] BYREF
  int v61; // [rsp+60h] [rbp-10h]
  Windows::ErrorHandling::COM *v62; // [rsp+68h] [rbp-8h]
  Windows::ErrorHandling::COM *v64; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v65; // [rsp+C8h] [rbp+58h] BYREF

  v4 = a2;
  LODWORD(v62) = -2147023537;
  v54 = 0;
  v60 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v58 = 0;
  v59 = 0;
  v65 = 0;
  v57 = 0;
  v8 = 0;
  IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(a3, a2, &v65);
  if ( a4 )
    *a4 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    v61 = 21626;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v57);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v60,
      &v60);
    return (unsigned int)v62;
  }
  if ( !a3 )
  {
    v61 = 21627;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v60);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v57);
    return (unsigned int)v62;
  }
  if ( a4 )
  {
    if ( !(_DWORD)v4 )
    {
      v16 = (unsigned int *)*((_QWORD *)&v57 + 1);
      goto LABEL_24;
    }
  }
  else if ( (_DWORD)v4 != 1 )
  {
    ii = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfr"
                                     "e\\amd64\\com_cms.cpp",
      (const char *)0x547C,
      -2147467261,
      v9);
    goto LABEL_10;
  }
  v65 = 0;
  BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(&v64, 8, v4, &v65);
  v12 = (unsigned int)v64;
  if ( (int)v64 < 0 )
  {
LABEL_15:
    if ( v12 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5480,
      v12,
      (unsigned int)v54);
    ii = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v17);
    do
    {
      v18 = a3[v8];
      if ( v18 )
        ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < (unsigned int)v4 );
    goto LABEL_10;
  }
  v13 = v65;
  ProcessHeap_0 = GetProcessHeap_0();
  v15 = (unsigned int *)HeapAlloc_0(ProcessHeap_0, 0, v13 + 8);
  v16 = v15;
  if ( !v15 )
  {
    v12 = -1073741801;
    goto LABEL_15;
  }
  *((_QWORD *)&v57 + 1) = v15;
  v10 = v4;
  v58 = v4;
LABEL_24:
  if ( v10 )
    LODWORD(v8) = v10;
  v19 = *((_QWORD *)this + 3);
  LODWORD(v64) = v8;
  v59 = v8;
  v20 = Windows::Cdf::Rtl::Fetch(v19, v4, v16, &v54);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v25 = (unsigned __int64)v54;
    v26 = 0;
    if ( v54 )
    {
      while ( 1 )
      {
        v54 = 0;
        v55 = 0;
        v27 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::Allocate(
                           &v54,
                           &v65);
        if ( v27 < 0 )
          break;
        v28 = (unsigned int)v64;
        if ( (unsigned int)v64 < v58 )
          v28 = v58;
        v29 = v16[2 * v26];
        LODWORD(v64) = v28;
        v59 = v28;
        v30 = IsolationImplementation::Com::CopyOut(*((_QWORD *)this + 2), v29, &v55);
        ii = v30;
        if ( v30 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x548A,
            v30,
            v31);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v54);
          for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
          {
            v49 = a3[i];
            if ( v49 )
              ((void (__fastcall *)(struct IUnknown *))v49->lpVtbl->Release)(v49);
          }
          goto LABEL_10;
        }
        v32 = (unsigned int)v64;
        if ( (unsigned int)v64 < v58 )
          v32 = v58;
        v33 = v16[2 * v26 + 1];
        v34 = *((_QWORD *)this + 2);
        LODWORD(v64) = v32;
        v59 = v32;
        v35 = CAssemblyReferenceEntry::Initialize(v54, v34, v33, v55);
        ii = v35;
        if ( v35 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x548B,
            v35,
            v36);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v54);
          for ( j = 0; (unsigned int)j < (unsigned int)v4; j = (unsigned int)(j + 1) )
          {
            v47 = a3[j];
            if ( v47 )
              ((void (__fastcall *)(struct IUnknown *))v47->lpVtbl->Release)(v47);
          }
          goto LABEL_10;
        }
        LODWORD(v62) = -1073741595;
        v60 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
        if ( (unsigned int)v26 < (unsigned int)v4 )
        {
          v37 = &a3[v26];
          v38 = 0;
        }
        else
        {
          v56 = 0;
          v61 = 40;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
            &v60,
            &v60);
          v37 = v56;
          v38 = (int)v62;
        }
        if ( v38 < 0 )
        {
          if ( v38 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x548C,
            v38,
            (unsigned int)v54);
          ii = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v38,
                 v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v54);
          for ( k = 0; (unsigned int)k < (unsigned int)v4; k = (unsigned int)(k + 1) )
          {
            v45 = a3[k];
            if ( v45 )
              ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
          }
          goto LABEL_10;
        }
        v39 = (**v54)(v54, &GUID_00000000_0000_0000_c000_000000000046, v37);
        ii = v39;
        if ( v39 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x548D,
            v39,
            v40);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v54);
          for ( m = 0; (unsigned int)m < (unsigned int)v4; m = (unsigned int)(m + 1) )
          {
            v42 = a3[m];
            if ( v42 )
              ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
          }
          goto LABEL_10;
        }
        v54 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v54);
        v26 = (unsigned int)(v26 + 1);
        if ( (unsigned int)v26 >= v25 )
          goto LABEL_48;
      }
      if ( v27 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x5489,
        v27,
        (unsigned int)v54);
      ii = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v27, v50);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v54);
      for ( n = 0; (unsigned int)n < (unsigned int)v4; n = (unsigned int)(n + 1) )
      {
        v52 = a3[n];
        if ( v52 )
          ((void (__fastcall *)(struct IUnknown *))v52->lpVtbl->Release)(v52);
      }
      goto LABEL_10;
    }
LABEL_48:
    if ( a4 )
    {
      if ( v25 > 0xFFFFFFFF )
      {
        ii = -805306219;
        if ( g_HRESULT_to_break_on == -805306219 )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"HR originated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
          (const char *)0x5495,
          -805306219,
          (unsigned int)v54);
        goto LABEL_10;
      }
      *a4 = v25;
    }
    ii = v25 != v4;
  }
  else
  {
    if ( v20 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5481,
      v21,
      (unsigned int)v54);
    v23 = 0;
    for ( ii = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v21, v22);
          (unsigned int)v23 < (unsigned int)v4;
          v23 = (unsigned int)(v23 + 1) )
    {
      v24 = a3[v23];
      if ( v24 )
        ((void (__fastcall *)(struct IUnknown *))v24->lpVtbl->Release)(v24);
    }
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v57);
  return ii;
}

```

## disassembly

```asm
0x1800734c0  mov     [rsp-38h+arg_10], rbx
0x1800734c5  mov     [rsp-38h+arg_0], rcx
0x1800734ca  push    rbp
0x1800734cb  push    rsi
0x1800734cc  push    rdi
0x1800734cd  push    r12
0x1800734cf  push    r13
0x1800734d1  push    r14
0x1800734d3  push    r15
0x1800734d5  mov     rbp, rsp
0x1800734d8  sub     rsp, 70h
0x1800734dc  xor     r15d, r15d
0x1800734df  mov     edi, edx
0x1800734e1  mov     rsi, r8
0x1800734e4  mov     edx, edx
0x1800734e6  mov     rbx, rcx
0x1800734e9  mov     dword ptr [rbp+var_8], 8007054Fh
0x1800734f0  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800734f7  mov     [rbp+var_50], r15
0x1800734fb  xorps   xmm0, xmm0
0x1800734fe  mov     [rbp+var_18], rax
0x180073502  mov     rcx, rsi
0x180073505  mov     [rbp+var_20], r15d
0x180073509  lea     r8, [rbp+arg_18]
0x18007350d  mov     [rbp+var_1C], r15d
0x180073511  mov     r13, r9
0x180073514  mov     [rbp+arg_18], r15
0x180073518  movdqu  [rbp+var_30], xmm0
0x18007351d  mov     r11d, r15d
0x180073520  mov     r14d, r15d
0x180073523  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x180073528  test    r13, r13
0x18007352b  jz      short loc_180073531
0x18007352d  mov     [r13+0], r15d
0x180073531  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180073538  test    rdx, rdx
0x18007353b  jz      loc_180073A35
0x180073541  mov     rcx, [rbx+18h]
0x180073545  call    RtlIsTypeSafeHandleValid
0x18007354a  test    al, al
0x18007354c  jz      loc_180073A35
0x180073552  test    rsi, rsi
0x180073555  jnz     short loc_180073575
0x180073557  lea     rcx, [rbp+var_18]
0x18007355b  mov     [rbp+var_10], 547Bh
0x180073562  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180073567  lea     rcx, [rbp+var_30]
0x18007356b  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180073570  jmp     loc_180073A52
0x180073575  test    r13, r13
0x180073578  jnz     short loc_1800735A6
0x18007357a  cmp     edi, 1
0x18007357d  jz      short loc_1800735AE
0x18007357f  mov     ebx, 80004003h
0x180073584  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007358b  mov     r8d, ebx; int
0x18007358e  mov     edx, 547Ch; char *
0x180073593  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180073598  lea     rcx, [rbp+var_30]
0x18007359c  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x1800735a1  jmp     loc_180073A55
0x1800735a6  test    edi, edi
0x1800735a8  jz      loc_180073663
0x1800735ae  lea     r9, [rbp+arg_18]
0x1800735b2  mov     [rbp+arg_18], r15
0x1800735b6  mov     r8, rdi
0x1800735b9  lea     rcx, [rbp+arg_8]
0x1800735bd  mov     edx, 8
0x1800735c2  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x1800735c7  mov     ebx, dword ptr [rbp+arg_8]
0x1800735ca  test    ebx, ebx
0x1800735cc  js      short loc_1800735F6
0x1800735ce  mov     rbx, [rbp+arg_18]
0x1800735d2  call    GetProcessHeap_0
0x1800735d7  mov     rcx, rax; hHeap
0x1800735da  lea     r8, [rbx+8]; dwBytes
0x1800735de  xor     edx, edx; dwFlags
0x1800735e0  call    HeapAlloc_0
0x1800735e5  mov     r15, rax
0x1800735e8  test    rax, rax
0x1800735eb  jnz     short loc_180073653
0x1800735ed  mov     ebx, 0C0000017h
0x1800735f2  test    ebx, ebx
0x1800735f4  jns     short loc_18007365F
0x1800735f6  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800735fc  jnz     short loc_180073604
0x1800735fe  call    cs:__imp_DebugBreak
0x180073604  mov     r9d, ebx; int
0x180073607  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007360e  mov     r8d, 5480h; char *
0x180073614  lea     rcx, aStatusPropagat; "Status propagated"
0x18007361b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180073620  mov     ecx, ebx; this
0x180073622  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180073627  mov     ebx, eax
0x180073629  test    edi, edi
0x18007362b  jz      loc_180073598
0x180073631  mov     rcx, [rsi+r14*8]
0x180073635  test    rcx, rcx
0x180073638  jz      short loc_180073646
0x18007363a  mov     rdx, [rcx]
0x18007363d  mov     rax, [rdx+10h]
0x180073641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073646  inc     r14d
0x180073649  cmp     r14d, edi
0x18007364c  jb      short loc_180073631
0x18007364e  jmp     loc_180073598
0x180073653  mov     qword ptr [rbp+var_30+8], r15
0x180073657  mov     r11d, edi
0x18007365a  mov     [rbp+var_20], edi
0x18007365d  jmp     short loc_180073667
0x18007365f  mov     r11d, [rbp+var_20]
0x180073663  mov     r15, qword ptr [rbp+var_30+8]
0x180073667  mov     rcx, [rbp+arg_0]
0x18007366b  lea     r9, [rbp+var_50]
0x18007366f  test    r11d, r11d
0x180073672  mov     r8, r15
0x180073675  mov     rdx, rdi
0x180073678  cmovnz  r14d, r11d
0x18007367c  mov     rcx, [rcx+18h]
0x180073680  mov     dword ptr [rbp+arg_8], r14d
0x180073684  mov     [rbp+var_1C], r14d
0x180073688  call    ?Fetch@Rtl@Cdf@Windows@@YAJU_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@123@_KQEAU_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@123@PEA_K@Z; Windows::Cdf::Rtl::Fetch(Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,unsigned __int64,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM * const,unsigned __int64 *)
0x18007368d  mov     ebx, eax
0x18007368f  test    eax, eax
0x180073691  jns     short loc_1800736F3
0x180073693  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180073699  jnz     short loc_1800736A1
0x18007369b  call    cs:__imp_DebugBreak
0x1800736a1  mov     r9d, ebx; int
0x1800736a4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800736ab  mov     r8d, 5481h; char *
0x1800736b1  lea     rcx, aStatusPropagat; "Status propagated"
0x1800736b8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800736bd  mov     ecx, ebx; this
0x1800736bf  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800736c4  xor     r14d, r14d
0x1800736c7  mov     ebx, eax
0x1800736c9  test    edi, edi
0x1800736cb  jz      loc_180073598
0x1800736d1  mov     rcx, [rsi+r14*8]
0x1800736d5  test    rcx, rcx
0x1800736d8  jz      short loc_1800736E6
0x1800736da  mov     rax, [rcx]
0x1800736dd  mov     rax, [rax+10h]
0x1800736e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800736e6  inc     r14d
0x1800736e9  cmp     r14d, edi
0x1800736ec  jb      short loc_1800736D1
0x1800736ee  jmp     loc_180073598
0x1800736f3  mov     r14, [rbp+var_50]
0x1800736f7  xor     r12d, r12d
0x1800736fa  test    r14, r14
0x1800736fd  jz      loc_180073819
0x180073703  lea     rdx, [rbp+arg_18]
0x180073707  mov     [rbp+var_50], 0
0x18007370f  lea     rcx, [rbp+var_50]
0x180073713  mov     [rbp+var_48], 0
0x18007371b  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::Allocate(void)
0x180073720  mov     ebx, [rax]
0x180073722  test    ebx, ebx
0x180073724  js      loc_1800739AE
0x18007372a  mov     ecx, dword ptr [rbp+arg_8]
0x18007372d  lea     r8, [rbp+var_48]
0x180073731  cmp     ecx, [rbp+var_20]
0x180073734  mov     rax, [rbp+arg_0]
0x180073738  cmovb   ecx, [rbp+var_20]
0x18007373c  mov     edx, [r15+r12*8]
0x180073740  mov     dword ptr [rbp+arg_8], ecx
0x180073743  mov     [rbp+var_1C], ecx
0x180073746  mov     rcx, [rax+10h]
0x18007374a  call    ?CopyOut@Com@IsolationImplementation@@YAJU_CDF@Rtl@Cdf@Windows@@U_CDF_IDENTITYID@456@PEAPEAUIReferenceIdentity@@@Z; IsolationImplementation::Com::CopyOut(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_IDENTITYID,IReferenceIdentity * *)
0x18007374f  mov     ebx, eax
0x180073751  test    eax, eax
0x180073753  js      loc_180073964
0x180073759  mov     ecx, dword ptr [rbp+arg_8]
0x18007375c  cmp     ecx, [rbp+var_20]
0x18007375f  mov     rax, [rbp+arg_0]
0x180073763  cmovb   ecx, [rbp+var_20]
0x180073767  mov     r9, [rbp+var_48]
0x18007376b  mov     r8d, [r15+r12*8+4]
0x180073770  mov     rdx, [rax+10h]
0x180073774  mov     dword ptr [rbp+arg_8], ecx
0x180073777  mov     [rbp+var_1C], ecx
0x18007377a  mov     rcx, [rbp+var_50]
0x18007377e  call    ?Initialize@CAssemblyReferenceEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEAUIReferenceIdentity@@@Z; CAssemblyReferenceEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,IReferenceIdentity *)
0x180073783  mov     ebx, eax
0x180073785  test    eax, eax
0x180073787  js      loc_18007391A
0x18007378d  mov     dword ptr [rbp+var_8], 0C00000E5h
0x180073794  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007379b  mov     [rbp+var_18], rax
0x18007379f  cmp     r12d, edi
0x1800737a2  jb      short loc_1800737C9
0x1800737a4  mov     [rbp+var_40], 0
0x1800737ac  mov     [rbp+var_10], 28h ; '('
0x1800737b3  lea     rdx, [rbp+var_18]
0x1800737b7  lea     rcx, [rbp+var_18]
0x1800737bb  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800737c0  mov     rcx, [rbp+var_40]
0x1800737c4  mov     ebx, dword ptr [rbp+var_8]
0x1800737c7  jmp     short loc_1800737CF
0x1800737c9  lea     rcx, [rsi+r12*8]
0x1800737cd  xor     ebx, ebx
0x1800737cf  test    ebx, ebx
0x1800737d1  js      loc_1800738B1
0x1800737d7  mov     r9, [rbp+var_50]
0x1800737db  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800737e2  mov     r8, rcx
0x1800737e5  mov     rcx, r9
0x1800737e8  mov     rax, [r9]
0x1800737eb  mov     rax, [rax]
0x1800737ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737f3  mov     ebx, eax
0x1800737f5  test    eax, eax
0x1800737f7  js      short loc_180073867
0x1800737f9  lea     rcx, [rbp+var_50]
0x1800737fd  mov     [rbp+var_50], 0
0x180073805  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(void)
0x18007380a  inc     r12d
0x18007380d  mov     eax, r12d
0x180073810  cmp     rax, r14
0x180073813  jb      loc_180073703
0x180073819  test    r13, r13
0x18007381c  jz      loc_180073A1B
0x180073822  mov     eax, 0FFFFFFFFh
0x180073827  cmp     r14, rax
0x18007382a  jbe     loc_180073A17
0x180073830  mov     ebx, 0D0000095h
0x180073835  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x18007383b  jnz     short loc_180073843
0x18007383d  call    cs:__imp_DebugBreak
0x180073843  mov     r9d, 0D0000095h; int
0x180073849  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073850  mov     r8d, 5495h; char *
0x180073856  lea     rcx, aHrOriginated; "HR originated"
0x18007385d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180073862  jmp     loc_180073598
0x180073867  mov     r8d, eax; int
0x18007386a  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073871  mov     edx, 548Dh; char *
0x180073876  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007387b  lea     rcx, [rbp+var_50]
0x18007387f  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(void)
0x180073884  xor     r14d, r14d
0x180073887  test    edi, edi
0x180073889  jz      loc_180073598
0x18007388f  mov     rcx, [rsi+r14*8]
0x180073893  test    rcx, rcx
0x180073896  jz      short loc_1800738A4
0x180073898  mov     rax, [rcx]
0x18007389b  mov     rax, [rax+10h]
0x18007389f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800738a4  inc     r14d
0x1800738a7  cmp     r14d, edi
0x1800738aa  jb      short loc_18007388F
0x1800738ac  jmp     loc_180073598
0x1800738b1  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800738b7  jnz     short loc_1800738BF
0x1800738b9  call    cs:__imp_DebugBreak
0x1800738bf  mov     r9d, ebx; int
0x1800738c2  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800738c9  mov     r8d, 548Ch; char *
0x1800738cf  lea     rcx, aStatusPropagat; "Status propagated"
0x1800738d6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800738db  mov     ecx, ebx; this
0x1800738dd  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800738e2  lea     rcx, [rbp+var_50]
0x1800738e6  mov     ebx, eax
0x1800738e8  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(void)
0x1800738ed  xor     r14d, r14d
0x1800738f0  test    edi, edi
0x1800738f2  jz      loc_180073598
0x1800738f8  mov     rcx, [rsi+r14*8]
0x1800738fc  test    rcx, rcx
0x1800738ff  jz      short loc_18007390D
0x180073901  mov     rax, [rcx]
0x180073904  mov     rax, [rax+10h]
0x180073908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007390d  inc     r14d
0x180073910  cmp     r14d, edi
0x180073913  jb      short loc_1800738F8
0x180073915  jmp     loc_180073598
0x18007391a  mov     r8d, eax; int
0x18007391d  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180073924  mov     edx, 548Bh; char *
0x180073929  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007392e  lea     rcx, [rbp+var_50]
0x180073932  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(void)
0x180073937  xor     r14d, r14d
0x18007393a  test    edi, edi
0x18007393c  jz      loc_180073598
0x180073942  mov     rcx, [rsi+r14*8]
0x180073946  test    rcx, rcx
0x180073949  jz      short loc_180073957
0x18007394b  mov     rax, [rcx]
0x18007394e  mov     rax, [rax+10h]
0x180073952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073957  inc     r14d
0x18007395a  cmp     r14d, edi
  ... truncated ...
```
