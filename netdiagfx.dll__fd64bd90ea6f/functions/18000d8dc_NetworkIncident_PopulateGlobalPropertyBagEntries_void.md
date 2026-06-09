# NetworkIncident::PopulateGlobalPropertyBagEntries(void)

- ea: `0x18000d8dc`
- end: `0x18000dd14`
- name: `?PopulateGlobalPropertyBagEntries@NetworkIncident@@AEAAJXZ`
- size: `1080`
- prototype: `__int64 __fastcall(NetworkIncident *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d028`

## callees

- `0x1800035a8`
- `0x18000579c`
- `0x180006d58`
- `0x180006fa0`
- `0x180007014`
- `0x180008ca8`
- `0x18000acf0`
- `0x18000bca0`
- `0x18000c2ec`
- `0x18000d8dc`
- `0x180011810`
- `0x180025118`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc59`

## string_xrefs

- `0x18000db1f`: `Using caller supplied SID for global property bag entry.`
- `0x18000db18`: `Automatically detected caller SID for global property bag entry.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NetworkIncident::PopulateGlobalPropertyBagEntries(ProblemNode **this)
{
  ProblemNode **v1; // r14
  NetworkIncident *v2; // r15
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rsi
  __int64 v6; // rcx
  unsigned __int64 v7; // rbx
  int Attribute; // eax
  int SID; // ebx
  DWORD v10; // edx
  unsigned __int64 v11; // rbx
  WCHAR *v12; // rax
  int v13; // eax
  int v14; // edx
  const wchar_t *v15; // r8
  int v16; // eax
  struct tagHELPER_ATTRIBUTE *p_pv; // [rsp+20h] [rbp-1F8h] BYREF
  __int64 v19; // [rsp+28h] [rbp-1F0h]
  unsigned __int64 v20; // [rsp+30h] [rbp-1E8h] BYREF
  NetworkIncident *v21; // [rsp+38h] [rbp-1E0h]
  struct tagHELPER_ATTRIBUTE pv; // [rsp+50h] [rbp-1C8h] BYREF
  struct _GUID v23; // [rsp+E0h] [rbp-138h] BYREF
  unsigned __int16 v24[128]; // [rsp+F0h] [rbp-128h] BYREF
  ATL::CAtlException *v25; // [rsp+1F0h] [rbp-28h] BYREF

  v1 = this;
  v2 = (NetworkIncident *)this;
  v21 = (NetworkIncident *)this;
  memset_0(&pv.type + 1, 0, 0x84u);
  p_pv = 0;
  v19 = 0;
  pv.pwszName = L"SQMSessionID";
  pv.type = AT_GUID;
  pv.Guid = *GetSessionID(&v23);
  v3 = ProblemNode::AddProperty(*(ProblemNode **)v2, &pv);
  v4 = v3;
  v5 = (_QWORD *)((char *)v2 + 216);
  *(_QWORD *)&v23.Data1 = (char *)v2 + 216;
  v6 = *((_QWORD *)v2 + 27);
  if ( v6 )
  {
    if ( v3 < 0 )
    {
      try
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v20);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          (__int64)&v20,
          (__int64)L"Failed while adding SQM session ID to the global property bag. HR: 0x%x",
          v4);
        v7 = v20;
        (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int64))(*(_QWORD *)*v5 + 96LL))(*v5, 0, v20);
        ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
      }
      catch ( ATL::CAtlException *v25 )
      {
        v2 = v21;
        v1 = (ProblemNode **)v21;
        v5 = *(_QWORD **)&v23.Data1;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v6 + 96LL))(
        v6,
        0,
        L"Added SQM session ID to the global property bag.");
    }
  }
  memset_0(&pv, 0, sizeof(pv));
  Attribute = FindAttribute((wchar_t *)L"userid");
  SID = Attribute;
  if ( Attribute == -2147023728 )
  {
    SID = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 10) + 56LL))(*((_QWORD *)v2 + 10));
    if ( SID < 0 )
      goto LABEL_38;
    SID = GetSID(&pv.OctetString, v10);
    if ( SID >= 0 )
    {
      p_pv = &pv;
      v19 = 1;
      v20 = 0;
      SID = StringCchLengthW(L"userid", 0xFFFEu, &v20);
      if ( SID >= 0 )
      {
        v11 = v20;
        v12 = (WCHAR *)CoTaskMemAlloc(2 * v20 + 2);
        pv.pwszName = v12;
        if ( v12 )
          SID = StringCchCopyW(v12, v11 + 1, L"userid");
        else
          SID = -2147024882;
      }
      pv.type = AT_OCTET_STRING;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 10) + 64LL))(*((_QWORD *)v2 + 10));
    if ( SID < 0 )
      goto LABEL_38;
    v14 = 0;
    if ( v13 < 0 )
    {
      SID = v13;
LABEL_38:
      memset_0(v24, 0, sizeof(v24));
      StringCchPrintfW(
        v24,
        0x80u,
        L"Error while adding entries to global property bag. HRESULT 0x%x",
        (unsigned int)SID);
      (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)*v5 + 96LL))(*v5, 0, v24);
      goto LABEL_39;
    }
  }
  else
  {
    v14 = 1;
    if ( Attribute < 0 )
      goto LABEL_38;
  }
  p_pv = &pv;
  v19 = 1;
  if ( *v5 )
  {
    v15 = L"Using caller supplied SID for global property bag entry.";
    if ( !v14 )
      v15 = L"Automatically detected caller SID for global property bag entry.";
    (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(*(_QWORD *)*v5 + 96LL))(*v5, 0, v15);
  }
  SID = ProblemNode::AddProperty(*v1, &pv);
  p_pv = 0;
  v19 = 0;
  CoTaskMemFree(pv.pwszName);
  pv.pwszName = 0;
  if ( pv.type == AT_STRING )
  {
    CoTaskMemFree(pv.PWStr);
    pv.Int64 = 0;
  }
  else if ( pv.type == AT_OCTET_STRING )
  {
    CoTaskMemFree(pv.OctetString.lpValue);
    pv.OctetString.lpValue = 0;
  }
  pv.type = AT_INVALID;
  if ( SID < 0 )
    goto LABEL_38;
  memset_0(&pv, 0, sizeof(pv));
  v16 = FindAttribute((wchar_t *)L"appid");
  SID = v16;
  if ( v16 < 0 )
  {
    if ( v16 == -2147023728 )
    {
      if ( *v5 )
        (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(*(_QWORD *)*v5 + 96LL))(
          *v5,
          0,
          L"Application ID was not supplied by caller, will not be available in global property bag.");
      SID = 0;
    }
  }
  else
  {
    p_pv = &pv;
    v19 = 1;
    if ( *v5 )
      (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(*(_QWORD *)*v5 + 96LL))(
        *v5,
        0,
        L"Using caller supplied Application ID for global property bag entry.");
    SID = ProblemNode::AddProperty(*v1, &pv);
    p_pv = 0;
    v19 = 0;
    CoTaskMemFree(pv.pwszName);
    pv.pwszName = 0;
    if ( pv.type == AT_STRING )
    {
      CoTaskMemFree(pv.PWStr);
      pv.Int64 = 0;
    }
    else if ( pv.type == AT_OCTET_STRING )
    {
      CoTaskMemFree(pv.OctetString.lpValue);
      pv.OctetString.lpValue = 0;
    }
    pv.type = AT_INVALID;
  }
  if ( SID < 0 )
    goto LABEL_38;
