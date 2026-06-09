# PTMergeAndValidatePrintTicketImp(HPTPROVIDER__ *,IXMLDOMDocument2 *,IXMLDOMDocument2 *,EPrintTicketScope,IXMLDOMDocument2 * *,ushort * *)

- ea: `0x18000e608`
- end: `0x18000ea38`
- name: `?PTMergeAndValidatePrintTicketImp@@YAJPEAUHPTPROVIDER__@@PEAUIXMLDOMDocument2@@1W4EPrintTicketScope@@PEAPEAU2@PEAPEAG@Z`
- size: `1072`
- prototype: `__int64 __fastcall(HPTPROVIDER this, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 *, enum EPrintTicketScope, struct IXMLDOMDocument2 **, IRecordInfo *ppv)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800141b0`

## callees

- `0x180003708`
- `0x180005e70`
- `0x180007660`
- `0x180008498`
- `0x180008a68`
- `0x180008da4`
- `0x180009150`
- `0x180009214`
- `0x180009268`
- `0x180009354`
- `0x180009514`
- `0x18000dee8`
- `0x18000df24`
- `0x18000e608`
- `0x18000ea40`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e756`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e756`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e78c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e78c`
- `OLEAUT32!__imp_VariantInit` at `0x18000e8fc`
- `OLEAUT32!__imp_VariantInit` at `0x18000e8fc`
- `OLEAUT32!__imp_VariantClear` at `0x18000e952`
- `OLEAUT32!__imp_VariantClear` at `0x18000e952`

## pseudocode

```c
__int64 __fastcall PTMergeAndValidatePrintTicketImp(
        HPTPROVIDER this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 *a3,
        enum EPrintTicketScope a4,
        struct IXMLDOMDocument2 **a5,
        IRecordInfo *ppv)
{
  struct IXMLDOMDocument2 *v6; // rsi
  struct IXMLDOMDocument2 *v7; // r15
  struct IXMLDOMDocument2 **v10; // r13
  int (*v11)(HPTPROVIDER, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **, unsigned __int16 **); // rdx
  int IsValidPrintTicket; // ebx
  const wchar_t *v13; // rdi
  unsigned int v14; // r15d
  int v15; // edi
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // r14d
  unsigned __int16 *v19; // rbx
  struct NPrintTicketUtil::TFeatureListRoot *v21; // r8
  struct NPrintTicketUtil::CPrintTicketWrapper *v22; // r15
  int v23; // r9d
  unsigned int v24; // r12d
  struct NPrintTicketUtil::TFeatureListRoot *v25; // r8
  struct NPrintTicketUtil::CPrintTicketWrapper *v26; // r8
  struct IPrintTicketProvider *v27; // rax
  struct NPrintTicketUtil::CPrintTicketWrapper *v28; // rsi
  struct IXMLDOMDocument2 **v29; // rdx
  int v30; // r9d
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  int v32; // eax
  struct NPrintTicketUtil::TFeatureListRoot *v33; // r8
  VARIANTARG pvarg; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v35; // [rsp+48h] [rbp-99h]
  __m256i v36; // [rsp+50h] [rbp-91h] BYREF
  __int16 v37; // [rsp+70h] [rbp-71h]
  int v38; // [rsp+74h] [rbp-6Dh]
  void **v39; // [rsp+78h] [rbp-69h] BYREF
  __int128 v40; // [rsp+80h] [rbp-61h]
  __int64 v41; // [rsp+90h] [rbp-51h]
  __int16 v42; // [rsp+98h] [rbp-49h]
  int v43; // [rsp+9Ch] [rbp-45h]
  void **v44; // [rsp+A0h] [rbp-41h] BYREF
  __int128 v45; // [rsp+A8h] [rbp-39h]
  __int64 v46; // [rsp+B8h] [rbp-29h]
  __int16 v47; // [rsp+C0h] [rbp-21h]
  int v48; // [rsp+C4h] [rbp-1Dh]
  __int64 v49; // [rsp+C8h] [rbp-19h] BYREF
  __int128 v50; // [rsp+D8h] [rbp-9h] BYREF
  __int64 v51; // [rsp+E8h] [rbp+7h]
  struct NPrintTicketUtil::CPrintTicketWrapper *v52; // [rsp+138h] [rbp+57h] BYREF
  struct IXMLDOMDocument2 *v53; // [rsp+140h] [rbp+5Fh]
  struct NPrintTicketUtil::CPrintTicketWrapper *v54; // [rsp+150h] [rbp+6Fh]

  LODWORD(v54) = a4;
  v53 = a2;
  v6 = (struct IXMLDOMDocument2 *)&v49;
  v7 = a2;
  v49 = 0;
  v44 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v46 = 0;
  if ( ppv )
    v6 = (struct IXMLDOMDocument2 *)ppv;
  v47 = 0;
  v48 = 0;
  v39 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v36.m256i_i64[0] = (__int64)&NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v37 = 0;
  v38 = 0;
  v52 = 0;
  v45 = 0;
  v40 = 0;
  memset(&v36.m256i_u64[1], 0, 24);
  if ( !a2 || (v10 = a5) == 0 || !this || this != *((HPTPROVIDER *)this + 2) )
  {
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v36);
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v39);
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v44);
    return 2147942487LL;
  }
  *a5 = 0;
  IsValidPrintTicket = NPrintTicketUtil::IsValidPrintTicket(a2, v6, (unsigned __int16 **)a3);
  v13 = L"Base ticket: ";
  if ( IsValidPrintTicket != 1 )
    v13 = &psz;
  if ( IsValidPrintTicket )
  {
    v14 = -2147221501;
  }
  else
  {
    if ( !a3 )
    {
      v15 = 262145;
      goto LABEL_26;
    }
    IsValidPrintTicket = NPrintTicketUtil::IsValidPrintTicket(a3, v6, 0);
    v13 = L"Delta ticket: ";
    v14 = -2147221499;
  }
  if ( IsValidPrintTicket != 1 )
  {
    v15 = 262145;
    if ( IsValidPrintTicket < 0 )
    {
LABEL_50:
      NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v36);
      NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v39);
      NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v44);
      return (unsigned int)IsValidPrintTicket;
    }
    v7 = v53;
