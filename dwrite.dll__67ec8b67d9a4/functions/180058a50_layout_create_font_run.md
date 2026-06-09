# layout::create_font_run

- ea: `0x180058a50`
- end: `0x180059b04`
- name: `layout::create_font_run`
- size: `4276`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID Address)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054300`
- `0x18005d420`

## callees

- `0x180026e10`
- `0x180026eb0`
- `0x180026f50`
- `0x180027000`
- `0x1800270a0`
- `0x180046980`
- `0x180046d70`
- `0x1800471a0`
- `0x180058a50`
- `0x18005a0d0`
- `0x18005a800`
- `0x1800dc910`
- `0x180115c30`
- `0x18021e1b6`
- `0x18021e1ce`
- `0x18021e1da`
- `0x180316190`
- `0x180316232`
- `0x1803168c1`
- `0x180316ae0`
- `0x180316d00`
- `0x180316ee0`
- `0x180319b70`
- `0x180319c30`

## import_xrefs

- `oleaut32!GetErrorInfo` at `0x1800590b5`
- `oleaut32!GetErrorInfo` at `0x1800590e9`
- `oleaut32!GetErrorInfo` at `0x180059118`
- `oleaut32!GetErrorInfo` at `0x180059146`
- `oleaut32!GetErrorInfo` at `0x180059262`
- `oleaut32!GetErrorInfo` at `0x18005927f`
- `oleaut32!GetErrorInfo` at `0x1800593f2`
- `oleaut32!GetErrorInfo` at `0x180059462`
- `oleaut32!GetErrorInfo` at `0x1800590b5`
- `oleaut32!GetErrorInfo` at `0x1800590e9`
- `oleaut32!GetErrorInfo` at `0x180059118`
- `oleaut32!GetErrorInfo` at `0x180059146`
- `oleaut32!GetErrorInfo` at `0x180059262`
- `oleaut32!GetErrorInfo` at `0x18005927f`
- `oleaut32!GetErrorInfo` at `0x1800593f2`
- `oleaut32!GetErrorInfo` at `0x180059462`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18005999a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18005999a`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
IErrorInfo **__fastcall layout::create_font_run(
        IErrorInfo **a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        IErrorInfo *Address)
{
  struct IErrorInfoVtbl *v6; // r13
  HRESULT (__stdcall **v9)(IErrorInfo *, const IID *const, void **); // rcx
  __int64 v10; // rdx
  int is_zero_slow_path; // eax
  struct IErrorInfoVtbl *lpVtbl; // rbx
  struct IErrorInfoVtbl *v13; // r12
  unsigned __int64 v14; // rsi
  HRESULT (__stdcall *v15)(IErrorInfo *, const IID *const, void **); // rcx
  struct IErrorInfoVtbl *v16; // rdx
  unsigned __int64 v17; // r15
  __int64 v18; // r14
  __int64 v19; // rcx
  ULONG (__stdcall *AddRef)(IErrorInfo *); // rax
  __int64 v21; // rcx
  struct IErrorInfoVtbl *v22; // rbx
  unsigned __int64 v23; // rbx
  struct IErrorInfoVtbl *v24; // r12
  HRESULT (__stdcall **v25)(IErrorInfo *, const IID *const, void **); // r14
  unsigned __int64 v26; // rax
  HRESULT (__stdcall **v27)(IErrorInfo *, const IID *const, void **); // rsi
  size_t v28; // rbx
  struct IErrorInfoVtbl *v29; // rcx
  size_t v30; // r8
  unsigned __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned __int64 v34; // r9
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm3
  char *v38; // r10
  unsigned __int64 v39; // r9
  HRESULT (__stdcall *v40)(IErrorInfo *, const IID *const, void **); // r11
  unsigned __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  unsigned __int64 v44; // r9
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm3
  char *v48; // r10
  unsigned __int64 v49; // r9
  HRESULT (__stdcall *v50)(IErrorInfo *, const IID *const, void **); // r11
  HRESULT (__stdcall **v51)(IErrorInfo *, const IID *const, void **); // r15
  HRESULT (__stdcall *v52)(IErrorInfo *, const IID *const, void **); // rcx
  __int64 v53; // r12
  int v54; // eax
  unsigned __int64 v55; // r14
  unsigned __int64 v56; // rdx
  IErrorInfo *v57; // rdi
  IErrorInfo *v58; // rbx
  HRESULT (__stdcall *v59)(IErrorInfo *, const IID *const, void **); // rcx
  int v60; // eax
  IErrorInfo *v61; // rdi
  int v62; // eax
  __int64 v63; // rsi
  IErrorInfo *GetHelpFile; // r15
  struct IErrorInfoVtbl *v65; // rax
  int v66; // eax
  IErrorInfo *v67; // rsi
  size_t v68; // r15
  char v69; // al
  bool v70; // r14
  bool v71; // si
  int v72; // eax
  int v73; // eax
  void (*v74)(void); // rax
  size_t v75; // rbx
  __int64 v76; // rcx
  __int64 v77; // r15
  __int64 v78; // rdi
  IErrorInfo *v79; // rsi
  void *v80; // r13
  __int64 v81; // rdx
  __int64 v82; // r8
  unsigned __int64 v83; // rsi
  _DWORD *v84; // rdx
  __int64 v85; // rcx
  IErrorInfo *v86; // rdi
  unsigned __int64 v87; // rax
  __int64 v88; // r15
  unsigned __int64 v89; // rcx
  unsigned __int64 v90; // rax
  unsigned __int64 v91; // rcx
  HRESULT (__stdcall **v92)(IErrorInfo *, const IID *const, void **); // r14
  __int64 v93; // rdx
  __int64 v94; // r8
  __int128 v95; // xmm1
  _DWORD *v96; // r8
  __int64 v97; // rax
  __int64 v98; // r9
  int v99; // xmm0_4
  struct IErrorInfoVtbl *v100; // rsi
  struct IErrorInfoVtbl *v101; // rax
  HRESULT (__stdcall *GetGUID)(IErrorInfo *, GUID *); // rcx
  ULONG (__stdcall *Release)(IErrorInfo *); // rdx
  HRESULT (__stdcall *QueryInterface)(IErrorInfo *, const IID *const, void **); // rax
  HRESULT (__stdcall **v105)(IErrorInfo *, const IID *const, void **); // rcx
  __int128 v106; // xmm0
  __int128 v107; // xmm1
  __int128 v108; // xmm2
  struct IErrorInfoVtbl *v109; // rdi
  struct IErrorInfoVtbl *v110; // rbx
  struct IErrorInfoVtbl *v111; // rsi
  struct IErrorInfoVtbl *v112; // rax
  __int64 v113; // rcx
  __int128 v114; // xmm0
  __int128 v115; // xmm1
  __int128 v116; // xmm2
  __int64 v117; // r15
  __int64 v118; // r14
  __int64 v119; // r15
  __int64 v120; // r14
  int v121; // xmm6_4
  __int64 v122; // rdi
  IErrorInfo **result; // rax
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-58h] BYREF
  __int64 v125; // [rsp+30h] [rbp-50h]
  __int64 v126; // [rsp+38h] [rbp-48h]
  IErrorInfo *v127; // [rsp+128h] [rbp+A8h] BYREF
  IErrorInfo **v128; // [rsp+130h] [rbp+B0h]
  IErrorInfo *v129; // [rsp+138h] [rbp+B8h]
  IErrorInfo *v130; // [rsp+140h] [rbp+C0h]
  __int64 v131; // [rsp+148h] [rbp+C8h]
  __int128 v132; // [rsp+150h] [rbp+D0h]
  __int128 v133; // [rsp+160h] [rbp+E0h]
  __int128 v134; // [rsp+170h] [rbp+F0h]
  __int128 v135; // [rsp+180h] [rbp+100h]
  HRESULT (__stdcall *v136)(IErrorInfo *, const IID *const, void **); // [rsp+190h] [rbp+110h]
  size_t Size; // [rsp+198h] [rbp+118h]
  IErrorInfo *v138; // [rsp+1A0h] [rbp+120h]
  IErrorInfo *v139; // [rsp+1A8h] [rbp+128h]
  unsigned int v140; // [rsp+1B4h] [rbp+134h] BYREF
  __int64 v141; // [rsp+1B8h] [rbp+138h]
  IErrorInfo *v142; // [rsp+1C0h] [rbp+140h]
  int v143; // [rsp+1C8h] [rbp+148h]
  _BYTE v144[12]; // [rsp+1CCh] [rbp+14Ch]
  void *Buf2; // [rsp+1D8h] [rbp+158h]
  IErrorInfo *v146; // [rsp+1E0h] [rbp+160h]
  struct IErrorInfoVtbl *v147; // [rsp+1E8h] [rbp+168h]
  __int64 v148; // [rsp+1F0h] [rbp+170h]
  IErrorInfo *v149; // [rsp+1F8h] [rbp+178h]
  HRESULT (__stdcall **v150)(IErrorInfo *, const IID *const, void **); // [rsp+200h] [rbp+180h]
  IErrorInfo *v151; // [rsp+208h] [rbp+188h] BYREF
  char v152; // [rsp+217h] [rbp+197h]
  __int64 v153; // [rsp+218h] [rbp+198h]

  v153 = -2;
  v131 = a2;
  v9 = (HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))(a3 + 48);
  v149 = *(IErrorInfo **)(a3 + 48);
  if ( !v149 )
    v9 = 0;
  v150 = v9;
  Buf2 = *(void **)(a3 + 32);
  v10 = *(_QWORD *)(a3 + 40);
  *(_QWORD *)v144 = *(_QWORD *)(a3 + 84);
  *(_DWORD *)&v144[8] = *(_DWORD *)(a3 + 92);
  if ( _InterlockedCompareExchange8((volatile signed __int8 *)Address, 1, 0) )
  {
    v117 = v10;
    v118 = a3;
    std::sys::sync::mutex::futex::Mutex::lock_contended(Address);
    a3 = v118;
    v10 = v117;
  }
  if ( 2 * qword_1804B1950 )
  {
    v119 = v10;
    v120 = a3;
    is_zero_slow_path = std::panicking::panic_count::is_zero_slow_path();
    a3 = v120;
    v10 = v119;
    LOBYTE(is_zero_slow_path) = is_zero_slow_path ^ 1;
  }
  else
  {
    is_zero_slow_path = 0;
  }
  if ( BYTE1(Address->lpVtbl) )
  {
    pperrinfo = Address;
    LOBYTE(v125) = is_zero_slow_path;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&pperrinfo,
      (unsigned int)&off_1803373E8,
      (__int64)&off_1803389A8);
  }
  v141 = a3;
  v128 = a1;
  v143 = is_zero_slow_path;
  v129 = Address + 1;
  v130 = Address + 4;
  lpVtbl = Address[5].lpVtbl;
  v13 = (struct IErrorInfoVtbl *)((char *)lpVtbl + 8 * (__int64)Address[6].lpVtbl);
  v148 = v10;
  Size = 2 * v10;
  v14 = 0;
  do
  {
    while ( 1 )
    {
      do
      {
        do
        {
          while ( 1 )
          {
            if ( lpVtbl == v13 )
            {
              if ( v149 )
              {
                v51 = v150;
                v52 = *v150;
                v53 = v141;
              }
              else
              {
                v65 = (struct IErrorInfoVtbl *)(*(__int64 (__fastcall **)(_QWORD, bool))(**(_QWORD **)(v131 + 16) + 40LL))(
                                                 *(_QWORD *)(v131 + 16),
                                                 a5 == 0);
                if ( !v65 )
                  core::option::unwrap_failed(&off_180338A38);
                v6 = v65;
                v151 = 0;
                v66 = (*(__int64 (__fastcall **)(struct IErrorInfoVtbl *, int *, IErrorInfo **))v65->QueryInterface)(
                        v65,
                        &dword_1803B36F4,
                        &v151);
                if ( v66 < 0 )
                {
                  v63 = (unsigned int)v66;
                  pperrinfo = 0;
                  GetErrorInfo(0, &pperrinfo);
                  GetHelpFile = pperrinfo;
                  v58 = Address;
                  v53 = v141;
                  goto LABEL_96;
                }
                v53 = v141;
                if ( !v151 )
                {
                  pperrinfo = 0;
                  GetErrorInfo(0, &pperrinfo);
                  GetHelpFile = pperrinfo;
                  v63 = 2147500035LL;
                  v58 = Address;
                  goto LABEL_96;
                }
                v127 = v151;
                v67 = v151;
                (*((void (__fastcall **)(struct IErrorInfoVtbl *))v6->QueryInterface + 2))(v6);
                v52 = (HRESULT (__stdcall *)(IErrorInfo *, const IID *const, void **))v67;
                v51 = (HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))&v127;
                v6 = (struct IErrorInfoVtbl *)v67;
              }
              v140 = 0;
              LODWORD(v151) = 0;
              v54 = (*(__int64 (__fastcall **)(HRESULT (__stdcall *)(IErrorInfo *, const IID *const, void **), void *, unsigned int *, IErrorInfo **))(*(_QWORD *)v52 + 40LL))(
                      v52,
                      Buf2,
                      &v140,
                      &v151);
              if ( v54 < 0 )
              {
                v63 = (unsigned int)v54;
                pperrinfo = 0;
                GetErrorInfo(0, &pperrinfo);
                GetHelpFile = pperrinfo;
                v58 = Address;
                if ( v149 )
                  goto LABEL_97;
              }
              else
              {
                v55 = a4;
                v56 = ((unsigned __int64)v140 << 32) + 1;
                v57 = 0;
                if ( !(_DWORD)v151 )
                  v56 = 0;
                v58 = Address;
                if ( !(_BYTE)v56 )
                {
LABEL_115:
                  if ( v149 )
                  {
                    v74 = *(void (**)(void))(*(_QWORD *)*v150 + 8LL);
                    v150 = (HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))*v150;
                    v74();
                  }
                  else
                  {
                    (*((void (__fastcall **)(struct IErrorInfoVtbl *))v6->QueryInterface + 2))(v6);
                    v150 = 0;
                  }
                  v75 = Size;
                  v149 = v57;
                  if ( v148 < 0 || Size > 0x7FFFFFFFFFFFFFFELL )
                  {
                    v76 = 0;
                    goto LABEL_120;
                  }
                  if ( Size )
                  {
                    v77 = std::sys::alloc::windows::process_heap_alloc(0, Size);
                    v78 = v148;
                    v79 = (IErrorInfo *)v148;
                    if ( !v77 )
                    {
                      v76 = 2;
LABEL_120:
                      alloc::raw_vec::handle_error(v76, v75, &off_180348EC0);
                    }
                  }
                  else
                  {
                    v77 = 2;
                    v79 = 0;
                    v78 = v148;
                  }
                  memcpy_0((void *)v77, Buf2, v75);
                  pperrinfo = v79;
                  v125 = v77;
                  v126 = v78;
                  v80 = (void *)widestring::ucstring::U16CString::from_vec_unchecked_alloc::vec::Vec_u16_alloc::alloc::Global___(&pperrinfo);
                  v82 = v81;
                  v83 = a5;
                  v84 = (_DWORD *)(8 * a5);
                  v148 = v82;
                  if ( a5 >> 61 != 0 || 8 * a5 > 0x7FFFFFFFFFFFFFFCLL )
                  {
                    Buf2 = v80;
                    v85 = 0;
                    goto LABEL_127;
                  }
                  v86 = v149;
                  if ( v84 )
                  {
                    v87 = std::sys::alloc::windows::process_heap_alloc(0, v84);
                    if ( !v87 )
                    {
                      Buf2 = v80;
                      v85 = 4;
                      v84 = (_DWORD *)(8 * a5);
LABEL_127:
                      alloc::raw_vec::handle_error(v85, v84, &off_180342F70);
                    }
                    v88 = v87;
                    v83 = a5;
                    if ( a5 )
                    {
                      v89 = a5 - 1;
                      if ( a5 - 1 < 0xA )
                        goto LABEL_135;
                      if ( a5 < v89 )
                        v89 = a5;
                      if ( v55 < v87 + 8 * v89 + 8 && v87 < v55 + 8 * v89 + 8 )
                      {
LABEL_135:
                        v90 = 0;
                        v91 = a5;
                        v84 = (_DWORD *)v55;
                      }
                      else
                      {
                        v93 = 4;
                        if ( (a5 & 3) != 0 )
                          v93 = a5 & 3;
                        v90 = a5 - v93;
                        v91 = v93;
                        v84 = (_DWORD *)(v55 + 8 * (a5 - v93));
                        v94 = 0;
                        do
                        {
                          v95 = *(_OWORD *)(v55 + 8 * v94 + 16);
                          *(_OWORD *)(v88 + 8 * v94) = *(_OWORD *)(v55 + 8 * v94);
                          *(_OWORD *)(v88 + 8 * v94 + 16) = v95;
                          v94 += 4;
                        }
                        while ( v90 != v94 );
                      }
                      v96 = (_DWORD *)(v55 + 8 * a5);
                      v97 = v88 + 8 * v90 + 4;
                      v98 = 0;
                      v92 = v150;
                      do
                      {
                        if ( v84 == v96 )
                          break;
                        v99 = v84[1];
                        *(_DWORD *)(v97 + 8 * v98 - 4) = *v84;
                        *(_DWORD *)(v97 + 8 * v98++) = v99;
                        v84 += 2;
                      }
                      while ( v91 != v98 );
                      goto LABEL_145;
                    }
                  }
                  else
                  {
                    v88 = 4;
                  }
                  v92 = v150;
LABEL_145:
                  if ( v86 )
                    ((void (__fastcall *)(IErrorInfo *, _DWORD *))v86->lpVtbl->AddRef)(v86, v84);
                  else
                    v86 = 0;
                  *((_QWORD *)&v134 + 1) = v92;
                  *((_QWORD *)&v133 + 1) = v80;
                  *(_QWORD *)&v134 = v148;
                  *(_QWORD *)&v132 = v83;
                  *((_QWORD *)&v132 + 1) = v88;
                  *(_QWORD *)&v133 = v83;
                  *((_QWORD *)&v135 + 1) = *(_QWORD *)v144;
                  LODWORD(v136) = *(_DWORD *)&v144[8];
                  *(_QWORD *)&v135 = v86;
                  v100 = Address[6].lpVtbl;
                  if ( v100 == (struct IErrorInfoVtbl *)4 )
                  {
                    v101 = Address[5].lpVtbl;
                    GetGUID = v101->GetGUID;
                    Release = v101->Release;
                    *(_OWORD *)&v101->AddRef = *(_OWORD *)&v101->QueryInterface;
                    v101->GetGUID = (HRESULT (__stdcall *)(IErrorInfo *, GUID *))Release;
                    v101->QueryInterface = (HRESULT (__stdcall *)(IErrorInfo *, const IID *const, void **))GetGUID;
                    if ( !Address[6].lpVtbl )
                    {
                      v152 = 1;
                      core::panicking::panic_bounds_check(0, 0, &off_1803389F0);
                    }
                    QueryInterface = Address[5].lpVtbl->QueryInterface;
                    v148 = (__int64)Address[3].lpVtbl;
                    Buf2 = QueryInterface;
                    if ( (unsigned __int64)QueryInterface >= v148 )
                      core::panicking::panic_bounds_check(QueryInterface, v148, &off_180338A08);
                    v150 = &Address[2].lpVtbl->QueryInterface + 9 * (_QWORD)QueryInterface;
                    core::ptr::drop_in_place_layout::recent_font_cache::Entry_();
                    v105 = v150;
                    v150[8] = v136;
                    v106 = v132;
                    v107 = v133;
                    v108 = v134;
                    *((_OWORD *)v105 + 3) = v135;
                    *((_OWORD *)v105 + 2) = v108;
                    *((_OWORD *)v105 + 1) = v107;
                    *(_OWORD *)v105 = v106;
                    v58 = Address;
                  }
                  else
                  {
                    v109 = Address[3].lpVtbl;
                    if ( v100 == Address[4].lpVtbl )
                    {
                      v152 = 1;
                      alloc::raw_vec::RawVec_usize_alloc::alloc::Global_::grow_one_usize_alloc::alloc::Global_(v130);
                    }
                    v110 = Address[5].lpVtbl;
                    if ( v100 )
                      memmove_0(&v110->AddRef, Address[5].lpVtbl, 8LL * (_QWORD)v100);
                    v110->QueryInterface = (HRESULT (__stdcall *)(IErrorInfo *, const IID *const, void **))v109;
                    Address[6].lpVtbl = (struct IErrorInfoVtbl *)((char *)&v100->QueryInterface + 1);
                    v111 = Address[3].lpVtbl;
                    v53 = v141;
                    if ( v111 == Address[1].lpVtbl )
                      alloc::raw_vec::RawVec_layout::recent_font_cache::Entry_alloc::alloc::Global_::grow_one_layout::recent_font_cache::Entry_alloc::alloc::Global_(v129);
                    v58 = Address;
                    v112 = Address[2].lpVtbl;
                    v113 = 9LL * (_QWORD)v111;
                    *((_QWORD *)&v112[1].QueryInterface + v113) = v136;
                    v114 = v132;
                    v115 = v133;
                    v116 = v134;
                    *(_OWORD *)(&v112->GetHelpFile + v113) = v135;
                    *(_OWORD *)(&v112->GetSource + v113) = v116;
                    *(_OWORD *)(&v112->Release + v113) = v115;
                    *(_OWORD *)(&v112->QueryInterface + v113) = v114;
                    Address[3].lpVtbl = (struct IErrorInfoVtbl *)((char *)&v111->QueryInterface + 1);
                  }
                  GetHelpFile = v149;
                  if ( !(_BYTE)v143
                    && 2 * qword_1804B1950
                    && !(unsigned __int8)std::panicking::panic_count::is_zero_slow_path() )
                  {
                    BYTE1(v58->lpVtbl) = 1;
                  }
                  v63 = 0;
                  goto LABEL_99;
                }
                v59 = *v51;
                v151 = 0;
                v60 = (*(__int64 (__fastcall **)(HRESULT (__stdcall *)(IErrorInfo *, const IID *const, void **), unsigned __int64, IErrorInfo **))(*(_QWORD *)v59 + 32LL))(
                        v59,
                        HIDWORD(v56),
                        &v151);
                if ( v60 < 0 )
                {
                  v63 = (unsigned int)v60;
                }
                else
                {
                  v61 = v151;
                  if ( v151 )
                  {
                    if ( a5 )
                    {
                      v151 = 0;
                      v62 = ((__int64 (__fastcall *)(IErrorInfo *, int *, IErrorInfo **))v61->lpVtbl->QueryInterface)(
                              v61,
                              &dword_1803B36C4,
                              &v151);
                      if ( v62 < 0 )
                      {
                        v63 = (unsigned int)v62;
                        pperrinfo = 0;
                        GetErrorInfo(0, &pperrinfo);
                        GetHelpFile = pperrinfo;
                        goto LABEL_95;
                      }
                      if ( !v151 )
                      {
                        pperrinfo = 0;
                        GetErrorInfo(0, &pperrinfo);
                        GetHelpFile = pperrinfo;
                        v63 = 2147500035LL;
                        goto LABEL_95;
                      }
                      v146 = v61;
                      v147 = v6;
                      v142 = v151;
                      dwrite::font_family::IDWriteFontFamily2::get_matching_fonts(&pperrinfo, v151, v55, a5);
                      v63 = (unsigned int)v125;
                      GetHelpFile = pperrinfo;
                      if ( (_DWORD)v125 )
                      {
                        v6 = v147;
                        v61 = v146;
LABEL_94:
                        ((void (__fastcall *)(IErrorInfo *))v142->lpVtbl->Release)(v142);
LABEL_95:
                        ((void (__fastcall *)(IErrorInfo *))v61->lpVtbl->Release)(v61);
                        if ( v149 )
                          goto LABEL_97;
                        goto LABEL_96;
                      }
                      v138 = pperrinfo;
                      dwrite::font_list::IDWriteFontList1::get_font_face_reference(&pperrinfo, pperrinfo, 0);
                      v63 = (unsigned int)v125;
                      GetHelpFile = pperrinfo;
                      if ( (_DWORD)v125 )
                      {
LABEL_93:
                        v6 = v147;
                        v61 = v146;
                        ((void (__fastcall *)(IErrorInfo *))v138->lpVtbl->Release)(v138);
                        goto LABEL_94;
                      }
                      v139 = pperrinfo;
                      dwrite::font_face_reference::IDWriteFontFaceReference::create_font_face(&pperrinfo, pperrinfo);
                      v63 = (unsigned int)v125;
                      GetHelpFile = pperrinfo;
                      if ( (_DWORD)v125 )
                      {
                        ((void (__fastcall *)(IErrorInfo *))v139->lpVtbl->Release)(v139);
                        goto LABEL_93;
                      }
                      v151 = 0;
                      v73 = ((__int64 (__fastcall *)(IErrorInfo *, int *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                              pperrinfo,
                              &dword_1803B3704,
                              &v151);
                      v6 = v147;
                      if ( v73 < 0 || (v57 = v151) == 0 )
                      {
                        pperrinfo = 0;
                        GetErrorInfo(0, &pperrinfo);
                        if ( pperrinfo )
                          ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
                        v57 = 0;
                      }
                      ((void (__fastcall *)(IErrorInfo *))GetHelpFile->lpVtbl->Release)(GetHelpFile);
                      ((void (__fastcall *)(IErrorInfo *))v139->lpVtbl->Release)(v139);
                      GetHelpFile = v138;
                      goto LABEL_114;
                    }
                    v147 = v6;
                    v146 = v151;
                    dwrite::font_family::IDWriteFontFamily::get_first_matching_font(
                      (unsigned int)&pperrinfo,
                      (_DWORD)v151,
                      *(_DWORD *)v144,
                      *(_DWORD *)&v144[4],
                      *(_DWORD *)&v144[8]);
                    v63 = (unsigned int)v125;
                    GetHelpFile = pperrinfo;
                    if ( !(_DWORD)v125 )
                    {
                      v142 = pperrinfo;
                      dwrite::font::IDWriteFont::create_font_face(&pperrinfo, pperrinfo);
                      v63 = (unsigned int)v125;
                      GetHelpFile = pperrinfo;
                      if ( !(_DWORD)v125 )
                      {
                        v151 = 0;
                        v72 = ((__int64 (__fastcall *)(IErrorInfo *, int *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                                pperrinfo,
                                &dword_1803B3704,
                                &v151);
                        v6 = v147;
                        if ( v72 < 0 || (v57 = v151) == 0 )
                        {
                          pperrinfo = 0;
                          GetErrorInfo(0, &pperrinfo);
                          if ( pperrinfo )
                            ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
                          v57 = 0;
                        }
LABEL_114:
                        ((void (__fastcall *)(IErrorInfo *))GetHelpFile->lpVtbl->Release)(GetHelpFile);
                        ((void (__fastcall *)(IErrorInfo *))v142->lpVtbl->Release)(v142);
                        ((void (__fastcall *)(IErrorInfo *))v146->lpVtbl->Release)(v146);
                        goto LABEL_115;
                      }
                      ((void (__fastcall *)(IErrorInfo *))v142->lpVtbl->Release)(v142);
                    }
                    v6 = v147;
                    v61 = v146;
                    goto LABEL_95;
                  }
                  v63 = 2147549183LL;
                }
                pperrinfo = 0;
                GetErrorInfo(0, &pperrinfo);
                GetHelpFile = pperrinfo;
                if ( v149 )
                  goto LABEL_97;
              }
LABEL_96:
              (*((void (__fastcall **)(struct IErrorInfoVtbl *))v6->QueryInterface + 2))(v6);
              goto LABEL_97;
            }
            v15 = lpVtbl->QueryInterface;
            v16 = Address[3].lpVtbl;
            if ( (char *)lpVtbl->QueryInterface >= (char *)v16 )
              core::panicking::panic_bounds_check(v15, v16, &off_180338A20);
            v17 = v14;
            lpVtbl = (struct IErrorInfoVtbl *)((char *)lpVtbl + 8);
            ++v14;
            v6 = Address[2].lpVtbl;
            v18 = 9LL * (_QWORD)v15;
            v19 = *((_QWORD *)&v6->GetDescription + 9 * (_QWORD)v15);
            if ( v19 )
              break;
            if ( !v149 )
              goto LABEL_15;
          }
        }
        while ( !v149 || !(unsigned __int8)windows_core::unknown::impl_3::eq(v19, *v150) );
LABEL_15:
        v6 = (struct IErrorInfoVtbl *)((char *)v6 + 8 * v18);
      }
      while ( v6->GetSource != (HRESULT (__stdcall *)(IErrorInfo *, BSTR *))v148
           || memcmp_0(v6->GetGUID, Buf2, Size)
           || v6->Release != (ULONG (__stdcall *)(IErrorInfo *))a5 );
      if ( !a5 )
        break;
      AddRef = v6->AddRef;
      v21 = 0;
      while ( *((float *)AddRef + 2 * v21 + 1) == *(float *)(a4 + 8 * v21 + 4)
           && *((_DWORD *)AddRef + 2 * v21) == *(_DWORD *)(a4 + 8 * v21) )
      {
        if ( a5 == ++v21 )
          goto LABEL_26;
      }
    }
  }
  while ( LODWORD(v6->GetHelpContext) != *(_DWORD *)v144
       || *(HRESULT (__stdcall **)(IErrorInfo *, DWORD *))((char *)&v6->GetHelpContext + 4) != *(HRESULT (__stdcall **)(IErrorInfo *, DWORD *))&v144[4] );
LABEL_26:
  v22 = Address[6].lpVtbl;
  if ( (unsigned __int64)v22 < v17 )
    core::panicking::panic(
      "assertion failed: mid <= self.len()AlignmentErrorDecodeErrorSizeErrorAlignmentSizerust\\shaping\\src\\caching.rs",
      35,
      &off_18033B4F0);
  v23 = (unsigned __int64)v22 - v17;
  if ( v17 != 0 && v23 != 0 )
  {
    v24 = Address[5].lpVtbl;
    v25 = &v24->QueryInterface + v17;
    v26 = v17;
    if ( v23 < v17 )
      v26 = v23;
    if ( v26 >= 0x21 )
    {
      do
      {
        if ( v17 >= v23 )
        {
          v41 = v23 & 0xFFFFFFFFFFFFFFFCuLL;
          v42 = -8LL * v23;
          v43 = (__int64)&v25[-v23 + 2];
          do
          {
            v44 = 0;
            if ( v23 < 4 )
              goto LABEL_47;
            do
            {
              v45 = *(_OWORD *)(v43 + 8 * v44 - 16);
              v46 = *(_OWORD *)(v43 + 8 * v44);
              v47 = *(_OWORD *)&v25[v44 + 2];
              *(_OWORD *)(v43 + 8 * v44 - 16) = *(_OWORD *)&v25[v44];
              *(_OWORD *)(v43 + 8 * v44) = v47;
              *(_OWORD *)&v25[v44] = v45;
              *(_OWORD *)&v25[v44 + 2] = v46;
              v44 += 4LL;
            }
            while ( v41 != v44 );
            v44 = v23 & 0xFFFFFFFFFFFFFFFCuLL;
            if ( v23 != v41 )
            {
LABEL_47:
              v48 = (char *)&v25[v44];
              v49 = v44 - v23;
              do
              {
                v50 = v25[v49];
                v25[v49] = *(HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))v48;
                *(_QWORD *)v48 = v50;
                v48 += 8;
                ++v49;
              }
              while ( v49 );
            }
            v25 = (HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))((char *)v25 + v42);
            v17 -= v23;
            v43 += v42;
          }
          while ( v17 >= v23 );
        }
        else
        {
          v31 = v17 & 0xFFFFFFFFFFFFFFFCuLL;
          v32 = 8 * v17;
          v33 = (__int64)&v25[-v17 + 2];
          do
          {
            v34 = 0;
            if ( v17 < 4 )
              goto LABEL_39;
            do
            {
              v35 = *(_OWORD *)(v33 + 8 * v34 - 16);
              v36 = *(_OWORD *)(v33 + 8 * v34);
              v37 = *(_OWORD *)&v25[v34 + 2];
              *(_OWORD *)(v33 + 8 * v34 - 16) = *(_OWORD *)&v25[v34];
              *(_OWORD *)(v33 + 8 * v34) = v37;
              *(_OWORD *)&v25[v34] = v35;
              *(_OWORD *)&v25[v34 + 2] = v36;
              v34 += 4LL;
            }
            while ( v31 != v34 );
            v34 = v17 & 0xFFFFFFFFFFFFFFFCuLL;
            if ( v17 != v31 )
            {
LABEL_39:
              v38 = (char *)&v25[v34];
              v39 = v34 - v17;
              do
              {
                v40 = v25[v39];
                v25[v39] = *(HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))v38;
                *(_QWORD *)v38 = v40;
                v38 += 8;
                ++v39;
              }
              while ( v39 );
            }
            v25 = (HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))((char *)v25 + v32);
            v23 -= v17;
            v33 += v32;
          }
          while ( v23 >= v17 );
        }
      }
      while ( v23 && v17 );
    }
    else
    {
      v27 = &v24->QueryInterface + v23;
      if ( v23 >= v17 )
      {
        v68 = 8 * v17;
        memcpy_0(&pperrinfo, Address[5].lpVtbl, v68);
        memmove_0(v24, v25, 8 * v23);
        v29 = (struct IErrorInfoVtbl *)((char *)v24 + 8 * v23);
        v30 = v68;
      }
      else
      {
        v28 = 8 * v23;
        memcpy_0(&pperrinfo, &v24->QueryInterface + v17, v28);
        memmove_0(v27, v24, 8 * v17);
        v29 = v24;
        v30 = v28;
      }
      memcpy_0(v29, &pperrinfo, v30);
    }
  }
  GetHelpFile = (IErrorInfo *)v6->GetHelpFile;
  v63 = 0;
  if ( GetHelpFile )
    ((void (__fastcall *)(HRESULT (__stdcall *)(IErrorInfo *, BSTR *)))GetHelpFile->lpVtbl->AddRef)(v6->GetHelpFile);
  else
    GetHelpFile = 0;
  v58 = Address;
  v53 = v141;
