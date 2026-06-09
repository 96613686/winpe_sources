# CEnumHashElementSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18007bbb0`
- end: `0x18007c089`
- name: `?Next@CEnumHashElementSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1241`
- prototype: `__int64 __fastcall(CEnumHashElementSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x1800583e8`
- `0x18005b890`
- `0x18005e01c`
- `0x18006a234`
- `0x18007bbb0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bca6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bd2e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bea2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bf1e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bfd1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bca6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bd2e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bea2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bf1e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007bfd1`

## string_xrefs

- `0x18007bbe0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007bcaf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007bd37`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007bdf9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007beae`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007becf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007bf27`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007bf82`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007bfda`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumHashElementSection::Next(
        CEnumHashElementSection *this,
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
    v46 = 20618;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v45,
      &v45);
    return (unsigned int)v47;
  }
  if ( !a3 )
  {
    v46 = 20619;
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
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::Allocate(
                               &v50,
                               &v49);
            if ( v24 < 0 )
              break;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            HIDWORD(v44) = v15;
            v25 = CHashElementEntry::Initialize(
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
                (const char *)0x509B,
                v25,
                v26);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(&v50);
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
                (const char *)0x509C,
                v28,
                (unsigned int)v42);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v28,
                    v33);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(&v50);
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
                (const char *)0x509D,
                v29,
                v30);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(&v50);
              for ( k = 0; (unsigned int)k < (unsigned int)v4; k = (unsigned int)(k + 1) )
              {
                v32 = a3[k];
                if ( v32 )
                  ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
              }
              goto LABEL_10;
            }
            v50 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(&v50);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x5099,
            v24,
            (unsigned int)v42);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v38);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(&v50);
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
              (const char *)0x50A5,
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
          (const char *)0x5091,
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
        (const char *)0x5090,
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
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x508C, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
  return n;
}

