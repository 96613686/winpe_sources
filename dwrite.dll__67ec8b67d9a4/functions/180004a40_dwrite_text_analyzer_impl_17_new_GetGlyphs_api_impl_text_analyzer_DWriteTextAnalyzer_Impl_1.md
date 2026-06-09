# dwrite::text_analyzer::impl$17::new::GetGlyphs_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_

- ea: `0x180004a40`
- end: `0x1800053d7`
- name: `dwrite::text_analyzer::impl$17::new::GetGlyphs_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_`
- size: `2455`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001f60`
- `0x180004a40`
- `0x180022de0`
- `0x180027340`
- `0x180042930`
- `0x1800cff10`
- `0x1800dc910`
- `0x180316190`
- `0x180316255`
- `0x180316540`
- `0x180316730`
- `0x180316ae0`
- `0x180316d00`
- `0x180316ee0`

## import_xrefs

- `kernel32!HeapFree` at `0x180004bf9`
- `kernel32!HeapFree` at `0x180005081`
- `kernel32!HeapFree` at `0x1800050de`
- `kernel32!HeapFree` at `0x180005186`
- `kernel32!HeapFree` at `0x1800051df`
- `kernel32!HeapFree` at `0x180004bf9`
- `kernel32!HeapFree` at `0x180005081`
- `kernel32!HeapFree` at `0x1800050c2`
- `kernel32!HeapFree` at `0x180005186`
- `kernel32!HeapFree` at `0x1800051c7`
- `kernel32!GetProcessHeap` at `0x180004be7`
- `kernel32!GetProcessHeap` at `0x18000506f`
- `kernel32!GetProcessHeap` at `0x1800050d4`
- `kernel32!GetProcessHeap` at `0x180005178`
- `kernel32!GetProcessHeap` at `0x1800051d4`
- `kernel32!GetProcessHeap` at `0x180004be7`
- `kernel32!GetProcessHeap` at `0x18000506f`
- `kernel32!GetProcessHeap` at `0x1800050bb`
- `kernel32!GetProcessHeap` at `0x180005178`
- `kernel32!GetProcessHeap` at `0x1800051c0`
- `oleaut32!GetErrorInfo` at `0x180004b83`
- `oleaut32!GetErrorInfo` at `0x180004d1d`
- `oleaut32!GetErrorInfo` at `0x1800052d5`
- `oleaut32!GetErrorInfo` at `0x180005339`
- `oleaut32!GetErrorInfo` at `0x180004b83`
- `oleaut32!GetErrorInfo` at `0x180004d1d`
- `oleaut32!GetErrorInfo` at `0x1800052d5`
- `oleaut32!GetErrorInfo` at `0x180005339`

## string_xrefs

- `0x18000526d`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x18000529b`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=2
__int64 __fastcall dwrite::text_analyzer::impl_17::new::GetGlyphs_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_(
        __int64 a1,
        IErrorInfo *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        void *a11,
        __int64 a12,
        unsigned int a13,
        __int64 a14,
        void *a15,
        __int64 a16,
        __int64 a17,
        _DWORD *a18)
{
  int v21; // eax
  __int64 (*v22)(void); // rax
  int v23; // eax
  __int64 v24; // rsi
  unsigned int v25; // esi
  __int64 v26; // rdx
  HANDLE ProcessHeap; // rax
  __int64 v28; // rax
  void *v29; // rax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // rdi
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  unsigned __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rsi
  __int64 v39; // r13
  __int64 v40; // r14
  __int64 v41; // rsi
  __int64 v42; // rax
  int v43; // edx
  unsigned __int64 v44; // r10
  __int64 v45; // r11
  unsigned __int64 v46; // rbx
  unsigned __int64 v47; // rcx
  LPVOID v48; // rsi
  __int64 v49; // r14
  unsigned __int64 v50; // r10
  __int64 v51; // r8
  __m128i si128; // xmm0
  __m128i v53; // xmm1
  unsigned __int64 v54; // r9
  __m128i v55; // xmm2
  __int64 *v56; // rcx
  __int16 v57; // r9
  int v58; // r8d
  HANDLE v59; // rax
  __int64 v60; // rcx
  _UNKNOWN **v61; // rdi
  HANDLE v62; // rax
  _QWORD *v63; // rsi
  void *v64; // rbx
  HANDLE v65; // rax
  __int64 v66; // rcx
  _UNKNOWN **v67; // rbx
  HANDLE v68; // rax
  _QWORD *v69; // rdi
  int v71; // esi
  int v72; // esi
  __int64 v73[2]; // [rsp+D0h] [rbp+50h] BYREF
  int v74; // [rsp+E0h] [rbp+60h] BYREF
  int v75; // [rsp+E4h] [rbp+64h]
  __int64 v76; // [rsp+E8h] [rbp+68h]
  __int64 v77; // [rsp+F0h] [rbp+70h]
  __int64 v78; // [rsp+F8h] [rbp+78h]
  int v79[2]; // [rsp+100h] [rbp+80h] BYREF
  __int64 v80; // [rsp+108h] [rbp+88h]
  __int64 v81; // [rsp+110h] [rbp+90h]
  int v82[4]; // [rsp+118h] [rbp+98h] BYREF
  _UNKNOWN **v83; // [rsp+128h] [rbp+A8h]
  __int64 v84; // [rsp+130h] [rbp+B0h] BYREF
  LPVOID lpMem; // [rsp+138h] [rbp+B8h]
  __int64 v86; // [rsp+140h] [rbp+C0h]
  __int64 v87; // [rsp+148h] [rbp+C8h]
  IErrorInfo *pperrinfo; // [rsp+150h] [rbp+D0h] BYREF
  int *v89; // [rsp+158h] [rbp+D8h]
  __int64 v90; // [rsp+160h] [rbp+E0h]
  __int64 v91; // [rsp+168h] [rbp+E8h]
  LPVOID v92; // [rsp+170h] [rbp+F0h]
  __int64 v93; // [rsp+178h] [rbp+F8h]

  v93 = -2;
  *a18 = 0;
  if ( !a4 )
  {
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    a2 = pperrinfo;
    v25 = -2147024809;
    goto LABEL_85;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
  *(_QWORD *)v82 = 0;
  v21 = (**(__int64 (__fastcall ***)(__int64, int *, int *))a4)(a4, &dword_1803B3704, v82);
  v87 = a4;
  if ( v21 < 0 )
  {
    v71 = v21;
    goto LABEL_94;
  }
  if ( !*(_QWORD *)v82 )
  {
    v71 = -2147467261;
LABEL_94:
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    LODWORD(v89) = v71;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&pperrinfo,
      (unsigned int)&off_180335008,
      (__int64)&off_1803350B8);
  }
  v22 = *(__int64 (**)(void))(**(_QWORD **)v82 + 544LL);
  v86 = *(_QWORD *)v82;
  *(_QWORD *)v79 = v22();
  if ( a9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a9 + 8LL))(a9);
    *(_QWORD *)v82 = 0;
    v23 = (**(__int64 (__fastcall ***)(__int64, __int64 *, int *))a9)(a9, qword_180405980, v82);
    if ( v23 < 0 )
    {
      v72 = v23;
    }
    else
    {
      v24 = *(_QWORD *)v82;
      if ( *(_QWORD *)v82 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a9 + 16LL))(a9);
        goto LABEL_10;
      }
      v72 = -2147467261;
    }
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    LODWORD(v89) = v72;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&pperrinfo,
      (unsigned int)&off_180335008,
      (__int64)&off_1803350A0);
  }
  v24 = 0;