LABEL_97:
  if ( !(_BYTE)v143 && 2 * qword_1804B1950 && !(unsigned __int8)std::panicking::panic_count::is_zero_slow_path() )
    BYTE1(v58->lpVtbl) = 1;
LABEL_99:
  v69 = (char)v58->lpVtbl;
  LOBYTE(v58->lpVtbl) = 0;
  if ( v69 == 2 )
  {
    WakeByAddressSingle(v58);
    if ( (_DWORD)v63 )
      goto LABEL_165;
LABEL_101:
    if ( !GetHelpFile )
      goto LABEL_165;
    v70 = ((unsigned int (__fastcall *)(IErrorInfo *))GetHelpFile->lpVtbl->GetHelpContext)(GetHelpFile) != 0;
    v71 = 0;
  }
  else
  {
    if ( !(_DWORD)v63 )
      goto LABEL_101;
LABEL_165:
    v150 = (HRESULT (__stdcall **)(IErrorInfo *, const IID *const, void **))v63;
    v149 = GetHelpFile;
    GetHelpFile = (IErrorInfo *)layout::text_layout_factory::TextLayoutFactory::get_last_resort_font(v131);
    v71 = *(_QWORD *)(v53 + 64) == 0;
    v70 = 0;
    if ( (_DWORD)v150 && v149 )
    {
      ((void (__fastcall *)(IErrorInfo *))v149->lpVtbl->Release)(v149);
      v70 = 0;
    }
  }
  v121 = *(_DWORD *)(v53 + 80);
  v122 = ((__int64 (__fastcall *)(IErrorInfo *))GetHelpFile->lpVtbl[8].GetSource)(GetHelpFile);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 8LL))(v122);
  result = v128;
  *v128 = GetHelpFile;
  result[1] = (IErrorInfo *)v122;
  *((_DWORD *)result + 4) = v121;
  *((_BYTE *)result + 20) = v70;
  *((_BYTE *)result + 21) = v71;
  return result;
}

