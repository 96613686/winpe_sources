# ShellHandwriting::HandwritingClient::GetCharacterLevelContext(IUIAutomationTextRange *,int,IUIAutomationTextPattern *,IUIAutomationElementArray *,int,tagRECT,IUIAutomationTextRange *,std::vector<TextUnitInfo,std::allocator<TextUnitInfo>> &)

- ea: `0x1800f57c0`
- end: `0x1800f60b8`
- name: `?GetCharacterLevelContext@HandwritingClient@ShellHandwriting@@AEAAJPEAUIUIAutomationTextRange@@HPEAUIUIAutomationTextPattern@@PEAUIUIAutomationElementArray@@HUtagRECT@@0AEAV?$vector@UTextUnitInfo@@V?$allocator@UTextUnitInfo@@@std@@@std@@@Z`
- size: `2296`
- prototype: `__int64 __usercall@<rax>(ShellHandwriting::HandwritingClient *this@<rcx>, __int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f80e0`

## callees

- `0x18008b4b4`
- `0x18008e51c`
- `0x180091e60`
- `0x180093364`
- `0x1800f0004`
- `0x1800f04b0`
- `0x1800f0cd4`
- `0x1800f0e40`
- `0x1800f57c0`
- `0x1800f6e5c`
- `0x1800fa59c`
- `0x1800fa6b4`
- `0x1800fc8d8`
- `0x1800fd314`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5aea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5ef0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5aea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5ef0`
- `USER32!IsRectEmpty` at `0x1800f5bf7`
- `USER32!IsRectEmpty` at `0x1800f5d66`
- `USER32!IsRectEmpty` at `0x1800f5e25`
- `USER32!IsRectEmpty` at `0x1800f5bf7`
- `USER32!IsRectEmpty` at `0x1800f5d66`
- `USER32!IsRectEmpty` at `0x1800f5e25`
- `OLEAUT32!__imp_SysStringLen` at `0x1800f59b7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800f59b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellHandwriting::HandwritingClient::GetCharacterLevelContext(
        ShellHandwriting::HandwritingClient *this,
        __int64 a2,
        int a3,
        struct IUIAutomationTextPattern *a4,
        OLECHAR *a5,
        int a6,
        _DWORD *a7,
        struct IUIAutomationTextRange *a8,
        __int64 a9)
{
  struct IUIAutomationTextPattern v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  int v22; // eax
  char v23; // si
  int v24; // eax
  __int64 v25; // rdx
  void *p_pbstr; // rcx
  __int64 (__fastcall *v27)(__int64, __int64, __int64); // rbx
  __int64 v28; // rax
  HRESULT (__stdcall *Clone)(IUIAutomationTextRange *, IUIAutomationTextRange **); // rbx
  struct IUIAutomationTextRange *v30; // rcx
  unsigned int v31; // ecx
  float v32; // xmm6_4
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // ebx
  int v37; // r15d
  unsigned int v38; // r13d
  __int64 v39; // r12
  int v40; // edi
  struct IUIAutomationTextRange *v41; // rdi
  HRESULT (__stdcall *GetText)(IUIAutomationTextRange *, int, BSTR *); // rbx
  __int64 v43; // rax
  int v44; // eax
  DWORD v45; // ebx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // r9
  _QWORD *v52; // rax
  int Start; // eax
  __int64 v54; // r9
  __int64 v55; // rdx
  DWORD LowPart; // edi
  int v57; // r12d
  _QWORD *v58; // rax
  __int64 v59; // rcx
  DWORD v60; // edi
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rax
  __int64 v66; // r9
  _QWORD *v67; // rax
  unsigned __int64 v68; // rax
  __int64 v70; // rdx
  __int64 v71; // rdx
  int v72; // [rsp+20h] [rbp-E0h]
  unsigned int *v73; // [rsp+20h] [rbp-E0h]
  struct IUIAutomationTextRange *v74; // [rsp+40h] [rbp-C0h] BYREF
  struct IUIAutomationTextRange *v75; // [rsp+48h] [rbp-B8h] BYREF
  struct IUIAutomationTextRange *v76; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v77; // [rsp+58h] [rbp-A8h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp-A0h] BYREF
  LARGE_INTEGER v79; // [rsp+68h] [rbp-98h] BYREF
  struct tagPOINT v80; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v81; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v82; // [rsp+7Ch] [rbp-84h] BYREF
  int v83; // [rsp+80h] [rbp-80h] BYREF
  int v84; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v85; // [rsp+88h] [rbp-78h]
  int v86; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v87; // [rsp+94h] [rbp-6Ch]
  unsigned int v88; // [rsp+98h] [rbp-68h]
  RECT v89; // [rsp+9Ch] [rbp-64h]
  int v90; // [rsp+B0h] [rbp-50h] BYREF
  int v91; // [rsp+B4h] [rbp-4Ch] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v93[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v94[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v95[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v96[8]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v97[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v98[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v99[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v100[8]; // [rsp+F8h] [rbp-8h] BYREF
  RECT rc; // [rsp+100h] [rbp+0h] BYREF
  RECT v102; // [rsp+110h] [rbp+10h] BYREF
  RECT v103; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  pbstr = a5;
  v85 = a9;
  v80.x = (*a7 + a7[2]) / 2;
  v80.y = (a7[1] + a7[3]) / 2;
  v13.lpVtbl = a4->lpVtbl;
  v76 = 0;
  v14 = ((__int64 (__fastcall *)(struct IUIAutomationTextPattern *, struct tagPOINT, struct IUIAutomationTextRange **))v13.lpVtbl->RangeFromPoint)(
          a4,
          v80,
          &v76);
  v15 = v14;
  if ( v14 < 0 )
  {
    v16 = (unsigned int)v14;
    v17 = 3369;
LABEL_94:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\client\\handwritingclient.cpp",
      (const char *)v16,
      v72);
    goto LABEL_95;
  }
  if ( !v76 )
  {
    v15 = -2147467259;
    v16 = 2147500037LL;
    v17 = 3372;
    goto LABEL_94;
  }
  v74 = 0;
  v18 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, struct IUIAutomationTextRange **))v76->lpVtbl->Clone)(
          v76,
          &v74);
  v15 = v18;
  if ( v18 < 0 )
  {
    v19 = (unsigned int)v18;
    v20 = 3376;
LABEL_91:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\client\\handwritingclient.cpp",
      (const char *)v19,
      v72);
    goto LABEL_92;
  }
  if ( !v74 )
  {
    v15 = -2147467259;
    v19 = 2147500037LL;
    v20 = 3378;
    goto LABEL_91;
  }
  v21 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD))v76->lpVtbl->ExpandToEnclosingUnit)(v76, 0);
  v15 = v21;
  if ( v21 < 0 )
  {
    v19 = (unsigned int)v21;
    v20 = 3381;
    goto LABEL_91;
  }
  v22 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD))v74->lpVtbl->ExpandToEnclosingUnit)(v74, 0);
  v15 = v22;
  if ( v22 < 0 )
  {
    v19 = (unsigned int)v22;
    v20 = 3382;
    goto LABEL_91;
  }
  v77 = 0;
  v75 = 0;
  v23 = 1;
  if ( a6 )
  {
    Start = ShellHandwriting::HandwritingClient::GetStart(
              this,
              a8,
              v76,
              a4,
              (struct IUIAutomationElementArray *)pbstr,
              a6,
              (int *)&v77,
              &v75);
    v15 = Start;
    if ( Start < 0 )
    {
      v54 = (unsigned int)Start;
      v55 = 3416;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v55,
        (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\client\\handwritingclient.cpp",
        (const char *)v54,
        v72);
LABEL_16:
      wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v75);
LABEL_92:
      wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v74);
      goto LABEL_95;
    }
  }
  else
  {
    pbstr = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, __int64, struct IUIAutomationTextRange *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            1,
            v76,
            0);
    v15 = v24;
    if ( v24 < 0 )
    {
      v25 = 3390;
      goto LABEL_14;
    }
    v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a2 + 96LL);
    v28 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pbstr);
    v24 = v27(a2, 0xFFFFFFFFLL, v28);
    v15 = v24;
    if ( v24 < 0 )
    {
      v25 = 3391;
      goto LABEL_14;
    }
    v77 = SysStringLen(pbstr);
    Clone = a8->lpVtbl->Clone;
    v30 = v75;
    v75 = 0;
    if ( v30 )
      ((void (__fastcall *)(struct IUIAutomationTextRange *))v30->lpVtbl->Release)(v30);
    v24 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, struct IUIAutomationTextRange **))Clone)(a8, &v75);
    v15 = v24;
    if ( v24 < 0 )
    {
      v25 = 3393;
      goto LABEL_14;
    }
    if ( v77 == a3 )
    {
      v90 = 0;
      v91 = 0;
      v24 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD, __int64, int *))v76->lpVtbl->Move)(
              v76,
              0,
              0xFFFFFFFFLL,
              &v90);
      v15 = v24;
      if ( v24 < 0 )
      {
        v25 = 3403;
        goto LABEL_14;
      }
      v24 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD, __int64, int *))v74->lpVtbl->Move)(
              v74,
              0,
              1,
              &v91);
      v15 = v24;
      if ( v24 < 0 )
      {
        v25 = 3404;
        goto LABEL_14;
      }
      v24 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD))v76->lpVtbl->ExpandToEnclosingUnit)(
              v76,
              0);
      v15 = v24;
      if ( v24 < 0 )
      {
        v25 = 3407;
        goto LABEL_14;
      }
      v24 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD))v74->lpVtbl->ExpandToEnclosingUnit)(
              v74,
              0);
      v15 = v24;
      if ( v24 < 0 )
      {
        v25 = 3408;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\client\\handwritingclient.cpp",
          (const char *)(unsigned int)v24,
          v72);
        p_pbstr = &pbstr;
