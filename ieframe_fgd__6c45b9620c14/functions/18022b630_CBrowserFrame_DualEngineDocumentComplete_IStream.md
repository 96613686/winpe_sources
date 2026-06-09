# CBrowserFrame::DualEngineDocumentComplete(IStream *)

- ea: `0x18022b630`
- end: `0x18022ba46`
- name: `?DualEngineDocumentComplete@CBrowserFrame@@UEAAJPEAUIStream@@@Z`
- size: `1046`
- prototype: `int(CBrowserFrame *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180228510`
- `0x18022a2a4`
- `0x18022a530`
- `0x18022b630`
- `0x1802330ac`
- `0x1803aba34`
- `0x1803b0c00`
- `0x1803b2230`
- `0x180550010`

## import_xrefs

- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b6f4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b728`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b75c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b790`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b7c4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b7f8`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b82c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b860`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b894`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b8c8`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b8fc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b930`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b964`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b998`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b9cc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ba00`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b6f4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b728`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b75c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b790`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b7c4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b7f8`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b82c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b860`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b894`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b8c8`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b8fc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b930`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b964`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b998`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022b9cc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ba00`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022b685`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022b685`

## pseudocode

```c
__int64 __fastcall CBrowserFrame::DualEngineDocumentComplete(CBrowserFrame *this, struct IStream *a2)
{
  IStream *v2; // rdi
  bool v4; // zf
  unsigned int v5; // r14d
  CDualEngine6BrowserCoupling *v6; // rdi
  int v7; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *ItemPtr; // rax
  CDualEngine6BrowserCoupling *v9; // rdi
  int v10; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v11; // rax
  CDualEngine6BrowserCoupling *v12; // rdi
  int v13; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v14; // rax
  CDualEngine6BrowserCoupling *v15; // rdi
  int v16; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v17; // rax
  CDualEngine6BrowserCoupling *v18; // rdi
  int v19; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v20; // rax
  CDualEngine6BrowserCoupling *v21; // rdi
  int v22; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v23; // rax
  CDualEngine6BrowserCoupling *v24; // rdi
  int v25; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v26; // rax
  CDualEngine6BrowserCoupling *v27; // rdi
  int v28; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v29; // rax
  CDualEngine6BrowserCoupling *v30; // rdi
  int v31; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v32; // rax
  CDualEngine14BrowserCoupling *v33; // rdi
  int v34; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v35; // rax
  CDualEngine18BrowserCoupling *v36; // rdi
  int v37; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v38; // rax
  CDualEngine18BrowserCoupling *v39; // rdi
  int v40; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v41; // rax
  CDualEngine18BrowserCoupling *v42; // rdi
  int v43; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v44; // rax
  CDualEngine18BrowserCoupling *v45; // rdi
  int v46; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v47; // rax
  CDualEngine18BrowserCoupling *v48; // rdi
  int v49; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v50; // rax
  CDualEngine18BrowserCoupling *v51; // rdi
  int v52; // ebx
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v53; // rax
  HDSA hdsa[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int pv; // [rsp+60h] [rbp+30h] BYREF
  HRESULT v57; // [rsp+68h] [rbp+38h] BYREF

  v2 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::GetImpl'::`2'::impl,
    a2);
  v4 = *((_QWORD *)this + 125) == 0;
  v5 = -2147467259;
  v57 = -2147467259;
  if ( !v4 )
  {
    pv = 0;
    v57 = IStream_Read(v2, &pv, 4u);
    v5 = v57;
    if ( v57 >= 0 )
    {
      hdsa[0] = 0;
      CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::Create(hdsa, 2);
      v57 = (*(__int64 (__fastcall **)(_QWORD, IStream *, HDSA *))(**((_QWORD **)this + 125) + 32LL))(
              *((_QWORD *)this + 125),
              v2,
              hdsa);
      v5 = v57;
      if ( v57 >= 0 )
      {
        v6 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 104);
        if ( v6 )
        {
          if ( hdsa[0] )
            v7 = *(_DWORD *)hdsa[0];
          else
            v7 = 0;
          ItemPtr = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v6, pv, ItemPtr, v7);
        }
        v9 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 105);
        if ( v9 )
        {
          if ( hdsa[0] )
            v10 = *(_DWORD *)hdsa[0];
          else
            v10 = 0;
          v11 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v9, pv, v11, v10);
        }
        v12 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 106);
        if ( v12 )
        {
          if ( hdsa[0] )
            v13 = *(_DWORD *)hdsa[0];
          else
            v13 = 0;
          v14 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v12, pv, v14, v13);
        }
        v15 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 107);
        if ( v15 )
        {
          if ( hdsa[0] )
            v16 = *(_DWORD *)hdsa[0];
          else
            v16 = 0;
          v17 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v15, pv, v17, v16);
        }
        v18 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 108);
        if ( v18 )
        {
          if ( hdsa[0] )
            v19 = *(_DWORD *)hdsa[0];
          else
            v19 = 0;
          v20 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v18, pv, v20, v19);
        }
        v21 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 109);
        if ( v21 )
        {
          if ( hdsa[0] )
            v22 = *(_DWORD *)hdsa[0];
          else
            v22 = 0;
          v23 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v21, pv, v23, v22);
        }
        v24 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 110);
        if ( v24 )
        {
          if ( hdsa[0] )
            v25 = *(_DWORD *)hdsa[0];
          else
            v25 = 0;
          v26 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v24, pv, v26, v25);
        }
        v27 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 111);
        if ( v27 )
        {
          if ( hdsa[0] )
            v28 = *(_DWORD *)hdsa[0];
          else
            v28 = 0;
          v29 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v27, pv, v29, v28);
        }
        v30 = (CDualEngine6BrowserCoupling *)*((_QWORD *)this + 112);
        if ( v30 )
        {
          if ( hdsa[0] )
            v31 = *(_DWORD *)hdsa[0];
          else
            v31 = 0;
          v32 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine6BrowserCoupling::OnDocumentComplete(v30, pv, v32, v31);
        }
        v33 = (CDualEngine14BrowserCoupling *)*((_QWORD *)this + 113);
        if ( v33 )
        {
          if ( hdsa[0] )
            v34 = *(_DWORD *)hdsa[0];
          else
            v34 = 0;
          v35 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine14BrowserCoupling::OnDocumentComplete(v33, pv, v35, v34);
        }
        v36 = (CDualEngine18BrowserCoupling *)*((_QWORD *)this + 114);
        if ( v36 )
        {
          if ( hdsa[0] )
            v37 = *(_DWORD *)hdsa[0];
          else
            v37 = 0;
          v38 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine18BrowserCoupling::OnDocumentComplete(v36, pv, v38, v37);
        }
        v39 = (CDualEngine18BrowserCoupling *)*((_QWORD *)this + 115);
        if ( v39 )
        {
          if ( hdsa[0] )
            v40 = *(_DWORD *)hdsa[0];
          else
            v40 = 0;
          v41 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine18BrowserCoupling::OnDocumentComplete(v39, pv, v41, v40);
        }
        v42 = (CDualEngine18BrowserCoupling *)*((_QWORD *)this + 116);
        if ( v42 )
        {
          if ( hdsa[0] )
            v43 = *(_DWORD *)hdsa[0];
          else
            v43 = 0;
          v44 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine18BrowserCoupling::OnDocumentComplete(v42, pv, v44, v43);
        }
        v45 = (CDualEngine18BrowserCoupling *)*((_QWORD *)this + 117);
        if ( v45 )
        {
          if ( hdsa[0] )
            v46 = *(_DWORD *)hdsa[0];
          else
            v46 = 0;
          v47 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine18BrowserCoupling::OnDocumentComplete(v45, pv, v47, v46);
        }
        v48 = (CDualEngine18BrowserCoupling *)*((_QWORD *)this + 118);
        if ( v48 )
        {
          if ( hdsa[0] )
            v49 = *(_DWORD *)hdsa[0];
          else
            v49 = 0;
          v50 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine18BrowserCoupling::OnDocumentComplete(v48, pv, v50, v49);
        }
        v51 = (CDualEngine18BrowserCoupling *)*((_QWORD *)this + 119);
        if ( v51 )
        {
          if ( hdsa[0] )
            v52 = *(_DWORD *)hdsa[0];
          else
            v52 = 0;
          v53 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa[0], 0);
          CDualEngine18BrowserCoupling::OnDocumentComplete(v51, pv, v53, v52);
        }
      }
      CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::DestroyCallback(
        hdsa,
        CBrowserFrame::DualEngineDestroyVisibleListUpdateEntry);
    }
  }
  BrowserTelemetry::IEModeDocumentCompleteEvent<long &>(&v57);
  return v5;
}