```

## disassembly

```asm
0x18007bbb0  mov     [rsp-38h+arg_10], rbx
0x18007bbb5  mov     [rsp-38h+arg_0], rcx
0x18007bbba  push    rbp
0x18007bbbb  push    rsi
0x18007bbbc  push    rdi
0x18007bbbd  push    r12
0x18007bbbf  push    r13
0x18007bbc1  push    r14
0x18007bbc3  push    r15
0x18007bbc5  mov     rbp, rsp
0x18007bbc8  sub     rsp, 60h
0x18007bbcc  xor     r13d, r13d
0x18007bbcf  mov     edi, edx
0x18007bbd1  mov     rsi, r8
0x18007bbd4  mov     edx, edx
0x18007bbd6  mov     r12, rcx
0x18007bbd9  mov     dword ptr [rbp+var_8], 8007054Fh
0x18007bbe0  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007bbe7  mov     [rbp+arg_18], r13
0x18007bbeb  xorps   xmm0, xmm0
0x18007bbee  mov     [rbp+var_18], r11
0x18007bbf2  mov     rcx, rsi
0x18007bbf5  mov     [rbp+var_20], r13
0x18007bbf9  lea     r8, [rbp+var_40]
0x18007bbfd  mov     [rbp+var_40], r13
0x18007bc01  mov     r15, r9
0x18007bc04  movdqu  [rbp+var_30], xmm0
0x18007bc09  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007bc0e  test    r15, r15
0x18007bc11  jz      short loc_18007BC16
0x18007bc13  mov     [r15], r13d
0x18007bc16  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007bc1d  test    rdx, rdx
0x18007bc20  jz      loc_18007C04F
0x18007bc26  mov     rcx, [r12+18h]
0x18007bc2b  call    RtlIsTypeSafeHandleValid
0x18007bc30  test    al, al
0x18007bc32  jz      loc_18007C04F
0x18007bc38  test    rsi, rsi
0x18007bc3b  jnz     short loc_18007BC5B
0x18007bc3d  lea     rcx, [rbp+var_18]
0x18007bc41  mov     [rbp+var_10], 508Bh
0x18007bc48  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007bc4d  lea     rcx, [rbp+var_30]
0x18007bc51  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007bc56  jmp     loc_18007C06C
0x18007bc5b  test    r15, r15
0x18007bc5e  jnz     short loc_18007BC88
0x18007bc60  cmp     edi, 1
0x18007bc63  jz      short loc_18007BC88
0x18007bc65  mov     ebx, 80004003h
0x18007bc6a  mov     edx, 508Ch; char *
0x18007bc6f  mov     r8d, ebx; int
0x18007bc72  mov     rcx, r11; this
0x18007bc75  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007bc7a  lea     rcx, [rbp+var_30]
0x18007bc7e  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x18007bc83  jmp     loc_18007C06F
0x18007bc88  mov     r8d, edi
0x18007bc8b  lea     rdx, [rbp+arg_8]
0x18007bc8f  lea     rcx, [rbp+var_30]
0x18007bc93  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x18007bc98  mov     ebx, [rax]
0x18007bc9a  test    ebx, ebx
0x18007bc9c  jns     short loc_18007BCFA
0x18007bc9e  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007bca4  jnz     short loc_18007BCAC
0x18007bca6  call    cs:__imp_DebugBreak
0x18007bcac  mov     r9d, ebx; int
0x18007bcaf  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007bcb6  mov     r8d, 5090h; char *
0x18007bcbc  lea     rcx, aStatusPropagat; "Status propagated"
0x18007bcc3  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007bcc8  mov     ecx, ebx; this
0x18007bcca  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007bccf  mov     ebx, eax
0x18007bcd1  mov     r14d, r13d
0x18007bcd4  test    edi, edi
0x18007bcd6  jz      short loc_18007BC7A
0x18007bcd8  mov     ecx, r14d
0x18007bcdb  mov     rcx, [rsi+rcx*8]
0x18007bcdf  test    rcx, rcx
0x18007bce2  jz      short loc_18007BCF0
0x18007bce4  mov     rdx, [rcx]
0x18007bce7  mov     rax, [rdx+10h]
0x18007bceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bcf0  inc     r14d
0x18007bcf3  cmp     r14d, edi
0x18007bcf6  jb      short loc_18007BCD8
0x18007bcf8  jmp     short loc_18007BC7A
0x18007bcfa  mov     r13d, dword ptr [rbp+var_20+4]
0x18007bcfe  lea     r9, [rbp+arg_18]
0x18007bd02  cmp     r13d, dword ptr [rbp+var_20]
0x18007bd06  mov     rdx, rdi
0x18007bd09  mov     r8, qword ptr [rbp+var_30+8]
0x18007bd0d  cmovb   r13d, dword ptr [rbp+var_20]
0x18007bd12  mov     rcx, [r12+18h]
0x18007bd17  mov     dword ptr [rbp+var_20+4], r13d
0x18007bd1b  call    ?Fetch@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE_ENUMERATOR@123@_KQEAU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@123@PEA_K@Z; Windows::Cdf::Rtl::Fetch(Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,unsigned __int64,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM * const,unsigned __int64 *)
0x18007bd20  mov     ebx, eax
0x18007bd22  test    eax, eax
0x18007bd24  jns     short loc_18007BD86
0x18007bd26  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18007bd2c  jnz     short loc_18007BD34
0x18007bd2e  call    cs:__imp_DebugBreak
0x18007bd34  mov     r9d, ebx; int
0x18007bd37  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007bd3e  mov     r8d, 5091h; char *
0x18007bd44  lea     rcx, aStatusPropagat; "Status propagated"
0x18007bd4b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007bd50  mov     ecx, ebx; this
0x18007bd52  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007bd57  xor     r14d, r14d
0x18007bd5a  mov     ebx, eax
0x18007bd5c  test    edi, edi
0x18007bd5e  jz      loc_18007BC7A
0x18007bd64  mov     rcx, [rsi+r14*8]
0x18007bd68  test    rcx, rcx
0x18007bd6b  jz      short loc_18007BD79
0x18007bd6d  mov     rax, [rcx]
0x18007bd70  mov     rax, [rax+10h]
0x18007bd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bd79  inc     r14d
0x18007bd7c  cmp     r14d, edi
0x18007bd7f  jb      short loc_18007BD64
0x18007bd81  jmp     loc_18007BC7A
0x18007bd86  mov     r14, [rbp+arg_18]
0x18007bd8a  xor     r12d, r12d
0x18007bd8d  test    r14, r14
0x18007bd90  jz      loc_18007BE7E
0x18007bd96  lea     rdx, [rbp+arg_8]
0x18007bd9a  mov     [rbp+arg_18], 0
0x18007bda2  lea     rcx, [rbp+arg_18]
0x18007bda6  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCHashElementEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::Allocate(void)
0x18007bdab  mov     ebx, [rax]
0x18007bdad  test    ebx, ebx
0x18007bdaf  js      loc_18007BFC9
0x18007bdb5  mov     eax, dword ptr [rbp+var_20]
0x18007bdb8  cmp     r13d, eax
0x18007bdbb  mov     rcx, [rbp+arg_18]
0x18007bdbf  cmovb   r13d, eax
0x18007bdc3  cmp     r13d, eax
0x18007bdc6  cmovb   r13d, eax
0x18007bdca  mov     rax, qword ptr [rbp+var_30+8]
0x18007bdce  mov     dword ptr [rbp+var_20+4], r13d
0x18007bdd2  mov     r9d, [rax+r12*8]
0x18007bdd6  mov     r8d, [rax+r12*8+4]
0x18007bddb  mov     rax, [rbp+arg_0]
0x18007bddf  mov     rdx, [rax+10h]
0x18007bde3  call    ?Initialize@CHashElementEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@K@Z; CHashElementEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ulong)
0x18007bde8  mov     ebx, eax
0x18007bdea  test    eax, eax
0x18007bdec  js      loc_18007BF7F
0x18007bdf2  mov     dword ptr [rbp+var_8], 0C00000E5h
0x18007bdf9  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007be00  mov     [rbp+var_18], rax
0x18007be04  cmp     r12d, edi
0x18007be07  jb      short loc_18007BE2E
0x18007be09  mov     [rbp+var_40], 0
0x18007be11  mov     [rbp+var_10], 28h ; '('
0x18007be18  lea     rdx, [rbp+var_18]
0x18007be1c  lea     rcx, [rbp+var_18]
0x18007be20  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18007be25  mov     rcx, [rbp+var_40]
0x18007be29  mov     ebx, dword ptr [rbp+var_8]
0x18007be2c  jmp     short loc_18007BE34
0x18007be2e  lea     rcx, [rsi+r12*8]
0x18007be32  xor     ebx, ebx
0x18007be34  test    ebx, ebx
0x18007be36  js      loc_18007BF16
0x18007be3c  mov     r9, [rbp+arg_18]
0x18007be40  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18007be47  mov     r8, rcx
0x18007be4a  mov     rcx, r9
0x18007be4d  mov     rax, [r9]
0x18007be50  mov     rax, [rax]
0x18007be53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007be58  mov     ebx, eax
0x18007be5a  test    eax, eax
0x18007be5c  js      short loc_18007BECC
0x18007be5e  lea     rcx, [rbp+arg_18]
0x18007be62  mov     [rbp+arg_18], 0
0x18007be6a  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCHashElementEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(void)
0x18007be6f  inc     r12d
0x18007be72  mov     eax, r12d
0x18007be75  cmp     rax, r14
0x18007be78  jb      loc_18007BD96
0x18007be7e  test    r15, r15
0x18007be81  jz      loc_18007C035
0x18007be87  mov     eax, 0FFFFFFFFh
0x18007be8c  cmp     r14, rax
0x18007be8f  jbe     loc_18007C032
0x18007be95  mov     ebx, 0D0000095h
0x18007be9a  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x18007bea0  jnz     short loc_18007BEA8
0x18007bea2  call    cs:__imp_DebugBreak
0x18007bea8  mov     r9d, 0D0000095h; int
0x18007beae  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007beb5  mov     r8d, 50A5h; char *
0x18007bebb  lea     rcx, aHrOriginated; "HR originated"
0x18007bec2  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007bec7  jmp     loc_18007BC7A
0x18007becc  mov     r8d, eax; int
0x18007becf  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007bed6  mov     edx, 509Dh; char *
0x18007bedb  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007bee0  lea     rcx, [rbp+arg_18]
0x18007bee4  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCHashElementEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(void)
0x18007bee9  xor     r14d, r14d
0x18007beec  test    edi, edi
0x18007beee  jz      loc_18007BC7A
0x18007bef4  mov     rcx, [rsi+r14*8]
0x18007bef8  test    rcx, rcx
0x18007befb  jz      short loc_18007BF09
0x18007befd  mov     rax, [rcx]
0x18007bf00  mov     rax, [rax+10h]
0x18007bf04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bf09  inc     r14d
0x18007bf0c  cmp     r14d, edi
0x18007bf0f  jb      short loc_18007BEF4
0x18007bf11  jmp     loc_18007BC7A
0x18007bf16  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007bf1c  jnz     short loc_18007BF24
0x18007bf1e  call    cs:__imp_DebugBreak
0x18007bf24  mov     r9d, ebx; int
0x18007bf27  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007bf2e  mov     r8d, 509Ch; char *
0x18007bf34  lea     rcx, aStatusPropagat; "Status propagated"
0x18007bf3b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007bf40  mov     ecx, ebx; this
0x18007bf42  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007bf47  lea     rcx, [rbp+arg_18]
0x18007bf4b  mov     ebx, eax
0x18007bf4d  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCHashElementEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(void)
0x18007bf52  xor     r14d, r14d
0x18007bf55  test    edi, edi
0x18007bf57  jz      loc_18007BC7A
0x18007bf5d  mov     rcx, [rsi+r14*8]
0x18007bf61  test    rcx, rcx
0x18007bf64  jz      short loc_18007BF72
0x18007bf66  mov     rax, [rcx]
0x18007bf69  mov     rax, [rax+10h]
0x18007bf6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bf72  inc     r14d
0x18007bf75  cmp     r14d, edi
0x18007bf78  jb      short loc_18007BF5D
0x18007bf7a  jmp     loc_18007BC7A
0x18007bf7f  mov     r8d, eax; int
0x18007bf82  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007bf89  mov     edx, 509Bh; char *
0x18007bf8e  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007bf93  lea     rcx, [rbp+arg_18]
0x18007bf97  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCHashElementEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(void)
0x18007bf9c  xor     r14d, r14d
0x18007bf9f  test    edi, edi
0x18007bfa1  jz      loc_18007BC7A
0x18007bfa7  mov     rcx, [rsi+r14*8]
0x18007bfab  test    rcx, rcx
0x18007bfae  jz      short loc_18007BFBC
0x18007bfb0  mov     rax, [rcx]
0x18007bfb3  mov     rax, [rax+10h]
0x18007bfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfbc  inc     r14d
0x18007bfbf  cmp     r14d, edi
0x18007bfc2  jb      short loc_18007BFA7
0x18007bfc4  jmp     loc_18007BC7A
0x18007bfc9  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007bfcf  jnz     short loc_18007BFD7
0x18007bfd1  call    cs:__imp_DebugBreak
0x18007bfd7  mov     r9d, ebx; int
0x18007bfda  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007bfe1  mov     r8d, 5099h; char *
0x18007bfe7  lea     rcx, aStatusPropagat; "Status propagated"
0x18007bfee  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007bff3  mov     ecx, ebx; this
0x18007bff5  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007bffa  lea     rcx, [rbp+arg_18]
0x18007bffe  mov     ebx, eax
0x18007c000  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCHashElementEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CHashElementEntry>>>(void)
0x18007c005  xor     r14d, r14d
0x18007c008  test    edi, edi
0x18007c00a  jz      loc_18007BC7A
0x18007c010  mov     rcx, [rsi+r14*8]
0x18007c014  test    rcx, rcx
0x18007c017  jz      short loc_18007C025
0x18007c019  mov     rax, [rcx]
0x18007c01c  mov     rax, [rax+10h]
0x18007c020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c025  inc     r14d
0x18007c028  cmp     r14d, edi
0x18007c02b  jb      short loc_18007C010
0x18007c02d  jmp     loc_18007BC7A
0x18007c032  mov     [r15], r14d
0x18007c035  lea     rcx, [rbp+var_30]
0x18007c039  cmp     r14, rdi
0x18007c03c  jz      short loc_18007C048
0x18007c03e  mov     ebx, 1
0x18007c043  jmp     loc_18007BC7E
0x18007c048  xor     ebx, ebx
0x18007c04a  jmp     loc_18007BC7E
  ... truncated ...
```
