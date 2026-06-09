# dxc::CConversionSinkImpl::UpdateSiblingClip(win_scope::scope<IXpsOMVisual *,win_scope::const_policies<win_scope::com_policies>> const &,win_scope::scope<ID2D1Geometry *,win_scope::const_policies<win_scope::com_policies>> const &)

- ea: `0x1801f7444`
- end: `0x1801f79fb`
- name: `?UpdateSiblingClip@CConversionSinkImpl@dxc@@AEAAXAEBV?$scope@PEAUIXpsOMVisual@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV?$scope@PEAUID2D1Geometry@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@4@@Z`
- size: `1463`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f5fe0`
- `0x1801f7444`

## callees

- `0x1800152a0`
- `0x1800172a0`
- `0x1800f7c54`
- `0x1801b4640`
- `0x1801e940c`
- `0x1801edd7c`
- `0x1801f6554`
- `0x1801f7444`
- `0x180214888`
- `0x18023fbfc`
- `0x18028d710`
- `0x1802a6afc`
- `0x1802a82d4`
- `0x1802f5370`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f794d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f794d`

## string_xrefs

- `0x1801f7939`: `AACLIP`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall dxc::CConversionSinkImpl::UpdateSiblingClip(__int64 a1, _QWORD *a2, struct ID2D1Geometry **a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64); // rbx
  __int64 v8; // rax
  int v9; // eax
  int v10; // edx
  const char *v11; // r8
  int v12; // r9d
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  unsigned int v15; // eax
  const char *v16; // r8
  int v17; // r9d
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64 *); // rdi
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  int v24; // eax
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  unsigned int i; // esi
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rbx
  int v31; // eax
  int v32; // edx
  const char *v33; // r8
  int v34; // r9d
  ID2D1Geometry *v35; // rcx
  bool v36; // bl
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64 *); // rbx
  int v39; // eax
  int v40; // edx
  const char *v41; // r8
  int v42; // r9d
  _QWORD *v43; // rax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, ID2D1Geometry **); // rbx
  int v46; // eax
  int v47; // edx
  const char *v48; // r8
  int v49; // r9d
  ID2D1Geometry *v50; // rbx
  __int64 (__fastcall *v51)(ID2D1Geometry *, struct ID2D1SimplifiedGeometrySink **); // rdi
  int v52; // eax
  int v53; // edx
  const char *v54; // r8
  int v55; // r9d
  ID2D1Geometry *v56; // rdi
  int v57; // eax
  int v58; // edx
  const char *v59; // r8
  int v60; // r9d
  int v61; // eax
  int v62; // edx
  const char *v63; // r8
  int v64; // r9d
  enum D2D1_GEOMETRY_SIMPLIFICATION_OPTION v65; // edx
  const struct D2D_MATRIX_3X2_F *v66; // r8
  int v67; // eax
  int v68; // edx
  const char *v69; // r8
  int v70; // r9d
  int XpsOMGeometry; // eax
  int v72; // edx
  const char *v73; // r8
  int v74; // r9d
  ID2D1Geometry *v75; // rbx
  int v76; // eax
  int v77; // edx
  const char *v78; // r8
  int v79; // r9d
  wchar_t *v80; // rdi
  int v81; // ebx
  ID2D1Geometry *v82; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v83; // [rsp+38h] [rbp-C8h] BYREF
  ID2D1Geometry *v84; // [rsp+40h] [rbp-C0h] BYREF
  struct ID2D1SimplifiedGeometrySink *v85; // [rsp+48h] [rbp-B8h] BYREF
  ID2D1Geometry *v86; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v87; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v88; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v89)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 v90; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String1[3]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v92[176]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v93; // [rsp+158h] [rbp+58h] BYREF
  __int64 v94; // [rsp+168h] [rbp+68h] BYREF

  v89 = 0;
  v6 = *a2;
  v7 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)*a2 + 24LL);
  v8 = win_scope::detail::scope_helper<IUnknown *,win_scope::const_policies<win_scope::com_policies>>::safe_replace(&v89);
  v9 = v7(v6, v8);
  if ( v9 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v9, v10, v11, v12);
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v89;
  if ( v89 )
  {
    v83 = 0;
    v14 = **v89;
    win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v83,
      0);
    v83 = 0;
    v15 = v14(v13, &GUID_221d1452_331e_47c6_87e9_6ccefb9b5ba3, &v83);
    if ( (int)(v15 + 0x80000000) >= 0 && v15 != -2147467262 )
      dxc::ThrowHRExceptionPage((dxc *)v15, 0x80000000, v16, v17);
    v18 = v83;
    if ( v83 )
    {
      v88 = 0;
      v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 240LL);
      v94 = 0;
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v94,
        &v88);
      if ( v94 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      v88 = 0;
      v20 = v19(v18, &v88);
      if ( v20 < 0 )
        dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v20, v21, v22, v23);
      v93 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v88 + 24LL))(v88, &v93);
      if ( v24 < 0 )
        dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v24, v25, v26, v27);
      for ( i = 0; i < v93; ++i )
      {
        v94 = 0;
        v29 = v88;
        v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v88 + 32LL);
        win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
          &v94,
          0);
        v94 = 0;
        v31 = v30(v29, i, &v94);
        if ( v31 < 0 )
          dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v31, v32, v33, v34);
        String1[1] = (wchar_t *)&v82;
        v82 = 0;
        win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
          &v82,
          *a2);
        v84 = 0;
        win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
          &v84,
          v94);
        v35 = v82;
        v36 = v84 == v82;
        if ( v84 )
        {
          (*(void (__fastcall **)(ID2D1Geometry *))(*(_QWORD *)v84 + 16LL))(v84);
          v35 = v82;
        }
        if ( v35 )
          (*(void (__fastcall **)(ID2D1Geometry *))(*(_QWORD *)v35 + 16LL))(v35);
        if ( !v36 )
        {
          v84 = 0;
          v87 = 0;
          v37 = v94;
          v38 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v94 + 80LL);
          win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
            &v87,
            0);
          v87 = 0;
          v39 = v38(v37, &v87);
          if ( v39 < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v39, v40, v41, v42);
          if ( !v87 || dword_1805DC190 == -1 )
          {
            win_scope::scope<ID2D1Geometry *,win_scope::const_policies<win_scope::com_policies>>::operator=(
              &v84,
              a1 + 88);
          }
          else
          {
            v43 = (_QWORD *)dxc::ConvertXpsToD2DGeometry(&v90, *(_QWORD *)(a1 + 136), &v87);
            win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(
              &v84,
              *v43);
            if ( v90 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
              v90 = 0;
            }
          }
          v86 = 0;
          v44 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL);
          v45 = *(__int64 (__fastcall **)(__int64, ID2D1Geometry **))(*(_QWORD *)v44 + 80LL);
          win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(
            &v86,
            0);
          v86 = 0;
          v46 = v45(v44, &v86);
          if ( v46 < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v46, v47, v48, v49);
          v85 = 0;
          v50 = v86;
          v51 = *(__int64 (__fastcall **)(ID2D1Geometry *, struct ID2D1SimplifiedGeometrySink **))(*(_QWORD *)v86 + 136LL);
          v82 = 0;
          win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
            &v82,
            &v85);
          if ( v82 )
            (*(void (__fastcall **)(ID2D1Geometry *))(*(_QWORD *)v82 + 16LL))(v82);
          v85 = 0;
          v52 = v51(v50, &v85);
          if ( v52 < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v52, v53, v54, v55);
          v56 = v84;
          v57 = ID2D1Geometry::CombineWithGeometry(v84, *a3, D2D1_COMBINE_MODE_EXCLUDE, 0, v85);
          if ( v57 < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v57, v58, v59, v60);
          v61 = (*(__int64 (__fastcall **)(struct ID2D1SimplifiedGeometrySink *))(*(_QWORD *)v85 + 72LL))(v85);
          if ( v61 < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v61, v62, v63, v64);
          dxc::GeometrySink::GeometrySink(v92, *(_QWORD *)(a1 + 136) + 16LL);
          v67 = ID2D1Geometry::Simplify(v86, v65, v66, (struct ID2D1SimplifiedGeometrySink *)v92);
          if ( v67 < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v67, v68, v69, v70);
          v82 = 0;
          XpsOMGeometry = dxc::GeometrySink::GetXpsOMGeometry(v92, 0, &v82);
          if ( XpsOMGeometry < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)XpsOMGeometry, v72, v73, v74);
          v75 = v82;
          v76 = (*(__int64 (__fastcall **)(__int64, ID2D1Geometry *))(*(_QWORD *)v94 + 96LL))(v94, v82);
          if ( v76 < 0 )
            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v76, v77, v78, v79);
          if ( v75 )
            (*(void (__fastcall **)(ID2D1Geometry *))(*(_QWORD *)v75 + 16LL))(v75);
          dxc::GeometrySink::~GeometrySink((dxc::GeometrySink *)v92);
          if ( v85 )
          {
            (*(void (__fastcall **)(struct ID2D1SimplifiedGeometrySink *))(*(_QWORD *)v85 + 16LL))(v85);
            v85 = 0;
          }
          if ( v86 )
          {
            (*(void (__fastcall **)(ID2D1Geometry *))(*(_QWORD *)v86 + 16LL))(v86);
            v86 = 0;
          }
          if ( v87 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
            v87 = 0;
          }
          if ( v56 )
            (*(void (__fastcall **)(ID2D1Geometry *))(*(_QWORD *)v56 + 16LL))(v56);
        }
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      }
      String1[0] = 0;
      if ( (*(int (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v83 + 264LL))(v83, String1) >= 0 )
      {
        v80 = String1[0];
        if ( String1[0] )
        {
          v81 = wcscmp_0(String1[0], L"AACLIP");
          CoTaskMemFree(v80);
          if ( !v81 )
          {
            v94 = 0;
            win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
              &v94,
              v83);
            dxc::CConversionSinkImpl::UpdateSiblingClip(a1, &v94, a3);
            if ( v94 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          }
        }
      }
      if ( v88 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
        v88 = 0;
      }
      if ( v83 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        v83 = 0;
      }
    }
    if ( v89 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v89)[2])(v89);
  }
}

