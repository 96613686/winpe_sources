# CEnumCounterSetSection::Next(ulong,IUnknown * *,ulong *)

- ea: `0x180078130`
- end: `0x18007862e`
- name: `?Next@CEnumCounterSetSection@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1278`
- prototype: `__int64 __fastcall(CEnumCounterSetSection *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
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
- `0x180057f18`
- `0x18005abf4`
- `0x18005de44`
- `0x1800678a4`
- `0x180078130`
- `0x1800d552c`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180078235`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800782bd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007843f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800784bb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007856e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180078235`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800782bd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007843f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800784bb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007856e`

## string_xrefs

- `0x180078168`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007823e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800782c6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180078396`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007844b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007846c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800784c4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18007851f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180078577`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCounterSetSection::Next(
        CEnumCounterSetSection *this,
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
  CEnumCounterSetSection *v49; // [rsp+68h] [rbp-21h]
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
    DWORD2(v46) = 23309;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v46,
      &v46);
    return v47;
  }
  if ( !a3 )
  {
    DWORD2(v46) = 23310;
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
            v24 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::Allocate(
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
            v26 = CCounterSetEntry::Initialize(v43, *((_QWORD *)v49 + 2), v25, &v46);
            n = v26;
            if ( v26 < 0 )
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whid"
                                               "bey\\objfre\\amd64\\com_cms.cpp",
                (const char *)0x5B1E,
                v26,
                v27);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(&v43);
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
                (const char *)0x5B1F,
                v29,
                (unsigned int)v43);
              n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                    (Windows::ErrorHandling::COM *)(unsigned int)v29,
                    v34);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(&v43);
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
                (const char *)0x5B20,
                v30,
                v31);
              BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(&v43);
              for ( k = 0; (unsigned int)k < (unsigned int)v5; k = (unsigned int)(k + 1) )
              {
                v33 = a3[k];
                if ( v33 )
                  ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
              }
              goto LABEL_10;
            }
            v43 = 0;
            BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(&v43);
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v22 )
              goto LABEL_42;
          }
          if ( v24 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x5B1C,
            v24,
            (unsigned int)v43);
          n = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v24,
                v39);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(&v43);
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
              (const char *)0x5B28,
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
          (const char *)0x5B14,
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
        (const char *)0x5B13,
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
    Windows::ErrorHandling::COM::ReportErrorOrigination(v9, (const char *)0x5B0F, -2147467261, v8);
  }
LABEL_10:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned long>,BCL::Nt::CCallDisposition>(&v44);
  return n;
}

