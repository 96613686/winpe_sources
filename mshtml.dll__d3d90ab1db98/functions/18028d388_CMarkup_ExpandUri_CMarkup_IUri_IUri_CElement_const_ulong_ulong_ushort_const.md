# CMarkup::ExpandUri(CMarkup *,IUri *,IUri * *,CElement const *,ulong,ulong,ushort const *)

- ea: `0x18028d388`
- end: `0x18028dada`
- name: `?ExpandUri@CMarkup@@SAJPEAV1@PEAUIUri@@PEAPEAU2@PEBVCElement@@KKPEBG@Z`
- size: `1874`
- prototype: `__int64 __usercall@<rax>(struct CMarkup *this@<rcx>, struct IUri *@<rdx>, struct IUri **@<r8>, const struct CElement *@<r9>, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `16`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802155c0`
- `0x18026f5b0`
- `0x18028cad0`
- `0x18028ee58`
- `0x1803033ec`
- `0x18047eb54`
- `0x1805f801c`
- `0x180671614`
- `0x180836998`
- `0x180889920`
- `0x180899358`
- `0x1808d2f10`
- `0x1808fb4a8`
- `0x1808fb8c0`
- `0x1809a4264`
- `0x180a772ac`

## callees

- `0x1801086ac`
- `0x1801393a8`
- `0x180149610`
- `0x18025f744`
- `0x18028d33c`
- `0x18028d388`
- `0x18028dae0`
- `0x1803ddae0`
- `0x1804067d4`
- `0x180422abc`
- `0x180429e94`
- `0x18083bed4`
- `0x1808990bc`
- `0x181104010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18028dab0`
- `msvcrt!_wcsnicmp` at `0x18028dab0`
- `iertutil!GetIUriPriv` at `0x18028d9a2`
- `iertutil!GetIUriPriv` at `0x18028d9a2`
- `iertutil!CreateUri` at `0x18028d7b4`
- `iertutil!CreateUri` at `0x18028d86b`
- `iertutil!CreateUri` at `0x18028d8ef`
- `iertutil!CreateUri` at `0x18028d7b4`
- `iertutil!CreateUri` at `0x18028d86b`
- `iertutil!CreateUri` at `0x18028d8ef`
- `urlmon!CoInternetQueryInfo` at `0x18028d77d`
- `urlmon!CoInternetQueryInfo` at `0x18028d77d`
- `urlmon!CoInternetCombineIUri` at `0x18028d5aa`
- `urlmon!CoInternetCombineIUri` at `0x18028d7e3`
- `urlmon!CoInternetCombineIUri` at `0x18028d5aa`
- `urlmon!CoInternetCombineIUri` at `0x18028d7e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18028d9fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18028dac1`
- `OLEAUT32!__imp_SysFreeString` at `0x18028d9fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18028dac1`
- `OLEAUT32!__imp_SysStringLen` at `0x18028da39`
- `OLEAUT32!__imp_SysStringLen` at `0x18028da39`

## pseudocode

