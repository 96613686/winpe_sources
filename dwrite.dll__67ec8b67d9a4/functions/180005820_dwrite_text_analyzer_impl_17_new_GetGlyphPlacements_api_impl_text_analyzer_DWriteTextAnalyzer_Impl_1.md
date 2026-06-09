# dwrite::text_analyzer::impl$17::new::GetGlyphPlacements_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_

- ea: `0x180005820`
- end: `0x180006094`
- name: `dwrite::text_analyzer::impl$17::new::GetGlyphPlacements_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_`
- size: `2164`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001f60`
- `0x180005820`
- `0x180022de0`
- `0x180027340`
- `0x180042930`
- `0x1800d3fc0`
- `0x1800dc910`
- `0x180316190`
- `0x180316255`
- `0x180316540`
- `0x180316730`
- `0x180316ae0`
- `0x180316d00`
- `0x180316ee0`

## import_xrefs

- `kernel32!HeapFree` at `0x180005936`
- `kernel32!HeapFree` at `0x180005deb`
- `kernel32!HeapFree` at `0x180005e4e`
- `kernel32!HeapFree` at `0x180005e8b`
- `kernel32!HeapFree` at `0x180005eee`
- `kernel32!HeapFree` at `0x180005936`
- `kernel32!HeapFree` at `0x180005deb`
- `kernel32!HeapFree` at `0x180005e33`
- `kernel32!HeapFree` at `0x180005e8b`
- `kernel32!HeapFree` at `0x180005ecc`
- `kernel32!GetProcessHeap` at `0x180005924`
- `kernel32!GetProcessHeap` at `0x180005dd9`
- `kernel32!GetProcessHeap` at `0x180005e44`
- `kernel32!GetProcessHeap` at `0x180005e79`
- `kernel32!GetProcessHeap` at `0x180005ee4`
- `kernel32!GetProcessHeap` at `0x180005924`
- `kernel32!GetProcessHeap` at `0x180005dd9`
- `kernel32!GetProcessHeap` at `0x180005e2c`
- `kernel32!GetProcessHeap` at `0x180005e79`
- `kernel32!GetProcessHeap` at `0x180005ec5`
- `oleaut32!GetErrorInfo` at `0x180005a54`
- `oleaut32!GetErrorInfo` at `0x180005ff5`
- `oleaut32!GetErrorInfo` at `0x180005a54`
- `oleaut32!GetErrorInfo` at `0x180005ff5`

## string_xrefs

- `0x180005f82`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x180005fb0`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall dwrite::text_analyzer::impl_17::new::GetGlyphPlacements_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        int a11,
        int a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        void *a18,
        void *a19)
{
  __int64 v19; // r15
  int v23; // eax
  __int64 v24; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v26; // r12d
  __int64 v27; // rax
  __int64 v28; // rax
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // r15
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v33; // r14d
  __int64 v34; // rdx
  unsigned __int64 v35; // r14
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rsi
  __int64 v39; // rbx
  __int64 v40; // r12
  __int64 v41; // rsi
  __int64 v42; // rax
  __int64 v43; // r10
  __int64 v44; // rbx
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rax
  unsigned __int64 v47; // rcx
  unsigned __int64 v48; // rdx
  __int64 v49; // r8
  __m128i si128; // xmm0
  __m128i v51; // xmm1
  unsigned __int64 v52; // r9
  __m128i v53; // xmm2
  __int16 v54; // r8
  int v55; // r9d
  int glyph_placements; // eax
  int v57; // ecx
  int v58; // kr00_4
  __int64 v59; // rax
  HANDLE v60; // rax
  __int64 v61; // rcx
  unsigned __int64 *v62; // rsi
  HANDLE v63; // rax
  HANDLE v64; // rax
  __int64 v65; // rcx
  unsigned __int64 *v66; // rsi
  HANDLE v67; // rax
  _QWORD *v68; // rdi
  int v70; // esi
  LPVOID v71; // [rsp+38h] [rbp-48h]
  __int64 v72[2]; // [rsp+F0h] [rbp+70h] BYREF
  int v73[2]; // [rsp+108h] [rbp+88h]
  int v74[2]; // [rsp+110h] [rbp+90h] BYREF
  __int64 v75; // [rsp+118h] [rbp+98h]
  __int64 v76; // [rsp+120h] [rbp+A0h]
  int v77[4]; // [rsp+128h] [rbp+A8h] BYREF
  unsigned __int64 *v78; // [rsp+138h] [rbp+B8h]
  __int64 v79; // [rsp+140h] [rbp+C0h]
  LPVOID lpMem; // [rsp+148h] [rbp+C8h]
  IErrorInfo *pperrinfo; // [rsp+150h] [rbp+D0h] BYREF
  int *v82; // [rsp+158h] [rbp+D8h]
  __int64 v83; // [rsp+160h] [rbp+E0h]
  __int64 v84; // [rsp+168h] [rbp+E8h]
  __int64 v85; // [rsp+170h] [rbp+F0h]
  LPVOID v86; // [rsp+178h] [rbp+F8h]
  __int64 v87; // [rsp+180h] [rbp+100h]

  v87 = -2;
  v19 = a9;
  if ( !a9 )
    core::option::unwrap_failed(&off_1803350D0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a9 + 8LL))(a9);
  *(_QWORD *)v77 = 0;
  v23 = (**(__int64 (__fastcall ***)(__int64, int *, int *))a9)(a9, &dword_1803B3704, v77);
  if ( v23 < 0 )
  {
    v70 = v23;
    goto LABEL_80;
  }
  v24 = *(_QWORD *)v77;
  if ( !*(_QWORD *)v77 )
  {
    v70 = -2147467261;
LABEL_80:
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    LODWORD(v82) = v70;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&pperrinfo,
      (unsigned int)&off_180335008,
      (__int64)&off_1803350B8);
  }
  *(_QWORD *)v74 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v77 + 544LL))(*(_QWORD *)v77);
  v85 = v24;
  v86 = a4;
  if ( a14 )
  {
    dwrite::wchar::utf16::string_from_cwstr(&pperrinfo);
    lpMem = v82;
    langtag::parse_language_tag(v72, v82, v83);
    if ( pperrinfo )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  else
  {
    *(_OWORD *)v72 = 0;
  }
  v26 = 0;
  if ( !(_DWORD)a8 )
  {
LABEL_54:
    v33 = 0;
    goto LABEL_67;
  }
  if ( !(_DWORD)a5 )
  {
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    a2 = (unsigned __int64)pperrinfo;
    v33 = -2147024809;
    goto LABEL_67;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v74 + 296LL))(*(_QWORD *)v74);
  if ( !v27 )
    core::option::unwrap_failed(&off_180336098);
  v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 144LL))(v27);
  if ( !v28 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_1803431B8);
  *(_QWORD *)v73 = v28;
  lpMem = (LPVOID)a2;
  *(_QWORD *)v77 = 0;
  v78 = (unsigned __int64 *)&off_1804AF000;
  a2 = (unsigned int)a17;
  v75 = a3;
  if ( (_DWORD)a17 )
  {
    v76 = a16;
    if ( 16 * (unsigned __int64)(unsigned int)a17 <= (unsigned __int64)off_1804AF020
      && (v29 = 16LL * (unsigned int)a17,
          v30 = (unsigned __int64)&off_1804AF020[v29 / 0xFFFFFFFFFFFFFFF8uLL] & 0xFFFFFFFFFFFFFFF8uLL,
          v30 >= (unsigned __int64)off_1804AF000) )
    {
      off_1804AF020 = (_UNKNOWN **)((unsigned __int64)&off_1804AF020[v29 / 0xFFFFFFFFFFFFFFF8uLL] & 0xFFFFFFFFFFFFFFF8uLL);
    }
    else
    {
      v30 = bumpalo::Bump::alloc_layout_slow(v77, 8);
      if ( !v30 )
        bumpalo::alloc::handle_alloc_error(8, 16LL * (unsigned int)a17, v31, v32);
    }
  }
  else
  {
    v30 = 8;
    v76 = 4;
  }
  pperrinfo = (IErrorInfo *)v30;
  v82 = v77;
  v83 = (unsigned int)a17;
  v34 = 0;
  v35 = 0;
  while ( 1 )
  {
    v84 = v34;
    if ( v35 >= (unsigned int)a17 )
      break;
    v37 = *(_QWORD *)(a15 + 8 * v35);
    v38 = *(unsigned int *)(v37 + 8);
    if ( !*(_DWORD *)(v37 + 8) )
    {
      v39 = 4;
      if ( v34 != v83 )
        goto LABEL_21;
LABEL_28:
      bumpalo::collections::raw_vec::RawVec_shaping::ShapingTextRangeProperties_::reserve_internal_or_panic_shaping::ShapingTextRangeProperties_(&pperrinfo);
      v30 = (unsigned __int64)pperrinfo;
      v34 = v84;
      goto LABEL_21;
    }
    v39 = *(_QWORD *)v37;
    if ( !*(_QWORD *)v37 )
      core::panicking::panic(
        "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_ut"
        "ils\\src\\lib.rs",
        32,
        &off_1803491E0);
    if ( v34 == v83 )
      goto LABEL_28;
LABEL_21:
    ++v35;
    v36 = 16 * v34;
    *(_QWORD *)(v30 + v36) = v39;
    *(_QWORD *)(v30 + v36 + 8) = v38;
    ++v34;
  }
  v79 = v34;
  if ( v34 )
  {
    v40 = 8 * v34;
    v41 = v34;
    v42 = std::sys::alloc::windows::process_heap_alloc(0, 8 * v34);
    v43 = v75;
    if ( !v42 )
      alloc::alloc::handle_alloc_error(8, v40);
    v44 = v42;
    v45 = (v41 - 1) & 0xFFFFFFFFFFFFFFFLL;
    if ( v45 < 3 )
    {
      v46 = 0;
      v47 = v30;
      v26 = 0;
      goto LABEL_37;
    }
    v48 = v45 + 1;
    v46 = v48 & 0xFFFFFFFFFFFFFFFCuLL;
    v47 = v30 + 16 * (v48 & 0xFFFFFFFFFFFFFFFCuLL);
    v49 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v51 = _mm_load_si128((const __m128i *)&_xmm);
    v52 = v30;
    v26 = 0;
    do
    {
      v53 = _mm_shuffle_epi32((__m128i)v52, 68);
      *(__m128i *)(v44 + 8 * v49) = _mm_add_epi64(v53, si128);
      *(__m128i *)(v44 + 8 * v49 + 16) = _mm_add_epi64(v53, v51);
      v49 += 4;
      v52 += 64LL;
    }
    while ( v46 != v49 );
    if ( v48 != v46 )
    {
      do
      {
LABEL_37:
        *(_QWORD *)(v44 + 8 * v46) = v47;
        v47 += 16LL;
        ++v46;
      }
      while ( v47 != v30 + 16 * v41 );
    }
  }
  else
  {
    v44 = 8;
    v46 = 0;
    v26 = 0;
    v43 = v75;
  }
  v54 = *(_WORD *)a13;
  v55 = *(_DWORD *)(a13 + 4);
  v71 = v86;
  v86 = (LPVOID)v44;
  glyph_placements = shaping_cache::get_glyph_placements(
                       v73[0],
                       (int)v77,
                       (int)v74,
                       (int)lpMem,
                       (unsigned int)a5,
                       v43,
                       (unsigned int)a5,
                       (__int64)v71,
                       (unsigned int)a5,
                       a10,
                       1065353216,
                       0,
                       0,
                       a11 != 0,
                       a12 != 0,
                       v54,
                       v55,
                       (__int64)v72,
                       v44,
                       v46,
                       v76,
                       (unsigned int)a17,
                       a6,
                       (unsigned int)a8,
                       a7,
                       (unsigned int)a8,
                       a18,
                       (unsigned int)a8,
                       a19,
                       (unsigned int)a8);
  v57 = glyph_placements + 4;
  v58 = glyph_placements;
  v59 = v79;
  switch ( v57 )
  {
    case 0:
      v33 = -2003283968;
      goto LABEL_56;
    case 1:
    case 2:
      v33 = -2147024774;
      if ( !v79 )
        goto LABEL_58;
      goto LABEL_57;
    case 3:
      v33 = -2147024809;
      if ( !v79 )
        goto LABEL_58;
      goto LABEL_57;
    case 4:
      if ( v79 )
      {
        v60 = GetProcessHeap();
        HeapFree(v60, 0, v86);
      }
      if ( v83 )
      {
        v61 = *((_QWORD *)v82 + 2);
        if ( *(_QWORD *)(v61 + 32) == v30 )
          *(_QWORD *)(v61 + 32) = 16 * v83 + v30;
      }
      v62 = v78;
      v19 = a9;
      while ( v62 != (unsigned __int64 *)&off_1804AF000 )
      {
        a2 = *v62;
        if ( v62[1] >= 0x11 )
          a2 = *(_QWORD *)(a2 - 8);
        v62 = (unsigned __int64 *)v62[3];
        v63 = GetProcessHeap();
        HeapFree(v63, 0, (LPVOID)a2);
      }
      goto LABEL_54;
    default:
      v33 = -2003283967;
      v59 = v79;
      if ( v58 == -101 )
      {
        v33 = -2147467263;
        if ( !v79 )
          goto LABEL_58;
      }
      else
      {
LABEL_56:
        if ( !v59 )
          goto LABEL_58;
      }
LABEL_57:
      v64 = GetProcessHeap();
      HeapFree(v64, 0, v86);
LABEL_58:
      if ( v83 )
      {
        v65 = *((_QWORD *)v82 + 2);
        if ( *(_QWORD *)(v65 + 32) == v30 )
          *(_QWORD *)(v65 + 32) = 16 * v83 + v30;
      }
      v66 = v78;
      while ( v66 != (unsigned __int64 *)&off_1804AF000 )
      {
        v68 = (_QWORD *)*v66;
        if ( v66[1] >= 0x11 )
          v68 = (_QWORD *)*(v68 - 1);
        v66 = (unsigned __int64 *)v66[3];
        v67 = GetProcessHeap();
        HeapFree(v67, 0, v68);
      }
      a2 = 0;
      v19 = a9;
      break;
  }
