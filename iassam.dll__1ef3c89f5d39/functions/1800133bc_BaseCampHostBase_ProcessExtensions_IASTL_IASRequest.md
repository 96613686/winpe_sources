# BaseCampHostBase::ProcessExtensions(IASTL::IASRequest &)

- ea: `0x1800133bc`
- end: `0x1800139c8`
- name: `?ProcessExtensions@BaseCampHostBase@@IEAAXAEAVIASRequest@IASTL@@@Z`
- size: `1548`
- prototype: `void(BaseCampHostBase *__hidden this, struct IASTL::IASRequest *)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013ce0`
- `0x180013ec0`

## callees

- `0x180001f0c`
- `0x1800028e0`
- `0x18000aae0`
- `0x18000ab7c`
- `0x18000acf4`
- `0x18000ad58`
- `0x18000b08c`
- `0x18000b0e0`
- `0x18000ba5c`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000c808`
- `0x18000d604`
- `0x18000df68`
- `0x18000dfa4`
- `0x18001261c`
- `0x180012700`
- `0x1800129dc`
- `0x180012a04`
- `0x1800133bc`
- `0x180013af8`
- `0x180013b34`
- `0x1800141a4`
- `0x180014300`
- `0x1800254a0`
- `0x18002b472`
- `0x18002e010`

## import_xrefs

- `msvcrt!free` at `0x1800136c9`
- `msvcrt!free` at `0x1800136c9`
- `msvcrt!malloc` at `0x180013462`
- `msvcrt!malloc` at `0x180013462`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001348a`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800134ec`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001348a`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800134ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001391c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001391c`

## string_xrefs

- `0x180013658`: `Could not process Extension dlls, extension dll crash?: hr=%x`
- `0x18001383f`: `Routing Type changed from IAS_REQUEST_CHALLENGE_RESPONSE to IAS_REQUEST_ACCESS_REQUEST`
- `0x18001397f`: `IAS extension host returned responseType=%d, reasonCode=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall BaseCampHostBase::ProcessExtensions(BaseCampHostBase *this, struct IASTL::IASRequest *a2)
{
  struct IASTL::IASRequest *v2; // r14
  unsigned int AttributeCount; // r15d
  unsigned int v4; // esi
  unsigned int v5; // ebx
  struct _IASATTRIBUTE *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // r12d
  LPVOID *v13; // rbx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rax
  size_t v16; // rdi
  size_t v17; // r8
  _QWORD *v18; // rdi
  __int64 v19; // r13
  void *v20; // r9
  unsigned int i; // ecx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rcx
  int v25; // edx
  unsigned int v26; // edx
  int v27; // ecx
  int v28; // edi
  PVOID *v29; // rax
  const char *v30; // rdi
  const char *v31; // rax
  int v32; // edi
  void *v33; // rcx
  _QWORD *v34; // r14
  unsigned int v35; // esi
  void *v36; // rdi
  unsigned int j; // r14d
  void *v38; // rdi
  int v39; // [rsp+40h] [rbp-59h]
  LPVOID v40[2]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v41; // [rsp+60h] [rbp-39h]
  int v42; // [rsp+64h] [rbp-35h]
  unsigned int v43; // [rsp+68h] [rbp-31h]
  __int64 v44; // [rsp+70h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-21h]
  void *v46; // [rsp+80h] [rbp-19h] BYREF
  int Request; // [rsp+88h] [rbp-11h] BYREF
  LPVOID *v48; // [rsp+90h] [rbp-9h]
  _QWORD pExceptionObject[11]; // [rsp+98h] [rbp-1h] BYREF
  unsigned int Reason; // [rsp+110h] [rbp+77h] BYREF
  unsigned int Response; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = a2;
  AttributeCount = IASTL::IASRequest::GetAttributeCount(a2);
  if ( !AttributeCount )
    return;
  v4 = 0;
  v5 = 0;
  while ( v5 < AttributeCount )
  {
    v6 = IASTL::IASRequest::PeekAttribute(v2, v5);
    if ( !v6 )
      _com_issue_error(-2147418113);
    ++v5;
    v10 = IASIsAttributeMarshallable(v6, v7, v8, v9);
    v11 = v4 + 1;
    if ( !v10 )
      v11 = v4;
    v4 = v11;
  }
  if ( !v4 )
    return;
  v12 = AttributeCount - v4;
  v13 = 0;
  v48 = 0;
  if ( AttributeCount != v4 )
  {
    v14 = 8LL * v12;
    if ( v14 > 0xFFFFFFFF )
      goto LABEL_73;
    v13 = (LPVOID *)malloc((unsigned int)v14);
    v48 = v13;
    if ( !v13 )
    {
      v40[0] = "bad allocation";
      exception::exception((exception *)pExceptionObject, (const char *const *)v40, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  v15 = 8LL * v4;
  if ( v15 > 0xFFFFFFFF )
LABEL_73:
    _com_issue_error(-2147024362);
  v16 = (unsigned int)v15;
  ATL::CComPtr<IRequest>::CComPtr<IRequest>(&v46);
  if ( !(unsigned __int8)ATL::CHeapPtrBase<_IASATTRIBUTE *,ATL::CComAllocator>::AllocateBytes(&v46, (unsigned int)v16) )
  {
    v40[0] = "bad allocation";
    exception::exception((exception *)pExceptionObject, (const char *const *)v40, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  v17 = v16;
  v18 = v46;
  memset_0(v46, 0, v17);
  v19 = *((_QWORD *)v2 + 1);
  v20 = 0;
  v42 = 0;
  v41 = 0;
  for ( i = 0; ; i = v43 + 1 )
  {
    v43 = i;
    if ( i >= AttributeCount )
      break;
    v40[0] = v20;
    v39 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v19 + 104LL))(v19, i, v40);
    if ( v39 < 0 || !v40[0] )
    {
      IASAttributeReleaseArray(v41, v13);
      v27 = -2147418113;
      if ( v39 < 0 )
        v27 = v39;
      _com_issue_error(v27);
    }
    if ( (unsigned int)IASIsAttributeMarshallable(v40[0], v22, v23, 0) )
    {
      v25 = v42;
      v18[v42] = v24;
      v42 = v25 + 1;
    }
    else
    {
      IASAttributeAddRef();
      v26 = v41;
      v13[v41] = v40[0];
      v41 = v26 + 1;
    }
  }
  v40[0] = (LPVOID)__PAIR64__((unsigned int)v20, v4);
  v40[1] = v18;
  v44 = 0;
  pv = v20;
  Request = IASTL::IASRequest::get_Request(v2);
  Response = IASTL::IASRequest::get_Response(v2);
  Reason = IASTL::IASRequest::get_Reason(v2);
  v28 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, int *, unsigned int *, unsigned int *, __int64 *))(**((_QWORD **)this + 11) + 32LL))(
          *((_QWORD *)this + 11),
          v40,
          &Request,
          &Response,
          &Reason,
          &v44);
  if ( v28 >= 0 )
  {
    v29 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      v30 = "true";
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("isNetworkPolicyEnforcedForPAPChallengeResponse: %s");
        v31 = "true";
        if ( !BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse )
          v31 = "false";
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
          (unsigned int)"NPSSVC",
          (__int64)v31);
        v29 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v29 != &WPP_GLOBAL_Control && *((_BYTE *)v29 + 25) >= 4u && (*((_BYTE *)v29 + 28) & 4) != 0 )
      {
        IASTL::IASRequest::get_RoutingType(v2);
        WppDbgPrint("IAS_REQUEST_CHALLENGE_RESPONSE: %s");
        if ( (unsigned int)IASTL::IASRequest::get_RoutingType(v2) != 2 )
          v30 = "false";
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
          (unsigned int)"NPSSVC",
          (__int64)v30);
      }
    }
    if ( (unsigned int)IASTL::IASRequest::get_RoutingType(v2) == 2
      && BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse )
    {
      v40[0] = 0;
      if ( (unsigned __int8)IASTL::IASAttribute::load(v40, *((_QWORD *)v2 + 1), 2, 6) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("Routing Type changed from IAS_REQUEST_CHALLENGE_RESPONSE to IAS_REQUEST_ACCESS_REQUEST");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids, "NPSSVC");
        }
        IASTL::IASRequest::put_RoutingType(v2, 0);
      }
      if ( v40[0] )
        IASAttributeRelease(v40[0]);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
    v32 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 88LL))(v19, v12 + (unsigned int)v44);
    if ( v32 < 0 )
    {
      IASFreeAttributesArray((unsigned int)v44, pv);
      IASAttributeReleaseArray(v12, v13);
      _com_issue_error(v32);
    }
    v33 = pv;
    if ( (_DWORD)v44 )
    {
      v34 = pv;
      v35 = 0;
      do
      {
        v36 = (void *)v34[v35];
        (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v19 + 96LL))(v19, v36);
        IASAttributeRelease(v36);
        ++v35;
      }
      while ( v35 < (unsigned int)v44 );
      v33 = pv;
      v2 = a2;
    }
    CoTaskMemFree(v33);
    if ( v12 )
    {
      for ( j = 0; j < v12; ++j )
      {
        v38 = v13[j];
        (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v19 + 96LL))(v19, v38);
        IASAttributeRelease(v38);
      }
      v2 = a2;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("IAS extension host returned responseType=%d, reasonCode=%d");
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    IASTL::IASRequest::SetResponse(v2, Response, Reason);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Could not process Extension dlls, extension dll crash?: hr=%x");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids);
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v2 + 104LL))(*(_QWORD *)v2, 5, 10);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v2 + 128LL))(*(_QWORD *)v2, (unsigned int)v28);
    IASAttributeReleaseArray(v12, v13);
  }
  ATL::CComHeapPtr<_IASATTRIBUTE *>::~CComHeapPtr<_IASATTRIBUTE *>(&v46);
  free(v13);
}