```c
__int64 __fastcall CMarkup::ExpandUri(
        struct CMarkup *this,
        struct IUri *a2,
        struct IUri **a3,
        const struct CElement *a4,
        char a5,
        DWORD a6,
        struct IUri *a7)
{
  DWORD v9; // ecx
  int v10; // r13d
  const struct CMarkup *MarkupPtr; // rbx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r14
  struct CMarkup *v14; // rdi
  CDoc *v15; // rax
  struct CMarkupTopElemCache *v16; // rax
  __int64 v17; // rax
  const unsigned __int16 *OriginUrl; // rax
  IUri *UriRaw; // rax
  OLECHAR *v20; // rbx
  IUri *v21; // rdi
  BOOL v22; // r14d
  BOOL v23; // r12d
  int v24; // edi
  IUri **v25; // r14
  DWORD v26; // r12d
  struct IUriVtbl *lpVtbl; // rax
  CDoc *v29; // rax
  const WCHAR *v30; // rdi
  IUri **v31; // rcx
  IUri *v32; // rdi
  DWORD v33; // edx
  const WCHAR *v34; // rcx
  CDoc *v35; // rax
  struct CMarkup *v36; // rcx
  const unsigned __int16 *v37; // r12
  UINT v38; // ebx
  struct CDoc *v39; // rax
  OLECHAR *v40; // [rsp+48h] [rbp-61h] BYREF
  IUri *pBaseUri; // [rsp+50h] [rbp-59h] BYREF
  int pvBuffer; // [rsp+58h] [rbp-51h] BYREF
  void **v43; // [rsp+60h] [rbp-49h]
  IUri *v44; // [rsp+68h] [rbp-41h]
  unsigned int v45; // [rsp+70h] [rbp-39h]
  BSTR bstrString[2]; // [rsp+78h] [rbp-31h] BYREF
  UINT v47; // [rsp+88h] [rbp-21h] BYREF
  int v48; // [rsp+90h] [rbp-19h] BYREF
  DWORD dwCombineFlags; // [rsp+94h] [rbp-15h]
  DWORD pcbBuffer; // [rsp+98h] [rbp-11h] BYREF
  const unsigned __int16 *v51; // [rsp+A0h] [rbp-9h] BYREF
  const unsigned __int16 *Url; // [rsp+A8h] [rbp-1h]
  IUri **ppCombinedUri; // [rsp+108h] [rbp+5Fh] BYREF

  ppCombinedUri = a3;
  pvBuffer = 0;
  v43 = &CUString::`vftable';
  pcbBuffer = 0;
  pBaseUri = 0;
  v44 = 0;
  v45 = 11;
  v47 = 0;
  *(_OWORD *)bstrString = 0;
  if ( !a3 )
  {
    LODWORD(v20) = -2147024809;
LABEL_40:
    v10 = 0;
    goto LABEL_41;
  }
  v9 = 100663296;
  v10 = 1;
  if ( a6 != -1 )
    v9 = a6;
  dwCombineFlags = v9;
  if ( !a2 )
  {
    LODWORD(v20) = CreateUri(&Source, 0x3002B81u, 0, a3);
    goto LABEL_37;
  }
  MarkupPtr = this;
  if ( this
    || (Url = 0, (unsigned __int64)a4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL)
    && ((MarkupPtr = CElement::GetMarkupPtr(a4)) != 0
     || (v35 = CElement::Doc(a4), (MarkupPtr = CDoc::PrimaryMarkup(v35)) != 0)) )
  {
    Url = CMarkup::GetUrl(MarkupPtr);
    if ( MarkupPtr )
    {
      if ( *(__int64 (__fastcall **)())(*(_QWORD *)MarkupPtr + 984LL) != _vtguard )
        _report_securityfailure(1, v12);
      if ( (*(unsigned __int8 (__fastcall **)(const struct CMarkup *))(*(_QWORD *)MarkupPtr + 1216LL))(MarkupPtr) )
      {
        OriginUrl = CMarkup::GetUrl(MarkupPtr);
        goto LABEL_19;
      }
    }
  }
  v13 = 0;
  v14 = MarkupPtr;
  if ( MarkupPtr )
  {
    if ( !a4 )
      goto LABEL_15;
    if ( a4 == (const struct CElement *)-1LL )
    {
LABEL_17:
      if ( (*((_BYTE *)v14 + 97) & 2) != 0 )
      {
        if ( (unsigned int)CMarkup::IsXmlParsingMode(v14) )
        {
          if ( *((int *)v14 + 212) >= 90000 )
          {
            a7 = 0;
            if ( (int)CMarkup::GetMarkupPrintUri(v36, &a7) >= 0 )
            {
              v37 = (const unsigned __int16 *)a7;
              v40 = 0;
              if ( (int)GetIUriPriv(a7, &v40) >= 0 )
              {
                v48 = 0;
                v51 = 0;
                if ( (*(int (__fastcall **)(OLECHAR *, const unsigned __int16 **, int *))(*(_QWORD *)v40 + 232LL))(
                       v40,
                       &v51,
                       &v48) >= 0 )
                  v13 = v51;
                (*(void (**)(void))(*(_QWORD *)v40 + 16LL))();
              }
              (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v37 + 16LL))(v37);
              if ( v13 )
                goto LABEL_84;
            }
          }
        }
      }
      goto LABEL_18;
    }
  }
  else
  {
    if ( (unsigned __int64)a4 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_18;
    v14 = CElement::GetMarkupPtr(a4);
    if ( !v14 )
    {
      v15 = CElement::Doc(a4);
      v14 = CDoc::PrimaryMarkup(v15);
    }
  }
  CElement::Doc(a4);
  if ( !v14 )
    goto LABEL_18;
LABEL_15:
  v16 = CMarkup::EnsureTopElems(v14);
  if ( !v16 )
    goto LABEL_17;
  v17 = *((_QWORD *)v16 + 6);
  if ( !v17 )
    goto LABEL_17;
  v13 = *(const unsigned __int16 **)(v17 + 88);
  if ( !v13 )
  {
    if ( v14 )
      goto LABEL_17;
LABEL_18:
    OriginUrl = CMarkup::GetOriginUrl(v14);
LABEL_19:
    LODWORD(a7) = 1;
    v13 = OriginUrl;
    goto LABEL_20;
  }
LABEL_84:
  LODWORD(a7) = 0;
LABEL_20:
  if ( v13 == Url )
  {
    UriRaw = CMarkup::GetUriRaw(MarkupPtr);
    pBaseUri = UriRaw;
    if ( UriRaw )
    {
      v20 = 0;
      ((void (__fastcall *)(IUri *))UriRaw->lpVtbl->AddRef)(UriRaw);
      goto LABEL_23;
    }
    v33 = 50342784;
    v34 = L"about:blank";
  }
  else
  {
    v33 = 50342789;
    v34 = v13;
  }
  v20 = (OLECHAR *)(unsigned int)CreateUri(v34, v33, 0, &pBaseUri);
LABEL_23:
  if ( (_DWORD)v20 )
    goto LABEL_37;
  v21 = pBaseUri;
  v22 = pBaseUri != v44;
  v23 = v45 != 12;
  if ( pBaseUri != v44 || v45 != 12 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = v20;
    }
    bstrString[1] = v20;
    v47 = 0;
    if ( v22 && v44 )
    {
      ((void (__fastcall *)(IUri *))v44->lpVtbl->Release)(v44);
      v44 = (IUri *)v20;
    }
  }
  v45 = 12;
  if ( !v21 || !v23 && !v22 )
    goto LABEL_31;
  lpVtbl = v21->lpVtbl;
  v40 = v20;
  if ( ((__int64 (__fastcall *)(IUri *, GUID *, OLECHAR **))lpVtbl->QueryInterface)(
         v21,
         &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
         &v40) < 0 )
  {
    LODWORD(v20) = ((__int64 (__fastcall *)(IUri *, _QWORD, BSTR *, _QWORD))v21->lpVtbl->GetPropertyBSTR)(
                     v21,
                     v45,
                     bstrString,
                     0);
    if ( (int)v20 >= 0 )
    {
      bstrString[1] = bstrString[0];
      v47 = SysStringLen(bstrString[0]);
    }
  }
  else
  {
    LODWORD(v20) = (*(__int64 (__fastcall **)(OLECHAR *, _QWORD, BSTR *, UINT *))(*(_QWORD *)v40 + 224LL))(
                     v40,
                     v45,
                     &bstrString[1],
                     &v47);
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v40 + 16LL))(v40);
  }
  if ( v22 )
  {
    if ( (int)v20 < 0 )
      goto LABEL_37;
    v44 = v21;
    ((void (__fastcall *)(IUri *))v21->lpVtbl->AddRef)(v21);
  }
  else
  {
LABEL_31:
    if ( (int)v20 < 0 )
      goto LABEL_37;
  }
  v24 = (int)a7;
  if ( !bCallCoInternetCombineUrl && !(_DWORD)a7 )
  {
    v38 = v47;
    if ( v47 )
    {
      if ( (unsigned __int64)a4 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( !this )
          goto LABEL_34;
        v39 = CMarkup::Doc(this);
      }
      else
      {
        v39 = CElement::Doc(a4);
      }
      if ( v39 && (*((_DWORD *)v39 + 1217) & 0x800) != 0 && v38 == 7 )
        _wcsnicmp(L"outbind", bstrString[1], 7u);
    }
  }
