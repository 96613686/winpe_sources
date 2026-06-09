# CBrowserFrame::DualEngineAllButCurrentEntryDeleted(IStream *)

- ea: `0x1802473d4`
- end: `0x1802477d2`
- name: `?DualEngineAllButCurrentEntryDeleted@CBrowserFrame@@QEAAXPEAUIStream@@@Z`
- size: `1022`
- prototype: `void __fastcall(CBrowserFrame *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18027cff0`

## callees

- `0x180246ccc`
- `0x180246f60`
- `0x1802473d4`
- `0x18025008c`
- `0x18025011c`
- `0x1803dde08`
- `0x1803e3138`
- `0x1803e4814`
- `0x180594010`

## import_xrefs

- `iertutil!__imp_DSA_GetItemPtr` at `0x180247465`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024749c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802474d3`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024750a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247541`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247578`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802475af`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802475e6`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024761d`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247654`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024768b`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802476c2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802476f9`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247730`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247767`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024779e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247465`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024749c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802474d3`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024750a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247541`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247578`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802475af`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802475e6`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024761d`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247654`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024768b`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802476c2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1802476f9`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247730`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180247767`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18024779e`

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
0x1802473d4  push    rbp
0x1802473d6  push    rbx
0x1802473d7  push    rsi
0x1802473d8  push    rdi
0x1802473d9  mov     rbp, rsp
0x1802473dc  sub     rsp, 28h
0x1802473e0  mov     rdi, rdx
0x1802473e3  mov     rbx, rcx
0x1802473e6  mov     dl, 1
0x1802473e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose> `wil::Feature<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::GetImpl(void)'::`2'::impl
0x1802473ef  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_UninitializeCouplingOnClose>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1802473f4  cmp     qword ptr [rbx+4C8h], 0
0x1802473fc  jz      loc_1802477C8
0x180247402  mov     dl, 1
0x180247404  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization> `wil::Feature<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization>::GetImpl(void)'::`2'::impl
0x18024740b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_AllButCurrentEntryDeletedDeserialization>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180247410  mov     edx, 1
0x180247415  mov     [rbp+hdsa], 0
0x18024741d  lea     rcx, [rbp+hdsa]
0x180247421  call    ?Create@?$CDSA_Base@U__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@@@QEAAHH@Z; CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::Create(int)
0x180247426  mov     rcx, [rbx+4C8h]
0x18024742d  lea     r8, [rbp+hdsa]
0x180247431  mov     rdx, rdi
0x180247434  mov     rax, [rcx]
0x180247437  mov     rax, [rax+28h]
0x18024743b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180247440  test    eax, eax
0x180247442  js      loc_1802477B8
0x180247448  mov     rdi, [rbx+420h]
0x18024744f  test    rdi, rdi
0x180247452  jz      short loc_18024747F
0x180247454  mov     rcx, [rbp+hdsa]; hdsa
0x180247458  test    rcx, rcx
0x18024745b  jz      short loc_180247461
0x18024745d  mov     esi, [rcx]
0x18024745f  jmp     short loc_180247463
0x180247461  xor     esi, esi
0x180247463  xor     edx, edx; i
0x180247465  call    cs:__imp_DSA_GetItemPtr
0x18024746c  nop     dword ptr [rax+rax+00h]
0x180247471  mov     r8d, esi; int
0x180247474  mov     rcx, rdi; this
0x180247477  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024747a  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024747f  mov     rdi, [rbx+428h]
0x180247486  test    rdi, rdi
0x180247489  jz      short loc_1802474B6
0x18024748b  mov     rcx, [rbp+hdsa]; hdsa
0x18024748f  test    rcx, rcx
0x180247492  jz      short loc_180247498
0x180247494  mov     esi, [rcx]
0x180247496  jmp     short loc_18024749A
0x180247498  xor     esi, esi
0x18024749a  xor     edx, edx; i
0x18024749c  call    cs:__imp_DSA_GetItemPtr
0x1802474a3  nop     dword ptr [rax+rax+00h]
0x1802474a8  mov     r8d, esi; int
0x1802474ab  mov     rcx, rdi; this
0x1802474ae  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802474b1  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802474b6  mov     rdi, [rbx+430h]
0x1802474bd  test    rdi, rdi
0x1802474c0  jz      short loc_1802474ED
0x1802474c2  mov     rcx, [rbp+hdsa]; hdsa
0x1802474c6  test    rcx, rcx
0x1802474c9  jz      short loc_1802474CF
0x1802474cb  mov     esi, [rcx]
0x1802474cd  jmp     short loc_1802474D1
0x1802474cf  xor     esi, esi
0x1802474d1  xor     edx, edx; i
0x1802474d3  call    cs:__imp_DSA_GetItemPtr
0x1802474da  nop     dword ptr [rax+rax+00h]
0x1802474df  mov     r8d, esi; int
0x1802474e2  mov     rcx, rdi; this
0x1802474e5  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802474e8  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802474ed  mov     rdi, [rbx+438h]
0x1802474f4  test    rdi, rdi
0x1802474f7  jz      short loc_180247524
0x1802474f9  mov     rcx, [rbp+hdsa]; hdsa
0x1802474fd  test    rcx, rcx
0x180247500  jz      short loc_180247506
0x180247502  mov     esi, [rcx]
0x180247504  jmp     short loc_180247508
0x180247506  xor     esi, esi
0x180247508  xor     edx, edx; i
0x18024750a  call    cs:__imp_DSA_GetItemPtr
0x180247511  nop     dword ptr [rax+rax+00h]
0x180247516  mov     r8d, esi; int
0x180247519  mov     rcx, rdi; this
0x18024751c  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024751f  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180247524  mov     rdi, [rbx+440h]
0x18024752b  test    rdi, rdi
0x18024752e  jz      short loc_18024755B
0x180247530  mov     rcx, [rbp+hdsa]; hdsa
0x180247534  test    rcx, rcx
0x180247537  jz      short loc_18024753D
0x180247539  mov     esi, [rcx]
0x18024753b  jmp     short loc_18024753F
0x18024753d  xor     esi, esi
0x18024753f  xor     edx, edx; i
0x180247541  call    cs:__imp_DSA_GetItemPtr
0x180247548  nop     dword ptr [rax+rax+00h]
0x18024754d  mov     r8d, esi; int
0x180247550  mov     rcx, rdi; this
0x180247553  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180247556  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024755b  mov     rdi, [rbx+448h]
0x180247562  test    rdi, rdi
0x180247565  jz      short loc_180247592
0x180247567  mov     rcx, [rbp+hdsa]; hdsa
0x18024756b  test    rcx, rcx
0x18024756e  jz      short loc_180247574
0x180247570  mov     esi, [rcx]
0x180247572  jmp     short loc_180247576
0x180247574  xor     esi, esi
0x180247576  xor     edx, edx; i
0x180247578  call    cs:__imp_DSA_GetItemPtr
0x18024757f  nop     dword ptr [rax+rax+00h]
0x180247584  mov     r8d, esi; int
0x180247587  mov     rcx, rdi; this
0x18024758a  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024758d  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180247592  mov     rdi, [rbx+450h]
0x180247599  test    rdi, rdi
0x18024759c  jz      short loc_1802475C9
0x18024759e  mov     rcx, [rbp+hdsa]; hdsa
0x1802475a2  test    rcx, rcx
0x1802475a5  jz      short loc_1802475AB
0x1802475a7  mov     esi, [rcx]
0x1802475a9  jmp     short loc_1802475AD
0x1802475ab  xor     esi, esi
0x1802475ad  xor     edx, edx; i
0x1802475af  call    cs:__imp_DSA_GetItemPtr
0x1802475b6  nop     dword ptr [rax+rax+00h]
0x1802475bb  mov     r8d, esi; int
0x1802475be  mov     rcx, rdi; this
0x1802475c1  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802475c4  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802475c9  mov     rdi, [rbx+458h]
0x1802475d0  test    rdi, rdi
0x1802475d3  jz      short loc_180247600
0x1802475d5  mov     rcx, [rbp+hdsa]; hdsa
0x1802475d9  test    rcx, rcx
0x1802475dc  jz      short loc_1802475E2
0x1802475de  mov     esi, [rcx]
0x1802475e0  jmp     short loc_1802475E4
0x1802475e2  xor     esi, esi
0x1802475e4  xor     edx, edx; i
0x1802475e6  call    cs:__imp_DSA_GetItemPtr
0x1802475ed  nop     dword ptr [rax+rax+00h]
0x1802475f2  mov     r8d, esi; int
0x1802475f5  mov     rcx, rdi; this
0x1802475f8  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802475fb  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180247600  mov     rdi, [rbx+460h]
0x180247607  test    rdi, rdi
0x18024760a  jz      short loc_180247637
0x18024760c  mov     rcx, [rbp+hdsa]; hdsa
0x180247610  test    rcx, rcx
0x180247613  jz      short loc_180247619
0x180247615  mov     esi, [rcx]
0x180247617  jmp     short loc_18024761B
0x180247619  xor     esi, esi
0x18024761b  xor     edx, edx; i
0x18024761d  call    cs:__imp_DSA_GetItemPtr
0x180247624  nop     dword ptr [rax+rax+00h]
0x180247629  mov     r8d, esi; int
0x18024762c  mov     rcx, rdi; this
0x18024762f  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180247632  call    ?OnAllButCurrentEntryDeleted@CDualEngine13BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine13BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180247637  mov     rdi, [rbx+468h]
0x18024763e  test    rdi, rdi
0x180247641  jz      short loc_18024766E
0x180247643  mov     rcx, [rbp+hdsa]; hdsa
0x180247647  test    rcx, rcx
0x18024764a  jz      short loc_180247650
0x18024764c  mov     esi, [rcx]
0x18024764e  jmp     short loc_180247652
0x180247650  xor     esi, esi
0x180247652  xor     edx, edx; i
0x180247654  call    cs:__imp_DSA_GetItemPtr
0x18024765b  nop     dword ptr [rax+rax+00h]
0x180247660  mov     r8d, esi; int
0x180247663  mov     rcx, rdi; this
0x180247666  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180247669  call    ?OnAllButCurrentEntryDeleted@CDualEngine14BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine14BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024766e  mov     rdi, [rbx+470h]
0x180247675  test    rdi, rdi
0x180247678  jz      short loc_1802476A5
0x18024767a  mov     rcx, [rbp+hdsa]; hdsa
0x18024767e  test    rcx, rcx
0x180247681  jz      short loc_180247687
0x180247683  mov     esi, [rcx]
0x180247685  jmp     short loc_180247689
0x180247687  xor     esi, esi
0x180247689  xor     edx, edx; i
0x18024768b  call    cs:__imp_DSA_GetItemPtr
0x180247692  nop     dword ptr [rax+rax+00h]
0x180247697  mov     r8d, esi; int
0x18024769a  mov     rcx, rdi; this
0x18024769d  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802476a0  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802476a5  mov     rdi, [rbx+478h]
0x1802476ac  test    rdi, rdi
0x1802476af  jz      short loc_1802476DC
0x1802476b1  mov     rcx, [rbp+hdsa]; hdsa
0x1802476b5  test    rcx, rcx
0x1802476b8  jz      short loc_1802476BE
0x1802476ba  mov     esi, [rcx]
0x1802476bc  jmp     short loc_1802476C0
0x1802476be  xor     esi, esi
0x1802476c0  xor     edx, edx; i
0x1802476c2  call    cs:__imp_DSA_GetItemPtr
0x1802476c9  nop     dword ptr [rax+rax+00h]
0x1802476ce  mov     r8d, esi; int
0x1802476d1  mov     rcx, rdi; this
0x1802476d4  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802476d7  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802476dc  mov     rdi, [rbx+480h]
0x1802476e3  test    rdi, rdi
0x1802476e6  jz      short loc_180247713
0x1802476e8  mov     rcx, [rbp+hdsa]; hdsa
0x1802476ec  test    rcx, rcx
0x1802476ef  jz      short loc_1802476F5
0x1802476f1  mov     esi, [rcx]
0x1802476f3  jmp     short loc_1802476F7
0x1802476f5  xor     esi, esi
0x1802476f7  xor     edx, edx; i
0x1802476f9  call    cs:__imp_DSA_GetItemPtr
0x180247700  nop     dword ptr [rax+rax+00h]
0x180247705  mov     r8d, esi; int
0x180247708  mov     rcx, rdi; this
0x18024770b  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024770e  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180247713  mov     rdi, [rbx+488h]
0x18024771a  test    rdi, rdi
0x18024771d  jz      short loc_18024774A
0x18024771f  mov     rcx, [rbp+hdsa]; hdsa
0x180247723  test    rcx, rcx
0x180247726  jz      short loc_18024772C
0x180247728  mov     esi, [rcx]
0x18024772a  jmp     short loc_18024772E
0x18024772c  xor     esi, esi
0x18024772e  xor     edx, edx; i
0x180247730  call    cs:__imp_DSA_GetItemPtr
0x180247737  nop     dword ptr [rax+rax+00h]
0x18024773c  mov     r8d, esi; int
0x18024773f  mov     rcx, rdi; this
0x180247742  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x180247745  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x18024774a  mov     rdi, [rbx+490h]
0x180247751  test    rdi, rdi
0x180247754  jz      short loc_180247781
0x180247756  mov     rcx, [rbp+hdsa]; hdsa
0x18024775a  test    rcx, rcx
0x18024775d  jz      short loc_180247763
0x18024775f  mov     esi, [rcx]
0x180247761  jmp     short loc_180247765
0x180247763  xor     esi, esi
0x180247765  xor     edx, edx; i
0x180247767  call    cs:__imp_DSA_GetItemPtr
0x18024776e  nop     dword ptr [rax+rax+00h]
0x180247773  mov     r8d, esi; int
0x180247776  mov     rcx, rdi; this
0x180247779  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x18024777c  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x180247781  mov     rdi, [rbx+498h]
0x180247788  test    rdi, rdi
0x18024778b  jz      short loc_1802477B8
0x18024778d  mov     rcx, [rbp+hdsa]; hdsa
0x180247791  test    rcx, rcx
0x180247794  jz      short loc_18024779A
0x180247796  mov     ebx, [rcx]
0x180247798  jmp     short loc_18024779C
0x18024779a  xor     ebx, ebx
0x18024779c  xor     edx, edx; i
0x18024779e  call    cs:__imp_DSA_GetItemPtr
0x1802477a5  nop     dword ptr [rax+rax+00h]
0x1802477aa  mov     r8d, ebx; int
0x1802477ad  mov     rcx, rdi; this
0x1802477b0  mov     rdx, rax; struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *
0x1802477b3  call    ?OnAllButCurrentEntryDeleted@CDualEngine19BrowserCoupling@@QEAAXPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@H@Z; CDualEngine19BrowserCoupling::OnAllButCurrentEntryDeleted(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,int)
0x1802477b8  lea     rdx, ?DualEngineDestroyVisibleListUpdateEntry@CBrowserFrame@@KAHPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@PEAX@Z; CBrowserFrame::DualEngineDestroyVisibleListUpdateEntry(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,void *)
0x1802477bf  lea     rcx, [rbp+hdsa]
0x1802477c3  call    ?DestroyCallback@?$CDSA_Base@U__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@@@QEAAXP6AHPEAU__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009@@PEAX@Z1@Z; CDSA_Base<__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009>::DestroyCallback(int (*)(__MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *,void *),void *)
0x1802477c8  add     rsp, 28h
0x1802477cc  pop     rdi
0x1802477cd  pop     rsi
0x1802477ce  pop     rbx
0x1802477cf  pop     rbp
0x1802477d0  retn
```
