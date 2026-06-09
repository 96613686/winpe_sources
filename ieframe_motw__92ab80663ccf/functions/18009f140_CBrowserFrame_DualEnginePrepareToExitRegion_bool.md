# CBrowserFrame::_DualEnginePrepareToExitRegion(bool)

- ea: `0x18009f140`
- end: `0x18009f8e1`
- name: `?_DualEnginePrepareToExitRegion@CBrowserFrame@@IEAAX_N@Z`
- size: `1953`
- prototype: `void __fastcall(CBrowserFrame *__hidden this, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180032700`

## callees

- `0x180005030`
- `0x18009e3cc`
- `0x18009f140`
- `0x18009f8e8`
- `0x180270718`
- `0x1803e8c44`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f1fb`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f24a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f29a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f2ea`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f33a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f38a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f3da`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f42a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f47a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f4ca`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f51a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f56a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f5ba`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f60a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f65a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f6ac`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f1fb`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f24a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f29a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f2ea`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f33a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f38a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f3da`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f42a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f47a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f4ca`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f51a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f56a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f5ba`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f60a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f65a`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009f6ac`
- `iertutil!__imp_DPA_GetPtr` at `0x18009f19d`
- `iertutil!__imp_DPA_GetPtr` at `0x18009f19d`

## pseudocode

```c
void __fastcall CBrowserFrame::_DualEnginePrepareToExitRegion(CBrowserFrame *this, unsigned __int8 a2)
{
  int v3; // ebx
  CTabWindow *Ptr; // rax
  struct _DSA **v5; // rax
  __int64 v6; // r14
  struct _DSA **v7; // rbx
  struct _DSA *v8; // rcx
  int v9; // esi
  PVOID ItemPtr; // rax
  __int64 v11; // rsi
  struct _DSA *v12; // rcx
  int v13; // r14d
  PVOID v14; // rax
  __int64 v15; // rsi
  struct _DSA *v16; // rcx
  int v17; // r14d
  PVOID v18; // rax
  __int64 v19; // rsi
  struct _DSA *v20; // rcx
  int v21; // r14d
  PVOID v22; // rax
  __int64 v23; // rsi
  struct _DSA *v24; // rcx
  int v25; // r14d
  PVOID v26; // rax
  __int64 v27; // rsi
  struct _DSA *v28; // rcx
  int v29; // r14d
  PVOID v30; // rax
  __int64 v31; // rsi
  struct _DSA *v32; // rcx
  int v33; // r14d
  PVOID v34; // rax
  __int64 v35; // rsi
  struct _DSA *v36; // rcx
  int v37; // r14d
  PVOID v38; // rax
  __int64 v39; // rsi
  struct _DSA *v40; // rcx
  int v41; // r14d
  PVOID v42; // rax
  __int64 v43; // rsi
  struct _DSA *v44; // rcx
  int v45; // r14d
  PVOID v46; // rax
  __int64 v47; // rsi
  struct _DSA *v48; // rcx
  int v49; // r14d
  PVOID v50; // rax
  __int64 v51; // rsi
  struct _DSA *v52; // rcx
  int v53; // r14d
  PVOID v54; // rax
  __int64 v55; // rsi
  struct _DSA *v56; // rcx
  int v57; // r14d
  PVOID v58; // rax
  __int64 v59; // rsi
  struct _DSA *v60; // rcx
  int v61; // r14d
  PVOID v62; // rax
  __int64 v63; // rsi
  struct _DSA *v64; // rcx
  int v65; // r14d
  PVOID v66; // rax
  CDualEngine20BrowserCoupling *v67; // rdi
  struct _DSA *v68; // rcx
  int v69; // ebx
  struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  CDualEngine20BrowserCoupling *v86; // rcx
  unsigned int v87; // [rsp+30h] [rbp-30h] BYREF
  struct IUnknown *v88; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v89; // [rsp+40h] [rbp-20h] BYREF

  v3 = a2;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  CDualEngineVisibleListOnExit::CreateInstance((struct IDualEngineVisibleListOnExit **)&v88);
  Ptr = (CTabWindow *)DPA_GetPtr(*(HDPA *)(*((_QWORD *)this + 35) + 328LL), *(int *)(*((_QWORD *)this + 35) + 128LL));
  if ( (int)CTabWindow::DualEnginePrepareToExitRegion(Ptr, v3, v88, &v89, &v87) < 0 )
  {
    v71 = *((_QWORD *)this + 132);
    if ( v71 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v71 + 56) + 240LL))(*(_QWORD *)(v71 + 56));
    v72 = *((_QWORD *)this + 133);
    if ( v72 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v72 + 56) + 240LL))(*(_QWORD *)(v72 + 56));
    v73 = *((_QWORD *)this + 134);
    if ( v73 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v73 + 56) + 240LL))(*(_QWORD *)(v73 + 56));
    v74 = *((_QWORD *)this + 135);
    if ( v74 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v74 + 56) + 240LL))(*(_QWORD *)(v74 + 56));
    v75 = *((_QWORD *)this + 136);
    if ( v75 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v75 + 56) + 240LL))(*(_QWORD *)(v75 + 56));
    v76 = *((_QWORD *)this + 137);
    if ( v76 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v76 + 56) + 240LL))(*(_QWORD *)(v76 + 56));
    v77 = *((_QWORD *)this + 138);
    if ( v77 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v77 + 56) + 240LL))(*(_QWORD *)(v77 + 56));
    v78 = *((_QWORD *)this + 139);
    if ( v78 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v78 + 56) + 240LL))(*(_QWORD *)(v78 + 56));
    v79 = *((_QWORD *)this + 140);
    if ( v79 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v79 + 56) + 240LL))(*(_QWORD *)(v79 + 56));
    v80 = *((_QWORD *)this + 141);
    if ( v80 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v80 + 56) + 256LL))(*(_QWORD *)(v80 + 56));
    v81 = *((_QWORD *)this + 142);
    if ( v81 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v81 + 88) + 256LL))(*(_QWORD *)(v81 + 88));
    v82 = *((_QWORD *)this + 143);
    if ( v82 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v82 + 88) + 256LL))(*(_QWORD *)(v82 + 88));
    v83 = *((_QWORD *)this + 144);
    if ( v83 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v83 + 88) + 256LL))(*(_QWORD *)(v83 + 88));
    v84 = *((_QWORD *)this + 145);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v84 + 88) + 256LL))(*(_QWORD *)(v84 + 88));
    v85 = *((_QWORD *)this + 146);
    if ( v85 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v85 + 88) + 256LL))(*(_QWORD *)(v85 + 88));
    v86 = (CDualEngine20BrowserCoupling *)*((_QWORD *)this + 147);
    if ( v86 )
      CDualEngine20BrowserCoupling::OnPrepareToExitRegionFailed(v86);
  }
  else
  {
    v5 = (struct _DSA **)((__int64 (__fastcall *)(struct IUnknown *))v88->lpVtbl[1].AddRef)(v88);
    v6 = *((_QWORD *)this + 132);
    v7 = v5;
    if ( v6 )
    {
      v8 = *v5;
      if ( *v5 )
        v9 = *(_DWORD *)v8;
      else
        v9 = 0;
      ItemPtr = DSA_GetItemPtr(v8, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v6 + 56) + 232LL))(
        *(_QWORD *)(v6 + 56),
        &v89,
        v87,
        ItemPtr,
        v9);
    }
    v11 = *((_QWORD *)this + 133);
    if ( v11 )
    {
      v12 = *v7;
      if ( *v7 )
        v13 = *(_DWORD *)v12;
      else
        v13 = 0;
      v14 = DSA_GetItemPtr(v12, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v11 + 56) + 232LL))(
        *(_QWORD *)(v11 + 56),
        &v89,
        v87,
        v14,
        v13);
    }
    v15 = *((_QWORD *)this + 134);
    if ( v15 )
    {
      v16 = *v7;
      if ( *v7 )
        v17 = *(_DWORD *)v16;
      else
        v17 = 0;
      v18 = DSA_GetItemPtr(v16, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v15 + 56) + 232LL))(
        *(_QWORD *)(v15 + 56),
        &v89,
        v87,
        v18,
        v17);
    }
    v19 = *((_QWORD *)this + 135);
    if ( v19 )
    {
      v20 = *v7;
      if ( *v7 )
        v21 = *(_DWORD *)v20;
      else
        v21 = 0;
      v22 = DSA_GetItemPtr(v20, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v19 + 56) + 232LL))(
        *(_QWORD *)(v19 + 56),
        &v89,
        v87,
        v22,
        v21);
    }
    v23 = *((_QWORD *)this + 136);
    if ( v23 )
    {
      v24 = *v7;
      if ( *v7 )
        v25 = *(_DWORD *)v24;
      else
        v25 = 0;
      v26 = DSA_GetItemPtr(v24, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v23 + 56) + 232LL))(
        *(_QWORD *)(v23 + 56),
        &v89,
        v87,
        v26,
        v25);
    }
    v27 = *((_QWORD *)this + 137);
    if ( v27 )
    {
      v28 = *v7;
      if ( *v7 )
        v29 = *(_DWORD *)v28;
      else
        v29 = 0;
      v30 = DSA_GetItemPtr(v28, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v27 + 56) + 232LL))(
        *(_QWORD *)(v27 + 56),
        &v89,
        v87,
        v30,
        v29);
    }
    v31 = *((_QWORD *)this + 138);
    if ( v31 )
    {
      v32 = *v7;
      if ( *v7 )
        v33 = *(_DWORD *)v32;
      else
        v33 = 0;
      v34 = DSA_GetItemPtr(v32, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v31 + 56) + 232LL))(
        *(_QWORD *)(v31 + 56),
        &v89,
        v87,
        v34,
        v33);
    }
    v35 = *((_QWORD *)this + 139);
    if ( v35 )
    {
      v36 = *v7;
      if ( *v7 )
        v37 = *(_DWORD *)v36;
      else
        v37 = 0;
      v38 = DSA_GetItemPtr(v36, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v35 + 56) + 232LL))(
        *(_QWORD *)(v35 + 56),
        &v89,
        v87,
        v38,
        v37);
    }
    v39 = *((_QWORD *)this + 140);
    if ( v39 )
    {
      v40 = *v7;
      if ( *v7 )
        v41 = *(_DWORD *)v40;
      else
        v41 = 0;
      v42 = DSA_GetItemPtr(v40, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v39 + 56) + 232LL))(
        *(_QWORD *)(v39 + 56),
        &v89,
        v87,
        v42,
        v41);
    }
    v43 = *((_QWORD *)this + 141);
    if ( v43 )
    {
      v44 = *v7;
      if ( *v7 )
        v45 = *(_DWORD *)v44;
      else
        v45 = 0;
      v46 = DSA_GetItemPtr(v44, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v43 + 56) + 248LL))(
        *(_QWORD *)(v43 + 56),
        &v89,
        v87,
        v46,
        v45);
    }
    v47 = *((_QWORD *)this + 142);
    if ( v47 )
    {
      v48 = *v7;
      if ( *v7 )
        v49 = *(_DWORD *)v48;
      else
        v49 = 0;
      v50 = DSA_GetItemPtr(v48, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v47 + 88) + 248LL))(
        *(_QWORD *)(v47 + 88),
        &v89,
        v87,
        v50,
        v49);
    }
    v51 = *((_QWORD *)this + 143);
    if ( v51 )
    {
      v52 = *v7;
      if ( *v7 )
        v53 = *(_DWORD *)v52;
      else
        v53 = 0;
      v54 = DSA_GetItemPtr(v52, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v51 + 88) + 248LL))(
        *(_QWORD *)(v51 + 88),
        &v89,
        v87,
        v54,
        v53);
    }
    v55 = *((_QWORD *)this + 144);
    if ( v55 )
    {
      v56 = *v7;
      if ( *v7 )
        v57 = *(_DWORD *)v56;
      else
        v57 = 0;
      v58 = DSA_GetItemPtr(v56, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v55 + 88) + 248LL))(
        *(_QWORD *)(v55 + 88),
        &v89,
        v87,
        v58,
        v57);
    }
    v59 = *((_QWORD *)this + 145);
    if ( v59 )
    {
      v60 = *v7;
      if ( *v7 )
        v61 = *(_DWORD *)v60;
      else
        v61 = 0;
      v62 = DSA_GetItemPtr(v60, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v59 + 88) + 248LL))(
        *(_QWORD *)(v59 + 88),
        &v89,
        v87,
        v62,
        v61);
    }
    v63 = *((_QWORD *)this + 146);
    if ( v63 )
    {
      v64 = *v7;
      if ( *v7 )
        v65 = *(_DWORD *)v64;
      else
        v65 = 0;
      v66 = DSA_GetItemPtr(v64, 0);
      (*(void (__fastcall **)(_QWORD, struct _GUID *, _QWORD, PVOID, int))(**(_QWORD **)(v63 + 88) + 248LL))(
        *(_QWORD *)(v63 + 88),
        &v89,
        v87,
        v66,
        v65);
    }
    v67 = (CDualEngine20BrowserCoupling *)*((_QWORD *)this + 147);
    if ( v67 )
    {
      v68 = *v7;
      if ( *v7 )
        v69 = *(_DWORD *)v68;
      else
        v69 = 0;
      v70 = (struct __MIDL___MIDL_itf_dualengine2Dcommon_0000_0000_0009 *)DSA_GetItemPtr(v68, 0);
      CDualEngine20BrowserCoupling::OnReadyToExitRegion(v67, &v89, v87, v70, v69);
    }
  }
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v88);
}