LABEL_39:
  TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>(&p_pv);
  return (unsigned int)SID;
}

```

## disassembly

```asm
0x18000d8dc  mov     [rsp+arg_8], rbx
0x18000d8e1  mov     [rsp+arg_10], rsi
0x18000d8e6  push    rdi
0x18000d8e7  push    r14
0x18000d8e9  push    r15
0x18000d8eb  sub     rsp, 200h
0x18000d8f2  mov     rax, cs:__security_cookie
0x18000d8f9  xor     rax, rsp
0x18000d8fc  mov     [rsp+218h+var_20], rax
0x18000d904  mov     r14, rcx
0x18000d907  mov     r15, rcx
0x18000d90a  mov     [rsp+218h+var_1E0], rcx
0x18000d90f  xor     edx, edx; Val
0x18000d911  mov     r8d, 84h; Size
0x18000d917  lea     rcx, [rsp+218h+var_1BC]; void *
0x18000d91c  call    memset_0
0x18000d921  xor     edi, edi
0x18000d923  mov     [rsp+218h+var_1F8], rdi
0x18000d928  mov     [rsp+218h+var_1F0], rdi
0x18000d92d  lea     rax, aSqmsessionid; "SQMSessionID"
0x18000d934  mov     [rsp+218h+pv], rax
0x18000d939  mov     [rsp+218h+var_1C0], 0Bh
0x18000d941  lea     rcx, [rsp+218h+var_138]; retstr
0x18000d949  call    ?GetSessionID@@YA?AU_GUID@@XZ; GetSessionID(void)
0x18000d94e  movups  xmm0, xmmword ptr [rax]
0x18000d951  movdqu  xmmword ptr [rsp+218h+var_1B8.dwLength], xmm0
0x18000d957  lea     rdx, [rsp+218h+pv]; struct tagHELPER_ATTRIBUTE *
0x18000d95c  mov     rcx, [r15]; this
0x18000d95f  call    ?AddProperty@ProblemNode@@QEAAJAEBUtagHELPER_ATTRIBUTE@@H@Z; ProblemNode::AddProperty(tagHELPER_ATTRIBUTE const &,int)
0x18000d964  mov     ebx, eax
0x18000d966  lea     rsi, [r15+0D8h]
0x18000d96d  mov     qword ptr [rsp+218h+var_138.Data1], rsi
0x18000d975  mov     rcx, [rsi]
0x18000d978  test    rcx, rcx
0x18000d97b  jz      short loc_18000D9EF
0x18000d97d  test    eax, eax
0x18000d97f  js      short loc_18000D998
0x18000d981  mov     rax, [rcx]
0x18000d984  lea     r8, aAddedSqmSessio; "Added SQM session ID to the global prop"...
0x18000d98b  xor     edx, edx
0x18000d98d  mov     rax, [rax+60h]
0x18000d991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d996  jmp     short loc_18000D9EF
0x18000d998  lea     rcx, [rsp+218h+var_1E8]
0x18000d99d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000d9a2  nop
0x18000d9a3  mov     r8d, ebx
0x18000d9a6  lea     rdx, aFailedWhileAdd_0; "Failed while adding SQM session ID to t"...
0x18000d9ad  lea     rcx, [rsp+218h+var_1E8]
0x18000d9b2  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000d9b7  mov     rcx, [rsi]
0x18000d9ba  mov     rax, [rcx]
0x18000d9bd  mov     rbx, [rsp+218h+var_1E8]
0x18000d9c2  mov     r8, rbx
0x18000d9c5  xor     edx, edx
0x18000d9c7  mov     rax, [rax+60h]
0x18000d9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d0  nop
0x18000d9d1  lea     rcx, [rbx-18h]; this
0x18000d9d5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d9da  nop
0x18000d9db  jmp     short loc_18000D9EF
0x18000d9dd  xor     edi, edi
0x18000d9df  mov     r15, [rsp+218h+var_1E0]
0x18000d9e4  mov     r14, r15
0x18000d9e7  mov     rsi, qword ptr [rsp+218h+var_138.Data1]
0x18000d9ef  xor     edx, edx; Val
0x18000d9f1  mov     r8d, 90h; Size
0x18000d9f7  lea     rcx, [rsp+218h+pv]; void *
0x18000d9fc  call    memset_0
0x18000da01  mov     rax, [r14]
0x18000da04  mov     rdx, [rax]
0x18000da07  lea     r8, [rsp+218h+pv]
0x18000da0c  mov     rdx, [rdx+28h]
0x18000da10  lea     rcx, aUserid; "userid"
0x18000da17  call    ?FindAttribute@@YAJPEBGPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@PEAUtagHELPER_ATTRIBUTE@@@Z; FindAttribute(ushort const *,std::list<tagHELPER_ATTRIBUTE> *,tagHELPER_ATTRIBUTE *)
0x18000da1c  mov     ebx, eax
0x18000da1e  cmp     eax, 80070490h
0x18000da23  jnz     loc_18000DAED
0x18000da29  mov     rcx, [r15+50h]
0x18000da2d  mov     rax, [rcx]
0x18000da30  mov     rax, [rax+38h]
0x18000da34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da39  mov     ebx, eax
0x18000da3b  test    eax, eax
0x18000da3d  js      loc_18000DC94
0x18000da43  lea     rcx, [rsp+218h+var_1B8]; struct tagOCTET_STRING *
0x18000da48  call    ?GetSID@@YAJPEAUtagOCTET_STRING@@H@Z; GetSID(tagOCTET_STRING *,int)
0x18000da4d  mov     ebx, eax
0x18000da4f  test    eax, eax
0x18000da51  js      short loc_18000DAC8
0x18000da53  lea     rax, [rsp+218h+pv]
0x18000da58  mov     [rsp+218h+var_1F8], rax
0x18000da5d  mov     [rsp+218h+var_1F0], 1
0x18000da66  mov     [rsp+218h+var_1E8], rdi
0x18000da6b  lea     r8, [rsp+218h+var_1E8]; unsigned __int64 *
0x18000da70  mov     edx, 0FFFEh; unsigned __int64
0x18000da75  lea     rcx, aUserid; "userid"
0x18000da7c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000da81  mov     ebx, eax
0x18000da83  test    eax, eax
0x18000da85  js      short loc_18000DAC0
0x18000da87  mov     rbx, [rsp+218h+var_1E8]
0x18000da8c  lea     rcx, ds:2[rbx*2]; cb
0x18000da94  call    cs:__imp_CoTaskMemAlloc
0x18000da9a  mov     [rsp+218h+pv], rax
0x18000da9f  test    rax, rax
0x18000daa2  jnz     short loc_18000DAAB
0x18000daa4  mov     ebx, 8007000Eh
0x18000daa9  jmp     short loc_18000DAC0
0x18000daab  lea     rdx, [rbx+1]; unsigned __int64
0x18000daaf  lea     r8, aUserid; "userid"
0x18000dab6  mov     rcx, rax; unsigned __int16 *
0x18000dab9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dabe  mov     ebx, eax
0x18000dac0  mov     [rsp+218h+var_1C0], 0Eh
0x18000dac8  mov     rcx, [r15+50h]
0x18000dacc  mov     rax, [rcx]
0x18000dacf  mov     rax, [rax+40h]
0x18000dad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dad8  test    ebx, ebx
0x18000dada  js      loc_18000DC94
0x18000dae0  mov     edx, edi
0x18000dae2  test    eax, eax
0x18000dae4  jns     short loc_18000DAFA
0x18000dae6  mov     ebx, eax
0x18000dae8  jmp     loc_18000DC94
0x18000daed  mov     edx, 1
0x18000daf2  test    eax, eax
0x18000daf4  js      loc_18000DC94
0x18000dafa  lea     rax, [rsp+218h+pv]
0x18000daff  mov     [rsp+218h+var_1F8], rax
0x18000db04  mov     [rsp+218h+var_1F0], 1
0x18000db0d  mov     rcx, [rsi]
0x18000db10  test    rcx, rcx
0x18000db13  jz      short loc_18000DB37
0x18000db15  mov     rax, [rcx]
0x18000db18  lea     r9, aAutomaticallyD; "Automatically detected caller SID for g"...
0x18000db1f  lea     r8, aUsingCallerSup; "Using caller supplied SID for global pr"...
0x18000db26  test    edx, edx
0x18000db28  cmovz   r8, r9
0x18000db2c  xor     edx, edx
0x18000db2e  mov     rax, [rax+60h]
0x18000db32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db37  lea     rdx, [rsp+218h+pv]; struct tagHELPER_ATTRIBUTE *
0x18000db3c  mov     rcx, [r14]; this
0x18000db3f  call    ?AddProperty@ProblemNode@@QEAAJAEBUtagHELPER_ATTRIBUTE@@H@Z; ProblemNode::AddProperty(tagHELPER_ATTRIBUTE const &,int)
0x18000db44  mov     ebx, eax
0x18000db46  mov     [rsp+218h+var_1F8], rdi
0x18000db4b  mov     [rsp+218h+var_1F0], 0
0x18000db54  mov     rcx, [rsp+218h+pv]; pv
0x18000db59  call    cs:__imp_CoTaskMemFree
0x18000db5f  mov     [rsp+218h+pv], rdi
0x18000db64  cmp     [rsp+218h+var_1C0], 0Ah
0x18000db69  jz      short loc_18000DB84
0x18000db6b  cmp     [rsp+218h+var_1C0], 0Eh
0x18000db70  jnz     short loc_18000DB94
0x18000db72  mov     rcx, [rsp+218h+var_1B8.lpValue]; pv
0x18000db77  call    cs:__imp_CoTaskMemFree
0x18000db7d  mov     [rsp+218h+var_1B8.lpValue], rdi
0x18000db82  jmp     short loc_18000DB94
0x18000db84  mov     rcx, qword ptr [rsp+218h+var_1B8.dwLength]; pv
0x18000db89  call    cs:__imp_CoTaskMemFree
0x18000db8f  mov     qword ptr [rsp+218h+var_1B8.dwLength], rdi
0x18000db94  mov     [rsp+218h+var_1C0], edi
0x18000db98  test    ebx, ebx
0x18000db9a  js      loc_18000DC94
0x18000dba0  xor     edx, edx; Val
0x18000dba2  mov     r8d, 90h; Size
0x18000dba8  lea     rcx, [rsp+218h+pv]; void *
0x18000dbad  call    memset_0
0x18000dbb2  mov     rax, [r14]
0x18000dbb5  mov     rdx, [rax]
0x18000dbb8  lea     r8, [rsp+218h+pv]
0x18000dbbd  mov     rdx, [rdx+28h]
0x18000dbc1  lea     rcx, aAppid; "appid"
0x18000dbc8  call    ?FindAttribute@@YAJPEBGPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@PEAUtagHELPER_ATTRIBUTE@@@Z; FindAttribute(ushort const *,std::list<tagHELPER_ATTRIBUTE> *,tagHELPER_ATTRIBUTE *)
0x18000dbcd  mov     ebx, eax
0x18000dbcf  test    eax, eax
0x18000dbd1  js      loc_18000DC6A
0x18000dbd7  lea     rax, [rsp+218h+pv]
0x18000dbdc  mov     [rsp+218h+var_1F8], rax
0x18000dbe1  mov     [rsp+218h+var_1F0], 1
0x18000dbea  mov     rcx, [rsi]
0x18000dbed  test    rcx, rcx
0x18000dbf0  jz      short loc_18000DC07
0x18000dbf2  mov     rax, [rcx]
0x18000dbf5  lea     r8, aUsingCallerSup_0; "Using caller supplied Application ID fo"...
0x18000dbfc  xor     edx, edx
0x18000dbfe  mov     rax, [rax+60h]
0x18000dc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc07  lea     rdx, [rsp+218h+pv]; struct tagHELPER_ATTRIBUTE *
0x18000dc0c  mov     rcx, [r14]; this
0x18000dc0f  call    ?AddProperty@ProblemNode@@QEAAJAEBUtagHELPER_ATTRIBUTE@@H@Z; ProblemNode::AddProperty(tagHELPER_ATTRIBUTE const &,int)
0x18000dc14  mov     ebx, eax
0x18000dc16  mov     [rsp+218h+var_1F8], rdi
0x18000dc1b  mov     [rsp+218h+var_1F0], 0
0x18000dc24  mov     rcx, [rsp+218h+pv]; pv
0x18000dc29  call    cs:__imp_CoTaskMemFree
0x18000dc2f  mov     [rsp+218h+pv], rdi
0x18000dc34  cmp     [rsp+218h+var_1C0], 0Ah
0x18000dc39  jz      short loc_18000DC54
0x18000dc3b  cmp     [rsp+218h+var_1C0], 0Eh
0x18000dc40  jnz     short loc_18000DC64
0x18000dc42  mov     rcx, [rsp+218h+var_1B8.lpValue]; pv
0x18000dc47  call    cs:__imp_CoTaskMemFree
0x18000dc4d  mov     [rsp+218h+var_1B8.lpValue], rdi
0x18000dc52  jmp     short loc_18000DC64
0x18000dc54  mov     rcx, qword ptr [rsp+218h+var_1B8.dwLength]; pv
0x18000dc59  call    cs:__imp_CoTaskMemFree
0x18000dc5f  mov     qword ptr [rsp+218h+var_1B8.dwLength], rdi
0x18000dc64  mov     [rsp+218h+var_1C0], edi
0x18000dc68  jmp     short loc_18000DC90
0x18000dc6a  cmp     eax, 80070490h
0x18000dc6f  jnz     short loc_18000DC90
0x18000dc71  mov     rcx, [rsi]
0x18000dc74  test    rcx, rcx
0x18000dc77  jz      short loc_18000DC8E
0x18000dc79  mov     rax, [rcx]
0x18000dc7c  lea     r8, aApplicationIdW; "Application ID was not supplied by call"...
0x18000dc83  xor     edx, edx
0x18000dc85  mov     rax, [rax+60h]
0x18000dc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc8e  mov     ebx, edi
0x18000dc90  test    ebx, ebx
0x18000dc92  jns     short loc_18000DCDF
0x18000dc94  xor     edx, edx; Val
0x18000dc96  mov     r8d, 100h; Size
0x18000dc9c  lea     rcx, [rsp+218h+var_128]; void *
0x18000dca4  call    memset_0
0x18000dca9  mov     r9d, ebx
0x18000dcac  lea     r8, aErrorWhileAddi; "Error while adding entries to global pr"...
0x18000dcb3  mov     edx, 80h; unsigned __int64
0x18000dcb8  lea     rcx, [rsp+218h+var_128]; unsigned __int16 *
0x18000dcc0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dcc5  mov     rcx, [rsi]
0x18000dcc8  mov     rax, [rcx]
0x18000dccb  lea     r8, [rsp+218h+var_128]
0x18000dcd3  xor     edx, edx
0x18000dcd5  mov     rax, [rax+60h]
0x18000dcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcde  nop
0x18000dcdf  lea     rcx, [rsp+218h+var_1F8]
0x18000dce4  call    ??1?$TNDFDeallocator@PEAUtagHELPER_ATTRIBUTE@@$1?FreeHelperAttributes@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>(void)
0x18000dce9  mov     eax, ebx
0x18000dceb  mov     rcx, [rsp+218h+var_20]
0x18000dcf3  xor     rcx, rsp; StackCookie
0x18000dcf6  call    __security_check_cookie
0x18000dcfb  lea     r11, [rsp+218h+var_18]
0x18000dd03  mov     rbx, [r11+28h]
0x18000dd07  mov     rsi, [r11+30h]
0x18000dd0b  mov     rsp, r11
0x18000dd0e  pop     r15
0x18000dd10  pop     r14
0x18000dd12  pop     rdi
0x18000dd13  retn
```