LABEL_34:
  v25 = ppCombinedUri;
  v26 = dwCombineFlags;
  LODWORD(v20) = CoInternetCombineIUri(pBaseUri, a2, dwCombineFlags, ppCombinedUri, a5 & 3);
  if ( !(_DWORD)v20 )
  {
    if ( (unsigned __int64)a4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL && !this )
    {
      this = CElement::GetMarkupForBaseUrl(a4);
      if ( !this )
      {
        v29 = CElement::Doc(a4);
        if ( v29 )
          this = CDoc::PrimaryMarkup(v29);
      }
    }
    if ( !v24 )
    {
      if ( this )
      {
        v30 = CMarkup::GetUrl(this);
        if ( !CoInternetQueryInfo(v30, QUERY_RECOMBINE, 0, &pvBuffer, 4u, &pcbBuffer, 0) )
        {
          if ( pvBuffer )
          {
            v31 = 0;
            ppCombinedUri = 0;
            if ( v30 )
            {
              LODWORD(v20) = CreateUri(v30, 0x3002B84u, 0, (IUri **)&ppCombinedUri);
              if ( (int)v20 < 0 )
                goto LABEL_37;
              v31 = ppCombinedUri;
            }
            v32 = *v25;
            LODWORD(v20) = CoInternetCombineIUri((IUri *)v31, *v25, v26, v25, 0);
            if ( ppCombinedUri )
              ((void (__fastcall *)(IUri **))(*ppCombinedUri)[2].lpVtbl)(ppCombinedUri);
            if ( v32 )
              ((void (__fastcall *)(IUri *))v32->lpVtbl->Release)(v32);
          }
        }
      }
    }
  }
