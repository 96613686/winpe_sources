# CEnumCategoryMembershipDataSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180076ca0`
- end: `0x180077179`
- name: `?Next@CEnumCategoryMembershipDataSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1241`
- prototype: `__int64 __fastcall(CEnumCategoryMembershipDataSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x180014738`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x180033b0c`
- `0x18004f2dc`
- `0x1800569a8`
- `0x180057ce8`
- `0x18005a644`
- `0x18005e01c`
- `0x18006703c`
- `0x180076ca0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076d96`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076e1e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076f92`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007700e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800770c1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076d96`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076e1e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076f92`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007700e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800770c1`

## string_xrefs

- `0x180076cd0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076d9f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076e27`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076ee9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076f9e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076fbf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077017`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077072`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800770ca`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCategoryMembershipDataSection::Next(
        CEnumCategoryMembershipDataSection *this,
        unsigned int a2,
        struct IUnknown **a3,
        unsigned int *a4)
{
  __int64 v4; // rdi
  int v8; // r9d
  Windows::ErrorHandling::COM *v9; // r11
  unsigned int n; // ebx
  int v11; // ebx
  int v12; // edx
  unsigned int ii; // r14d
  struct IUnknown *v14; // rcx
  unsigned int v15; // r13d
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // edx
  __int64 v20; // r14
  struct IUnknown *v21; // rcx
  unsigned __int64 v22; // r14
  __int64 v23; // r12
  int v24; // ebx
  int v25; // eax
  int v26; // r9d
  struct IUnknown **v27; // rcx
  int v28; // ebx
  int v29; // eax
  int v30; // r9d
  __int64 k; // r14
  struct IUnknown *v32; // rcx
  int v33; // edx
  __int64 j; // r14
  struct IUnknown *v35; // rcx
  __int64 i; // r14
  struct IUnknown *v37; // rcx
  int v38; // edx
  __int64 m; // r14
  struct IUnknown *v40; // rcx
  struct IUnknown **v42; // [rsp+20h] [rbp-40h] BYREF
  __int128 v43; // [rsp+30h] [rbp-30h] BYREF
  __int64 v44; // [rsp+40h] [rbp-20h]
  const char *v45; // [rsp+48h] [rbp-18h] BYREF
  int v46; // [rsp+50h] [rbp-10h]
  Windows::ErrorHandling::COM *v47; // [rsp+58h] [rbp-8h]
  char v49; // [rsp+A8h] [rbp+48h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, struct IUnknown **); // [rsp+B8h] [rbp+58h] BYREF

  v4 = a2;
  LODWORD(v47) = -2147023537;
  v50 = 0;
  v45 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v44 = 0;
  v42 = 0;
  v43 = 0;
  IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(a3, a2, &v42);
  if ( a4 )
    *a4 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    v46 = 21178;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v45,
      &v45);
    return (unsigned int)v47;
  }
  if ( !a3 )
  {
    v46 = 21179;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v45);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
    return (unsigned int)v47;
  }
  if ( a4 || (_DWORD)v4 == 1 )
  {
    v11 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned long,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>>::EnlargeNoPreserve(
                       &v43,
                       &v49,
                       (unsigned int)v4);
    if ( v11 >= 0 )
    {
      v15 = HIDWORD(v44);
      if ( HIDWORD(v44) < (unsigned int)v44 )
        v15 = v44;
      v16 = *((_QWORD *)this + 3);
      HIDWORD(v44) = v15;
      v17 = Windows::Cdf::Rtl::Fetch(v16, v4, *((_QWORD *)&v43 + 1), &v50);
      v18 = v17;
      if ( v17 >= 0 )
      {
        v22 = (unsigned __int64)v50;
        v23 = 0;
        if ( v50 )
        {
          while ( 1 )
          {
            v50 = 0;
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::Allocate(
                               &v50,
                               &v49);
            if ( v24 < 0 )
              break;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            HIDWORD(v44) = v15;
            v25 = CCategoryMembershipDataEntry::Initialize(
                    v50,
                    *((_QWORD *)this + 2),
                    *(unsigned int *)(*((_QWORD *)&v43 + 1) + 8 * v23 + 4),
                    *(unsigned int *)(*((_QWORD *)&v43 + 1) + 8 * v23));
            n = v25;
            if ( v25 < 0 )
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whid"
                                               "bey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x52CB,
                v25,
                v26);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(&v50);
              for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
              {
                v37 = a3[i];
                if ( v37 )
                  ((void (__fastcall *)(struct IUnknown *))v37->lpVtbl->Release)(v37);
              }
              goto LABEL_10;
            }
            LODWORD(v47) = -1073741595;
            v45 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
            if ( (unsigned int)v23 < (unsigned int)v4 )
            {
              v27 = &a3[v23];
              v28 = 0;
            }
            else
            {
              v42 = 0;
              v46 = 40;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                &v45,
                &v45);
              v27 = v42;
              v28 = (int)v47;
            }
            if ( v28 < 0 )
            {
              if ( v28 == g_NTSTATUS_to_break_on_propagate )
                DebugBreak();
              Windows::ErrorHandling::COM::ReportError(
                (Windows::ErrorHandling::COM *)"Status propagated",
                "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x52CC,
                v28,
                (unsigned int)v42);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v28,
                    v33);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(&v50);
              for ( j = 0; (unsigned int)j < (unsigned int)v4; j = (unsigned int)(j + 1) )
              {
                v35 = a3[j];
                if ( v35 )
                  ((void (__fastcall *)(struct IUnknown *))v35->lpVtbl->Release)(v35);
              }
              goto LABEL_10;
            }
            v29 = (**v50)(v50, &GUID_00000000_0000_0000_c000_000000000046, v27);
            n = v29;
            if ( v29 < 0 )
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whid"
                                               "bey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x52CD,
                v29,
                v30);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(&v50);
              for ( k = 0; (unsigned int)k < (unsigned int)v4; k = (unsigned int)(k + 1) )
              {
                v32 = a3[k];
                if ( v32 )
                  ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
              }
              goto LABEL_10;
            }
            v50 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(&v50);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x52C9,
            v24,
            (unsigned int)v42);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v38);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(&v50);
          for ( m = 0; (unsigned int)m < (unsigned int)v4; m = (unsigned int)(m + 1) )
          {
            v40 = a3[m];
            if ( v40 )
              ((void (__fastcall *)(struct IUnknown *))v40->lpVtbl->Release)(v40);
          }
          goto LABEL_10;
        }
