# dwrite::text_analyzer::impl$17::new::GetGdiCompatibleGlyphPlacements_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_

- ea: `0x1800064c0`
- end: `0x180006d5b`
- name: `dwrite::text_analyzer::impl$17::new::GetGdiCompatibleGlyphPlacements_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_`
- size: `2203`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001f60`
- `0x1800064c0`
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

- `kernel32!HeapFree` at `0x1800065dd`
- `kernel32!HeapFree` at `0x180006aa8`
- `kernel32!HeapFree` at `0x180006b0e`
- `kernel32!HeapFree` at `0x180006b4b`
- `kernel32!HeapFree` at `0x180006bae`
- `kernel32!HeapFree` at `0x1800065dd`
- `kernel32!HeapFree` at `0x180006aa8`
- `kernel32!HeapFree` at `0x180006af0`
- `kernel32!HeapFree` at `0x180006b4b`
- `kernel32!HeapFree` at `0x180006b8c`
- `kernel32!GetProcessHeap` at `0x1800065cb`
- `kernel32!GetProcessHeap` at `0x180006a96`
- `kernel32!GetProcessHeap` at `0x180006b04`
- `kernel32!GetProcessHeap` at `0x180006b39`
- `kernel32!GetProcessHeap` at `0x180006ba4`
- `kernel32!GetProcessHeap` at `0x1800065cb`
- `kernel32!GetProcessHeap` at `0x180006a96`
- `kernel32!GetProcessHeap` at `0x180006ae9`
- `kernel32!GetProcessHeap` at `0x180006b39`
- `kernel32!GetProcessHeap` at `0x180006b85`
- `oleaut32!GetErrorInfo` at `0x1800066fb`
- `oleaut32!GetErrorInfo` at `0x180006cbc`
- `oleaut32!GetErrorInfo` at `0x1800066fb`
- `oleaut32!GetErrorInfo` at `0x180006cbc`

## string_xrefs

- `0x180006c49`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x180006c77`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall dwrite::text_analyzer::impl_17::new::GetGdiCompatibleGlyphPlacements_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_(
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
        __int64 a12,
        unsigned int a13,
        int a14,
        int a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        void *a21,
        void *a22)
{
  __int64 v22; // r15
  int v26; // eax
  __int64 v27; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v29; // r12d
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int64 v32; // r12
  unsigned __int64 v33; // r15
  __int64 v34; // r8
  __int64 v35; // r9
  unsigned int v36; // r14d
  __int64 v37; // rdx
  unsigned __int64 v38; // r14
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rsi
  __int64 v42; // rbx
  __int64 v43; // r12
  __int64 v44; // rsi
  __int64 v45; // rax
  __int64 v46; // r11
  __int64 v47; // rbx
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  __int64 v52; // r8
  __m128i si128; // xmm0
  __m128i v54; // xmm1
  unsigned __int64 v55; // r9
  __m128i v56; // xmm2
  __int16 v57; // r9
  int v58; // r10d
  int glyph_placements; // eax
  int v60; // ecx
  int v61; // kr00_4
  __int64 v62; // rax
  HANDLE v63; // rax
  __int64 v64; // rcx
  unsigned __int64 *v65; // rsi
  HANDLE v66; // rax
  HANDLE v67; // rax
  __int64 v68; // rcx
  unsigned __int64 *v69; // rsi
  HANDLE v70; // rax
  _QWORD *v71; // rdi
  int v73; // esi
  LPVOID v74; // [rsp+38h] [rbp-48h]
  __int64 v75[2]; // [rsp+F0h] [rbp+70h] BYREF
  int v76[2]; // [rsp+108h] [rbp+88h]
  int v77[2]; // [rsp+110h] [rbp+90h] BYREF
  __int64 v78; // [rsp+118h] [rbp+98h]
  __int64 v79; // [rsp+120h] [rbp+A0h]
  int v80[4]; // [rsp+128h] [rbp+A8h] BYREF
  unsigned __int64 *v81; // [rsp+138h] [rbp+B8h]
  __int64 v82; // [rsp+140h] [rbp+C0h]
  LPVOID lpMem; // [rsp+148h] [rbp+C8h]
  IErrorInfo *pperrinfo; // [rsp+150h] [rbp+D0h] BYREF
  int *v85; // [rsp+158h] [rbp+D8h]
  __int64 v86; // [rsp+160h] [rbp+E0h]
  __int64 v87; // [rsp+168h] [rbp+E8h]
  __int64 v88; // [rsp+170h] [rbp+F0h]
  LPVOID v89; // [rsp+178h] [rbp+F8h]
  __int64 v90; // [rsp+180h] [rbp+100h]

  v90 = -2;
  v22 = a9;
  if ( !a9 )
    core::option::unwrap_failed(&off_1803350E8);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a9 + 8LL))(a9);
  *(_QWORD *)v80 = 0;
  v26 = (**(__int64 (__fastcall ***)(__int64, int *, int *))a9)(a9, &dword_1803B3704, v80);
  if ( v26 < 0 )
  {
    v73 = v26;
    goto LABEL_80;
  }
  v27 = *(_QWORD *)v80;
  if ( !*(_QWORD *)v80 )
  {
    v73 = -2147467261;
LABEL_80:
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    LODWORD(v85) = v73;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&pperrinfo,
      (unsigned int)&off_180335008,
      (__int64)&off_1803350B8);
  }
  *(_QWORD *)v77 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v80 + 544LL))(*(_QWORD *)v80);
  v88 = v27;
  v89 = a4;
  if ( a17 )
  {
    dwrite::wchar::utf16::string_from_cwstr(&pperrinfo);
    lpMem = v85;
    langtag::parse_language_tag(v75, v85, v86);
    if ( pperrinfo )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  else
  {
    *(_OWORD *)v75 = 0;
  }
  v29 = 0;
  if ( !(_DWORD)a8 )
  {
LABEL_54:
    v36 = 0;
    goto LABEL_67;
  }
  if ( !(_DWORD)a5 )
  {
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    a2 = (unsigned __int64)pperrinfo;
    v36 = -2147024809;
    goto LABEL_67;
  }
  v30 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v77 + 296LL))(*(_QWORD *)v77);
  if ( !v30 )
    core::option::unwrap_failed(&off_180336098);
  v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 144LL))(v30);
  if ( !v31 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_1803431B8);
  *(_QWORD *)v76 = v31;
  lpMem = (LPVOID)a2;
  *(_QWORD *)v80 = 0;
  v81 = (unsigned __int64 *)&off_1804AF000;
  a2 = (unsigned int)a20;
  v78 = a3;
  if ( (_DWORD)a20 )
  {
    v79 = a19;
    if ( 16 * (unsigned __int64)(unsigned int)a20 <= (unsigned __int64)off_1804AF020
      && (v32 = 16LL * (unsigned int)a20,
          v33 = (unsigned __int64)&off_1804AF020[v32 / 0xFFFFFFFFFFFFFFF8uLL] & 0xFFFFFFFFFFFFFFF8uLL,
          v33 >= (unsigned __int64)off_1804AF000) )
    {
      off_1804AF020 = (_UNKNOWN **)((unsigned __int64)&off_1804AF020[v32 / 0xFFFFFFFFFFFFFFF8uLL] & 0xFFFFFFFFFFFFFFF8uLL);
    }
    else
    {
      v33 = bumpalo::Bump::alloc_layout_slow(v80, 8);
      if ( !v33 )
        bumpalo::alloc::handle_alloc_error(8, 16LL * (unsigned int)a20, v34, v35);
    }
  }
  else
  {
    v33 = 8;
    v79 = 4;
  }
  pperrinfo = (IErrorInfo *)v33;
  v85 = v80;
  v86 = (unsigned int)a20;
  v37 = 0;
  v38 = 0;
  while ( 1 )
  {
    v87 = v37;
    if ( v38 >= (unsigned int)a20 )
      break;
    v40 = *(_QWORD *)(a18 + 8 * v38);
    v41 = *(unsigned int *)(v40 + 8);
    if ( !*(_DWORD *)(v40 + 8) )
    {
      v42 = 4;
      if ( v37 != v86 )
        goto LABEL_21;
LABEL_28:
      bumpalo::collections::raw_vec::RawVec_shaping::ShapingTextRangeProperties_::reserve_internal_or_panic_shaping::ShapingTextRangeProperties_(&pperrinfo);
      v33 = (unsigned __int64)pperrinfo;
      v37 = v87;
      goto LABEL_21;
    }
    v42 = *(_QWORD *)v40;
    if ( !*(_QWORD *)v40 )
      core::panicking::panic(
        "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_ut"
        "ils\\src\\lib.rs",
        32,
        &off_1803491E0);
    if ( v37 == v86 )
      goto LABEL_28;
LABEL_21:
    ++v38;
    v39 = 16 * v37;
    *(_QWORD *)(v33 + v39) = v42;
    *(_QWORD *)(v33 + v39 + 8) = v41;
    ++v37;
  }
  v82 = v37;
  if ( v37 )
  {
    v43 = 8 * v37;
    v44 = v37;
    v45 = std::sys::alloc::windows::process_heap_alloc(0, 8 * v37);
    v46 = v78;
    if ( !v45 )
      alloc::alloc::handle_alloc_error(8, v43);
    v47 = v45;
    v48 = (v44 - 1) & 0xFFFFFFFFFFFFFFFLL;
    if ( v48 < 3 )
    {
      v49 = 0;
      v50 = v33;
      v29 = 0;
      goto LABEL_37;
    }
    v51 = v48 + 1;
    v49 = v51 & 0xFFFFFFFFFFFFFFFCuLL;
    v50 = v33 + 16 * (v51 & 0xFFFFFFFFFFFFFFFCuLL);
    v52 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v54 = _mm_load_si128((const __m128i *)&_xmm);
    v55 = v33;
    v29 = 0;
    do
    {
      v56 = _mm_shuffle_epi32((__m128i)v55, 68);
      *(__m128i *)(v47 + 8 * v52) = _mm_add_epi64(v56, si128);
      *(__m128i *)(v47 + 8 * v52 + 16) = _mm_add_epi64(v56, v54);
      v52 += 4;
      v55 += 64LL;
    }
    while ( v49 != v52 );
    if ( v51 != v49 )
    {
      do
      {
LABEL_37:
        *(_QWORD *)(v47 + 8 * v49) = v50;
        v50 += 16LL;
        ++v49;
      }
      while ( v50 != v33 + 16 * v44 );
    }
  }
  else
  {
    v47 = 8;
    v49 = 0;
    v29 = 0;
    v46 = v78;
  }
  v57 = *(_WORD *)a16;
  v58 = *(_DWORD *)(a16 + 4);
  v74 = v89;
  v89 = (LPVOID)v47;
  glyph_placements = shaping_cache::get_glyph_placements(
                       v76[0],
                       (int)v80,
                       (int)v77,
                       (int)lpMem,
                       (unsigned int)a5,
                       v46,
                       (unsigned int)a5,
                       (__int64)v74,
                       (unsigned int)a5,
                       a10,
                       a11,
                       a12,
                       ((a13 | 0x200000000uLL) - 1) >> 32,
                       a14 != 0,
                       a15 != 0,
                       v57,
                       v58,
                       (__int64)v75,
                       v47,
                       v49,
                       v79,
                       (unsigned int)a20,
                       a6,
                       (unsigned int)a8,
                       a7,
                       (unsigned int)a8,
                       a21,
                       (unsigned int)a8,
                       a22,
                       (unsigned int)a8);
  v60 = glyph_placements + 4;
  v61 = glyph_placements;
  v62 = v82;
  switch ( v60 )
  {
    case 0:
      v36 = -2003283968;
      goto LABEL_56;
    case 1:
    case 2:
      v36 = -2147024774;
      if ( !v82 )
        goto LABEL_58;
      goto LABEL_57;
    case 3:
      v36 = -2147024809;
      if ( !v82 )
        goto LABEL_58;
      goto LABEL_57;
    case 4:
      if ( v82 )
      {
        v63 = GetProcessHeap();
        HeapFree(v63, 0, v89);
      }
      if ( v86 )
      {
        v64 = *((_QWORD *)v85 + 2);
        if ( *(_QWORD *)(v64 + 32) == v33 )
          *(_QWORD *)(v64 + 32) = 16 * v86 + v33;
      }
      v65 = v81;
      v22 = a9;
      while ( v65 != (unsigned __int64 *)&off_1804AF000 )
      {
        a2 = *v65;
        if ( v65[1] >= 0x11 )
          a2 = *(_QWORD *)(a2 - 8);
        v65 = (unsigned __int64 *)v65[3];
        v66 = GetProcessHeap();
        HeapFree(v66, 0, (LPVOID)a2);
      }
      goto LABEL_54;
    default:
      v36 = -2003283967;
      v62 = v82;
      if ( v61 == -101 )
      {
        v36 = -2147467263;
        if ( !v82 )
          goto LABEL_58;
      }
      else
      {
LABEL_56:
        if ( !v62 )
          goto LABEL_58;
      }
LABEL_57:
      v67 = GetProcessHeap();
      HeapFree(v67, 0, v89);
LABEL_58:
      if ( v86 )
      {
        v68 = *((_QWORD *)v85 + 2);
        if ( *(_QWORD *)(v68 + 32) == v33 )
          *(_QWORD *)(v68 + 32) = 16 * v86 + v33;
      }
      v69 = v81;
      while ( v69 != (unsigned __int64 *)&off_1804AF000 )
      {
        v71 = (_QWORD *)*v69;
        if ( v69[1] >= 0x11 )
          v71 = (_QWORD *)*(v71 - 1);
        v69 = (unsigned __int64 *)v69[3];
        v70 = GetProcessHeap();
        HeapFree(v70, 0, v71);
      }
      a2 = 0;
      v22 = a9;
      break;
  }