```

## disassembly

```asm
0x180058a50  push    rbp
0x180058a51  push    r15
0x180058a53  push    r14
0x180058a55  push    r13
0x180058a57  push    r12
0x180058a59  push    rsi
0x180058a5a  push    rdi
0x180058a5b  push    rbx
0x180058a5c  sub     rsp, 238h
0x180058a63  lea     rbp, [rsp+80h]
0x180058a6b  movaps  [rbp+1F0h+var_50], xmm6
0x180058a72  mov     [rbp+1F0h+var_58], 0FFFFFFFFFFFFFFFEh
0x180058a7d  mov     rdi, r9
0x180058a80  mov     [rbp+1F0h+var_128], rdx
0x180058a87  mov     rbx, rcx
0x180058a8a  mov     rsi, [rbp+1F0h+Address]
0x180058a91  lea     rcx, [r8+30h]
0x180058a95  mov     rax, [r8+30h]
0x180058a99  test    rax, rax
0x180058a9c  mov     [rbp+1F0h+var_78], rax
0x180058aa3  cmovz   rcx, rax
0x180058aa7  mov     [rbp+1F0h+var_70], rcx
0x180058aae  mov     rax, [r8+20h]
0x180058ab2  mov     [rbp+1F0h+Buf2], rax
0x180058ab9  mov     rdx, [r8+28h]
0x180058abd  mov     eax, [r8+54h]
0x180058ac1  mov     dword ptr [rbp+1F0h+var_A4], eax
0x180058ac7  mov     eax, [r8+58h]
0x180058acb  mov     dword ptr [rbp+1F0h+var_A4+4], eax
0x180058ad1  mov     eax, [r8+5Ch]
0x180058ad5  mov     dword ptr [rbp+1F0h+var_A4+8], eax
0x180058adb  mov     cl, 1
0x180058add  xor     eax, eax
0x180058adf  lock cmpxchg [rsi], cl
0x180058ae3  jnz     loc_180059932
0x180058ae9  mov     rax, cs:qword_1804B1950
0x180058af0  shl     rax, 1
0x180058af3  test    rax, rax
0x180058af6  jnz     loc_18005994B
0x180058afc  xor     eax, eax
0x180058afe  movzx   ecx, byte ptr [rsi+1]
0x180058b02  test    cl, cl
0x180058b04  jnz     loc_180059963
0x180058b0a  mov     [rbp+1F0h+var_B8], r8
0x180058b11  mov     [rbp+1F0h+var_140], rbx
0x180058b18  mov     [rbp+1F0h+var_A8], eax
0x180058b1e  lea     rax, [rsi+8]
0x180058b22  mov     [rbp+1F0h+var_138], rax
0x180058b29  lea     rax, [rsi+20h]
0x180058b2d  mov     [rbp+1F0h+var_130], rax
0x180058b34  mov     rbx, [rsi+28h]
0x180058b38  mov     rax, [rsi+30h]
0x180058b3c  lea     r12, [rbx+rax*8]
0x180058b40  mov     [rbp+1F0h+var_80], rdx
0x180058b47  lea     rax, [rdx+rdx]
0x180058b4b  mov     [rbp+1F0h+Size], rax
0x180058b52  xor     esi, esi
0x180058b54  jmp     short loc_180058B6A
0x180058b60  cmp     [rbp+1F0h+var_78], 0
0x180058b68  jz      short loc_180058BC3
0x180058b6a  cmp     rbx, r12
0x180058b6d  jz      loc_180058EA7
0x180058b73  mov     rcx, [rbx]
0x180058b76  mov     rax, [rbp+1F0h+Address]
0x180058b7d  mov     rdx, [rax+18h]
0x180058b81  cmp     rcx, rdx
0x180058b84  jnb     loc_180059A9B
0x180058b8a  mov     r15, rsi
0x180058b8d  add     rbx, 8
0x180058b91  inc     rsi
0x180058b94  mov     r13, [rax+10h]
0x180058b98  lea     r14, [rcx+rcx*8]
0x180058b9c  mov     rcx, [r13+r14*8+28h]
0x180058ba1  test    rcx, rcx
0x180058ba4  jz      short loc_180058B60
0x180058ba6  cmp     [rbp+1F0h+var_78], 0
0x180058bae  jz      short loc_180058B6A
0x180058bb0  mov     rax, [rbp+1F0h+var_70]
0x180058bb7  mov     rdx, [rax]
0x180058bba  call    windows_core__unknown__impl$3__eq
0x180058bbf  test    al, al
0x180058bc1  jz      short loc_180058B6A
0x180058bc3  lea     r13, [r13+r14*8+0]
0x180058bc8  mov     rax, [rbp+1F0h+var_80]
0x180058bcf  cmp     [r13+20h], rax
0x180058bd3  jnz     short loc_180058B6A
0x180058bd5  mov     rcx, [r13+18h]; Buf1
0x180058bd9  mov     rdx, [rbp+1F0h+Buf2]; Buf2
0x180058be0  mov     r8, [rbp+1F0h+Size]; Size
0x180058be7  call    memcmp_0
0x180058bec  test    eax, eax
0x180058bee  jnz     loc_180058B6A
0x180058bf4  mov     rax, [rbp+1F0h+arg_20]
0x180058bfb  cmp     [r13+10h], rax
0x180058bff  jnz     loc_180058B6A
0x180058c05  cmp     [rbp+1F0h+arg_20], 0
0x180058c0d  jz      short loc_180058C51
0x180058c0f  mov     rax, [r13+8]
0x180058c13  xor     ecx, ecx
0x180058c15  nop     word ptr [rax+rax+00000000h]
0x180058c20  movss   xmm0, dword ptr [rax+rcx*8+4]
0x180058c26  ucomiss xmm0, dword ptr [rdi+rcx*8+4]
0x180058c2b  jnz     loc_180058B6A
0x180058c31  jp      loc_180058B6A
0x180058c37  mov     edx, [rdi+rcx*8]
0x180058c3a  cmp     [rax+rcx*8], edx
0x180058c3d  jnz     loc_180058B6A
0x180058c43  inc     rcx
0x180058c46  cmp     [rbp+1F0h+arg_20], rcx
0x180058c4d  jnz     short loc_180058C20
0x180058c4f  jmp     short loc_180058C81
0x180058c51  mov     eax, dword ptr [rbp+1F0h+var_A4]
0x180058c57  cmp     [r13+38h], eax
0x180058c5b  jnz     loc_180058B6A
0x180058c61  mov     eax, dword ptr [rbp+1F0h+var_A4+4]
0x180058c67  cmp     [r13+3Ch], eax
0x180058c6b  jnz     loc_180058B6A
0x180058c71  mov     eax, dword ptr [rbp+1F0h+var_A4+8]
0x180058c77  cmp     [r13+40h], eax
0x180058c7b  jnz     loc_180058B6A
0x180058c81  mov     rax, [rbp+1F0h+Address]
0x180058c88  mov     rbx, [rax+30h]
0x180058c8c  cmp     rbx, r15
0x180058c8f  jb      loc_180059A81
0x180058c95  test    r15, r15
0x180058c98  setz    al
0x180058c9b  sub     rbx, r15
0x180058c9e  setz    cl
0x180058ca1  or      cl, al
0x180058ca3  jnz     loc_180059199
0x180058ca9  mov     rax, [rbp+1F0h+Address]
0x180058cb0  mov     r12, [rax+28h]
0x180058cb4  lea     r14, [r12+r15*8]
0x180058cb8  cmp     rbx, r15
0x180058cbb  mov     rax, r15
0x180058cbe  cmovb   rax, rbx
0x180058cc2  cmp     rax, 21h ; '!'
0x180058cc6  jnb     short loc_180058D10
0x180058cc8  lea     rsi, [r12+rbx*8]
0x180058ccc  cmp     rbx, r15
0x180058ccf  jnb     loc_180059163
0x180058cd5  shl     rbx, 3
0x180058cd9  lea     rdi, [rbp+1F0h+pperrinfo]
0x180058cdd  mov     rcx, rdi; void *
0x180058ce0  mov     rdx, r14; Src
0x180058ce3  mov     r8, rbx; Size
0x180058ce6  call    memcpy_0
0x180058ceb  shl     r15, 3
0x180058cef  mov     rcx, rsi; void *
0x180058cf2  mov     rdx, r12; Src
0x180058cf5  mov     r8, r15; Size
0x180058cf8  call    memmove_0
0x180058cfd  mov     rcx, r12
0x180058d00  mov     rdx, rdi
0x180058d03  mov     r8, rbx
0x180058d06  jmp     loc_180059194
0x180058d10  cmp     r15, rbx
0x180058d13  jnb     loc_180058DD0
0x180058d19  mov     rax, r15
0x180058d1c  neg     rax
0x180058d1f  mov     rcx, r15
0x180058d22  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180058d26  lea     rdx, ds:0[r15*8]
0x180058d2e  mov     r8, r14
0x180058d31  sub     r8, rdx
0x180058d34  add     r8, 10h
0x180058d38  jmp     short loc_180058D52
0x180058d40  add     r14, rdx
0x180058d43  sub     rbx, r15
0x180058d46  add     r8, rdx
0x180058d49  cmp     rbx, r15
0x180058d4c  jb      loc_180058E90
0x180058d52  xor     r9d, r9d
0x180058d55  cmp     r15, 4
0x180058d59  jb      short loc_180058D9D
0x180058d5b  nop     dword ptr [rax+rax+00h]
0x180058d60  movups  xmm0, xmmword ptr [r8+r9*8-10h]
0x180058d66  movups  xmm1, xmmword ptr [r8+r9*8]
0x180058d6b  movups  xmm2, xmmword ptr [r14+r9*8]
0x180058d70  movups  xmm3, xmmword ptr [r14+r9*8+10h]
0x180058d76  movups  xmmword ptr [r8+r9*8-10h], xmm2
0x180058d7c  movups  xmmword ptr [r8+r9*8], xmm3
0x180058d81  movups  xmmword ptr [r14+r9*8], xmm0
0x180058d86  movups  xmmword ptr [r14+r9*8+10h], xmm1
0x180058d8c  add     r9, 4
0x180058d90  cmp     rcx, r9
0x180058d93  jnz     short loc_180058D60
0x180058d95  mov     r9, rcx
0x180058d98  cmp     r15, rcx
0x180058d9b  jz      short loc_180058D40
0x180058d9d  lea     r10, [r14+r9*8]
0x180058da1  add     r9, rax
0x180058da4  nop     word ptr [rax+rax+00000000h]
0x180058db0  mov     r11, [r14+r9*8]
0x180058db4  mov     rsi, [r10]
0x180058db7  mov     [r14+r9*8], rsi
0x180058dbb  mov     [r10], r11
0x180058dbe  add     r10, 8
0x180058dc2  inc     r9
0x180058dc5  jnz     short loc_180058DB0
0x180058dc7  jmp     loc_180058D40
0x180058dd0  mov     rax, rbx
0x180058dd3  neg     rax
0x180058dd6  mov     rcx, rbx
0x180058dd9  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180058ddd  lea     rdx, ds:0[rbx*8]
0x180058de5  mov     r8, r14
0x180058de8  sub     r8, rdx
0x180058deb  neg     rdx
0x180058dee  add     r8, 10h
0x180058df2  jmp     short loc_180058E12
0x180058e00  add     r14, rdx
0x180058e03  sub     r15, rbx
0x180058e06  add     r8, rdx
0x180058e09  cmp     r15, rbx
0x180058e0c  jb      loc_180058E90
0x180058e12  xor     r9d, r9d
0x180058e15  cmp     rbx, 4
0x180058e19  jb      short loc_180058E5D
0x180058e1b  nop     dword ptr [rax+rax+00h]
0x180058e20  movups  xmm0, xmmword ptr [r8+r9*8-10h]
0x180058e26  movups  xmm1, xmmword ptr [r8+r9*8]
0x180058e2b  movups  xmm2, xmmword ptr [r14+r9*8]
0x180058e30  movups  xmm3, xmmword ptr [r14+r9*8+10h]
0x180058e36  movups  xmmword ptr [r8+r9*8-10h], xmm2
0x180058e3c  movups  xmmword ptr [r8+r9*8], xmm3
0x180058e41  movups  xmmword ptr [r14+r9*8], xmm0
0x180058e46  movups  xmmword ptr [r14+r9*8+10h], xmm1
0x180058e4c  add     r9, 4
0x180058e50  cmp     rcx, r9
0x180058e53  jnz     short loc_180058E20
0x180058e55  mov     r9, rcx
0x180058e58  cmp     rbx, rcx
0x180058e5b  jz      short loc_180058E00
0x180058e5d  lea     r10, [r14+r9*8]
0x180058e61  add     r9, rax
0x180058e64  nop     word ptr [rax+rax+00000000h]
0x180058e70  mov     r11, [r14+r9*8]
0x180058e74  mov     rsi, [r10]
0x180058e77  mov     [r14+r9*8], rsi
0x180058e7b  mov     [r10], r11
0x180058e7e  add     r10, 8
0x180058e82  inc     r9
0x180058e85  jnz     short loc_180058E70
0x180058e87  jmp     loc_180058E00
0x180058e90  test    rbx, rbx
0x180058e93  jz      loc_180059199
0x180058e99  test    r15, r15
0x180058e9c  jnz     loc_180058D10
0x180058ea2  jmp     loc_180059199
0x180058ea7  cmp     [rbp+1F0h+var_78], 0
0x180058eaf  jz      loc_180059004
0x180058eb5  mov     r15, [rbp+1F0h+var_70]
0x180058ebc  mov     rcx, [r15]
0x180058ebf  mov     r12, [rbp+1F0h+var_B8]
0x180058ec6  mov     [rbp+1F0h+var_BC], 0
0x180058ed0  mov     dword ptr [rbp+1F0h+var_68], 0
0x180058eda  mov     rax, [rcx]
0x180058edd  mov     rax, [rax+28h]
0x180058ee1  lea     r8, [rbp+1F0h+var_BC]
0x180058ee8  lea     r9, [rbp+1F0h+var_68]
0x180058eef  mov     rdx, [rbp+1F0h+Buf2]
0x180058ef6  call    cs:__guard_dispatch_icall_fptr
0x180058efc  test    eax, eax
0x180058efe  js      loc_1800590A5
0x180058f04  mov     r14, rdi
0x180058f07  mov     edx, [rbp+1F0h+var_BC]
0x180058f0d  shl     rdx, 20h
0x180058f11  inc     rdx
0x180058f14  xor     edi, edi
0x180058f16  cmp     dword ptr [rbp+1F0h+var_68], 0
0x180058f1d  cmovz   rdx, rdi
0x180058f21  test    dl, dl
0x180058f23  mov     rbx, [rbp+1F0h+Address]
0x180058f2a  jz      loc_1800594E3
0x180058f30  shr     rdx, 20h
0x180058f34  mov     rcx, [r15]
0x180058f37  mov     [rbp+1F0h+var_68], 0
0x180058f42  mov     rax, [rcx]
0x180058f45  mov     rax, [rax+20h]
0x180058f49  lea     r8, [rbp+1F0h+var_68]
0x180058f50  call    cs:__guard_dispatch_icall_fptr
0x180058f56  test    eax, eax
0x180058f58  js      loc_180059106
0x180058f5e  mov     rdi, [rbp+1F0h+var_68]
0x180058f65  test    rdi, rdi
0x180058f68  jz      loc_180059133
0x180058f6e  mov     r15, [rbp+1F0h+arg_20]
0x180058f75  test    r15, r15
0x180058f78  jz      loc_1800591CC
0x180058f7e  mov     [rbp+1F0h+var_68], 0
0x180058f89  mov     rax, [rdi]
0x180058f8c  mov     rax, [rax]
0x180058f8f  lea     rdx, dword_1803B36C4
0x180058f96  lea     r8, [rbp+1F0h+var_68]
0x180058f9d  mov     rcx, rdi
0x180058fa0  call    cs:__guard_dispatch_icall_fptr
0x180058fa6  test    eax, eax
0x180058fa8  js      loc_180059252
0x180058fae  mov     rdx, [rbp+1F0h+var_68]
  ... truncated ...
```