LABEL_42:
        if ( a4 )
        {
          if ( v22 > 0xFFFFFFFF )
          {
            n = -805306219;
            if ( g_HRESULT_to_break_on == -805306219 )
              DebugBreak();
            Windows::ErrorHandling::COM::ReportError(
              (Windows::ErrorHandling::COM *)"HR originated",
              "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
              (const char *)0x52D5,
              -805306219,
              (unsigned int)v42);
            goto LABEL_10;
          }
          *a4 = v22;
        }
        n = v22 != v4;
      }
      else
      {
        if ( v17 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
          (const char *)0x52C1,
          v18,
          (unsigned int)v42);
        v20 = 0;
        for ( n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v18, v19);
              (unsigned int)v20 < (unsigned int)v4;
              v20 = (unsigned int)(v20 + 1) )
        {
          v21 = a3[v20];
          if ( v21 )
            ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
        }
      }
    }
    else
    {
      if ( v11 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x52C0,
        v11,
        (unsigned int)v42);
      n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v11, v12);
      for ( ii = 0; ii < (unsigned int)v4; ++ii )
      {
        v14 = a3[ii];
        if ( v14 )
          ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
      }
    }
  }
  else
  {
    n = -2147467261;
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x52BC, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
  return n;
}

```

## disassembly

```asm
0x180076ca0  mov     [rsp-38h+arg_10], rbx
0x180076ca5  mov     [rsp-38h+arg_0], rcx
0x180076caa  push    rbp
0x180076cab  push    rsi
0x180076cac  push    rdi
0x180076cad  push    r12
0x180076caf  push    r13
0x180076cb1  push    r14
0x180076cb3  push    r15
0x180076cb5  mov     rbp, rsp
0x180076cb8  sub     rsp, 60h
0x180076cbc  xor     r13d, r13d
0x180076cbf  mov     edi, edx
0x180076cc1  mov     rsi, r8
0x180076cc4  mov     edx, edx
0x180076cc6  mov     r12, rcx
0x180076cc9  mov     dword ptr [rbp+var_8], 8007054Fh
0x180076cd0  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076cd7  mov     [rbp+arg_18], r13
0x180076cdb  xorps   xmm0, xmm0
0x180076cde  mov     [rbp+var_18], r11
0x180076ce2  mov     rcx, rsi
0x180076ce5  mov     [rbp+var_20], r13
0x180076ce9  lea     r8, [rbp+var_40]
0x180076ced  mov     [rbp+var_40], r13
0x180076cf1  mov     r15, r9
0x180076cf4  movdqu  [rbp+var_30], xmm0
0x180076cf9  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x180076cfe  test    r15, r15
0x180076d01  jz      short loc_180076D06
0x180076d03  mov     [r15], r13d
0x180076d06  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180076d0d  test    rdx, rdx
0x180076d10  jz      loc_18007713F
0x180076d16  mov     rcx, [r12+18h]
0x180076d1b  call    RtlIsTypeSafeHandleValid
0x180076d20  test    al, al
0x180076d22  jz      loc_18007713F
0x180076d28  test    rsi, rsi
0x180076d2b  jnz     short loc_180076D4B
0x180076d2d  lea     rcx, [rbp+var_18]
0x180076d31  mov     [rbp+var_10], 52BBh
0x180076d38  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180076d3d  lea     rcx, [rbp+var_30]
0x180076d41  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180076d46  jmp     loc_18007715C
0x180076d4b  test    r15, r15
0x180076d4e  jnz     short loc_180076D78
0x180076d50  cmp     edi, 1
0x180076d53  jz      short loc_180076D78
0x180076d55  mov     ebx, 80004003h
0x180076d5a  mov     edx, 52BCh; char *
0x180076d5f  mov     r8d, ebx; int
0x180076d62  mov     rcx, r11; this
0x180076d65  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180076d6a  lea     rcx, [rbp+var_30]
0x180076d6e  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180076d73  jmp     loc_18007715F
0x180076d78  mov     r8d, edi
0x180076d7b  lea     rdx, [rbp+arg_8]
0x180076d7f  lea     rcx, [rbp+var_30]
0x180076d83  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180076d88  mov     ebx, [rax]
0x180076d8a  test    ebx, ebx
0x180076d8c  jns     short loc_180076DEA
0x180076d8e  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180076d94  jnz     short loc_180076D9C
0x180076d96  call    cs:__imp_DebugBreak
0x180076d9c  mov     r9d, ebx; int
0x180076d9f  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076da6  mov     r8d, 52C0h; char *
0x180076dac  lea     rcx, aStatusPropagat; "Status propagated"
0x180076db3  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180076db8  mov     ecx, ebx; this
0x180076dba  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180076dbf  mov     ebx, eax
0x180076dc1  mov     r14d, r13d
0x180076dc4  test    edi, edi
0x180076dc6  jz      short loc_180076D6A
0x180076dc8  mov     ecx, r14d
0x180076dcb  mov     rcx, [rsi+rcx*8]
0x180076dcf  test    rcx, rcx
0x180076dd2  jz      short loc_180076DE0
0x180076dd4  mov     rdx, [rcx]
0x180076dd7  mov     rax, [rdx+10h]
0x180076ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076de0  inc     r14d
0x180076de3  cmp     r14d, edi
0x180076de6  jb      short loc_180076DC8
0x180076de8  jmp     short loc_180076D6A
0x180076dea  mov     r13d, dword ptr [rbp+var_20+4]
0x180076dee  lea     r9, [rbp+arg_18]
0x180076df2  cmp     r13d, dword ptr [rbp+var_20]
0x180076df6  mov     rdx, rdi
0x180076df9  mov     r8, qword ptr [rbp+var_30+8]
0x180076dfd  cmovb   r13d, dword ptr [rbp+var_20]
0x180076e02  mov     rcx, [r12+18h]
0x180076e07  mov     dword ptr [rbp+var_20+4], r13d
0x180076e0b  call    ?Fetch@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE_ENUMERATOR@123@_KQEAU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@123@PEA_K@Z; Windows::Cdf::Rtl::Fetch(Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,unsigned __int64,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM * const,unsigned __int64 *)
0x180076e10  mov     ebx, eax
0x180076e12  test    eax, eax
0x180076e14  jns     short loc_180076E76
0x180076e16  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180076e1c  jnz     short loc_180076E24
0x180076e1e  call    cs:__imp_DebugBreak
0x180076e24  mov     r9d, ebx; int
0x180076e27  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076e2e  mov     r8d, 52C1h; char *
0x180076e34  lea     rcx, aStatusPropagat; "Status propagated"
0x180076e3b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180076e40  mov     ecx, ebx; this
0x180076e42  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180076e47  xor     r14d, r14d
0x180076e4a  mov     ebx, eax
0x180076e4c  test    edi, edi
0x180076e4e  jz      loc_180076D6A
0x180076e54  mov     rcx, [rsi+r14*8]
0x180076e58  test    rcx, rcx
0x180076e5b  jz      short loc_180076E69
0x180076e5d  mov     rax, [rcx]
0x180076e60  mov     rax, [rax+10h]
0x180076e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e69  inc     r14d
0x180076e6c  cmp     r14d, edi
0x180076e6f  jb      short loc_180076E54
0x180076e71  jmp     loc_180076D6A
0x180076e76  mov     r14, [rbp+arg_18]
0x180076e7a  xor     r12d, r12d
0x180076e7d  test    r14, r14
0x180076e80  jz      loc_180076F6E
0x180076e86  lea     rdx, [rbp+arg_8]
0x180076e8a  mov     [rbp+arg_18], 0
0x180076e92  lea     rcx, [rbp+arg_18]
0x180076e96  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipDataEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::Allocate(void)
0x180076e9b  mov     ebx, [rax]
0x180076e9d  test    ebx, ebx
0x180076e9f  js      loc_1800770B9
0x180076ea5  mov     eax, dword ptr [rbp+var_20]
0x180076ea8  cmp     r13d, eax
0x180076eab  mov     rcx, [rbp+arg_18]
0x180076eaf  cmovb   r13d, eax
0x180076eb3  cmp     r13d, eax
0x180076eb6  cmovb   r13d, eax
0x180076eba  mov     rax, qword ptr [rbp+var_30+8]
0x180076ebe  mov     dword ptr [rbp+var_20+4], r13d
0x180076ec2  mov     r9d, [rax+r12*8]
0x180076ec6  mov     r8d, [rax+r12*8+4]
0x180076ecb  mov     rax, [rbp+arg_0]
0x180076ecf  mov     rdx, [rax+10h]
0x180076ed3  call    ?Initialize@CCategoryMembershipDataEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@K@Z; CCategoryMembershipDataEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ulong)
0x180076ed8  mov     ebx, eax
0x180076eda  test    eax, eax
0x180076edc  js      loc_18007706F
0x180076ee2  mov     dword ptr [rbp+var_8], 0C00000E5h
0x180076ee9  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076ef0  mov     [rbp+var_18], rax
0x180076ef4  cmp     r12d, edi
0x180076ef7  jb      short loc_180076F1E
0x180076ef9  mov     [rbp+var_40], 0
0x180076f01  mov     [rbp+var_10], 28h ; '('
0x180076f08  lea     rdx, [rbp+var_18]
0x180076f0c  lea     rcx, [rbp+var_18]
0x180076f10  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180076f15  mov     rcx, [rbp+var_40]
0x180076f19  mov     ebx, dword ptr [rbp+var_8]
0x180076f1c  jmp     short loc_180076F24
0x180076f1e  lea     rcx, [rsi+r12*8]
0x180076f22  xor     ebx, ebx
0x180076f24  test    ebx, ebx
0x180076f26  js      loc_180077006
0x180076f2c  mov     r9, [rbp+arg_18]
0x180076f30  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180076f37  mov     r8, rcx
0x180076f3a  mov     rcx, r9
0x180076f3d  mov     rax, [r9]
0x180076f40  mov     rax, [rax]
0x180076f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f48  mov     ebx, eax
0x180076f4a  test    eax, eax
0x180076f4c  js      short loc_180076FBC
0x180076f4e  lea     rcx, [rbp+arg_18]
0x180076f52  mov     [rbp+arg_18], 0
0x180076f5a  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipDataEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(void)
0x180076f5f  inc     r12d
0x180076f62  mov     eax, r12d
0x180076f65  cmp     rax, r14
0x180076f68  jb      loc_180076E86
0x180076f6e  test    r15, r15
0x180076f71  jz      loc_180077125
0x180076f77  mov     eax, 0FFFFFFFFh
0x180076f7c  cmp     r14, rax
0x180076f7f  jbe     loc_180077122
0x180076f85  mov     ebx, 0D0000095h
0x180076f8a  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x180076f90  jnz     short loc_180076F98
0x180076f92  call    cs:__imp_DebugBreak
0x180076f98  mov     r9d, 0D0000095h; int
0x180076f9e  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076fa5  mov     r8d, 52D5h; char *
0x180076fab  lea     rcx, aHrOriginated; "HR originated"
0x180076fb2  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180076fb7  jmp     loc_180076D6A
0x180076fbc  mov     r8d, eax; int
0x180076fbf  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076fc6  mov     edx, 52CDh; char *
0x180076fcb  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180076fd0  lea     rcx, [rbp+arg_18]
0x180076fd4  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipDataEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(void)
0x180076fd9  xor     r14d, r14d
0x180076fdc  test    edi, edi
0x180076fde  jz      loc_180076D6A
0x180076fe4  mov     rcx, [rsi+r14*8]
0x180076fe8  test    rcx, rcx
0x180076feb  jz      short loc_180076FF9
0x180076fed  mov     rax, [rcx]
0x180076ff0  mov     rax, [rax+10h]
0x180076ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ff9  inc     r14d
0x180076ffc  cmp     r14d, edi
0x180076fff  jb      short loc_180076FE4
0x180077001  jmp     loc_180076D6A
0x180077006  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007700c  jnz     short loc_180077014
0x18007700e  call    cs:__imp_DebugBreak
0x180077014  mov     r9d, ebx; int
0x180077017  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007701e  mov     r8d, 52CCh; char *
0x180077024  lea     rcx, aStatusPropagat; "Status propagated"
0x18007702b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077030  mov     ecx, ebx; this
0x180077032  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180077037  lea     rcx, [rbp+arg_18]
0x18007703b  mov     ebx, eax
0x18007703d  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipDataEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(void)
0x180077042  xor     r14d, r14d
0x180077045  test    edi, edi
0x180077047  jz      loc_180076D6A
0x18007704d  mov     rcx, [rsi+r14*8]
0x180077051  test    rcx, rcx
0x180077054  jz      short loc_180077062
0x180077056  mov     rax, [rcx]
0x180077059  mov     rax, [rax+10h]
0x18007705d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077062  inc     r14d
0x180077065  cmp     r14d, edi
0x180077068  jb      short loc_18007704D
0x18007706a  jmp     loc_180076D6A
0x18007706f  mov     r8d, eax; int
0x180077072  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077079  mov     edx, 52CBh; char *
0x18007707e  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180077083  lea     rcx, [rbp+arg_18]
0x180077087  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipDataEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(void)
0x18007708c  xor     r14d, r14d
0x18007708f  test    edi, edi
0x180077091  jz      loc_180076D6A
0x180077097  mov     rcx, [rsi+r14*8]
0x18007709b  test    rcx, rcx
0x18007709e  jz      short loc_1800770AC
0x1800770a0  mov     rax, [rcx]
0x1800770a3  mov     rax, [rax+10h]
0x1800770a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770ac  inc     r14d
0x1800770af  cmp     r14d, edi
0x1800770b2  jb      short loc_180077097
0x1800770b4  jmp     loc_180076D6A
0x1800770b9  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800770bf  jnz     short loc_1800770C7
0x1800770c1  call    cs:__imp_DebugBreak
0x1800770c7  mov     r9d, ebx; int
0x1800770ca  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800770d1  mov     r8d, 52C9h; char *
0x1800770d7  lea     rcx, aStatusPropagat; "Status propagated"
0x1800770de  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800770e3  mov     ecx, ebx; this
0x1800770e5  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800770ea  lea     rcx, [rbp+arg_18]
0x1800770ee  mov     ebx, eax
0x1800770f0  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipDataEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipDataEntry>>>(void)
0x1800770f5  xor     r14d, r14d
0x1800770f8  test    edi, edi
0x1800770fa  jz      loc_180076D6A
0x180077100  mov     rcx, [rsi+r14*8]
0x180077104  test    rcx, rcx
0x180077107  jz      short loc_180077115
0x180077109  mov     rax, [rcx]
0x18007710c  mov     rax, [rax+10h]
0x180077110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077115  inc     r14d
0x180077118  cmp     r14d, edi
0x18007711b  jb      short loc_180077100
0x18007711d  jmp     loc_180076D6A
0x180077122  mov     [r15], r14d
0x180077125  lea     rcx, [rbp+var_30]
0x180077129  cmp     r14, rdi
0x18007712c  jz      short loc_180077138
0x18007712e  mov     ebx, 1
0x180077133  jmp     loc_180076D6E
0x180077138  xor     ebx, ebx
0x18007713a  jmp     loc_180076D6E
  ... truncated ...
```
