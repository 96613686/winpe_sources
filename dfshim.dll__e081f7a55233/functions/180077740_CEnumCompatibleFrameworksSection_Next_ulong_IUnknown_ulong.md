# CEnumCompatibleFrameworksSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180077740`
- end: `0x180077c19`
- name: `?Next@CEnumCompatibleFrameworksSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1241`
- prototype: `__int64 __fastcall(CEnumCompatibleFrameworksSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180057dc8`
- `0x18005a8cc`
- `0x18005e01c`
- `0x180067464`
- `0x180077740`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077836`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800778be`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077a32`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077aae`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077b61`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077836`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800778be`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077a32`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077aae`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077b61`

## string_xrefs

- `0x180077770`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007783f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800778c7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077989`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077a3e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077a5f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077ab7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077b12`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077b6a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCompatibleFrameworksSection::Next(
        CEnumCompatibleFrameworksSection *this,
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
    v46 = 23533;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v45,
      &v45);
    return (unsigned int)v47;
  }
  if ( !a3 )
  {
    v46 = 23534;
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
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::Allocate(
                               &v50,
                               &v49);
            if ( v24 < 0 )
              break;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            if ( v15 < (unsigned int)v44 )
              v15 = v44;
            HIDWORD(v44) = v15;
            v25 = CCompatibleFrameworkEntry::Initialize(
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
                (const char *)0x5BFE,
                v25,
                v26);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(&v50);
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
                (const char *)0x5BFF,
                v28,
                (unsigned int)v42);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v28,
                    v33);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(&v50);
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
                (const char *)0x5C00,
                v29,
                v30);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(&v50);
              for ( k = 0; (unsigned int)k < (unsigned int)v4; k = (unsigned int)(k + 1) )
              {
                v32 = a3[k];
                if ( v32 )
                  ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
              }
              goto LABEL_10;
            }
            v50 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(&v50);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x5BFC,
            v24,
            (unsigned int)v42);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v38);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(&v50);
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
              (const char *)0x5C08,
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
          (const char *)0x5BF4,
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
        (const char *)0x5BF3,
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
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x5BEF, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v43);
  return n;
}

