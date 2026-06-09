# CCategoryMembershipSection::Lookup(IDefinitionIdentity *,IUnknown * *)

- ea: `0x18006fc10`
- end: `0x18007011f`
- name: `?Lookup@CCategoryMembershipSection@@UEAAJPEAUIDefinitionIdentity@@PEAPEAUIUnknown@@@Z`
- size: `1295`
- prototype: `int(CCategoryMembershipSection *__hidden this, struct IDefinitionIdentity *, struct IUnknown **)`
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
- `0x18002f55c`
- `0x180030674`
- `0x180043644`
- `0x18004f2dc`
- `0x180057d58`
- `0x18005a788`
- `0x180067200`
- `0x18006fc10`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006fd9a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006fed3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006fd9a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006fed3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006fea7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006fea7`

## string_xrefs

- `0x18006fc4a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006fedc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180070075`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCategoryMembershipSection::Lookup(
        CCategoryMembershipSection *this,
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
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v14; // r8
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
  int DefinitionIdentity; // eax
  unsigned int v27; // edi
  int v28; // edx
  void (__fastcall *v29)(LPVOID *); // rax
  HANDLE v30; // rax
  LPVOID *v31; // rbx
  void (__fastcall *v32)(LPVOID *); // rax
  HANDLE v33; // rax
  LPVOID *v34; // rbx
  void (__fastcall *v35)(LPVOID *); // rax
  HANDLE v36; // rax
  LPVOID *v37; // rbx
  __int64 (__fastcall ***v38)(_QWORD, GUID *, struct IUnknown **); // rdi
  int v39; // eax
  int v40; // r9d
  __int64 v41; // rdx
  LPVOID lpMem[2]; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, struct IUnknown **); // [rsp+30h] [rbp-50h] BYREF
  const char *v45; // [rsp+38h] [rbp-48h] BYREF
  int v46; // [rsp+40h] [rbp-40h]
  unsigned int v47; // [rsp+48h] [rbp-38h]
  __int64 v48; // [rsp+50h] [rbp-30h] BYREF
  char v49[8]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v50; // [rsp+60h] [rbp-20h] BYREF

  v47 = -2147023537;
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  v45 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v44 = 0;
  v48 = 0;
  v50 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      v46 = 5223;
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v45);
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
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
      {
        v13 = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::Allocate(
                           &v44,
                           v49);
        if ( v13 < 0 )
        {
          if ( v13 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x146B,
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
          goto LABEL_49;
        }
        v20 = IsolationImplementation::Com::ConvertIn(a2, (struct IDefinitionIdentity *)&v48, v14);
        v12 = v20;
        if ( v20 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\"
                                           "objfre\\amd64\\com_cms.cpp",
            (const char *)0x146C,
            v20,
            v21);
          if ( v48 )
            RtlCloseDefinitionIdentityHandle(v48);
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
          goto LABEL_49;
        }
        if ( (_DWORD)v50 )
          RaiseException(0xC00000E5, 1u, 0, 0);
        v25 = v48;
        DefinitionIdentity = CdfDefinitionIdentityTableFindDefinitionIdentity(*((_QWORD *)this + 3), v48, &v50);
        v27 = DefinitionIdentity;
        if ( DefinitionIdentity < 0 )
        {
          if ( DefinitionIdentity == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
            (const char *)0x146D,
            v27,
            (unsigned int)lpMem[0]);
          v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v27, v28);
          if ( v25 )
            RtlCloseDefinitionIdentityHandle(v25);
          while ( 1 )
          {
            v31 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v31 == lpMem )
              break;
            v29 = (void (__fastcall *)(LPVOID *))v31[2];
            if ( v29 )
              v29(v31 + 3);
            v30 = GetProcessHeap_0();
            HeapFree_0(v30, 0, v31);
          }
          goto LABEL_49;
        }
        if ( !(_DWORD)v50 )
        {
          v46 = 5230;
          if ( v25 )
            RtlCloseDefinitionIdentityHandle(v25);
          while ( 1 )
          {
            v34 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v34 == lpMem )
              break;
            v32 = (void (__fastcall *)(LPVOID *))v34[2];
            if ( v32 )
              v32(v34 + 3);
            v33 = GetProcessHeap_0();
            HeapFree_0(v33, 0, v34);
          }
          Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v50);
          BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v44);
          Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v45);
          return v47;
        }
        if ( (_DWORD)v50 != 1 )
        {
          v46 = 5231;
          if ( v25 )
            RtlCloseDefinitionIdentityHandle(v25);
          while ( 1 )
          {
            v37 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v37 == lpMem )
              break;
            v35 = (void (__fastcall *)(LPVOID *))v37[2];
            if ( v35 )
              v35(v37 + 3);
            v36 = GetProcessHeap_0();
            HeapFree_0(v36, 0, v37);
          }
          goto LABEL_77;
        }
        ((void (__fastcall *)(__int64 (__fastcall ***)(IsolationImplementation::Com *, GUID *, __int64 *)))(*a2)[1])(a2);
        v38 = v44;
        v39 = CCategoryMembershipEntry::Initialize(v44, *((_QWORD *)this + 2), DWORD2(v50), a2);
        v12 = v39;
        if ( v39 >= 0 )
        {
          v39 = (**v38)(v38, &GUID_00000000_0000_0000_c000_000000000046, a3);
          v12 = v39;
          if ( v39 >= 0 )
          {
            v44 = 0;
            v12 = 0;
            goto LABEL_72;
          }
          v41 = 5234;
        }
        else
        {
          v41 = 5233;
        }
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\o"
                                         "bjfre\\amd64\\com_cms.cpp",
          (const char *)v41,
          v39,
          v40);
LABEL_72:
        if ( v25 )
          RtlCloseDefinitionIdentityHandle(v25);
        Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
        goto LABEL_49;
      }
      v46 = 5225;
    }
    else
    {
      v46 = 5224;
    }
LABEL_77:
    Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v50);
    BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v44);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v45,
      &v45);
    return v47;
  }
  v46 = 5222;
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v45);
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
  v12 = v47;
LABEL_49:
  Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v50);
  BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(&v44);
  return v12;
}

```