LABEL_10:
  v26 = a8;
  v84 = v24;
  if ( a8 )
  {
    dwrite::wchar::utf16::string_from_cwstr(&pperrinfo);
    lpMem = v89;
    langtag::parse_language_tag(v73, v89, v90);
    if ( pperrinfo )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    if ( a3 )
      goto LABEL_14;
LABEL_23:
    v25 = 0;
    goto LABEL_82;
  }
  *(_OWORD *)v73 = 0;
  if ( !a3 )
    goto LABEL_23;
LABEL_14:
  if ( !a13 )
  {
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    a2 = pperrinfo;
    v25 = -2147024774;
    goto LABEL_82;
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v79 + 296LL))(*(_QWORD *)v79);
  if ( !v28 )
    core::option::unwrap_failed(&off_180336098);
  v29 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 144LL))(v28);
  if ( !v29 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_1803431B8);
  v77 = (__int64)a2;
  *(_QWORD *)v82 = 0;
  v83 = &off_1804AF000;
  lpMem = v29;
  if ( (_DWORD)a12 )
  {
    v92 = a11;
    if ( 16 * (unsigned __int64)(unsigned int)a12 <= (unsigned __int64)off_1804AF020
      && (v30 = 16LL * (unsigned int)a12,
          v31 = (unsigned __int64)&off_1804AF020[v30 / 0xFFFFFFFFFFFFFFF8uLL] & 0xFFFFFFFFFFFFFFF8uLL,
          v31 >= (unsigned __int64)off_1804AF000) )
    {
      off_1804AF020 = (_UNKNOWN **)((unsigned __int64)&off_1804AF020[v30 / 0xFFFFFFFFFFFFFFF8uLL] & 0xFFFFFFFFFFFFFFF8uLL);
    }
    else
    {
      v31 = bumpalo::Bump::alloc_layout_slow(v82, 8);
      if ( !v31 )
        bumpalo::alloc::handle_alloc_error(8, 16LL * (unsigned int)a12, v32, v33);
    }
  }
  else
  {
    v31 = 8;
    v92 = (LPVOID)4;
  }
  v80 = a3;
  v78 = a13;
  pperrinfo = (IErrorInfo *)v31;
  v89 = v82;
  v90 = (unsigned int)a12;
  v34 = 0;
  v35 = 0;
  while ( 1 )
  {
    v91 = v34;
    if ( v35 >= (unsigned int)a12 )
      break;
    v37 = *(_QWORD *)(a10 + 8 * v35);
    v38 = *(unsigned int *)(v37 + 8);
    if ( !*(_DWORD *)(v37 + 8) )
    {
      v39 = 4;
      if ( v34 != v90 )
        goto LABEL_28;
LABEL_35:
      bumpalo::collections::raw_vec::RawVec_shaping::ShapingTextRangeProperties_::reserve_internal_or_panic_shaping::ShapingTextRangeProperties_(&pperrinfo);
      v31 = (unsigned __int64)pperrinfo;
      v34 = v91;
      goto LABEL_28;
    }
    v39 = *(_QWORD *)v37;
    if ( !*(_QWORD *)v37 )
      core::panicking::panic(
        "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_ut"
        "ils\\src\\lib.rs",
        32,
        &off_1803491E0);
    if ( v34 == v90 )
      goto LABEL_35;
LABEL_28:
    ++v35;
    v36 = 16 * v34;
    *(_QWORD *)(v31 + v36) = v39;
    *(_QWORD *)(v31 + v36 + 8) = v38;
    ++v34;
  }
  v81 = v34;
  if ( v34 )
  {
    v40 = 8 * v34;
    v41 = v34;
    v42 = std::sys::alloc::windows::process_heap_alloc(0, 8 * v34);
    v43 = (int)lpMem;
    if ( !v42 )
      alloc::alloc::handle_alloc_error(8, v40);
    v44 = (v41 - 1) & 0xFFFFFFFFFFFFFFFLL;
    v45 = v41;
    if ( v44 < 3 )
    {
      v46 = 0;
      v47 = v31;
      v48 = v92;
      v49 = v80;
      goto LABEL_44;
    }
    v50 = v44 + 1;
    v46 = v50 & 0xFFFFFFFFFFFFFFFCuLL;
    v47 = v31 + 16 * (v50 & 0xFFFFFFFFFFFFFFFCuLL);
    v51 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v53 = _mm_load_si128((const __m128i *)&_xmm);
    v54 = v31;
    v48 = v92;
    v49 = v80;
    do
    {
      v55 = _mm_shuffle_epi32((__m128i)v54, 68);
      *(__m128i *)(v42 + 8 * v51) = _mm_add_epi64(v55, si128);
      *(__m128i *)(v42 + 8 * v51 + 16) = _mm_add_epi64(v55, v53);
      v51 += 4;
      v54 += 64LL;
    }
    while ( v46 != v51 );
    if ( v50 != v46 )
    {
      do
      {
LABEL_44:
        *(_QWORD *)(v42 + 8 * v46) = v47;
        v47 += 16LL;
        ++v46;
      }
      while ( v47 != v31 + 16 * v45 );
    }
  }
  else
  {
    v42 = 8;
    v46 = 0;
    v43 = (int)lpMem;
    v48 = v92;
    v49 = v80;
  }
  v56 = &v84;
  if ( !v84 )
    v56 = 0;
  v57 = *(_WORD *)a7;
  v58 = *(_DWORD *)(a7 + 4);
  v92 = (LPVOID)v42;
  shaping_cache::get_glyphs(
    (int)&v74,
    v43,
    (int)v82,
    (int)v79,
    (__int64)v56,
    v77,
    v49,
    a5 != 0,
    a6 != 0,
    v57,
    v58,
    (__int64)v73,
    v42,
    v46,
    (__int64)v48,
    (unsigned int)a12,
    v78,
    a14,
    v49,
    a15,
    v49,
    a16,
    v78,
    a17,
    v78);
  if ( v74 != 1 )
  {
    *a18 = v76;
    if ( v81 )
    {
      v59 = GetProcessHeap();
      HeapFree(v59, 0, v92);
    }
    if ( v90 )
    {
      v60 = *((_QWORD *)v89 + 2);
      if ( *(_QWORD *)(v60 + 32) == v31 )
        *(_QWORD *)(v60 + 32) = 16 * v90 + v31;
    }
    v61 = v83;
    while ( v61 != &off_1804AF000 )
    {
      v63 = *v61;
      if ( (unsigned __int64)v61[1] >= 0x11 )
        v63 = (_QWORD *)*(v63 - 1);
      v61 = (_UNKNOWN **)v61[3];
      v62 = GetProcessHeap();
      HeapFree(v62, 0, v63);
    }
    if ( v84 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
    return 0;
  }
  v25 = -2003283967;
  v26 = v81;
  if ( v75 <= -4 )
  {
    if ( v75 == -101 )
    {
      v25 = -2147467263;
LABEL_70:
      v64 = v92;
    }
    else
    {
      v64 = v92;
      if ( v75 == -4 )
        v25 = -2003283968;
    }
  }
  else
  {
    if ( (unsigned int)(v75 + 3) < 2 )
    {
      v25 = -2147024774;
      goto LABEL_70;
    }
    v64 = v92;
    if ( v75 == -1 )
      v25 = -2147024809;
  }
  if ( v81 )
  {
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v64);
  }
  if ( v90 )
  {
    v66 = *((_QWORD *)v89 + 2);
    if ( *(_QWORD *)(v66 + 32) == v31 )
      *(_QWORD *)(v66 + 32) = 16 * v90 + v31;
  }
  v67 = v83;
  while ( v67 != &off_1804AF000 )
  {
    v69 = *v67;
    if ( (unsigned __int64)v67[1] >= 0x11 )
      v69 = (_QWORD *)*(v69 - 1);
    v67 = (_UNKNOWN **)v67[3];
    v68 = GetProcessHeap();
    HeapFree(v68, 0, v69);
  }
  a2 = 0;
