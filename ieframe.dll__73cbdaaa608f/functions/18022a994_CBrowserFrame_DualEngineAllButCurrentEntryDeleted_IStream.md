# CBrowserFrame::DualEngineAllButCurrentEntryDeleted(IStream *)

- ea: `0x18022a994`
- end: `0x18022ad31`
- name: `?DualEngineAllButCurrentEntryDeleted@CBrowserFrame@@QEAAXPEAUIStream@@@Z`
- size: `925`
- prototype: `void __fastcall(CBrowserFrame *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18025d568`

## callees

- `0x18022a2a4`
- `0x18022a530`
- `0x18022a994`
- `0x180233020`
- `0x1802330ac`
- `0x1803aba18`
- `0x1803b0be4`
- `0x1803b2214`
- `0x180550010`

## import_xrefs

- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aa25`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aa56`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aa87`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aab8`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aae9`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ab1a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ab4b`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ab7c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022abad`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022abde`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ac0f`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ac40`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ac71`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aca2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022acd3`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ad04`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aa25`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aa56`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aa87`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aab8`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aae9`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ab1a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ab4b`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ab7c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022abad`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022abde`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ac0f`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ac40`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ac71`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022aca2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022acd3`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18022ad04`

## pseudocode

```c
void __fastcall CBrowserFrame::DualEngineAllButCurrentEntryDeleted(CBrowserFrame *this, struct IStream *a2)
{
  struct IStream *v2; // rdi
  __int64 v4; // rdx
  CDualEngine13BrowserCoupling *v5; // rdi
  int v6; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *ItemPtr; // rax
  CDualEngine13BrowserCoupling *v8; // rdi
  int v9; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v10; // rax
  CDualEngine13BrowserCoupling *v11; // rdi
  int v12; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v13; // rax
  CDualEngine13BrowserCoupling *v14; // rdi
  int v15; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v16; // rax
  CDualEngine13BrowserCoupling *v17; // rdi
  int v18; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v19; // rax
  CDualEngine13BrowserCoupling *v20; // rdi
  int v21; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v22; // rax
  CDualEngine13BrowserCoupling *v23; // rdi
  int v24; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v25; // rax
  CDualEngine13BrowserCoupling *v26; // rdi
  int v27; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v28; // rax
  CDualEngine13BrowserCoupling *v29; // rdi
  int v30; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v31; // rax
  CDualEngine14BrowserCoupling *v32; // rdi
  int v33; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v34; // rax
  CDualEngine19BrowserCoupling *v35; // rdi
  int v36; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v37; // rax
  CDualEngine19BrowserCoupling *v38; // rdi
  int v39; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v40; // rax
  CDualEngine19BrowserCoupling *v41; // rdi
  int v42; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v43; // rax
  CDualEngine19BrowserCoupling *v44; // rdi
  int v45; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v46; // rax
  CDualEngine19BrowserCoupling *v47; // rdi
  int v48; // esi
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v49; // rax
  CDualEngine19BrowserCoupling *v50; // rdi
  int v51; // ebx
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v52; // rax
  HDSA hdsa; // [rsp+60h] [rbp+38h] BYREF

  v2 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::GetImpl'::`2'::impl,
    a2);
  if ( *((_QWORD *)this + 153) )
  {
    LOBYTE(v4) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization>::GetImpl'::`2'::impl,
      v4);
    hdsa = 0;
    CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::Create(&hdsa, 1);
    if ( (*(int (__fastcall **)(_QWORD, struct IStream *, HDSA *))(**((_QWORD **)this + 153) + 40LL))(
           *((_QWORD *)this + 153),
           v2,
           &hdsa) >= 0 )
    {
      v5 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 132);
      if ( v5 )
      {
        if ( hdsa )
          v6 = *(_DWORD *)hdsa;
        else
          v6 = 0;
        ItemPtr = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v5, ItemPtr, v6);
      }
      v8 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 133);
      if ( v8 )
      {
        if ( hdsa )
          v9 = *(_DWORD *)hdsa;
        else
          v9 = 0;
        v10 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v8, v10, v9);
      }
      v11 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 134);
      if ( v11 )
      {
        if ( hdsa )
          v12 = *(_DWORD *)hdsa;
        else
          v12 = 0;
        v13 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v11, v13, v12);
      }
      v14 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 135);
      if ( v14 )
      {
        if ( hdsa )
          v15 = *(_DWORD *)hdsa;
        else
          v15 = 0;
        v16 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v14, v16, v15);
      }
      v17 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 136);
      if ( v17 )
      {
        if ( hdsa )
          v18 = *(_DWORD *)hdsa;
        else
          v18 = 0;
        v19 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v17, v19, v18);
      }
      v20 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 137);
      if ( v20 )
      {
        if ( hdsa )
          v21 = *(_DWORD *)hdsa;
        else
          v21 = 0;
        v22 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v20, v22, v21);
      }
      v23 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 138);
      if ( v23 )
      {
        if ( hdsa )
          v24 = *(_DWORD *)hdsa;
        else
          v24 = 0;
        v25 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v23, v25, v24);
      }
      v26 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 139);
      if ( v26 )
      {
        if ( hdsa )
          v27 = *(_DWORD *)hdsa;
        else
          v27 = 0;
        v28 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v26, v28, v27);
      }
      v29 = (CDualEngine13BrowserCoupling *)*((_QWORD *)this + 140);
      if ( v29 )
      {
        if ( hdsa )
          v30 = *(_DWORD *)hdsa;
        else
          v30 = 0;
        v31 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(v29, v31, v30);
      }
      v32 = (CDualEngine14BrowserCoupling *)*((_QWORD *)this + 141);
      if ( v32 )
      {
        if ( hdsa )
          v33 = *(_DWORD *)hdsa;
        else
          v33 = 0;
        v34 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine14BrowserCoupling::OnAllButCurrentEntryDeleted(v32, v34, v33);
      }
      v35 = (CDualEngine19BrowserCoupling *)*((_QWORD *)this + 142);
      if ( v35 )
      {
        if ( hdsa )
          v36 = *(_DWORD *)hdsa;
        else
          v36 = 0;
        v37 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(v35, v37, v36);
      }
      v38 = (CDualEngine19BrowserCoupling *)*((_QWORD *)this + 143);
      if ( v38 )
      {
        if ( hdsa )
          v39 = *(_DWORD *)hdsa;
        else
          v39 = 0;
        v40 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(v38, v40, v39);
      }
      v41 = (CDualEngine19BrowserCoupling *)*((_QWORD *)this + 144);
      if ( v41 )
      {
        if ( hdsa )
          v42 = *(_DWORD *)hdsa;
        else
          v42 = 0;
        v43 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(v41, v43, v42);
      }
      v44 = (CDualEngine19BrowserCoupling *)*((_QWORD *)this + 145);
      if ( v44 )
      {
        if ( hdsa )
          v45 = *(_DWORD *)hdsa;
        else
          v45 = 0;
        v46 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(v44, v46, v45);
      }
      v47 = (CDualEngine19BrowserCoupling *)*((_QWORD *)this + 146);
      if ( v47 )
      {
        if ( hdsa )
          v48 = *(_DWORD *)hdsa;
        else
          v48 = 0;
        v49 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(v47, v49, v48);
      }
      v50 = (CDualEngine19BrowserCoupling *)*((_QWORD *)this + 147);
      if ( v50 )
      {
        if ( hdsa )
          v51 = *(_DWORD *)hdsa;
        else
          v51 = 0;
        v52 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(hdsa, 0);
        CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(v50, v52, v51);
      }
    }
    CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::DestroyCallback(
      &hdsa,
      CBrowserFrame::DualEngineDestroyVisibleListUpdateEntry);
  }
}