```

## disassembly

```asm
0x1801f7444  mov     [rsp-8+arg_0], rbx
0x1801f7449  push    rbp
0x1801f744a  push    rsi
0x1801f744b  push    rdi
0x1801f744c  push    r12
0x1801f744e  push    r13
0x1801f7450  push    r14
0x1801f7452  push    r15
0x1801f7454  lea     rbp, [rsp-10h]
0x1801f7459  sub     rsp, 110h
0x1801f7460  mov     r15, r8
0x1801f7463  mov     r12, rdx
0x1801f7466  mov     r14, rcx
0x1801f7469  xor     r13d, r13d
0x1801f746c  mov     [rsp+140h+var_D8], r13
0x1801f7471  mov     rdi, [rdx]
0x1801f7474  mov     rax, [rdi]
0x1801f7477  mov     rbx, [rax+18h]
0x1801f747b  lea     rcx, [rsp+140h+var_D8]
0x1801f7480  call    ?safe_replace@?$scope_helper@PEAUIUnknown@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAPEAPEAUIUnknown@@AEAV?$scope@PEAUIUnknown@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@@Z; win_scope::detail::scope_helper<IUnknown *,win_scope::const_policies<win_scope::com_policies>>::safe_replace(win_scope::scope<IUnknown *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801f7485  mov     rdx, rax
0x1801f7488  mov     rcx, rdi
0x1801f748b  mov     rax, rbx
0x1801f748e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7493  test    eax, eax
0x1801f7495  jns     short loc_1801F749F
0x1801f7497  mov     ecx, eax; this
0x1801f7499  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801f749f  mov     rbx, [rsp+140h+var_D8]
0x1801f74a4  test    rbx, rbx
0x1801f74a7  jz      loc_1801F79E0
0x1801f74ad  mov     [rsp+140h+var_108], r13
0x1801f74b2  mov     rax, [rbx]
0x1801f74b5  mov     rdi, [rax]
0x1801f74b8  xor     edx, edx
0x1801f74ba  lea     rcx, [rsp+140h+var_108]
0x1801f74bf  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801f74c4  mov     [rsp+140h+var_108], r13
0x1801f74c9  lea     r8, [rsp+140h+var_108]
0x1801f74ce  lea     rdx, _GUID_221d1452_331e_47c6_87e9_6ccefb9b5ba3
0x1801f74d5  mov     rcx, rbx
0x1801f74d8  mov     rax, rdi
0x1801f74db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f74e0  mov     edx, 80000000h; int
0x1801f74e5  lea     ecx, [rax+rdx]
0x1801f74e8  test    edx, ecx
0x1801f74ea  jnz     short loc_1801F74FB
0x1801f74ec  cmp     eax, 80004002h
0x1801f74f1  jz      short loc_1801F74FB
0x1801f74f3  mov     ecx, eax; this
0x1801f74f5  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801f74fb  mov     rbx, [rsp+140h+var_108]
0x1801f7500  test    rbx, rbx
0x1801f7503  jz      loc_1801F79C8
0x1801f7509  mov     [rsp+140h+var_E0], r13
0x1801f750e  mov     rax, [rbx]
0x1801f7511  mov     rdi, [rax+0F0h]
0x1801f7518  mov     [rbp+40h+arg_18], r13
0x1801f751c  lea     rdx, [rsp+140h+var_E0]
0x1801f7521  lea     rcx, [rbp+40h+arg_18]
0x1801f7525  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801f752a  nop
0x1801f752b  mov     rcx, [rbp+40h+arg_18]
0x1801f752f  test    rcx, rcx
0x1801f7532  jz      short loc_1801F7541
0x1801f7534  mov     rdx, [rcx]
0x1801f7537  mov     rax, [rdx+10h]
0x1801f753b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7540  nop
0x1801f7541  mov     [rsp+140h+var_E0], r13
0x1801f7546  lea     rdx, [rsp+140h+var_E0]
0x1801f754b  mov     rcx, rbx
0x1801f754e  mov     rax, rdi
0x1801f7551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7556  test    eax, eax
0x1801f7558  jns     short loc_1801F7562
0x1801f755a  mov     ecx, eax; this
0x1801f755c  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801f7562  mov     [rbp+40h+arg_8], r13d
0x1801f7566  mov     rcx, [rsp+140h+var_E0]
0x1801f756b  mov     rax, [rcx]
0x1801f756e  lea     rdx, [rbp+40h+arg_8]
0x1801f7572  mov     rax, [rax+18h]
0x1801f7576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f757b  test    eax, eax
0x1801f757d  jns     short loc_1801F7587
0x1801f757f  mov     ecx, eax; this
0x1801f7581  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801f7587  mov     esi, r13d
0x1801f758a  cmp     esi, [rbp+40h+arg_8]
0x1801f758d  jnb     loc_1801F790D
0x1801f7593  mov     [rbp+40h+arg_18], r13
0x1801f7597  mov     rdi, [rsp+140h+var_E0]
0x1801f759c  mov     rax, [rdi]
0x1801f759f  mov     rbx, [rax+20h]
0x1801f75a3  xor     edx, edx
0x1801f75a5  lea     rcx, [rbp+40h+arg_18]
0x1801f75a9  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801f75ae  mov     [rbp+40h+arg_18], r13
0x1801f75b2  lea     r8, [rbp+40h+arg_18]
0x1801f75b6  mov     edx, esi
0x1801f75b8  mov     rcx, rdi
0x1801f75bb  mov     rax, rbx
0x1801f75be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f75c3  test    eax, eax
0x1801f75c5  js      loc_1801F7905
0x1801f75cb  lea     rax, [rsp+140h+var_110]
0x1801f75d0  mov     [rbp+40h+var_C0], rax
0x1801f75d4  mov     [rsp+140h+var_110], r13
0x1801f75d9  mov     rdx, [r12]
0x1801f75dd  lea     rcx, [rsp+140h+var_110]
0x1801f75e2  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801f75e7  nop
0x1801f75e8  mov     [rsp+140h+var_100], r13
0x1801f75ed  mov     rdx, [rbp+40h+arg_18]
0x1801f75f1  lea     rcx, [rsp+140h+var_100]
0x1801f75f6  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801f75fb  nop
0x1801f75fc  mov     rdx, [rsp+140h+var_100]
0x1801f7601  mov     rcx, [rsp+140h+var_110]
0x1801f7606  cmp     rdx, rcx
0x1801f7609  setz    bl
0x1801f760c  test    rdx, rdx
0x1801f760f  jz      short loc_1801F7625
0x1801f7611  mov     rax, [rdx]
0x1801f7614  mov     rcx, rdx
0x1801f7617  mov     rax, [rax+10h]
0x1801f761b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7620  mov     rcx, [rsp+140h+var_110]
0x1801f7625  test    rcx, rcx
0x1801f7628  jz      short loc_1801F7637
0x1801f762a  mov     rax, [rcx]
0x1801f762d  mov     rax, [rax+10h]
0x1801f7631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7636  nop
0x1801f7637  test    bl, bl
0x1801f7639  jz      short loc_1801F7640
0x1801f763b  jmp     loc_1801F78A8
0x1801f7640  mov     [rsp+140h+var_100], r13
0x1801f7645  mov     [rsp+140h+var_E8], r13
0x1801f764a  mov     rdi, [rbp+40h+arg_18]
0x1801f764e  mov     rax, [rdi]
0x1801f7651  mov     rbx, [rax+50h]
0x1801f7655  xor     edx, edx
0x1801f7657  lea     rcx, [rsp+140h+var_E8]
0x1801f765c  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801f7661  mov     [rsp+140h+var_E8], r13
0x1801f7666  lea     rdx, [rsp+140h+var_E8]
0x1801f766b  mov     rcx, rdi
0x1801f766e  mov     rax, rbx
0x1801f7671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7676  test    eax, eax
0x1801f7678  js      loc_1801F78FD
0x1801f767e  cmp     [rsp+140h+var_E8], r13
0x1801f7683  jz      short loc_1801F76D0
0x1801f7685  cmp     cs:dword_1805DC190, 0FFFFFFFFh
0x1801f768c  jz      short loc_1801F76D0
0x1801f768e  lea     r8, [rsp+140h+var_E8]
0x1801f7693  mov     rdx, [r14+88h]
0x1801f769a  lea     rcx, [rsp+140h+var_D0]
0x1801f769f  call    ?ConvertXpsToD2DGeometry@dxc@@YA?AV?$scope@PEAUID2D1PathGeometry@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBURenderState@1@AEBV?$scope@PEAUIXpsOMGeometry@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@@Z; dxc::ConvertXpsToD2DGeometry(dxc::RenderState const &,win_scope::scope<IXpsOMGeometry *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1801f76a4  nop
0x1801f76a5  mov     rdx, [rax]
0x1801f76a8  lea     rcx, [rsp+140h+var_100]
0x1801f76ad  call    ?reset@?$scope_helper@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAVIDeviceInternal@@@Z; win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>> &,IDeviceInternal *)
0x1801f76b2  nop
0x1801f76b3  mov     rcx, [rsp+140h+var_D0]
0x1801f76b8  test    rcx, rcx
0x1801f76bb  jz      short loc_1801F76DE
0x1801f76bd  mov     rax, [rcx]
0x1801f76c0  mov     rax, [rax+10h]
0x1801f76c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f76c9  mov     [rsp+140h+var_D0], r13
0x1801f76ce  jmp     short loc_1801F76DE
0x1801f76d0  lea     rdx, [r14+58h]
0x1801f76d4  lea     rcx, [rsp+140h+var_100]
0x1801f76d9  call    ??4?$scope@PEAUID2D1Geometry@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAAAEAV01@AEBV01@@Z; win_scope::scope<ID2D1Geometry *,win_scope::const_policies<win_scope::com_policies>>::operator=(win_scope::scope<ID2D1Geometry *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1801f76de  mov     [rsp+140h+var_F0], r13
0x1801f76e3  mov     rax, [r14+88h]
0x1801f76ea  mov     rdi, [rax+8]
0x1801f76ee  mov     rax, [rdi]
0x1801f76f1  mov     rbx, [rax+50h]
0x1801f76f5  xor     edx, edx
0x1801f76f7  lea     rcx, [rsp+140h+var_F0]
0x1801f76fc  call    ?reset@?$scope_helper@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAVIDeviceInternal@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAVIDeviceInternal@@@Z; win_scope::detail::scope_helper<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IDeviceInternal *,win_scope::const_policies<win_scope::com_policies>> &,IDeviceInternal *)
0x1801f7701  mov     [rsp+140h+var_F0], r13
0x1801f7706  lea     rdx, [rsp+140h+var_F0]
0x1801f770b  mov     rcx, rdi
0x1801f770e  mov     rax, rbx
0x1801f7711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7716  test    eax, eax
0x1801f7718  js      loc_1801F78F5
0x1801f771e  mov     [rsp+140h+var_F8], r13
0x1801f7723  mov     rbx, [rsp+140h+var_F0]
0x1801f7728  mov     rax, [rbx]
0x1801f772b  mov     rdi, [rax+88h]
0x1801f7732  mov     [rsp+140h+var_110], r13
0x1801f7737  lea     rdx, [rsp+140h+var_F8]
0x1801f773c  lea     rcx, [rsp+140h+var_110]
0x1801f7741  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801f7746  mov     rcx, [rsp+140h+var_110]
0x1801f774b  test    rcx, rcx
0x1801f774e  jz      short loc_1801F775C
0x1801f7750  mov     rdx, [rcx]
0x1801f7753  mov     rax, [rdx+10h]
0x1801f7757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f775c  mov     [rsp+140h+var_F8], r13
0x1801f7761  lea     rdx, [rsp+140h+var_F8]
0x1801f7766  mov     rcx, rbx
0x1801f7769  mov     rax, rdi
0x1801f776c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7771  test    eax, eax
0x1801f7773  js      loc_1801F78ED
0x1801f7779  mov     rax, [rsp+140h+var_F8]
0x1801f777e  mov     [rsp+140h+var_120], rax; struct ID2D1SimplifiedGeometrySink *
0x1801f7783  xor     r9d, r9d; struct D2D_MATRIX_3X2_F *
0x1801f7786  lea     r8d, [r9+3]; enum D2D1_COMBINE_MODE
0x1801f778a  mov     rdx, [r15]; struct ID2D1Geometry *
0x1801f778d  mov     rdi, [rsp+140h+var_100]
0x1801f7792  mov     rcx, rdi; this
0x1801f7795  call    ?CombineWithGeometry@ID2D1Geometry@@QEBAJPEAU1@W4D2D1_COMBINE_MODE@@PEBUD2D_MATRIX_3X2_F@@PEAUID2D1SimplifiedGeometrySink@@@Z; ID2D1Geometry::CombineWithGeometry(ID2D1Geometry *,D2D1_COMBINE_MODE,D2D_MATRIX_3X2_F const *,ID2D1SimplifiedGeometrySink *)
0x1801f779a  test    eax, eax
0x1801f779c  js      loc_1801F78E5
0x1801f77a2  mov     rcx, [rsp+140h+var_F8]
0x1801f77a7  mov     rax, [rcx]
0x1801f77aa  mov     rax, [rax+48h]
0x1801f77ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f77b3  test    eax, eax
0x1801f77b5  js      loc_1801F78DD
0x1801f77bb  mov     rdx, [r14+88h]
0x1801f77c2  add     rdx, 10h
0x1801f77c6  lea     rcx, [rbp+40h+var_B0]
0x1801f77ca  call    ??0GeometrySink@dxc@@QEAA@AEBV?$scope@PEAUIXpsOMObjectFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; dxc::GeometrySink::GeometrySink(win_scope::scope<IXpsOMObjectFactory *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1801f77cf  nop
0x1801f77d0  lea     r9, [rbp+40h+var_B0]; struct ID2D1SimplifiedGeometrySink *
0x1801f77d4  mov     rcx, [rsp+140h+var_F0]; this
0x1801f77d9  call    ?Simplify@ID2D1Geometry@@QEBAJW4D2D1_GEOMETRY_SIMPLIFICATION_OPTION@@PEBUD2D_MATRIX_3X2_F@@PEAUID2D1SimplifiedGeometrySink@@@Z; ID2D1Geometry::Simplify(D2D1_GEOMETRY_SIMPLIFICATION_OPTION,D2D_MATRIX_3X2_F const *,ID2D1SimplifiedGeometrySink *)
0x1801f77de  test    eax, eax
0x1801f77e0  js      loc_1801F78D5
0x1801f77e6  mov     [rsp+140h+var_110], r13
0x1801f77eb  lea     r8, [rsp+140h+var_110]
0x1801f77f0  xor     edx, edx
0x1801f77f2  lea     rcx, [rbp+40h+var_B0]
0x1801f77f6  call    ?GetXpsOMGeometry@GeometrySink@dxc@@QEBAJW4Enum@EmptyBehavior@2@AEAV?$scope@PEAUIXpsOMGeometry@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; dxc::GeometrySink::GetXpsOMGeometry(dxc::EmptyBehavior::Enum,win_scope::scope<IXpsOMGeometry *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801f77fb  test    eax, eax
0x1801f77fd  js      loc_1801F78CD
0x1801f7803  mov     rcx, [rbp+40h+arg_18]
0x1801f7807  mov     rax, [rcx]
0x1801f780a  mov     rbx, [rsp+140h+var_110]
0x1801f780f  mov     rdx, rbx
0x1801f7812  mov     rax, [rax+60h]
0x1801f7816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f781b  test    eax, eax
0x1801f781d  js      loc_1801F78C5
0x1801f7823  test    rbx, rbx
0x1801f7826  jz      short loc_1801F7838
0x1801f7828  mov     rax, [rbx]
0x1801f782b  mov     rcx, rbx
0x1801f782e  mov     rax, [rax+10h]
0x1801f7832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7837  nop
0x1801f7838  lea     rcx, [rbp+40h+var_B0]; this
0x1801f783c  call    ??1GeometrySink@dxc@@UEAA@XZ; dxc::GeometrySink::~GeometrySink(void)
0x1801f7841  nop
0x1801f7842  mov     rcx, [rsp+140h+var_F8]
0x1801f7847  test    rcx, rcx
0x1801f784a  jz      short loc_1801F785D
0x1801f784c  mov     rax, [rcx]
0x1801f784f  mov     rax, [rax+10h]
0x1801f7853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7858  mov     [rsp+140h+var_F8], r13
0x1801f785d  mov     rcx, [rsp+140h+var_F0]
0x1801f7862  test    rcx, rcx
0x1801f7865  jz      short loc_1801F7878
0x1801f7867  mov     rax, [rcx]
0x1801f786a  mov     rax, [rax+10h]
0x1801f786e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f7873  mov     [rsp+140h+var_F0], r13
0x1801f7878  mov     rcx, [rsp+140h+var_E8]
0x1801f787d  test    rcx, rcx
0x1801f7880  jz      short loc_1801F7893
0x1801f7882  mov     rax, [rcx]
0x1801f7885  mov     rax, [rax+10h]
0x1801f7889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f788e  mov     [rsp+140h+var_E8], r13
0x1801f7893  test    rdi, rdi
0x1801f7896  jz      short loc_1801F78A8
0x1801f7898  mov     rax, [rdi]
0x1801f789b  mov     rcx, rdi
0x1801f789e  mov     rax, [rax+10h]
0x1801f78a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f78a7  nop
0x1801f78a8  mov     rcx, [rbp+40h+arg_18]
0x1801f78ac  test    rcx, rcx
0x1801f78af  jz      short loc_1801F78BE
0x1801f78b1  mov     rax, [rcx]
0x1801f78b4  mov     rax, [rax+10h]
0x1801f78b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f78bd  nop
0x1801f78be  inc     esi
  ... truncated ...
```