```

## disassembly

```asm
0x1800133bc  mov     [rsp-8+arg_8], rdx
0x1800133c1  mov     [rsp-8+arg_0], rcx
0x1800133c6  push    rbp
0x1800133c7  push    rbx
0x1800133c8  push    rsi
0x1800133c9  push    rdi
0x1800133ca  push    r12
0x1800133cc  push    r13
0x1800133ce  push    r14
0x1800133d0  push    r15
0x1800133d2  lea     rbp, [rsp-1Fh]
0x1800133d7  sub     rsp, 0B8h
0x1800133de  mov     r14, rdx
0x1800133e1  mov     rcx, rdx; this
0x1800133e4  call    ?GetAttributeCount@IASRequest@IASTL@@QEBAKXZ; IASTL::IASRequest::GetAttributeCount(void)
0x1800133e9  mov     r15d, eax
0x1800133ec  test    eax, eax
0x1800133ee  jz      loc_1800136CF
0x1800133f4  xor     esi, esi
0x1800133f6  xor     ebx, ebx
0x1800133f8  lea     r13d, [rsi+1]
0x1800133fc  cmp     ebx, r15d
0x1800133ff  jnb     short loc_180013432
0x180013401  mov     edx, ebx; unsigned int
0x180013403  mov     rcx, r14; this
0x180013406  call    ?PeekAttribute@IASRequest@IASTL@@QEAAPEAU_IASATTRIBUTE@@K@Z; IASTL::IASRequest::PeekAttribute(ulong)
0x18001340b  test    rax, rax
0x18001340e  jz      short loc_180013427
0x180013410  add     ebx, r13d
0x180013413  mov     rcx, rax
0x180013416  call    IASIsAttributeMarshallable
0x18001341b  lea     ecx, [rsi+1]
0x18001341e  test    eax, eax
0x180013420  cmovz   ecx, esi
0x180013423  mov     esi, ecx
0x180013425  jmp     short loc_1800133FC
0x180013427  mov     ecx, 8000FFFFh; int
0x18001342c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180013432  test    esi, esi
0x180013434  jz      loc_1800136CF
0x18001343a  mov     r12d, r15d
0x18001343d  mov     edi, 0FFFFFFFFh
0x180013442  sub     r12d, esi
0x180013445  mov     ebx, 0
0x18001344a  mov     [rbp+57h+var_60], rbx
0x18001344e  jz      short loc_1800134AC
0x180013450  mov     eax, r12d
0x180013453  shl     rax, 3
0x180013457  cmp     rax, rdi
0x18001345a  ja      loc_1800139BD
0x180013460  mov     ecx, eax; Size
0x180013462  call    cs:__imp_malloc
0x180013468  mov     rbx, rax
0x18001346b  mov     [rbp+57h+var_60], rax
0x18001346f  test    rax, rax
0x180013472  jnz     short loc_1800134AC
0x180013474  lea     rax, aBadAllocation; "bad allocation"
0x18001347b  mov     [rbp+57h+var_A0], rax
0x18001347f  mov     r8d, r13d
0x180013482  lea     rdx, [rbp+57h+var_A0]
0x180013486  lea     rcx, [rbp+57h+pExceptionObject]
0x18001348a  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180013490  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180013497  mov     [rbp+57h+pExceptionObject], rax
0x18001349b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800134a2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800134a6  call    _CxxThrowException_0
0x1800134ac  mov     eax, esi
0x1800134ae  shl     rax, 3
0x1800134b2  cmp     rax, rdi
0x1800134b5  ja      loc_1800139BD
0x1800134bb  mov     edi, eax
0x1800134bd  lea     rcx, [rbp+57h+var_70]; void *
0x1800134c1  call    ??0?$CComPtr@UIRequest@@@ATL@@QEAA@XZ; ATL::CComPtr<IRequest>::CComPtr<IRequest>(void)
0x1800134c6  nop
0x1800134c7  mov     edx, edi
0x1800134c9  lea     rcx, [rbp+57h+var_70]
0x1800134cd  call    ?AllocateBytes@?$CHeapPtrBase@PEAU_IASATTRIBUTE@@VCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_IASATTRIBUTE *,ATL::CComAllocator>::AllocateBytes(unsigned __int64)
0x1800134d2  test    al, al
0x1800134d4  jnz     short loc_18001350E
0x1800134d6  lea     rax, aBadAllocation; "bad allocation"
0x1800134dd  mov     [rbp+57h+var_A0], rax
0x1800134e1  mov     r8d, r13d
0x1800134e4  lea     rdx, [rbp+57h+var_A0]
0x1800134e8  lea     rcx, [rbp+57h+pExceptionObject]
0x1800134ec  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x1800134f2  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800134f9  mov     [rbp+57h+pExceptionObject], rax
0x1800134fd  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180013504  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013508  call    _CxxThrowException_0
0x18001350e  mov     r8, rdi; Size
0x180013511  xor     edx, edx; Val
0x180013513  mov     rdi, [rbp+57h+var_70]
0x180013517  mov     rcx, rdi; void *
0x18001351a  call    memset_0
0x18001351f  mov     r13, [r14+8]
0x180013523  xor     r9d, r9d
0x180013526  mov     [rbp+57h+var_8C], r9d
0x18001352a  mov     [rbp+57h+var_90], r9d
0x18001352e  mov     ecx, r9d
0x180013531  mov     [rbp+57h+var_88], ecx
0x180013534  cmp     ecx, r15d
0x180013537  jnb     short loc_1800135B7
0x180013539  mov     [rbp+57h+var_A0], r9
0x18001353d  mov     rax, [r13+0]
0x180013541  lea     r8, [rbp+57h+var_A0]
0x180013545  mov     edx, ecx
0x180013547  mov     rcx, r13
0x18001354a  mov     rax, [rax+68h]
0x18001354e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013553  mov     [rbp+57h+var_B0], eax
0x180013556  xor     r9d, r9d
0x180013559  test    eax, eax
0x18001355b  js      short loc_180013599
0x18001355d  mov     rcx, [rbp+57h+var_A0]
0x180013561  test    rcx, rcx
0x180013564  jz      short loc_180013599
0x180013566  call    IASIsAttributeMarshallable
0x18001356b  test    eax, eax
0x18001356d  jz      short loc_18001357D
0x18001356f  mov     edx, [rbp+57h+var_8C]
0x180013572  mov     [rdi+rdx*8], rcx
0x180013576  inc     edx
0x180013578  mov     [rbp+57h+var_8C], edx
0x18001357b  jmp     short loc_180013592
0x18001357d  call    IASAttributeAddRef
0x180013582  mov     edx, [rbp+57h+var_90]
0x180013585  mov     rax, [rbp+57h+var_A0]
0x180013589  mov     [rbx+rdx*8], rax
0x18001358d  inc     edx
0x18001358f  mov     [rbp+57h+var_90], edx
0x180013592  mov     ecx, [rbp+57h+var_88]
0x180013595  inc     ecx
0x180013597  jmp     short loc_180013531
0x180013599  mov     rdx, rbx
0x18001359c  mov     ecx, [rbp+57h+var_90]
0x18001359f  call    IASAttributeReleaseArray
0x1800135a4  mov     ecx, 8000FFFFh
0x1800135a9  mov     eax, [rbp+57h+var_B0]
0x1800135ac  test    eax, eax
0x1800135ae  cmovs   ecx, eax; int
0x1800135b1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800135b7  mov     dword ptr [rbp+57h+var_A0+4], r9d
0x1800135bb  mov     dword ptr [rbp+57h+var_A0], esi
0x1800135be  mov     [rbp+57h+var_A0+8], rdi
0x1800135c2  mov     [rbp+57h+var_80], 0
0x1800135ca  mov     [rbp+57h+pv], r9
0x1800135ce  mov     rcx, r14
0x1800135d1  call    ?get_Request@IASRequest@IASTL@@QEBA?AW4_IASREQUEST@@XZ; IASTL::IASRequest::get_Request(void)
0x1800135d6  mov     [rbp+57h+var_68], eax
0x1800135d9  mov     rcx, r14
0x1800135dc  call    ?get_Response@IASRequest@IASTL@@QEBA?AW4_IASRESPONSE@@XZ; IASTL::IASRequest::get_Response(void)
0x1800135e1  mov     [rbp+57h+arg_18], eax
0x1800135e4  mov     rcx, r14; this
0x1800135e7  call    ?get_Reason@IASRequest@IASTL@@QEBAKXZ; IASTL::IASRequest::get_Reason(void)
0x1800135ec  mov     [rbp+57h+arg_10], eax
0x1800135ef  mov     rcx, [rbp+57h+arg_0]
0x1800135f3  mov     rcx, [rcx+58h]
0x1800135f7  movaps  xmm0, xmmword ptr [rbp+57h+var_A0]
0x1800135fb  movdqa  xmmword ptr [rbp+57h+var_A0], xmm0
0x180013600  mov     rax, [rcx]
0x180013603  lea     rdx, [rbp+57h+var_80]
0x180013607  mov     [rsp+0F0h+var_C8], rdx
0x18001360c  lea     rdx, [rbp+57h+arg_10]
0x180013610  mov     [rsp+0F0h+var_D0], rdx
0x180013615  lea     r9, [rbp+57h+arg_18]
0x180013619  lea     r8, [rbp+57h+var_68]
0x18001361d  lea     rdx, [rbp+57h+var_A0]
0x180013621  mov     rax, [rax+20h]
0x180013625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001362a  mov     edi, eax
0x18001362c  test    eax, eax
0x18001362e  jns     loc_1800136E3
0x180013634  lea     r15, WPP_GLOBAL_Control
0x18001363b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013642  cmp     rcx, r15
0x180013645  jz      short loc_180013684
0x180013647  cmp     byte ptr [rcx+19h], 2
0x18001364b  jb      short loc_180013684
0x18001364d  mov     sil, 4
0x180013650  test    [rcx+1Ch], sil
0x180013654  jz      short loc_180013684
0x180013656  mov     edx, eax
0x180013658  lea     rcx, aCouldNotProces; "Could not process Extension dlls, exten"...
0x18001365f  call    WppDbgPrint
0x180013664  mov     edx, 1Dh
0x180013669  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18001366d  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013674  mov     rcx, cs:WPP_GLOBAL_Control
0x18001367b  mov     rcx, [rcx+10h]
0x18001367f  call    WPP_SF_sd
0x180013684  mov     rcx, [r14]
0x180013687  mov     rax, [rcx]
0x18001368a  mov     edx, 5
0x18001368f  lea     r8d, [rdx+5]
0x180013693  mov     rax, [rax+68h]
0x180013697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001369c  mov     rcx, [r14]
0x18001369f  mov     rax, [rcx]
0x1800136a2  mov     edx, edi
0x1800136a4  mov     rax, [rax+80h]
0x1800136ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136b0  mov     rdx, rbx
0x1800136b3  mov     ecx, r12d
0x1800136b6  call    IASAttributeReleaseArray
0x1800136bb  nop
0x1800136bc  lea     rcx, [rbp+57h+var_70]
0x1800136c0  call    ??1?$CComHeapPtr@PEAU_IASATTRIBUTE@@@ATL@@QEAA@XZ; ATL::CComHeapPtr<_IASATTRIBUTE *>::~CComHeapPtr<_IASATTRIBUTE *>(void)
0x1800136c5  nop
0x1800136c6  mov     rcx, rbx; Block
0x1800136c9  call    cs:__imp_free
0x1800136cf  add     rsp, 0B8h
0x1800136d6  pop     r15
0x1800136d8  pop     r14
0x1800136da  pop     r13
0x1800136dc  pop     r12
0x1800136de  pop     rdi
0x1800136df  pop     rsi
0x1800136e0  pop     rbx
0x1800136e1  pop     rbp
0x1800136e2  retn
0x1800136e3  lea     r15, WPP_GLOBAL_Control
0x1800136ea  mov     sil, 4
0x1800136ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800136f4  cmp     rax, r15
0x1800136f7  jz      loc_1800137E9
0x1800136fd  lea     rdi, aTrue; "true"
0x180013704  lea     rcx, aFalse; "false"
0x18001370b  cmp     [rax+19h], sil
0x18001370f  jb      short loc_180013775
0x180013711  test    [rax+1Ch], sil
0x180013715  jz      short loc_180013775
0x180013717  mov     rdx, rdi
0x18001371a  cmp     cs:?isNetworkPolicyEnforcedForPAPChallengeResponse@BaseCampHostBase@@1_NA, 0; bool BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse
0x180013721  cmovz   rdx, rcx
0x180013725  lea     rcx, aIsnetworkpolic; "isNetworkPolicyEnforcedForPAPChallengeR"...
0x18001372c  call    WppDbgPrint
0x180013731  mov     rax, rdi
0x180013734  cmp     cs:?isNetworkPolicyEnforcedForPAPChallengeResponse@BaseCampHostBase@@1_NA, 0; bool BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse
0x18001373b  lea     rcx, aFalse; "false"
0x180013742  cmovz   rax, rcx
0x180013746  mov     edx, 1Eh
0x18001374b  mov     [rsp+0F0h+var_D0], rax
0x180013750  lea     r9, aNpssvc; "NPSSVC"
0x180013757  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x18001375e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013765  mov     rcx, [rcx+10h]
0x180013769  call    WPP_SF_ss
0x18001376e  mov     rax, cs:WPP_GLOBAL_Control
0x180013775  cmp     rax, r15
0x180013778  jz      short loc_1800137E9
0x18001377a  cmp     [rax+19h], sil
0x18001377e  jb      short loc_1800137E9
0x180013780  test    [rax+1Ch], sil
0x180013784  jz      short loc_1800137E9
0x180013786  mov     rcx, r14
0x180013789  call    ?get_RoutingType@IASRequest@IASTL@@QEBA?AW4_IASREQUEST@@XZ; IASTL::IASRequest::get_RoutingType(void)
0x18001378e  mov     rdx, rdi
0x180013791  cmp     eax, 2
0x180013794  lea     rax, aFalse; "false"
0x18001379b  cmovnz  rdx, rax
0x18001379f  lea     rcx, aIasRequestChal; "IAS_REQUEST_CHALLENGE_RESPONSE: %s"
0x1800137a6  call    WppDbgPrint
0x1800137ab  mov     rcx, r14
0x1800137ae  call    ?get_RoutingType@IASRequest@IASTL@@QEBA?AW4_IASREQUEST@@XZ; IASTL::IASRequest::get_RoutingType(void)
0x1800137b3  cmp     eax, 2
0x1800137b6  lea     rax, aFalse; "false"
0x1800137bd  cmovnz  rdi, rax
0x1800137c1  mov     edx, 1Fh
0x1800137c6  mov     [rsp+0F0h+var_D0], rdi
0x1800137cb  lea     r9, aNpssvc; "NPSSVC"
0x1800137d2  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x1800137d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137e0  mov     rcx, [rcx+10h]
0x1800137e4  call    WPP_SF_ss
0x1800137e9  mov     rcx, r14
0x1800137ec  call    ?get_RoutingType@IASRequest@IASTL@@QEBA?AW4_IASREQUEST@@XZ; IASTL::IASRequest::get_RoutingType(void)
0x1800137f1  cmp     eax, 2
0x1800137f4  jnz     loc_180013887
0x1800137fa  cmp     cs:?isNetworkPolicyEnforcedForPAPChallengeResponse@BaseCampHostBase@@1_NA, 0; bool BaseCampHostBase::isNetworkPolicyEnforcedForPAPChallengeResponse
0x180013801  jz      loc_180013887
0x180013807  mov     [rbp+57h+var_A0], 0
0x18001380f  lea     r9d, [rax+4]
0x180013813  mov     r8d, eax
0x180013816  mov     rdx, [r14+8]
0x18001381a  lea     rcx, [rbp+57h+var_A0]
0x18001381e  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x180013823  test    al, al
0x180013825  jz      short loc_180013879
0x180013827  mov     rax, cs:WPP_GLOBAL_Control
0x18001382e  cmp     rax, r15
0x180013831  jz      short loc_18001386E
0x180013833  cmp     [rax+19h], sil
0x180013837  jb      short loc_18001386E
0x180013839  test    [rax+1Ch], sil
0x18001383d  jz      short loc_18001386E
0x18001383f  lea     rcx, aRoutingTypeCha; "Routing Type changed from IAS_REQUEST_C"...
0x180013846  call    WppDbgPrint
0x18001384b  mov     edx, 20h ; ' '
  ... truncated ...
```
