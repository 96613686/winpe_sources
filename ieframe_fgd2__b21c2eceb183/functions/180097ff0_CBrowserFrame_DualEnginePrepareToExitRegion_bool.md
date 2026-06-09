# CBrowserFrame::_DualEnginePrepareToExitRegion(bool)

- ea: `0x180097ff0`
- end: `0x18009872a`
- name: `?_DualEnginePrepareToExitRegion@CBrowserFrame@@IEAAX_N@Z`
- size: `1850`
- prototype: `void __fastcall(CBrowserFrame *__hidden this, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180036918`

## callees

- `0x18000b9e0`
- `0x18009729c`
- `0x180097ff0`
- `0x180098730`
- `0x1802516fc`
- `0x1803b6544`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `iertutil!__imp_DSA_GetItemPtr` at `0x1800980a5`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800980ee`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098138`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098182`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800981cc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098216`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098260`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800982aa`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800982f4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009833e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098388`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800983d2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009841c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098466`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800984b0`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800984fc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800980a5`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800980ee`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098138`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098182`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800981cc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098216`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098260`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800982aa`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800982f4`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009833e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098388`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800983d2`
- `iertutil!__imp_DSA_GetItemPtr` at `0x18009841c`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180098466`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800984b0`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1800984fc`
- `iertutil!__imp_DPA_GetPtr` at `0x18009804d`
- `iertutil!__imp_DPA_GetPtr` at `0x18009804d`

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
0x180097ff0  mov     [rsp-18h+arg_10], rbx
0x180097ff5  mov     [rsp-18h+arg_18], rsi
0x180097ffa  push    rbp
0x180097ffb  push    rdi
0x180097ffc  push    r14
0x180097ffe  mov     rbp, rsp
0x180098001  sub     rsp, 60h
0x180098005  mov     rax, cs:__security_cookie
0x18009800c  xor     rax, rsp
0x18009800f  mov     [rbp+var_10], rax
0x180098013  mov     rdi, rcx
0x180098016  movzx   ebx, dl
0x180098019  xorps   xmm0, xmm0
0x18009801c  mov     [rbp+var_30], 0
0x180098023  lea     rcx, [rbp+var_28]; struct IDualEngineVisibleListOnExit **
0x180098027  mov     [rbp+var_28], 0
0x18009802f  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x180098033  call    ?CreateInstance@CDualEngineVisibleListOnExit@@SAJPEAPEAUIDualEngineVisibleListOnExit@@@Z; CDualEngineVisibleListOnExit::CreateInstance(IDualEngineVisibleListOnExit * *)
0x180098038  mov     rcx, [rdi+118h]
0x18009803f  movsxd  rdx, dword ptr [rcx+80h]; i
0x180098046  mov     rcx, [rcx+148h]; hdpa
0x18009804d  call    cs:__imp_DPA_GetPtr
0x180098053  mov     r8, [rbp+var_28]; struct IUnknown *
0x180098057  lea     rcx, [rbp+var_30]
0x18009805b  mov     [rsp+60h+var_40], rcx; unsigned int *
0x180098060  lea     r9, [rbp+var_20]; struct _GUID *
0x180098064  mov     rcx, rax; this
0x180098067  mov     edx, ebx; int
0x180098069  call    ?DualEnginePrepareToExitRegion@CTabWindow@@QEAAJHPEAUIUnknown@@PEAU_GUID@@PEAK@Z; CTabWindow::DualEnginePrepareToExitRegion(int,IUnknown *,_GUID *,ulong *)
0x18009806e  test    eax, eax
0x180098070  js      loc_18009851E
0x180098076  mov     rcx, [rbp+var_28]
0x18009807a  mov     rax, [rcx]
0x18009807d  mov     rax, [rax+20h]
0x180098081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098086  mov     r14, [rdi+420h]
0x18009808d  mov     rbx, rax
0x180098090  test    r14, r14
0x180098093  jz      short loc_1800980D0
0x180098095  mov     rcx, [rax]; hdsa
0x180098098  test    rcx, rcx
0x18009809b  jz      short loc_1800980A1
0x18009809d  mov     esi, [rcx]
0x18009809f  jmp     short loc_1800980A3
0x1800980a1  xor     esi, esi
0x1800980a3  xor     edx, edx; i
0x1800980a5  call    cs:__imp_DSA_GetItemPtr
0x1800980ab  mov     rcx, [r14+38h]
0x1800980af  mov     r9, rax
0x1800980b2  mov     r8d, [rbp+var_30]
0x1800980b6  mov     dword ptr [rsp+60h+var_40], esi
0x1800980ba  mov     rdx, [rcx]
0x1800980bd  mov     r10, [rdx+0E8h]
0x1800980c4  lea     rdx, [rbp+var_20]
0x1800980c8  mov     rax, r10
0x1800980cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980d0  mov     rsi, [rdi+428h]
0x1800980d7  test    rsi, rsi
0x1800980da  jz      short loc_18009811A
0x1800980dc  mov     rcx, [rbx]; hdsa
0x1800980df  test    rcx, rcx
0x1800980e2  jz      short loc_1800980E9
0x1800980e4  mov     r14d, [rcx]
0x1800980e7  jmp     short loc_1800980EC
0x1800980e9  xor     r14d, r14d
0x1800980ec  xor     edx, edx; i
0x1800980ee  call    cs:__imp_DSA_GetItemPtr
0x1800980f4  mov     rcx, [rsi+38h]
0x1800980f8  mov     r9, rax
0x1800980fb  mov     r8d, [rbp+var_30]
0x1800980ff  mov     dword ptr [rsp+60h+var_40], r14d
0x180098104  mov     rdx, [rcx]
0x180098107  mov     r10, [rdx+0E8h]
0x18009810e  lea     rdx, [rbp+var_20]
0x180098112  mov     rax, r10
0x180098115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009811a  mov     rsi, [rdi+430h]
0x180098121  test    rsi, rsi
0x180098124  jz      short loc_180098164
0x180098126  mov     rcx, [rbx]; hdsa
0x180098129  test    rcx, rcx
0x18009812c  jz      short loc_180098133
0x18009812e  mov     r14d, [rcx]
0x180098131  jmp     short loc_180098136
0x180098133  xor     r14d, r14d
0x180098136  xor     edx, edx; i
0x180098138  call    cs:__imp_DSA_GetItemPtr
0x18009813e  mov     rcx, [rsi+38h]
0x180098142  mov     r9, rax
0x180098145  mov     r8d, [rbp+var_30]
0x180098149  mov     dword ptr [rsp+60h+var_40], r14d
0x18009814e  mov     rdx, [rcx]
0x180098151  mov     r10, [rdx+0E8h]
0x180098158  lea     rdx, [rbp+var_20]
0x18009815c  mov     rax, r10
0x18009815f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098164  mov     rsi, [rdi+438h]
0x18009816b  test    rsi, rsi
0x18009816e  jz      short loc_1800981AE
0x180098170  mov     rcx, [rbx]; hdsa
0x180098173  test    rcx, rcx
0x180098176  jz      short loc_18009817D
0x180098178  mov     r14d, [rcx]
0x18009817b  jmp     short loc_180098180
0x18009817d  xor     r14d, r14d
0x180098180  xor     edx, edx; i
0x180098182  call    cs:__imp_DSA_GetItemPtr
0x180098188  mov     rcx, [rsi+38h]
0x18009818c  mov     r9, rax
0x18009818f  mov     r8d, [rbp+var_30]
0x180098193  mov     dword ptr [rsp+60h+var_40], r14d
0x180098198  mov     rdx, [rcx]
0x18009819b  mov     r10, [rdx+0E8h]
0x1800981a2  lea     rdx, [rbp+var_20]
0x1800981a6  mov     rax, r10
0x1800981a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800981ae  mov     rsi, [rdi+440h]
0x1800981b5  test    rsi, rsi
0x1800981b8  jz      short loc_1800981F8
0x1800981ba  mov     rcx, [rbx]; hdsa
0x1800981bd  test    rcx, rcx
0x1800981c0  jz      short loc_1800981C7
0x1800981c2  mov     r14d, [rcx]
0x1800981c5  jmp     short loc_1800981CA
0x1800981c7  xor     r14d, r14d
0x1800981ca  xor     edx, edx; i
0x1800981cc  call    cs:__imp_DSA_GetItemPtr
0x1800981d2  mov     rcx, [rsi+38h]
0x1800981d6  mov     r9, rax
0x1800981d9  mov     r8d, [rbp+var_30]
0x1800981dd  mov     dword ptr [rsp+60h+var_40], r14d
0x1800981e2  mov     rdx, [rcx]
0x1800981e5  mov     r10, [rdx+0E8h]
0x1800981ec  lea     rdx, [rbp+var_20]
0x1800981f0  mov     rax, r10
0x1800981f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800981f8  mov     rsi, [rdi+448h]
0x1800981ff  test    rsi, rsi
0x180098202  jz      short loc_180098242
0x180098204  mov     rcx, [rbx]; hdsa
0x180098207  test    rcx, rcx
0x18009820a  jz      short loc_180098211
0x18009820c  mov     r14d, [rcx]
0x18009820f  jmp     short loc_180098214
0x180098211  xor     r14d, r14d
0x180098214  xor     edx, edx; i
0x180098216  call    cs:__imp_DSA_GetItemPtr
0x18009821c  mov     rcx, [rsi+38h]
0x180098220  mov     r9, rax
0x180098223  mov     r8d, [rbp+var_30]
0x180098227  mov     dword ptr [rsp+60h+var_40], r14d
0x18009822c  mov     rdx, [rcx]
0x18009822f  mov     r10, [rdx+0E8h]
0x180098236  lea     rdx, [rbp+var_20]
0x18009823a  mov     rax, r10
0x18009823d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098242  mov     rsi, [rdi+450h]
0x180098249  test    rsi, rsi
0x18009824c  jz      short loc_18009828C
0x18009824e  mov     rcx, [rbx]; hdsa
0x180098251  test    rcx, rcx
0x180098254  jz      short loc_18009825B
0x180098256  mov     r14d, [rcx]
0x180098259  jmp     short loc_18009825E
0x18009825b  xor     r14d, r14d
0x18009825e  xor     edx, edx; i
0x180098260  call    cs:__imp_DSA_GetItemPtr
0x180098266  mov     rcx, [rsi+38h]
0x18009826a  mov     r9, rax
0x18009826d  mov     r8d, [rbp+var_30]
0x180098271  mov     dword ptr [rsp+60h+var_40], r14d
0x180098276  mov     rdx, [rcx]
0x180098279  mov     r10, [rdx+0E8h]
0x180098280  lea     rdx, [rbp+var_20]
0x180098284  mov     rax, r10
0x180098287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009828c  mov     rsi, [rdi+458h]
0x180098293  test    rsi, rsi
0x180098296  jz      short loc_1800982D6
0x180098298  mov     rcx, [rbx]; hdsa
0x18009829b  test    rcx, rcx
0x18009829e  jz      short loc_1800982A5
0x1800982a0  mov     r14d, [rcx]
0x1800982a3  jmp     short loc_1800982A8
0x1800982a5  xor     r14d, r14d
0x1800982a8  xor     edx, edx; i
0x1800982aa  call    cs:__imp_DSA_GetItemPtr
0x1800982b0  mov     rcx, [rsi+38h]
0x1800982b4  mov     r9, rax
0x1800982b7  mov     r8d, [rbp+var_30]
0x1800982bb  mov     dword ptr [rsp+60h+var_40], r14d
0x1800982c0  mov     rdx, [rcx]
0x1800982c3  mov     r10, [rdx+0E8h]
0x1800982ca  lea     rdx, [rbp+var_20]
0x1800982ce  mov     rax, r10
0x1800982d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800982d6  mov     rsi, [rdi+460h]
0x1800982dd  test    rsi, rsi
0x1800982e0  jz      short loc_180098320
0x1800982e2  mov     rcx, [rbx]; hdsa
0x1800982e5  test    rcx, rcx
0x1800982e8  jz      short loc_1800982EF
0x1800982ea  mov     r14d, [rcx]
0x1800982ed  jmp     short loc_1800982F2
0x1800982ef  xor     r14d, r14d
0x1800982f2  xor     edx, edx; i
0x1800982f4  call    cs:__imp_DSA_GetItemPtr
0x1800982fa  mov     rcx, [rsi+38h]
0x1800982fe  mov     r9, rax
0x180098301  mov     r8d, [rbp+var_30]
0x180098305  mov     dword ptr [rsp+60h+var_40], r14d
0x18009830a  mov     rdx, [rcx]
0x18009830d  mov     r10, [rdx+0E8h]
0x180098314  lea     rdx, [rbp+var_20]
0x180098318  mov     rax, r10
0x18009831b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098320  mov     rsi, [rdi+468h]
0x180098327  test    rsi, rsi
0x18009832a  jz      short loc_18009836A
0x18009832c  mov     rcx, [rbx]; hdsa
0x18009832f  test    rcx, rcx
0x180098332  jz      short loc_180098339
0x180098334  mov     r14d, [rcx]
0x180098337  jmp     short loc_18009833C
0x180098339  xor     r14d, r14d
0x18009833c  xor     edx, edx; i
0x18009833e  call    cs:__imp_DSA_GetItemPtr
0x180098344  mov     rcx, [rsi+38h]
0x180098348  mov     r9, rax
0x18009834b  mov     r8d, [rbp+var_30]
0x18009834f  mov     dword ptr [rsp+60h+var_40], r14d
0x180098354  mov     rdx, [rcx]
0x180098357  mov     r10, [rdx+0F8h]
0x18009835e  lea     rdx, [rbp+var_20]
0x180098362  mov     rax, r10
0x180098365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009836a  mov     rsi, [rdi+470h]
0x180098371  test    rsi, rsi
0x180098374  jz      short loc_1800983B4
0x180098376  mov     rcx, [rbx]; hdsa
0x180098379  test    rcx, rcx
0x18009837c  jz      short loc_180098383
0x18009837e  mov     r14d, [rcx]
0x180098381  jmp     short loc_180098386
0x180098383  xor     r14d, r14d
0x180098386  xor     edx, edx; i
0x180098388  call    cs:__imp_DSA_GetItemPtr
0x18009838e  mov     rcx, [rsi+58h]
0x180098392  mov     r9, rax
0x180098395  mov     r8d, [rbp+var_30]
0x180098399  mov     dword ptr [rsp+60h+var_40], r14d
0x18009839e  mov     rdx, [rcx]
0x1800983a1  mov     r10, [rdx+0F8h]
0x1800983a8  lea     rdx, [rbp+var_20]
0x1800983ac  mov     rax, r10
0x1800983af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800983b4  mov     rsi, [rdi+478h]
0x1800983bb  test    rsi, rsi
0x1800983be  jz      short loc_1800983FE
0x1800983c0  mov     rcx, [rbx]; hdsa
0x1800983c3  test    rcx, rcx
0x1800983c6  jz      short loc_1800983CD
0x1800983c8  mov     r14d, [rcx]
0x1800983cb  jmp     short loc_1800983D0
0x1800983cd  xor     r14d, r14d
0x1800983d0  xor     edx, edx; i
0x1800983d2  call    cs:__imp_DSA_GetItemPtr
0x1800983d8  mov     rcx, [rsi+58h]
0x1800983dc  mov     r9, rax
0x1800983df  mov     r8d, [rbp+var_30]
0x1800983e3  mov     dword ptr [rsp+60h+var_40], r14d
0x1800983e8  mov     rdx, [rcx]
0x1800983eb  mov     r10, [rdx+0F8h]
0x1800983f2  lea     rdx, [rbp+var_20]
0x1800983f6  mov     rax, r10
0x1800983f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800983fe  mov     rsi, [rdi+480h]
0x180098405  test    rsi, rsi
0x180098408  jz      short loc_180098448
0x18009840a  mov     rcx, [rbx]; hdsa
0x18009840d  test    rcx, rcx
0x180098410  jz      short loc_180098417
0x180098412  mov     r14d, [rcx]
0x180098415  jmp     short loc_18009841A
0x180098417  xor     r14d, r14d
0x18009841a  xor     edx, edx; i
0x18009841c  call    cs:__imp_DSA_GetItemPtr
0x180098422  mov     rcx, [rsi+58h]
0x180098426  mov     r9, rax
0x180098429  mov     r8d, [rbp+var_30]
0x18009842d  mov     dword ptr [rsp+60h+var_40], r14d
0x180098432  mov     rdx, [rcx]
0x180098435  mov     r10, [rdx+0F8h]
0x18009843c  lea     rdx, [rbp+var_20]
0x180098440  mov     rax, r10
0x180098443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098448  mov     rsi, [rdi+488h]
0x18009844f  test    rsi, rsi
0x180098452  jz      short loc_180098492
0x180098454  mov     rcx, [rbx]; hdsa
  ... truncated ...
```