```

## disassembly

```asm
0x180078130  push    rbp
0x180078132  push    rbx
0x180078133  push    rsi
0x180078134  push    rdi
0x180078135  push    r12
0x180078137  push    r13
0x180078139  push    r14
0x18007813b  push    r15
0x18007813d  lea     rbp, [rsp-1Fh]
0x180078142  sub     rsp, 0A8h
0x180078149  mov     rax, cs:__security_cookie
0x180078150  xor     rax, rsp
0x180078153  mov     [rbp+57h+var_50], rax
0x180078157  xor     r13d, r13d
0x18007815a  mov     [rbp+57h+var_78], rcx
0x18007815e  mov     rsi, r8
0x180078161  mov     edi, edx
0x180078163  mov     r12, rcx
0x180078166  mov     edx, edx
0x180078168  lea     r11, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007816f  mov     [rbp+57h+var_90], 8007054Fh
0x180078176  xorps   xmm0, xmm0
0x180078179  mov     qword ptr [rbp+57h+var_A0], r11
0x18007817d  mov     rcx, rsi
0x180078180  mov     [rbp+57h+var_C0], r13
0x180078184  lea     r8, [rbp+57h+var_80]
0x180078188  mov     [rbp+57h+var_A8], r13
0x18007818c  mov     r15, r9
0x18007818f  mov     [rbp+57h+var_80], r13
0x180078193  movdqu  [rbp+57h+var_B8], xmm0
0x180078198  call    ??$InitializeOutParameterArray@PEAUIUnknown@@@Com@IsolationImplementation@@YAXPEAPEAUIUnknown@@_KAEBQEAU2@@Z; IsolationImplementation::Com::InitializeOutParameterArray<IUnknown *>(IUnknown * *,unsigned __int64,IUnknown * const &)
0x18007819d  test    r15, r15
0x1800781a0  jz      short loc_1800781A5
0x1800781a2  mov     [r15], r13d
0x1800781a5  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800781ac  test    rdx, rdx
0x1800781af  jz      loc_1800785EC
0x1800781b5  mov     rcx, [r12+18h]
0x1800781ba  call    RtlIsTypeSafeHandleValid
0x1800781bf  test    al, al
0x1800781c1  jz      loc_1800785EC
0x1800781c7  test    rsi, rsi
0x1800781ca  jnz     short loc_1800781EA
0x1800781cc  lea     rcx, [rbp+57h+var_A0]
0x1800781d0  mov     dword ptr [rbp+57h+var_A0+8], 5B0Eh
0x1800781d7  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800781dc  lea     rcx, [rbp+57h+var_B8]
0x1800781e0  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x1800781e5  jmp     loc_180078609
0x1800781ea  test    r15, r15
0x1800781ed  jnz     short loc_180078217
0x1800781ef  cmp     edi, 1
0x1800781f2  jz      short loc_180078217
0x1800781f4  mov     ebx, 80004003h
0x1800781f9  mov     edx, 5B0Fh; char *
0x1800781fe  mov     r8d, ebx; int
0x180078201  mov     rcx, r11; this
0x180078204  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180078209  lea     rcx, [rbp+57h+var_B8]
0x18007820d  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>,BCL::Nt::CCallDisposition>(void)
0x180078212  jmp     loc_18007860C
0x180078217  mov     r8d, edi
0x18007821a  lea     rdx, [rbp+57h+var_80]
0x18007821e  lea     rcx, [rbp+57h+var_B8]
0x180078222  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@KU_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@V?$CDefaultObjectTraits@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@Rtl@Cdf@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@K@Z; BCL::Nt::CSmartArrayHolder<ulong,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::CDefaultObjectTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<ulong>>::EnlargeNoPreserve(ulong)
0x180078227  mov     ebx, [rax]
0x180078229  test    ebx, ebx
0x18007822b  jns     short loc_180078289
0x18007822d  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180078233  jnz     short loc_18007823B
0x180078235  call    cs:__imp_DebugBreak
0x18007823b  mov     r9d, ebx; int
0x18007823e  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180078245  mov     r8d, 5B13h; char *
0x18007824b  lea     rcx, aStatusPropagat; "Status propagated"
0x180078252  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180078257  mov     ecx, ebx; this
0x180078259  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18007825e  mov     ebx, eax
0x180078260  mov     r14d, r13d
0x180078263  test    edi, edi
0x180078265  jz      short loc_180078209
0x180078267  mov     ecx, r14d
0x18007826a  mov     rcx, [rsi+rcx*8]
0x18007826e  test    rcx, rcx
0x180078271  jz      short loc_18007827F
0x180078273  mov     rdx, [rcx]
0x180078276  mov     rax, [rdx+10h]
0x18007827a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007827f  inc     r14d
0x180078282  cmp     r14d, edi
0x180078285  jb      short loc_180078267
0x180078287  jmp     short loc_180078209
0x180078289  mov     r13d, dword ptr [rbp+57h+var_A8+4]
0x18007828d  lea     r9, [rbp+57h+var_C0]
0x180078291  cmp     r13d, dword ptr [rbp+57h+var_A8]
0x180078295  mov     rdx, rdi
0x180078298  mov     r8, qword ptr [rbp+57h+var_B8+8]
0x18007829c  cmovb   r13d, dword ptr [rbp+57h+var_A8]
0x1800782a1  mov     rcx, [r12+18h]
0x1800782a6  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x1800782aa  call    CdfFetchGuidTableEnumeratorData
0x1800782af  mov     ebx, eax
0x1800782b1  test    eax, eax
0x1800782b3  jns     short loc_180078315
0x1800782b5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800782bb  jnz     short loc_1800782C3
0x1800782bd  call    cs:__imp_DebugBreak
0x1800782c3  mov     r9d, ebx; int
0x1800782c6  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800782cd  mov     r8d, 5B14h; char *
0x1800782d3  lea     rcx, aStatusPropagat; "Status propagated"
0x1800782da  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800782df  mov     ecx, ebx; this
0x1800782e1  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800782e6  xor     r14d, r14d
0x1800782e9  mov     ebx, eax
0x1800782eb  test    edi, edi
0x1800782ed  jz      loc_180078209
0x1800782f3  mov     rcx, [rsi+r14*8]
0x1800782f7  test    rcx, rcx
0x1800782fa  jz      short loc_180078308
0x1800782fc  mov     rax, [rcx]
0x1800782ff  mov     rax, [rax+10h]
0x180078303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078308  inc     r14d
0x18007830b  cmp     r14d, edi
0x18007830e  jb      short loc_1800782F3
0x180078310  jmp     loc_180078209
0x180078315  mov     r14, [rbp+57h+var_C0]
0x180078319  xor     r12d, r12d
0x18007831c  test    r14, r14
0x18007831f  jz      loc_18007841B
0x180078325  lea     rdx, [rbp+57h+var_80]
0x180078329  mov     [rbp+57h+var_C0], 0
0x180078331  lea     rcx, [rbp+57h+var_C0]
0x180078335  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterSetEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::Allocate(void)
0x18007833a  mov     ebx, [rax]
0x18007833c  test    ebx, ebx
0x18007833e  js      loc_180078566
0x180078344  mov     eax, dword ptr [rbp+57h+var_A8]
0x180078347  lea     r8, [r12+r12*4]
0x18007834b  mov     rcx, [rbp+57h+var_C0]
0x18007834f  lea     r9, [rbp+57h+var_A0]
0x180078353  cmp     r13d, eax
0x180078356  cmovb   r13d, eax
0x18007835a  cmp     r13d, eax
0x18007835d  cmovb   r13d, eax
0x180078361  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x180078365  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x180078369  movups  xmm0, xmmword ptr [rax+r8*4]
0x18007836e  mov     r8d, [rax+r8*4+10h]
0x180078373  mov     rax, [rbp+57h+var_78]
0x180078377  movdqu  [rbp+57h+var_A0], xmm0
0x18007837c  mov     rdx, [rax+10h]
0x180078380  call    ?Initialize@CCounterSetEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@U_GUID@@@Z; CCounterSetEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,_GUID)
0x180078385  mov     ebx, eax
0x180078387  test    eax, eax
0x180078389  js      loc_18007851C
0x18007838f  mov     dword ptr [rbp+57h+var_58], 0C00000E5h
0x180078396  lea     rax, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007839d  mov     [rbp+57h+var_68], rax
0x1800783a1  cmp     r12d, edi
0x1800783a4  jb      short loc_1800783CB
0x1800783a6  mov     qword ptr [rbp+57h+var_A0], 0
0x1800783ae  mov     [rbp+57h+var_60], 28h ; '('
0x1800783b5  lea     rdx, [rbp+57h+var_68]
0x1800783b9  lea     rcx, [rbp+57h+var_68]
0x1800783bd  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800783c2  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1800783c6  mov     ebx, dword ptr [rbp+57h+var_58]
0x1800783c9  jmp     short loc_1800783D1
0x1800783cb  lea     rcx, [rsi+r12*8]
0x1800783cf  xor     ebx, ebx
0x1800783d1  test    ebx, ebx
0x1800783d3  js      loc_1800784B3
0x1800783d9  mov     r9, [rbp+57h+var_C0]
0x1800783dd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800783e4  mov     r8, rcx
0x1800783e7  mov     rcx, r9
0x1800783ea  mov     rax, [r9]
0x1800783ed  mov     rax, [rax]
0x1800783f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800783f5  mov     ebx, eax
0x1800783f7  test    eax, eax
0x1800783f9  js      short loc_180078469
0x1800783fb  lea     rcx, [rbp+57h+var_C0]
0x1800783ff  mov     [rbp+57h+var_C0], 0
0x180078407  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterSetEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(void)
0x18007840c  inc     r12d
0x18007840f  mov     eax, r12d
0x180078412  cmp     rax, r14
0x180078415  jb      loc_180078325
0x18007841b  test    r15, r15
0x18007841e  jz      loc_1800785D2
0x180078424  mov     eax, 0FFFFFFFFh
0x180078429  cmp     r14, rax
0x18007842c  jbe     loc_1800785CF
0x180078432  mov     ebx, 0D0000095h
0x180078437  cmp     cs:?g_HRESULT_to_break_on@@3JA, ebx; long g_HRESULT_to_break_on
0x18007843d  jnz     short loc_180078445
0x18007843f  call    cs:__imp_DebugBreak
0x180078445  mov     r9d, 0D0000095h; int
0x18007844b  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180078452  mov     r8d, 5B28h; char *
0x180078458  lea     rcx, aHrOriginated; "HR originated"
0x18007845f  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180078464  jmp     loc_180078209
0x180078469  mov     r8d, eax; int
0x18007846c  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180078473  mov     edx, 5B20h; char *
0x180078478  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18007847d  lea     rcx, [rbp+57h+var_C0]
0x180078481  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterSetEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(void)
0x180078486  xor     r14d, r14d
0x180078489  test    edi, edi
0x18007848b  jz      loc_180078209
0x180078491  mov     rcx, [rsi+r14*8]
0x180078495  test    rcx, rcx
0x180078498  jz      short loc_1800784A6
0x18007849a  mov     rax, [rcx]
0x18007849d  mov     rax, [rax+10h]
0x1800784a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784a6  inc     r14d
0x1800784a9  cmp     r14d, edi
0x1800784ac  jb      short loc_180078491
0x1800784ae  jmp     loc_180078209
0x1800784b3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800784b9  jnz     short loc_1800784C1
0x1800784bb  call    cs:__imp_DebugBreak
0x1800784c1  mov     r9d, ebx; int
0x1800784c4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800784cb  mov     r8d, 5B1Fh; char *
0x1800784d1  lea     rcx, aStatusPropagat; "Status propagated"
0x1800784d8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800784dd  mov     ecx, ebx; this
0x1800784df  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800784e4  lea     rcx, [rbp+57h+var_C0]
0x1800784e8  mov     ebx, eax
0x1800784ea  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterSetEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(void)
0x1800784ef  xor     r14d, r14d
0x1800784f2  test    edi, edi
0x1800784f4  jz      loc_180078209
0x1800784fa  mov     rcx, [rsi+r14*8]
0x1800784fe  test    rcx, rcx
0x180078501  jz      short loc_18007850F
0x180078503  mov     rax, [rcx]
0x180078506  mov     rax, [rax+10h]
0x18007850a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007850f  inc     r14d
0x180078512  cmp     r14d, edi
0x180078515  jb      short loc_1800784FA
0x180078517  jmp     loc_180078209
0x18007851c  mov     r8d, eax; int
0x18007851f  lea     rcx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180078526  mov     edx, 5B1Eh; char *
0x18007852b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180078530  lea     rcx, [rbp+57h+var_C0]
0x180078534  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterSetEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(void)
0x180078539  xor     r14d, r14d
0x18007853c  test    edi, edi
0x18007853e  jz      loc_180078209
0x180078544  mov     rcx, [rsi+r14*8]
0x180078548  test    rcx, rcx
0x18007854b  jz      short loc_180078559
0x18007854d  mov     rax, [rcx]
0x180078550  mov     rax, [rax+10h]
0x180078554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078559  inc     r14d
0x18007855c  cmp     r14d, edi
0x18007855f  jb      short loc_180078544
0x180078561  jmp     loc_180078209
0x180078566  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18007856c  jnz     short loc_180078574
0x18007856e  call    cs:__imp_DebugBreak
0x180078574  mov     r9d, ebx; int
0x180078577  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18007857e  mov     r8d, 5B1Ch; char *
0x180078584  lea     rcx, aStatusPropagat; "Status propagated"
0x18007858b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180078590  mov     ecx, ebx; this
0x180078592  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180078597  lea     rcx, [rbp+57h+var_C0]
0x18007859b  mov     ebx, eax
0x18007859d  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCounterSetEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCounterSetEntry>>>(void)
0x1800785a2  xor     r14d, r14d
0x1800785a5  test    edi, edi
0x1800785a7  jz      loc_180078209
0x1800785ad  mov     rcx, [rsi+r14*8]
0x1800785b1  test    rcx, rcx
0x1800785b4  jz      short loc_1800785C2
0x1800785b6  mov     rax, [rcx]
0x1800785b9  mov     rax, [rax+10h]
0x1800785bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800785c2  inc     r14d
0x1800785c5  cmp     r14d, edi
0x1800785c8  jb      short loc_1800785AD
0x1800785ca  jmp     loc_180078209
0x1800785cf  mov     [r15], r14d
0x1800785d2  lea     rcx, [rbp+57h+var_B8]
  ... truncated ...
```