LABEL_26:
    IsValidPrintTicket = TProviderInfo::GetSupportedFeaturesList(
                           (TProviderInfo *)this,
                           v11,
                           &v52,
                           (unsigned __int16 **)v6);
    if ( IsValidPrintTicket < 0 )
      goto LABEL_50;
    IsValidPrintTicket = NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
                           (NPrintTicketUtil::CPrintTicketWrapper *)&v44,
                           v7,
                           0);
    if ( IsValidPrintTicket < 0 )
      goto LABEL_50;
    v22 = v52;
    IsValidPrintTicket = NPrintTicketUtil::AutoMapPrintTicketToFeatureList((NPrintTicketUtil *)&v44, v52, v21);
    if ( IsValidPrintTicket < 0 )
      goto LABEL_50;
    if ( a3 )
    {
      IsValidPrintTicket = NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
                             (NPrintTicketUtil::CPrintTicketWrapper *)&v39,
                             a3,
                             0);
      if ( IsValidPrintTicket < 0 )
        goto LABEL_50;
      v24 = (unsigned int)v54;
      IsValidPrintTicket = NPrintTicketUtil::FilterPrintTicket(
                             (NPrintTicketUtil *)&v39,
                             (struct NPrintTicketUtil::CPrintTicketWrapper *)(unsigned int)v54,
                             kPTPageScope,
                             v23);
      if ( IsValidPrintTicket < 0 )
        goto LABEL_50;
      IsValidPrintTicket = NPrintTicketUtil::AutoMapPrintTicketToFeatureList((NPrintTicketUtil *)&v39, v22, v25);
      if ( IsValidPrintTicket < 0 )
        goto LABEL_50;
      IsValidPrintTicket = NPrintTicketUtil::MergeTickets(
                             (NPrintTicketUtil *)&v44,
                             (struct NPrintTicketUtil::CPrintTicketWrapper *)&v39,
                             v26);
      if ( IsValidPrintTicket < 0 )
        goto LABEL_50;
    }
    else
    {
      v24 = (unsigned int)v54;
    }
    v27 = TProviderInfo::Provider((TProviderInfo *)this);
    v52 = 0;
    v28 = (struct NPrintTicketUtil::CPrintTicketWrapper *)v27;
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v52);
    if ( v28 )
    {
      v52 = v28;
      ppv = 0;
      IsValidPrintTicket = NPrintTicketUtil::CreateDomDocument((LPVOID *)&ppv, v29);
      if ( IsValidPrintTicket >= 0 )
      {
        *(_OWORD *)&pvarg.decVal.Lo32 = 0;
        v35 = 0;
        VariantInit((VARIANTARG *)&pvarg.decVal.8);
        pvarg.iVal = 13;
        pvarg.pRecInfo = ppv;
        ((void (__fastcall *)(IRecordInfo *))ppv->lpVtbl->AddRef)(ppv);
        lpVtbl = v53->lpVtbl;
        v50 = *(_OWORD *)&pvarg.decVal.Lo32;
        v51 = v35;
        IsValidPrintTicket = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int128 *))lpVtbl->save)(v53, &v50);
        VariantClear((VARIANTARG *)&pvarg.decVal.8);
        if ( IsValidPrintTicket >= 0 )
        {
          v32 = (*(__int64 (__fastcall **)(struct NPrintTicketUtil::CPrintTicketWrapper *, IRecordInfo *))(*(_QWORD *)v28 + 72LL))(
                  v28,
                  ppv);
          v15 = v32;
          if ( v32 >= 0 )
            v32 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
                    (NPrintTicketUtil::CPrintTicketWrapper *)&v36,
                    (struct IXMLDOMDocument2 *)ppv,
                    0);
          IsValidPrintTicket = v32;
        }
      }
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&ppv);
    }
    else
    {
      v52 = 0;
      v15 = ValidateWithoutPlugin(this, &v44, &v36);
      IsValidPrintTicket = v15;
    }
    if ( IsValidPrintTicket >= 0 )
      IsValidPrintTicket = NPrintTicketUtil::FilterPrintTicket(
                             (NPrintTicketUtil *)&v36,
                             (struct NPrintTicketUtil::CPrintTicketWrapper *)v24,
                             kPTPageScope,
                             v30);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v52);
    if ( IsValidPrintTicket >= 0 )
    {
      IsValidPrintTicket = NPrintTicketUtil::PrunePrintTicketToFeatureList((NPrintTicketUtil *)&v36, v22, v33);
      if ( IsValidPrintTicket >= 0 )
      {
        IsValidPrintTicket = NPrintTicketUtil::CPrintTicketWrapper::GetXML(
                               (NPrintTicketUtil::CPrintTicketWrapper *)&v36,
                               v10);
        if ( IsValidPrintTicket >= 0 )
          IsValidPrintTicket = v15;
      }
    }
    goto LABEL_50;
  }
  if ( v6->lpVtbl )
  {
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( v13[v17] );
    do
      ++v16;
    while ( *((_WORD *)&v6->lpVtbl->QueryInterface + v16) );
    v18 = v17 + v16;
    v19 = SysAllocStringLen(0, (int)v17 + (int)v16);
    if ( v19 )
    {
      if ( (int)StringCchPrintfW(v19, v18 + 1, L"%s%s", v13, v6->lpVtbl) >= 0 )
      {
        SysFreeString((BSTR)v6->lpVtbl);
        v6->lpVtbl = (struct IXMLDOMDocument2Vtbl *)v19;
      }
    }
  }
  else
  {
    v14 = -2147418113;
  }
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v36);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v39);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v44);
  return v14;
}

