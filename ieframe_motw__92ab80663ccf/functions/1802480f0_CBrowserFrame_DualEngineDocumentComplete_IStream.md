# CBrowserFrame::DualEngineDocumentComplete(IStream *)

- ea: `0x1802480f0`
- end: `0x18024856d`
- name: `?DualEngineDocumentComplete@CBrowserFrame@@UEAAJPEAUIStream@@@Z`
- size: `1149`
- prototype: `int(CBrowserFrame *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180244dec`
- `0x180246ccc`
- `0x180246f60`
- `0x1802480f0`
- `0x18025011c`
- `0x1803dde24`
- `0x1803e3154`
- `0x1803e4830`
- `0x180594010`

## import_xrefs

- `iertutil!__imp_DSA_GetItemPtr` at `0x1802481ba`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802481f4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024822e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248268`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802482a2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802482dc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248316`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248350`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024838a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802483c4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802483fe`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248438`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248472`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802484ac`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802484e6`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248520`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802481ba`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802481f4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024822e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248268`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802482a2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802482dc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248316`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248350`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024838a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802483c4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802483fe`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248438`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248472`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802484ac`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802484e6`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180248520`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180248145`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180248145`

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
0x1802480f0  mov     [rsp-18h+arg_0], rbx
0x1802480f5  mov     [rsp-18h+arg_8], rsi
0x1802480fa  push    rbp
0x1802480fb  push    rdi
0x1802480fc  push    r14
0x1802480fe  mov     rbp, rsp
0x180248101  sub     rsp, 30h
0x180248105  mov     rdi, rdx
0x180248108  mov     rbx, rcx
0x18024810b  mov     dl, 1
0x18024810d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose> `wil::Feature<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::GetImpl(void)'::`2'::impl
0x180248114  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180248119  cmp     qword ptr [rbx+3E8h], 0
0x180248121  mov     r14d, 80004005h
0x180248127  mov     [rbp+arg_18], r14d
0x18024812b  jz      loc_18024854D
0x180248131  mov     r8d, 4; cb
0x180248137  mov     [rbp+pv], 0
0x18024813e  lea     rdx, [rbp+pv]; pv
0x180248142  mov     rcx, rdi; pstm
0x180248145  call    cs:__imp_IStream_Read
0x18024814c  nop     dword ptr [rax+rax+00h]
0x180248151  mov     [rbp+arg_18], eax
0x180248154  mov     r14d, eax
0x180248157  test    eax, eax
0x180248159  js      loc_18024854D
0x18024815f  mov     edx, 2
0x180248164  mov     [rbp+hdsa], 0
0x18024816c  lea     rcx, [rbp+hdsa]
0x180248170  call    ?Create@?$CDSA_Base@U__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@@@QEAAHH@Z; CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::Create(int)
0x180248175  mov     rcx, [rbx+3E8h]
0x18024817c  lea     r8, [rbp+hdsa]
0x180248180  mov     rdx, rdi
0x180248183  mov     rax, [rcx]
0x180248186  mov     rax, [rax+20h]
0x18024818a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024818f  mov     [rbp+arg_18], eax
0x180248192  mov     r14d, eax
0x180248195  test    eax, eax
0x180248197  js      loc_18024853D
0x18024819d  mov     rdi, [rbx+340h]
0x1802481a4  test    rdi, rdi
0x1802481a7  jz      short loc_1802481D7
0x1802481a9  mov     rcx, [rbp+hdsa]; hdsa
0x1802481ad  test    rcx, rcx
0x1802481b0  jz      short loc_1802481B6
0x1802481b2  mov     esi, [rcx]
0x1802481b4  jmp     short loc_1802481B8
0x1802481b6  xor     esi, esi
0x1802481b8  xor     edx, edx; i
0x1802481ba  call    cs:__imp_DSA_GetItemPtr
0x1802481c1  nop     dword ptr [rax+rax+00h]
0x1802481c6  mov     edx, [rbp+pv]; unsigned int
0x1802481c9  mov     r9d, esi; int
0x1802481cc  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802481cf  mov     rcx, rdi; this
0x1802481d2  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802481d7  mov     rdi, [rbx+348h]
0x1802481de  test    rdi, rdi
0x1802481e1  jz      short loc_180248211
0x1802481e3  mov     rcx, [rbp+hdsa]; hdsa
0x1802481e7  test    rcx, rcx
0x1802481ea  jz      short loc_1802481F0
0x1802481ec  mov     esi, [rcx]
0x1802481ee  jmp     short loc_1802481F2
0x1802481f0  xor     esi, esi
0x1802481f2  xor     edx, edx; i
0x1802481f4  call    cs:__imp_DSA_GetItemPtr
0x1802481fb  nop     dword ptr [rax+rax+00h]
0x180248200  mov     edx, [rbp+pv]; unsigned int
0x180248203  mov     r9d, esi; int
0x180248206  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180248209  mov     rcx, rdi; this
0x18024820c  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180248211  mov     rdi, [rbx+350h]
0x180248218  test    rdi, rdi
0x18024821b  jz      short loc_18024824B
0x18024821d  mov     rcx, [rbp+hdsa]; hdsa
0x180248221  test    rcx, rcx
0x180248224  jz      short loc_18024822A
0x180248226  mov     esi, [rcx]
0x180248228  jmp     short loc_18024822C
0x18024822a  xor     esi, esi
0x18024822c  xor     edx, edx; i
0x18024822e  call    cs:__imp_DSA_GetItemPtr
0x180248235  nop     dword ptr [rax+rax+00h]
0x18024823a  mov     edx, [rbp+pv]; unsigned int
0x18024823d  mov     r9d, esi; int
0x180248240  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180248243  mov     rcx, rdi; this
0x180248246  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024824b  mov     rdi, [rbx+358h]
0x180248252  test    rdi, rdi
0x180248255  jz      short loc_180248285
0x180248257  mov     rcx, [rbp+hdsa]; hdsa
0x18024825b  test    rcx, rcx
0x18024825e  jz      short loc_180248264
0x180248260  mov     esi, [rcx]
0x180248262  jmp     short loc_180248266
0x180248264  xor     esi, esi
0x180248266  xor     edx, edx; i
0x180248268  call    cs:__imp_DSA_GetItemPtr
0x18024826f  nop     dword ptr [rax+rax+00h]
0x180248274  mov     edx, [rbp+pv]; unsigned int
0x180248277  mov     r9d, esi; int
0x18024827a  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024827d  mov     rcx, rdi; this
0x180248280  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180248285  mov     rdi, [rbx+360h]
0x18024828c  test    rdi, rdi
0x18024828f  jz      short loc_1802482BF
0x180248291  mov     rcx, [rbp+hdsa]; hdsa
0x180248295  test    rcx, rcx
0x180248298  jz      short loc_18024829E
0x18024829a  mov     esi, [rcx]
0x18024829c  jmp     short loc_1802482A0
0x18024829e  xor     esi, esi
0x1802482a0  xor     edx, edx; i
0x1802482a2  call    cs:__imp_DSA_GetItemPtr
0x1802482a9  nop     dword ptr [rax+rax+00h]
0x1802482ae  mov     edx, [rbp+pv]; unsigned int
0x1802482b1  mov     r9d, esi; int
0x1802482b4  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802482b7  mov     rcx, rdi; this
0x1802482ba  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802482bf  mov     rdi, [rbx+368h]
0x1802482c6  test    rdi, rdi
0x1802482c9  jz      short loc_1802482F9
0x1802482cb  mov     rcx, [rbp+hdsa]; hdsa
0x1802482cf  test    rcx, rcx
0x1802482d2  jz      short loc_1802482D8
0x1802482d4  mov     esi, [rcx]
0x1802482d6  jmp     short loc_1802482DA
0x1802482d8  xor     esi, esi
0x1802482da  xor     edx, edx; i
0x1802482dc  call    cs:__imp_DSA_GetItemPtr
0x1802482e3  nop     dword ptr [rax+rax+00h]
0x1802482e8  mov     edx, [rbp+pv]; unsigned int
0x1802482eb  mov     r9d, esi; int
0x1802482ee  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802482f1  mov     rcx, rdi; this
0x1802482f4  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802482f9  mov     rdi, [rbx+370h]
0x180248300  test    rdi, rdi
0x180248303  jz      short loc_180248333
0x180248305  mov     rcx, [rbp+hdsa]; hdsa
0x180248309  test    rcx, rcx
0x18024830c  jz      short loc_180248312
0x18024830e  mov     esi, [rcx]
0x180248310  jmp     short loc_180248314
0x180248312  xor     esi, esi
0x180248314  xor     edx, edx; i
0x180248316  call    cs:__imp_DSA_GetItemPtr
0x18024831d  nop     dword ptr [rax+rax+00h]
0x180248322  mov     edx, [rbp+pv]; unsigned int
0x180248325  mov     r9d, esi; int
0x180248328  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024832b  mov     rcx, rdi; this
0x18024832e  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180248333  mov     rdi, [rbx+378h]
0x18024833a  test    rdi, rdi
0x18024833d  jz      short loc_18024836D
0x18024833f  mov     rcx, [rbp+hdsa]; hdsa
0x180248343  test    rcx, rcx
0x180248346  jz      short loc_18024834C
0x180248348  mov     esi, [rcx]
0x18024834a  jmp     short loc_18024834E
0x18024834c  xor     esi, esi
0x18024834e  xor     edx, edx; i
0x180248350  call    cs:__imp_DSA_GetItemPtr
0x180248357  nop     dword ptr [rax+rax+00h]
0x18024835c  mov     edx, [rbp+pv]; unsigned int
0x18024835f  mov     r9d, esi; int
0x180248362  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180248365  mov     rcx, rdi; this
0x180248368  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024836d  mov     rdi, [rbx+380h]
0x180248374  test    rdi, rdi
0x180248377  jz      short loc_1802483A7
0x180248379  mov     rcx, [rbp+hdsa]; hdsa
0x18024837d  test    rcx, rcx
0x180248380  jz      short loc_180248386
0x180248382  mov     esi, [rcx]
0x180248384  jmp     short loc_180248388
0x180248386  xor     esi, esi
0x180248388  xor     edx, edx; i
0x18024838a  call    cs:__imp_DSA_GetItemPtr
0x180248391  nop     dword ptr [rax+rax+00h]
0x180248396  mov     edx, [rbp+pv]; unsigned int
0x180248399  mov     r9d, esi; int
0x18024839c  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024839f  mov     rcx, rdi; this
0x1802483a2  call    ?OnDocumentComplete@CDualEngine6BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine6BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802483a7  mov     rdi, [rbx+388h]
0x1802483ae  test    rdi, rdi
0x1802483b1  jz      short loc_1802483E1
0x1802483b3  mov     rcx, [rbp+hdsa]; hdsa
0x1802483b7  test    rcx, rcx
0x1802483ba  jz      short loc_1802483C0
0x1802483bc  mov     esi, [rcx]
0x1802483be  jmp     short loc_1802483C2
0x1802483c0  xor     esi, esi
0x1802483c2  xor     edx, edx; i
0x1802483c4  call    cs:__imp_DSA_GetItemPtr
0x1802483cb  nop     dword ptr [rax+rax+00h]
0x1802483d0  mov     edx, [rbp+pv]; unsigned int
0x1802483d3  mov     r9d, esi; int
0x1802483d6  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802483d9  mov     rcx, rdi; this
0x1802483dc  call    ?OnDocumentComplete@CDualEngine14BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine14BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802483e1  mov     rdi, [rbx+390h]
0x1802483e8  test    rdi, rdi
0x1802483eb  jz      short loc_18024841B
0x1802483ed  mov     rcx, [rbp+hdsa]; hdsa
0x1802483f1  test    rcx, rcx
0x1802483f4  jz      short loc_1802483FA
0x1802483f6  mov     esi, [rcx]
0x1802483f8  jmp     short loc_1802483FC
0x1802483fa  xor     esi, esi
0x1802483fc  xor     edx, edx; i
0x1802483fe  call    cs:__imp_DSA_GetItemPtr
0x180248405  nop     dword ptr [rax+rax+00h]
0x18024840a  mov     edx, [rbp+pv]; unsigned int
0x18024840d  mov     r9d, esi; int
0x180248410  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180248413  mov     rcx, rdi; this
0x180248416  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024841b  mov     rdi, [rbx+398h]
0x180248422  test    rdi, rdi
0x180248425  jz      short loc_180248455
0x180248427  mov     rcx, [rbp+hdsa]; hdsa
0x18024842b  test    rcx, rcx
0x18024842e  jz      short loc_180248434
0x180248430  mov     esi, [rcx]
0x180248432  jmp     short loc_180248436
0x180248434  xor     esi, esi
0x180248436  xor     edx, edx; i
0x180248438  call    cs:__imp_DSA_GetItemPtr
0x18024843f  nop     dword ptr [rax+rax+00h]
0x180248444  mov     edx, [rbp+pv]; unsigned int
0x180248447  mov     r9d, esi; int
0x18024844a  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024844d  mov     rcx, rdi; this
0x180248450  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180248455  mov     rdi, [rbx+3A0h]
0x18024845c  test    rdi, rdi
0x18024845f  jz      short loc_18024848F
0x180248461  mov     rcx, [rbp+hdsa]; hdsa
0x180248465  test    rcx, rcx
0x180248468  jz      short loc_18024846E
0x18024846a  mov     esi, [rcx]
0x18024846c  jmp     short loc_180248470
0x18024846e  xor     esi, esi
0x180248470  xor     edx, edx; i
0x180248472  call    cs:__imp_DSA_GetItemPtr
0x180248479  nop     dword ptr [rax+rax+00h]
0x18024847e  mov     edx, [rbp+pv]; unsigned int
0x180248481  mov     r9d, esi; int
0x180248484  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180248487  mov     rcx, rdi; this
0x18024848a  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024848f  mov     rdi, [rbx+3A8h]
0x180248496  test    rdi, rdi
0x180248499  jz      short loc_1802484C9
0x18024849b  mov     rcx, [rbp+hdsa]; hdsa
0x18024849f  test    rcx, rcx
0x1802484a2  jz      short loc_1802484A8
0x1802484a4  mov     esi, [rcx]
0x1802484a6  jmp     short loc_1802484AA
0x1802484a8  xor     esi, esi
0x1802484aa  xor     edx, edx; i
0x1802484ac  call    cs:__imp_DSA_GetItemPtr
0x1802484b3  nop     dword ptr [rax+rax+00h]
0x1802484b8  mov     edx, [rbp+pv]; unsigned int
0x1802484bb  mov     r9d, esi; int
0x1802484be  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802484c1  mov     rcx, rdi; this
0x1802484c4  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802484c9  mov     rdi, [rbx+3B0h]
0x1802484d0  test    rdi, rdi
0x1802484d3  jz      short loc_180248503
0x1802484d5  mov     rcx, [rbp+hdsa]; hdsa
0x1802484d9  test    rcx, rcx
0x1802484dc  jz      short loc_1802484E2
0x1802484de  mov     esi, [rcx]
0x1802484e0  jmp     short loc_1802484E4
0x1802484e2  xor     esi, esi
0x1802484e4  xor     edx, edx; i
0x1802484e6  call    cs:__imp_DSA_GetItemPtr
0x1802484ed  nop     dword ptr [rax+rax+00h]
0x1802484f2  mov     edx, [rbp+pv]; unsigned int
0x1802484f5  mov     r9d, esi; int
0x1802484f8  mov     r8, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802484fb  mov     rcx, rdi; this
0x1802484fe  call    ?OnDocumentComplete@CDualEngine18BrowserCoupling@@QEAAXKPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine18BrowserCoupling::OnDocumentComplete(ulong,__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180248503  mov     rdi, [rbx+3B8h]
0x18024850a  test    rdi, rdi
0x18024850d  jz      short loc_18024853D
0x18024850f  mov     rcx, [rbp+hdsa]; hdsa
0x180248513  test    rcx, rcx
  ... truncated ...
```
