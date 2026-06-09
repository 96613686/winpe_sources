# CAssemblyReferenceSection::Lookup(IReferenceIdentity *,IUnknown * *)

- ea: `0x18006ece0`
- end: `0x18006f1fb`
- name: `?Lookup@CAssemblyReferenceSection@@UEAAJPEAUIReferenceIdentity@@PEAPEAUIUnknown@@@Z`
- size: `1307`
- prototype: `int(CAssemblyReferenceSection *__hidden this, struct IReferenceIdentity *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012538`
- `0x180012910`
- `0x180012acc`
- `0x180012b38`
- `0x180013fd4`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18002e7b8`
- `0x18003094c`
- `0x180044708`
- `0x18004f2dc`
- `0x180057b28`
- `0x18005a134`
- `0x18006696c`
- `0x18006ece0`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ee6a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006efaf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ee6a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006efaf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ef77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ef77`

## string_xrefs

- `0x18006ed1a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006efb8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006f151`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CAssemblyReferenceSection::Lookup(
        CAssemblyReferenceSection *this,
        __int64 (__fastcall ***a2)(IsolationImplementation::Com *, GUID *, __int64 *),
        struct IUnknown **a3)
{
  void (__fastcall *v6)(LPVOID *); // rax
  HANDLE v7; // rax
  LPVOID *v8; // rbx
  void (__fastcall *v9)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v11; // rbx
  unsigned int v12; // esi
  int v13; // ebx
  struct Windows::Isolation::Rtl::_REFERENCE_IDENTITY *v14; // r8
  int v15; // edx
  unsigned int v16; // eax
  LPVOID *v17; // rbx
  void (__fastcall *v18)(LPVOID *); // rax
  HANDLE v19; // rax
  int v20; // eax
  int v21; // r9d
  void (__fastcall *v22)(LPVOID *); // rax
  HANDLE v23; // rax
  LPVOID *v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // edi
  int v29; // edx
  void (__fastcall *v30)(LPVOID *); // rax
  HANDLE v31; // rax
  LPVOID *v32; // rbx
  void (__fastcall *v33)(LPVOID *); // rax
  HANDLE v34; // rax
  LPVOID *v35; // rbx
  void (__fastcall *v36)(LPVOID *); // rax
  HANDLE v37; // rax
  LPVOID *v38; // rbx
  __int64 (__fastcall ***v39)(_QWORD, GUID *, struct IUnknown **); // rdi
  int v40; // eax
  int v41; // r9d
  __int64 v42; // rdx
  LPVOID lpMem[2]; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, struct IUnknown **); // [rsp+30h] [rbp-50h] BYREF
  const char *v46; // [rsp+38h] [rbp-48h] BYREF
  int v47; // [rsp+40h] [rbp-40h]
  unsigned int v48; // [rsp+48h] [rbp-38h]
  __int64 v49; // [rsp+50h] [rbp-30h] BYREF
  char v50[8]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v51; // [rsp+60h] [rbp-20h] BYREF

  v48 = -2147023537;
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v45 = 0;
  v49 = 0;
  v51 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      v47 = 6128;
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v46);
      while ( 1 )
      {
        v11 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v11 == lpMem )
          break;
        v9 = (void (__fastcall *)(LPVOID *))v11[2];
        if ( v9 )
          v9(v11 + 3);
        ProcessHeap_0 = GetProcessHeap_0();
        HeapFree_0(ProcessHeap_0, 0, v11);
      }
      goto LABEL_16;
    }
    if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 2)) )
    {
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
      {
        v13 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::Allocate(
                           &v45,
                           v50);
        if ( v13 < 0 )
        {
          if ( v13 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x17F4,
            v13,
            (unsigned int)lpMem[0]);
          v16 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                  (Windows::ErrorHandling::COM *)(unsigned int)v13,
                  v15);
          v17 = (LPVOID *)lpMem[0];
          v12 = v16;
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          while ( v17 != lpMem )
          {
            v18 = (void (__fastcall *)(LPVOID *))v17[2];
            if ( v18 )
              v18(v17 + 3);
            v19 = GetProcessHeap_0();
            HeapFree_0(v19, 0, v17);
            v17 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
          }
          goto LABEL_51;
        }
        v20 = IsolationImplementation::Com::ConvertIn(a2, (struct IReferenceIdentity *)&v49, v14);
        v12 = v20;
        if ( v20 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x17F5,
            v20,
            v21);
          if ( v49 )
            RtlCloseReferenceIdentityHandle(v49);
          while ( 1 )
          {
            v24 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v24 == lpMem )
              break;
            v22 = (void (__fastcall *)(LPVOID *))v24[2];
            if ( v22 )
              v22(v24 + 3);
            v23 = GetProcessHeap_0();
            HeapFree_0(v23, 0, v24);
          }
          goto LABEL_51;
        }
        if ( (_DWORD)v51 )
          RaiseException(0xC00000E5, 1u, 0, 0);
        v25 = v49;
        v26 = *((_QWORD *)this + 3);
        LODWORD(v51) = 0;
        v27 = CCdfInternalGenericTableBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA,_CDF_IDENTITY_TABLE_BLOB_HEADER,Windows::Cdf::Rtl::_CDF_IDENTITYID>::PublicSearch<Windows::Isolation::Rtl::_REFERENCE_IDENTITY,Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE>>(
                v26,
                v49,
                &v51);
        v28 = 0;
        if ( v27 < 0 )
          v28 = v27;
        if ( v28 < 0 )
        {
          if ( v28 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x17F6,
            v28,
            (unsigned int)lpMem[0]);
          v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                  (Windows::ErrorHandling::COM *)(unsigned int)v28,
                  v29);
          if ( v25 )
            RtlCloseReferenceIdentityHandle(v25);
          while ( 1 )
          {
            v32 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v32 == lpMem )
              break;
            v30 = (void (__fastcall *)(LPVOID *))v32[2];
            if ( v30 )
              v30(v32 + 3);
            v31 = GetProcessHeap_0();
            HeapFree_0(v31, 0, v32);
          }
          goto LABEL_51;
        }
        if ( !(_DWORD)v51 )
        {
          v47 = 6135;
          if ( v25 )
            RtlCloseReferenceIdentityHandle(v25);
          while ( 1 )
          {
            v35 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v35 == lpMem )
              break;
            v33 = (void (__fastcall *)(LPVOID *))v35[2];
            if ( v33 )
              v33(v35 + 3);
            v34 = GetProcessHeap_0();
            HeapFree_0(v34, 0, v35);
          }
          Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v51);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v45);
          Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v46);
          return v48;
        }
        if ( (_DWORD)v51 != 1 )
        {
          v47 = 6136;
          if ( v25 )
            RtlCloseReferenceIdentityHandle(v25);
          while ( 1 )
          {
            v38 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v38 == lpMem )
              break;
            v36 = (void (__fastcall *)(LPVOID *))v38[2];
            if ( v36 )
              v36(v38 + 3);
            v37 = GetProcessHeap_0();
            HeapFree_0(v37, 0, v38);
          }
          goto LABEL_79;
        }
        ((void (__fastcall *)(__int64 (__fastcall ***)(IsolationImplementation::Com *, GUID *, __int64 *)))(*a2)[1])(a2);
        v39 = v45;
        v40 = CAssemblyReferenceEntry::Initialize(v45, *((_QWORD *)this + 2), DWORD2(v51), a2);
        v12 = v40;
        if ( v40 >= 0 )
        {
          v40 = (**v39)(v39, &GUID_00000000_0000_0000_c000_000000000046, a3);
          v12 = v40;
          if ( v40 >= 0 )
          {
            v45 = 0;
            v12 = 0;
            goto LABEL_74;
          }
          v42 = 6139;
        }
        else
        {
          v42 = 6138;
        }
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\o"
                                         "bjfre\\amd64\\com_cms.cpp",
          (const char *)v42,
          v40,
          v41);
