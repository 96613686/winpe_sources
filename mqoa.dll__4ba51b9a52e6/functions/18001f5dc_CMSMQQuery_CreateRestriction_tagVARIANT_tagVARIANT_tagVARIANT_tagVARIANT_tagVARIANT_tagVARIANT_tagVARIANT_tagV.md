# CMSMQQuery::CreateRestriction(tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagMQRESTRICTION *,tagMQCOLUMNSET *)

- ea: `0x18001f5dc`
- end: `0x18001fbb6`
- name: `?CreateRestriction@CMSMQQuery@@KAJPEAUtagVARIANT@@0000000000PEAUtagMQRESTRICTION@@PEAUtagMQCOLUMNSET@@@Z`
- size: `1498`
- prototype: `__int64 __usercall@<rax>(struct tagVARIANT *@<rcx>, struct tagVARIANT *@<rdx>, struct tagVARIANT *@<r8>, struct tagVARIANT *@<r9>, struct tagVARIANT *, VARIANTARG *pvarSrc, VARIANTARG *, VARIANTARG *, VARIANTARG *, struct tagVARIANT *, VARIANTARG *, struct tagMQRESTRICTION *, struct tagMQCOLUMNSET *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001fcb0`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x1800075a8`
- `0x18001f5dc`
- `0x18001fe80`
- `0x1800200bc`
- `0x18002695c`
- `0x1800271cc`
- `0x18002737e`

## import_xrefs

- `ole32!CLSIDFromString` at `0x18001f76a`
- `ole32!CLSIDFromString` at `0x18001f804`
- `ole32!CLSIDFromString` at `0x18001f76a`
- `ole32!CLSIDFromString` at `0x18001f804`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f8c4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001faaa`
- `OLEAUT32!__imp_SysStringLen` at `0x18001fab7`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f8c4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001faaa`
- `OLEAUT32!__imp_SysStringLen` at `0x18001fab7`

## pseudocode

```c
__int64 __fastcall CMSMQQuery::CreateRestriction(
        struct tagVARIANT *a1,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5,
        VARIANTARG *pvarSrc,
        VARIANTARG *a7,
        VARIANTARG *a8,
        VARIANTARG *a9,
        struct tagVARIANT *a10,
        VARIANTARG *a11,
        struct tagMQRESTRICTION *a12,
        struct tagMQCOLUMNSET *a13)
{
  GUID *v17; // rax
  CLSID *v18; // rdi
  GUID *v19; // rax
  CLSID *v20; // rsi
  ULONG v21; // ebp
  MQPROPERTYRESTRICTION *v22; // rax
  MQPROPERTYRESTRICTION *v23; // r14
  HRESULT v24; // ebx
  __int64 v25; // r15
  const OLECHAR *Bstr; // rax
  CLSID *v27; // rax
  const OLECHAR *v28; // r13
  __int64 v29; // r12
  CLSID *v30; // rax
  unsigned int v31; // eax
  __int16 v32; // r13
  __int64 v33; // r12
  OLECHAR *v34; // rbx
  wchar_t *v35; // rax
  unsigned int v36; // eax
  __int64 v37; // r12
  unsigned int v38; // eax
  __int64 v39; // r12
  unsigned int v40; // eax
  __int64 v41; // r15
  OLECHAR *v42; // rax
  OLECHAR *v43; // rbp
  UINT v44; // ebx
  wchar_t *v45; // rax
  unsigned int v46; // eax
  PROPID *v47; // rcx
  __int64 v49; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int64 v50; // [rsp+28h] [rbp-40h]