LABEL_15:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_pbstr);
        goto LABEL_16;
      }
      --v77;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
  }
  if ( !v75 )
  {
    v15 = -2147467259;
    v54 = 2147500037LL;
    v55 = 3419;
    goto LABEL_50;
  }
  v31 = v77;
  *((_BYTE *)this + 117) = (int)v77 > 0;
  ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::UIACharacterLevelEditContextInitiated(v31, &v80);
  v32 = 0.0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v36 = 0;
  v37 = v77;
  v82 = 1;
  v81 = 1;
  v83 = 0;
  v84 = 0;
  v38 = v77;
  v39 = v85;
  while ( 1 )
  {
    if ( (int)v82 <= 0 && (int)v81 <= 0 )
    {
LABEL_82:
      if ( v36 <= 0 )
        goto LABEL_83;
      goto LABEL_72;
    }
    v73 = &v82;
    v40 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD, struct IUIAutomationTextRange *, _QWORD))v76->lpVtbl->CompareEndpoints)(
            v76,
            0,
            v75,
            0);
    if ( v40 < 0 )
      break;
    v73 = &v81;
    v40 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, __int64, struct IUIAutomationTextRange *, __int64))v75->lpVtbl->CompareEndpoints)(
            v75,
            1,
            v74,
            1);
    if ( v40 < 0 )
    {
      v71 = 3444;
      goto LABEL_88;
    }
    if ( v36 )
    {
      if ( (v82 & 0x80000000) == 0 && v37 > 0 && v83 < 0 )
      {
        v102 = 0;
        v79.LowPart = 0;
        v40 = ShellHandwriting::HandwritingClient::CollectBoundingBoxUIA(this, v76, &v102, (int *)&v79);
        if ( v40 < 0 )
        {
          v71 = 3478;
          goto LABEL_88;
        }
        ++v36;
        LowPart = v79.LowPart;
        if ( !v79.LowPart || IsRectEmpty(&v102) )
          goto LABEL_82;
        v86 = 0;
        v57 = v37 - LowPart;
        v87 = v37 - LowPart;
        v88 = v37;
        v89 = v102;
        v58 = (_QWORD *)std::vector<TextUnitInfo>::begin(v85, v96);
        std::vector<TextUnitInfo>::insert(v59, v97, *v58, &v86);
        v40 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD, __int64, int *))v76->lpVtbl->Move)(
                v76,
                0,
                0xFFFFFFFFLL,
                &v83);
        if ( v40 < 0 )
        {
          v71 = 3489;
          goto LABEL_88;
        }
        v37 = v57;
      }
      if ( (v81 & 0x80000000) != 0 || v84 <= 0 )
      {
        v39 = v85;
      }
      else
      {
        v103 = 0;
        v79.LowPart = 0;
        v40 = ShellHandwriting::HandwritingClient::CollectBoundingBoxUIA(this, v74, &v103, (int *)&v79);
        if ( v40 < 0 )
        {
          v71 = 3497;
          goto LABEL_88;
        }
        ++v36;
        v60 = v79.LowPart;
        if ( !v79.LowPart || IsRectEmpty(&v103) )
          goto LABEL_82;
        v86 = 0;
        v87 = v38;
        v38 += v60;
        v88 = v38;
        v89 = v103;
        v39 = v85;
        v61 = std::vector<TextUnitInfo>::begin(v85, v98);
        v65 = std::vector<TextUnitInfo>::size(v63, v62, v64, v61);
        v67 = (_QWORD *)std::_Vector_iterator<std::_Vector_val<std::_Simple_types<TextUnitInfo>>>::operator+(
                          v66,
                          v99,
                          v65);
        std::vector<TextUnitInfo>::insert(v39, v100, *v67, &v86);
        v40 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD, __int64, int *))v74->lpVtbl->Move)(
                v74,
                0,
                1,
                &v84);
        if ( v40 < 0 )
        {
          v71 = 3508;
          goto LABEL_88;
        }
      }
      if ( v36 > 20 && *((_BYTE *)this + 118) )
        goto LABEL_72;
      v33 = (unsigned int)(v36 / 250);
      if ( v36 == 250 * (_DWORD)v33 && v36 > 249 )
      {
        v79.QuadPart = 0;
        QueryPerformanceCounter(&v79);
        v32 = ShellHandwriting::HandwritingClient::CalculateDuration(this, PerformanceCount.QuadPart, v79.QuadPart);
        if ( v32 > 0.0 )
          goto LABEL_72;
      }
    }
    else
    {
      v80 = 0;
      v41 = v76;
      GetText = v76->lpVtbl->GetText;
      v43 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v80);
      v44 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, __int64, __int64))GetText)(v41, 0xFFFFFFFFLL, v43);
      v15 = v44;
      if ( v44 < 0 )
      {
        v70 = 3450;
        goto LABEL_74;
      }
      rc = 0;
      v79.LowPart = 0;
      v44 = ShellHandwriting::HandwritingClient::CollectBoundingBoxUIA(this, v76, &rc, (int *)&v79);
      v15 = v44;
      if ( v44 < 0 )
      {
        v70 = 3454;
        goto LABEL_74;
      }
      v45 = v79.LowPart;
      if ( !v79.LowPart || IsRectEmpty(&rc) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v80);
