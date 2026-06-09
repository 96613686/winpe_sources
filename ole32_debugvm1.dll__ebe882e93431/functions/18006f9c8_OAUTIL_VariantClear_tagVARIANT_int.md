# OAUTIL::VariantClear(tagVARIANT *,int)

- ea: `0x18006f9c8`
- end: `0x18006fc27`
- name: `?VariantClear@OAUTIL@@QEAAJPEAUtagVARIANT@@H@Z`
- size: `607`
- prototype: `HRESULT __fastcall(OAUTIL *this, tagVARIANT *pvarg, int fWeOwnByRefs)`
- caller_count: `7`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c36c`
- `0x1800692b0`
- `0x180069800`
- `0x180069f50`
- `0x18006f9c8`
- `0x18006fc30`
- `0x180072488`

## callees

- `0x180014ef8`
- `0x18001df18`
- `0x18006f2b4`
- `0x18006f9c8`
- `0x180072338`
- `0x1800ce010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18006fc07`
- `OLEAUT32!__imp_VariantClear` at `0x18006fc07`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006fba3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006fba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fa76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fa76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fbdd`

## pseudocode

```c
__int64 __fastcall OAUTIL::VariantClear(OAUTIL *this, ITypeInfo *pvarg, int fWeOwnByRefs)
{
  tagVARIANT *v4; // rdi
  HRESULT v7; // esi
  IRecordInfo *lpVtbl; // rcx
  struct IUnknownVtbl *v9; // rbx
  struct IUnknownVtbl *v10; // rax
  ICallFrameWalker *m_pWalkerFree; // rdx
  ICallFrameWalker *m_pWalkerWalk; // rbx
  __int16 v13; // ax
  __int64 *pllVal; // r14
  SAFEARRAY *v15; // rbx
  unsigned int cDims; // edx
  unsigned int cElements; // r12d
  unsigned int i; // ecx
  __int64 v19; // rax
  tagVARIANT *pvData; // rdi
  unsigned int v21; // r13d
  wchar_t *bstrVal; // rcx
  tagVARIANT *pvarVal; // rdx
  HRESULT v24; // eax
  InterfaceWalkerFree walkerFree; // [rsp+20h] [rbp-58h] BYREF
  ITypeInfo *ptinfo; // [rsp+88h] [rbp+10h] BYREF

  ptinfo = pvarg;
  v4 = (tagVARIANT *)pvarg;
  if ( !pvarg )
    return 2147500035LL;
  v7 = 0;
  if ( fWeOwnByRefs && ((__int64)pvarg->lpVtbl & 0xBFFF) == 0x24 )
  {
    lpVtbl = (IRecordInfo *)pvarg[2].lpVtbl;
    if ( lpVtbl )
    {
      v9 = pvarg[1].lpVtbl;
      if ( !v9 )
        goto LABEL_10;
      v10 = lpVtbl->lpVtbl;
      ptinfo = 0;
      v7 = ((__int64 (__fastcall *)(IRecordInfo *, ITypeInfo **))v10[3].QueryInterface)(lpVtbl, &ptinfo);
      if ( v7 >= 0 )
      {
        v7 = OAUTIL::FreeRecord(this, v9, ptinfo, fWeOwnByRefs);
        ((void (__fastcall *)(ITypeInfo *))ptinfo->lpVtbl->Release)(ptinfo);
        CoTaskMemFree(v9);
      }
      if ( v7 >= 0 )
      {
LABEL_10:
        if ( (v4->vt & 0x4000) == 0 )
          ((void (__fastcall *)(IRecordInfo *))v4->pRecInfo->lpVtbl->Release)(v4->pRecInfo);
        v4->vt = 0;
      }
    }
    return (unsigned int)v7;
  }
  m_pWalkerFree = this->m_pWalkerFree;
  if ( !m_pWalkerFree
    || (InterfaceWalkerFree::InterfaceWalkerFree(&walkerFree, m_pWalkerFree),
        m_pWalkerWalk = this->m_pWalkerWalk,
        this->m_pWalkerWalk = &walkerFree,
        v7 = OAUTIL::Walk(this, v4),
        this->m_pWalkerWalk = m_pWalkerWalk,
        walkerFree.lpVtbl = (struct IUnknownVtbl *)InterfaceWalkerFree::`vftable',
        Release<ICallFrameEvents>(&walkerFree.m_pWalker),
        v7 >= 0) )
  {
    if ( !fWeOwnByRefs || (v4->vt & 0x4000) == 0 )
    {
      v7 = VariantClear(v4);
      goto LABEL_40;
    }
    v13 = v4->vt & 0xBFFF;
    if ( (v4->vt & 0x2000) != 0 )
    {
      pllVal = v4->pllVal;
      if ( pllVal )
      {
        v15 = (SAFEARRAY *)*pllVal;
        if ( *pllVal && (v15->fFeatures & 0x800) != 0 )
        {
          cDims = v15->cDims;
          cElements = v15->rgsabound[0].cElements;
          for ( i = 1; i < cDims; cElements *= v15->rgsabound[v19].cElements )
            v19 = i++;
          pvData = (tagVARIANT *)v15->pvData;
          v7 = 0;
          v21 = 0;
          do
          {
            if ( v21 >= cElements )
              break;
            v7 = OAUTIL::VariantClear(this, pvData, 1);
            ++v21;
            pvData = (tagVARIANT *)((char *)pvData + v15->cbElements);
          }
          while ( v7 >= 0 );
          v4 = (tagVARIANT *)ptinfo;
          if ( v7 < 0 )
            goto LABEL_40;
        }
        else
        {
          v7 = 0;
        }
        if ( !*pllVal || (v7 = SafeArrayDestroy((SAFEARRAY *)*pllVal), v7 >= 0) )
        {
          CoTaskMemFree(pllVal);
          v4->llVal = 0;
        }
      }
LABEL_40:
      v4->vt = 0;
      return (unsigned int)v7;
    }
    if ( v13 != 9 )
    {
      if ( v13 == 12 )
      {
        pvarVal = v4->pvarVal;
        if ( !pvarVal )
          goto LABEL_40;
        v24 = OAUTIL::VariantClear(this, pvarVal, 1);
        bstrVal = v4->bstrVal;
        v7 = v24;
        goto LABEL_36;
      }
      if ( v13 != 13 )
        goto LABEL_40;
    }
    bstrVal = v4->bstrVal;
    if ( !bstrVal )
      goto LABEL_40;
LABEL_36:
    CoTaskMemFree(bstrVal);
    goto LABEL_40;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006f9c8  mov     [rsp+ptinfo], pvarg
0x18006f9cd  push    rbx
0x18006f9ce  push    rbp
0x18006f9cf  push    rsi
0x18006f9d0  push    rdi
0x18006f9d1  push    r12
0x18006f9d3  push    r13
0x18006f9d5  push    r14
0x18006f9d7  push    r15
0x18006f9d9  sub     rsp, 38h
0x18006f9dd  mov     ebp, fWeOwnByRefs
0x18006f9e0  mov     rdi, pvarg
0x18006f9e3  mov     r15, this
0x18006f9e6  test    pvarg, pvarg
0x18006f9e9  jnz     short loc_18006F9F5
0x18006f9eb  mov     eax, 80004003h
0x18006f9f0  jmp     loc_18006FC16
0x18006f9f5  xor     esi, esi
0x18006f9f7  test    ebp, ebp
0x18006f9f9  jz      loc_18006FAA8
0x18006f9ff  movzx   eax, word ptr [pvarg]
0x18006fa02  btr     eax, 0Eh
0x18006fa06  cmp     eax, 24h ; '$'
0x18006fa09  jnz     loc_18006FAA8
0x18006fa0f  mov     this, [pvarg+10h]
0x18006fa13  test    this, this
0x18006fa16  jz      loc_18006FC14
0x18006fa1c  mov     rbx, [pvarg+8]
0x18006fa20  test    rbx, rbx
0x18006fa23  jz      short loc_18006FA84
0x18006fa25  mov     rax, [this]
0x18006fa28  lea     pvarg, [rsp+78h+ptinfo]
0x18006fa30  mov     [rsp+78h+ptinfo], rsi
0x18006fa38  mov     rax, [rax+48h]
0x18006fa3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa41  mov     esi, eax
0x18006fa43  test    eax, eax
0x18006fa45  js      short loc_18006FA7C
0x18006fa47  mov     r8, [rsp+78h+ptinfo]; ptinfo
0x18006fa4f  mov     r9d, ebp; fWeOwnByRefs
0x18006fa52  mov     pvarg, rbx; pvSrc
0x18006fa55  mov     this, r15; this
0x18006fa58  call    ?FreeRecord@OAUTIL@@AEAAJPEAXPEAUITypeInfo@@H@Z; OAUTIL::FreeRecord(void *,ITypeInfo *,int)
0x18006fa5d  mov     this, [rsp+78h+ptinfo]
0x18006fa65  mov     esi, eax
0x18006fa67  mov     rax, [this]
0x18006fa6a  mov     rax, [rax+10h]
0x18006fa6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa73  mov     this, rbx; pv
0x18006fa76  call    cs:__imp_CoTaskMemFree
0x18006fa7c  test    esi, esi
0x18006fa7e  js      loc_18006FC14
0x18006fa84  mov     ecx, 4000h
0x18006fa89  test    [rdi], cx
0x18006fa8c  jnz     short loc_18006FA9E
0x18006fa8e  mov     this, [rdi+10h]
0x18006fa92  mov     pvarg, [this]
0x18006fa95  mov     rax, [pvarg+10h]
0x18006fa99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa9e  xor     ecx, ecx
0x18006faa0  mov     [rdi], cx
0x18006faa3  jmp     loc_18006FC14
0x18006faa8  mov     pvarg, [this+8]; p
0x18006faac  test    pvarg, pvarg
0x18006faaf  jz      short loc_18006FAF7
0x18006fab1  lea     this, [rsp+78h+walkerFree]; this
0x18006fab6  call    ??0InterfaceWalkerFree@@QEAA@PEAUICallFrameWalker@@@Z; InterfaceWalkerFree::InterfaceWalkerFree(ICallFrameWalker *)
0x18006fabb  mov     rbx, [r15+10h]
0x18006fabf  lea     rax, [rsp+78h+walkerFree]
0x18006fac4  mov     pvarg, rdi; pvar
0x18006fac7  mov     [r15+10h], rax
0x18006facb  mov     this, r15; this
0x18006face  call    ?Walk@OAUTIL@@QEAAJPEAUtagVARIANT@@@Z; OAUTIL::Walk(tagVARIANT *)
0x18006fad3  mov     esi, eax
0x18006fad5  mov     [r15+10h], rbx
0x18006fad9  lea     rax, ??_7InterfaceWalkerFree@@6B@; const InterfaceWalkerFree::`vftable'
0x18006fae0  lea     this, [rsp+78h+walkerFree.m_pWalker]; punk
0x18006fae5  mov     [rsp+78h+walkerFree.lpVtbl], rax
0x18006faea  call    ??$Release@UICallFrameEvents@@@@YAXAEAPEAUICallFrameEvents@@@Z; Release<ICallFrameEvents>(ICallFrameEvents * &)
0x18006faef  test    esi, esi
0x18006faf1  js      loc_18006FC14
0x18006faf7  test    ebp, ebp
0x18006faf9  jz      loc_18006FC04
0x18006faff  movzx   eax, word ptr [rdi]
0x18006fb02  bt      ax, 0Eh
0x18006fb07  jnb     loc_18006FC04
0x18006fb0d  mov     ecx, 0BFFFh
0x18006fb12  and     ax, cx
0x18006fb15  bt      ax, 0Dh
0x18006fb1a  jnb     loc_18006FBC2
0x18006fb20  mov     r14, [rdi+8]
0x18006fb24  test    r14, r14
0x18006fb27  jz      loc_18006FC0F
0x18006fb2d  mov     rbx, [r14]
0x18006fb30  test    rbx, rbx
0x18006fb33  jz      short loc_18006FB99
0x18006fb35  mov     eax, 800h
0x18006fb3a  test    [rbx+2], ax
0x18006fb3e  jz      short loc_18006FB99
0x18006fb40  movzx   edx, word ptr [rbx]
0x18006fb43  mov     ebp, 1
0x18006fb48  mov     r12d, [rbx+18h]
0x18006fb4c  mov     ecx, ebp
0x18006fb4e  cmp     edx, ebp
0x18006fb50  jbe     short loc_18006FB60
0x18006fb52  mov     eax, ecx
0x18006fb54  add     ecx, ebp
0x18006fb56  imul    r12d, [rbx+rax*8+18h]
0x18006fb5c  cmp     ecx, edx
0x18006fb5e  jb      short loc_18006FB52
0x18006fb60  mov     rdi, [rbx+10h]
0x18006fb64  xor     esi, esi
0x18006fb66  xor     r13d, r13d
0x18006fb69  cmp     r13d, r12d
0x18006fb6c  jnb     short loc_18006FB8B
0x18006fb6e  mov     fWeOwnByRefs, ebp; fWeOwnByRefs
0x18006fb71  mov     pvarg, rdi; pvarg
0x18006fb74  mov     this, r15; this
0x18006fb77  call    ?VariantClear@OAUTIL@@QEAAJPEAUtagVARIANT@@H@Z; OAUTIL::VariantClear(tagVARIANT *,int)
0x18006fb7c  mov     esi, eax
0x18006fb7e  add     r13d, ebp
0x18006fb81  mov     eax, [rbx+4]
0x18006fb84  add     rdi, rax
0x18006fb87  test    esi, esi
0x18006fb89  jns     short loc_18006FB69
0x18006fb8b  mov     rdi, [rsp+78h+ptinfo]
0x18006fb93  test    esi, esi
0x18006fb95  js      short loc_18006FC0F
0x18006fb97  jmp     short loc_18006FB9B
0x18006fb99  xor     esi, esi
0x18006fb9b  mov     this, [r14]; psa
0x18006fb9e  test    this, this
0x18006fba1  jz      short loc_18006FBAF
0x18006fba3  call    cs:__imp_SafeArrayDestroy
0x18006fba9  mov     esi, eax
0x18006fbab  test    eax, eax
0x18006fbad  js      short loc_18006FC0F
0x18006fbaf  mov     this, r14; pv
0x18006fbb2  call    cs:__imp_CoTaskMemFree
0x18006fbb8  mov     qword ptr [rdi+8], 0
0x18006fbc0  jmp     short loc_18006FC0F
0x18006fbc2  movzx   ecx, ax
0x18006fbc5  sub     ecx, 9
0x18006fbc8  jz      short loc_18006FBD4
0x18006fbca  sub     ecx, 3
0x18006fbcd  jz      short loc_18006FBE5
0x18006fbcf  cmp     ecx, 1
0x18006fbd2  jnz     short loc_18006FC0F
0x18006fbd4  mov     this, [rdi+8]; pv
0x18006fbd8  test    this, this
0x18006fbdb  jz      short loc_18006FC0F
0x18006fbdd  call    cs:__imp_CoTaskMemFree
0x18006fbe3  jmp     short loc_18006FC0F
0x18006fbe5  mov     pvarg, [rdi+8]; pvarg
0x18006fbe9  test    pvarg, pvarg
0x18006fbec  jz      short loc_18006FC0F
0x18006fbee  mov     fWeOwnByRefs, 1; fWeOwnByRefs
0x18006fbf4  mov     this, r15; this
0x18006fbf7  call    ?VariantClear@OAUTIL@@QEAAJPEAUtagVARIANT@@H@Z; OAUTIL::VariantClear(tagVARIANT *,int)
0x18006fbfc  mov     this, [rdi+8]
0x18006fc00  mov     esi, eax
0x18006fc02  jmp     short loc_18006FBDD
0x18006fc04  mov     this, rdi; pvarg
0x18006fc07  call    cs:__imp_VariantClear
0x18006fc0d  mov     esi, eax
0x18006fc0f  xor     eax, eax
0x18006fc11  mov     [rdi], ax
0x18006fc14  mov     eax, esi
0x18006fc16  add     rsp, 38h
0x18006fc1a  pop     r15
0x18006fc1c  pop     r14
0x18006fc1e  pop     r13
0x18006fc20  pop     r12
0x18006fc22  pop     rdi
0x18006fc23  pop     rsi
0x18006fc24  pop     rbp
0x18006fc25  pop     rbx
0x18006fc26  retn
```