```

## disassembly

```asm
0x180077740  mov     [rsp-38h+arg_10], rbx
0x180077745  mov     [rsp-38h+arg_0], rcx
0x18007774a  push    rbp
0x18007774b  push    rsi
0x18007774c  push    rdi
0x18007774d  push    r12
0x18007774f  push    r13
0x180077751  push    r14
0x180077753  push    r15
0x180077755  mov     rbp, rsp
0x180077758  sub     rsp, 60h
0x18007775c  xor     r13d, r13d
0x18007775f  mov     edi, edx
0x180077761  mov     rsi, r8
0x180077764  mov     edx, edx
0x180077766  mov     r12, rcx
0x180077769  mov     dword ptr [rbp+var_8], 8007054Fh
0x180077770  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077777  mov     [rbp+arg_18], r13
0x18007777b  xorps   xmm0, xmm0
0x18007777e  mov     [rbp+var_18], r11
0x180077782  mov     rcx, rsi
0x180077785  mov     [rbp+var_20], r13
0x180077789  lea     r8, [rbp+var_40]
0x18007778d  mov     [rbp+var_40], r13
0x180077791  mov     r15, r9
0x180077794  movdqu  [rbp+var_30], xmm0
0x180077799  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007779e  test    r15, r15
0x1800777a1  jz      short loc_1800777A6
0x1800777a3  mov     [r15], r13d
0x1800777a6  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800777ad  test    rdx, rdx
0x1800777b0  jz      loc_180077BDF
0x1800777b6  mov     rcx, [r12+18h]
0x1800777bb  call    RtlIsTypeSafeHandleValid
0x1800777c0  test    al, al
0x1800777c2  jz      loc_180077BDF
0x1800777c8  test    rsi, rsi
0x1800777cb  jnz     short loc_1800777EB
0x1800777cd  lea     rcx, [rbp+var_18]
0x1800777d1  mov     [rbp+var_10], 5BEEh
0x1800777d8  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800777dd  lea     rcx, [rbp+var_30]
0x1800777e1  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x1800777e6  jmp     loc_180077BFC
0x1800777eb  test    r15, r15
0x1800777ee  jnz     short loc_180077818
0x1800777f0  cmp     edi, 1
0x1800777f3  jz      short loc_180077818
0x1800777f5  mov     ebx, 80004003h
0x1800777fa  mov     edx, 5BEFh; char *
0x1800777ff  mov     r8d, ebx; int
0x180077802  mov     rcx, r11; this
0x180077805  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x18007780a  lea     rcx, [rbp+var_30]
0x18007780e  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180077813  jmp     loc_180077BFF
0x180077818  mov     r8d, edi
0x18007781b  lea     rdx, [rbp+arg_8]
0x18007781f  lea     rcx, [rbp+var_30]
0x180077823  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_ULONG_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180077828  mov     ebx, [rax]
0x18007782a  test    ebx, ebx
0x18007782c  jns     short loc_18007788A
0x18007782e  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180077834  jnz     short loc_18007783C
0x180077836  call    cs:__imp_DebugBreak
0x18007783c  mov     r9d, ebx; int
0x18007783f  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077846  mov     r8d, 5BF3h; char *
0x18007784c  lea     rcx, aStatusPropagat; "Status propagated"
0x180077853  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077858  mov     ecx, ebx; this
0x18007785a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007785f  mov     ebx, eax
0x180077861  mov     r14d, r13d
0x180077864  test    edi, edi
0x180077866  jz      short loc_18007780A
0x180077868  mov     ecx, r14d
0x18007786b  mov     rcx, [rsi+rcx*8]
0x18007786f  test    rcx, rcx
0x180077872  jz      short loc_180077880
0x180077874  mov     rdx, [rcx]
0x180077877  mov     rax, [rdx+10h]
0x18007787b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077880  inc     r14d
0x180077883  cmp     r14d, edi
0x180077886  jb      short loc_180077868
0x180077888  jmp     short loc_18007780A
0x18007788a  mov     r13d, dword ptr [rbp+var_20+4]
0x18007788e  lea     r9, [rbp+arg_18]
0x180077892  cmp     r13d, dword ptr [rbp+var_20]
0x180077896  mov     rdx, rdi
0x180077899  mov     r8, qword ptr [rbp+var_30+8]
0x18007789d  cmovb   r13d, dword ptr [rbp+var_20]
0x1800778a2  mov     rcx, [r12+18h]
0x1800778a7  mov     dword ptr [rbp+var_20+4], r13d
0x1800778ab  call    ?Fetch@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE_ENUMERATOR@123@_KQEAU_CDF_ULONG_TABLE_ENUMERATOR_ITEM@123@PEA_K@Z; Windows::Cdf::Rtl::Fetch(Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,unsigned __int64,Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR_ITEM * const,unsigned __int64 *)
0x1800778b0  mov     ebx, eax
0x1800778b2  test    eax, eax
0x1800778b4  jns     short loc_180077916
0x1800778b6  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800778bc  jnz     short loc_1800778C4
0x1800778be  call    cs:__imp_DebugBreak
0x1800778c4  mov     r9d, ebx; int
0x1800778c7  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800778ce  mov     r8d, 5BF4h; char *
0x1800778d4  lea     rcx, aStatusPropagat; "Status propagated"
0x1800778db  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800778e0  mov     ecx, ebx; this
0x1800778e2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800778e7  xor     r14d, r14d
0x1800778ea  mov     ebx, eax
0x1800778ec  test    edi, edi
0x1800778ee  jz      loc_18007780A
0x1800778f4  mov     rcx, [rsi+r14*8]
0x1800778f8  test    rcx, rcx
0x1800778fb  jz      short loc_180077909
0x1800778fd  mov     rax, [rcx]
0x180077900  mov     rax, [rax+10h]
0x180077904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077909  inc     r14d
0x18007790c  cmp     r14d, edi
0x18007790f  jb      short loc_1800778F4
0x180077911  jmp     loc_18007780A
0x180077916  mov     r14, [rbp+arg_18]
0x18007791a  xor     r12d, r12d
0x18007791d  test    r14, r14
0x180077920  jz      loc_180077A0E
0x180077926  lea     rdx, [rbp+arg_8]
0x18007792a  mov     [rbp+arg_18], 0
0x180077932  lea     rcx, [rbp+arg_18]
0x180077936  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCompatibleFrameworkEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::Allocate(void)
0x18007793b  mov     ebx, [rax]
0x18007793d  test    ebx, ebx
0x18007793f  js      loc_180077B59
0x180077945  mov     eax, dword ptr [rbp+var_20]
0x180077948  cmp     r13d, eax
0x18007794b  mov     rcx, [rbp+arg_18]
0x18007794f  cmovb   r13d, eax
0x180077953  cmp     r13d, eax
0x180077956  cmovb   r13d, eax
0x18007795a  mov     rax, qword ptr [rbp+var_30+8]
0x18007795e  mov     dword ptr [rbp+var_20+4], r13d
0x180077962  mov     r9d, [rax+r12*8]
0x180077966  mov     r8d, [rax+r12*8+4]
0x18007796b  mov     rax, [rbp+arg_0]
0x18007796f  mov     rdx, [rax+10h]
0x180077973  call    ?Initialize@CCompatibleFrameworkEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@K@Z; CCompatibleFrameworkEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,ulong)
0x180077978  mov     ebx, eax
0x18007797a  test    eax, eax
0x18007797c  js      loc_180077B0F
0x180077982  mov     dword ptr [rbp+var_8], 0C00000E5h
0x180077989  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077990  mov     [rbp+var_18], rax
0x180077994  cmp     r12d, edi
0x180077997  jb      short loc_1800779BE
0x180077999  mov     [rbp+var_40], 0
0x1800779a1  mov     [rbp+var_10], 28h ; '('
0x1800779a8  lea     rdx, [rbp+var_18]
0x1800779ac  lea     rcx, [rbp+var_18]
0x1800779b0  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800779b5  mov     rcx, [rbp+var_40]
0x1800779b9  mov     ebx, dword ptr [rbp+var_8]
0x1800779bc  jmp     short loc_1800779C4
0x1800779be  lea     rcx, [rsi+r12*8]
0x1800779c2  xor     ebx, ebx
0x1800779c4  test    ebx, ebx
0x1800779c6  js      loc_180077AA6
0x1800779cc  mov     r9, [rbp+arg_18]
0x1800779d0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800779d7  mov     r8, rcx
0x1800779da  mov     rcx, r9
0x1800779dd  mov     rax, [r9]
0x1800779e0  mov     rax, [rax]
0x1800779e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779e8  mov     ebx, eax
0x1800779ea  test    eax, eax
0x1800779ec  js      short loc_180077A5C
0x1800779ee  lea     rcx, [rbp+arg_18]
0x1800779f2  mov     [rbp+arg_18], 0
0x1800779fa  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCompatibleFrameworkEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(void)
0x1800779ff  inc     r12d
0x180077a02  mov     eax, r12d
0x180077a05  cmp     rax, r14
0x180077a08  jb      loc_180077926
0x180077a0e  test    r15, r15
0x180077a11  jz      loc_180077BC5
0x180077a17  mov     eax, 0FFFFFFFFh
0x180077a1c  cmp     r14, rax
0x180077a1f  jbe     loc_180077BC2
0x180077a25  mov     ebx, 0D0000095h
0x180077a2a  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x180077a30  jnz     short loc_180077A38
0x180077a32  call    cs:__imp_DebugBreak
0x180077a38  mov     r9d, 0D0000095h; int
0x180077a3e  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077a45  mov     r8d, 5C08h; char *
0x180077a4b  lea     rcx, aHrOriginated; "HR originated"
0x180077a52  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077a57  jmp     loc_18007780A
0x180077a5c  mov     r8d, eax; int
0x180077a5f  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077a66  mov     edx, 5C00h; char *
0x180077a6b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180077a70  lea     rcx, [rbp+arg_18]
0x180077a74  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCompatibleFrameworkEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(void)
0x180077a79  xor     r14d, r14d
0x180077a7c  test    edi, edi
0x180077a7e  jz      loc_18007780A
0x180077a84  mov     rcx, [rsi+r14*8]
0x180077a88  test    rcx, rcx
0x180077a8b  jz      short loc_180077A99
0x180077a8d  mov     rax, [rcx]
0x180077a90  mov     rax, [rax+10h]
0x180077a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a99  inc     r14d
0x180077a9c  cmp     r14d, edi
0x180077a9f  jb      short loc_180077A84
0x180077aa1  jmp     loc_18007780A
0x180077aa6  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180077aac  jnz     short loc_180077AB4
0x180077aae  call    cs:__imp_DebugBreak
0x180077ab4  mov     r9d, ebx; int
0x180077ab7  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077abe  mov     r8d, 5BFFh; char *
0x180077ac4  lea     rcx, aStatusPropagat; "Status propagated"
0x180077acb  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077ad0  mov     ecx, ebx; this
0x180077ad2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180077ad7  lea     rcx, [rbp+arg_18]
0x180077adb  mov     ebx, eax
0x180077add  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCompatibleFrameworkEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(void)
0x180077ae2  xor     r14d, r14d
0x180077ae5  test    edi, edi
0x180077ae7  jz      loc_18007780A
0x180077aed  mov     rcx, [rsi+r14*8]
0x180077af1  test    rcx, rcx
0x180077af4  jz      short loc_180077B02
0x180077af6  mov     rax, [rcx]
0x180077af9  mov     rax, [rax+10h]
0x180077afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b02  inc     r14d
0x180077b05  cmp     r14d, edi
0x180077b08  jb      short loc_180077AED
0x180077b0a  jmp     loc_18007780A
0x180077b0f  mov     r8d, eax; int
0x180077b12  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077b19  mov     edx, 5BFEh; char *
0x180077b1e  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180077b23  lea     rcx, [rbp+arg_18]
0x180077b27  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCompatibleFrameworkEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(void)
0x180077b2c  xor     r14d, r14d
0x180077b2f  test    edi, edi
0x180077b31  jz      loc_18007780A
0x180077b37  mov     rcx, [rsi+r14*8]
0x180077b3b  test    rcx, rcx
0x180077b3e  jz      short loc_180077B4C
0x180077b40  mov     rax, [rcx]
0x180077b43  mov     rax, [rax+10h]
0x180077b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b4c  inc     r14d
0x180077b4f  cmp     r14d, edi
0x180077b52  jb      short loc_180077B37
0x180077b54  jmp     loc_18007780A
0x180077b59  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180077b5f  jnz     short loc_180077B67
0x180077b61  call    cs:__imp_DebugBreak
0x180077b67  mov     r9d, ebx; int
0x180077b6a  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077b71  mov     r8d, 5BFCh; char *
0x180077b77  lea     rcx, aStatusPropagat; "Status propagated"
0x180077b7e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077b83  mov     ecx, ebx; this
0x180077b85  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180077b8a  lea     rcx, [rbp+arg_18]
0x180077b8e  mov     ebx, eax
0x180077b90  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCompatibleFrameworkEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCompatibleFrameworkEntry>>>(void)
0x180077b95  xor     r14d, r14d
0x180077b98  test    edi, edi
0x180077b9a  jz      loc_18007780A
0x180077ba0  mov     rcx, [rsi+r14*8]
0x180077ba4  test    rcx, rcx
0x180077ba7  jz      short loc_180077BB5
0x180077ba9  mov     rax, [rcx]
0x180077bac  mov     rax, [rax+10h]
0x180077bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077bb5  inc     r14d
0x180077bb8  cmp     r14d, edi
0x180077bbb  jb      short loc_180077BA0
0x180077bbd  jmp     loc_18007780A
0x180077bc2  mov     [r15], r14d
0x180077bc5  lea     rcx, [rbp+var_30]
0x180077bc9  cmp     r14, rdi
0x180077bcc  jz      short loc_180077BD8
0x180077bce  mov     ebx, 1
0x180077bd3  jmp     loc_18007780E
0x180077bd8  xor     ebx, ebx
0x180077bda  jmp     loc_18007780E
  ... truncated ...
```