LABEL_83:
        if ( !*((_BYTE *)this + 117) )
          v23 = 0;
LABEL_72:
        *((_BYTE *)this + 117) = v23;
        v68 = std::vector<TextUnitInfo>::size(v85, v33, v34, v35);
        ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::UIACharacterLevelEditContext(
          v68,
          v32,
          v37,
          v38,
          v82,
          v81);
        wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v75);
        wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v74);
        wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v76);
        return 0;
      }
      v86 = 0;
      v87 = v38;
      v38 += v45;
      v88 = v38;
      v89 = rc;
      v46 = std::vector<TextUnitInfo>::begin(v39, v93);
      v50 = std::vector<TextUnitInfo>::size(v48, v47, v49, v46);
      v52 = (_QWORD *)std::_Vector_iterator<std::_Vector_val<std::_Simple_types<TextUnitInfo>>>::operator+(
                        v51,
                        v94,
                        v50);
      std::vector<TextUnitInfo>::insert(v39, v95, *v52, &v86);
      v44 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD, __int64, int *))v76->lpVtbl->Move)(
              v76,
              0,
              0xFFFFFFFFLL,
              &v83);
      v15 = v44;
      if ( v44 < 0 )
      {
        v70 = 3467;
        goto LABEL_74;
      }
      v44 = ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, _QWORD, __int64, int *))v74->lpVtbl->Move)(
              v74,
              0,
              1,
              &v84);
      v15 = v44;
      if ( v44 < 0 )
      {
        v70 = 3468;
LABEL_74:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v70,
          (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\client\\handwritingclient.cpp",
          (const char *)(unsigned int)v44,
          (int)&v81);
        p_pbstr = &v80;
        goto LABEL_15;
      }
      v36 = 1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v80);
    }
  }
  v71 = 3443;