  v49 = 0;
  v17 = (GUID *)operator new(0x10u);
  v18 = v17;
  if ( v17 )
  {
    *v17 = GUID_NULL;
    v19 = (GUID *)operator new(0x10u);
    v20 = v19;
    if ( !v19 )
    {
      v20 = 0;
      goto LABEL_76;
    }
    *v19 = GUID_NULL;
    v21 = a1->vt != 10;
    if ( a2->vt != 10 && (unsigned int)IsValidRel(pvarSrc) )
      ++v21;
    if ( a3->vt != 10 && (unsigned int)IsValidRel(a7) )
      ++v21;
    if ( a4->vt != 10 && (unsigned int)IsValidRel(a8) )
      ++v21;
    if ( a5->vt != 10 && (unsigned int)IsValidRel(a9) )
      ++v21;
    if ( a10->vt != 10 && (unsigned int)IsValidRel(a11) )
      ++v21;
    v22 = (MQPROPERTYRESTRICTION *)operator new(saturated_mul(v21, 0x20u));
    v23 = v22;
    if ( !v22 )
      goto LABEL_76;
    v24 = 0;
    memset_0(v22, 0, 32LL * v21);
    v25 = 0;
    a12->cRes = v21;
    a12->paPropRes = v23;
    if ( a1->vt != 10 && v21 )
    {
      v23->prval.vt = 10;
      Bstr = GetBstr(a1);
      if ( !Bstr )
      {
LABEL_22:
        v24 = -2147024809;
LABEL_77:
        operator delete(v18);
        operator delete(v20);
        return (unsigned int)v24;
      }
      v24 = CLSIDFromString(Bstr, v18);
      if ( v24 < 0 )
        goto LABEL_77;
      v27 = (CLSID *)operator new(0x10u);
      if ( v27 )
        *v27 = *v18;
      v23->prval.hVal.QuadPart = (LONGLONG)v27;
      if ( !v27 )
        goto LABEL_76;
      v23->rel = 4;
      v23->prop = 101;
      v23->prval.vt = 72;
      v25 = 1;
    }
    if ( a2->vt != 10 )
    {
      v28 = GetBstr(a2);
      if ( !v28 )
        goto LABEL_22;
      if ( (unsigned int)IsValidRel(pvarSrc) && (unsigned int)v25 < v21 )
      {
        v29 = (unsigned int)v25;
        v23[v29].prval.vt = 10;
        v24 = CLSIDFromString(v28, v20);
        if ( v24 < 0 )
          goto LABEL_77;
        v30 = (CLSID *)operator new(0x10u);
        if ( v30 )
          *v30 = *v20;
        v23[v29].prval.hVal.QuadPart = (LONGLONG)v30;
        if ( !v30 )
          goto LABEL_76;
        v31 = PrOfVar(pvarSrc);
        v23[v29].prop = 102;
        v23[v29].prval.vt = 72;
        if ( v31 == -1 )
          v31 = 4;
        v25 = (unsigned int)(v25 + 1);
        v23[v29].rel = v31;
      }
    }
    v32 = 31;
    if ( a3->vt != 10 && (unsigned int)IsValidRel(a7) && (unsigned int)v25 < v21 )
    {
      v33 = (unsigned int)v25;
      v23[v33].prval.vt = 10;
      v34 = GetBstr(a3);
      v50 = SysStringLen(v34) + 1;
      v35 = (wchar_t *)operator new(saturated_mul(v50, 2u));
      v23[v33].prval.hVal.QuadPart = (LONGLONG)v35;
      if ( !v35 )
        goto LABEL_76;
      v24 = StringCchCopyW(v35, v50, v34);
      if ( v24 < 0 )
        goto LABEL_77;
      v36 = PrOfVar(a7);
      v23[v33].prop = 108;
      v23[v33].prval.vt = 31;
      if ( v36 == -1 )
        v36 = 4;
      v25 = (unsigned int)(v25 + 1);
      v23[v33].rel = v36;
    }
    if ( a4->vt != 10 && (unsigned int)IsValidRel(a8) && (unsigned int)v25 < v21 )
    {
      v37 = (unsigned int)v25;
      v23[v37].prval.vt = 10;
      if ( !VariantTimeToTime(a4, &v49) )
        goto LABEL_22;
      v23[v37].prval.lVal = v49;
      v23[v37].prop = 109;
      v23[v37].prval.vt = 3;
      v38 = PrOfVar(a8);
      if ( v38 == -1 )
        v38 = 4;
      v25 = (unsigned int)(v25 + 1);
      v23[v37].rel = v38;
    }
    if ( a5->vt != 10 && (unsigned int)IsValidRel(a9) && (unsigned int)v25 < v21 )
    {
      v39 = (unsigned int)v25;
      v23[v39].prval.vt = 10;
      if ( !VariantTimeToTime(a5, &v49) )
        goto LABEL_22;
      v23[v39].prval.lVal = v49;
      v23[v39].prop = 110;
      v23[v39].prval.vt = 3;
      v40 = PrOfVar(a9);
      if ( v40 == -1 )
        v40 = 4;
      v25 = (unsigned int)(v25 + 1);
      v23[v39].rel = v40;
    }
    if ( a10->vt != 10 && (unsigned int)IsValidRel(a11) && (unsigned int)v25 < v21 )
    {
      v41 = v25;
      v23[v41].prval.vt = 10;
      v42 = GetBstr(a10);
      v43 = v42;
      if ( v42 && SysStringLen(v42) )
      {
        v44 = SysStringLen(v43) + 1;
        v45 = (wchar_t *)operator new(saturated_mul(v44, 2u));
        v23[v41].prval.hVal.QuadPart = (LONGLONG)v45;
        if ( !v45 )
          goto LABEL_76;
        v24 = StringCchCopyW(v45, v44, v43);
        if ( v24 < 0 )
          goto LABEL_77;
      }
      else
      {
        v32 = 0;
      }
      v23[v41].prval.vt = v32;
      v46 = PrOfVar(a11);
      v23[v41].prop = 125;
      if ( v46 == -1 )
        v46 = 4;
      v23[v41].rel = v46;
    }
    v47 = (PROPID *)operator new(0x34u);
    a13->aCol = v47;
    if ( v47 )
    {
      a13->cCol = 13;
      *(_OWORD *)v47 = *(_OWORD *)&g_rgpropidRefresh;
      *((_OWORD *)v47 + 1) = xmmword_18002FA30;
      *((_OWORD *)v47 + 2) = xmmword_18002FA40;
      v47[12] = 107;
      goto LABEL_77;
    }
LABEL_76:
    v24 = -2147024882;
    goto LABEL_77;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001f5dc  mov     rax, rsp
0x18001f5df  mov     [rax+8], rbx
0x18001f5e3  mov     [rax+20h], r9
0x18001f5e7  mov     [rax+18h], r8
0x18001f5eb  push    rbp
0x18001f5ec  push    rsi
0x18001f5ed  push    rdi
0x18001f5ee  push    r12
0x18001f5f0  push    r13
0x18001f5f2  push    r14
0x18001f5f4  push    r15
0x18001f5f6  sub     rsp, 30h
0x18001f5fa  mov     r12, rcx
0x18001f5fd  mov     qword ptr [rax-48h], 0
0x18001f605  mov     esi, 10h
0x18001f60a  mov     r14, r9
0x18001f60d  mov     ecx, esi; Size
0x18001f60f  mov     rbx, r8
0x18001f612  mov     r13, rdx
0x18001f615  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f61a  mov     rdi, rax
0x18001f61d  test    rax, rax
0x18001f620  jz      loc_18001FB9C
0x18001f626  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001f62d  mov     ecx, esi; Size
0x18001f62f  movdqu  xmmword ptr [rax], xmm0
0x18001f633  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f638  mov     rsi, rax
0x18001f63b  test    rax, rax
0x18001f63e  jz      loc_18001FB81
0x18001f644  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001f64b  xor     ebp, ebp
0x18001f64d  movdqu  xmmword ptr [rax], xmm0
0x18001f651  lea     r15d, [rbp+0Ah]
0x18001f655  cmp     [r12], r15w
0x18001f65a  setnz   bpl
0x18001f65e  cmp     [r13+0], r15w
0x18001f663  jz      short loc_18001F678
0x18001f665  mov     rcx, [rsp+68h+pvarSrc]
0x18001f66d  call    IsValidRel
0x18001f672  test    eax, eax
0x18001f674  jz      short loc_18001F678
0x18001f676  inc     ebp
0x18001f678  cmp     [rbx], r15w
0x18001f67c  jz      short loc_18001F691
0x18001f67e  mov     rcx, [rsp+68h+arg_30]
0x18001f686  call    IsValidRel
0x18001f68b  test    eax, eax
0x18001f68d  jz      short loc_18001F691
0x18001f68f  inc     ebp
0x18001f691  cmp     [r14], r15w
0x18001f695  jz      short loc_18001F6AA
0x18001f697  mov     rcx, [rsp+68h+arg_38]
0x18001f69f  call    IsValidRel
0x18001f6a4  test    eax, eax
0x18001f6a6  jz      short loc_18001F6AA
0x18001f6a8  inc     ebp
0x18001f6aa  mov     rax, [rsp+68h+arg_20]
0x18001f6b2  cmp     [rax], r15w
0x18001f6b6  jz      short loc_18001F6CB
0x18001f6b8  mov     rcx, [rsp+68h+arg_40]
0x18001f6c0  call    IsValidRel
0x18001f6c5  test    eax, eax
0x18001f6c7  jz      short loc_18001F6CB
0x18001f6c9  inc     ebp
0x18001f6cb  mov     rax, [rsp+68h+arg_48]
0x18001f6d3  cmp     [rax], r15w
0x18001f6d7  jz      short loc_18001F6EC
0x18001f6d9  mov     rcx, [rsp+68h+arg_50]
0x18001f6e1  call    IsValidRel
0x18001f6e6  test    eax, eax
0x18001f6e8  jz      short loc_18001F6EC
0x18001f6ea  inc     ebp
0x18001f6ec  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f6f3  mov     r15d, ebp
0x18001f6f6  mov     eax, 20h ; ' '
0x18001f6fb  mul     r15
0x18001f6fe  cmovb   rax, rcx
0x18001f702  mov     rcx, rax; Size
0x18001f705  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f70a  mov     r14, rax
0x18001f70d  test    rax, rax
0x18001f710  jz      loc_18001FB83
0x18001f716  shl     r15, 5
0x18001f71a  xor     edx, edx; Val
0x18001f71c  mov     r8, r15; Size
0x18001f71f  mov     rcx, rax; void *
0x18001f722  xor     ebx, ebx
0x18001f724  call    memset_0
0x18001f729  mov     rax, [rsp+68h+arg_58]
0x18001f731  xor     r15d, r15d
0x18001f734  mov     [rax], ebp
0x18001f736  mov     [rax+8], r14
0x18001f73a  lea     eax, [rbx+0Ah]
0x18001f73d  cmp     [r12], ax
0x18001f742  jz      short loc_18001F7BE
0x18001f744  test    ebp, ebp
0x18001f746  jz      short loc_18001F7BE
0x18001f748  mov     rcx, r12; struct tagVARIANT *
0x18001f74b  mov     [r14+8], ax
0x18001f750  call    ?GetBstr@@YAPEA_WPEAUtagVARIANT@@@Z; GetBstr(tagVARIANT *)
0x18001f755  test    rax, rax
0x18001f758  jnz     short loc_18001F764
0x18001f75a  mov     ebx, 80070057h
0x18001f75f  jmp     loc_18001FB88
0x18001f764  mov     rdx, rdi; pclsid
0x18001f767  mov     rcx, rax; lpsz
0x18001f76a  call    cs:__imp_CLSIDFromString
0x18001f770  mov     ebx, eax
0x18001f772  test    eax, eax
0x18001f774  js      loc_18001FB88
0x18001f77a  mov     ecx, 10h; Size
0x18001f77f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f784  test    rax, rax
0x18001f787  jz      short loc_18001F790
0x18001f789  movups  xmm0, xmmword ptr [rdi]
0x18001f78c  movdqu  xmmword ptr [rax], xmm0
0x18001f790  mov     [r14+10h], rax
0x18001f794  test    rax, rax
0x18001f797  jz      loc_18001FB83
0x18001f79d  mov     dword ptr [r14], 4
0x18001f7a4  mov     eax, 0Ah
0x18001f7a9  mov     dword ptr [r14+4], 65h ; 'e'
0x18001f7b1  mov     word ptr [r14+8], 48h ; 'H'
0x18001f7b8  mov     r15d, 1
0x18001f7be  cmp     [r13+0], ax
0x18001f7c3  jz      loc_18001F868
0x18001f7c9  mov     rcx, r13; struct tagVARIANT *
0x18001f7cc  call    ?GetBstr@@YAPEA_WPEAUtagVARIANT@@@Z; GetBstr(tagVARIANT *)
0x18001f7d1  mov     r13, rax
0x18001f7d4  test    rax, rax
0x18001f7d7  jz      short loc_18001F75A
0x18001f7d9  mov     rcx, [rsp+68h+pvarSrc]
0x18001f7e1  call    IsValidRel
0x18001f7e6  test    eax, eax
0x18001f7e8  jz      short loc_18001F868
0x18001f7ea  cmp     r15d, ebp
0x18001f7ed  jnb     short loc_18001F868
0x18001f7ef  mov     r12d, r15d
0x18001f7f2  mov     rdx, rsi; pclsid
0x18001f7f5  shl     r12, 5
0x18001f7f9  mov     rcx, r13; lpsz
0x18001f7fc  mov     word ptr [r12+r14+8], 0Ah
0x18001f804  call    cs:__imp_CLSIDFromString
0x18001f80a  mov     ebx, eax
0x18001f80c  test    eax, eax
0x18001f80e  js      loc_18001FB88
0x18001f814  mov     ecx, 10h; Size
0x18001f819  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f81e  test    rax, rax
0x18001f821  jz      short loc_18001F82A
0x18001f823  movups  xmm0, xmmword ptr [rsi]
0x18001f826  movdqu  xmmword ptr [rax], xmm0
0x18001f82a  mov     [r12+r14+10h], rax
0x18001f82f  test    rax, rax
0x18001f832  jz      loc_18001FB83
0x18001f838  mov     rcx, [rsp+68h+pvarSrc]; pvarSrc
0x18001f840  call    ?PrOfVar@@YAIPEAUtagVARIANT@@@Z; PrOfVar(tagVARIANT *)
0x18001f845  cmp     eax, 0FFFFFFFFh
0x18001f848  mov     dword ptr [r12+r14+4], 66h ; 'f'
0x18001f851  mov     ecx, 4
0x18001f856  mov     word ptr [r12+r14+8], 48h ; 'H'
0x18001f85e  cmovz   eax, ecx
0x18001f861  inc     r15d
0x18001f864  mov     [r12+r14], eax
0x18001f868  mov     rax, [rsp+68h+arg_10]
0x18001f870  mov     r13d, 1Fh
0x18001f876  lea     r12d, [r13-15h]
0x18001f87a  cmp     [rax], r12w
0x18001f87e  jz      loc_18001F945
0x18001f884  mov     rcx, [rsp+68h+arg_30]
0x18001f88c  call    IsValidRel
0x18001f891  test    eax, eax
0x18001f893  jz      loc_18001F945
0x18001f899  cmp     r15d, ebp
0x18001f89c  jnb     loc_18001F945
0x18001f8a2  mov     rcx, [rsp+68h+arg_10]; struct tagVARIANT *
0x18001f8aa  mov     r12d, r15d
0x18001f8ad  shl     r12, 5
0x18001f8b1  mov     word ptr [r12+r14+8], 0Ah
0x18001f8b9  call    ?GetBstr@@YAPEA_WPEAUtagVARIANT@@@Z; GetBstr(tagVARIANT *)
0x18001f8be  mov     rcx, rax; pbstr
0x18001f8c1  mov     rbx, rax
0x18001f8c4  call    cs:__imp_SysStringLen
0x18001f8ca  lea     ecx, [rax+1]
0x18001f8cd  mov     [rsp+68h+var_40], rcx
0x18001f8d2  lea     eax, [r13-1Dh]
0x18001f8d6  mul     rcx
0x18001f8d9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f8e0  cmovb   rax, rcx
0x18001f8e4  mov     rcx, rax; Size
0x18001f8e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f8ec  mov     [r12+r14+10h], rax
0x18001f8f1  test    rax, rax
0x18001f8f4  jz      loc_18001FB83
0x18001f8fa  mov     rdx, [rsp+68h+var_40]; unsigned __int64
0x18001f8ff  mov     r8, rbx; wchar_t *
0x18001f902  mov     rcx, rax; wchar_t *
0x18001f905  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001f90a  mov     ebx, eax
0x18001f90c  test    eax, eax
0x18001f90e  js      loc_18001FB88
0x18001f914  mov     rcx, [rsp+68h+arg_30]; pvarSrc
0x18001f91c  call    ?PrOfVar@@YAIPEAUtagVARIANT@@@Z; PrOfVar(tagVARIANT *)
0x18001f921  cmp     eax, 0FFFFFFFFh
0x18001f924  mov     dword ptr [r12+r14+4], 6Ch ; 'l'
0x18001f92d  lea     ecx, [r13-1Bh]
0x18001f931  mov     [r12+r14+8], r13w
0x18001f937  cmovz   eax, ecx
0x18001f93a  inc     r15d
0x18001f93d  mov     [r12+r14], eax
0x18001f941  lea     r12d, [r13-15h]
0x18001f945  mov     rax, [rsp+68h+arg_18]
0x18001f94d  cmp     [rax], r12w
0x18001f951  jz      short loc_18001F9CF
0x18001f953  mov     rcx, [rsp+68h+arg_38]
0x18001f95b  call    IsValidRel
0x18001f960  test    eax, eax
0x18001f962  jz      short loc_18001F9CF
0x18001f964  cmp     r15d, ebp
0x18001f967  jnb     short loc_18001F9CF
0x18001f969  mov     rcx, [rsp+68h+arg_18]; struct tagVARIANT *
0x18001f971  lea     rdx, [rsp+68h+var_48]; __int64 *
0x18001f976  mov     r12d, r15d
0x18001f979  shl     r12, 5
0x18001f97d  mov     word ptr [r12+r14+8], 0Ah
0x18001f985  call    ?VariantTimeToTime@@YAHPEAUtagVARIANT@@PEA_J@Z; VariantTimeToTime(tagVARIANT *,__int64 *)
0x18001f98a  test    eax, eax
0x18001f98c  jz      loc_18001F75A
0x18001f992  mov     eax, dword ptr [rsp+68h+var_48]
0x18001f996  mov     rcx, [rsp+68h+arg_38]; pvarSrc
0x18001f99e  mov     [r12+r14+10h], eax
0x18001f9a3  mov     dword ptr [r12+r14+4], 6Dh ; 'm'
0x18001f9ac  mov     word ptr [r12+r14+8], 3
0x18001f9b4  call    ?PrOfVar@@YAIPEAUtagVARIANT@@@Z; PrOfVar(tagVARIANT *)
0x18001f9b9  cmp     eax, 0FFFFFFFFh
0x18001f9bc  mov     ecx, 4
0x18001f9c1  cmovz   eax, ecx
0x18001f9c4  inc     r15d
0x18001f9c7  mov     [r12+r14], eax
0x18001f9cb  lea     r12d, [rcx+6]
0x18001f9cf  mov     rax, [rsp+68h+arg_20]
0x18001f9d7  cmp     [rax], r12w
0x18001f9db  jz      short loc_18001FA55
0x18001f9dd  mov     rcx, [rsp+68h+arg_40]
0x18001f9e5  call    IsValidRel
0x18001f9ea  test    eax, eax
0x18001f9ec  jz      short loc_18001FA55
0x18001f9ee  cmp     r15d, ebp
0x18001f9f1  jnb     short loc_18001FA55
0x18001f9f3  mov     rcx, [rsp+68h+arg_20]; struct tagVARIANT *
0x18001f9fb  lea     rdx, [rsp+68h+var_48]; __int64 *
0x18001fa00  mov     r12d, r15d
0x18001fa03  shl     r12, 5
0x18001fa07  mov     word ptr [r12+r14+8], 0Ah
0x18001fa0f  call    ?VariantTimeToTime@@YAHPEAUtagVARIANT@@PEA_J@Z; VariantTimeToTime(tagVARIANT *,__int64 *)
0x18001fa14  test    eax, eax
0x18001fa16  jz      loc_18001F75A
0x18001fa1c  mov     eax, dword ptr [rsp+68h+var_48]
0x18001fa20  mov     rcx, [rsp+68h+arg_40]; pvarSrc
0x18001fa28  mov     [r12+r14+10h], eax
0x18001fa2d  mov     dword ptr [r12+r14+4], 6Eh ; 'n'
0x18001fa36  mov     word ptr [r12+r14+8], 3
0x18001fa3e  call    ?PrOfVar@@YAIPEAUtagVARIANT@@@Z; PrOfVar(tagVARIANT *)
0x18001fa43  cmp     eax, 0FFFFFFFFh
0x18001fa46  mov     ecx, 4
0x18001fa4b  cmovz   eax, ecx
0x18001fa4e  inc     r15d
0x18001fa51  mov     [r12+r14], eax
0x18001fa55  mov     r12, [rsp+68h+arg_48]
0x18001fa5d  mov     eax, 0Ah
0x18001fa62  cmp     [r12], ax
0x18001fa67  jz      loc_18001FB32
0x18001fa6d  mov     rcx, [rsp+68h+arg_50]
0x18001fa75  call    IsValidRel
0x18001fa7a  test    eax, eax
0x18001fa7c  jz      loc_18001FB32
0x18001fa82  cmp     r15d, ebp
0x18001fa85  jnb     loc_18001FB32
0x18001fa8b  shl     r15, 5
0x18001fa8f  mov     rcx, r12; struct tagVARIANT *
0x18001fa92  mov     word ptr [r15+r14+8], 0Ah
0x18001fa9a  call    ?GetBstr@@YAPEA_WPEAUtagVARIANT@@@Z; GetBstr(tagVARIANT *)
0x18001fa9f  mov     rbp, rax
0x18001faa2  test    rax, rax
0x18001faa5  jz      short loc_18001FB01
0x18001faa7  mov     rcx, rax; pbstr
0x18001faaa  call    cs:__imp_SysStringLen
0x18001fab0  test    eax, eax
0x18001fab2  jz      short loc_18001FB01
0x18001fab4  mov     rcx, rbp; pbstr
0x18001fab7  call    cs:__imp_SysStringLen
0x18001fabd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fac4  lea     ebx, [rax+1]
0x18001fac7  mov     eax, 2
0x18001facc  mul     rbx
0x18001facf  cmovb   rax, rcx
0x18001fad3  mov     rcx, rax; Size
0x18001fad6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fadb  mov     [r15+r14+10h], rax
  ... truncated ...
```