LABEL_67:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v36 )
  {
    if ( a2 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)a2 + 16LL))(a2);
    return v36;
  }
  return v29;
}

```

## disassembly

```asm
0x1800064c0  push    rbp
0x1800064c1  push    r15
0x1800064c3  push    r14
0x1800064c5  push    r13
0x1800064c7  push    r12
0x1800064c9  push    rsi
0x1800064ca  push    rdi
0x1800064cb  push    rbx
0x1800064cc  sub     rsp, 1B8h
0x1800064d3  lea     rbp, [rsp+80h]
0x1800064db  movaps  [rbp+170h+var_50], xmm7
0x1800064e2  movaps  [rbp+170h+var_60], xmm6
0x1800064e9  mov     [rbp+170h+var_70], 0FFFFFFFFFFFFFFFEh
0x1800064f4  mov     r15, [rbp+170h+arg_40]
0x1800064fb  test    r15, r15
0x1800064fe  jz      loc_180006C91
0x180006504  mov     r12, r9
0x180006507  mov     r14, r8
0x18000650a  mov     rdi, rdx
0x18000650d  mov     rax, [r15]
0x180006510  mov     rax, [rax+8]
0x180006514  mov     rcx, r15
0x180006517  call    cs:__guard_dispatch_icall_fptr
0x18000651d  mov     qword ptr [rbp+170h+var_C8], 0
0x180006528  mov     rax, [r15]
0x18000652b  mov     rax, [rax]
0x18000652e  lea     rdx, dword_1803B3704
0x180006535  lea     r13, [rbp+170h+var_C8]
0x18000653c  mov     rcx, r15
0x18000653f  mov     r8, r13
0x180006542  call    cs:__guard_dispatch_icall_fptr
0x180006548  test    eax, eax
0x18000654a  js      loc_180006C9F
0x180006550  mov     rbx, qword ptr [rbp+170h+var_C8]
0x180006557  test    rbx, rbx
0x18000655a  jz      loc_180006CA3
0x180006560  mov     rsi, [rbp+170h+arg_80]
0x180006567  mov     rax, [rbx]
0x18000656a  mov     rax, [rax+220h]
0x180006571  mov     rcx, rbx
0x180006574  call    cs:__guard_dispatch_icall_fptr
0x18000657a  mov     qword ptr [rbp+170h+var_E0], rax
0x180006581  test    rsi, rsi
0x180006584  mov     [rbp+170h+var_80], rbx
0x18000658b  mov     [rbp+170h+var_78], r12
0x180006592  jz      short loc_1800065E5
0x180006594  lea     rcx, [rbp+170h+pperrinfo]
0x18000659b  mov     rdx, rsi
0x18000659e  call    dwrite__wchar__utf16__string_from_cwstr
0x1800065a3  mov     rdx, [rbp+170h+var_98]
0x1800065aa  mov     r8, [rbp+170h+var_90]
0x1800065b1  lea     rcx, [rbp+170h+var_100]
0x1800065b5  mov     [rbp+170h+lpMem], rdx
0x1800065bc  call    langtag__parse_language_tag
0x1800065c1  cmp     [rbp+170h+pperrinfo], 0
0x1800065c9  jz      short loc_1800065EE
0x1800065cb  call    cs:__imp_GetProcessHeap
0x1800065d1  mov     rcx, rax; hHeap
0x1800065d4  xor     edx, edx; dwFlags
0x1800065d6  mov     r8, [rbp+170h+lpMem]; lpMem
0x1800065dd  call    cs:__imp_HeapFree
0x1800065e3  jmp     short loc_1800065EE
0x1800065e5  pxor    xmm0, xmm0
0x1800065e9  movdqa  xmmword ptr [rbp+170h+var_100], xmm0
0x1800065ee  xor     r12d, r12d
0x1800065f1  cmp     dword ptr [rbp+170h+arg_38], 0
0x1800065f8  jz      loc_180006B26
0x1800065fe  cmp     dword ptr [rbp+170h+arg_20], 0
0x180006605  jz      loc_1800066E7
0x18000660b  mov     rcx, qword ptr [rbp+170h+var_E0]
0x180006612  mov     rax, [rcx]
0x180006615  mov     rax, [rax+128h]
0x18000661c  call    cs:__guard_dispatch_icall_fptr
0x180006622  test    rax, rax
0x180006625  jz      loc_180006C66
0x18000662b  mov     rcx, [rax]
0x18000662e  mov     rdx, [rcx+90h]
0x180006635  mov     rcx, rax
0x180006638  mov     rax, rdx
0x18000663b  call    cs:__guard_dispatch_icall_fptr
0x180006641  test    rax, rax
0x180006644  jz      loc_180006C77
0x18000664a  mov     qword ptr [rbp+170h+var_E8], rax
0x180006651  mov     [rbp+170h+lpMem], rdi
0x180006658  mov     eax, dword ptr [rbp+170h+arg_98]
0x18000665e  mov     qword ptr [rbp+170h+var_C8], 0
0x180006669  lea     rcx, off_1804AF000
0x180006670  mov     [rbp+170h+var_B8], rcx
0x180006677  mov     edi, eax
0x180006679  test    eax, eax
0x18000667b  mov     [rbp+170h+var_D8], r14
0x180006682  jz      loc_180006713
0x180006688  mov     rax, [rbp+170h+arg_90]
0x18000668f  mov     [rbp+170h+var_D0], rax
0x180006696  mov     r12, rdi
0x180006699  shl     r12, 4
0x18000669d  mov     r15, cs:off_1804AF020
0x1800066a4  cmp     r12, r15
0x1800066a7  ja      short loc_1800066B9
0x1800066a9  sub     r15, r12
0x1800066ac  and     r15, 0FFFFFFFFFFFFFFF8h
0x1800066b0  cmp     r15, cs:off_1804AF000
0x1800066b7  jnb     short loc_180006727
0x1800066b9  lea     rcx, [rbp+170h+var_C8]
0x1800066c0  mov     edx, 8
0x1800066c5  mov     r8, r12
0x1800066c8  call    bumpalo__Bump__alloc_layout_slow
0x1800066cd  mov     r15, rax
0x1800066d0  test    rax, rax
0x1800066d3  jnz     short loc_18000672E
0x1800066d5  mov     ecx, 8
0x1800066da  mov     rdx, r12
0x1800066dd  call    bumpalo__alloc__handle_alloc_error
0x1800066e2  jmp     loc_180006D10
0x1800066e7  mov     [rbp+170h+pperrinfo], 0
0x1800066f2  lea     rdx, [rbp+170h+pperrinfo]; pperrinfo
0x1800066f9  xor     ecx, ecx; dwReserved
0x1800066fb  call    cs:__imp_GetErrorInfo
0x180006701  mov     rdi, [rbp+170h+pperrinfo]
0x180006708  mov     r14d, 80070057h
0x18000670e  jmp     loc_180006BCF
0x180006713  mov     r15d, 8
0x180006719  mov     eax, 4
0x18000671e  mov     [rbp+170h+var_D0], rax
0x180006725  jmp     short loc_18000672E
0x180006727  mov     cs:off_1804AF020, r15
0x18000672e  mov     r12, [rbp+170h+arg_88]
0x180006735  movss   xmm7, [rbp+170h+arg_50]
0x18000673d  movss   xmm6, [rbp+170h+arg_48]
0x180006745  mov     [rbp+170h+pperrinfo], r15
0x18000674c  mov     [rbp+170h+var_98], r13
0x180006753  mov     [rbp+170h+var_90], rdi
0x18000675a  xor     edx, edx
0x18000675c  lea     r13, [rbp+170h+pperrinfo]
0x180006763  xor     r14d, r14d
0x180006766  jmp     short loc_180006786
0x180006770  inc     r14
0x180006773  mov     rax, rdx
0x180006776  shl     rax, 4
0x18000677a  mov     [r15+rax], rbx
0x18000677e  mov     [r15+rax+8], rsi
0x180006783  inc     rdx
0x180006786  mov     [rbp+170h+var_88], rdx
0x18000678d  cmp     r14, rdi
0x180006790  jnb     short loc_1800067E6
0x180006792  mov     rax, [r12+r14*8]
0x180006796  mov     esi, [rax+8]
0x180006799  test    rsi, rsi
0x18000679c  jz      short loc_1800067C0
0x18000679e  mov     rbx, [rax]
0x1800067a1  test    rbx, rbx
0x1800067a4  jz      loc_180006C49
0x1800067aa  cmp     rdx, [rbp+170h+var_90]
0x1800067b1  jnz     short loc_180006770
0x1800067b3  jmp     short loc_1800067CE
0x1800067c0  mov     ebx, 4
0x1800067c5  cmp     rdx, [rbp+170h+var_90]
0x1800067cc  jnz     short loc_180006770
0x1800067ce  mov     rcx, r13
0x1800067d1  call    bumpalo__collections__raw_vec__RawVec_shaping__ShapingTextRangeProperties___reserve_internal_or_panic_shaping__ShapingTextRangeProperties_
0x1800067d6  mov     r15, [rbp+170h+pperrinfo]
0x1800067dd  mov     rdx, [rbp+170h+var_88]
0x1800067e4  jmp     short loc_180006770
0x1800067e6  test    rdx, rdx
0x1800067e9  mov     [rbp+170h+var_B0], rdx
0x1800067f0  jz      short loc_180006848
0x1800067f2  lea     r12, ds:0[rdx*8]
0x1800067fa  xor     ecx, ecx
0x1800067fc  mov     rsi, rdx
0x1800067ff  mov     rdx, r12
0x180006802  call    std__sys__alloc__windows__process_heap_alloc
0x180006807  test    rax, rax
0x18000680a  lea     r13, off_1804AF000
0x180006811  mov     r11, [rbp+170h+var_D8]
0x180006818  jz      loc_180006D03
0x18000681e  mov     rbx, rax
0x180006821  lea     rax, [rsi-1]
0x180006825  mov     rdx, 0FFFFFFFFFFFFFFFh
0x18000682f  and     rdx, rax
0x180006832  cmp     rdx, 3
0x180006836  mov     r10, rsi
0x180006839  jnb     short loc_180006865
0x18000683b  xor     eax, eax
0x18000683d  mov     rcx, r15
0x180006840  xor     r12d, r12d
0x180006843  jmp     loc_1800068D5
0x180006848  mov     ebx, 8
0x18000684d  xor     eax, eax
0x18000684f  xor     r12d, r12d
0x180006852  lea     r13, off_1804AF000
0x180006859  mov     r11, [rbp+170h+var_D8]
0x180006860  jmp     loc_1800068F0
0x180006865  inc     rdx
0x180006868  mov     rax, rdx
0x18000686b  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000686f  mov     rcx, rax
0x180006872  shl     rcx, 4
0x180006876  add     rcx, r15
0x180006879  xor     r8d, r8d
0x18000687c  movdqa  xmm0, cs:__xmm@00000000000000100000000000000000
0x180006884  movdqa  xmm1, cs:__xmm@00000000000000300000000000000020
0x18000688c  mov     r9, r15
0x18000688f  xor     r12d, r12d
0x180006892  nop     word ptr [rax+rax+00000000h]
0x1800068a0  movq    xmm2, r9
0x1800068a5  pshufd  xmm2, xmm2, 44h ; 'D'
0x1800068aa  movdqa  xmm3, xmm2
0x1800068ae  paddq   xmm3, xmm0
0x1800068b2  paddq   xmm2, xmm1
0x1800068b6  movdqu  xmmword ptr [rbx+r8*8], xmm3
0x1800068bc  movdqu  xmmword ptr [rbx+r8*8+10h], xmm2
0x1800068c3  add     r8, 4
0x1800068c7  add     r9, 40h ; '@'
0x1800068cb  cmp     rax, r8
0x1800068ce  jnz     short loc_1800068A0
0x1800068d0  cmp     rdx, rax
0x1800068d3  jz      short loc_1800068F0
0x1800068d5  mov     rdx, r10
0x1800068d8  shl     rdx, 4
0x1800068dc  add     rdx, r15
0x1800068df  nop
0x1800068e0  mov     [rbx+rax*8], rcx
0x1800068e4  add     rcx, 10h
0x1800068e8  inc     rax
0x1800068eb  cmp     rcx, rdx
0x1800068ee  jnz     short loc_1800068E0
0x1800068f0  mov     ecx, dword ptr [rbp+170h+arg_20]
0x1800068f6  mov     r8d, dword ptr [rbp+170h+arg_38]
0x1800068fd  cmp     [rbp+170h+arg_60], 1
0x180006904  mov     edx, 2
0x180006909  sbb     edx, 0
0x18000690c  mov     r10, [rbp+170h+arg_78]
0x180006913  movzx   r9d, word ptr [r10]
0x180006917  mov     r10d, [r10+4]
0x18000691b  cmp     [rbp+170h+arg_70], 0
0x180006922  setnz   [rsp+1F0h+var_180]
0x180006927  cmp     [rbp+170h+arg_68], 0
0x18000692e  mov     rsi, [rbp+170h+arg_A8]
0x180006935  mov     [rsp+1F0h+var_110], rsi; void *
0x18000693d  mov     rsi, [rbp+170h+arg_A0]
0x180006944  mov     [rsp+1F0h+var_120], rsi; void *
0x18000694c  mov     rsi, [rbp+170h+arg_30]
0x180006953  mov     [rsp+1F0h+var_130], rsi; __int64
0x18000695b  mov     [rsp+1F0h+var_108], r8; __int64
0x180006963  mov     [rsp+1F0h+var_118], r8; __int64
0x18000696b  mov     [rsp+1F0h+var_128], r8; __int64
0x180006973  mov     [rsp+1F0h+var_138], r8; __int64
0x18000697b  mov     r8, [rbp+170h+arg_28]
0x180006982  mov     [rsp+1F0h+var_140], r8; __int64
0x18000698a  mov     [rsp+1F0h+var_148], rdi; __int64
0x180006992  mov     r8, [rbp+170h+var_D0]
0x180006999  mov     [rsp+1F0h+var_150], r8; __int64
0x1800069a1  mov     [rsp+1F0h+var_158], rax; __int64
0x1800069a9  lea     rax, [rbp+170h+var_100]
0x1800069ad  mov     [rsp+1F0h+var_168], rax; __int64
0x1800069b5  mov     dword ptr [rsp+1F0h+var_170], r10d; char
0x1800069bd  mov     [rsp+1F0h+var_178], r9w; __int16
0x1800069c3  mov     [rsp+1F0h+var_190], edx; int
0x1800069c7  mov     rax, [rbp+170h+arg_58]
0x1800069ce  mov     [rsp+1F0h+var_198], rax; __int64
0x1800069d3  mov     rax, [rbp+170h+var_78]
0x1800069da  mov     [rsp+1F0h+var_1B8], rax; __int64
0x1800069df  mov     [rbp+170h+var_78], rbx
0x1800069e6  mov     [rsp+1F0h+var_160], rbx; __int64
0x1800069ee  setnz   [rsp+1F0h+var_188]
0x1800069f3  movss   [rsp+1F0h+var_1A0], xmm7; int
0x1800069f9  movss   [rsp+1F0h+var_1A8], xmm6; int
0x1800069ff  mov     [rsp+1F0h+var_1B0], rcx; __int64
0x180006a04  mov     [rsp+1F0h+var_1C0], rcx; __int64
0x180006a09  mov     [rsp+1F0h+var_1C8], r11; __int64
0x180006a0e  mov     [rsp+1F0h+var_1D0], rcx; __int64
0x180006a13  lea     rdx, [rbp+170h+var_C8]; int
0x180006a1a  lea     r8, [rbp+170h+var_E0]; int
0x180006a21  mov     r9, [rbp+170h+lpMem]; int
0x180006a28  mov     rcx, qword ptr [rbp+170h+var_E8]; int
0x180006a2f  call    shaping_cache__get_glyph_placements
0x180006a34  lea     ecx, [rax+4]; switch 5 cases
0x180006a37  cmp     ecx, 4
0x180006a3a  ja      short def_180006A51; jumptable 0000000180006A51 default case
0x180006a3c  lea     rax, jpt_180006A51
0x180006a43  movsxd  rcx, ds:(jpt_180006A51 - 180406360h)[rax+rcx*4]
0x180006a47  add     rcx, rax
0x180006a4a  mov     rax, [rbp+170h+var_B0]
0x180006a51  jmp     rcx; switch jump
0x180006a53  mov     r14d, 8007007Ah; jumptable 0000000180006A51 cases -3,-2
0x180006a59  test    rax, rax
0x180006a5c  jnz     loc_180006B39
0x180006a62  jmp     loc_180006B51
0x180006a67  mov     r14d, 88985001h; jumptable 0000000180006A51 default case
0x180006a6d  cmp     eax, 0FFFFFF9Bh
0x180006a70  mov     rax, [rbp+170h+var_B0]
0x180006a77  jnz     loc_180006B34
0x180006a7d  mov     r14d, 80004001h
0x180006a83  test    rax, rax
0x180006a86  jnz     loc_180006B39
0x180006a8c  jmp     loc_180006B51
0x180006a91  test    rax, rax; jumptable 0000000180006A51 case 0
0x180006a94  jz      short loc_180006AAE
0x180006a96  call    cs:__imp_GetProcessHeap
0x180006a9c  mov     rcx, rax; hHeap
  ... truncated ...
```
