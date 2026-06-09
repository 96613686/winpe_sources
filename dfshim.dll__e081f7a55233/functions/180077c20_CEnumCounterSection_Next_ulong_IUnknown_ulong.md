# CEnumCounterSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180077c20`
- end: `0x18007811e`
- name: `?Next@CEnumCounterSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1278`
- prototype: `__int64 __fastcall(CEnumCounterSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18004f2dc`
- `0x1800569a8`
- `0x1800576e0`
- `0x180057ea8`
- `0x18005aab0`
- `0x18005de44`
- `0x180067700`
- `0x180077c20`
- `0x1800d552c`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077d25`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077dad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077f2f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077fab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007805e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077d25`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077dad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077f2f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180077fab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007805e`

## string_xrefs

- `0x180077c58`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077d2e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077db6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077e86`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077f3b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077f5c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180077fb4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007800f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180078067`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCounterSection::Next(
        CEnumCounterSection *this,
        unsigned int a2,
        struct IUnknown **a3,
        unsigned int *a4)
{
  __int64 v5; // rdi
  int v8; // r9d
  Windows::ErrorHandling::COM *v9; // r11
  unsigned int n; // ebx
  int v11; // ebx
  int v12; // edx
  unsigned int ii; // r14d
  struct IUnknown *v14; // rcx
  unsigned int v15; // r13d
  __int64 v16; // rcx
  int GuidTableEnumeratorData; // eax
  unsigned int v18; // ebx
  int v19; // edx
  __int64 v20; // r14
  struct IUnknown *v21; // rcx
  unsigned __int64 v22; // r14
  __int64 v23; // r12
  int v24; // ebx
  __int64 v25; // r8
  int v26; // eax
  int v27; // r9d
  struct IUnknown **v28; // rcx
  int v29; // ebx
  int v30; // eax
  int v31; // r9d
  __int64 k; // r14
  struct IUnknown *v33; // rcx
  int v34; // edx
  __int64 j; // r14
  struct IUnknown *v36; // rcx
  __int64 i; // r14
  struct IUnknown *v38; // rcx
  int v39; // edx
  __int64 m; // r14
  struct IUnknown *v41; // rcx
  __int64 (__fastcall ***v43)(_QWORD, GUID *, struct IUnknown **); // [rsp+20h] [rbp-69h] BYREF
  __int128 v44; // [rsp+28h] [rbp-61h] BYREF
  __int64 v45; // [rsp+38h] [rbp-51h]
  __int128 v46; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-39h]
  __int64 v48; // [rsp+60h] [rbp-29h] BYREF
  CEnumCounterSection *v49; // [rsp+68h] [rbp-21h]
  const char *v50; // [rsp+78h] [rbp-11h] BYREF
  int v51; // [rsp+80h] [rbp-9h]
  Windows::ErrorHandling::COM *v52; // [rsp+88h] [rbp-1h]

  v49 = this;
  v5 = a2;
  v47 = -2147023537;
  *(_QWORD *)&v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v43 = 0;
  v45 = 0;
  v48 = 0;
  v44 = 0;
  IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(a3, a2, &v48);
  if ( a4 )
    *a4 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    DWORD2(v46) = 23421;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v46,
      &v46);
    return v47;
  }
  if ( !a3 )
  {
    DWORD2(v46) = 23422;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v46);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
    return v47;
  }
  if ( a4 || (_DWORD)v5 == 1 )
  {
    v11 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned long,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>>::EnlargeNoPreserve(
                       &v44,
                       &v48,
                       (unsigned int)v5);
    if ( v11 >= 0 )
    {
      v15 = HIDWORD(v45);
      if ( HIDWORD(v45) < (unsigned int)v45 )
        v15 = v45;
      v16 = *((_QWORD *)this + 3);
      HIDWORD(v45) = v15;
      GuidTableEnumeratorData = CdfFetchGuidTableEnumeratorData(v16, v5, *((_QWORD *)&v44 + 1), &v43);
      v18 = GuidTableEnumeratorData;
      if ( GuidTableEnumeratorData >= 0 )
      {
        v22 = (unsigned __int64)v43;
        v23 = 0;
        if ( v43 )
        {
          while ( 1 )
          {
            v43 = 0;
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::Allocate(
                               &v43,
                               &v48);
            if ( v24 < 0 )
              break;
            if ( v15 < (unsigned int)v45 )
              v15 = v45;
            if ( v15 < (unsigned int)v45 )
              v15 = v45;
            HIDWORD(v45) = v15;
            v25 = *(unsigned int *)(*((_QWORD *)&v44 + 1) + 20 * v23 + 16);
            v46 = *(_OWORD *)(*((_QWORD *)&v44 + 1) + 20 * v23);
            v26 = CCounterEntry::Initialize(v43, *((_QWORD *)v49 + 2), v25, &v46);
            n = v26;
            if ( v26 < 0 )
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whid"
                                               "bey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x5B8E,
                v26,
                v27);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(&v43);
              for ( i = 0; (unsigned int)i < (unsigned int)v5; i = (unsigned int)(i + 1) )
              {
                v38 = a3[i];
                if ( v38 )
                  ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
              }
              goto LABEL_10;
            }
            LODWORD(v52) = -1073741595;
            v50 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
            if ( (unsigned int)v23 < (unsigned int)v5 )
            {
              v28 = &a3[v23];
              v29 = 0;
            }
            else
            {
              *(_QWORD *)&v46 = 0;
              v51 = 40;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                &v50,
                &v50);
              v28 = (struct IUnknown **)v46;
              v29 = (int)v52;
            }
            if ( v29 < 0 )
            {
              if ( v29 == g_NTSTATUS_to_break_on_propagate )
                DebugBreak();
              Windows::ErrorHandling::COM::ReportError(
                (Windows::ErrorHandling::COM *)"Status propagated",
                "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x5B8F,
                v29,
                (unsigned int)v43);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v29,
                    v34);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(&v43);
              for ( j = 0; (unsigned int)j < (unsigned int)v5; j = (unsigned int)(j + 1) )
              {
                v36 = a3[j];
                if ( v36 )
                  ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
              }
              goto LABEL_10;
            }
            v30 = (**v43)(v43, &GUID_00000000_0000_0000_c000_000000000046, v28);
            n = v30;
            if ( v30 < 0 )
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whid"
                                               "bey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x5B90,
                v30,
                v31);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(&v43);
              for ( k = 0; (unsigned int)k < (unsigned int)v5; k = (unsigned int)(k + 1) )
              {
                v33 = a3[k];
                if ( v33 )
                  ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
              }
              goto LABEL_10;
            }
            v43 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(&v43);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x5B8C,
            v24,
            (unsigned int)v43);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(&v43);
          for ( m = 0; (unsigned int)m < (unsigned int)v5; m = (unsigned int)(m + 1) )
          {
            v41 = a3[m];
            if ( v41 )
              ((void (__fastcall *)(struct IUnknown *))v41->lpVtbl->Release)(v41);
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
              (const char *)0x5B98,
              -805306219,
              (unsigned int)v43);
            goto LABEL_10;
          }
          *a4 = v22;
        }
        n = v22 != v5;
      }
      else
      {
        if ( GuidTableEnumeratorData == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
          (const char *)0x5B84,
          v18,
          (unsigned int)v43);
        v20 = 0;
        for ( n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v18, v19);
              (unsigned int)v20 < (unsigned int)v5;
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
        (const char *)0x5B83,
        v11,
        (unsigned int)v43);
      n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v11, v12);
      for ( ii = 0; ii < (unsigned int)v5; ++ii )
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
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x5B7F, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
  return n;
}

```