LABEL_67:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v33 )
  {
    if ( a2 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)a2 + 16LL))(a2);
    return v33;
  }
  return v26;
}

```

## disassembly

```asm
0x180005820  push    rbp
0x180005821  push    r15
0x180005823  push    r14
0x180005825  push    r13
0x180005827  push    r12
0x180005829  push    rsi
0x18000582a  push    rdi
0x18000582b  push    rbx
0x18000582c  sub     rsp, 1A8h
0x180005833  lea     rbp, [rsp+80h]
0x18000583b  movaps  [rbp+160h+var_50], xmm6
0x180005842  mov     [rbp+160h+var_60], 0FFFFFFFFFFFFFFFEh
0x18000584d  mov     r15, [rbp+160h+arg_40]
0x180005854  test    r15, r15
0x180005857  jz      loc_180005FCA
0x18000585d  mov     r12, r9
0x180005860  mov     r14, r8
0x180005863  mov     rdi, rdx
0x180005866  mov     rax, [r15]
0x180005869  mov     rax, [rax+8]
0x18000586d  mov     rcx, r15
0x180005870  call    cs:__guard_dispatch_icall_fptr
0x180005876  mov     qword ptr [rbp+160h+var_B8], 0
0x180005881  mov     rax, [r15]
0x180005884  mov     rax, [rax]
0x180005887  lea     rdx, dword_1803B3704
0x18000588e  lea     r13, [rbp+160h+var_B8]
0x180005895  mov     rcx, r15
0x180005898  mov     r8, r13
0x18000589b  call    cs:__guard_dispatch_icall_fptr
0x1800058a1  test    eax, eax
0x1800058a3  js      loc_180005FD8
0x1800058a9  mov     rbx, qword ptr [rbp+160h+var_B8]
0x1800058b0  test    rbx, rbx
0x1800058b3  jz      loc_180005FDC
0x1800058b9  mov     rsi, [rbp+160h+arg_68]
0x1800058c0  mov     rax, [rbx]
0x1800058c3  mov     rax, [rax+220h]
0x1800058ca  mov     rcx, rbx
0x1800058cd  call    cs:__guard_dispatch_icall_fptr
0x1800058d3  mov     qword ptr [rbp+160h+var_D0], rax
0x1800058da  test    rsi, rsi
0x1800058dd  mov     [rbp+160h+var_70], rbx
0x1800058e4  mov     [rbp+160h+var_68], r12
0x1800058eb  jz      short loc_18000593E
0x1800058ed  lea     rcx, [rbp+160h+pperrinfo]
0x1800058f4  mov     rdx, rsi
0x1800058f7  call    dwrite__wchar__utf16__string_from_cwstr
0x1800058fc  mov     rdx, [rbp+160h+var_88]
0x180005903  mov     r8, [rbp+160h+var_80]
0x18000590a  lea     rcx, [rbp+160h+var_F0]
0x18000590e  mov     [rbp+160h+lpMem], rdx
0x180005915  call    langtag__parse_language_tag
0x18000591a  cmp     [rbp+160h+pperrinfo], 0
0x180005922  jz      short loc_180005947
0x180005924  call    cs:__imp_GetProcessHeap
0x18000592a  mov     rcx, rax; hHeap
0x18000592d  xor     edx, edx; dwFlags
0x18000592f  mov     r8, [rbp+160h+lpMem]; lpMem
0x180005936  call    cs:__imp_HeapFree
0x18000593c  jmp     short loc_180005947
0x18000593e  pxor    xmm0, xmm0
0x180005942  movdqa  xmmword ptr [rbp+160h+var_F0], xmm0
0x180005947  xor     r12d, r12d
0x18000594a  cmp     dword ptr [rbp+160h+arg_38], 0
0x180005951  jz      loc_180005E66
0x180005957  cmp     dword ptr [rbp+160h+arg_20], 0
0x18000595e  jz      loc_180005A40
0x180005964  mov     rcx, qword ptr [rbp+160h+var_D0]
0x18000596b  mov     rax, [rcx]
0x18000596e  mov     rax, [rax+128h]
0x180005975  call    cs:__guard_dispatch_icall_fptr
0x18000597b  test    rax, rax
0x18000597e  jz      loc_180005F9F
0x180005984  mov     rcx, [rax]
0x180005987  mov     rdx, [rcx+90h]
0x18000598e  mov     rcx, rax
0x180005991  mov     rax, rdx
0x180005994  call    cs:__guard_dispatch_icall_fptr
0x18000599a  test    rax, rax
0x18000599d  jz      loc_180005FB0
0x1800059a3  mov     qword ptr [rbp+160h+var_D8], rax
0x1800059aa  mov     [rbp+160h+lpMem], rdi
0x1800059b1  mov     eax, dword ptr [rbp+160h+arg_80]
0x1800059b7  mov     qword ptr [rbp+160h+var_B8], 0
0x1800059c2  lea     rcx, off_1804AF000
0x1800059c9  mov     [rbp+160h+var_A8], rcx
0x1800059d0  mov     edi, eax
0x1800059d2  test    eax, eax
0x1800059d4  mov     [rbp+160h+var_C8], r14
0x1800059db  jz      loc_180005A6C
0x1800059e1  mov     rax, [rbp+160h+arg_78]
0x1800059e8  mov     [rbp+160h+var_C0], rax
0x1800059ef  mov     r12, rdi
0x1800059f2  shl     r12, 4
0x1800059f6  mov     r15, cs:off_1804AF020
0x1800059fd  cmp     r12, r15
0x180005a00  ja      short loc_180005A12
0x180005a02  sub     r15, r12
0x180005a05  and     r15, 0FFFFFFFFFFFFFFF8h
0x180005a09  cmp     r15, cs:off_1804AF000
0x180005a10  jnb     short loc_180005A80
0x180005a12  lea     rcx, [rbp+160h+var_B8]
0x180005a19  mov     edx, 8
0x180005a1e  mov     r8, r12
0x180005a21  call    bumpalo__Bump__alloc_layout_slow
0x180005a26  mov     r15, rax
0x180005a29  test    rax, rax
0x180005a2c  jnz     short loc_180005A87
0x180005a2e  mov     ecx, 8
0x180005a33  mov     rdx, r12
0x180005a36  call    bumpalo__alloc__handle_alloc_error
0x180005a3b  jmp     loc_180006049
0x180005a40  mov     [rbp+160h+pperrinfo], 0
0x180005a4b  lea     rdx, [rbp+160h+pperrinfo]; pperrinfo
0x180005a52  xor     ecx, ecx; dwReserved
0x180005a54  call    cs:__imp_GetErrorInfo
0x180005a5a  mov     rdi, [rbp+160h+pperrinfo]
0x180005a61  mov     r14d, 80070057h
0x180005a67  jmp     loc_180005F0F
0x180005a6c  mov     r15d, 8
0x180005a72  mov     eax, 4
0x180005a77  mov     [rbp+160h+var_C0], rax
0x180005a7e  jmp     short loc_180005A87
0x180005a80  mov     cs:off_1804AF020, r15
0x180005a87  mov     r12, [rbp+160h+arg_70]
0x180005a8e  movss   xmm6, [rbp+160h+arg_48]
0x180005a96  mov     [rbp+160h+pperrinfo], r15
0x180005a9d  mov     [rbp+160h+var_88], r13
0x180005aa4  mov     [rbp+160h+var_80], rdi
0x180005aab  xor     edx, edx
0x180005aad  lea     r13, [rbp+160h+pperrinfo]
0x180005ab4  xor     r14d, r14d
0x180005ab7  jmp     short loc_180005AD6
0x180005ac0  inc     r14
0x180005ac3  mov     rax, rdx
0x180005ac6  shl     rax, 4
0x180005aca  mov     [r15+rax], rbx
0x180005ace  mov     [r15+rax+8], rsi
0x180005ad3  inc     rdx
0x180005ad6  mov     [rbp+160h+var_78], rdx
0x180005add  cmp     r14, rdi
0x180005ae0  jnb     short loc_180005B36
0x180005ae2  mov     rax, [r12+r14*8]
0x180005ae6  mov     esi, [rax+8]
0x180005ae9  test    rsi, rsi
0x180005aec  jz      short loc_180005B10
0x180005aee  mov     rbx, [rax]
0x180005af1  test    rbx, rbx
0x180005af4  jz      loc_180005F82
0x180005afa  cmp     rdx, [rbp+160h+var_80]
0x180005b01  jnz     short loc_180005AC0
0x180005b03  jmp     short loc_180005B1E
0x180005b10  mov     ebx, 4
0x180005b15  cmp     rdx, [rbp+160h+var_80]
0x180005b1c  jnz     short loc_180005AC0
0x180005b1e  mov     rcx, r13
0x180005b21  call    bumpalo__collections__raw_vec__RawVec_shaping__ShapingTextRangeProperties___reserve_internal_or_panic_shaping__ShapingTextRangeProperties_
0x180005b26  mov     r15, [rbp+160h+pperrinfo]
0x180005b2d  mov     rdx, [rbp+160h+var_78]
0x180005b34  jmp     short loc_180005AC0
0x180005b36  test    rdx, rdx
0x180005b39  mov     [rbp+160h+var_A0], rdx
0x180005b40  jz      short loc_180005B98
0x180005b42  lea     r12, ds:0[rdx*8]
0x180005b4a  xor     ecx, ecx
0x180005b4c  mov     rsi, rdx
0x180005b4f  mov     rdx, r12
0x180005b52  call    std__sys__alloc__windows__process_heap_alloc
0x180005b57  test    rax, rax
0x180005b5a  lea     r13, off_1804AF000
0x180005b61  mov     r10, [rbp+160h+var_C8]
0x180005b68  jz      loc_18000603C
0x180005b6e  mov     rbx, rax
0x180005b71  lea     rax, [rsi-1]
0x180005b75  mov     rdx, 0FFFFFFFFFFFFFFFh
0x180005b7f  and     rdx, rax
0x180005b82  cmp     rdx, 3
0x180005b86  mov     r11, rsi
0x180005b89  jnb     short loc_180005BB5
0x180005b8b  xor     eax, eax
0x180005b8d  mov     rcx, r15
0x180005b90  xor     r12d, r12d
0x180005b93  jmp     loc_180005C25
0x180005b98  mov     ebx, 8
0x180005b9d  xor     eax, eax
0x180005b9f  xor     r12d, r12d
0x180005ba2  lea     r13, off_1804AF000
0x180005ba9  mov     r10, [rbp+160h+var_C8]
0x180005bb0  jmp     loc_180005C40
0x180005bb5  inc     rdx
0x180005bb8  mov     rax, rdx
0x180005bbb  and     rax, 0FFFFFFFFFFFFFFFCh
0x180005bbf  mov     rcx, rax
0x180005bc2  shl     rcx, 4
0x180005bc6  add     rcx, r15
0x180005bc9  xor     r8d, r8d
0x180005bcc  movdqa  xmm0, cs:__xmm@00000000000000100000000000000000
0x180005bd4  movdqa  xmm1, cs:__xmm@00000000000000300000000000000020
0x180005bdc  mov     r9, r15
0x180005bdf  xor     r12d, r12d
0x180005be2  nop     word ptr [rax+rax+00000000h]
0x180005bf0  movq    xmm2, r9
0x180005bf5  pshufd  xmm2, xmm2, 44h ; 'D'
0x180005bfa  movdqa  xmm3, xmm2
0x180005bfe  paddq   xmm3, xmm0
0x180005c02  paddq   xmm2, xmm1
0x180005c06  movdqu  xmmword ptr [rbx+r8*8], xmm3
0x180005c0c  movdqu  xmmword ptr [rbx+r8*8+10h], xmm2
0x180005c13  add     r8, 4
0x180005c17  add     r9, 40h ; '@'
0x180005c1b  cmp     rax, r8
0x180005c1e  jnz     short loc_180005BF0
0x180005c20  cmp     rdx, rax
0x180005c23  jz      short loc_180005C40
0x180005c25  mov     rdx, r11
0x180005c28  shl     rdx, 4
0x180005c2c  add     rdx, r15
0x180005c2f  nop
0x180005c30  mov     [rbx+rax*8], rcx
0x180005c34  add     rcx, 10h
0x180005c38  inc     rax
0x180005c3b  cmp     rcx, rdx
0x180005c3e  jnz     short loc_180005C30
0x180005c40  mov     ecx, dword ptr [rbp+160h+arg_20]
0x180005c46  mov     edx, dword ptr [rbp+160h+arg_38]
0x180005c4c  mov     r9, [rbp+160h+arg_60]
0x180005c53  movzx   r8d, word ptr [r9]
0x180005c57  mov     r9d, [r9+4]
0x180005c5b  cmp     [rbp+160h+arg_58], 0
0x180005c62  setnz   [rsp+1E0h+var_170]
0x180005c67  cmp     [rbp+160h+arg_50], 0
0x180005c6e  mov     r11, [rbp+160h+arg_90]
0x180005c75  mov     [rsp+1E0h+var_100], r11; void *
0x180005c7d  mov     r11, [rbp+160h+arg_88]
0x180005c84  mov     [rsp+1E0h+var_110], r11; void *
0x180005c8c  mov     r11, [rbp+160h+arg_30]
0x180005c93  mov     [rsp+1E0h+var_120], r11; __int64
0x180005c9b  mov     [rsp+1E0h+var_F8], rdx; __int64
0x180005ca3  mov     [rsp+1E0h+var_108], rdx; __int64
0x180005cab  mov     [rsp+1E0h+var_118], rdx; __int64
0x180005cb3  mov     [rsp+1E0h+var_128], rdx; __int64
0x180005cbb  mov     rdx, [rbp+160h+arg_28]
0x180005cc2  mov     [rsp+1E0h+var_130], rdx; __int64
0x180005cca  mov     [rsp+1E0h+var_138], rdi; __int64
0x180005cd2  mov     rdx, [rbp+160h+var_C0]
0x180005cd9  mov     [rsp+1E0h+var_140], rdx; __int64
0x180005ce1  mov     [rsp+1E0h+var_148], rax; __int64
0x180005ce9  lea     rax, [rbp+160h+var_F0]
0x180005ced  mov     [rsp+1E0h+var_158], rax; __int64
0x180005cf5  mov     dword ptr [rsp+1E0h+var_160], r9d; char
0x180005cfd  mov     [rsp+1E0h+var_168], r8w; __int16
0x180005d03  setnz   [rsp+1E0h+var_178]
0x180005d08  mov     rax, [rbp+160h+var_68]
0x180005d0f  mov     [rsp+1E0h+var_1A8], rax; __int64
0x180005d14  mov     [rbp+160h+var_68], rbx
0x180005d1b  mov     [rsp+1E0h+var_150], rbx; __int64
0x180005d23  movss   [rsp+1E0h+var_198], xmm6; int
0x180005d29  mov     [rsp+1E0h+var_1A0], rcx; __int64
0x180005d2e  mov     [rsp+1E0h+var_1B0], rcx; __int64
0x180005d33  mov     [rsp+1E0h+var_1B8], r10; __int64
0x180005d38  mov     [rsp+1E0h+var_1C0], rcx; __int64
0x180005d3d  mov     [rsp+1E0h+var_180], 0; int
0x180005d45  mov     [rsp+1E0h+var_188], 0; __int64
0x180005d4e  mov     [rsp+1E0h+var_190], 3F800000h; int
0x180005d56  lea     rdx, [rbp+160h+var_B8]; int
0x180005d5d  lea     r8, [rbp+160h+var_D0]; int
0x180005d64  mov     r9, [rbp+160h+lpMem]; int
0x180005d6b  mov     rcx, qword ptr [rbp+160h+var_D8]; int
0x180005d72  call    shaping_cache__get_glyph_placements
0x180005d77  lea     ecx, [rax+4]; switch 5 cases
0x180005d7a  cmp     ecx, 4
0x180005d7d  ja      short def_180005D94; jumptable 0000000180005D94 default case
0x180005d7f  lea     rax, jpt_180005D94
0x180005d86  movsxd  rcx, ds:(jpt_180005D94 - 18040634Ch)[rax+rcx*4]
0x180005d8a  add     rcx, rax
0x180005d8d  mov     rax, [rbp+160h+var_A0]
0x180005d94  jmp     rcx; switch jump
0x180005d96  mov     r14d, 8007007Ah; jumptable 0000000180005D94 cases -3,-2
0x180005d9c  test    rax, rax
0x180005d9f  jnz     loc_180005E79
0x180005da5  jmp     loc_180005E91
0x180005daa  mov     r14d, 88985001h; jumptable 0000000180005D94 default case
0x180005db0  cmp     eax, 0FFFFFF9Bh
0x180005db3  mov     rax, [rbp+160h+var_A0]
0x180005dba  jnz     loc_180005E74
0x180005dc0  mov     r14d, 80004001h
0x180005dc6  test    rax, rax
0x180005dc9  jnz     loc_180005E79
0x180005dcf  jmp     loc_180005E91
0x180005dd4  test    rax, rax; jumptable 0000000180005D94 case 0
0x180005dd7  jz      short loc_180005DF1
0x180005dd9  call    cs:__imp_GetProcessHeap
0x180005ddf  mov     rcx, rax; hHeap
0x180005de2  xor     edx, edx; dwFlags
0x180005de4  mov     r8, [rbp+160h+var_68]; lpMem
0x180005deb  call    cs:__imp_HeapFree
0x180005df1  mov     rax, [rbp+160h+var_80]
0x180005df8  test    rax, rax
0x180005dfb  jz      short loc_180005E19
  ... truncated ...
```
