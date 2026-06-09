# CEnumCLRSurrogateSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180074170`
- end: `0x18007466e`
- name: `?Next@CEnumCLRSurrogateSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1278`
- prototype: `__int64 __fastcall(CEnumCLRSurrogateSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180057c08`
- `0x18005a3bc`
- `0x18005de44`
- `0x180066cf4`
- `0x180074170`
- `0x1800d552c`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180074275`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800742fd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007447f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800744fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800745ae`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180074275`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800742fd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007447f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800744fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800745ae`

## string_xrefs

- `0x1800741a8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007427e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180074306`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800743d6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007448b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800744ac`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180074504`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007455f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800745b7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCLRSurrogateSection::Next(
        CEnumCLRSurrogateSection *this,
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
  CEnumCLRSurrogateSection *v49; // [rsp+68h] [rbp-21h]
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
    DWORD2(v46) = 21514;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v46,
      &v46);
    return v47;
  }
  if ( !a3 )
  {
    DWORD2(v46) = 21515;
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
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::Allocate(
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
            v26 = CCLRSurrogateEntry::Initialize(v43, *((_QWORD *)v49 + 2), v25, &v46);
            n = v26;
            if ( v26 < 0 )
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whid"
                                               "bey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x541B,
                v26,
                v27);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(&v43);
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
                (const char *)0x541C,
                v29,
                (unsigned int)v43);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v29,
                    v34);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(&v43);
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
                (const char *)0x541D,
                v30,
                v31);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(&v43);
              for ( k = 0; (unsigned int)k < (unsigned int)v5; k = (unsigned int)(k + 1) )
              {
                v33 = a3[k];
                if ( v33 )
                  ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
              }
              goto LABEL_10;
            }
            v43 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(&v43);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x5419,
            v24,
            (unsigned int)v43);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(&v43);
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
              (const char *)0x5425,
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
          (const char *)0x5411,
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
        (const char *)0x5410,
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
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x540C, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
  return n;
}