```

## disassembly

```asm
0x18022a994  push    rbp
0x18022a996  push    rbx
0x18022a997  push    rsi
0x18022a998  push    rdi
0x18022a999  mov     rbp, rsp
0x18022a99c  sub     rsp, 28h
0x18022a9a0  mov     rdi, rdx
0x18022a9a3  mov     rbx, rcx
0x18022a9a6  mov     dl, 1
0x18022a9a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose> `wil::Feature<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::GetImpl(void)'::`2'::impl
0x18022a9af  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18022a9b4  cmp     qword ptr [rbx+4C8h], 0
0x18022a9bc  jz      loc_18022AD28
0x18022a9c2  mov     dl, 1
0x18022a9c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization> `wil::Feature<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization>::GetImpl(void)'::`2'::impl
0x18022a9cb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18022a9d0  mov     edx, 1
0x18022a9d5  mov     [rbp+hdsa], 0
0x18022a9dd  lea     rcx, [rbp+hdsa]
0x18022a9e1  call    ?Create@?$CDSA_Base@U__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@@@QEAAHH@Z; CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::Create(int)
0x18022a9e6  mov     rcx, [rbx+4C8h]
0x18022a9ed  lea     r8, [rbp+hdsa]
0x18022a9f1  mov     rdx, rdi
0x18022a9f4  mov     rax, [rcx]
0x18022a9f7  mov     rax, [rax+28h]
0x18022a9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022aa00  test    eax, eax
0x18022aa02  js      loc_18022AD18
0x18022aa08  mov     rdi, [rbx+420h]
0x18022aa0f  test    rdi, rdi
0x18022aa12  jz      short loc_18022AA39
0x18022aa14  mov     rcx, [rbp+hdsa]; hdsa
0x18022aa18  test    rcx, rcx
0x18022aa1b  jz      short loc_18022AA21
0x18022aa1d  mov     esi, [rcx]
0x18022aa1f  jmp     short loc_18022AA23
0x18022aa21  xor     esi, esi
0x18022aa23  xor     edx, edx; i
0x18022aa25  call    cs:__imp_DSA_GetItemPtr
0x18022aa2b  mov     r8d, esi; int
0x18022aa2e  mov     rcx, rdi; this
0x18022aa31  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022aa34  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022aa39  mov     rdi, [rbx+428h]
0x18022aa40  test    rdi, rdi
0x18022aa43  jz      short loc_18022AA6A
0x18022aa45  mov     rcx, [rbp+hdsa]; hdsa
0x18022aa49  test    rcx, rcx
0x18022aa4c  jz      short loc_18022AA52
0x18022aa4e  mov     esi, [rcx]
0x18022aa50  jmp     short loc_18022AA54
0x18022aa52  xor     esi, esi
0x18022aa54  xor     edx, edx; i
0x18022aa56  call    cs:__imp_DSA_GetItemPtr
0x18022aa5c  mov     r8d, esi; int
0x18022aa5f  mov     rcx, rdi; this
0x18022aa62  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022aa65  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022aa6a  mov     rdi, [rbx+430h]
0x18022aa71  test    rdi, rdi
0x18022aa74  jz      short loc_18022AA9B
0x18022aa76  mov     rcx, [rbp+hdsa]; hdsa
0x18022aa7a  test    rcx, rcx
0x18022aa7d  jz      short loc_18022AA83
0x18022aa7f  mov     esi, [rcx]
0x18022aa81  jmp     short loc_18022AA85
0x18022aa83  xor     esi, esi
0x18022aa85  xor     edx, edx; i
0x18022aa87  call    cs:__imp_DSA_GetItemPtr
0x18022aa8d  mov     r8d, esi; int
0x18022aa90  mov     rcx, rdi; this
0x18022aa93  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022aa96  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022aa9b  mov     rdi, [rbx+438h]
0x18022aaa2  test    rdi, rdi
0x18022aaa5  jz      short loc_18022AACC
0x18022aaa7  mov     rcx, [rbp+hdsa]; hdsa
0x18022aaab  test    rcx, rcx
0x18022aaae  jz      short loc_18022AAB4
0x18022aab0  mov     esi, [rcx]
0x18022aab2  jmp     short loc_18022AAB6
0x18022aab4  xor     esi, esi
0x18022aab6  xor     edx, edx; i
0x18022aab8  call    cs:__imp_DSA_GetItemPtr
0x18022aabe  mov     r8d, esi; int
0x18022aac1  mov     rcx, rdi; this
0x18022aac4  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022aac7  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022aacc  mov     rdi, [rbx+440h]
0x18022aad3  test    rdi, rdi
0x18022aad6  jz      short loc_18022AAFD
0x18022aad8  mov     rcx, [rbp+hdsa]; hdsa
0x18022aadc  test    rcx, rcx
0x18022aadf  jz      short loc_18022AAE5
0x18022aae1  mov     esi, [rcx]
0x18022aae3  jmp     short loc_18022AAE7
0x18022aae5  xor     esi, esi
0x18022aae7  xor     edx, edx; i
0x18022aae9  call    cs:__imp_DSA_GetItemPtr
0x18022aaef  mov     r8d, esi; int
0x18022aaf2  mov     rcx, rdi; this
0x18022aaf5  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022aaf8  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022aafd  mov     rdi, [rbx+448h]
0x18022ab04  test    rdi, rdi
0x18022ab07  jz      short loc_18022AB2E
0x18022ab09  mov     rcx, [rbp+hdsa]; hdsa
0x18022ab0d  test    rcx, rcx
0x18022ab10  jz      short loc_18022AB16
0x18022ab12  mov     esi, [rcx]
0x18022ab14  jmp     short loc_18022AB18
0x18022ab16  xor     esi, esi
0x18022ab18  xor     edx, edx; i
0x18022ab1a  call    cs:__imp_DSA_GetItemPtr
0x18022ab20  mov     r8d, esi; int
0x18022ab23  mov     rcx, rdi; this
0x18022ab26  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ab29  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ab2e  mov     rdi, [rbx+450h]
0x18022ab35  test    rdi, rdi
0x18022ab38  jz      short loc_18022AB5F
0x18022ab3a  mov     rcx, [rbp+hdsa]; hdsa
0x18022ab3e  test    rcx, rcx
0x18022ab41  jz      short loc_18022AB47
0x18022ab43  mov     esi, [rcx]
0x18022ab45  jmp     short loc_18022AB49
0x18022ab47  xor     esi, esi
0x18022ab49  xor     edx, edx; i
0x18022ab4b  call    cs:__imp_DSA_GetItemPtr
0x18022ab51  mov     r8d, esi; int
0x18022ab54  mov     rcx, rdi; this
0x18022ab57  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ab5a  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ab5f  mov     rdi, [rbx+458h]
0x18022ab66  test    rdi, rdi
0x18022ab69  jz      short loc_18022AB90
0x18022ab6b  mov     rcx, [rbp+hdsa]; hdsa
0x18022ab6f  test    rcx, rcx
0x18022ab72  jz      short loc_18022AB78
0x18022ab74  mov     esi, [rcx]
0x18022ab76  jmp     short loc_18022AB7A
0x18022ab78  xor     esi, esi
0x18022ab7a  xor     edx, edx; i
0x18022ab7c  call    cs:__imp_DSA_GetItemPtr
0x18022ab82  mov     r8d, esi; int
0x18022ab85  mov     rcx, rdi; this
0x18022ab88  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ab8b  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ab90  mov     rdi, [rbx+460h]
0x18022ab97  test    rdi, rdi
0x18022ab9a  jz      short loc_18022ABC1
0x18022ab9c  mov     rcx, [rbp+hdsa]; hdsa
0x18022aba0  test    rcx, rcx
0x18022aba3  jz      short loc_18022ABA9
0x18022aba5  mov     esi, [rcx]
0x18022aba7  jmp     short loc_18022ABAB
0x18022aba9  xor     esi, esi
0x18022abab  xor     edx, edx; i
0x18022abad  call    cs:__imp_DSA_GetItemPtr
0x18022abb3  mov     r8d, esi; int
0x18022abb6  mov     rcx, rdi; this
0x18022abb9  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022abbc  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022abc1  mov     rdi, [rbx+468h]
0x18022abc8  test    rdi, rdi
0x18022abcb  jz      short loc_18022ABF2
0x18022abcd  mov     rcx, [rbp+hdsa]; hdsa
0x18022abd1  test    rcx, rcx
0x18022abd4  jz      short loc_18022ABDA
0x18022abd6  mov     esi, [rcx]
0x18022abd8  jmp     short loc_18022ABDC
0x18022abda  xor     esi, esi
0x18022abdc  xor     edx, edx; i
0x18022abde  call    cs:__imp_DSA_GetItemPtr
0x18022abe4  mov     r8d, esi; int
0x18022abe7  mov     rcx, rdi; this
0x18022abea  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022abed  call    ?OnAllButCurrentEntryDeleted@CDualEngine14BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine14BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022abf2  mov     rdi, [rbx+470h]
0x18022abf9  test    rdi, rdi
0x18022abfc  jz      short loc_18022AC23
0x18022abfe  mov     rcx, [rbp+hdsa]; hdsa
0x18022ac02  test    rcx, rcx
0x18022ac05  jz      short loc_18022AC0B
0x18022ac07  mov     esi, [rcx]
0x18022ac09  jmp     short loc_18022AC0D
0x18022ac0b  xor     esi, esi
0x18022ac0d  xor     edx, edx; i
0x18022ac0f  call    cs:__imp_DSA_GetItemPtr
0x18022ac15  mov     r8d, esi; int
0x18022ac18  mov     rcx, rdi; this
0x18022ac1b  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ac1e  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ac23  mov     rdi, [rbx+478h]
0x18022ac2a  test    rdi, rdi
0x18022ac2d  jz      short loc_18022AC54
0x18022ac2f  mov     rcx, [rbp+hdsa]; hdsa
0x18022ac33  test    rcx, rcx
0x18022ac36  jz      short loc_18022AC3C
0x18022ac38  mov     esi, [rcx]
0x18022ac3a  jmp     short loc_18022AC3E
0x18022ac3c  xor     esi, esi
0x18022ac3e  xor     edx, edx; i
0x18022ac40  call    cs:__imp_DSA_GetItemPtr
0x18022ac46  mov     r8d, esi; int
0x18022ac49  mov     rcx, rdi; this
0x18022ac4c  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ac4f  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ac54  mov     rdi, [rbx+480h]
0x18022ac5b  test    rdi, rdi
0x18022ac5e  jz      short loc_18022AC85
0x18022ac60  mov     rcx, [rbp+hdsa]; hdsa
0x18022ac64  test    rcx, rcx
0x18022ac67  jz      short loc_18022AC6D
0x18022ac69  mov     esi, [rcx]
0x18022ac6b  jmp     short loc_18022AC6F
0x18022ac6d  xor     esi, esi
0x18022ac6f  xor     edx, edx; i
0x18022ac71  call    cs:__imp_DSA_GetItemPtr
0x18022ac77  mov     r8d, esi; int
0x18022ac7a  mov     rcx, rdi; this
0x18022ac7d  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ac80  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ac85  mov     rdi, [rbx+488h]
0x18022ac8c  test    rdi, rdi
0x18022ac8f  jz      short loc_18022ACB6
0x18022ac91  mov     rcx, [rbp+hdsa]; hdsa
0x18022ac95  test    rcx, rcx
0x18022ac98  jz      short loc_18022AC9E
0x18022ac9a  mov     esi, [rcx]
0x18022ac9c  jmp     short loc_18022ACA0
0x18022ac9e  xor     esi, esi
0x18022aca0  xor     edx, edx; i
0x18022aca2  call    cs:__imp_DSA_GetItemPtr
0x18022aca8  mov     r8d, esi; int
0x18022acab  mov     rcx, rdi; this
0x18022acae  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022acb1  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022acb6  mov     rdi, [rbx+490h]
0x18022acbd  test    rdi, rdi
0x18022acc0  jz      short loc_18022ACE7
0x18022acc2  mov     rcx, [rbp+hdsa]; hdsa
0x18022acc6  test    rcx, rcx
0x18022acc9  jz      short loc_18022ACCF
0x18022accb  mov     esi, [rcx]
0x18022accd  jmp     short loc_18022ACD1
0x18022accf  xor     esi, esi
0x18022acd1  xor     edx, edx; i
0x18022acd3  call    cs:__imp_DSA_GetItemPtr
0x18022acd9  mov     r8d, esi; int
0x18022acdc  mov     rcx, rdi; this
0x18022acdf  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ace2  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ace7  mov     rdi, [rbx+498h]
0x18022acee  test    rdi, rdi
0x18022acf1  jz      short loc_18022AD18
0x18022acf3  mov     rcx, [rbp+hdsa]; hdsa
0x18022acf7  test    rcx, rcx
0x18022acfa  jz      short loc_18022AD00
0x18022acfc  mov     ebx, [rcx]
0x18022acfe  jmp     short loc_18022AD02
0x18022ad00  xor     ebx, ebx
0x18022ad02  xor     edx, edx; i
0x18022ad04  call    cs:__imp_DSA_GetItemPtr
0x18022ad0a  mov     r8d, ebx; int
0x18022ad0d  mov     rcx, rdi; this
0x18022ad10  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18022ad13  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18022ad18  lea     rdx, ?DualEngineDestroyVisibleListUpdateEntry@CBrowserFrame@@KAHPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@PEAX@Z; CBrowserFrame::DualEngineDestroyVisibleListUpdateEntry(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,void *)
0x18022ad1f  lea     rcx, [rbp+hdsa]
0x18022ad23  call    ?DestroyCallback@?$CDSA_Base@U__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@@@QEAAXP6AHPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@PEAX@Z1@Z; CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::DestroyCallback(int (*)(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,void *),void *)
0x18022ad28  add     rsp, 28h
0x18022ad2c  pop     rdi
0x18022ad2d  pop     rsi
0x18022ad2e  pop     rbx
0x18022ad2f  pop     rbp
0x18022ad30  retn
```
