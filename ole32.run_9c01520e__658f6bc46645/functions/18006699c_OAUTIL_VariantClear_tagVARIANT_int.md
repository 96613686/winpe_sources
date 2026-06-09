# OAUTIL::VariantClear(tagVARIANT *,int)

- ea: `0x18006699c`
- end: `0x180066b6d`
- name: `?VariantClear@OAUTIL@@QEAAJPEAUtagVARIANT@@H@Z`
- size: `465`
- prototype: `HRESULT __fastcall(OAUTIL *this, tagVARIANT *pvarg, int fWeOwnByRefs)`
- caller_count: `8`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027674`
- `0x18005ed90`
- `0x18005f2a0`
- `0x18005fa40`
- `0x18006635c`
- `0x18006699c`
- `0x180066b74`
- `0x1800695e0`

## callees

- `0x180014c98`
- `0x18002ed58`
- `0x180066100`
- `0x18006635c`
- `0x18006699c`
- `0x1800693f8`
- `0x1800d8010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180066b3f`
- `OLEAUT32!__imp_VariantClear` at `0x180066b3f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066acd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066acd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b0f`

## pseudocode

```c
__int64 __fastcall OAUTIL::VariantClear(OAUTIL *this, tagVARIANT *pvarg, int fWeOwnByRefs)
{
  HRESULT v6; // esi
  IRecordInfo *pRecInfo; // r8
  wchar_t *v9; // rdx
  ICallFrameWalker *m_pWalkerFree; // rdx
  ICallFrameWalker *m_pWalkerWalk; // rbx
  __int16 v12; // ax
  tagSAFEARRAY **pparray; // rbx
  wchar_t *bstrVal; // rcx
  tagVARIANT *pvarVal; // rdx
  HRESULT v16; // eax
  InterfaceWalkerFree walkerFree; // [rsp+20h] [rbp-28h] BYREF

  v6 = 0;
  if ( !pvarg )
    return 2147500035LL;
  if ( !fWeOwnByRefs || (pvarg->vt & 0xBFFF) != 0x24 )
  {
    m_pWalkerFree = this->m_pWalkerFree;
    if ( m_pWalkerFree )
    {
      InterfaceWalkerFree::InterfaceWalkerFree(&walkerFree, m_pWalkerFree);
      m_pWalkerWalk = this->m_pWalkerWalk;
      this->m_pWalkerWalk = &walkerFree;
      v6 = OAUTIL::Walk(this, pvarg);
      this->m_pWalkerWalk = m_pWalkerWalk;
      walkerFree.lpVtbl = (struct IUnknownVtbl *)InterfaceWalkerFree::`vftable';
      Release<ICallFrameEvents>(&walkerFree.m_pWalker);
      if ( v6 < 0 )
        return (unsigned int)v6;
    }
    if ( !fWeOwnByRefs || (pvarg->vt & 0x4000) == 0 )
    {
      v6 = VariantClear(pvarg);
      goto LABEL_28;
    }
    v12 = pvarg->vt & 0xBFFF;
    if ( (pvarg->vt & 0x2000) != 0 )
    {
      pparray = pvarg->pparray;
      if ( pparray )
      {
        v6 = OAUTIL::SafeArrayClear(this, *pparray, fWeOwnByRefs);
        if ( v6 >= 0 )
        {
          if ( !*pparray || (v6 = SafeArrayDestroy(*pparray), v6 >= 0) )
          {
            CoTaskMemFree(pparray);
            pvarg->llVal = 0;
          }
        }
      }
      goto LABEL_28;
    }
    if ( v12 != 9 )
    {
      if ( v12 == 12 )
      {
        pvarVal = pvarg->pvarVal;
        if ( !pvarVal )
          goto LABEL_28;
        v16 = OAUTIL::VariantClear(this, pvarVal, 1);
        bstrVal = pvarg->bstrVal;
        v6 = v16;
        goto LABEL_24;
      }
      if ( v12 != 13 )
        goto LABEL_28;
    }
    bstrVal = pvarg->bstrVal;
    if ( !bstrVal )
      goto LABEL_28;
LABEL_24:
    CoTaskMemFree(bstrVal);
    goto LABEL_28;
  }
  pRecInfo = pvarg->pRecInfo;
  if ( !pRecInfo )
    return (unsigned int)v6;
  v9 = pvarg->bstrVal;
  if ( v9 )
  {
    v6 = OAUTIL::FreeRecord(this, v9, pRecInfo, fWeOwnByRefs);
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  if ( (pvarg->vt & 0x4000) == 0 )
    ((void (__fastcall *)(IRecordInfo *))pvarg->pRecInfo->lpVtbl->Release)(pvarg->pRecInfo);
LABEL_28:
  pvarg->vt = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006699c  mov     [rsp+arg_0], rbx
0x1800669a1  mov     [rsp+arg_10], rbp
0x1800669a6  mov     [rsp+arg_18], rsi
0x1800669ab  push    rdi
0x1800669ac  push    r14
0x1800669ae  push    r15
0x1800669b0  sub     rsp, 30h
0x1800669b4  xor     r15d, r15d
0x1800669b7  mov     r14d, fWeOwnByRefs
0x1800669ba  mov     rdi, pvarg
0x1800669bd  mov     rbp, this
0x1800669c0  mov     esi, r15d
0x1800669c3  test    pvarg, pvarg
0x1800669c6  jnz     short loc_1800669D2
0x1800669c8  mov     eax, 80004003h
0x1800669cd  jmp     loc_180066B53
0x1800669d2  test    r14d, r14d
0x1800669d5  jz      short loc_180066A2E
0x1800669d7  movzx   eax, word ptr [pvarg]
0x1800669da  btr     eax, 0Eh
0x1800669de  cmp     eax, 24h ; '$'
0x1800669e1  jnz     short loc_180066A2E
0x1800669e3  mov     r8, [pvarg+10h]; priRecord
0x1800669e7  test    r8, r8
0x1800669ea  jz      loc_180066B51
0x1800669f0  mov     pvarg, [pvarg+8]; pvRecord
0x1800669f4  test    pvarg, pvarg
0x1800669f7  jz      short loc_180066A0B
0x1800669f9  mov     r9d, r14d; fWeOwnByRefs
0x1800669fc  call    ?FreeRecord@OAUTIL@@AEAAJPEAXPEAUIRecordInfo@@H@Z; OAUTIL::FreeRecord(void *,IRecordInfo *,int)
0x180066a01  mov     esi, eax
0x180066a03  test    eax, eax
0x180066a05  js      loc_180066B51
0x180066a0b  mov     ecx, 4000h
0x180066a10  test    [rdi], cx
0x180066a13  jnz     loc_180066B4D
0x180066a19  mov     this, [rdi+10h]
0x180066a1d  mov     pvarg, [this]
0x180066a20  mov     rax, [pvarg+10h]
0x180066a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a29  jmp     loc_180066B4D
0x180066a2e  mov     pvarg, [this+8]; p
0x180066a32  test    pvarg, pvarg
0x180066a35  jz      short loc_180066A7D
0x180066a37  lea     this, [rsp+48h+walkerFree]; this
0x180066a3c  call    ??0InterfaceWalkerFree@@QEAA@PEAUICallFrameWalker@@@Z; InterfaceWalkerFree::InterfaceWalkerFree(ICallFrameWalker *)
0x180066a41  mov     rbx, [rbp+10h]
0x180066a45  lea     rax, [rsp+48h+walkerFree]
0x180066a4a  mov     pvarg, rdi; pvar
0x180066a4d  mov     [rbp+10h], rax
0x180066a51  mov     this, rbp; this
0x180066a54  call    ?Walk@OAUTIL@@QEAAJPEAUtagVARIANT@@@Z; OAUTIL::Walk(tagVARIANT *)
0x180066a59  mov     esi, eax
0x180066a5b  mov     [rbp+10h], rbx
0x180066a5f  lea     rax, ??_7InterfaceWalkerFree@@6B@; const InterfaceWalkerFree::`vftable'
0x180066a66  lea     this, [rsp+48h+walkerFree.m_pWalker]; punk
0x180066a6b  mov     [rsp+48h+walkerFree.lpVtbl], rax
0x180066a70  call    ??$Release@UICallFrameEvents@@@@YAXAEAPEAUICallFrameEvents@@@Z; Release<ICallFrameEvents>(ICallFrameEvents * &)
0x180066a75  test    esi, esi
0x180066a77  js      loc_180066B51
0x180066a7d  test    r14d, r14d
0x180066a80  jz      loc_180066B3C
0x180066a86  movzx   eax, word ptr [rdi]
0x180066a89  bt      ax, 0Eh
0x180066a8e  jnb     loc_180066B3C
0x180066a94  mov     ecx, 0BFFFh
0x180066a99  and     ax, cx
0x180066a9c  bt      ax, 0Dh
0x180066aa1  jnb     short loc_180066AF4
0x180066aa3  mov     rbx, [rdi+8]
0x180066aa7  test    rbx, rbx
0x180066aaa  jz      loc_180066B4D
0x180066ab0  mov     pvarg, [rbx]; psa
0x180066ab3  mov     this, rbp; this
0x180066ab6  call    ?SafeArrayClear@OAUTIL@@QEAAJPEAUtagSAFEARRAY@@H@Z; OAUTIL::SafeArrayClear(tagSAFEARRAY *,int)
0x180066abb  mov     esi, eax
0x180066abd  test    eax, eax
0x180066abf  js      loc_180066B4D
0x180066ac5  mov     this, [rbx]; psa
0x180066ac8  test    this, this
0x180066acb  jz      short loc_180066ADF
0x180066acd  call    cs:__imp_SafeArrayDestroy
0x180066ad4  nop     dword ptr [rax+rax+00h]
0x180066ad9  mov     esi, eax
0x180066adb  test    eax, eax
0x180066add  js      short loc_180066B4D
0x180066adf  mov     this, rbx; pv
0x180066ae2  call    cs:__imp_CoTaskMemFree
0x180066ae9  nop     dword ptr [rax+rax+00h]
0x180066aee  mov     [rdi+8], r15
0x180066af2  jmp     short loc_180066B4D
0x180066af4  movzx   ecx, ax
0x180066af7  sub     ecx, 9
0x180066afa  jz      short loc_180066B06
0x180066afc  sub     ecx, 3
0x180066aff  jz      short loc_180066B1D
0x180066b01  cmp     ecx, 1
0x180066b04  jnz     short loc_180066B4D
0x180066b06  mov     this, [rdi+8]; pv
0x180066b0a  test    this, this
0x180066b0d  jz      short loc_180066B4D
0x180066b0f  call    cs:__imp_CoTaskMemFree
0x180066b16  nop     dword ptr [rax+rax+00h]
0x180066b1b  jmp     short loc_180066B4D
0x180066b1d  mov     pvarg, [rdi+8]; pvarg
0x180066b21  test    pvarg, pvarg
0x180066b24  jz      short loc_180066B4D
0x180066b26  mov     fWeOwnByRefs, 1; fWeOwnByRefs
0x180066b2c  mov     this, rbp; this
0x180066b2f  call    ?VariantClear@OAUTIL@@QEAAJPEAUtagVARIANT@@H@Z; OAUTIL::VariantClear(tagVARIANT *,int)
0x180066b34  mov     this, [rdi+8]
0x180066b38  mov     esi, eax
0x180066b3a  jmp     short loc_180066B0F
0x180066b3c  mov     this, rdi; pvarg
0x180066b3f  call    cs:__imp_VariantClear
0x180066b46  nop     dword ptr [rax+rax+00h]
0x180066b4b  mov     esi, eax
0x180066b4d  mov     [rdi], r15w
0x180066b51  mov     eax, esi
0x180066b53  mov     rbx, [rsp+48h+arg_0]
0x180066b58  mov     rbp, [rsp+48h+arg_10]
0x180066b5d  mov     rsi, [rsp+48h+arg_18]
0x180066b62  add     rsp, 30h
0x180066b66  pop     r15
0x180066b68  pop     r14
0x180066b6a  pop     rdi
0x180066b6b  retn
```