```

## disassembly

```asm
0x180074170  push    rbp
0x180074172  push    rbx
0x180074173  push    rsi
0x180074174  push    rdi
0x180074175  push    r12
0x180074177  push    r13
0x180074179  push    r14
0x18007417b  push    r15
0x18007417d  lea     rbp, [rsp-1Fh]
0x180074182  sub     rsp, 0A8h
0x180074189  mov     rax, cs:__security_cookie
0x180074190  xor     rax, rsp
0x180074193  mov     [rbp+57h+var_50], rax
0x180074197  xor     r13d, r13d
0x18007419a  mov     [rbp+57h+var_78], rcx
0x18007419e  mov     rsi, r8
0x1800741a1  mov     edi, edx
0x1800741a3  mov     r12, rcx
0x1800741a6  mov     edx, edx
0x1800741a8  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800741af  mov     [rbp+57h+var_90], 8007054Fh
0x1800741b6  xorps   xmm0, xmm0
0x1800741b9  mov     qword ptr [rbp+57h+var_A0], r11
0x1800741bd  mov     rcx, rsi
0x1800741c0  mov     [rbp+57h+var_C0], r13
0x1800741c4  lea     r8, [rbp+57h+var_80]
0x1800741c8  mov     [rbp+57h+var_A8], r13
0x1800741cc  mov     r15, r9
0x1800741cf  mov     [rbp+57h+var_80], r13
0x1800741d3  movdqu  [rbp+57h+var_B8], xmm0
0x1800741d8  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x1800741dd  test    r15, r15
0x1800741e0  jz      short loc_1800741E5
0x1800741e2  mov     [r15], r13d
0x1800741e5  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800741ec  test    rdx, rdx
0x1800741ef  jz      loc_18007462C
0x1800741f5  mov     rcx, [r12+18h]
0x1800741fa  call    RtlIsTypeSafeHandleValid
0x1800741ff  test    al, al
0x180074201  jz      loc_18007462C
0x180074207  test    rsi, rsi
0x18007420a  jnz     short loc_18007422A
0x18007420c  lea     rcx, [rbp+57h+var_A0]
0x180074210  mov     dword ptr [rbp+57h+var_A0+8], 540Bh
0x180074217  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007421c  lea     rcx, [rbp+57h+var_B8]
0x180074220  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180074225  jmp     loc_180074649
0x18007422a  test    r15, r15
0x18007422d  jnz     short loc_180074257
0x18007422f  cmp     edi, 1
0x180074232  jz      short loc_180074257
0x180074234  mov     ebx, 80004003h
0x180074239  mov     edx, 540Ch; char *
0x18007423e  mov     r8d, ebx; int
0x180074241  mov     rcx, r11; this
0x180074244  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180074249  lea     rcx, [rbp+57h+var_B8]
0x18007424d  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180074252  jmp     loc_18007464C
0x180074257  mov     r8d, edi
0x18007425a  lea     rdx, [rbp+57h+var_80]
0x18007425e  lea     rcx, [rbp+57h+var_B8]
0x180074262  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180074267  mov     ebx, [rax]
0x180074269  test    ebx, ebx
0x18007426b  jns     short loc_1800742C9
0x18007426d  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180074273  jnz     short loc_18007427B
0x180074275  call    cs:__imp_DebugBreak
0x18007427b  mov     r9d, ebx; int
0x18007427e  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180074285  mov     r8d, 5410h; char *
0x18007428b  lea     rcx, aStatusPropagat; "Status propagated"
0x180074292  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180074297  mov     ecx, ebx; this
0x180074299  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007429e  mov     ebx, eax
0x1800742a0  mov     r14d, r13d
0x1800742a3  test    edi, edi
0x1800742a5  jz      short loc_180074249
0x1800742a7  mov     ecx, r14d
0x1800742aa  mov     rcx, [rsi+rcx*8]
0x1800742ae  test    rcx, rcx
0x1800742b1  jz      short loc_1800742BF
0x1800742b3  mov     rdx, [rcx]
0x1800742b6  mov     rax, [rdx+10h]
0x1800742ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742bf  inc     r14d
0x1800742c2  cmp     r14d, edi
0x1800742c5  jb      short loc_1800742A7
0x1800742c7  jmp     short loc_180074249
0x1800742c9  mov     r13d, dword ptr [rbp+57h+var_A8+4]
0x1800742cd  lea     r9, [rbp+57h+var_C0]
0x1800742d1  cmp     r13d, dword ptr [rbp+57h+var_A8]
0x1800742d5  mov     rdx, rdi
0x1800742d8  mov     r8, qword ptr [rbp+57h+var_B8+8]
0x1800742dc  cmovb   r13d, dword ptr [rbp+57h+var_A8]
0x1800742e1  mov     rcx, [r12+18h]
0x1800742e6  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x1800742ea  call    CdfFetchGuidTableEnumeratorData
0x1800742ef  mov     ebx, eax
0x1800742f1  test    eax, eax
0x1800742f3  jns     short loc_180074355
0x1800742f5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800742fb  jnz     short loc_180074303
0x1800742fd  call    cs:__imp_DebugBreak
0x180074303  mov     r9d, ebx; int
0x180074306  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007430d  mov     r8d, 5411h; char *
0x180074313  lea     rcx, aStatusPropagat; "Status propagated"
0x18007431a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007431f  mov     ecx, ebx; this
0x180074321  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180074326  xor     r14d, r14d
0x180074329  mov     ebx, eax
0x18007432b  test    edi, edi
0x18007432d  jz      loc_180074249
0x180074333  mov     rcx, [rsi+r14*8]
0x180074337  test    rcx, rcx
0x18007433a  jz      short loc_180074348
0x18007433c  mov     rax, [rcx]
0x18007433f  mov     rax, [rax+10h]
0x180074343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074348  inc     r14d
0x18007434b  cmp     r14d, edi
0x18007434e  jb      short loc_180074333
0x180074350  jmp     loc_180074249
0x180074355  mov     r14, [rbp+57h+var_C0]
0x180074359  xor     r12d, r12d
0x18007435c  test    r14, r14
0x18007435f  jz      loc_18007445B
0x180074365  lea     rdx, [rbp+57h+var_80]
0x180074369  mov     [rbp+57h+var_C0], 0
0x180074371  lea     rcx, [rbp+57h+var_C0]
0x180074375  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCLRSurrogateEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::Allocate(void)
0x18007437a  mov     ebx, [rax]
0x18007437c  test    ebx, ebx
0x18007437e  js      loc_1800745A6
0x180074384  mov     eax, dword ptr [rbp+57h+var_A8]
0x180074387  lea     r8, [r12+r12*4]
0x18007438b  mov     rcx, [rbp+57h+var_C0]
0x18007438f  lea     r9, [rbp+57h+var_A0]
0x180074393  cmp     r13d, eax
0x180074396  cmovb   r13d, eax
0x18007439a  cmp     r13d, eax
0x18007439d  cmovb   r13d, eax
0x1800743a1  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x1800743a5  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x1800743a9  movups  xmm0, xmmword ptr [rax+r8*4]
0x1800743ae  mov     r8d, [rax+r8*4+10h]
0x1800743b3  mov     rax, [rbp+57h+var_78]
0x1800743b7  movdqu  [rbp+57h+var_A0], xmm0
0x1800743bc  mov     rdx, [rax+10h]
0x1800743c0  call    ?Initialize@CCLRSurrogateEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@U_GUID@@@Z; CCLRSurrogateEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,_GUID)
0x1800743c5  mov     ebx, eax
0x1800743c7  test    eax, eax
0x1800743c9  js      loc_18007455C
0x1800743cf  mov     dword ptr [rbp+57h+var_58], 0C00000E5h
0x1800743d6  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800743dd  mov     [rbp+57h+var_68], rax
0x1800743e1  cmp     r12d, edi
0x1800743e4  jb      short loc_18007440B
0x1800743e6  mov     qword ptr [rbp+57h+var_A0], 0
0x1800743ee  mov     [rbp+57h+var_60], 28h ; '('
0x1800743f5  lea     rdx, [rbp+57h+var_68]
0x1800743f9  lea     rcx, [rbp+57h+var_68]
0x1800743fd  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180074402  mov     rcx, qword ptr [rbp+57h+var_A0]
0x180074406  mov     ebx, dword ptr [rbp+57h+var_58]
0x180074409  jmp     short loc_180074411
0x18007440b  lea     rcx, [rsi+r12*8]
0x18007440f  xor     ebx, ebx
0x180074411  test    ebx, ebx
0x180074413  js      loc_1800744F3
0x180074419  mov     r9, [rbp+57h+var_C0]
0x18007441d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180074424  mov     r8, rcx
0x180074427  mov     rcx, r9
0x18007442a  mov     rax, [r9]
0x18007442d  mov     rax, [rax]
0x180074430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074435  mov     ebx, eax
0x180074437  test    eax, eax
0x180074439  js      short loc_1800744A9
0x18007443b  lea     rcx, [rbp+57h+var_C0]
0x18007443f  mov     [rbp+57h+var_C0], 0
0x180074447  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCLRSurrogateEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(void)
0x18007444c  inc     r12d
0x18007444f  mov     eax, r12d
0x180074452  cmp     rax, r14
0x180074455  jb      loc_180074365
0x18007445b  test    r15, r15
0x18007445e  jz      loc_180074612
0x180074464  mov     eax, 0FFFFFFFFh
0x180074469  cmp     r14, rax
0x18007446c  jbe     loc_18007460F
0x180074472  mov     ebx, 0D0000095h
0x180074477  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x18007447d  jnz     short loc_180074485
0x18007447f  call    cs:__imp_DebugBreak
0x180074485  mov     r9d, 0D0000095h; int
0x18007448b  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180074492  mov     r8d, 5425h; char *
0x180074498  lea     rcx, aHrOriginated; "HR originated"
0x18007449f  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800744a4  jmp     loc_180074249
0x1800744a9  mov     r8d, eax; int
0x1800744ac  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800744b3  mov     edx, 541Dh; char *
0x1800744b8  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800744bd  lea     rcx, [rbp+57h+var_C0]
0x1800744c1  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCLRSurrogateEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(void)
0x1800744c6  xor     r14d, r14d
0x1800744c9  test    edi, edi
0x1800744cb  jz      loc_180074249
0x1800744d1  mov     rcx, [rsi+r14*8]
0x1800744d5  test    rcx, rcx
0x1800744d8  jz      short loc_1800744E6
0x1800744da  mov     rax, [rcx]
0x1800744dd  mov     rax, [rax+10h]
0x1800744e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800744e6  inc     r14d
0x1800744e9  cmp     r14d, edi
0x1800744ec  jb      short loc_1800744D1
0x1800744ee  jmp     loc_180074249
0x1800744f3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800744f9  jnz     short loc_180074501
0x1800744fb  call    cs:__imp_DebugBreak
0x180074501  mov     r9d, ebx; int
0x180074504  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007450b  mov     r8d, 541Ch; char *
0x180074511  lea     rcx, aStatusPropagat; "Status propagated"
0x180074518  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007451d  mov     ecx, ebx; this
0x18007451f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180074524  lea     rcx, [rbp+57h+var_C0]
0x180074528  mov     ebx, eax
0x18007452a  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCLRSurrogateEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(void)
0x18007452f  xor     r14d, r14d
0x180074532  test    edi, edi
0x180074534  jz      loc_180074249
0x18007453a  mov     rcx, [rsi+r14*8]
0x18007453e  test    rcx, rcx
0x180074541  jz      short loc_18007454F
0x180074543  mov     rax, [rcx]
0x180074546  mov     rax, [rax+10h]
0x18007454a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007454f  inc     r14d
0x180074552  cmp     r14d, edi
0x180074555  jb      short loc_18007453A
0x180074557  jmp     loc_180074249
0x18007455c  mov     r8d, eax; int
0x18007455f  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180074566  mov     edx, 541Bh; char *
0x18007456b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180074570  lea     rcx, [rbp+57h+var_C0]
0x180074574  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCLRSurrogateEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(void)
0x180074579  xor     r14d, r14d
0x18007457c  test    edi, edi
0x18007457e  jz      loc_180074249
0x180074584  mov     rcx, [rsi+r14*8]
0x180074588  test    rcx, rcx
0x18007458b  jz      short loc_180074599
0x18007458d  mov     rax, [rcx]
0x180074590  mov     rax, [rax+10h]
0x180074594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074599  inc     r14d
0x18007459c  cmp     r14d, edi
0x18007459f  jb      short loc_180074584
0x1800745a1  jmp     loc_180074249
0x1800745a6  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800745ac  jnz     short loc_1800745B4
0x1800745ae  call    cs:__imp_DebugBreak
0x1800745b4  mov     r9d, ebx; int
0x1800745b7  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800745be  mov     r8d, 5419h; char *
0x1800745c4  lea     rcx, aStatusPropagat; "Status propagated"
0x1800745cb  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800745d0  mov     ecx, ebx; this
0x1800745d2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800745d7  lea     rcx, [rbp+57h+var_C0]
0x1800745db  mov     ebx, eax
0x1800745dd  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCLRSurrogateEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCLRSurrogateEntry>>>(void)
0x1800745e2  xor     r14d, r14d
0x1800745e5  test    edi, edi
0x1800745e7  jz      loc_180074249
0x1800745ed  mov     rcx, [rsi+r14*8]
0x1800745f1  test    rcx, rcx
0x1800745f4  jz      short loc_180074602
0x1800745f6  mov     rax, [rcx]
0x1800745f9  mov     rax, [rax+10h]
0x1800745fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074602  inc     r14d
0x180074605  cmp     r14d, edi
0x180074608  jb      short loc_1800745ED
0x18007460a  jmp     loc_180074249
0x18007460f  mov     [r15], r14d
0x180074612  lea     rcx, [rbp+57h+var_B8]
  ... truncated ...
```