```

## disassembly

```asm
0x18009f140  mov     [rsp-18h+arg_10], rbx
0x18009f145  mov     [rsp-18h+arg_18], rsi
0x18009f14a  push    rbp
0x18009f14b  push    rdi
0x18009f14c  push    r14
0x18009f14e  mov     rbp, rsp
0x18009f151  sub     rsp, 60h
0x18009f155  mov     rax, cs:__security_cookie
0x18009f15c  xor     rax, rsp
0x18009f15f  mov     [rbp+var_10], rax
0x18009f163  mov     rdi, rcx
0x18009f166  movzx   ebx, dl
0x18009f169  xorps   xmm0, xmm0
0x18009f16c  mov     [rbp+var_30], 0
0x18009f173  lea     rcx, [rbp+var_28]; struct IDualEngineVisibleListOnExit **
0x18009f177  mov     [rbp+var_28], 0
0x18009f17f  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x18009f183  call    ?CreateInstance@CDualEngineVisibleListOnExit@@SAJPEAPEAUIDualEngineVisibleListOnExit@@@Z; CDualEngineVisibleListOnExit::CreateInstance(IDualEngineVisibleListOnExit * *)
0x18009f188  mov     rcx, [rdi+118h]
0x18009f18f  movsxd  rdx, dword ptr [rcx+80h]; i
0x18009f196  mov     rcx, [rcx+148h]; hdpa
0x18009f19d  call    cs:__imp_DPA_GetPtr
0x18009f1a4  nop     dword ptr [rax+rax+00h]
0x18009f1a9  mov     r8, [rbp+var_28]; struct IUnknown *
0x18009f1ad  lea     rcx, [rbp+var_30]
0x18009f1b1  mov     [rsp+60h+var_40], rcx; unsigned int *
0x18009f1b6  lea     r9, [rbp+var_20]; struct _GUID *
0x18009f1ba  mov     rcx, rax; this
0x18009f1bd  mov     edx, ebx; int
0x18009f1bf  call    ?DualEnginePrepareToExitRegion@CTabWindow@@QEAAJHPEAUIUnknown@@PEAU_GUID@@PEAK@Z; CTabWindow::DualEnginePrepareToExitRegion(int,IUnknown *,_GUID *,ulong *)
0x18009f1c4  test    eax, eax
0x18009f1c6  js      loc_18009F6D4
0x18009f1cc  mov     rcx, [rbp+var_28]
0x18009f1d0  mov     rax, [rcx]
0x18009f1d3  mov     rax, [rax+20h]
0x18009f1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f1dc  mov     r14, [rdi+420h]
0x18009f1e3  mov     rbx, rax
0x18009f1e6  test    r14, r14
0x18009f1e9  jz      short loc_18009F22C
0x18009f1eb  mov     rcx, [rax]; hdsa
0x18009f1ee  test    rcx, rcx
0x18009f1f1  jz      short loc_18009F1F7
0x18009f1f3  mov     esi, [rcx]
0x18009f1f5  jmp     short loc_18009F1F9
0x18009f1f7  xor     esi, esi
0x18009f1f9  xor     edx, edx; i
0x18009f1fb  call    cs:__imp_DSA_GetItemPtr
0x18009f202  nop     dword ptr [rax+rax+00h]
0x18009f207  mov     rcx, [r14+38h]
0x18009f20b  mov     r9, rax
0x18009f20e  mov     r8d, [rbp+var_30]
0x18009f212  mov     dword ptr [rsp+60h+var_40], esi
0x18009f216  mov     rdx, [rcx]
0x18009f219  mov     r10, [rdx+0E8h]
0x18009f220  lea     rdx, [rbp+var_20]
0x18009f224  mov     rax, r10
0x18009f227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f22c  mov     rsi, [rdi+428h]
0x18009f233  test    rsi, rsi
0x18009f236  jz      short loc_18009F27C
0x18009f238  mov     rcx, [rbx]; hdsa
0x18009f23b  test    rcx, rcx
0x18009f23e  jz      short loc_18009F245
0x18009f240  mov     r14d, [rcx]
0x18009f243  jmp     short loc_18009F248
0x18009f245  xor     r14d, r14d
0x18009f248  xor     edx, edx; i
0x18009f24a  call    cs:__imp_DSA_GetItemPtr
0x18009f251  nop     dword ptr [rax+rax+00h]
0x18009f256  mov     rcx, [rsi+38h]
0x18009f25a  mov     r9, rax
0x18009f25d  mov     r8d, [rbp+var_30]
0x18009f261  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f266  mov     rdx, [rcx]
0x18009f269  mov     r10, [rdx+0E8h]
0x18009f270  lea     rdx, [rbp+var_20]
0x18009f274  mov     rax, r10
0x18009f277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f27c  mov     rsi, [rdi+430h]
0x18009f283  test    rsi, rsi
0x18009f286  jz      short loc_18009F2CC
0x18009f288  mov     rcx, [rbx]; hdsa
0x18009f28b  test    rcx, rcx
0x18009f28e  jz      short loc_18009F295
0x18009f290  mov     r14d, [rcx]
0x18009f293  jmp     short loc_18009F298
0x18009f295  xor     r14d, r14d
0x18009f298  xor     edx, edx; i
0x18009f29a  call    cs:__imp_DSA_GetItemPtr
0x18009f2a1  nop     dword ptr [rax+rax+00h]
0x18009f2a6  mov     rcx, [rsi+38h]
0x18009f2aa  mov     r9, rax
0x18009f2ad  mov     r8d, [rbp+var_30]
0x18009f2b1  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f2b6  mov     rdx, [rcx]
0x18009f2b9  mov     r10, [rdx+0E8h]
0x18009f2c0  lea     rdx, [rbp+var_20]
0x18009f2c4  mov     rax, r10
0x18009f2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f2cc  mov     rsi, [rdi+438h]
0x18009f2d3  test    rsi, rsi
0x18009f2d6  jz      short loc_18009F31C
0x18009f2d8  mov     rcx, [rbx]; hdsa
0x18009f2db  test    rcx, rcx
0x18009f2de  jz      short loc_18009F2E5
0x18009f2e0  mov     r14d, [rcx]
0x18009f2e3  jmp     short loc_18009F2E8
0x18009f2e5  xor     r14d, r14d
0x18009f2e8  xor     edx, edx; i
0x18009f2ea  call    cs:__imp_DSA_GetItemPtr
0x18009f2f1  nop     dword ptr [rax+rax+00h]
0x18009f2f6  mov     rcx, [rsi+38h]
0x18009f2fa  mov     r9, rax
0x18009f2fd  mov     r8d, [rbp+var_30]
0x18009f301  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f306  mov     rdx, [rcx]
0x18009f309  mov     r10, [rdx+0E8h]
0x18009f310  lea     rdx, [rbp+var_20]
0x18009f314  mov     rax, r10
0x18009f317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f31c  mov     rsi, [rdi+440h]
0x18009f323  test    rsi, rsi
0x18009f326  jz      short loc_18009F36C
0x18009f328  mov     rcx, [rbx]; hdsa
0x18009f32b  test    rcx, rcx
0x18009f32e  jz      short loc_18009F335
0x18009f330  mov     r14d, [rcx]
0x18009f333  jmp     short loc_18009F338
0x18009f335  xor     r14d, r14d
0x18009f338  xor     edx, edx; i
0x18009f33a  call    cs:__imp_DSA_GetItemPtr
0x18009f341  nop     dword ptr [rax+rax+00h]
0x18009f346  mov     rcx, [rsi+38h]
0x18009f34a  mov     r9, rax
0x18009f34d  mov     r8d, [rbp+var_30]
0x18009f351  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f356  mov     rdx, [rcx]
0x18009f359  mov     r10, [rdx+0E8h]
0x18009f360  lea     rdx, [rbp+var_20]
0x18009f364  mov     rax, r10
0x18009f367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f36c  mov     rsi, [rdi+448h]
0x18009f373  test    rsi, rsi
0x18009f376  jz      short loc_18009F3BC
0x18009f378  mov     rcx, [rbx]; hdsa
0x18009f37b  test    rcx, rcx
0x18009f37e  jz      short loc_18009F385
0x18009f380  mov     r14d, [rcx]
0x18009f383  jmp     short loc_18009F388
0x18009f385  xor     r14d, r14d
0x18009f388  xor     edx, edx; i
0x18009f38a  call    cs:__imp_DSA_GetItemPtr
0x18009f391  nop     dword ptr [rax+rax+00h]
0x18009f396  mov     rcx, [rsi+38h]
0x18009f39a  mov     r9, rax
0x18009f39d  mov     r8d, [rbp+var_30]
0x18009f3a1  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f3a6  mov     rdx, [rcx]
0x18009f3a9  mov     r10, [rdx+0E8h]
0x18009f3b0  lea     rdx, [rbp+var_20]
0x18009f3b4  mov     rax, r10
0x18009f3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f3bc  mov     rsi, [rdi+450h]
0x18009f3c3  test    rsi, rsi
0x18009f3c6  jz      short loc_18009F40C
0x18009f3c8  mov     rcx, [rbx]; hdsa
0x18009f3cb  test    rcx, rcx
0x18009f3ce  jz      short loc_18009F3D5
0x18009f3d0  mov     r14d, [rcx]
0x18009f3d3  jmp     short loc_18009F3D8
0x18009f3d5  xor     r14d, r14d
0x18009f3d8  xor     edx, edx; i
0x18009f3da  call    cs:__imp_DSA_GetItemPtr
0x18009f3e1  nop     dword ptr [rax+rax+00h]
0x18009f3e6  mov     rcx, [rsi+38h]
0x18009f3ea  mov     r9, rax
0x18009f3ed  mov     r8d, [rbp+var_30]
0x18009f3f1  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f3f6  mov     rdx, [rcx]
0x18009f3f9  mov     r10, [rdx+0E8h]
0x18009f400  lea     rdx, [rbp+var_20]
0x18009f404  mov     rax, r10
0x18009f407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f40c  mov     rsi, [rdi+458h]
0x18009f413  test    rsi, rsi
0x18009f416  jz      short loc_18009F45C
0x18009f418  mov     rcx, [rbx]; hdsa
0x18009f41b  test    rcx, rcx
0x18009f41e  jz      short loc_18009F425
0x18009f420  mov     r14d, [rcx]
0x18009f423  jmp     short loc_18009F428
0x18009f425  xor     r14d, r14d
0x18009f428  xor     edx, edx; i
0x18009f42a  call    cs:__imp_DSA_GetItemPtr
0x18009f431  nop     dword ptr [rax+rax+00h]
0x18009f436  mov     rcx, [rsi+38h]
0x18009f43a  mov     r9, rax
0x18009f43d  mov     r8d, [rbp+var_30]
0x18009f441  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f446  mov     rdx, [rcx]
0x18009f449  mov     r10, [rdx+0E8h]
0x18009f450  lea     rdx, [rbp+var_20]
0x18009f454  mov     rax, r10
0x18009f457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f45c  mov     rsi, [rdi+460h]
0x18009f463  test    rsi, rsi
0x18009f466  jz      short loc_18009F4AC
0x18009f468  mov     rcx, [rbx]; hdsa
0x18009f46b  test    rcx, rcx
0x18009f46e  jz      short loc_18009F475
0x18009f470  mov     r14d, [rcx]
0x18009f473  jmp     short loc_18009F478
0x18009f475  xor     r14d, r14d
0x18009f478  xor     edx, edx; i
0x18009f47a  call    cs:__imp_DSA_GetItemPtr
0x18009f481  nop     dword ptr [rax+rax+00h]
0x18009f486  mov     rcx, [rsi+38h]
0x18009f48a  mov     r9, rax
0x18009f48d  mov     r8d, [rbp+var_30]
0x18009f491  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f496  mov     rdx, [rcx]
0x18009f499  mov     r10, [rdx+0E8h]
0x18009f4a0  lea     rdx, [rbp+var_20]
0x18009f4a4  mov     rax, r10
0x18009f4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f4ac  mov     rsi, [rdi+468h]
0x18009f4b3  test    rsi, rsi
0x18009f4b6  jz      short loc_18009F4FC
0x18009f4b8  mov     rcx, [rbx]; hdsa
0x18009f4bb  test    rcx, rcx
0x18009f4be  jz      short loc_18009F4C5
0x18009f4c0  mov     r14d, [rcx]
0x18009f4c3  jmp     short loc_18009F4C8
0x18009f4c5  xor     r14d, r14d
0x18009f4c8  xor     edx, edx; i
0x18009f4ca  call    cs:__imp_DSA_GetItemPtr
0x18009f4d1  nop     dword ptr [rax+rax+00h]
0x18009f4d6  mov     rcx, [rsi+38h]
0x18009f4da  mov     r9, rax
0x18009f4dd  mov     r8d, [rbp+var_30]
0x18009f4e1  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f4e6  mov     rdx, [rcx]
0x18009f4e9  mov     r10, [rdx+0F8h]
0x18009f4f0  lea     rdx, [rbp+var_20]
0x18009f4f4  mov     rax, r10
0x18009f4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f4fc  mov     rsi, [rdi+470h]
0x18009f503  test    rsi, rsi
0x18009f506  jz      short loc_18009F54C
0x18009f508  mov     rcx, [rbx]; hdsa
0x18009f50b  test    rcx, rcx
0x18009f50e  jz      short loc_18009F515
0x18009f510  mov     r14d, [rcx]
0x18009f513  jmp     short loc_18009F518
0x18009f515  xor     r14d, r14d
0x18009f518  xor     edx, edx; i
0x18009f51a  call    cs:__imp_DSA_GetItemPtr
0x18009f521  nop     dword ptr [rax+rax+00h]
0x18009f526  mov     rcx, [rsi+58h]
0x18009f52a  mov     r9, rax
0x18009f52d  mov     r8d, [rbp+var_30]
0x18009f531  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f536  mov     rdx, [rcx]
0x18009f539  mov     r10, [rdx+0F8h]
0x18009f540  lea     rdx, [rbp+var_20]
0x18009f544  mov     rax, r10
0x18009f547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f54c  mov     rsi, [rdi+478h]
0x18009f553  test    rsi, rsi
0x18009f556  jz      short loc_18009F59C
0x18009f558  mov     rcx, [rbx]; hdsa
0x18009f55b  test    rcx, rcx
0x18009f55e  jz      short loc_18009F565
0x18009f560  mov     r14d, [rcx]
0x18009f563  jmp     short loc_18009F568
0x18009f565  xor     r14d, r14d
0x18009f568  xor     edx, edx; i
0x18009f56a  call    cs:__imp_DSA_GetItemPtr
0x18009f571  nop     dword ptr [rax+rax+00h]
0x18009f576  mov     rcx, [rsi+58h]
0x18009f57a  mov     r9, rax
0x18009f57d  mov     r8d, [rbp+var_30]
0x18009f581  mov     dword ptr [rsp+60h+var_40], r14d
0x18009f586  mov     rdx, [rcx]
0x18009f589  mov     r10, [rdx+0F8h]
0x18009f590  lea     rdx, [rbp+var_20]
0x18009f594  mov     rax, r10
0x18009f597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f59c  mov     rsi, [rdi+480h]
0x18009f5a3  test    rsi, rsi
0x18009f5a6  jz      short loc_18009F5EC
0x18009f5a8  mov     rcx, [rbx]; hdsa
0x18009f5ab  test    rcx, rcx
0x18009f5ae  jz      short loc_18009F5B5
0x18009f5b0  mov     r14d, [rcx]
0x18009f5b3  jmp     short loc_18009F5B8
0x18009f5b5  xor     r14d, r14d
0x18009f5b8  xor     edx, edx; i
0x18009f5ba  call    cs:__imp_DSA_GetItemPtr
  ... truncated ...
```