## disassembly

```asm
0x18006fc10  push    rbp
0x18006fc12  push    rbx
0x18006fc13  push    rsi
0x18006fc14  push    rdi
0x18006fc15  push    r13
0x18006fc17  push    r14
0x18006fc19  push    r15
0x18006fc1b  mov     rbp, rsp
0x18006fc1e  sub     rsp, 80h
0x18006fc25  mov     rax, cs:__security_cookie
0x18006fc2c  xor     rax, rsp
0x18006fc2f  mov     [rbp+var_10], rax
0x18006fc33  mov     [rbp+var_38], 8007054Fh
0x18006fc3a  lea     rax, [rbp+lpMem]
0x18006fc3e  mov     [rbp+var_58], rax
0x18006fc42  lea     rax, [rbp+lpMem]
0x18006fc46  mov     [rbp+lpMem], rax
0x18006fc4a  lea     rdi, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006fc51  mov     [rbp+var_48], rdi
0x18006fc55  xorps   xmm0, xmm0
0x18006fc58  mov     [rbp+var_50], 0
0x18006fc60  mov     r14, r8
0x18006fc63  mov     [rbp+var_30], 0
0x18006fc6b  mov     r15, rdx
0x18006fc6e  mov     r13, rcx
0x18006fc71  movups  [rbp+var_20], xmm0
0x18006fc75  test    r8, r8
0x18006fc78  jz      short loc_18006FC81
0x18006fc7a  mov     qword ptr [r8], 0
0x18006fc81  test    r15, r15
0x18006fc84  jnz     short loc_18006FCDA
0x18006fc86  lea     rcx, [rbp+var_48]
0x18006fc8a  mov     [rbp+var_40], 1466h
0x18006fc91  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18006fc96  jmp     short loc_18006FCBC
0x18006fc98  mov     rax, [rbx+10h]
0x18006fc9c  test    rax, rax
0x18006fc9f  jz      short loc_18006FCAA
0x18006fca1  lea     rcx, [rbx+18h]
0x18006fca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcaa  call    GetProcessHeap_0
0x18006fcaf  mov     r8, rbx; lpMem
0x18006fcb2  xor     edx, edx; dwFlags
0x18006fcb4  mov     rcx, rax; hHeap
0x18006fcb7  call    HeapFree_0
0x18006fcbc  mov     rbx, [rbp+lpMem]
0x18006fcc0  lea     rcx, [rbp+lpMem]
0x18006fcc4  mov     rax, [rbx]
0x18006fcc7  mov     [rbp+lpMem], rax
0x18006fccb  mov     [rax+8], rcx
0x18006fccf  lea     rax, [rbp+lpMem]
0x18006fcd3  cmp     rbx, rax
0x18006fcd6  jnz     short loc_18006FC98
0x18006fcd8  jmp     short loc_18006FD31
0x18006fcda  test    r14, r14
0x18006fcdd  jnz     short loc_18006FD39
0x18006fcdf  lea     rcx, [rbp+var_48]
0x18006fce3  mov     [rbp+var_40], 1467h
0x18006fcea  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18006fcef  jmp     short loc_18006FD15
0x18006fcf1  mov     rax, [rbx+10h]
0x18006fcf5  test    rax, rax
0x18006fcf8  jz      short loc_18006FD03
0x18006fcfa  lea     rcx, [rbx+18h]
0x18006fcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd03  call    GetProcessHeap_0
0x18006fd08  mov     r8, rbx; lpMem
0x18006fd0b  xor     edx, edx; dwFlags
0x18006fd0d  mov     rcx, rax; hHeap
0x18006fd10  call    HeapFree_0
0x18006fd15  mov     rbx, [rbp+lpMem]
0x18006fd19  lea     rcx, [rbp+lpMem]
0x18006fd1d  mov     rax, [rbx]
0x18006fd20  mov     [rbp+lpMem], rax
0x18006fd24  mov     [rax+8], rcx
0x18006fd28  lea     rax, [rbp+lpMem]
0x18006fd2c  cmp     rbx, rax
0x18006fd2f  jnz     short loc_18006FCF1
0x18006fd31  mov     esi, [rbp+var_38]
0x18006fd34  jmp     loc_18006FF4D
0x18006fd39  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18006fd40  test    rdx, rdx
0x18006fd43  jz      loc_1800700D6
0x18006fd49  mov     rcx, [rcx+10h]
0x18006fd4d  call    RtlIsTypeSafeHandleValid
0x18006fd52  test    al, al
0x18006fd54  jz      loc_1800700D6
0x18006fd5a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_DEFINITION_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18006fd61  test    rdx, rdx
0x18006fd64  jz      loc_1800700CD
0x18006fd6a  mov     rcx, [r13+18h]
0x18006fd6e  call    RtlIsTypeSafeHandleValid
0x18006fd73  test    al, al
0x18006fd75  jz      loc_1800700CD
0x18006fd7b  lea     rdx, [rbp+var_28]
0x18006fd7f  lea     rcx, [rbp+var_50]
0x18006fd83  call    ?Allocate@?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA?AVCCallDisposition@Nt@2@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::Allocate(void)
0x18006fd88  mov     ebx, [rax]
0x18006fd8a  test    ebx, ebx
0x18006fd8c  jns     loc_18006FE1B
0x18006fd92  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006fd98  jnz     short loc_18006FDA0
0x18006fd9a  call    cs:__imp_DebugBreak
0x18006fda0  mov     r9d, ebx; int
0x18006fda3  lea     rcx, aStatusPropagat; "Status propagated"
0x18006fdaa  mov     r8d, 146Bh; char *
0x18006fdb0  mov     rdx, rdi; char *
0x18006fdb3  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006fdb8  mov     ecx, ebx; this
0x18006fdba  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006fdbf  mov     rbx, [rbp+lpMem]
0x18006fdc3  mov     esi, eax
0x18006fdc5  lea     rax, [rbp+lpMem]
0x18006fdc9  mov     rcx, [rbx]
0x18006fdcc  mov     [rbp+lpMem], rcx
0x18006fdd0  mov     [rcx+8], rax
0x18006fdd4  jmp     short loc_18006FE0D
0x18006fdd6  mov     rax, [rbx+10h]
0x18006fdda  test    rax, rax
0x18006fddd  jz      short loc_18006FDE8
0x18006fddf  lea     rcx, [rbx+18h]
0x18006fde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fde8  call    GetProcessHeap_0
0x18006fded  mov     r8, rbx; lpMem
0x18006fdf0  xor     edx, edx; dwFlags
0x18006fdf2  mov     rcx, rax; hHeap
0x18006fdf5  call    HeapFree_0
0x18006fdfa  mov     rbx, [rbp+lpMem]
0x18006fdfe  lea     rcx, [rbp+lpMem]
0x18006fe02  mov     rax, [rbx]
0x18006fe05  mov     [rbp+lpMem], rax
0x18006fe09  mov     [rax+8], rcx
0x18006fe0d  lea     rax, [rbp+lpMem]
0x18006fe11  cmp     rbx, rax
0x18006fe14  jnz     short loc_18006FDD6
0x18006fe16  jmp     loc_18006FF4D
0x18006fe1b  lea     rdx, [rbp+var_30]; struct IDefinitionIdentity *
0x18006fe1f  mov     rcx, r15; this
0x18006fe22  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x18006fe27  mov     esi, eax
0x18006fe29  test    eax, eax
0x18006fe2b  jns     short loc_18006FE92
0x18006fe2d  mov     r8d, eax; int
0x18006fe30  mov     edx, 146Ch; char *
0x18006fe35  mov     rcx, rdi; this
0x18006fe38  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18006fe3d  mov     rcx, [rbp+var_30]
0x18006fe41  test    rcx, rcx
0x18006fe44  jz      short loc_18006FE71
0x18006fe46  call    RtlCloseDefinitionIdentityHandle
0x18006fe4b  jmp     short loc_18006FE71
0x18006fe4d  mov     rax, [rbx+10h]
0x18006fe51  test    rax, rax
0x18006fe54  jz      short loc_18006FE5F
0x18006fe56  lea     rcx, [rbx+18h]
0x18006fe5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe5f  call    GetProcessHeap_0
0x18006fe64  mov     r8, rbx; lpMem
0x18006fe67  xor     edx, edx; dwFlags
0x18006fe69  mov     rcx, rax; hHeap
0x18006fe6c  call    HeapFree_0
0x18006fe71  mov     rbx, [rbp+lpMem]
0x18006fe75  lea     rcx, [rbp+lpMem]
0x18006fe79  mov     rax, [rbx]
0x18006fe7c  mov     [rbp+lpMem], rax
0x18006fe80  mov     [rax+8], rcx
0x18006fe84  lea     rax, [rbp+lpMem]
0x18006fe88  cmp     rbx, rax
0x18006fe8b  jnz     short loc_18006FE4D
0x18006fe8d  jmp     loc_18006FF4D
0x18006fe92  cmp     dword ptr [rbp+var_20], 0
0x18006fe96  jz      short loc_18006FEAD
0x18006fe98  xor     r9d, r9d; lpArguments
0x18006fe9b  xor     r8d, r8d; nNumberOfArguments
0x18006fe9e  mov     ecx, 0C00000E5h; dwExceptionCode
0x18006fea3  lea     edx, [r9+1]; dwExceptionFlags
0x18006fea7  call    cs:__imp_RaiseException
0x18006fead  mov     rbx, [rbp+var_30]
0x18006feb1  lea     r8, [rbp+var_20]
0x18006feb5  mov     rcx, [r13+18h]
0x18006feb9  mov     rdx, rbx
0x18006febc  call    CdfDefinitionIdentityTableFindDefinitionIdentity
0x18006fec1  mov     edi, eax
0x18006fec3  test    eax, eax
0x18006fec5  jns     loc_18006FF64
0x18006fecb  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18006fed1  jnz     short loc_18006FED9
0x18006fed3  call    cs:__imp_DebugBreak
0x18006fed9  mov     r9d, edi; int
0x18006fedc  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006fee3  mov     r8d, 146Dh; char *
0x18006fee9  lea     rcx, aStatusPropagat; "Status propagated"
0x18006fef0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006fef5  mov     ecx, edi; this
0x18006fef7  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006fefc  mov     esi, eax
0x18006fefe  test    rbx, rbx
0x18006ff01  jz      short loc_18006FF31
0x18006ff03  mov     rcx, rbx
0x18006ff06  call    RtlCloseDefinitionIdentityHandle
0x18006ff0b  jmp     short loc_18006FF31
0x18006ff0d  mov     rax, [rbx+10h]
0x18006ff11  test    rax, rax
0x18006ff14  jz      short loc_18006FF1F
0x18006ff16  lea     rcx, [rbx+18h]
0x18006ff1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff1f  call    GetProcessHeap_0
0x18006ff24  mov     r8, rbx; lpMem
0x18006ff27  xor     edx, edx; dwFlags
0x18006ff29  mov     rcx, rax; hHeap
0x18006ff2c  call    HeapFree_0
0x18006ff31  mov     rbx, [rbp+lpMem]
0x18006ff35  lea     rcx, [rbp+lpMem]
0x18006ff39  mov     rax, [rbx]
0x18006ff3c  mov     [rbp+lpMem], rax
0x18006ff40  mov     [rax+8], rcx
0x18006ff44  lea     rax, [rbp+lpMem]
0x18006ff48  cmp     rbx, rax
0x18006ff4b  jnz     short loc_18006FF0D
0x18006ff4d  lea     rcx, [rbp+var_20]; this
0x18006ff51  call    ??1CCDF_VALUE@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE(void)
0x18006ff56  lea     rcx, [rbp+var_50]
0x18006ff5a  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(void)
0x18006ff5f  jmp     loc_1800700FF
0x18006ff64  mov     eax, dword ptr [rbp+var_20]
0x18006ff67  test    eax, eax
0x18006ff69  jnz     short loc_18006FFE1
0x18006ff6b  mov     [rbp+var_40], 146Eh
0x18006ff72  test    rbx, rbx
0x18006ff75  jz      short loc_18006FFA5
0x18006ff77  mov     rcx, rbx
0x18006ff7a  call    RtlCloseDefinitionIdentityHandle
0x18006ff7f  jmp     short loc_18006FFA5
0x18006ff81  mov     rax, [rbx+10h]
0x18006ff85  test    rax, rax
0x18006ff88  jz      short loc_18006FF93
0x18006ff8a  lea     rcx, [rbx+18h]
0x18006ff8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff93  call    GetProcessHeap_0
0x18006ff98  mov     r8, rbx; lpMem
0x18006ff9b  xor     edx, edx; dwFlags
0x18006ff9d  mov     rcx, rax; hHeap
0x18006ffa0  call    HeapFree_0
0x18006ffa5  mov     rbx, [rbp+lpMem]
0x18006ffa9  lea     rcx, [rbp+lpMem]
0x18006ffad  mov     rax, [rbx]
0x18006ffb0  mov     [rbp+lpMem], rax
0x18006ffb4  mov     [rax+8], rcx
0x18006ffb8  lea     rax, [rbp+lpMem]
0x18006ffbc  cmp     rbx, rax
0x18006ffbf  jnz     short loc_18006FF81
0x18006ffc1  lea     rcx, [rbp+var_20]; this
0x18006ffc5  call    ??1CCDF_VALUE@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE(void)
0x18006ffca  lea     rcx, [rbp+var_50]
0x18006ffce  call    ??1?$CSmartPtr@V?$CSmartPtrTraits@V?$CComObject@VCCategoryMembershipEntry@@@Com@IsolationImplementation@@@Nt@BCL@@@BCL@@QEAA@XZ; BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>::~CSmartPtr<BCL::Nt::CSmartPtrTraits<IsolationImplementation::Com::CComObject<CCategoryMembershipEntry>>>(void)
0x18006ffd3  lea     rcx, [rbp+var_48]
0x18006ffd7  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x18006ffdc  jmp     loc_1800700FC
0x18006ffe1  cmp     eax, 1
0x18006ffe4  jz      short loc_180070041
0x18006ffe6  mov     [rbp+var_40], 146Fh
0x18006ffed  test    rbx, rbx
0x18006fff0  jz      short loc_180070020
0x18006fff2  mov     rcx, rbx
0x18006fff5  call    RtlCloseDefinitionIdentityHandle
0x18006fffa  jmp     short loc_180070020
0x18006fffc  mov     rax, [rbx+10h]
0x180070000  test    rax, rax
0x180070003  jz      short loc_18007000E
0x180070005  lea     rcx, [rbx+18h]
0x180070009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007000e  call    GetProcessHeap_0
0x180070013  mov     r8, rbx; lpMem
0x180070016  xor     edx, edx; dwFlags
0x180070018  mov     rcx, rax; hHeap
0x18007001b  call    HeapFree_0
0x180070020  mov     rbx, [rbp+lpMem]
0x180070024  lea     rcx, [rbp+lpMem]
0x180070028  mov     rax, [rbx]
0x18007002b  mov     [rbp+lpMem], rax
0x18007002f  mov     [rax+8], rcx
0x180070033  lea     rax, [rbp+lpMem]
0x180070037  cmp     rbx, rax
0x18007003a  jnz     short loc_18006FFFC
0x18007003c  jmp     loc_1800700DD
0x180070041  mov     rax, [r15]
0x180070044  mov     rcx, r15
0x180070047  mov     rax, [rax+8]
0x18007004b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070050  mov     rdi, [rbp+var_50]
0x180070054  mov     r9, r15
0x180070057  mov     r8d, dword ptr [rbp+var_20+8]
0x18007005b  mov     rcx, rdi
0x18007005e  mov     rdx, [r13+10h]
0x180070062  call    ?Initialize@CCategoryMembershipEntry@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_BLOBID@345@PEAUIDefinitionIdentity@@@Z; CCategoryMembershipEntry::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,IDefinitionIdentity *)
0x180070067  mov     esi, eax
0x180070069  test    eax, eax
0x18007006b  jns     short loc_180070083
0x18007006d  mov     edx, 1471h; char *
0x180070072  mov     r8d, eax; int
  ... truncated ...
```