```

## disassembly

```asm
0x18000e608  mov     rax, rsp
0x18000e60b  mov     [rax+18h], rbx
0x18000e60f  mov     [rax+20h], r9d
0x18000e613  mov     [rax+10h], rdx
0x18000e617  push    rbp
0x18000e618  push    rsi
0x18000e619  push    rdi
0x18000e61a  push    r12
0x18000e61c  push    r13
0x18000e61e  push    r14
0x18000e620  push    r15
0x18000e622  lea     rbp, [rax-4Fh]
0x18000e626  sub     rsp, 0F0h
0x18000e62d  mov     rax, [rbp+47h+ppv]
0x18000e631  lea     rsi, [rbp+47h+var_60]
0x18000e635  xorps   xmm0, xmm0
0x18000e638  mov     r15, rdx
0x18000e63b  xor     edx, edx
0x18000e63d  mov     r14, rcx
0x18000e640  lea     rcx, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18000e647  mov     [rbp+47h+var_60], rdx
0x18000e64b  test    rax, rax
0x18000e64e  mov     [rbp+47h+var_88], rcx
0x18000e652  mov     r12, r8
0x18000e655  mov     [rbp+47h+var_70], rdx
0x18000e659  cmovnz  rsi, rax
0x18000e65d  mov     [rbp+47h+var_68], dx
0x18000e661  mov     [rbp+47h+var_64], edx
0x18000e664  mov     [rbp+47h+var_B0], rcx
0x18000e668  mov     [rbp+47h+var_98], rdx
0x18000e66c  mov     [rbp+47h+var_90], dx
0x18000e670  mov     [rbp+47h+var_8C], edx
0x18000e673  mov     qword ptr [rsp+120h+var_D8], rcx
0x18000e678  mov     [rbp+47h+var_C0], rdx
0x18000e67c  mov     [rbp+47h+var_B8], dx
0x18000e680  mov     [rbp+47h+var_B4], edx
0x18000e683  mov     [rbp+47h+arg_0], rdx
0x18000e687  movdqu  [rbp+47h+var_80], xmm0
0x18000e68c  movdqu  [rbp+47h+var_A8], xmm0
0x18000e691  movdqu  xmmword ptr [rsp+120h+var_D8+8], xmm0
0x18000e697  test    r15, r15
0x18000e69a  jz      loc_18000E9FC
0x18000e6a0  mov     r13, [rbp+47h+arg_20]
0x18000e6a4  test    r13, r13
0x18000e6a7  jz      loc_18000E9FC
0x18000e6ad  test    r14, r14
0x18000e6b0  jz      loc_18000E9FC
0x18000e6b6  cmp     r14, [r14+10h]
0x18000e6ba  jnz     loc_18000E9FC
0x18000e6c0  mov     [r13+0], rdx
0x18000e6c4  mov     rcx, r15; this
0x18000e6c7  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x18000e6ca  call    ?IsValidPrintTicket@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAG@Z; NPrintTicketUtil::IsValidPrintTicket(IXMLDOMDocument2 *,ushort * *)
0x18000e6cf  mov     ebx, eax
0x18000e6d1  lea     rdi, aBaseTicket; "Base ticket: "
0x18000e6d8  cmp     ebx, 1
0x18000e6db  lea     rax, psz
0x18000e6e2  cmovnz  rdi, rax
0x18000e6e6  xor     r8d, r8d; unsigned __int16 **
0x18000e6e9  test    ebx, ebx
0x18000e6eb  jnz     short loc_18000E71B
0x18000e6ed  test    r12, r12
0x18000e6f0  jz      short loc_18000E711
0x18000e6f2  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x18000e6f5  mov     rcx, r12; this
0x18000e6f8  call    ?IsValidPrintTicket@NPrintTicketUtil@@YAJPEAUIXMLDOMDocument2@@PEAPEAG@Z; NPrintTicketUtil::IsValidPrintTicket(IXMLDOMDocument2 *,ushort * *)
0x18000e6fd  mov     ebx, eax
0x18000e6ff  lea     rdi, aDeltaTicket; "Delta ticket: "
0x18000e706  xor     r8d, r8d
0x18000e709  mov     r15d, 80040005h
0x18000e70f  jmp     short loc_18000E721
0x18000e711  mov     edi, 40001h
0x18000e716  jmp     loc_18000E7D2
0x18000e71b  mov     r15d, 80040003h
0x18000e721  cmp     ebx, 1
0x18000e724  jnz     loc_18000E7C1
0x18000e72a  mov     rdx, [rsi]
0x18000e72d  test    rdx, rdx
0x18000e730  jz      short loc_18000E797
0x18000e732  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e736  mov     rcx, rax
0x18000e739  inc     rcx
0x18000e73c  cmp     [rdi+rcx*2], r8w
0x18000e741  jnz     short loc_18000E739
0x18000e743  inc     rax
0x18000e746  cmp     [rdx+rax*2], r8w
0x18000e74b  jnz     short loc_18000E743
0x18000e74d  lea     r14d, [rcx+rax]
0x18000e751  xor     ecx, ecx; strIn
0x18000e753  mov     edx, r14d; ui
0x18000e756  call    cs:__imp_SysAllocStringLen
0x18000e75c  mov     rbx, rax
0x18000e75f  test    rax, rax
0x18000e762  jz      short loc_18000E79D
0x18000e764  lea     eax, [r14+1]
0x18000e768  mov     r9, rdi
0x18000e76b  movsxd  rdx, eax; unsigned __int64
0x18000e76e  lea     r8, aSS; "%s%s"
0x18000e775  mov     rax, [rsi]
0x18000e778  mov     rcx, rbx; unsigned __int16 *
0x18000e77b  mov     [rsp+20h], rax
0x18000e780  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e785  test    eax, eax
0x18000e787  js      short loc_18000E79D
0x18000e789  mov     rcx, [rsi]; bstrString
0x18000e78c  call    cs:__imp_SysFreeString
0x18000e792  mov     [rsi], rbx
0x18000e795  jmp     short loc_18000E79D
0x18000e797  mov     r15d, 8000FFFFh
0x18000e79d  lea     rcx, [rsp+120h+var_D8]; this
0x18000e7a2  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000e7a7  lea     rcx, [rbp+47h+var_B0]; this
0x18000e7ab  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000e7b0  lea     rcx, [rbp+47h+var_88]; this
0x18000e7b4  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000e7b9  mov     eax, r15d
0x18000e7bc  jmp     loc_18000EA1D
0x18000e7c1  mov     edi, 40001h
0x18000e7c6  test    ebx, ebx
0x18000e7c8  js      loc_18000E9DC
0x18000e7ce  mov     r15, [rbp+47h+arg_8]
0x18000e7d2  mov     r9, rsi; unsigned __int16 **
0x18000e7d5  lea     r8, [rbp+47h+arg_0]; struct NPrintTicketUtil::TFeatureListRoot **
0x18000e7d9  mov     rcx, r14; this
0x18000e7dc  call    ?GetSupportedFeaturesList@TProviderInfo@@QEAAJP6AJPEAUHPTPROVIDER__@@PEAUIXMLDOMDocument2@@PEAPEAU3@PEAPEAG@ZPEAPEAUTFeatureListRoot@NPrintTicketUtil@@3@Z; TProviderInfo::GetSupportedFeaturesList(long (*)(HPTPROVIDER__ *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *,ushort * *),NPrintTicketUtil::TFeatureListRoot * *,ushort * *)
0x18000e7e1  mov     ebx, eax
0x18000e7e3  test    eax, eax
0x18000e7e5  js      loc_18000E9DC
0x18000e7eb  xor     r8d, r8d; int
0x18000e7ee  lea     rcx, [rbp+47h+var_88]; this
0x18000e7f2  mov     rdx, r15; struct IXMLDOMDocument2 *
0x18000e7f5  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x18000e7fa  mov     ebx, eax
0x18000e7fc  test    eax, eax
0x18000e7fe  js      loc_18000E9DC
0x18000e804  mov     r15, [rbp+47h+arg_0]
0x18000e808  lea     rcx, [rbp+47h+var_88]; this
0x18000e80c  mov     rdx, r15; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000e80f  call    ?AutoMapPrintTicketToFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::AutoMapPrintTicketToFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot *)
0x18000e814  mov     ebx, eax
0x18000e816  test    eax, eax
0x18000e818  js      loc_18000E9DC
0x18000e81e  test    r12, r12
0x18000e821  jz      short loc_18000E887
0x18000e823  xor     r8d, r8d; int
0x18000e826  lea     rcx, [rbp+47h+var_B0]; this
0x18000e82a  mov     rdx, r12; struct IXMLDOMDocument2 *
0x18000e82d  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x18000e832  mov     ebx, eax
0x18000e834  test    eax, eax
0x18000e836  js      loc_18000E9DC
0x18000e83c  mov     r12d, dword ptr [rbp+47h+arg_18]
0x18000e840  lea     rcx, [rbp+47h+var_B0]; this
0x18000e844  mov     edx, r12d; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000e847  xor     r8d, r8d; enum EPrintTicketScope
0x18000e84a  call    ?FilterPrintTicket@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@W4EPrintTicketScope@@H@Z; NPrintTicketUtil::FilterPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,EPrintTicketScope,int)
0x18000e84f  mov     ebx, eax
0x18000e851  test    eax, eax
0x18000e853  js      loc_18000E9DC
0x18000e859  mov     rdx, r15; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000e85c  lea     rcx, [rbp+47h+var_B0]; this
0x18000e860  call    ?AutoMapPrintTicketToFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::AutoMapPrintTicketToFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot *)
0x18000e865  mov     ebx, eax
0x18000e867  test    eax, eax
0x18000e869  js      loc_18000E9DC
0x18000e86f  lea     rdx, [rbp+47h+var_B0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000e873  lea     rcx, [rbp+47h+var_88]; this
0x18000e877  call    ?MergeTickets@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@0@Z; NPrintTicketUtil::MergeTickets(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::CPrintTicketWrapper *)
0x18000e87c  mov     ebx, eax
0x18000e87e  test    eax, eax
0x18000e880  jns     short loc_18000E88B
0x18000e882  jmp     loc_18000E9DC
0x18000e887  mov     r12d, dword ptr [rbp+47h+arg_18]
0x18000e88b  mov     rcx, r14; this
0x18000e88e  call    ?Provider@TProviderInfo@@QEBAPEAUIPrintTicketProvider@@XZ; TProviderInfo::Provider(void)
0x18000e893  lea     rcx, [rbp+47h+arg_0]
0x18000e897  mov     [rbp+47h+arg_0], 0
0x18000e89f  mov     rsi, rax
0x18000e8a2  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000e8a7  test    rsi, rsi
0x18000e8aa  jnz     short loc_18000E8CA
0x18000e8ac  lea     r8, [rsp+120h+var_D8]
0x18000e8b1  mov     [rbp+47h+arg_0], rsi
0x18000e8b5  lea     rdx, [rbp+47h+var_88]
0x18000e8b9  mov     rcx, r14
0x18000e8bc  call    ValidateWithoutPlugin
0x18000e8c1  mov     edi, eax
0x18000e8c3  mov     ebx, eax
0x18000e8c5  jmp     loc_18000E991
0x18000e8ca  xor     r14d, r14d
0x18000e8cd  mov     [rbp+47h+arg_0], rsi
0x18000e8d1  lea     rcx, [rbp+47h+ppv]; ppv
0x18000e8d5  mov     [rbp+47h+ppv], r14
0x18000e8d9  call    ?CreateDomDocument@NPrintTicketUtil@@YAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CreateDomDocument(IXMLDOMDocument2 * *)
0x18000e8de  mov     ebx, eax
0x18000e8e0  test    eax, eax
0x18000e8e2  js      loc_18000E988
0x18000e8e8  xorps   xmm0, xmm0
0x18000e8eb  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x18000e8f0  xor     eax, eax
0x18000e8f2  movups  xmmword ptr [rsp+120h+pvarg+8], xmm0
0x18000e8f7  mov     [rsp+120h+var_E0], rax
0x18000e8fc  call    cs:__imp_VariantInit
0x18000e902  mov     rcx, [rbp+47h+ppv]
0x18000e906  lea     eax, [r14+0Dh]
0x18000e90a  mov     word ptr [rsp+120h+pvarg+8], ax
0x18000e90f  mov     qword ptr [rsp+120h+pvarg+10h], rcx
0x18000e914  mov     rax, [rcx]
0x18000e917  mov     rax, [rax+8]
0x18000e91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e920  mov     rcx, [rbp+47h+arg_8]
0x18000e924  lea     rdx, [rbp+47h+var_50]
0x18000e928  movups  xmm0, xmmword ptr [rsp+120h+pvarg+8]
0x18000e92d  movsd   xmm1, [rsp+120h+var_E0]
0x18000e933  mov     rax, [rcx]
0x18000e936  movaps  [rbp+47h+var_50], xmm0
0x18000e93a  movsd   [rbp+47h+var_40], xmm1
0x18000e93f  mov     rax, [rax+210h]
0x18000e946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94b  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x18000e950  mov     ebx, eax
0x18000e952  call    cs:__imp_VariantClear
0x18000e958  test    ebx, ebx
0x18000e95a  js      short loc_18000E988
0x18000e95c  mov     rax, [rsi]
0x18000e95f  mov     rcx, rsi
0x18000e962  mov     rdx, [rbp+47h+ppv]
0x18000e966  mov     rax, [rax+48h]
0x18000e96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e96f  mov     edi, eax
0x18000e971  test    eax, eax
0x18000e973  js      short loc_18000E986
0x18000e975  mov     rdx, [rbp+47h+ppv]; struct IXMLDOMDocument2 *
0x18000e979  lea     rcx, [rsp+120h+var_D8]; this
0x18000e97e  xor     r8d, r8d; int
0x18000e981  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x18000e986  mov     ebx, eax
0x18000e988  lea     rcx, [rbp+47h+ppv]
0x18000e98c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000e991  test    ebx, ebx
0x18000e993  js      short loc_18000E9A7
0x18000e995  xor     r8d, r8d; enum EPrintTicketScope
0x18000e998  lea     rcx, [rsp+120h+var_D8]; this
0x18000e99d  mov     edx, r12d; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000e9a0  call    ?FilterPrintTicket@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@W4EPrintTicketScope@@H@Z; NPrintTicketUtil::FilterPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,EPrintTicketScope,int)
0x18000e9a5  mov     ebx, eax
0x18000e9a7  lea     rcx, [rbp+47h+arg_0]
0x18000e9ab  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000e9b0  test    ebx, ebx
0x18000e9b2  js      short loc_18000E9DC
0x18000e9b4  mov     rdx, r15; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000e9b7  lea     rcx, [rsp+120h+var_D8]; this
0x18000e9bc  call    ?PrunePrintTicketToFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::PrunePrintTicketToFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot *)
0x18000e9c1  mov     ebx, eax
0x18000e9c3  test    eax, eax
0x18000e9c5  js      short loc_18000E9DC
0x18000e9c7  mov     rdx, r13; struct IXMLDOMDocument2 **
0x18000e9ca  lea     rcx, [rsp+120h+var_D8]; this
0x18000e9cf  call    ?GetXML@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetXML(IXMLDOMDocument2 * *)
0x18000e9d4  mov     ebx, eax
0x18000e9d6  test    eax, eax
0x18000e9d8  js      short loc_18000E9DC
0x18000e9da  mov     ebx, edi
0x18000e9dc  lea     rcx, [rsp+120h+var_D8]; this
0x18000e9e1  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000e9e6  lea     rcx, [rbp+47h+var_B0]; this
0x18000e9ea  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000e9ef  lea     rcx, [rbp+47h+var_88]; this
0x18000e9f3  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000e9f8  mov     eax, ebx
0x18000e9fa  jmp     short loc_18000EA1D
0x18000e9fc  lea     rcx, [rsp+120h+var_D8]; this
0x18000ea01  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000ea06  lea     rcx, [rbp+47h+var_B0]; this
0x18000ea0a  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000ea0f  lea     rcx, [rbp+47h+var_88]; this
0x18000ea13  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18000ea18  mov     eax, 80070057h
0x18000ea1d  mov     rbx, [rsp+120h+arg_10]
0x18000ea25  add     rsp, 0F0h
0x18000ea2c  pop     r15
0x18000ea2e  pop     r14
0x18000ea30  pop     r13
0x18000ea32  pop     r12
0x18000ea34  pop     rdi
0x18000ea35  pop     rsi
0x18000ea36  pop     rbp
0x18000ea37  retn
```
