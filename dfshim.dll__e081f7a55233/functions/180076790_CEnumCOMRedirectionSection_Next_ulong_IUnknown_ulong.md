# CEnumCOMRedirectionSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180076790`
- end: `0x180076c8e`
- name: `?Next@CEnumCOMRedirectionSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1278`
- prototype: `__int64 __fastcall(CEnumCOMRedirectionSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180057c78`
- `0x18005a5a0`
- `0x18005de44`
- `0x180066f88`
- `0x180076790`
- `0x1800d552c`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076895`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007691d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076a9f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076b1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076bce`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076895`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007691d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076a9f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076b1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180076bce`

## string_xrefs

- `0x1800767c8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007689e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076926`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800769f6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076aab`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076acc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076b24`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076b7f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180076bd7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCOMRedirectionSection::Next(
        CEnumCOMRedirectionSection *this,
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
  CEnumCOMRedirectionSection *v49; // [rsp+68h] [rbp-21h]
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
    DWORD2(v46) = 21290;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v46,
      &v46);
    return v47;
  }
  if ( !a3 )
  {
    DWORD2(v46) = 21291;
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
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::Allocate(
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
            v26 = CCOMServerEntry::Initialize(v43, *((_QWORD *)v49 + 2), v25, &v46);
            n = v26;
            if ( v26 < 0 )
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whid"
                                               "bey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x533B,
                v26,
                v27);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(&v43);
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
                (const char *)0x533C,
                v29,
                (unsigned int)v43);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v29,
                    v34);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(&v43);
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
                (const char *)0x533D,
                v30,
                v31);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(&v43);
              for ( k = 0; (unsigned int)k < (unsigned int)v5; k = (unsigned int)(k + 1) )
              {
                v33 = a3[k];
                if ( v33 )
                  ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
              }
              goto LABEL_10;
            }
            v43 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(&v43);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x5339,
            v24,
            (unsigned int)v43);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(&v43);
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
              (const char *)0x5345,
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
          (const char *)0x5331,
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
        (const char *)0x5330,
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
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x532C, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
  return n;
}