```

## disassembly

```asm
0x18022b630  mov     [rsp-18h+arg_0], rbx
0x18022b635  mov     [rsp-18h+arg_8], rsi
0x18022b63a  push    rbp
0x18022b63b  push    rdi
0x18022b63c  push    r14
0x18022b63e  mov     rbp, rsp
0x18022b641  sub     rsp, 30h
0x18022b645  mov     rdi, rdx
0x18022b648  mov     rbx, rcx
0x18022b64b  mov     dl, 1
0x18022b64d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose> `wil::Feature<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::GetImpl(void)'::`2'::impl
0x18022b654  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18022b659  cmp     qword ptr [rbx+3E8h], 0
0x18022b661  mov     r14d, 80004005h
0x18022b667  mov     [rbp+arg_18], r14d
0x18022b66b  jz      loc_18022BA27
0x18022b671  mov     r8d, 4; cb
0x18022b677  mov     [rbp+pv], 0
0x18022b67e  lea     rdx, [rbp+pv]; pv
0x18022b682  mov     rcx, rdi; pstm
0x18022b685  call    cs:__imp_IStream_Read
0x18022b68b  mov     [rbp+arg_18], eax
0x18022b68e  mov     r14d, eax
0x18022b691  test    eax, eax
0x18022b693  js      loc_18022BA27
0x18022b699  mov     edx, 2
0x18022b69e  mov     [rbp+hdsa], 0
0x18022b6a6  lea     rcx, [rbp+hdsa]
0x18022b6aa  call    ?Create@?$CDSA_Base@U__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@@@QEAAHH@Z; CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::Create(int)
0x18022b6af  mov     rcx, [rbx+3E8h]
0x18022b6b6  lea     r8, [rbp+hdsa]
0x18022b6ba  mov     rdx, rdi
0x18022b6bd  mov     rax, [rcx]
0x18022b6c0  mov     rax, [rax+20h]
0x18022b6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022b6c9  mov     [rbp+arg_18], eax
0x18022b6cc  mov     r14d, eax
0x18022b6cf  test    eax, eax
0x18022b6d1  js      loc_18022BA17
0x18022b6d7  mov     rdi, [rbx+340h]
0x18022b6de  test    rdi, rdi
0x18022b6e1  jz      short loc_18022B70B
0x18022b6e3  mov     rcx, [rbp+hdsa]; hdsa
0x18022b6e7  test    rcx, rcx
0x18022b6ea  jz      short loc_18022B6F0
0x18022b6ec  mov     esi, [rcx]
0x18022b6ee  jmp     short loc_18022B6F2
0x18022b6f0  xor     esi, esi
0x18022b6f2  xor     edx, edx; i
0x18022b6f4  call    cs:__imp_DSA_GetItemPtr
0x18022b6fa  mov     edx, [rbp+pv]; unsigned int
0x18022b6fd  mov     r9d, esi; int
0x18022b700  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b703  mov     rcx, rdi; this
0x18022b706  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b70b  mov     rdi, [rbx+348h]
0x18022b712  test    rdi, rdi
0x18022b715  jz      short loc_18022B73F
0x18022b717  mov     rcx, [rbp+hdsa]; hdsa
0x18022b71b  test    rcx, rcx
0x18022b71e  jz      short loc_18022B724
0x18022b720  mov     esi, [rcx]
0x18022b722  jmp     short loc_18022B726
0x18022b724  xor     esi, esi
0x18022b726  xor     edx, edx; i
0x18022b728  call    cs:__imp_DSA_GetItemPtr
0x18022b72e  mov     edx, [rbp+pv]; unsigned int
0x18022b731  mov     r9d, esi; int
0x18022b734  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b737  mov     rcx, rdi; this
0x18022b73a  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b73f  mov     rdi, [rbx+350h]
0x18022b746  test    rdi, rdi
0x18022b749  jz      short loc_18022B773
0x18022b74b  mov     rcx, [rbp+hdsa]; hdsa
0x18022b74f  test    rcx, rcx
0x18022b752  jz      short loc_18022B758
0x18022b754  mov     esi, [rcx]
0x18022b756  jmp     short loc_18022B75A
0x18022b758  xor     esi, esi
0x18022b75a  xor     edx, edx; i
0x18022b75c  call    cs:__imp_DSA_GetItemPtr
0x18022b762  mov     edx, [rbp+pv]; unsigned int
0x18022b765  mov     r9d, esi; int
0x18022b768  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b76b  mov     rcx, rdi; this
0x18022b76e  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b773  mov     rdi, [rbx+358h]
0x18022b77a  test    rdi, rdi
0x18022b77d  jz      short loc_18022B7A7
0x18022b77f  mov     rcx, [rbp+hdsa]; hdsa
0x18022b783  test    rcx, rcx
0x18022b786  jz      short loc_18022B78C
0x18022b788  mov     esi, [rcx]
0x18022b78a  jmp     short loc_18022B78E
0x18022b78c  xor     esi, esi
0x18022b78e  xor     edx, edx; i
0x18022b790  call    cs:__imp_DSA_GetItemPtr
0x18022b796  mov     edx, [rbp+pv]; unsigned int
0x18022b799  mov     r9d, esi; int
0x18022b79c  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b79f  mov     rcx, rdi; this
0x18022b7a2  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b7a7  mov     rdi, [rbx+360h]
0x18022b7ae  test    rdi, rdi
0x18022b7b1  jz      short loc_18022B7DB
0x18022b7b3  mov     rcx, [rbp+hdsa]; hdsa
0x18022b7b7  test    rcx, rcx
0x18022b7ba  jz      short loc_18022B7C0
0x18022b7bc  mov     esi, [rcx]
0x18022b7be  jmp     short loc_18022B7C2
0x18022b7c0  xor     esi, esi
0x18022b7c2  xor     edx, edx; i
0x18022b7c4  call    cs:__imp_DSA_GetItemPtr
0x18022b7ca  mov     edx, [rbp+pv]; unsigned int
0x18022b7cd  mov     r9d, esi; int
0x18022b7d0  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b7d3  mov     rcx, rdi; this
0x18022b7d6  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b7db  mov     rdi, [rbx+368h]
0x18022b7e2  test    rdi, rdi
0x18022b7e5  jz      short loc_18022B80F
0x18022b7e7  mov     rcx, [rbp+hdsa]; hdsa
0x18022b7eb  test    rcx, rcx
0x18022b7ee  jz      short loc_18022B7F4
0x18022b7f0  mov     esi, [rcx]
0x18022b7f2  jmp     short loc_18022B7F6
0x18022b7f4  xor     esi, esi
0x18022b7f6  xor     edx, edx; i
0x18022b7f8  call    cs:__imp_DSA_GetItemPtr
0x18022b7fe  mov     edx, [rbp+pv]; unsigned int
0x18022b801  mov     r9d, esi; int
0x18022b804  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b807  mov     rcx, rdi; this
0x18022b80a  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b80f  mov     rdi, [rbx+370h]
0x18022b816  test    rdi, rdi
0x18022b819  jz      short loc_18022B843
0x18022b81b  mov     rcx, [rbp+hdsa]; hdsa
0x18022b81f  test    rcx, rcx
0x18022b822  jz      short loc_18022B828
0x18022b824  mov     esi, [rcx]
0x18022b826  jmp     short loc_18022B82A
0x18022b828  xor     esi, esi
0x18022b82a  xor     edx, edx; i
0x18022b82c  call    cs:__imp_DSA_GetItemPtr
0x18022b832  mov     edx, [rbp+pv]; unsigned int
0x18022b835  mov     r9d, esi; int
0x18022b838  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b83b  mov     rcx, rdi; this
0x18022b83e  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b843  mov     rdi, [rbx+378h]
0x18022b84a  test    rdi, rdi
0x18022b84d  jz      short loc_18022B877
0x18022b84f  mov     rcx, [rbp+hdsa]; hdsa
0x18022b853  test    rcx, rcx
0x18022b856  jz      short loc_18022B85C
0x18022b858  mov     esi, [rcx]
0x18022b85a  jmp     short loc_18022B85E
0x18022b85c  xor     esi, esi
0x18022b85e  xor     edx, edx; i
0x18022b860  call    cs:__imp_DSA_GetItemPtr
0x18022b866  mov     edx, [rbp+pv]; unsigned int
0x18022b869  mov     r9d, esi; int
0x18022b86c  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b86f  mov     rcx, rdi; this
0x18022b872  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b877  mov     rdi, [rbx+380h]
0x18022b87e  test    rdi, rdi
0x18022b881  jz      short loc_18022B8AB
0x18022b883  mov     rcx, [rbp+hdsa]; hdsa
0x18022b887  test    rcx, rcx
0x18022b88a  jz      short loc_18022B890
0x18022b88c  mov     esi, [rcx]
0x18022b88e  jmp     short loc_18022B892
0x18022b890  xor     esi, esi
0x18022b892  xor     edx, edx; i
0x18022b894  call    cs:__imp_DSA_GetItemPtr
0x18022b89a  mov     edx, [rbp+pv]; unsigned int
0x18022b89d  mov     r9d, esi; int
0x18022b8a0  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b8a3  mov     rcx, rdi; this
0x18022b8a6  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b8ab  mov     rdi, [rbx+388h]
0x18022b8b2  test    rdi, rdi
0x18022b8b5  jz      short loc_18022B8DF
0x18022b8b7  mov     rcx, [rbp+hdsa]; hdsa
0x18022b8bb  test    rcx, rcx
0x18022b8be  jz      short loc_18022B8C4
0x18022b8c0  mov     esi, [rcx]
0x18022b8c2  jmp     short loc_18022B8C6
0x18022b8c4  xor     esi, esi
0x18022b8c6  xor     edx, edx; i
0x18022b8c8  call    cs:__imp_DSA_GetItemPtr
0x18022b8ce  mov     edx, [rbp+pv]; unsigned int
0x18022b8d1  mov     r9d, esi; int
0x18022b8d4  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b8d7  mov     rcx, rdi; this
0x18022b8da  call    ?OnDocumentComplete@CDualEngine14BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine14BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b8df  mov     rdi, [rbx+390h]
0x18022b8e6  test    rdi, rdi
0x18022b8e9  jz      short loc_18022B913
0x18022b8eb  mov     rcx, [rbp+hdsa]; hdsa
0x18022b8ef  test    rcx, rcx
0x18022b8f2  jz      short loc_18022B8F8
0x18022b8f4  mov     esi, [rcx]
0x18022b8f6  jmp     short loc_18022B8FA
0x18022b8f8  xor     esi, esi
0x18022b8fa  xor     edx, edx; i
0x18022b8fc  call    cs:__imp_DSA_GetItemPtr
0x18022b902  mov     edx, [rbp+pv]; unsigned int
0x18022b905  mov     r9d, esi; int
0x18022b908  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b90b  mov     rcx, rdi; this
0x18022b90e  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b913  mov     rdi, [rbx+398h]
0x18022b91a  test    rdi, rdi
0x18022b91d  jz      short loc_18022B947
0x18022b91f  mov     rcx, [rbp+hdsa]; hdsa
0x18022b923  test    rcx, rcx
0x18022b926  jz      short loc_18022B92C
0x18022b928  mov     esi, [rcx]
0x18022b92a  jmp     short loc_18022B92E
0x18022b92c  xor     esi, esi
0x18022b92e  xor     edx, edx; i
0x18022b930  call    cs:__imp_DSA_GetItemPtr
0x18022b936  mov     edx, [rbp+pv]; unsigned int
0x18022b939  mov     r9d, esi; int
0x18022b93c  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b93f  mov     rcx, rdi; this
0x18022b942  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b947  mov     rdi, [rbx+3A0h]
0x18022b94e  test    rdi, rdi
0x18022b951  jz      short loc_18022B97B
0x18022b953  mov     rcx, [rbp+hdsa]; hdsa
0x18022b957  test    rcx, rcx
0x18022b95a  jz      short loc_18022B960
0x18022b95c  mov     esi, [rcx]
0x18022b95e  jmp     short loc_18022B962
0x18022b960  xor     esi, esi
0x18022b962  xor     edx, edx; i
0x18022b964  call    cs:__imp_DSA_GetItemPtr
0x18022b96a  mov     edx, [rbp+pv]; unsigned int
0x18022b96d  mov     r9d, esi; int
0x18022b970  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b973  mov     rcx, rdi; this
0x18022b976  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b97b  mov     rdi, [rbx+3A8h]
0x18022b982  test    rdi, rdi
0x18022b985  jz      short loc_18022B9AF
0x18022b987  mov     rcx, [rbp+hdsa]; hdsa
0x18022b98b  test    rcx, rcx
0x18022b98e  jz      short loc_18022B994
0x18022b990  mov     esi, [rcx]
0x18022b992  jmp     short loc_18022B996
0x18022b994  xor     esi, esi
0x18022b996  xor     edx, edx; i
0x18022b998  call    cs:__imp_DSA_GetItemPtr
0x18022b99e  mov     edx, [rbp+pv]; unsigned int
0x18022b9a1  mov     r9d, esi; int
0x18022b9a4  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b9a7  mov     rcx, rdi; this
0x18022b9aa  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b9af  mov     rdi, [rbx+3B0h]
0x18022b9b6  test    rdi, rdi
0x18022b9b9  jz      short loc_18022B9E3
0x18022b9bb  mov     rcx, [rbp+hdsa]; hdsa
0x18022b9bf  test    rcx, rcx
0x18022b9c2  jz      short loc_18022B9C8
0x18022b9c4  mov     esi, [rcx]
0x18022b9c6  jmp     short loc_18022B9CA
0x18022b9c8  xor     esi, esi
0x18022b9ca  xor     edx, edx; i
0x18022b9cc  call    cs:__imp_DSA_GetItemPtr
0x18022b9d2  mov     edx, [rbp+pv]; unsigned int
0x18022b9d5  mov     r9d, esi; int
0x18022b9d8  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022b9db  mov     rcx, rdi; this
0x18022b9de  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022b9e3  mov     rdi, [rbx+3B8h]
0x18022b9ea  test    rdi, rdi
0x18022b9ed  jz      short loc_18022BA17
0x18022b9ef  mov     rcx, [rbp+hdsa]; hdsa
0x18022b9f3  test    rcx, rcx
0x18022b9f6  jz      short loc_18022B9FC
0x18022b9f8  mov     ebx, [rcx]
0x18022b9fa  jmp     short loc_18022B9FE
0x18022b9fc  xor     ebx, ebx
0x18022b9fe  xor     edx, edx; i
0x18022ba00  call    cs:__imp_DSA_GetItemPtr
0x18022ba06  mov     edx, [rbp+pv]; unsigned int
0x18022ba09  mov     r9d, ebx; int
0x18022ba0c  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ba0f  mov     rcx, rdi; this
0x18022ba12  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ba17  lea     rdx, ?DualEngineDestroyVisibleListUpdateEntry@CBrowserFrame@@KAHPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@PEAX@Z; CBrowserFrame::DualEngineDestroyVisibleListUpdateEntry(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,void *)
0x18022ba1e  lea     rcx, [rbp+hdsa]
0x18022ba22  call    ?DestroyCallback@?$CDSA_Base@U__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@@@QEAAXP6AHPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@PEAX@Z1@Z; CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::DestroyCallback(int (*)(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,void *),void *)
0x18022ba27  lea     rcx, [rbp+arg_18]
0x18022ba2b  call    ??$IEModeDocumentCompleteEvent@AEAJ@BrowserTelemetry@@SAXAEAJ@Z; BrowserTelemetry::IEModeDocumentCompleteEvent<long &>(long &)
  ... truncated ...
```
