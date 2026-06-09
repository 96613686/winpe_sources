# CEnumCategoryMembershipSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180077180`
- end: `0x18007772f`
- name: `?Next@CEnumCategoryMembershipSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1455`
- prototype: `__int64 __fastcall(CEnumCategoryMembershipSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x18001a478`
- `0x180033b0c`
- `0x18004f2dc`
- `0x1800569a8`
- `0x180057d58`
- `0x18005a788`
- `0x18005e108`
- `0x180067200`
- `0x180077180`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800772be`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007735b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800774fd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077579`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077676`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800772be`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007735b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800774fd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077579`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077676`

## string_xrefs

- `0x1800771b0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077244`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800772c7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077364`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077454`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077509`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007752a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077582`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800775dd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077627`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007767f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCategoryMembershipSection::Next(
        CEnumCategoryMembershipSection *this,
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
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    v61 = 20954;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v57);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v60,
      &v60);
    return (unsigned int)v62;
  }
  if ( !a3 )
  {
    v61 = 20955;
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
      (const char *)0x51DC,
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
      (const char *)0x51E0,
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
        v27 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::Allocate(
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
            (const char *)0x51EA,
            v30,
            v31);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v54);
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
        v35 = CCategoryMembershipEntry::Initialize(v54, v34, v33, v55);
        ii = v35;
        if ( v35 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x51EB,
            v35,
            v36);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v54);
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
            (const char *)0x51EC,
            v38,
            (unsigned int)v54);
          ii = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                 (Windows::ErrorHandling::COM *)(unsigned int)v38,
                 v43);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v54);
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
            (const char *)0x51ED,
            v39,
            v40);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v54);
          for ( m = 0; (unsigned int)m < (unsigned int)v4; m = (unsigned int)(m + 1) )
          {
            v42 = a3[m];
            if ( v42 )
              ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
          }
          goto LABEL_10;
        }
        v54 = 0;
        BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v54);
        v26 = (unsigned int)(v26 + 1);
        if ( (unsigned int)v26 >= v25 )
          goto LABEL_48;
      }
      if ( v27 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x51E9,
        v27,
        (unsigned int)v54);
      ii = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v27, v50);
      BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v54);
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
          (const char *)0x51F5,
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
      (const char *)0x51E1,
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
0x180077180  mov     [rsp-38h+arg_10], rbx
0x180077185  mov     [rsp-38h+arg_0], rcx
0x18007718a  push    rbp
0x18007718b  push    rsi
0x18007718c  push    rdi
0x18007718d  push    r12
0x18007718f  push    r13
0x180077191  push    r14
0x180077193  push    r15
0x180077195  mov     rbp, rsp
0x180077198  sub     rsp, 70h
0x18007719c  xor     r15d, r15d
0x18007719f  mov     edi, edx
0x1800771a1  mov     rsi, r8
0x1800771a4  mov     edx, edx
0x1800771a6  mov     rbx, rcx
0x1800771a9  mov     dword ptr [rbp+var_8], 8007054Fh
0x1800771b0  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800771b7  mov     [rbp+var_50], r15
0x1800771bb  xorps   xmm0, xmm0
0x1800771be  mov     [rbp+var_18], rax
0x1800771c2  mov     rcx, rsi
0x1800771c5  mov     [rbp+var_20], r15d
0x1800771c9  lea     r8, [rbp+arg_18]
0x1800771cd  mov     [rbp+var_1C], r15d
0x1800771d1  mov     r13, r9
0x1800771d4  mov     [rbp+arg_18], r15
0x1800771d8  movdqu  [rbp+var_30], xmm0
0x1800771dd  mov     r11d, r15d
0x1800771e0  mov     r14d, r15d
0x1800771e3  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x1800771e8  test    r13, r13
0x1800771eb  jz      short loc_1800771F1
0x1800771ed  mov     [r13+0], r15d
0x1800771f1  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR@@U_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800771f8  test    rdx, rdx
0x1800771fb  jz      loc_1800776F5
0x180077201  mov     rcx, [rbx+18h]
0x180077205  call    RtlIsTypeSafeHandleValid
0x18007720a  test    al, al
0x18007720c  jz      loc_1800776F5
0x180077212  test    rsi, rsi
0x180077215  jnz     short loc_180077235
0x180077217  lea     rcx, [rbp+var_18]
0x18007721b  mov     [rbp+var_10], 51DBh
0x180077222  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180077227  lea     rcx, [rbp+var_30]
0x18007722b  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180077230  jmp     loc_180077712
0x180077235  test    r13, r13
0x180077238  jnz     short loc_180077266
0x18007723a  cmp     edi, 1
0x18007723d  jz      short loc_18007726E
0x18007723f  mov     ebx, 80004003h
0x180077244  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007724b  mov     r8d, ebx; int
0x18007724e  mov     edx, 51DCh; char *
0x180077253  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180077258  lea     rcx, [rbp+var_30]
0x18007725c  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180077261  jmp     loc_180077715
0x180077266  test    edi, edi
0x180077268  jz      loc_180077323
0x18007726e  lea     r9, [rbp+arg_18]
0x180077272  mov     [rbp+arg_18], r15
0x180077276  mov     r8, rdi
0x180077279  lea     rcx, [rbp+arg_8]
0x18007727d  mov     edx, 8
0x180077282  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x180077287  mov     ebx, dword ptr [rbp+arg_8]
0x18007728a  test    ebx, ebx
0x18007728c  js      short loc_1800772B6
0x18007728e  mov     rbx, [rbp+arg_18]
0x180077292  call    GetProcessHeap_0
0x180077297  mov     rcx, rax; hHeap
0x18007729a  lea     r8, [rbx+8]; dwBytes
0x18007729e  xor     edx, edx; dwFlags
0x1800772a0  call    HeapAlloc_0
0x1800772a5  mov     r15, rax
0x1800772a8  test    rax, rax
0x1800772ab  jnz     short loc_180077313
0x1800772ad  mov     ebx, 0C0000017h
0x1800772b2  test    ebx, ebx
0x1800772b4  jns     short loc_18007731F
0x1800772b6  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800772bc  jnz     short loc_1800772C4
0x1800772be  call    cs:__imp_DebugBreak
0x1800772c4  mov     r9d, ebx; int
0x1800772c7  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800772ce  mov     r8d, 51E0h; char *
0x1800772d4  lea     rcx, aStatusPropagat; "Status propagated"
0x1800772db  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800772e0  mov     ecx, ebx; this
0x1800772e2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800772e7  mov     ebx, eax
0x1800772e9  test    edi, edi
0x1800772eb  jz      loc_180077258
0x1800772f1  mov     rcx, [rsi+r14*8]
0x1800772f5  test    rcx, rcx
0x1800772f8  jz      short loc_180077306
0x1800772fa  mov     rdx, [rcx]
0x1800772fd  mov     rax, [rdx+10h]
0x180077301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077306  inc     r14d
0x180077309  cmp     r14d, edi
0x18007730c  jb      short loc_1800772F1
0x18007730e  jmp     loc_180077258
0x180077313  mov     qword ptr [rbp+var_30+8], r15
0x180077317  mov     r11d, edi
0x18007731a  mov     [rbp+var_20], edi
0x18007731d  jmp     short loc_180077327
0x18007731f  mov     r11d, [rbp+var_20]
0x180077323  mov     r15, qword ptr [rbp+var_30+8]
0x180077327  mov     rcx, [rbp+arg_0]
0x18007732b  lea     r9, [rbp+var_50]
0x18007732f  test    r11d, r11d
0x180077332  mov     r8, r15
0x180077335  mov     rdx, rdi
0x180077338  cmovnz  r14d, r11d
0x18007733c  mov     rcx, [rcx+18h]
0x180077340  mov     dword ptr [rbp+arg_8], r14d
0x180077344  mov     [rbp+var_1C], r14d
0x180077348  call    ?Fetch@Rtl@Cdf@Windows@@YAJU_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR@123@_KQEAU_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_ITEM@123@PEA_K@Z; Windows::Cdf::Rtl::Fetch(Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,unsigned __int64,Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_ITEM * const,unsigned __int64 *)
0x18007734d  mov     ebx, eax
0x18007734f  test    eax, eax
0x180077351  jns     short loc_1800773B3
0x180077353  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180077359  jnz     short loc_180077361
0x18007735b  call    cs:__imp_DebugBreak
0x180077361  mov     r9d, ebx; int
0x180077364  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007736b  mov     r8d, 51E1h; char *
0x180077371  lea     rcx, aStatusPropagat; "Status propagated"
0x180077378  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007737d  mov     ecx, ebx; this
0x18007737f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180077384  xor     r14d, r14d
0x180077387  mov     ebx, eax
0x180077389  test    edi, edi
0x18007738b  jz      loc_180077258
0x180077391  mov     rcx, [rsi+r14*8]
0x180077395  test    rcx, rcx
0x180077398  jz      short loc_1800773A6
0x18007739a  mov     rax, [rcx]
0x18007739d  mov     rax, [rax+10h]
0x1800773a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773a6  inc     r14d
0x1800773a9  cmp     r14d, edi
0x1800773ac  jb      short loc_180077391
0x1800773ae  jmp     loc_180077258
0x1800773b3  mov     r14, [rbp+var_50]
0x1800773b7  xor     r12d, r12d
0x1800773ba  test    r14, r14
0x1800773bd  jz      loc_1800774D9
0x1800773c3  lea     rdx, [rbp+arg_18]
0x1800773c7  mov     [rbp+var_50], 0
0x1800773cf  lea     rcx, [rbp+var_50]
0x1800773d3  mov     [rbp+var_48], 0
0x1800773db  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::Allocate(void)
0x1800773e0  mov     ebx, [rax]
0x1800773e2  test    ebx, ebx
0x1800773e4  js      loc_18007766E
0x1800773ea  mov     ecx, dword ptr [rbp+arg_8]
0x1800773ed  lea     r8, [rbp+var_48]
0x1800773f1  cmp     ecx, [rbp+var_20]
0x1800773f4  mov     rax, [rbp+arg_0]
0x1800773f8  cmovb   ecx, [rbp+var_20]
0x1800773fc  mov     edx, [r15+r12*8]
0x180077400  mov     dword ptr [rbp+arg_8], ecx
0x180077403  mov     [rbp+var_1C], ecx
0x180077406  mov     rcx, [rax+10h]
0x18007740a  call    ?CopyOut@Com@IsolationImplementation@@YAJU_CDF@Rtl@Cdf@Windows@@U_CDF_IDENTITYID@456@PEAPEAUIDefinitionIdentity@@@Z; IsolationImplementation::Com::CopyOut(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_IDENTITYID,IDefinitionIdentity * *)
0x18007740f  mov     ebx, eax
0x180077411  test    eax, eax
0x180077413  js      loc_180077624
0x180077419  mov     ecx, dword ptr [rbp+arg_8]
0x18007741c  cmp     ecx, [rbp+var_20]
0x18007741f  mov     rax, [rbp+arg_0]
0x180077423  cmovb   ecx, [rbp+var_20]
0x180077427  mov     r9, [rbp+var_48]
0x18007742b  mov     r8d, [r15+r12*8+4]
0x180077430  mov     rdx, [rax+10h]
0x180077434  mov     dword ptr [rbp+arg_8], ecx
0x180077437  mov     [rbp+var_1C], ecx
0x18007743a  mov     rcx, [rbp+var_50]
0x18007743e  call    ?Initialize@CCategoryMembershipEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEAUIDefinitionIdentity@@@Z; CCategoryMembershipEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,IDefinitionIdentity *)
0x180077443  mov     ebx, eax
0x180077445  test    eax, eax
0x180077447  js      loc_1800775DA
0x18007744d  mov     dword ptr [rbp+var_8], 0C00000E5h
0x180077454  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007745b  mov     [rbp+var_18], rax
0x18007745f  cmp     r12d, edi
0x180077462  jb      short loc_180077489
0x180077464  mov     [rbp+var_40], 0
0x18007746c  mov     [rbp+var_10], 28h ; '('
0x180077473  lea     rdx, [rbp+var_18]
0x180077477  lea     rcx, [rbp+var_18]
0x18007747b  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180077480  mov     rcx, [rbp+var_40]
0x180077484  mov     ebx, dword ptr [rbp+var_8]
0x180077487  jmp     short loc_18007748F
0x180077489  lea     rcx, [rsi+r12*8]
0x18007748d  xor     ebx, ebx
0x18007748f  test    ebx, ebx
0x180077491  js      loc_180077571
0x180077497  mov     r9, [rbp+var_50]
0x18007749b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800774a2  mov     r8, rcx
0x1800774a5  mov     rcx, r9
0x1800774a8  mov     rax, [r9]
0x1800774ab  mov     rax, [rax]
0x1800774ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774b3  mov     ebx, eax
0x1800774b5  test    eax, eax
0x1800774b7  js      short loc_180077527
0x1800774b9  lea     rcx, [rbp+var_50]
0x1800774bd  mov     [rbp+var_50], 0
0x1800774c5  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(void)
0x1800774ca  inc     r12d
0x1800774cd  mov     eax, r12d
0x1800774d0  cmp     rax, r14
0x1800774d3  jb      loc_1800773C3
0x1800774d9  test    r13, r13
0x1800774dc  jz      loc_1800776DB
0x1800774e2  mov     eax, 0FFFFFFFFh
0x1800774e7  cmp     r14, rax
0x1800774ea  jbe     loc_1800776D7
0x1800774f0  mov     ebx, 0D0000095h
0x1800774f5  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x1800774fb  jnz     short loc_180077503
0x1800774fd  call    cs:__imp_DebugBreak
0x180077503  mov     r9d, 0D0000095h; int
0x180077509  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077510  mov     r8d, 51F5h; char *
0x180077516  lea     rcx, aHrOriginated; "HR originated"
0x18007751d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077522  jmp     loc_180077258
0x180077527  mov     r8d, eax; int
0x18007752a  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077531  mov     edx, 51EDh; char *
0x180077536  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007753b  lea     rcx, [rbp+var_50]
0x18007753f  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(void)
0x180077544  xor     r14d, r14d
0x180077547  test    edi, edi
0x180077549  jz      loc_180077258
0x18007754f  mov     rcx, [rsi+r14*8]
0x180077553  test    rcx, rcx
0x180077556  jz      short loc_180077564
0x180077558  mov     rax, [rcx]
0x18007755b  mov     rax, [rax+10h]
0x18007755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077564  inc     r14d
0x180077567  cmp     r14d, edi
0x18007756a  jb      short loc_18007754F
0x18007756c  jmp     loc_180077258
0x180077571  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180077577  jnz     short loc_18007757F
0x180077579  call    cs:__imp_DebugBreak
0x18007757f  mov     r9d, ebx; int
0x180077582  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077589  mov     r8d, 51ECh; char *
0x18007758f  lea     rcx, aStatusPropagat; "Status propagated"
0x180077596  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007759b  mov     ecx, ebx; this
0x18007759d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800775a2  lea     rcx, [rbp+var_50]
0x1800775a6  mov     ebx, eax
0x1800775a8  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(void)
0x1800775ad  xor     r14d, r14d
0x1800775b0  test    edi, edi
0x1800775b2  jz      loc_180077258
0x1800775b8  mov     rcx, [rsi+r14*8]
0x1800775bc  test    rcx, rcx
0x1800775bf  jz      short loc_1800775CD
0x1800775c1  mov     rax, [rcx]
0x1800775c4  mov     rax, [rax+10h]
0x1800775c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775cd  inc     r14d
0x1800775d0  cmp     r14d, edi
0x1800775d3  jb      short loc_1800775B8
0x1800775d5  jmp     loc_180077258
0x1800775da  mov     r8d, eax; int
0x1800775dd  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800775e4  mov     edx, 51EBh; char *
0x1800775e9  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800775ee  lea     rcx, [rbp+var_50]
0x1800775f2  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(void)
0x1800775f7  xor     r14d, r14d
0x1800775fa  test    edi, edi
0x1800775fc  jz      loc_180077258
0x180077602  mov     rcx, [rsi+r14*8]
0x180077606  test    rcx, rcx
0x180077609  jz      short loc_180077617
0x18007760b  mov     rax, [rcx]
0x18007760e  mov     rax, [rax+10h]
0x180077612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077617  inc     r14d
0x18007761a  cmp     r14d, edi
  ... truncated ...
```