```

## disassembly

```asm
0x180076790  push    rbp
0x180076792  push    rbx
0x180076793  push    rsi
0x180076794  push    rdi
0x180076795  push    r12
0x180076797  push    r13
0x180076799  push    r14
0x18007679b  push    r15
0x18007679d  lea     rbp, [rsp-1Fh]
0x1800767a2  sub     rsp, 0A8h
0x1800767a9  mov     rax, cs:__security_cookie
0x1800767b0  xor     rax, rsp
0x1800767b3  mov     [rbp+57h+var_50], rax
0x1800767b7  xor     r13d, r13d
0x1800767ba  mov     [rbp+57h+var_78], rcx
0x1800767be  mov     rsi, r8
0x1800767c1  mov     edi, edx
0x1800767c3  mov     r12, rcx
0x1800767c6  mov     edx, edx
0x1800767c8  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800767cf  mov     [rbp+57h+var_90], 8007054Fh
0x1800767d6  xorps   xmm0, xmm0
0x1800767d9  mov     qword ptr [rbp+57h+var_A0], r11
0x1800767dd  mov     rcx, rsi
0x1800767e0  mov     [rbp+57h+var_C0], r13
0x1800767e4  lea     r8, [rbp+57h+var_80]
0x1800767e8  mov     [rbp+57h+var_A8], r13
0x1800767ec  mov     r15, r9
0x1800767ef  mov     [rbp+57h+var_80], r13
0x1800767f3  movdqu  [rbp+57h+var_B8], xmm0
0x1800767f8  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x1800767fd  test    r15, r15
0x180076800  jz      short loc_180076805
0x180076802  mov     [r15], r13d
0x180076805  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18007680c  test    rdx, rdx
0x18007680f  jz      loc_180076C4C
0x180076815  mov     rcx, [r12+18h]
0x18007681a  call    RtlIsTypeSafeHandleValid
0x18007681f  test    al, al
0x180076821  jz      loc_180076C4C
0x180076827  test    rsi, rsi
0x18007682a  jnz     short loc_18007684A
0x18007682c  lea     rcx, [rbp+57h+var_A0]
0x180076830  mov     dword ptr [rbp+57h+var_A0+8], 532Bh
0x180076837  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18007683c  lea     rcx, [rbp+57h+var_B8]
0x180076840  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180076845  jmp     loc_180076C69
0x18007684a  test    r15, r15
0x18007684d  jnz     short loc_180076877
0x18007684f  cmp     edi, 1
0x180076852  jz      short loc_180076877
0x180076854  mov     ebx, 80004003h
0x180076859  mov     edx, 532Ch; char *
0x18007685e  mov     r8d, ebx; int
0x180076861  mov     rcx, r11; this
0x180076864  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180076869  lea     rcx, [rbp+57h+var_B8]
0x18007686d  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180076872  jmp     loc_180076C6C
0x180076877  mov     r8d, edi
0x18007687a  lea     rdx, [rbp+57h+var_80]
0x18007687e  lea     rcx, [rbp+57h+var_B8]
0x180076882  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180076887  mov     ebx, [rax]
0x180076889  test    ebx, ebx
0x18007688b  jns     short loc_1800768E9
0x18007688d  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180076893  jnz     short loc_18007689B
0x180076895  call    cs:__imp_DebugBreak
0x18007689b  mov     r9d, ebx; int
0x18007689e  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800768a5  mov     r8d, 5330h; char *
0x1800768ab  lea     rcx, aStatusPropagat; "Status propagated"
0x1800768b2  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800768b7  mov     ecx, ebx; this
0x1800768b9  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800768be  mov     ebx, eax
0x1800768c0  mov     r14d, r13d
0x1800768c3  test    edi, edi
0x1800768c5  jz      short loc_180076869
0x1800768c7  mov     ecx, r14d
0x1800768ca  mov     rcx, [rsi+rcx*8]
0x1800768ce  test    rcx, rcx
0x1800768d1  jz      short loc_1800768DF
0x1800768d3  mov     rdx, [rcx]
0x1800768d6  mov     rax, [rdx+10h]
0x1800768da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800768df  inc     r14d
0x1800768e2  cmp     r14d, edi
0x1800768e5  jb      short loc_1800768C7
0x1800768e7  jmp     short loc_180076869
0x1800768e9  mov     r13d, dword ptr [rbp+57h+var_A8+4]
0x1800768ed  lea     r9, [rbp+57h+var_C0]
0x1800768f1  cmp     r13d, dword ptr [rbp+57h+var_A8]
0x1800768f5  mov     rdx, rdi
0x1800768f8  mov     r8, qword ptr [rbp+57h+var_B8+8]
0x1800768fc  cmovb   r13d, dword ptr [rbp+57h+var_A8]
0x180076901  mov     rcx, [r12+18h]
0x180076906  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x18007690a  call    CdfFetchGuidTableEnumeratorData
0x18007690f  mov     ebx, eax
0x180076911  test    eax, eax
0x180076913  jns     short loc_180076975
0x180076915  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18007691b  jnz     short loc_180076923
0x18007691d  call    cs:__imp_DebugBreak
0x180076923  mov     r9d, ebx; int
0x180076926  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007692d  mov     r8d, 5331h; char *
0x180076933  lea     rcx, aStatusPropagat; "Status propagated"
0x18007693a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18007693f  mov     ecx, ebx; this
0x180076941  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180076946  xor     r14d, r14d
0x180076949  mov     ebx, eax
0x18007694b  test    edi, edi
0x18007694d  jz      loc_180076869
0x180076953  mov     rcx, [rsi+r14*8]
0x180076957  test    rcx, rcx
0x18007695a  jz      short loc_180076968
0x18007695c  mov     rax, [rcx]
0x18007695f  mov     rax, [rax+10h]
0x180076963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076968  inc     r14d
0x18007696b  cmp     r14d, edi
0x18007696e  jb      short loc_180076953
0x180076970  jmp     loc_180076869
0x180076975  mov     r14, [rbp+57h+var_C0]
0x180076979  xor     r12d, r12d
0x18007697c  test    r14, r14
0x18007697f  jz      loc_180076A7B
0x180076985  lea     rdx, [rbp+57h+var_80]
0x180076989  mov     [rbp+57h+var_C0], 0
0x180076991  lea     rcx, [rbp+57h+var_C0]
0x180076995  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCOMServerEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::Allocate(void)
0x18007699a  mov     ebx, [rax]
0x18007699c  test    ebx, ebx
0x18007699e  js      loc_180076BC6
0x1800769a4  mov     eax, dword ptr [rbp+57h+var_A8]
0x1800769a7  lea     r8, [r12+r12*4]
0x1800769ab  mov     rcx, [rbp+57h+var_C0]
0x1800769af  lea     r9, [rbp+57h+var_A0]
0x1800769b3  cmp     r13d, eax
0x1800769b6  cmovb   r13d, eax
0x1800769ba  cmp     r13d, eax
0x1800769bd  cmovb   r13d, eax
0x1800769c1  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x1800769c5  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x1800769c9  movups  xmm0, xmmword ptr [rax+r8*4]
0x1800769ce  mov     r8d, [rax+r8*4+10h]
0x1800769d3  mov     rax, [rbp+57h+var_78]
0x1800769d7  movdqu  [rbp+57h+var_A0], xmm0
0x1800769dc  mov     rdx, [rax+10h]
0x1800769e0  call    ?Initialize@CCOMServerEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@U_GUID@@@Z; CCOMServerEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,_GUID)
0x1800769e5  mov     ebx, eax
0x1800769e7  test    eax, eax
0x1800769e9  js      loc_180076B7C
0x1800769ef  mov     dword ptr [rbp+57h+var_58], 0C00000E5h
0x1800769f6  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800769fd  mov     [rbp+57h+var_68], rax
0x180076a01  cmp     r12d, edi
0x180076a04  jb      short loc_180076A2B
0x180076a06  mov     qword ptr [rbp+57h+var_A0], 0
0x180076a0e  mov     [rbp+57h+var_60], 28h ; '('
0x180076a15  lea     rdx, [rbp+57h+var_68]
0x180076a19  lea     rcx, [rbp+57h+var_68]
0x180076a1d  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180076a22  mov     rcx, qword ptr [rbp+57h+var_A0]
0x180076a26  mov     ebx, dword ptr [rbp+57h+var_58]
0x180076a29  jmp     short loc_180076A31
0x180076a2b  lea     rcx, [rsi+r12*8]
0x180076a2f  xor     ebx, ebx
0x180076a31  test    ebx, ebx
0x180076a33  js      loc_180076B13
0x180076a39  mov     r9, [rbp+57h+var_C0]
0x180076a3d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180076a44  mov     r8, rcx
0x180076a47  mov     rcx, r9
0x180076a4a  mov     rax, [r9]
0x180076a4d  mov     rax, [rax]
0x180076a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a55  mov     ebx, eax
0x180076a57  test    eax, eax
0x180076a59  js      short loc_180076AC9
0x180076a5b  lea     rcx, [rbp+57h+var_C0]
0x180076a5f  mov     [rbp+57h+var_C0], 0
0x180076a67  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCOMServerEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(void)
0x180076a6c  inc     r12d
0x180076a6f  mov     eax, r12d
0x180076a72  cmp     rax, r14
0x180076a75  jb      loc_180076985
0x180076a7b  test    r15, r15
0x180076a7e  jz      loc_180076C32
0x180076a84  mov     eax, 0FFFFFFFFh
0x180076a89  cmp     r14, rax
0x180076a8c  jbe     loc_180076C2F
0x180076a92  mov     ebx, 0D0000095h
0x180076a97  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x180076a9d  jnz     short loc_180076AA5
0x180076a9f  call    cs:__imp_DebugBreak
0x180076aa5  mov     r9d, 0D0000095h; int
0x180076aab  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076ab2  mov     r8d, 5345h; char *
0x180076ab8  lea     rcx, aHrOriginated; "HR originated"
0x180076abf  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180076ac4  jmp     loc_180076869
0x180076ac9  mov     r8d, eax; int
0x180076acc  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076ad3  mov     edx, 533Dh; char *
0x180076ad8  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180076add  lea     rcx, [rbp+57h+var_C0]
0x180076ae1  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCOMServerEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(void)
0x180076ae6  xor     r14d, r14d
0x180076ae9  test    edi, edi
0x180076aeb  jz      loc_180076869
0x180076af1  mov     rcx, [rsi+r14*8]
0x180076af5  test    rcx, rcx
0x180076af8  jz      short loc_180076B06
0x180076afa  mov     rax, [rcx]
0x180076afd  mov     rax, [rax+10h]
0x180076b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b06  inc     r14d
0x180076b09  cmp     r14d, edi
0x180076b0c  jb      short loc_180076AF1
0x180076b0e  jmp     loc_180076869
0x180076b13  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180076b19  jnz     short loc_180076B21
0x180076b1b  call    cs:__imp_DebugBreak
0x180076b21  mov     r9d, ebx; int
0x180076b24  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076b2b  mov     r8d, 533Ch; char *
0x180076b31  lea     rcx, aStatusPropagat; "Status propagated"
0x180076b38  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180076b3d  mov     ecx, ebx; this
0x180076b3f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180076b44  lea     rcx, [rbp+57h+var_C0]
0x180076b48  mov     ebx, eax
0x180076b4a  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCOMServerEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(void)
0x180076b4f  xor     r14d, r14d
0x180076b52  test    edi, edi
0x180076b54  jz      loc_180076869
0x180076b5a  mov     rcx, [rsi+r14*8]
0x180076b5e  test    rcx, rcx
0x180076b61  jz      short loc_180076B6F
0x180076b63  mov     rax, [rcx]
0x180076b66  mov     rax, [rax+10h]
0x180076b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b6f  inc     r14d
0x180076b72  cmp     r14d, edi
0x180076b75  jb      short loc_180076B5A
0x180076b77  jmp     loc_180076869
0x180076b7c  mov     r8d, eax; int
0x180076b7f  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076b86  mov     edx, 533Bh; char *
0x180076b8b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180076b90  lea     rcx, [rbp+57h+var_C0]
0x180076b94  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCOMServerEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(void)
0x180076b99  xor     r14d, r14d
0x180076b9c  test    edi, edi
0x180076b9e  jz      loc_180076869
0x180076ba4  mov     rcx, [rsi+r14*8]
0x180076ba8  test    rcx, rcx
0x180076bab  jz      short loc_180076BB9
0x180076bad  mov     rax, [rcx]
0x180076bb0  mov     rax, [rax+10h]
0x180076bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076bb9  inc     r14d
0x180076bbc  cmp     r14d, edi
0x180076bbf  jb      short loc_180076BA4
0x180076bc1  jmp     loc_180076869
0x180076bc6  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180076bcc  jnz     short loc_180076BD4
0x180076bce  call    cs:__imp_DebugBreak
0x180076bd4  mov     r9d, ebx; int
0x180076bd7  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180076bde  mov     r8d, 5339h; char *
0x180076be4  lea     rcx, aStatusPropagat; "Status propagated"
0x180076beb  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180076bf0  mov     ecx, ebx; this
0x180076bf2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180076bf7  lea     rcx, [rbp+57h+var_C0]
0x180076bfb  mov     ebx, eax
0x180076bfd  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCOMServerEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCOMServerEntry>>>(void)
0x180076c02  xor     r14d, r14d
0x180076c05  test    edi, edi
0x180076c07  jz      loc_180076869
0x180076c0d  mov     rcx, [rsi+r14*8]
0x180076c11  test    rcx, rcx
0x180076c14  jz      short loc_180076C22
0x180076c16  mov     rax, [rcx]
0x180076c19  mov     rax, [rax+10h]
0x180076c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c22  inc     r14d
0x180076c25  cmp     r14d, edi
0x180076c28  jb      short loc_180076C0D
0x180076c2a  jmp     loc_180076869
0x180076c2f  mov     [r15], r14d
0x180076c32  lea     rcx, [rbp+57h+var_B8]
  ... truncated ...
```