LABEL_74:
        if ( v25 )
          RtlCloseReferenceIdentityHandle(v25);
        Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
        goto LABEL_51;
      }
      v47 = 6130;
    }
    else
    {
      v47 = 6129;
    }
LABEL_79:
    Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v51);
    BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v45);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v46,
      &v46);
    return v48;
  }
  v47 = 6127;
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v46);
  while ( 1 )
  {
    v8 = (LPVOID *)lpMem[0];
    lpMem[0] = *(LPVOID *)lpMem[0];
    *((_QWORD *)lpMem[0] + 1) = lpMem;
    if ( v8 == lpMem )
      break;
    v6 = (void (__fastcall *)(LPVOID *))v8[2];
    if ( v6 )
      v6(v8 + 3);
    v7 = GetProcessHeap_0();
    HeapFree_0(v7, 0, v8);
  }
LABEL_16:
  v12 = v48;
LABEL_51:
  Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v51);
  BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(&v45);
  return v12;
}

```

## disassembly

```asm
0x18006ece0  push    rbp
0x18006ece2  push    rbx
0x18006ece3  push    rsi
0x18006ece4  push    rdi
0x18006ece5  push    r13
0x18006ece7  push    r14
0x18006ece9  push    r15
0x18006eceb  mov     rbp, rsp
0x18006ecee  sub     rsp, 80h
0x18006ecf5  mov     rax, cs:__security_cookie
0x18006ecfc  xor     rax, rsp
0x18006ecff  mov     [rbp+var_10], rax
0x18006ed03  mov     [rbp+var_38], 8007054Fh
0x18006ed0a  lea     rax, [rbp+lpMem]
0x18006ed0e  mov     [rbp+var_58], rax
0x18006ed12  lea     rax, [rbp+lpMem]
0x18006ed16  mov     [rbp+lpMem], rax
0x18006ed1a  lea     rdi, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006ed21  mov     [rbp+var_48], rdi
0x18006ed25  xorps   xmm0, xmm0
0x18006ed28  mov     [rbp+var_50], 0
0x18006ed30  mov     r14, r8
0x18006ed33  mov     [rbp+var_30], 0
0x18006ed3b  mov     r15, rdx
0x18006ed3e  mov     r13, rcx
0x18006ed41  movups  [rbp+var_20], xmm0
0x18006ed45  test    r8, r8
0x18006ed48  jz      short loc_18006ED51
0x18006ed4a  mov     qword ptr [r8], 0
0x18006ed51  test    r15, r15
0x18006ed54  jnz     short loc_18006EDAA
0x18006ed56  lea     rcx, [rbp+var_48]
0x18006ed5a  mov     [rbp+var_40], 17EFh
0x18006ed61  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18006ed66  jmp     short loc_18006ED8C
0x18006ed68  mov     rax, [rbx+10h]
0x18006ed6c  test    rax, rax
0x18006ed6f  jz      short loc_18006ED7A
0x18006ed71  lea     rcx, [rbx+18h]
0x18006ed75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed7a  call    GetProcessHeap_0
0x18006ed7f  mov     r8, rbx; lpMem
0x18006ed82  xor     edx, edx; dwFlags
0x18006ed84  mov     rcx, rax; hHeap
0x18006ed87  call    HeapFree_0
0x18006ed8c  mov     rbx, [rbp+lpMem]
0x18006ed90  lea     rcx, [rbp+lpMem]
0x18006ed94  mov     rax, [rbx]
0x18006ed97  mov     [rbp+lpMem], rax
0x18006ed9b  mov     [rax+8], rcx
0x18006ed9f  lea     rax, [rbp+lpMem]
0x18006eda3  cmp     rbx, rax
0x18006eda6  jnz     short loc_18006ED68
0x18006eda8  jmp     short loc_18006EE01
0x18006edaa  test    r14, r14
0x18006edad  jnz     short loc_18006EE09
0x18006edaf  lea     rcx, [rbp+var_48]
0x18006edb3  mov     [rbp+var_40], 17F0h
0x18006edba  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18006edbf  jmp     short loc_18006EDE5
0x18006edc1  mov     rax, [rbx+10h]
0x18006edc5  test    rax, rax
0x18006edc8  jz      short loc_18006EDD3
0x18006edca  lea     rcx, [rbx+18h]
0x18006edce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006edd3  call    GetProcessHeap_0
0x18006edd8  mov     r8, rbx; lpMem
0x18006eddb  xor     edx, edx; dwFlags
0x18006eddd  mov     rcx, rax; hHeap
0x18006ede0  call    HeapFree_0
0x18006ede5  mov     rbx, [rbp+lpMem]
0x18006ede9  lea     rcx, [rbp+lpMem]
0x18006eded  mov     rax, [rbx]
0x18006edf0  mov     [rbp+lpMem], rax
0x18006edf4  mov     [rax+8], rcx
0x18006edf8  lea     rax, [rbp+lpMem]
0x18006edfc  cmp     rbx, rax
0x18006edff  jnz     short loc_18006EDC1
0x18006ee01  mov     esi, [rbp+var_38]
0x18006ee04  jmp     loc_18006F029
0x18006ee09  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18006ee10  test    rdx, rdx
0x18006ee13  jz      loc_18006F1B2
0x18006ee19  mov     rcx, [rcx+10h]
0x18006ee1d  call    RtlIsTypeSafeHandleValid
0x18006ee22  test    al, al
0x18006ee24  jz      loc_18006F1B2
0x18006ee2a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18006ee31  test    rdx, rdx
0x18006ee34  jz      loc_18006F1A9
0x18006ee3a  mov     rcx, [r13+18h]
0x18006ee3e  call    RtlIsTypeSafeHandleValid
0x18006ee43  test    al, al
0x18006ee45  jz      loc_18006F1A9
0x18006ee4b  lea     rdx, [rbp+var_28]
0x18006ee4f  lea     rcx, [rbp+var_50]
0x18006ee53  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::Allocate(void)
0x18006ee58  mov     ebx, [rax]
0x18006ee5a  test    ebx, ebx
0x18006ee5c  jns     loc_18006EEEB
0x18006ee62  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006ee68  jnz     short loc_18006EE70
0x18006ee6a  call    cs:__imp_DebugBreak
0x18006ee70  mov     r9d, ebx; int
0x18006ee73  lea     rcx, aStatusPropagat; "Status propagated"
0x18006ee7a  mov     r8d, 17F4h; char *
0x18006ee80  mov     rdx, rdi; char *
0x18006ee83  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006ee88  mov     ecx, ebx; this
0x18006ee8a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006ee8f  mov     rbx, [rbp+lpMem]
0x18006ee93  mov     esi, eax
0x18006ee95  lea     rax, [rbp+lpMem]
0x18006ee99  mov     rcx, [rbx]
0x18006ee9c  mov     [rbp+lpMem], rcx
0x18006eea0  mov     [rcx+8], rax
0x18006eea4  jmp     short loc_18006EEDD
0x18006eea6  mov     rax, [rbx+10h]
0x18006eeaa  test    rax, rax
0x18006eead  jz      short loc_18006EEB8
0x18006eeaf  lea     rcx, [rbx+18h]
0x18006eeb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eeb8  call    GetProcessHeap_0
0x18006eebd  mov     r8, rbx; lpMem
0x18006eec0  xor     edx, edx; dwFlags
0x18006eec2  mov     rcx, rax; hHeap
0x18006eec5  call    HeapFree_0
0x18006eeca  mov     rbx, [rbp+lpMem]
0x18006eece  lea     rcx, [rbp+lpMem]
0x18006eed2  mov     rax, [rbx]
0x18006eed5  mov     [rbp+lpMem], rax
0x18006eed9  mov     [rax+8], rcx
0x18006eedd  lea     rax, [rbp+lpMem]
0x18006eee1  cmp     rbx, rax
0x18006eee4  jnz     short loc_18006EEA6
0x18006eee6  jmp     loc_18006F029
0x18006eeeb  lea     rdx, [rbp+var_30]; struct IReferenceIdentity *
0x18006eeef  mov     rcx, r15; this
0x18006eef2  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIReferenceIdentity@@PEAU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IReferenceIdentity *,Windows::Isolation::Rtl::_REFERENCE_IDENTITY *)
0x18006eef7  mov     esi, eax
0x18006eef9  test    eax, eax
0x18006eefb  jns     short loc_18006EF62
0x18006eefd  mov     r8d, eax; int
0x18006ef00  mov     edx, 17F5h; char *
0x18006ef05  mov     rcx, rdi; this
0x18006ef08  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18006ef0d  mov     rcx, [rbp+var_30]
0x18006ef11  test    rcx, rcx
0x18006ef14  jz      short loc_18006EF41
0x18006ef16  call    RtlCloseReferenceIdentityHandle
0x18006ef1b  jmp     short loc_18006EF41
0x18006ef1d  mov     rax, [rbx+10h]
0x18006ef21  test    rax, rax
0x18006ef24  jz      short loc_18006EF2F
0x18006ef26  lea     rcx, [rbx+18h]
0x18006ef2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef2f  call    GetProcessHeap_0
0x18006ef34  mov     r8, rbx; lpMem
0x18006ef37  xor     edx, edx; dwFlags
0x18006ef39  mov     rcx, rax; hHeap
0x18006ef3c  call    HeapFree_0
0x18006ef41  mov     rbx, [rbp+lpMem]
0x18006ef45  lea     rcx, [rbp+lpMem]
0x18006ef49  mov     rax, [rbx]
0x18006ef4c  mov     [rbp+lpMem], rax
0x18006ef50  mov     [rax+8], rcx
0x18006ef54  lea     rax, [rbp+lpMem]
0x18006ef58  cmp     rbx, rax
0x18006ef5b  jnz     short loc_18006EF1D
0x18006ef5d  jmp     loc_18006F029
0x18006ef62  cmp     dword ptr [rbp+var_20], 0
0x18006ef66  jz      short loc_18006EF7D
0x18006ef68  xor     r9d, r9d; lpArguments
0x18006ef6b  xor     r8d, r8d; nNumberOfArguments
0x18006ef6e  mov     ecx, 0C00000E5h; dwExceptionCode
0x18006ef73  lea     edx, [r9+1]; dwExceptionFlags
0x18006ef77  call    cs:__imp_RaiseException
0x18006ef7d  mov     rbx, [rbp+var_30]
0x18006ef81  lea     r8, [rbp+var_20]
0x18006ef85  mov     rcx, [r13+18h]
0x18006ef89  mov     rdx, rbx
0x18006ef8c  mov     dword ptr [rbp+var_20], 0
0x18006ef93  call    ??$PublicSearch@U_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@V?$CTypeSafeHandlePointer@U_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE@@@2Provider@TypeSafeHandle@4@@?$CCdfInternalGenericTableBaseClass@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@U_CDF_IDENTITY_TABLE_BLOB_HEADER@@U_CDF_IDENTITYID@234@@@SAJU_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_REFERENCE_IDENTITY@2Isolation@4@PEAU_CDF_VALUE@234@@Z; CCdfInternalGenericTableBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA,_CDF_IDENTITY_TABLE_BLOB_HEADER,Windows::Cdf::Rtl::_CDF_IDENTITYID>::PublicSearch<Windows::Isolation::Rtl::_REFERENCE_IDENTITY,Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE>>(Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Isolation::Rtl::_REFERENCE_IDENTITY,Windows::Cdf::Rtl::_CDF_VALUE *)
0x18006ef98  xor     edi, edi
0x18006ef9a  test    eax, eax
0x18006ef9c  cmovs   edi, eax
0x18006ef9f  test    edi, edi
0x18006efa1  jns     loc_18006F040
0x18006efa7  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006efad  jnz     short loc_18006EFB5
0x18006efaf  call    cs:__imp_DebugBreak
0x18006efb5  mov     r9d, edi; int
0x18006efb8  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006efbf  mov     r8d, 17F6h; char *
0x18006efc5  lea     rcx, aStatusPropagat; "Status propagated"
0x18006efcc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006efd1  mov     ecx, edi; this
0x18006efd3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006efd8  mov     esi, eax
0x18006efda  test    rbx, rbx
0x18006efdd  jz      short loc_18006F00D
0x18006efdf  mov     rcx, rbx
0x18006efe2  call    RtlCloseReferenceIdentityHandle
0x18006efe7  jmp     short loc_18006F00D
0x18006efe9  mov     rax, [rbx+10h]
0x18006efed  test    rax, rax
0x18006eff0  jz      short loc_18006EFFB
0x18006eff2  lea     rcx, [rbx+18h]
0x18006eff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006effb  call    GetProcessHeap_0
0x18006f000  mov     r8, rbx; lpMem
0x18006f003  xor     edx, edx; dwFlags
0x18006f005  mov     rcx, rax; hHeap
0x18006f008  call    HeapFree_0
0x18006f00d  mov     rbx, [rbp+lpMem]
0x18006f011  lea     rcx, [rbp+lpMem]
0x18006f015  mov     rax, [rbx]
0x18006f018  mov     [rbp+lpMem], rax
0x18006f01c  mov     [rax+8], rcx
0x18006f020  lea     rax, [rbp+lpMem]
0x18006f024  cmp     rbx, rax
0x18006f027  jnz     short loc_18006EFE9
0x18006f029  lea     rcx, [rbp+var_20]; this
0x18006f02d  call    ??1CCDF_VALUE@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE(void)
0x18006f032  lea     rcx, [rbp+var_50]
0x18006f036  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(void)
0x18006f03b  jmp     loc_18006F1DB
0x18006f040  mov     eax, dword ptr [rbp+var_20]
0x18006f043  test    eax, eax
0x18006f045  jnz     short loc_18006F0BD
0x18006f047  mov     [rbp+var_40], 17F7h
0x18006f04e  test    rbx, rbx
0x18006f051  jz      short loc_18006F081
0x18006f053  mov     rcx, rbx
0x18006f056  call    RtlCloseReferenceIdentityHandle
0x18006f05b  jmp     short loc_18006F081
0x18006f05d  mov     rax, [rbx+10h]
0x18006f061  test    rax, rax
0x18006f064  jz      short loc_18006F06F
0x18006f066  lea     rcx, [rbx+18h]
0x18006f06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f06f  call    GetProcessHeap_0
0x18006f074  mov     r8, rbx; lpMem
0x18006f077  xor     edx, edx; dwFlags
0x18006f079  mov     rcx, rax; hHeap
0x18006f07c  call    HeapFree_0
0x18006f081  mov     rbx, [rbp+lpMem]
0x18006f085  lea     rcx, [rbp+lpMem]
0x18006f089  mov     rax, [rbx]
0x18006f08c  mov     [rbp+lpMem], rax
0x18006f090  mov     [rax+8], rcx
0x18006f094  lea     rax, [rbp+lpMem]
0x18006f098  cmp     rbx, rax
0x18006f09b  jnz     short loc_18006F05D
0x18006f09d  lea     rcx, [rbp+var_20]; this
0x18006f0a1  call    ??1CCDF_VALUE@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE(void)
0x18006f0a6  lea     rcx, [rbp+var_50]
0x18006f0aa  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCAssemblyReferenceEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CAssemblyReferenceEntry>>>(void)
0x18006f0af  lea     rcx, [rbp+var_48]
0x18006f0b3  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x18006f0b8  jmp     loc_18006F1D8
0x18006f0bd  cmp     eax, 1
0x18006f0c0  jz      short loc_18006F11D
0x18006f0c2  mov     [rbp+var_40], 17F8h
0x18006f0c9  test    rbx, rbx
0x18006f0cc  jz      short loc_18006F0FC
0x18006f0ce  mov     rcx, rbx
0x18006f0d1  call    RtlCloseReferenceIdentityHandle
0x18006f0d6  jmp     short loc_18006F0FC
0x18006f0d8  mov     rax, [rbx+10h]
0x18006f0dc  test    rax, rax
0x18006f0df  jz      short loc_18006F0EA
0x18006f0e1  lea     rcx, [rbx+18h]
0x18006f0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f0ea  call    GetProcessHeap_0
0x18006f0ef  mov     r8, rbx; lpMem
0x18006f0f2  xor     edx, edx; dwFlags
0x18006f0f4  mov     rcx, rax; hHeap
0x18006f0f7  call    HeapFree_0
0x18006f0fc  mov     rbx, [rbp+lpMem]
0x18006f100  lea     rcx, [rbp+lpMem]
0x18006f104  mov     rax, [rbx]
0x18006f107  mov     [rbp+lpMem], rax
0x18006f10b  mov     [rax+8], rcx
0x18006f10f  lea     rax, [rbp+lpMem]
0x18006f113  cmp     rbx, rax
0x18006f116  jnz     short loc_18006F0D8
0x18006f118  jmp     loc_18006F1B9
0x18006f11d  mov     rax, [r15]
0x18006f120  mov     rcx, r15
0x18006f123  mov     rax, [rax+8]
0x18006f127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f12c  mov     rdi, [rbp+var_50]
0x18006f130  mov     r9, r15
0x18006f133  mov     r8d, dword ptr [rbp+var_20+8]
0x18006f137  mov     rcx, rdi
0x18006f13a  mov     rdx, [r13+10h]
0x18006f13e  call    ?Initialize@CAssemblyReferenceEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEAUIReferenceIdentity@@@Z; CAssemblyReferenceEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,IReferenceIdentity *)
0x18006f143  mov     esi, eax
0x18006f145  test    eax, eax
  ... truncated ...
```