## disassembly

```asm
0x180077c20  push    rbp
0x180077c22  push    rbx
0x180077c23  push    rsi
0x180077c24  push    rdi
0x180077c25  push    r12
0x180077c27  push    r13
0x180077c29  push    r14
0x180077c2b  push    r15
0x180077c2d  lea     rbp, [rsp-1Fh]
0x180077c32  sub     rsp, 0A8h
0x180077c39  mov     rax, cs:__security_cookie
0x180077c40  xor     rax, rsp
0x180077c43  mov     [rbp+57h+var_50], rax
0x180077c47  xor     r13d, r13d
0x180077c4a  mov     [rbp+57h+var_78], rcx
0x180077c4e  mov     rsi, r8
0x180077c51  mov     edi, edx
0x180077c53  mov     r12, rcx
0x180077c56  mov     edx, edx
0x180077c58  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077c5f  mov     [rbp+57h+var_90], 8007054Fh
0x180077c66  xorps   xmm0, xmm0
0x180077c69  mov     qword ptr [rbp+57h+var_A0], r11
0x180077c6d  mov     rcx, rsi
0x180077c70  mov     [rbp+57h+var_C0], r13
0x180077c74  lea     r8, [rbp+57h+var_80]
0x180077c78  mov     [rbp+57h+var_A8], r13
0x180077c7c  mov     r15, r9
0x180077c7f  mov     [rbp+57h+var_80], r13
0x180077c83  movdqu  [rbp+57h+var_B8], xmm0
0x180077c88  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x180077c8d  test    r15, r15
0x180077c90  jz      short loc_180077C95
0x180077c92  mov     [r15], r13d
0x180077c95  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180077c9c  test    rdx, rdx
0x180077c9f  jz      loc_1800780DC
0x180077ca5  mov     rcx, [r12+18h]
0x180077caa  call    RtlIsTypeSafeHandleValid
0x180077caf  test    al, al
0x180077cb1  jz      loc_1800780DC
0x180077cb7  test    rsi, rsi
0x180077cba  jnz     short loc_180077CDA
0x180077cbc  lea     rcx, [rbp+57h+var_A0]
0x180077cc0  mov     dword ptr [rbp+57h+var_A0+8], 5B7Eh
0x180077cc7  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180077ccc  lea     rcx, [rbp+57h+var_B8]
0x180077cd0  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180077cd5  jmp     loc_1800780F9
0x180077cda  test    r15, r15
0x180077cdd  jnz     short loc_180077D07
0x180077cdf  cmp     edi, 1
0x180077ce2  jz      short loc_180077D07
0x180077ce4  mov     ebx, 80004003h
0x180077ce9  mov     edx, 5B7Fh; char *
0x180077cee  mov     r8d, ebx; int
0x180077cf1  mov     rcx, r11; this
0x180077cf4  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180077cf9  lea     rcx, [rbp+57h+var_B8]
0x180077cfd  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180077d02  jmp     loc_1800780FC
0x180077d07  mov     r8d, edi
0x180077d0a  lea     rdx, [rbp+57h+var_80]
0x180077d0e  lea     rcx, [rbp+57h+var_B8]
0x180077d12  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180077d17  mov     ebx, [rax]
0x180077d19  test    ebx, ebx
0x180077d1b  jns     short loc_180077D79
0x180077d1d  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180077d23  jnz     short loc_180077D2B
0x180077d25  call    cs:__imp_DebugBreak
0x180077d2b  mov     r9d, ebx; int
0x180077d2e  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077d35  mov     r8d, 5B83h; char *
0x180077d3b  lea     rcx, aStatusPropagat; "Status propagated"
0x180077d42  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077d47  mov     ecx, ebx; this
0x180077d49  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180077d4e  mov     ebx, eax
0x180077d50  mov     r14d, r13d
0x180077d53  test    edi, edi
0x180077d55  jz      short loc_180077CF9
0x180077d57  mov     ecx, r14d
0x180077d5a  mov     rcx, [rsi+rcx*8]
0x180077d5e  test    rcx, rcx
0x180077d61  jz      short loc_180077D6F
0x180077d63  mov     rdx, [rcx]
0x180077d66  mov     rax, [rdx+10h]
0x180077d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077d6f  inc     r14d
0x180077d72  cmp     r14d, edi
0x180077d75  jb      short loc_180077D57
0x180077d77  jmp     short loc_180077CF9
0x180077d79  mov     r13d, dword ptr [rbp+57h+var_A8+4]
0x180077d7d  lea     r9, [rbp+57h+var_C0]
0x180077d81  cmp     r13d, dword ptr [rbp+57h+var_A8]
0x180077d85  mov     rdx, rdi
0x180077d88  mov     r8, qword ptr [rbp+57h+var_B8+8]
0x180077d8c  cmovb   r13d, dword ptr [rbp+57h+var_A8]
0x180077d91  mov     rcx, [r12+18h]
0x180077d96  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x180077d9a  call    CdfFetchGuidTableEnumeratorData
0x180077d9f  mov     ebx, eax
0x180077da1  test    eax, eax
0x180077da3  jns     short loc_180077E05
0x180077da5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180077dab  jnz     short loc_180077DB3
0x180077dad  call    cs:__imp_DebugBreak
0x180077db3  mov     r9d, ebx; int
0x180077db6  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077dbd  mov     r8d, 5B84h; char *
0x180077dc3  lea     rcx, aStatusPropagat; "Status propagated"
0x180077dca  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077dcf  mov     ecx, ebx; this
0x180077dd1  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180077dd6  xor     r14d, r14d
0x180077dd9  mov     ebx, eax
0x180077ddb  test    edi, edi
0x180077ddd  jz      loc_180077CF9
0x180077de3  mov     rcx, [rsi+r14*8]
0x180077de7  test    rcx, rcx
0x180077dea  jz      short loc_180077DF8
0x180077dec  mov     rax, [rcx]
0x180077def  mov     rax, [rax+10h]
0x180077df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077df8  inc     r14d
0x180077dfb  cmp     r14d, edi
0x180077dfe  jb      short loc_180077DE3
0x180077e00  jmp     loc_180077CF9
0x180077e05  mov     r14, [rbp+57h+var_C0]
0x180077e09  xor     r12d, r12d
0x180077e0c  test    r14, r14
0x180077e0f  jz      loc_180077F0B
0x180077e15  lea     rdx, [rbp+57h+var_80]
0x180077e19  mov     [rbp+57h+var_C0], 0
0x180077e21  lea     rcx, [rbp+57h+var_C0]
0x180077e25  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::Allocate(void)
0x180077e2a  mov     ebx, [rax]
0x180077e2c  test    ebx, ebx
0x180077e2e  js      loc_180078056
0x180077e34  mov     eax, dword ptr [rbp+57h+var_A8]
0x180077e37  lea     r8, [r12+r12*4]
0x180077e3b  mov     rcx, [rbp+57h+var_C0]
0x180077e3f  lea     r9, [rbp+57h+var_A0]
0x180077e43  cmp     r13d, eax
0x180077e46  cmovb   r13d, eax
0x180077e4a  cmp     r13d, eax
0x180077e4d  cmovb   r13d, eax
0x180077e51  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x180077e55  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x180077e59  movups  xmm0, xmmword ptr [rax+r8*4]
0x180077e5e  mov     r8d, [rax+r8*4+10h]
0x180077e63  mov     rax, [rbp+57h+var_78]
0x180077e67  movdqu  [rbp+57h+var_A0], xmm0
0x180077e6c  mov     rdx, [rax+10h]
0x180077e70  call    ?Initialize@CCounterEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@U_GUID@@@Z; CCounterEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,_GUID)
0x180077e75  mov     ebx, eax
0x180077e77  test    eax, eax
0x180077e79  js      loc_18007800C
0x180077e7f  mov     dword ptr [rbp+57h+var_58], 0C00000E5h
0x180077e86  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077e8d  mov     [rbp+57h+var_68], rax
0x180077e91  cmp     r12d, edi
0x180077e94  jb      short loc_180077EBB
0x180077e96  mov     qword ptr [rbp+57h+var_A0], 0
0x180077e9e  mov     [rbp+57h+var_60], 28h ; '('
0x180077ea5  lea     rdx, [rbp+57h+var_68]
0x180077ea9  lea     rcx, [rbp+57h+var_68]
0x180077ead  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180077eb2  mov     rcx, qword ptr [rbp+57h+var_A0]
0x180077eb6  mov     ebx, dword ptr [rbp+57h+var_58]
0x180077eb9  jmp     short loc_180077EC1
0x180077ebb  lea     rcx, [rsi+r12*8]
0x180077ebf  xor     ebx, ebx
0x180077ec1  test    ebx, ebx
0x180077ec3  js      loc_180077FA3
0x180077ec9  mov     r9, [rbp+57h+var_C0]
0x180077ecd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180077ed4  mov     r8, rcx
0x180077ed7  mov     rcx, r9
0x180077eda  mov     rax, [r9]
0x180077edd  mov     rax, [rax]
0x180077ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ee5  mov     ebx, eax
0x180077ee7  test    eax, eax
0x180077ee9  js      short loc_180077F59
0x180077eeb  lea     rcx, [rbp+57h+var_C0]
0x180077eef  mov     [rbp+57h+var_C0], 0
0x180077ef7  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(void)
0x180077efc  inc     r12d
0x180077eff  mov     eax, r12d
0x180077f02  cmp     rax, r14
0x180077f05  jb      loc_180077E15
0x180077f0b  test    r15, r15
0x180077f0e  jz      loc_1800780C2
0x180077f14  mov     eax, 0FFFFFFFFh
0x180077f19  cmp     r14, rax
0x180077f1c  jbe     loc_1800780BF
0x180077f22  mov     ebx, 0D0000095h
0x180077f27  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x180077f2d  jnz     short loc_180077F35
0x180077f2f  call    cs:__imp_DebugBreak
0x180077f35  mov     r9d, 0D0000095h; int
0x180077f3b  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077f42  mov     r8d, 5B98h; char *
0x180077f48  lea     rcx, aHrOriginated; "HR originated"
0x180077f4f  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077f54  jmp     loc_180077CF9
0x180077f59  mov     r8d, eax; int
0x180077f5c  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077f63  mov     edx, 5B90h; char *
0x180077f68  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180077f6d  lea     rcx, [rbp+57h+var_C0]
0x180077f71  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(void)
0x180077f76  xor     r14d, r14d
0x180077f79  test    edi, edi
0x180077f7b  jz      loc_180077CF9
0x180077f81  mov     rcx, [rsi+r14*8]
0x180077f85  test    rcx, rcx
0x180077f88  jz      short loc_180077F96
0x180077f8a  mov     rax, [rcx]
0x180077f8d  mov     rax, [rax+10h]
0x180077f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077f96  inc     r14d
0x180077f99  cmp     r14d, edi
0x180077f9c  jb      short loc_180077F81
0x180077f9e  jmp     loc_180077CF9
0x180077fa3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180077fa9  jnz     short loc_180077FB1
0x180077fab  call    cs:__imp_DebugBreak
0x180077fb1  mov     r9d, ebx; int
0x180077fb4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180077fbb  mov     r8d, 5B8Fh; char *
0x180077fc1  lea     rcx, aStatusPropagat; "Status propagated"
0x180077fc8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180077fcd  mov     ecx, ebx; this
0x180077fcf  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180077fd4  lea     rcx, [rbp+57h+var_C0]
0x180077fd8  mov     ebx, eax
0x180077fda  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(void)
0x180077fdf  xor     r14d, r14d
0x180077fe2  test    edi, edi
0x180077fe4  jz      loc_180077CF9
0x180077fea  mov     rcx, [rsi+r14*8]
0x180077fee  test    rcx, rcx
0x180077ff1  jz      short loc_180077FFF
0x180077ff3  mov     rax, [rcx]
0x180077ff6  mov     rax, [rax+10h]
0x180077ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077fff  inc     r14d
0x180078002  cmp     r14d, edi
0x180078005  jb      short loc_180077FEA
0x180078007  jmp     loc_180077CF9
0x18007800c  mov     r8d, eax; int
0x18007800f  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180078016  mov     edx, 5B8Eh; char *
0x18007801b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180078020  lea     rcx, [rbp+57h+var_C0]
0x180078024  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(void)
0x180078029  xor     r14d, r14d
0x18007802c  test    edi, edi
0x18007802e  jz      loc_180077CF9
0x180078034  mov     rcx, [rsi+r14*8]
0x180078038  test    rcx, rcx
0x18007803b  jz      short loc_180078049
0x18007803d  mov     rax, [rcx]
0x180078040  mov     rax, [rax+10h]
0x180078044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078049  inc     r14d
0x18007804c  cmp     r14d, edi
0x18007804f  jb      short loc_180078034
0x180078051  jmp     loc_180077CF9
0x180078056  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007805c  jnz     short loc_180078064
0x18007805e  call    cs:__imp_DebugBreak
0x180078064  mov     r9d, ebx; int
0x180078067  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007806e  mov     r8d, 5B8Ch; char *
0x180078074  lea     rcx, aStatusPropagat; "Status propagated"
0x18007807b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180078080  mov     ecx, ebx; this
0x180078082  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180078087  lea     rcx, [rbp+57h+var_C0]
0x18007808b  mov     ebx, eax
0x18007808d  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterEntry>>>(void)
0x180078092  xor     r14d, r14d
0x180078095  test    edi, edi
0x180078097  jz      loc_180077CF9
0x18007809d  mov     rcx, [rsi+r14*8]
0x1800780a1  test    rcx, rcx
0x1800780a4  jz      short loc_1800780B2
0x1800780a6  mov     rax, [rcx]
0x1800780a9  mov     rax, [rax+10h]
0x1800780ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800780b2  inc     r14d
0x1800780b5  cmp     r14d, edi
0x1800780b8  jb      short loc_18007809D
0x1800780ba  jmp     loc_180077CF9
0x1800780bf  mov     [r15], r14d
0x1800780c2  lea     rcx, [rbp+57h+var_B8]
  ... truncated ...
```
