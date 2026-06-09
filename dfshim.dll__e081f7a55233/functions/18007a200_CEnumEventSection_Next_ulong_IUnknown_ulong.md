# CEnumEventSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007a200`
- end: `0x18007a6d9`
- name: `?Next@CEnumEventSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1241`
- prototype: `__int64 __fastcall(CEnumEventSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x1800581b8`
- `0x18005b23c`
- `0x18005e01c`
- `0x180069960`
- `0x18007a200`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a2f6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a37e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a4f2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a56e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a621`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a2f6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a37e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a4f2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a56e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007a621`

## string_xrefs

- `0x18007a230`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a2ff`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a387`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a449`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a4fe`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a51f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a577`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a5d2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007a62a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumEventSection::Next(
        CEnumEventSection *this,
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
    v46 = 22637;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v45,
      &v45);
    return (unsigned int)v47;
  }
  if ( !a3 )
  {
    v46 = 22638;
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
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::Allocate(
                               &v50,
                               &v49);
            if ( v24 < 0 )
              break;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            HIDWORD(v44) = v15;
            v25 = CEventEntry::Initialize(
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
                (const char *)0x587E,
                v25,
                v26);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(&v50);
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
                (const char *)0x587F,
                v28,
                (unsigned int)v42);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v28,
                    v33);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(&v50);
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
                (const char *)0x5880,
                v29,
                v30);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(&v50);
              for ( k = 0; (unsigned int)k < (unsigned int)v4; k = (unsigned int)(k + 1) )
              {
                v32 = a3[k];
                if ( v32 )
                  ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
              }
              goto LABEL_10;
            }
            v50 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(&v50);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x587C,
            v24,
            (unsigned int)v42);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v38);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(&v50);
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
              (const char *)0x5888,
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
          (const char *)0x5874,
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
        (const char *)0x5873,
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
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x586F, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
  return n;
}

```

## disassembly