LABEL_37:
  if ( pBaseUri )
    ((void (__fastcall *)(IUri *))pBaseUri->lpVtbl->Release)(pBaseUri);
  v43 = &CUString::`vftable';
  if ( !v44 )
    goto LABEL_40;
LABEL_41:
  if ( v10 || v45 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v47 = 0;
    if ( v10 && v44 )
      ((void (__fastcall *)(IUri *))v44->lpVtbl->Release)(v44);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18028d388  mov     rax, rsp
0x18028d38b  mov     [rax+8], rbx
0x18028d38f  mov     [rax+18h], r8
0x18028d393  mov     [rax+10h], rdx
0x18028d397  push    rbp
0x18028d398  push    rsi
0x18028d399  push    rdi
0x18028d39a  push    r12
0x18028d39c  push    r13
0x18028d39e  push    r14
0x18028d3a0  push    r15
0x18028d3a2  lea     rbp, [rax-47h]
0x18028d3a6  sub     rsp, 0B0h
0x18028d3ad  mov     [rbp+3Fh+pvBuffer], 0
0x18028d3b4  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x18028d3bb  mov     [rbp+3Fh+var_88], r14
0x18028d3bf  xorps   xmm0, xmm0
0x18028d3c2  mov     [rbp+3Fh+var_50], 0
0x18028d3c9  mov     rsi, r9
0x18028d3cc  mov     [rbp+3Fh+pBaseUri], 0
0x18028d3d4  mov     r15, rcx
0x18028d3d7  mov     [rbp+3Fh+var_80], 0
0x18028d3df  mov     [rbp+3Fh+var_78], 0Bh
0x18028d3e6  mov     [rbp+3Fh+var_60], 0
0x18028d3ed  movdqu  xmmword ptr [rbp+3Fh+bstrString], xmm0
0x18028d3f2  test    r8, r8
0x18028d3f5  jz      loc_18028D8D3
0x18028d3fb  cmp     [rbp+3Fh+arg_28], 0FFFFFFFFh
0x18028d3ff  mov     ecx, 6000000h
0x18028d404  mov     r13d, 1
0x18028d40a  cmovnz  ecx, [rbp+3Fh+arg_28]
0x18028d40e  mov     [rbp+3Fh+dwCombineFlags], ecx
0x18028d411  test    rdx, rdx
0x18028d414  jz      loc_18028D8DD
0x18028d41a  mov     rbx, r15
0x18028d41d  test    r15, r15
0x18028d420  jz      loc_18028D902
0x18028d426  mov     rcx, rbx; struct CMarkup *
0x18028d429  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x18028d42e  mov     [rbp+3Fh+var_40], rax
0x18028d432  test    rbx, rbx
0x18028d435  jz      short loc_18028D465
0x18028d437  mov     rax, [rbx]
0x18028d43a  lea     rcx, __vtguard
0x18028d441  cmp     [rax+3D8h], rcx
0x18028d448  jnz     loc_18028D94D
0x18028d44e  mov     rax, [rax+4C0h]
0x18028d455  mov     rcx, rbx
0x18028d458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d45d  test    al, al
0x18028d45f  jnz     loc_18028D87E
0x18028d465  xor     r14d, r14d
0x18028d468  mov     rdi, rbx
0x18028d46b  test    rbx, rbx
0x18028d46e  jz      loc_18028D823
0x18028d474  test    rsi, rsi
0x18028d477  jz      short loc_18028D4A1
0x18028d479  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18028d47d  jnz     short loc_18028D494
0x18028d47f  jmp     short loc_18028D4BB
0x18028d481  mov     rcx, rsi; this
0x18028d484  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x18028d489  mov     rcx, rax; this
0x18028d48c  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x18028d491  mov     rdi, rax
0x18028d494  mov     rcx, rsi; this
0x18028d497  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x18028d49c  test    rdi, rdi
0x18028d49f  jz      short loc_18028D4C5
0x18028d4a1  mov     rcx, rdi; this
0x18028d4a4  call    ?EnsureTopElems@CMarkup@@QEAAPEAVCMarkupTopElemCache@@XZ; CMarkup::EnsureTopElems(void)
0x18028d4a9  test    rax, rax
0x18028d4ac  jz      short loc_18028D4BB
0x18028d4ae  mov     rax, [rax+30h]
0x18028d4b2  test    rax, rax
0x18028d4b5  jnz     loc_18028D8C8
0x18028d4bb  test    byte ptr [rdi+61h], 2
0x18028d4bf  jnz     loc_18028D956
0x18028d4c5  mov     rcx, rdi; this
0x18028d4c8  call    ?GetOriginUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetOriginUrl(CMarkup const * const)
0x18028d4cd  mov     dword ptr [rbp+3Fh+arg_30], r13d
0x18028d4d1  mov     r14, rax
0x18028d4d4  cmp     r14, [rbp+3Fh+var_40]
0x18028d4d8  jnz     loc_18028D88B
0x18028d4de  mov     rcx, rbx; struct CMarkup *
0x18028d4e1  call    ?GetUriRaw@CMarkup@@SAPEAUIUri@@QEBV1@@Z; CMarkup::GetUriRaw(CMarkup const * const)
0x18028d4e6  mov     [rbp+3Fh+pBaseUri], rax
0x18028d4ea  mov     rcx, rax
0x18028d4ed  test    rax, rax
0x18028d4f0  jz      loc_18028D858
0x18028d4f6  mov     rax, [rax]
0x18028d4f9  xor     ebx, ebx
0x18028d4fb  mov     rax, [rax+8]
0x18028d4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d504  test    ebx, ebx
0x18028d506  jnz     loc_18028D5D2
0x18028d50c  mov     rdi, [rbp+3Fh+pBaseUri]
0x18028d510  xor     r14d, r14d
0x18028d513  cmp     rdi, [rbp+3Fh+var_80]
0x18028d517  setnz   r14b
0x18028d51b  xor     r12d, r12d
0x18028d51e  cmp     [rbp+3Fh+var_78], 0Ch
0x18028d522  setnz   r12b
0x18028d526  test    r14d, r14d
0x18028d529  jz      loc_18028D734
0x18028d52f  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18028d533  test    rcx, rcx
0x18028d536  jnz     loc_18028D9FC
0x18028d53c  mov     [rbp+3Fh+bstrString+8], rbx
0x18028d540  mov     [rbp+3Fh+var_60], ebx
0x18028d543  test    r14d, r14d
0x18028d546  jz      short loc_18028D561
0x18028d548  mov     rcx, [rbp+3Fh+var_80]
0x18028d54c  test    rcx, rcx
0x18028d54f  jz      short loc_18028D561
0x18028d551  mov     rax, [rcx]
0x18028d554  mov     rax, [rax+10h]
0x18028d558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d55d  mov     [rbp+3Fh+var_80], rbx
0x18028d561  mov     [rbp+3Fh+var_78], 0Ch
0x18028d568  test    rdi, rdi
0x18028d56b  jnz     loc_18028D662
0x18028d571  test    ebx, ebx
0x18028d573  js      short loc_18028D5D2
0x18028d575  cmp     cs:?bCallCoInternetCombineUrl@@3HA, 0; int bCallCoInternetCombineUrl
0x18028d57c  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x18028d57f  jnz     short loc_18028D589
0x18028d581  test    edi, edi
0x18028d583  jz      loc_18028DA4D
0x18028d589  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x18028d58c  mov     r14, [rbp+3Fh+ppCombinedUri]
0x18028d590  and     eax, 3
0x18028d593  mov     r12d, [rbp+3Fh+dwCombineFlags]
0x18028d597  mov     r9, r14; ppCombinedUri
0x18028d59a  mov     rdx, [rbp+3Fh+pRelativeUri]; pRelativeUri
0x18028d59e  mov     r8d, r12d; dwCombineFlags
0x18028d5a1  mov     rcx, [rbp+3Fh+pBaseUri]; pBaseUri
0x18028d5a5  mov     [rsp+0E0h+dwReserved], rax; dwReserved
0x18028d5aa  call    cs:__imp_CoInternetCombineIUri
0x18028d5b1  nop     dword ptr [rax+rax+00h]
0x18028d5b6  mov     ebx, eax
0x18028d5b8  test    eax, eax
0x18028d5ba  jnz     short loc_18028D5D2
0x18028d5bc  lea     rax, [rsi-1]
0x18028d5c0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18028d5c4  jbe     loc_18028D6F6
0x18028d5ca  test    edi, edi
0x18028d5cc  jz      loc_18028D742
0x18028d5d2  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x18028d5d9  mov     rcx, [rbp+3Fh+pBaseUri]
0x18028d5dd  test    rcx, rcx
0x18028d5e0  jz      short loc_18028D5EE
0x18028d5e2  mov     rax, [rcx]
0x18028d5e5  mov     rax, [rax+10h]
0x18028d5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d5ee  cmp     [rbp+3Fh+var_80], 0
0x18028d5f3  mov     [rbp+3Fh+var_88], r14
0x18028d5f7  jnz     short loc_18028D5FC
0x18028d5f9  xor     r13d, r13d
0x18028d5fc  xor     eax, eax
0x18028d5fe  cmp     [rbp+3Fh+var_78], 0Bh
0x18028d602  setnz   al
0x18028d605  test    r13d, r13d
0x18028d608  jz      loc_18028D6E9
0x18028d60e  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18028d612  test    rcx, rcx
0x18028d615  jnz     loc_18028DAC1
0x18028d61b  mov     [rbp+3Fh+bstrString+8], 0
0x18028d623  mov     [rbp+3Fh+var_60], 0
0x18028d62a  test    r13d, r13d
0x18028d62d  jz      short loc_18028D644
0x18028d62f  mov     rcx, [rbp+3Fh+var_80]
0x18028d633  test    rcx, rcx
0x18028d636  jz      short loc_18028D644
0x18028d638  mov     rax, [rcx]
0x18028d63b  mov     rax, [rax+10h]
0x18028d63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d644  mov     eax, ebx
0x18028d646  mov     rbx, [rsp+0E0h+arg_0]
0x18028d64e  add     rsp, 0B0h
0x18028d655  pop     r15
0x18028d657  pop     r14
0x18028d659  pop     r13
0x18028d65b  pop     r12
0x18028d65d  pop     rdi
0x18028d65e  pop     rsi
0x18028d65f  pop     rbp
0x18028d660  retn
0x18028d662  test    r12d, r12d
0x18028d665  jz      loc_18028D84A
0x18028d66b  mov     rax, [rdi]
0x18028d66e  lea     r8, [rbp+3Fh+var_A0]
0x18028d672  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x18028d679  mov     [rbp+3Fh+var_A0], rbx
0x18028d67d  mov     rcx, rdi
0x18028d680  mov     rax, [rax]
0x18028d683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d688  mov     edx, [rbp+3Fh+var_78]
0x18028d68b  test    eax, eax
0x18028d68d  js      loc_18028DA11
0x18028d693  mov     rcx, [rbp+3Fh+var_A0]
0x18028d697  lea     r9, [rbp+3Fh+var_60]
0x18028d69b  lea     r8, [rbp+3Fh+bstrString+8]
0x18028d69f  mov     rax, [rcx]
0x18028d6a2  mov     rax, [rax+0E0h]
0x18028d6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d6ae  mov     rcx, [rbp+3Fh+var_A0]
0x18028d6b2  mov     ebx, eax
0x18028d6b4  mov     rax, [rcx]
0x18028d6b7  mov     rax, [rax+10h]
0x18028d6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d6c0  test    r14d, r14d
0x18028d6c3  jz      loc_18028D571
0x18028d6c9  test    ebx, ebx
0x18028d6cb  js      loc_18028D5D2
0x18028d6d1  mov     [rbp+3Fh+var_80], rdi
0x18028d6d5  mov     rcx, rdi
0x18028d6d8  mov     rax, [rdi]
0x18028d6db  mov     rax, [rax+8]
0x18028d6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d6e4  jmp     loc_18028D575
0x18028d6e9  test    eax, eax
0x18028d6eb  jz      loc_18028D644
0x18028d6f1  jmp     loc_18028D60E
0x18028d6f6  test    r15, r15
0x18028d6f9  jnz     loc_18028D5CA
0x18028d6ff  mov     rcx, rsi; this
0x18028d702  call    ?GetMarkupForBaseUrl@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupForBaseUrl(void)
0x18028d707  mov     r15, rax
0x18028d70a  test    rax, rax
0x18028d70d  jnz     loc_18028D5CA
0x18028d713  mov     rcx, rsi; this
0x18028d716  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x18028d71b  test    rax, rax
0x18028d71e  jz      loc_18028D5CA
0x18028d724  mov     rcx, rax; this
0x18028d727  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x18028d72c  mov     r15, rax
0x18028d72f  jmp     loc_18028D5CA
0x18028d734  test    r12d, r12d
0x18028d737  jz      loc_18028D561
0x18028d73d  jmp     loc_18028D52F
0x18028d742  test    r15, r15
0x18028d745  jz      loc_18028D5D2
0x18028d74b  mov     rcx, r15; struct CMarkup *
0x18028d74e  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x18028d753  mov     rdi, rax
0x18028d756  mov     dword ptr [rsp+30h], 0; dwReserved
0x18028d75e  xor     r8d, r8d; dwQueryFlags
0x18028d761  lea     rax, [rbp+3Fh+var_50]
0x18028d765  mov     [rsp+0E0h+pcbBuffer], rax; pcbBuffer
0x18028d76a  lea     r9, [rbp+3Fh+pvBuffer]; pvBuffer
0x18028d76e  mov     rcx, rdi; pwzUrl
0x18028d771  mov     dword ptr [rsp+0E0h+dwReserved], 4; cbBuffer
0x18028d779  lea     edx, [r8+6]; QueryOptions
0x18028d77d  call    cs:__imp_CoInternetQueryInfo
0x18028d784  nop     dword ptr [rax+rax+00h]
0x18028d789  test    eax, eax
0x18028d78b  jnz     loc_18028D5D2
0x18028d791  cmp     [rbp+3Fh+pvBuffer], eax
0x18028d794  jz      loc_18028D5D2
0x18028d79a  xor     ecx, ecx
0x18028d79c  mov     [rbp+3Fh+ppCombinedUri], rcx
0x18028d7a0  test    rdi, rdi
0x18028d7a3  jz      short loc_18028D7CE
0x18028d7a5  lea     r9, [rbp+3Fh+ppCombinedUri]; ppURI
0x18028d7a9  xor     r8d, r8d; dwReserved
0x18028d7ac  mov     edx, 3002B84h; dwFlags
0x18028d7b1  mov     rcx, rdi; pwzURI
0x18028d7b4  call    cs:__imp_CreateUri
0x18028d7bb  nop     dword ptr [rax+rax+00h]
0x18028d7c0  mov     ebx, eax
0x18028d7c2  test    eax, eax
0x18028d7c4  js      loc_18028D5D2
0x18028d7ca  mov     rcx, [rbp+3Fh+ppCombinedUri]; pBaseUri
0x18028d7ce  mov     rdi, [r14]
0x18028d7d1  mov     r9, r14; ppCombinedUri
0x18028d7d4  mov     rdx, rdi; pRelativeUri
0x18028d7d7  mov     [rsp+0E0h+dwReserved], 0; dwReserved
0x18028d7e0  mov     r8d, r12d; dwCombineFlags
0x18028d7e3  call    cs:__imp_CoInternetCombineIUri
0x18028d7ea  nop     dword ptr [rax+rax+00h]
0x18028d7ef  mov     rcx, [rbp+3Fh+ppCombinedUri]
0x18028d7f3  mov     ebx, eax
0x18028d7f5  test    rcx, rcx
0x18028d7f8  jz      short loc_18028D806
0x18028d7fa  mov     rax, [rcx]
0x18028d7fd  mov     rax, [rax+10h]
0x18028d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d806  test    rdi, rdi
0x18028d809  jz      loc_18028D5D2
0x18028d80f  mov     rax, [rdi]
0x18028d812  mov     rcx, rdi
0x18028d815  mov     rax, [rax+10h]
0x18028d819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028d81e  jmp     loc_18028D5D2
0x18028d823  lea     rax, [rsi-1]
0x18028d827  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18028d82b  ja      loc_18028D4C5
0x18028d831  mov     rcx, rsi; this
  ... truncated ...
```