LABEL_88:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v71,
    (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\client\\handwritingclient.cpp",
    (const char *)(unsigned int)v40,
    (int)v73);
  wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v75);
  wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v74);
  v15 = v40;
LABEL_95:
  wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v76);
  return v15;
}

```

## disassembly

```asm
0x1800f57c0  mov     rax, rsp
0x1800f57c3  mov     [rax+18h], rbx
0x1800f57c7  push    rbp
0x1800f57c8  push    rsi
0x1800f57c9  push    rdi
0x1800f57ca  push    r12
0x1800f57cc  push    r13
0x1800f57ce  push    r14
0x1800f57d0  push    r15
0x1800f57d2  lea     rbp, [rsp-50h]
0x1800f57d7  sub     rsp, 150h
0x1800f57de  movaps  xmmword ptr [rax-48h], xmm6
0x1800f57e2  mov     rax, cs:__security_cookie
0x1800f57e9  xor     rax, rsp
0x1800f57ec  mov     [rbp+80h+var_50], rax
0x1800f57f0  mov     r12, r9
0x1800f57f3  mov     r13d, r8d
0x1800f57f6  mov     rdi, rdx
0x1800f57f9  mov     r14, rcx
0x1800f57fc  mov     r9, [rbp+80h+arg_30]
0x1800f5803  mov     rax, [rbp+80h+arg_20]
0x1800f580a  mov     [rsp+180h+pbstr], rax
0x1800f580f  mov     r15, [rbp+80h+arg_38]
0x1800f5816  mov     rax, [rbp+80h+arg_40]
0x1800f581d  mov     [rbp+80h+var_F8], rax
0x1800f5821  mov     eax, [r9+8]
0x1800f5825  add     eax, [r9]
0x1800f5828  cdq
0x1800f5829  mov     ecx, 2
0x1800f582e  idiv    ecx
0x1800f5830  mov     [rsp+180h+var_110.x], eax
0x1800f5834  mov     eax, [r9+0Ch]
0x1800f5838  add     eax, [r9+4]
0x1800f583c  cdq
0x1800f583d  idiv    ecx
0x1800f583f  mov     [rsp+180h+var_110.y], eax
0x1800f5843  mov     rax, [r12]
0x1800f5847  xor     esi, esi
0x1800f5849  mov     [rsp+180h+var_130], rsi
0x1800f584e  lea     r8, [rsp+180h+var_130]
0x1800f5853  mov     rdx, qword ptr [rsp+180h+var_110.x]
0x1800f5858  mov     rcx, r12
0x1800f585b  mov     rax, [rax+18h]
0x1800f585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5864  mov     ebx, eax
0x1800f5866  test    eax, eax
0x1800f5868  jns     short loc_1800F5877
0x1800f586a  mov     r9d, eax
0x1800f586d  mov     edx, 0D29h
0x1800f5872  jmp     loc_1800F606D
0x1800f5877  mov     rcx, [rsp+180h+var_130]
0x1800f587c  test    rcx, rcx
0x1800f587f  jz      loc_1800F6060
0x1800f5885  mov     [rsp+180h+var_140], rsi
0x1800f588a  mov     rax, [rcx]
0x1800f588d  lea     rdx, [rsp+180h+var_140]
0x1800f5892  mov     rax, [rax+18h]
0x1800f5896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f589b  mov     ebx, eax
0x1800f589d  test    eax, eax
0x1800f589f  jns     short loc_1800F58AE
0x1800f58a1  mov     r9d, eax
0x1800f58a4  mov     edx, 0D30h
0x1800f58a9  jmp     loc_1800F6041
0x1800f58ae  cmp     [rsp+180h+var_140], rsi
0x1800f58b3  jz      loc_1800F6034
0x1800f58b9  mov     rcx, [rsp+180h+var_130]
0x1800f58be  mov     rax, [rcx]
0x1800f58c1  xor     edx, edx
0x1800f58c3  mov     rax, [rax+30h]
0x1800f58c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f58cc  mov     ebx, eax
0x1800f58ce  test    eax, eax
0x1800f58d0  jns     short loc_1800F58DF
0x1800f58d2  mov     r9d, eax
0x1800f58d5  mov     edx, 0D35h
0x1800f58da  jmp     loc_1800F6041
0x1800f58df  mov     rcx, [rsp+180h+var_140]
0x1800f58e4  mov     rax, [rcx]
0x1800f58e7  xor     edx, edx
0x1800f58e9  mov     rax, [rax+30h]
0x1800f58ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f58f2  mov     ebx, eax
0x1800f58f4  test    eax, eax
0x1800f58f6  jns     short loc_1800F5905
0x1800f58f8  mov     r9d, eax
0x1800f58fb  mov     edx, 0D36h
0x1800f5900  jmp     loc_1800F6041
0x1800f5905  mov     [rsp+180h+var_128], esi
0x1800f5909  mov     [rsp+180h+var_138], rsi
0x1800f590e  mov     esi, 1
0x1800f5913  mov     eax, [rbp+80h+arg_28]
0x1800f5919  test    eax, eax
0x1800f591b  jnz     loc_1800F5CAC
0x1800f5921  mov     [rsp+180h+pbstr], 0
0x1800f592a  mov     rax, [rdi]
0x1800f592d  xor     r9d, r9d
0x1800f5930  mov     r8, [rsp+180h+var_130]
0x1800f5935  mov     edx, esi
0x1800f5937  mov     rcx, rdi
0x1800f593a  mov     rax, [rax+78h]
0x1800f593e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5943  mov     ebx, eax
0x1800f5945  test    eax, eax
0x1800f5947  jns     short loc_1800F597D
0x1800f5949  mov     edx, 0D3Eh; void *
0x1800f594e  mov     rcx, [rbp+88h]; this
0x1800f5955  mov     r9d, eax; char *
0x1800f5958  lea     r8, aClientcoreWind; "clientcore\\windows\\advcore\\ctf\\shel"...
0x1800f595f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5964  lea     rcx, [rsp+180h+pbstr]
0x1800f5969  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f596e  lea     rcx, [rsp+180h+var_138]
0x1800f5973  call    ??1?$com_ptr_t@UITfContextView@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(void)
0x1800f5978  jmp     loc_1800F6054
0x1800f597d  mov     rax, [rdi]
0x1800f5980  mov     rbx, [rax+60h]
0x1800f5984  lea     rcx, [rsp+180h+pbstr]
0x1800f5989  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800f598e  mov     r8, rax
0x1800f5991  or      r12d, 0FFFFFFFFh
0x1800f5995  mov     edx, r12d
0x1800f5998  mov     rcx, rdi
0x1800f599b  mov     rax, rbx
0x1800f599e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f59a3  mov     ebx, eax
0x1800f59a5  xor     edi, edi
0x1800f59a7  test    eax, eax
0x1800f59a9  jns     short loc_1800F59B2
0x1800f59ab  mov     edx, 0D3Fh
0x1800f59b0  jmp     short loc_1800F594E
0x1800f59b2  mov     rcx, [rsp+180h+pbstr]; pbstr
0x1800f59b7  call    cs:__imp_SysStringLen
0x1800f59bd  mov     [rsp+180h+var_128], eax
0x1800f59c1  mov     rax, [r15]
0x1800f59c4  mov     rbx, [rax+18h]
0x1800f59c8  mov     rcx, [rsp+180h+var_138]
0x1800f59cd  mov     [rsp+180h+var_138], rdi
0x1800f59d2  test    rcx, rcx
0x1800f59d5  jz      short loc_1800F59E4
0x1800f59d7  mov     rdx, [rcx]
0x1800f59da  mov     rax, [rdx+10h]
0x1800f59de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f59e3  nop
0x1800f59e4  lea     rdx, [rsp+180h+var_138]
0x1800f59e9  mov     rcx, r15
0x1800f59ec  mov     rax, rbx
0x1800f59ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f59f4  mov     ebx, eax
0x1800f59f6  test    eax, eax
0x1800f59f8  jns     short loc_1800F5A04
0x1800f59fa  mov     edx, 0D41h
0x1800f59ff  jmp     loc_1800F594E
0x1800f5a04  cmp     [rsp+180h+var_128], r13d
0x1800f5a09  jnz     loc_1800F5AB3
0x1800f5a0f  mov     [rbp+80h+var_D0], edi
0x1800f5a12  mov     [rbp+80h+var_CC], edi
0x1800f5a15  mov     rcx, [rsp+180h+var_130]
0x1800f5a1a  mov     rax, [rcx]
0x1800f5a1d  lea     r9, [rbp+80h+var_D0]
0x1800f5a21  mov     r8d, r12d
0x1800f5a24  xor     edx, edx
0x1800f5a26  mov     rax, [rax+68h]
0x1800f5a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a2f  mov     ebx, eax
0x1800f5a31  test    eax, eax
0x1800f5a33  jns     short loc_1800F5A3F
0x1800f5a35  mov     edx, 0D4Bh
0x1800f5a3a  jmp     loc_1800F594E
0x1800f5a3f  mov     rcx, [rsp+180h+var_140]
0x1800f5a44  mov     rax, [rcx]
0x1800f5a47  lea     r9, [rbp+80h+var_CC]
0x1800f5a4b  mov     r8d, esi
0x1800f5a4e  xor     edx, edx
0x1800f5a50  mov     rax, [rax+68h]
0x1800f5a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a59  mov     ebx, eax
0x1800f5a5b  test    eax, eax
0x1800f5a5d  jns     short loc_1800F5A69
0x1800f5a5f  mov     edx, 0D4Ch
0x1800f5a64  jmp     loc_1800F594E
0x1800f5a69  mov     rcx, [rsp+180h+var_130]
0x1800f5a6e  mov     rax, [rcx]
0x1800f5a71  xor     edx, edx
0x1800f5a73  mov     rax, [rax+30h]
0x1800f5a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a7c  mov     ebx, eax
0x1800f5a7e  test    eax, eax
0x1800f5a80  jns     short loc_1800F5A8C
0x1800f5a82  mov     edx, 0D4Fh
0x1800f5a87  jmp     loc_1800F594E
0x1800f5a8c  mov     rcx, [rsp+180h+var_140]
0x1800f5a91  mov     rax, [rcx]
0x1800f5a94  xor     edx, edx
0x1800f5a96  mov     rax, [rax+30h]
0x1800f5a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a9f  mov     ebx, eax
0x1800f5aa1  test    eax, eax
0x1800f5aa3  jns     short loc_1800F5AAF
0x1800f5aa5  mov     edx, 0D50h
0x1800f5aaa  jmp     loc_1800F594E
0x1800f5aaf  sub     [rsp+180h+var_128], esi
0x1800f5ab3  lea     rcx, [rsp+180h+pbstr]
0x1800f5ab8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f5abd  cmp     [rsp+180h+var_138], rdi
0x1800f5ac2  jz      loc_1800F6022
0x1800f5ac8  mov     ecx, [rsp+180h+var_128]; unsigned int
0x1800f5acc  test    ecx, ecx
0x1800f5ace  setnle  al
0x1800f5ad1  mov     [r14+75h], al
0x1800f5ad5  lea     rdx, [rsp+180h+var_110]; struct tagPOINT *
0x1800f5ada  call    ?UIACharacterLevelEditContextInitiated@Client@ShellHandwriting@InputTraceLogging@2@SAXIPEBUtagPOINT@@@Z; ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::UIACharacterLevelEditContextInitiated(uint,tagPOINT const *)
0x1800f5adf  xorps   xmm6, xmm6
0x1800f5ae2  mov     qword ptr [rbp+80h+PerformanceCount], rdi
0x1800f5ae6  lea     rcx, [rbp+80h+PerformanceCount]; lpPerformanceCount
0x1800f5aea  call    cs:__imp_QueryPerformanceCounter
0x1800f5af0  mov     ebx, edi
0x1800f5af2  mov     r15d, [rsp+180h+var_128]
0x1800f5af7  mov     [rsp+180h+var_104], esi
0x1800f5afb  mov     [rsp+180h+var_108], esi
0x1800f5aff  mov     [rbp+80h+var_100], edi
0x1800f5b02  mov     [rbp+80h+var_FC], edi
0x1800f5b05  mov     r13d, r15d
0x1800f5b08  mov     r12, [rbp+80h+var_F8]
0x1800f5b0c  cmp     [rsp+180h+var_104], edi
0x1800f5b10  jg      short loc_1800F5B1C
0x1800f5b12  cmp     [rsp+180h+var_108], edi
0x1800f5b16  jle     loc_1800F5FC7
0x1800f5b1c  mov     rcx, [rsp+180h+var_130]
0x1800f5b21  mov     rax, [rcx]
0x1800f5b24  lea     rdx, [rsp+180h+var_104]
0x1800f5b29  mov     [rsp+180h+var_160], rdx; int
0x1800f5b2e  xor     r9d, r9d
0x1800f5b31  mov     r8, [rsp+180h+var_138]
0x1800f5b36  xor     edx, edx
0x1800f5b38  mov     rax, [rax+28h]
0x1800f5b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5b41  mov     edi, eax
0x1800f5b43  test    eax, eax
0x1800f5b45  js      loc_1800F5FEF
0x1800f5b4b  mov     rcx, [rsp+180h+var_138]
0x1800f5b50  mov     rax, [rcx]
0x1800f5b53  lea     rdx, [rsp+180h+var_108]
0x1800f5b58  mov     [rsp+180h+var_160], rdx; int
0x1800f5b5d  mov     r9d, esi
0x1800f5b60  mov     r8, [rsp+180h+var_140]
0x1800f5b65  mov     edx, esi
0x1800f5b67  mov     rax, [rax+28h]
0x1800f5b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5b70  mov     edi, eax
0x1800f5b72  test    eax, eax
0x1800f5b74  js      loc_1800F5FE8
0x1800f5b7a  xor     edi, edi
0x1800f5b7c  test    ebx, ebx
0x1800f5b7e  jnz     loc_1800F5D0D
0x1800f5b84  mov     qword ptr [rsp+180h+var_110.x], rdi
0x1800f5b89  mov     rdi, [rsp+180h+var_130]
0x1800f5b8e  mov     rax, [rdi]
0x1800f5b91  mov     rbx, [rax+60h]
0x1800f5b95  lea     rcx, [rsp+180h+var_110]
0x1800f5b9a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800f5b9f  mov     r8, rax
0x1800f5ba2  or      edx, 0FFFFFFFFh
0x1800f5ba5  mov     rcx, rdi
0x1800f5ba8  mov     rax, rbx
0x1800f5bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5bb0  mov     ebx, eax
0x1800f5bb2  xor     edi, edi
0x1800f5bb4  test    eax, eax
0x1800f5bb6  js      loc_1800F5FA9
0x1800f5bbc  xorps   xmm0, xmm0
0x1800f5bbf  movups  xmmword ptr [rbp+80h+rc.left], xmm0
0x1800f5bc3  mov     dword ptr [rsp+180h+var_118], edi
0x1800f5bc7  lea     r9, [rsp+180h+var_118]; int *
0x1800f5bcc  lea     r8, [rbp+80h+rc]; struct tagRECT *
0x1800f5bd0  mov     rdx, [rsp+180h+var_130]; struct IUIAutomationTextRange *
0x1800f5bd5  mov     rcx, r14; this
0x1800f5bd8  call    ?CollectBoundingBoxUIA@HandwritingClient@ShellHandwriting@@AEAAJPEAUIUIAutomationTextRange@@PEAUtagRECT@@PEAH@Z; ShellHandwriting::HandwritingClient::CollectBoundingBoxUIA(IUIAutomationTextRange *,tagRECT *,int *)
0x1800f5bdd  mov     ebx, eax
0x1800f5bdf  test    eax, eax
0x1800f5be1  js      loc_1800F5FA2
0x1800f5be7  mov     ebx, dword ptr [rsp+180h+var_118]
0x1800f5beb  test    ebx, ebx
0x1800f5bed  jz      loc_1800F5F96
0x1800f5bf3  lea     rcx, [rbp+80h+rc]; lprc
0x1800f5bf7  call    cs:__imp_IsRectEmpty
0x1800f5bfd  test    eax, eax
0x1800f5bff  jnz     loc_1800F5F96
0x1800f5c05  mov     [rbp+80h+var_F0], edi
0x1800f5c08  mov     [rbp+80h+var_EC], r13d
0x1800f5c0c  add     r13d, ebx
0x1800f5c0f  mov     [rbp+80h+var_E8], r13d
0x1800f5c13  movups  xmm0, xmmword ptr [rbp+80h+rc.left]
0x1800f5c17  movdqu  [rbp+80h+var_E4], xmm0
0x1800f5c1c  lea     rdx, [rbp+80h+var_C0]
0x1800f5c20  mov     rcx, r12
0x1800f5c23  call    ?begin@?$vector@UTextUnitInfo@@V?$allocator@UTextUnitInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UTextUnitInfo@@@std@@@std@@@2@XZ; std::vector<TextUnitInfo>::begin(void)
0x1800f5c28  mov     r9, rax
0x1800f5c2b  call    ?size@?$vector@UTextUnitInfo@@V?$allocator@UTextUnitInfo@@@std@@@std@@QEBA_KXZ; std::vector<TextUnitInfo>::size(void)
0x1800f5c30  mov     r8, rax
  ... truncated ...
```