```asm
0x18007a200  mov     [rsp-38h+arg_10], rbx
0x18007a205  mov     [rsp-38h+arg_0], rcx
0x18007a20a  push    rbp
0x18007a20b  push    rsi
0x18007a20c  push    rdi
0x18007a20d  push    r12
0x18007a20f  push    r13
0x18007a211  push    r14
0x18007a213  push    r15
0x18007a215  mov     rbp, rsp
0x18007a218  sub     rsp, 60h
0x18007a21c  xor     r13d, r13d
0x18007a21f  mov     edi, edx
0x18007a221  mov     rsi, r8
0x18007a224  mov     edx, edx
0x18007a226  mov     r12, rcx
0x18007a229  mov     dword ptr [rbp+var_8], 8007054Fh
0x18007a230  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a237  mov     [rbp+arg_18], r13
0x18007a23b  xorps   xmm0, xmm0
0x18007a23e  mov     [rbp+var_18], r11
0x18007a242  mov     rcx, rsi
0x18007a245  mov     [rbp+var_20], r13
0x18007a249  lea     r8, [rbp+var_40]
0x18007a24d  mov     [rbp+var_40], r13
0x18007a251  mov     r15, r9
0x18007a254  movdqu  [rbp+var_30], xmm0
0x18007a259  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007a25e  test    r15, r15
0x18007a261  jz      short loc_18007A266
0x18007a263  mov     [r15], r13d
0x18007a266  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007a26d  test    rdx, rdx
0x18007a270  jz      loc_18007A69F
0x18007a276  mov     rcx, [r12+18h]
0x18007a27b  call    RtlIsTypeSafeHandleValid
0x18007a280  test    al, al
0x18007a282  jz      loc_18007A69F
0x18007a288  test    rsi, rsi
0x18007a28b  jnz     short loc_18007A2AB
0x18007a28d  lea     rcx, [rbp+var_18]
0x18007a291  mov     [rbp+var_10], 586Eh
0x18007a298  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007a29d  lea     rcx, [rbp+var_30]
0x18007a2a1  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007a2a6  jmp     loc_18007A6BC
0x18007a2ab  test    r15, r15
0x18007a2ae  jnz     short loc_18007A2D8
0x18007a2b0  cmp     edi, 1
0x18007a2b3  jz      short loc_18007A2D8
0x18007a2b5  mov     ebx, 80004003h
0x18007a2ba  mov     edx, 586Fh; char *
0x18007a2bf  mov     r8d, ebx; int
0x18007a2c2  mov     rcx, r11; this
0x18007a2c5  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007a2ca  lea     rcx, [rbp+var_30]
0x18007a2ce  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007a2d3  jmp     loc_18007A6BF
0x18007a2d8  mov     r8d, edi
0x18007a2db  lea     rdx, [rbp+arg_8]
0x18007a2df  lea     rcx, [rbp+var_30]
0x18007a2e3  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007a2e8  mov     ebx, [rax]
0x18007a2ea  test    ebx, ebx
0x18007a2ec  jns     short loc_18007A34A
0x18007a2ee  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007a2f4  jnz     short loc_18007A2FC
0x18007a2f6  call    cs:__imp_DebugBreak
0x18007a2fc  mov     r9d, ebx; int
0x18007a2ff  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a306  mov     r8d, 5873h; char *
0x18007a30c  lea     rcx, aStatusPropagat; "Status propagated"
0x18007a313  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007a318  mov     ecx, ebx; this
0x18007a31a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007a31f  mov     ebx, eax
0x18007a321  mov     r14d, r13d
0x18007a324  test    edi, edi
0x18007a326  jz      short loc_18007A2CA
0x18007a328  mov     ecx, r14d
0x18007a32b  mov     rcx, [rsi+rcx*8]
0x18007a32f  test    rcx, rcx
0x18007a332  jz      short loc_18007A340
0x18007a334  mov     rdx, [rcx]
0x18007a337  mov     rax, [rdx+10h]
0x18007a33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a340  inc     r14d
0x18007a343  cmp     r14d, edi
0x18007a346  jb      short loc_18007A328
0x18007a348  jmp     short loc_18007A2CA
0x18007a34a  mov     r13d, dword ptr [rbp+var_20+4]
0x18007a34e  lea     r9, [rbp+arg_18]
0x18007a352  cmp     r13d, dword ptr [rbp+var_20]
0x18007a356  mov     rdx, rdi
0x18007a359  mov     r8, qword ptr [rbp+var_30+8]
0x18007a35d  cmovb   r13d, dword ptr [rbp+var_20]
0x18007a362  mov     rcx, [r12+18h]
0x18007a367  mov     dword ptr [rbp+var_20+4], r13d
0x18007a36b  call    ?Fetch@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE_ENUMERATOR@123@_KQEAU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@123@PEA_K@Z; Windows::Cdf::Rtl::Fetch(Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,unsigned __int64,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM * const,unsigned __int64 *)
0x18007a370  mov     ebx, eax
0x18007a372  test    eax, eax
0x18007a374  jns     short loc_18007A3D6
0x18007a376  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18007a37c  jnz     short loc_18007A384
0x18007a37e  call    cs:__imp_DebugBreak
0x18007a384  mov     r9d, ebx; int
0x18007a387  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a38e  mov     r8d, 5874h; char *
0x18007a394  lea     rcx, aStatusPropagat; "Status propagated"
0x18007a39b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007a3a0  mov     ecx, ebx; this
0x18007a3a2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007a3a7  xor     r14d, r14d
0x18007a3aa  mov     ebx, eax
0x18007a3ac  test    edi, edi
0x18007a3ae  jz      loc_18007A2CA
0x18007a3b4  mov     rcx, [rsi+r14*8]
0x18007a3b8  test    rcx, rcx
0x18007a3bb  jz      short loc_18007A3C9
0x18007a3bd  mov     rax, [rcx]
0x18007a3c0  mov     rax, [rax+10h]
0x18007a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3c9  inc     r14d
0x18007a3cc  cmp     r14d, edi
0x18007a3cf  jb      short loc_18007A3B4
0x18007a3d1  jmp     loc_18007A2CA
0x18007a3d6  mov     r14, [rbp+arg_18]
0x18007a3da  xor     r12d, r12d
0x18007a3dd  test    r14, r14
0x18007a3e0  jz      loc_18007A4CE
0x18007a3e6  lea     rdx, [rbp+arg_8]
0x18007a3ea  mov     [rbp+arg_18], 0
0x18007a3f2  lea     rcx, [rbp+arg_18]
0x18007a3f6  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::Allocate(void)
0x18007a3fb  mov     ebx, [rax]
0x18007a3fd  test    ebx, ebx
0x18007a3ff  js      loc_18007A619
0x18007a405  mov     eax, dword ptr [rbp+var_20]
0x18007a408  cmp     r13d, eax
0x18007a40b  mov     rcx, [rbp+arg_18]
0x18007a40f  cmovb   r13d, eax
0x18007a413  cmp     r13d, eax
0x18007a416  cmovb   r13d, eax
0x18007a41a  mov     rax, qword ptr [rbp+var_30+8]
0x18007a41e  mov     dword ptr [rbp+var_20+4], r13d
0x18007a422  mov     r9d, [rax+r12*8]
0x18007a426  mov     r8d, [rax+r12*8+4]
0x18007a42b  mov     rax, [rbp+arg_0]
0x18007a42f  mov     rdx, [rax+10h]
0x18007a433  call    ?Initialize@CEventEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@K@Z; CEventEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ulong)
0x18007a438  mov     ebx, eax
0x18007a43a  test    eax, eax
0x18007a43c  js      loc_18007A5CF
0x18007a442  mov     dword ptr [rbp+var_8], 0C00000E5h
0x18007a449  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a450  mov     [rbp+var_18], rax
0x18007a454  cmp     r12d, edi
0x18007a457  jb      short loc_18007A47E
0x18007a459  mov     [rbp+var_40], 0
0x18007a461  mov     [rbp+var_10], 28h ; '('
0x18007a468  lea     rdx, [rbp+var_18]
0x18007a46c  lea     rcx, [rbp+var_18]
0x18007a470  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007a475  mov     rcx, [rbp+var_40]
0x18007a479  mov     ebx, dword ptr [rbp+var_8]
0x18007a47c  jmp     short loc_18007A484
0x18007a47e  lea     rcx, [rsi+r12*8]
0x18007a482  xor     ebx, ebx
0x18007a484  test    ebx, ebx
0x18007a486  js      loc_18007A566
0x18007a48c  mov     r9, [rbp+arg_18]
0x18007a490  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007a497  mov     r8, rcx
0x18007a49a  mov     rcx, r9
0x18007a49d  mov     rax, [r9]
0x18007a4a0  mov     rax, [rax]
0x18007a4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4a8  mov     ebx, eax
0x18007a4aa  test    eax, eax
0x18007a4ac  js      short loc_18007A51C
0x18007a4ae  lea     rcx, [rbp+arg_18]
0x18007a4b2  mov     [rbp+arg_18], 0
0x18007a4ba  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(void)
0x18007a4bf  inc     r12d
0x18007a4c2  mov     eax, r12d
0x18007a4c5  cmp     rax, r14
0x18007a4c8  jb      loc_18007A3E6
0x18007a4ce  test    r15, r15
0x18007a4d1  jz      loc_18007A685
0x18007a4d7  mov     eax, 0FFFFFFFFh
0x18007a4dc  cmp     r14, rax
0x18007a4df  jbe     loc_18007A682
0x18007a4e5  mov     ebx, 0D0000095h
0x18007a4ea  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x18007a4f0  jnz     short loc_18007A4F8
0x18007a4f2  call    cs:__imp_DebugBreak
0x18007a4f8  mov     r9d, 0D0000095h; int
0x18007a4fe  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a505  mov     r8d, 5888h; char *
0x18007a50b  lea     rcx, aHrOriginated; "HR originated"
0x18007a512  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007a517  jmp     loc_18007A2CA
0x18007a51c  mov     r8d, eax; int
0x18007a51f  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a526  mov     edx, 5880h; char *
0x18007a52b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007a530  lea     rcx, [rbp+arg_18]
0x18007a534  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(void)
0x18007a539  xor     r14d, r14d
0x18007a53c  test    edi, edi
0x18007a53e  jz      loc_18007A2CA
0x18007a544  mov     rcx, [rsi+r14*8]
0x18007a548  test    rcx, rcx
0x18007a54b  jz      short loc_18007A559
0x18007a54d  mov     rax, [rcx]
0x18007a550  mov     rax, [rax+10h]
0x18007a554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a559  inc     r14d
0x18007a55c  cmp     r14d, edi
0x18007a55f  jb      short loc_18007A544
0x18007a561  jmp     loc_18007A2CA
0x18007a566  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007a56c  jnz     short loc_18007A574
0x18007a56e  call    cs:__imp_DebugBreak
0x18007a574  mov     r9d, ebx; int
0x18007a577  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a57e  mov     r8d, 587Fh; char *
0x18007a584  lea     rcx, aStatusPropagat; "Status propagated"
0x18007a58b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007a590  mov     ecx, ebx; this
0x18007a592  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007a597  lea     rcx, [rbp+arg_18]
0x18007a59b  mov     ebx, eax
0x18007a59d  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(void)
0x18007a5a2  xor     r14d, r14d
0x18007a5a5  test    edi, edi
0x18007a5a7  jz      loc_18007A2CA
0x18007a5ad  mov     rcx, [rsi+r14*8]
0x18007a5b1  test    rcx, rcx
0x18007a5b4  jz      short loc_18007A5C2
0x18007a5b6  mov     rax, [rcx]
0x18007a5b9  mov     rax, [rax+10h]
0x18007a5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5c2  inc     r14d
0x18007a5c5  cmp     r14d, edi
0x18007a5c8  jb      short loc_18007A5AD
0x18007a5ca  jmp     loc_18007A2CA
0x18007a5cf  mov     r8d, eax; int
0x18007a5d2  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a5d9  mov     edx, 587Eh; char *
0x18007a5de  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007a5e3  lea     rcx, [rbp+arg_18]
0x18007a5e7  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(void)
0x18007a5ec  xor     r14d, r14d
0x18007a5ef  test    edi, edi
0x18007a5f1  jz      loc_18007A2CA
0x18007a5f7  mov     rcx, [rsi+r14*8]
0x18007a5fb  test    rcx, rcx
0x18007a5fe  jz      short loc_18007A60C
0x18007a600  mov     rax, [rcx]
0x18007a603  mov     rax, [rax+10h]
0x18007a607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a60c  inc     r14d
0x18007a60f  cmp     r14d, edi
0x18007a612  jb      short loc_18007A5F7
0x18007a614  jmp     loc_18007A2CA
0x18007a619  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007a61f  jnz     short loc_18007A627
0x18007a621  call    cs:__imp_DebugBreak
0x18007a627  mov     r9d, ebx; int
0x18007a62a  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007a631  mov     r8d, 587Ch; char *
0x18007a637  lea     rcx, aStatusPropagat; "Status propagated"
0x18007a63e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007a643  mov     ecx, ebx; this
0x18007a645  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007a64a  lea     rcx, [rbp+arg_18]
0x18007a64e  mov     ebx, eax
0x18007a650  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCEventEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CEventEntry>>>(void)
0x18007a655  xor     r14d, r14d
0x18007a658  test    edi, edi
0x18007a65a  jz      loc_18007A2CA
0x18007a660  mov     rcx, [rsi+r14*8]
0x18007a664  test    rcx, rcx
0x18007a667  jz      short loc_18007A675
0x18007a669  mov     rax, [rcx]
0x18007a66c  mov     rax, [rax+10h]
0x18007a670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a675  inc     r14d
0x18007a678  cmp     r14d, edi
0x18007a67b  jb      short loc_18007A660
0x18007a67d  jmp     loc_18007A2CA
0x18007a682  mov     [r15], r14d
0x18007a685  lea     rcx, [rbp+var_30]
0x18007a689  cmp     r14, rdi
0x18007a68c  jz      short loc_18007A698
0x18007a68e  mov     ebx, 1
0x18007a693  jmp     loc_18007A2CE
0x18007a698  xor     ebx, ebx
0x18007a69a  jmp     loc_18007A2CE
  ... truncated ...
```