LABEL_82:
  if ( v84 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 16LL))(v84, v26);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 16LL))(v86, v26);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
  if ( !v25 )
    return 0;
LABEL_85:
  if ( a2 )
    ((void (__fastcall *)(IErrorInfo *))a2->lpVtbl->Release)(a2);
  return v25;
}

```

## disassembly

```asm
0x180004a40  push    rbp
0x180004a41  push    r15
0x180004a43  push    r14
0x180004a45  push    r13
0x180004a47  push    r12
0x180004a49  push    rsi
0x180004a4a  push    rdi
0x180004a4b  push    rbx
0x180004a4c  sub     rsp, 188h
0x180004a53  lea     rbp, [rsp+80h]
0x180004a5b  mov     [rbp+140h+var_48], 0FFFFFFFFFFFFFFFEh
0x180004a66  mov     rax, [rbp+140h+arg_88]
0x180004a6d  mov     dword ptr [rax], 0
0x180004a73  test    r9, r9
0x180004a76  jz      loc_180004B6F
0x180004a7c  mov     rsi, r9
0x180004a7f  mov     r14d, r8d
0x180004a82  mov     rdi, rdx
0x180004a85  mov     rax, [r9]
0x180004a88  mov     rax, [rax+8]
0x180004a8c  mov     rcx, r9
0x180004a8f  call    cs:__guard_dispatch_icall_fptr
0x180004a95  mov     qword ptr [rbp+140h+var_A8], 0
0x180004aa0  mov     rax, [rsi]
0x180004aa3  mov     rax, [rax]
0x180004aa6  lea     rdx, dword_1803B3704
0x180004aad  lea     r13, [rbp+140h+var_A8]
0x180004ab4  mov     rcx, rsi
0x180004ab7  mov     r8, r13
0x180004aba  call    cs:__guard_dispatch_icall_fptr
0x180004ac0  test    eax, eax
0x180004ac2  mov     [rbp+140h+var_78], rsi
0x180004ac9  js      loc_1800052B8
0x180004acf  mov     rcx, qword ptr [rbp+140h+var_A8]
0x180004ad6  test    rcx, rcx
0x180004ad9  jz      loc_1800052BC
0x180004adf  mov     rbx, [rbp+140h+arg_40]
0x180004ae6  mov     rax, [rcx]
0x180004ae9  mov     rax, [rax+220h]
0x180004af0  mov     [rbp+140h+var_80], rcx
0x180004af7  call    cs:__guard_dispatch_icall_fptr
0x180004afd  mov     qword ptr [rbp+140h+var_C0], rax
0x180004b04  test    rbx, rbx
0x180004b07  jz      loc_180004B9A
0x180004b0d  mov     rax, [rbx]
0x180004b10  mov     rax, [rax+8]
0x180004b14  mov     rcx, rbx
0x180004b17  call    cs:__guard_dispatch_icall_fptr
0x180004b1d  mov     qword ptr [rbp+140h+var_A8], 0
0x180004b28  mov     rax, [rbx]
0x180004b2b  mov     rax, [rax]
0x180004b2e  lea     rdx, qword_180405980
0x180004b35  lea     r8, [rbp+140h+var_A8]
0x180004b3c  mov     rcx, rbx
0x180004b3f  call    cs:__guard_dispatch_icall_fptr
0x180004b45  test    eax, eax
0x180004b47  js      loc_18000531C
0x180004b4d  mov     rsi, qword ptr [rbp+140h+var_A8]
0x180004b54  test    rsi, rsi
0x180004b57  jz      loc_180005320
0x180004b5d  mov     rax, [rbx]
0x180004b60  mov     rax, [rax+10h]
0x180004b64  mov     rcx, rbx
0x180004b67  call    cs:__guard_dispatch_icall_fptr
0x180004b6d  jmp     short loc_180004B9C
0x180004b6f  mov     [rbp+140h+pperrinfo], 0
0x180004b7a  lea     rdx, [rbp+140h+pperrinfo]; pperrinfo
0x180004b81  xor     ecx, ecx; dwReserved
0x180004b83  call    cs:__imp_GetErrorInfo
0x180004b89  mov     rdi, [rbp+140h+pperrinfo]
0x180004b90  mov     esi, 80070057h
0x180004b95  jmp     loc_18000523E
0x180004b9a  xor     esi, esi
0x180004b9c  mov     rdx, [rbp+140h+arg_38]
0x180004ba3  mov     [rbp+140h+var_90], rsi
0x180004baa  test    rdx, rdx
0x180004bad  jz      loc_180004CF0
0x180004bb3  lea     rcx, [rbp+140h+pperrinfo]
0x180004bba  call    dwrite__wchar__utf16__string_from_cwstr
0x180004bbf  mov     rdx, [rbp+140h+var_68]
0x180004bc6  mov     r8, [rbp+140h+var_60]
0x180004bcd  lea     rcx, [rbp+140h+var_F0]
0x180004bd1  mov     [rbp+140h+lpMem], rdx
0x180004bd8  call    langtag__parse_language_tag
0x180004bdd  cmp     [rbp+140h+pperrinfo], 0
0x180004be5  jz      short loc_180004BFF
0x180004be7  call    cs:__imp_GetProcessHeap
0x180004bed  mov     rcx, rax; hHeap
0x180004bf0  xor     edx, edx; dwFlags
0x180004bf2  mov     r8, [rbp+140h+lpMem]; lpMem
0x180004bf9  call    cs:__imp_HeapFree
0x180004bff  test    r14d, r14d
0x180004c02  jz      loc_180004D02
0x180004c08  mov     esi, [rbp+140h+arg_60]
0x180004c0e  test    esi, esi
0x180004c10  jz      loc_180004D09
0x180004c16  mov     rcx, qword ptr [rbp+140h+var_C0]
0x180004c1d  mov     rax, [rcx]
0x180004c20  mov     rax, [rax+128h]
0x180004c27  call    cs:__guard_dispatch_icall_fptr
0x180004c2d  test    rax, rax
0x180004c30  jz      loc_18000528A
0x180004c36  mov     rcx, [rax]
0x180004c39  mov     rdx, [rcx+90h]
0x180004c40  mov     rcx, rax
0x180004c43  mov     rax, rdx
0x180004c46  call    cs:__guard_dispatch_icall_fptr
0x180004c4c  test    rax, rax
0x180004c4f  jz      loc_18000529B
0x180004c55  mov     r15, rax
0x180004c58  mov     [rbp+140h+var_D0], rdi
0x180004c5c  mov     eax, dword ptr [rbp+140h+arg_58]
0x180004c62  mov     qword ptr [rbp+140h+var_A8], 0
0x180004c6d  lea     rcx, off_1804AF000
0x180004c74  mov     [rbp+140h+var_98], rcx
0x180004c7b  mov     r12d, eax
0x180004c7e  test    eax, eax
0x180004c80  mov     [rbp+140h+lpMem], r15
0x180004c87  jz      loc_180004D34
0x180004c8d  mov     rax, [rbp+140h+arg_50]
0x180004c94  mov     [rbp+140h+var_50], rax
0x180004c9b  mov     rbx, r12
0x180004c9e  shl     rbx, 4
0x180004ca2  mov     rdi, cs:off_1804AF020
0x180004ca9  cmp     rbx, rdi
0x180004cac  ja      short loc_180004CC2
0x180004cae  sub     rdi, rbx
0x180004cb1  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180004cb5  cmp     rdi, cs:off_1804AF000
0x180004cbc  jnb     loc_180004D47
0x180004cc2  lea     rcx, [rbp+140h+var_A8]
0x180004cc9  mov     edx, 8
0x180004cce  mov     r8, rbx
0x180004cd1  call    bumpalo__Bump__alloc_layout_slow
0x180004cd6  mov     rdi, rax
0x180004cd9  test    rax, rax
0x180004cdc  jnz     short loc_180004D4E
0x180004cde  mov     ecx, 8
0x180004ce3  mov     rdx, rbx
0x180004ce6  call    bumpalo__alloc__handle_alloc_error
0x180004ceb  jmp     loc_18000538D
0x180004cf0  pxor    xmm0, xmm0
0x180004cf4  movdqa  xmmword ptr [rbp+140h+var_F0], xmm0
0x180004cf9  test    r14d, r14d
0x180004cfc  jnz     loc_180004C08
0x180004d02  xor     esi, esi
0x180004d04  jmp     loc_1800051F9
0x180004d09  mov     [rbp+140h+pperrinfo], 0
0x180004d14  lea     rdx, [rbp+140h+pperrinfo]; pperrinfo
0x180004d1b  xor     ecx, ecx; dwReserved
0x180004d1d  call    cs:__imp_GetErrorInfo
0x180004d23  mov     rdi, [rbp+140h+pperrinfo]
0x180004d2a  mov     esi, 8007007Ah
0x180004d2f  jmp     loc_1800051F9
0x180004d34  mov     edi, 8
0x180004d39  mov     eax, 4
0x180004d3e  mov     [rbp+140h+var_50], rax
0x180004d45  jmp     short loc_180004D4E
0x180004d47  mov     cs:off_1804AF020, rdi
0x180004d4e  mov     r15, [rbp+140h+arg_48]
0x180004d55  mov     eax, r14d
0x180004d58  mov     [rbp+140h+var_B8], rax
0x180004d5f  mov     eax, esi
0x180004d61  mov     [rbp+140h+var_C8], rax
0x180004d65  mov     [rbp+140h+pperrinfo], rdi
0x180004d6c  mov     [rbp+140h+var_68], r13
0x180004d73  mov     [rbp+140h+var_60], r12
0x180004d7a  xor     edx, edx
0x180004d7c  lea     r14, [rbp+140h+pperrinfo]
0x180004d83  xor     ebx, ebx
0x180004d85  jmp     short loc_180004DA6
0x180004d90  inc     rbx
0x180004d93  mov     rax, rdx
0x180004d96  shl     rax, 4
0x180004d9a  mov     [rdi+rax], r13
0x180004d9e  mov     [rdi+rax+8], rsi
0x180004da3  inc     rdx
0x180004da6  mov     [rbp+140h+var_58], rdx
0x180004dad  cmp     rbx, r12
0x180004db0  jnb     short loc_180004E07
0x180004db2  mov     rax, [r15+rbx*8]
0x180004db6  mov     esi, [rax+8]
0x180004db9  test    rsi, rsi
0x180004dbc  jz      short loc_180004DE0
0x180004dbe  mov     r13, [rax]
0x180004dc1  test    r13, r13
0x180004dc4  jz      loc_18000526D
0x180004dca  cmp     rdx, [rbp+140h+var_60]
0x180004dd1  jnz     short loc_180004D90
0x180004dd3  jmp     short loc_180004DEF
0x180004de0  mov     r13d, 4
0x180004de6  cmp     rdx, [rbp+140h+var_60]
0x180004ded  jnz     short loc_180004D90
0x180004def  mov     rcx, r14
0x180004df2  call    bumpalo__collections__raw_vec__RawVec_shaping__ShapingTextRangeProperties___reserve_internal_or_panic_shaping__ShapingTextRangeProperties_
0x180004df7  mov     rdi, [rbp+140h+pperrinfo]
0x180004dfe  mov     rdx, [rbp+140h+var_58]
0x180004e05  jmp     short loc_180004D90
0x180004e07  test    rdx, rdx
0x180004e0a  mov     [rbp+140h+var_B0], rdx
0x180004e11  jz      short loc_180004E6A
0x180004e13  lea     r14, ds:0[rdx*8]
0x180004e1b  xor     ecx, ecx
0x180004e1d  mov     rsi, rdx
0x180004e20  mov     rdx, r14
0x180004e23  call    std__sys__alloc__windows__process_heap_alloc
0x180004e28  test    rax, rax
0x180004e2b  mov     rdx, [rbp+140h+lpMem]; int
0x180004e32  jz      loc_180005380
0x180004e38  lea     rcx, [rsi-1]
0x180004e3c  mov     r10, 0FFFFFFFFFFFFFFFh
0x180004e46  and     r10, rcx
0x180004e49  cmp     r10, 3
0x180004e4d  mov     r11, rsi
0x180004e50  jnb     short loc_180004E8B
0x180004e52  xor     ebx, ebx
0x180004e54  mov     rcx, rdi
0x180004e57  mov     rsi, [rbp+140h+var_50]
0x180004e5e  mov     r14, [rbp+140h+var_B8]
0x180004e65  jmp     loc_180004F05
0x180004e6a  mov     eax, 8
0x180004e6f  xor     ebx, ebx
0x180004e71  mov     rdx, [rbp+140h+lpMem]
0x180004e78  mov     rsi, [rbp+140h+var_50]
0x180004e7f  mov     r14, [rbp+140h+var_B8]
0x180004e86  jmp     loc_180004F20
0x180004e8b  inc     r10
0x180004e8e  mov     rbx, r10
0x180004e91  and     rbx, 0FFFFFFFFFFFFFFFCh
0x180004e95  mov     rcx, rbx
0x180004e98  shl     rcx, 4
0x180004e9c  add     rcx, rdi
0x180004e9f  xor     r8d, r8d
0x180004ea2  movdqa  xmm0, cs:__xmm@00000000000000100000000000000000
0x180004eaa  movdqa  xmm1, cs:__xmm@00000000000000300000000000000020
0x180004eb2  mov     r9, rdi
0x180004eb5  mov     rsi, [rbp+140h+var_50]
0x180004ebc  mov     r14, [rbp+140h+var_B8]
0x180004ec3  nop     word ptr [rax+rax+00000000h]
0x180004ed0  movq    xmm2, r9
0x180004ed5  pshufd  xmm2, xmm2, 44h ; 'D'
0x180004eda  movdqa  xmm3, xmm2
0x180004ede  paddq   xmm3, xmm0
0x180004ee2  paddq   xmm2, xmm1
0x180004ee6  movdqu  xmmword ptr [rax+r8*8], xmm3
0x180004eec  movdqu  xmmword ptr [rax+r8*8+10h], xmm2
0x180004ef3  add     r8, 4
0x180004ef7  add     r9, 40h ; '@'
0x180004efb  cmp     rbx, r8
0x180004efe  jnz     short loc_180004ED0
0x180004f00  cmp     r10, rbx
0x180004f03  jz      short loc_180004F20
0x180004f05  mov     r8, r11
0x180004f08  shl     r8, 4
0x180004f0c  add     r8, rdi
0x180004f0f  nop
0x180004f10  mov     [rax+rbx*8], rcx
0x180004f14  add     rcx, 10h
0x180004f18  inc     rbx
0x180004f1b  cmp     rcx, r8
0x180004f1e  jnz     short loc_180004F10
0x180004f20  mov     r8, [rbp+140h+var_90]
0x180004f27  test    r8, r8
0x180004f2a  lea     rcx, [rbp+140h+var_90]
0x180004f31  cmovz   rcx, r8
0x180004f35  mov     r8, [rbp+140h+arg_30]
0x180004f3c  movzx   r9d, word ptr [r8]
0x180004f40  mov     r8d, [r8+4]
0x180004f44  cmp     [rbp+140h+arg_28], 0
0x180004f4b  setnz   [rsp+1C0h+var_180]
0x180004f50  cmp     [rbp+140h+arg_20], 0
0x180004f57  mov     r10, [rbp+140h+arg_80]
0x180004f5e  mov     [rsp+1C0h+var_108], r10; __int64
0x180004f66  mov     r10, [rbp+140h+arg_78]
0x180004f6d  mov     [rsp+1C0h+var_118], r10; __int64
0x180004f75  mov     r10, [rbp+140h+arg_70]
0x180004f7c  mov     [rsp+1C0h+var_128], r10; void *
0x180004f84  mov     r10, [rbp+140h+arg_68]
0x180004f8b  mov     [rsp+1C0h+var_138], r10; __int64
0x180004f93  mov     r10, [rbp+140h+var_C8]
0x180004f97  mov     [rsp+1C0h+var_100], r10; __int64
0x180004f9f  mov     [rsp+1C0h+var_110], r10; __int64
0x180004fa7  mov     [rsp+1C0h+var_140], r10; __int64
0x180004faf  mov     [rsp+1C0h+var_148], r12; __int64
0x180004fb4  mov     [rsp+1C0h+var_150], rsi; __int64
0x180004fb9  mov     [rsp+1C0h+var_158], rbx; __int64
0x180004fbe  lea     r10, [rbp+140h+var_F0]
0x180004fc2  mov     [rsp+1C0h+var_168], r10; __int64
0x180004fc7  mov     dword ptr [rsp+1C0h+var_170], r8d; char
0x180004fcc  mov     [rsp+1C0h+var_178], r9w; __int16
0x180004fd2  mov     [rsp+1C0h+var_120], r14; __int64
0x180004fda  setnz   [rsp+1C0h+var_188]
0x180004fdf  mov     [rsp+1C0h+var_130], r14; __int64
0x180004fe7  mov     [rbp+140h+var_50], rax
0x180004fee  mov     [rsp+1C0h+var_160], rax; __int64
0x180004ff3  mov     [rsp+1C0h+var_190], r14; __int64
0x180004ff8  mov     rax, [rbp+140h+var_D0]
0x180004ffc  mov     [rsp+1C0h+var_198], rax; __int64
0x180005001  mov     [rsp+1C0h+var_1A0], rcx; __int64
0x180005006  lea     rcx, [rbp+140h+var_E0]; int
  ... truncated ...
```
