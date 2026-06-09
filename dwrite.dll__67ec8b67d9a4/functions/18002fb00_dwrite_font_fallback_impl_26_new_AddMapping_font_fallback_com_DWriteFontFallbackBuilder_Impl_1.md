# dwrite::font_fallback::impl$26::new::AddMapping_font_fallback_com::DWriteFontFallbackBuilder_Impl__1_

- ea: `0x18002fb00`
- end: `0x18003021f`
- name: `dwrite::font_fallback::impl$26::new::AddMapping_font_fallback_com::DWriteFontFallbackBuilder_Impl__1_`
- size: `1823`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180029d10`
- `0x180029de0`
- `0x180029ea0`
- `0x18002e1c0`
- `0x18002f450`
- `0x18002fb00`
- `0x1800d97e0`
- `0x1800dc910`
- `0x180115c30`
- `0x180316190`
- `0x180316255`
- `0x180316ae0`
- `0x180316dc0`

## import_xrefs

- `kernel32!HeapFree` at `0x1800300b3`
- `kernel32!HeapFree` at `0x1800300d2`
- `kernel32!HeapFree` at `0x1800300ec`
- `kernel32!HeapFree` at `0x180030140`
- `kernel32!HeapFree` at `0x180030159`
- `kernel32!HeapFree` at `0x1800301ac`
- `kernel32!HeapFree` at `0x1800300b3`
- `kernel32!HeapFree` at `0x1800300d2`
- `kernel32!HeapFree` at `0x1800300ec`
- `kernel32!HeapFree` at `0x18003010a`
- `kernel32!HeapFree` at `0x180030159`
- `kernel32!HeapFree` at `0x1800301ac`
- `kernel32!GetProcessHeap` at `0x1800300a5`
- `kernel32!GetProcessHeap` at `0x1800300c4`
- `kernel32!GetProcessHeap` at `0x1800300dd`
- `kernel32!GetProcessHeap` at `0x180030135`
- `kernel32!GetProcessHeap` at `0x18003014b`
- `kernel32!GetProcessHeap` at `0x18003019e`
- `kernel32!GetProcessHeap` at `0x1800300a5`
- `kernel32!GetProcessHeap` at `0x1800300c4`
- `kernel32!GetProcessHeap` at `0x1800300dd`
- `kernel32!GetProcessHeap` at `0x180030103`
- `kernel32!GetProcessHeap` at `0x18003014b`
- `kernel32!GetProcessHeap` at `0x18003019e`

## string_xrefs

- `0x1800301e7`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x1800301cd`: `assertion failed: !p.is_null()called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\os\out\rust\cargo_home\amd64fre\registry\src\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\windows-core-0.62.2\src\imp\ref_count.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=2
__int64 __fastcall dwrite::font_fallback::impl_26::new::AddMapping_font_fallback_com::DWriteFontFallbackBuilder_Impl__1_(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        float a9)
{
  __int64 v11; // r15
  unsigned __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  bool v17; // zf
  __int64 v18; // rsi
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rcx
  char *v22; // rdx
  _QWORD *v23; // rsi
  __int64 v24; // r8
  __int64 v25; // r8
  _QWORD *v26; // rbx
  _QWORD *v27; // r14
  char *v28; // rsi
  char *v29; // rdi
  char *v30; // rax
  _QWORD *v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int16 string_index; // r12
  __int64 v35; // r13
  __int64 v36; // rsi
  __int64 v37; // rax
  __int64 v38; // r13
  _QWORD *v39; // rbx
  __int64 v40; // rdi
  _QWORD *v41; // r14
  _QWORD *v42; // rdi
  unsigned int *v43; // rbx
  _DWORD *v44; // rax
  _QWORD *v45; // r14
  unsigned int v46; // edx
  unsigned int v47; // r15d
  unsigned int v48; // eax
  __int64 v49; // rax
  __int16 *v50; // r12
  __int16 *v51; // rdi
  __int16 *v52; // rax
  __int64 v53; // rbx
  _QWORD *v54; // rdx
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rsi
  __int16 v58; // r13
  __int64 v59; // rsi
  void *v60; // rdi
  HANDLE ProcessHeap; // rax
  void *v62; // rdi
  HANDLE v63; // rax
  HANDLE v64; // rax
  void *v65; // rdi
  __int64 v66; // r15
  void **v67; // r12
  void *v68; // rbx
  HANDLE v69; // rax
  HANDLE v70; // rax
  __int64 v72; // [rsp+28h] [rbp-58h] BYREF
  LPVOID v73; // [rsp+30h] [rbp-50h]
  __int64 v74; // [rsp+38h] [rbp-48h]
  __int64 v75; // [rsp+40h] [rbp-40h] BYREF
  LPVOID v76; // [rsp+48h] [rbp-38h]
  __int64 v77; // [rsp+50h] [rbp-30h]
  LPVOID v78; // [rsp+58h] [rbp-28h]
  __int64 v79; // [rsp+60h] [rbp-20h]
  LPVOID v80; // [rsp+68h] [rbp-18h]
  unsigned int *v81; // [rsp+70h] [rbp-10h]
  LPVOID lpMem[2]; // [rsp+78h] [rbp-8h] BYREF
  unsigned int *v83; // [rsp+88h] [rbp+8h]
  __int64 v84; // [rsp+90h] [rbp+10h]
  LPVOID v85; // [rsp+98h] [rbp+18h]
  __int64 v86; // [rsp+A0h] [rbp+20h]
  unsigned __int64 v87; // [rsp+A8h] [rbp+28h]
  LPVOID v88; // [rsp+B0h] [rbp+30h]
  _QWORD *v89; // [rsp+B8h] [rbp+38h]
  __int64 v90; // [rsp+C0h] [rbp+40h]

  v90 = -2;
  if ( a3 )
  {
    if ( !a2 )
      core::panicking::panic(
        "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_ut"
        "ils\\src\\lib.rs",
        32,
        &off_1803491E0);
    v84 = a2;
    v88 = (LPVOID)a3;
  }
  else
  {
    v84 = 4;
    v88 = 0;
  }
  if ( a5 )
  {
    v11 = std::sys::alloc::windows::process_heap_alloc(0, 24LL * a5);
    if ( !v11 )
      alloc::alloc::handle_alloc_error(8, 24LL * a5);
  }
  else
  {
    v11 = 8;
  }
  v89 = a1;
  v87 = (unsigned __int64)(a1 - 1);
  v75 = a5;
  v76 = (LPVOID)v11;
  v77 = 0;
  v86 = 0;
  v12 = 0;
  while ( v12 < a5 )
  {
    v15 = *(_QWORD *)(a4 + 8 * v12);
    if ( !v15 )
      core::panicking::panic(
        "assertion failed: !p.is_null()called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\o"
        "ut\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0."
        "62.2\\src\\imp\\ref_count.rs",
        30,
        &off_180349218);
    ++v12;
    v16 = 0;
    do
      v17 = *(_WORD *)(v15 + 2 * v16++) == 0;
    while ( !v17 );
    widestring::ucstr::U16CStr::to_string_lossy(lpMem, v15, v16);
    if ( v86 == v75 )
    {
      alloc::raw_vec::RawVec_alloc::string::String_alloc::alloc::Global_::grow_one_alloc::string::String_alloc::alloc::Global_(&v75);
      v11 = (__int64)v76;
    }
    v13 = v86;
    v14 = 3 * v86;
    *(_QWORD *)(v11 + 8 * v14 + 16) = v83;
    *(_OWORD *)(v11 + 8 * v14) = *(_OWORD *)lpMem;
    v86 = v13 + 1;
    v77 = v13 + 1;
  }
  v18 = v86;
  v19 = 16 * v86;
  if ( !v86 )
  {
    v85 = (LPVOID)8;
    goto LABEL_26;
  }
  v85 = (LPVOID)std::sys::alloc::windows::process_heap_alloc(0, 16 * v86);
  if ( !v85 )
    alloc::alloc::handle_alloc_error(8, v19);
  if ( v18 == 1 )
  {
    v20 = 0;
LABEL_25:
    *((_OWORD *)v85 + v20) = *(_OWORD *)(v11 + 24 * v20 + 8);
    goto LABEL_26;
  }
  v21 = v11 + 40;
  v22 = (char *)v85 + 24;
  v20 = 0;
  do
  {
    *(_OWORD *)(v22 - 24) = *(_OWORD *)(v21 - 32);
    *(_OWORD *)(v22 - 8) = *(_OWORD *)(v21 - 8);
    v20 += 2;
    v21 += 48;
    v22 += 32;
  }
  while ( (v18 & 0xFFFFFFFFFFFFFFFEuLL) != v20 );
  if ( (v18 & 1) != 0 )
    goto LABEL_25;
LABEL_26:
  v23 = v89;
  if ( !a7 )
  {
    v72 = 0;
    v73 = (LPVOID)1;
    v74 = 0;
    if ( a8 )
      goto LABEL_30;
LABEL_47:
    lpMem[0] = 0;
    lpMem[1] = (LPVOID)1;
    v83 = 0;
    if ( !v23[2] )
      goto LABEL_33;
LABEL_48:
    core::cell::panic_already_borrowed(&off_1803366E8);
  }
  v24 = 0;
  do
    v17 = *(_WORD *)(a7 + 2 * v24++) == 0;
  while ( !v17 );
  widestring::ucstr::U16CStr::to_string_lossy(&v72, a7, v24);
  if ( !a8 )
    goto LABEL_47;
LABEL_30:
  v25 = 0;
  do
    v17 = *(_WORD *)(a8 + 2 * v25++) == 0;
  while ( !v17 );
  widestring::ucstr::U16CStr::to_string_lossy(lpMem, a8, v25);
  if ( v23[2] )
    goto LABEL_48;
LABEL_33:
  v26 = v23 + 3;
  v23[2] = -1;
  v78 = v73;
  v79 = v74;
  v80 = lpMem[1];
  v81 = v83;
  v23[12] = 0;
  if ( v86 )
  {
    v27 = v89 + 10;
    v28 = (char *)v85;
    v29 = (char *)v85 + v19;
    v30 = (char *)v85 + 16;
    do
    {
      v32 = *(_QWORD *)v28;
      v33 = *((_QWORD *)v28 + 1);
      v28 = v30;
      string_index = font_fallback::builder::CoalescedStrings::get_string_index(v26, v32, v33);
      v35 = v89[12];
      if ( v35 == v89[10] )
        alloc::raw_vec::RawVec_u16_alloc::alloc::Global_::grow_one_u16_alloc::alloc::Global_(v27, &off_180336288);
      v30 = &v28[16 * (v28 != v29)];
      v31 = v89;
      *(_WORD *)(v89[11] + 2 * v35) = string_index;
      v31[12] = v35 + 1;
    }
    while ( v28 != v29 );
  }
  LOWORD(v78) = font_fallback::builder::CoalescedStrings::get_string_index(v26, v78, v79);
  LOWORD(v79) = font_fallback::builder::CoalescedStrings::get_string_index(v26, v80, v81);
  if ( a6 )
  {
    v36 = v89[14];
    v37 = v89[15];
    v38 = v37;
    if ( v37 )
    {
      v39 = (_QWORD *)(v36 + 8 * v37);
      v40 = 0;
      v41 = (_QWORD *)v89[14];
      while ( !(unsigned __int8)windows_core::unknown::impl_3::eq(*v41, a6) )
      {
        ++v41;
        ++v40;
        if ( v41 == v39 )
          goto LABEL_43;
      }
      v38 = v40;
      v43 = (unsigned int *)v84;
    }
    else
    {
LABEL_43:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 8LL))(a6);
      v42 = v89;
      v43 = (unsigned int *)v84;
      if ( v38 == v89[13] )
      {
        alloc::raw_vec::RawVec_dwrite::font_collection::IDWriteFontCollection_alloc::alloc::Global_::grow_one_dwrite::font_collection::IDWriteFontCollection_alloc::alloc::Global_(
          v89 + 13,
          &off_180336258);
        v36 = v42[14];
      }
      *(_QWORD *)(v36 + 8 * v38) = a6;
      v42[15] = v38 + 1;
    }
    LOBYTE(v38) = v38 + 1;
  }
  else
  {
    v38 = 0;
    v43 = (unsigned int *)v84;
  }
  if ( v88 )
  {
    LODWORD(v80) = (int)fminf(255.0, fmaxf(0.0, a9 * 64.0));
    v81 = &v43[2 * (_QWORD)v88];
    v44 = v43 + 2;
    v45 = v89 + 16;
    do
    {
      v46 = *v43;
      v47 = v43[1];
      v84 = (__int64)v44;
      v48 = 1114111;
      if ( v47 < 0x10FFFF )
        v48 = v47;
      LODWORD(v88) = v46;
      if ( v46 <= v48 )
      {
        v49 = v89[12];
        if ( v49 )
        {
          v50 = (__int16 *)v89[11];
          v51 = &v50[v49];
          v52 = v50 + 1;
          v53 = v89[18];
          do
          {
            v57 = v38;
            v58 = *v50;
            v50 = v52;
            if ( v53 == *v45 )
              alloc::raw_vec::RawVec_font_fallback::builder::MappedRange_alloc::alloc::Global_::grow_one_font_fallback::builder::MappedRange_alloc::alloc::Global_(
                v45,
                &off_180336270);
            v54 = v89;
            v55 = v89[17];
            v56 = 3 * v53;
            *(_QWORD *)(v55 + 8 * v56) = v53;
            *(_DWORD *)(v55 + 8 * v56 + 8) = (_DWORD)v88;
            *(_DWORD *)(v55 + 8 * v56 + 12) = v47;
            *(_WORD *)(v55 + 8 * v56 + 16) = v58;
            v38 = v57;
            *(_BYTE *)(v55 + 8 * v56 + 18) = v57;
            *(_BYTE *)(v55 + 8 * v56 + 19) = (_BYTE)v80;
            *(_WORD *)(v55 + 8 * v56 + 20) = (_WORD)v78;
            *(_WORD *)(v55 + 8 * v56 + 22) = v79;
            v54[18] = ++v53;
            v52 = &v50[v50 != v51];
          }
          while ( v50 != v51 );
        }
      }
      v43 = (unsigned int *)v84;
      v44 = (_DWORD *)(v84 + 8LL * (v84 != (_QWORD)v81));
    }
    while ( (unsigned int *)v84 != v81 );
  }
  ++v89[2];
  v87 &= 0xFFFFFFFF00000000uLL;
  v88 = 0;
  LODWORD(v89) = 0;
  v59 = v86;
  if ( lpMem[0] )
  {
    v60 = lpMem[1];
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v60);
  }
  if ( v72 )
  {
    v62 = v73;
    v63 = GetProcessHeap();
    HeapFree(v63, 0, v62);
  }
  if ( v59 )
  {
    v64 = GetProcessHeap();
    HeapFree(v64, 0, v85);
  }
  v65 = v76;
  v66 = v77;
  if ( v77 )
  {
    v67 = (void **)((char *)v76 + 8);
    do
    {
      if ( *(v67 - 1) )
      {
        v68 = *v67;
        v69 = GetProcessHeap();
        HeapFree(v69, 0, v68);
      }
      v67 += 3;
      --v66;
    }
    while ( v66 );
  }
  if ( v75 )
  {
    v70 = GetProcessHeap();
    HeapFree(v70, 0, v65);
  }
  return (unsigned int)v89;
}

```

## disassembly

```asm
0x18002fb00  push    rbp
0x18002fb01  push    r15
0x18002fb03  push    r14
0x18002fb05  push    r13
0x18002fb07  push    r12
0x18002fb09  push    rsi
0x18002fb0a  push    rdi
0x18002fb0b  push    rbx
0x18002fb0c  sub     rsp, 0E8h
0x18002fb13  lea     rbp, [rsp+80h]
0x18002fb1b  movaps  [rbp+0A0h+var_50], xmm6
0x18002fb1f  mov     [rbp+0A0h+var_60], 0FFFFFFFFFFFFFFFEh
0x18002fb27  mov     rdi, r9
0x18002fb2a  mov     rsi, rcx
0x18002fb2d  test    r8d, r8d
0x18002fb30  jz      short loc_18002FB48
0x18002fb32  test    rdx, rdx
0x18002fb35  jz      loc_1800301E7
0x18002fb3b  mov     [rbp+0A0h+var_90], rdx
0x18002fb3f  mov     eax, r8d
0x18002fb42  mov     [rbp+0A0h+var_70], rax
0x18002fb46  jmp     short loc_18002FB59
0x18002fb48  mov     eax, 4
0x18002fb4d  mov     [rbp+0A0h+var_90], rax
0x18002fb51  mov     [rbp+0A0h+var_70], 0
0x18002fb59  mov     eax, [rbp+0A0h+arg_20]
0x18002fb5f  mov     ebx, eax
0x18002fb61  test    eax, eax
0x18002fb63  jz      short loc_18002FB95
0x18002fb65  lea     rax, ds:0[rbx*8]
0x18002fb6d  lea     r14, [rax+rax*2]
0x18002fb71  xor     ecx, ecx
0x18002fb73  mov     rdx, r14
0x18002fb76  call    std__sys__alloc__windows__process_heap_alloc
0x18002fb7b  mov     r15, rax
0x18002fb7e  test    rax, rax
0x18002fb81  jnz     short loc_18002FB9B
0x18002fb83  mov     ecx, 8
0x18002fb88  mov     rdx, r14
0x18002fb8b  call    alloc__alloc__handle_alloc_error
0x18002fb90  jmp     loc_18003020E
0x18002fb95  mov     r15d, 8
0x18002fb9b  movss   xmm6, [rbp+0A0h+arg_40]
0x18002fba3  mov     r14, [rbp+0A0h+arg_30]
0x18002fbaa  mov     [rbp+0A0h+var_68], rsi
0x18002fbae  lea     rax, [rsi-8]
0x18002fbb2  mov     [rbp+0A0h+var_78], rax
0x18002fbb6  mov     [rbp+0A0h+var_E0], rbx
0x18002fbba  mov     [rbp+0A0h+var_D8], r15
0x18002fbbe  mov     [rbp+0A0h+var_D0], 0
0x18002fbc6  mov     [rbp+0A0h+var_80], 0
0x18002fbce  lea     r12, [rbp+0A0h+lpMem]
0x18002fbd2  lea     r13, [rbp+0A0h+var_E0]
0x18002fbd6  xor     esi, esi
0x18002fbd8  jmp     short loc_18002FC05
0x18002fbe0  mov     rdx, [rbp+0A0h+var_80]
0x18002fbe4  lea     rax, [rdx+rdx*2]
0x18002fbe8  mov     rcx, [rbp+0A0h+var_98]
0x18002fbec  mov     [r15+rax*8+10h], rcx
0x18002fbf1  movups  xmm0, xmmword ptr [rbp+0A0h+lpMem]
0x18002fbf5  movups  xmmword ptr [r15+rax*8], xmm0
0x18002fbfa  inc     rdx
0x18002fbfd  mov     [rbp+0A0h+var_80], rdx
0x18002fc01  mov     [rbp+0A0h+var_D0], rdx
0x18002fc05  cmp     rsi, rbx
0x18002fc08  jnb     short loc_18002FC4C
0x18002fc0a  mov     rdx, [rdi+rsi*8]
0x18002fc0e  test    rdx, rdx
0x18002fc11  jz      loc_1800301CD
0x18002fc17  inc     rsi
0x18002fc1a  xor     r8d, r8d
0x18002fc1d  nop     dword ptr [rax]
0x18002fc20  cmp     word ptr [rdx+r8*2], 0
0x18002fc26  lea     r8, [r8+1]
0x18002fc2a  jnz     short loc_18002FC20
0x18002fc2c  mov     rcx, r12
0x18002fc2f  call    widestring__ucstr__U16CStr__to_string_lossy
0x18002fc34  mov     rax, [rbp+0A0h+var_80]
0x18002fc38  cmp     rax, [rbp+0A0h+var_E0]
0x18002fc3c  jnz     short loc_18002FBE0
0x18002fc3e  mov     rcx, r13
0x18002fc41  call    alloc__raw_vec__RawVec_alloc__string__String_alloc__alloc__Global___grow_one_alloc__string__String_alloc__alloc__Global_
0x18002fc46  mov     r15, [rbp+0A0h+var_D8]
0x18002fc4a  jmp     short loc_18002FBE0
0x18002fc4c  mov     rsi, [rbp+0A0h+var_80]
0x18002fc50  mov     rdi, rsi
0x18002fc53  shl     rdi, 4
0x18002fc57  test    rsi, rsi
0x18002fc5a  jz      short loc_18002FC7D
0x18002fc5c  xor     ecx, ecx
0x18002fc5e  mov     rdx, rdi
0x18002fc61  call    std__sys__alloc__windows__process_heap_alloc
0x18002fc66  mov     [rbp+0A0h+var_88], rax
0x18002fc6a  test    rax, rax
0x18002fc6d  jz      loc_180030201
0x18002fc73  cmp     rsi, 1
0x18002fc77  jnz     short loc_18002FC88
0x18002fc79  xor     eax, eax
0x18002fc7b  jmp     short loc_18002FCC7
0x18002fc7d  mov     eax, 8
0x18002fc82  mov     [rbp+0A0h+var_88], rax
0x18002fc86  jmp     short loc_18002FCDD
0x18002fc88  lea     rcx, [r15+28h]
0x18002fc8c  mov     rdx, [rbp+0A0h+var_88]
0x18002fc90  add     rdx, 18h
0x18002fc94  mov     r8, rsi
0x18002fc97  and     r8, 0FFFFFFFFFFFFFFFEh
0x18002fc9b  xor     eax, eax
0x18002fc9d  nop     dword ptr [rax]
0x18002fca0  movups  xmm0, xmmword ptr [rcx-20h]
0x18002fca4  movups  xmmword ptr [rdx-18h], xmm0
0x18002fca8  movups  xmm0, xmmword ptr [rcx-8]
0x18002fcac  movups  xmmword ptr [rdx-8], xmm0
0x18002fcb0  add     rax, 2
0x18002fcb4  add     rcx, 30h ; '0'
0x18002fcb8  add     rdx, 20h ; ' '
0x18002fcbc  cmp     r8, rax
0x18002fcbf  jnz     short loc_18002FCA0
0x18002fcc1  test    sil, 1
0x18002fcc5  jz      short loc_18002FCDD
0x18002fcc7  lea     rcx, [rax+rax*2]
0x18002fccb  movups  xmm0, xmmword ptr [r15+rcx*8+8]
0x18002fcd1  shl     rax, 4
0x18002fcd5  mov     rcx, [rbp+0A0h+var_88]
0x18002fcd9  movups  xmmword ptr [rcx+rax], xmm0
0x18002fcdd  mov     rsi, [rbp+0A0h+var_68]
0x18002fce1  test    r14, r14
0x18002fce4  mov     rbx, [rbp+0A0h+arg_38]
0x18002fceb  jz      loc_18002FECE
0x18002fcf1  xor     r8d, r8d
0x18002fcf4  nop     word ptr [rax+rax+00000000h]
0x18002fd00  cmp     word ptr [r14+r8*2], 0
0x18002fd06  lea     r8, [r8+1]
0x18002fd0a  jnz     short loc_18002FD00
0x18002fd0c  lea     rcx, [rbp+0A0h+var_F8]
0x18002fd10  mov     rdx, r14
0x18002fd13  call    widestring__ucstr__U16CStr__to_string_lossy
0x18002fd18  test    rbx, rbx
0x18002fd1b  jz      loc_18002FEEF
0x18002fd21  xor     r8d, r8d
0x18002fd24  nop     word ptr [rax+rax+00000000h]
0x18002fd30  cmp     word ptr [rbx+r8*2], 0
0x18002fd36  lea     r8, [r8+1]
0x18002fd3a  jnz     short loc_18002FD30
0x18002fd3c  lea     rcx, [rbp+0A0h+lpMem]
0x18002fd40  mov     rdx, rbx
0x18002fd43  call    widestring__ucstr__U16CStr__to_string_lossy
0x18002fd48  cmp     qword ptr [rsi+10h], 0
0x18002fd4d  jnz     loc_18002FF12
0x18002fd53  lea     rbx, [rsi+18h]
0x18002fd57  mov     qword ptr [rsi+10h], 0FFFFFFFFFFFFFFFFh
0x18002fd5f  mov     rax, [rbp+0A0h+var_F0]
0x18002fd63  mov     [rbp+0A0h+var_C8], rax
0x18002fd67  mov     rax, [rbp+0A0h+var_E8]
0x18002fd6b  mov     [rbp+0A0h+var_C0], rax
0x18002fd6f  mov     rax, [rbp+0A0h+lpMem+8]
0x18002fd73  mov     [rbp+0A0h+var_B8], rax
0x18002fd77  mov     rax, [rbp+0A0h+var_98]
0x18002fd7b  mov     [rbp+0A0h+var_B0], rax
0x18002fd7f  mov     qword ptr [rsi+60h], 0
0x18002fd87  cmp     [rbp+0A0h+var_80], 0
0x18002fd8c  jz      short loc_18002FE08
0x18002fd8e  mov     rax, [rbp+0A0h+var_68]
0x18002fd92  lea     r14, [rax+50h]
0x18002fd96  mov     rsi, [rbp+0A0h+var_88]
0x18002fd9a  add     rdi, rsi
0x18002fd9d  lea     rax, [rsi+10h]
0x18002fda1  lea     r15, off_180336288; "rust\\font_fallback\\src\\builder.rs"
0x18002fda8  jmp     short loc_18002FDD8
0x18002fdb0  lea     rcx, [r13+1]
0x18002fdb4  xor     eax, eax
0x18002fdb6  cmp     rsi, rdi
0x18002fdb9  setnz   al
0x18002fdbc  shl     eax, 4
0x18002fdbf  add     rax, rsi
0x18002fdc2  mov     r8, [rbp+0A0h+var_68]
0x18002fdc6  mov     rdx, [r8+58h]
0x18002fdca  mov     [rdx+r13*2], r12w
0x18002fdcf  mov     [r8+60h], rcx
0x18002fdd3  cmp     rsi, rdi
0x18002fdd6  jz      short loc_18002FE08
0x18002fdd8  mov     rdx, [rsi]
0x18002fddb  mov     r8, [rsi+8]
0x18002fddf  mov     rsi, rax
0x18002fde2  mov     rcx, rbx
0x18002fde5  call    font_fallback__builder__CoalescedStrings__get_string_index
0x18002fdea  mov     r12d, eax
0x18002fded  mov     rax, [rbp+0A0h+var_68]
0x18002fdf1  mov     r13, [rax+60h]
0x18002fdf5  cmp     r13, [rax+50h]
0x18002fdf9  jnz     short loc_18002FDB0
0x18002fdfb  mov     rcx, r14
0x18002fdfe  mov     rdx, r15
0x18002fe01  call    alloc__raw_vec__RawVec_u16_alloc__alloc__Global___grow_one_u16_alloc__alloc__Global_
0x18002fe06  jmp     short loc_18002FDB0
0x18002fe08  mov     rcx, rbx
0x18002fe0b  mov     rdx, [rbp+0A0h+var_C8]
0x18002fe0f  mov     r8, [rbp+0A0h+var_C0]
0x18002fe13  call    font_fallback__builder__CoalescedStrings__get_string_index
0x18002fe18  mov     word ptr [rbp+0A0h+var_C8], ax
0x18002fe1c  mov     rcx, rbx
0x18002fe1f  mov     rdx, [rbp+0A0h+var_B8]
0x18002fe23  mov     r8, [rbp+0A0h+var_B0]
0x18002fe27  call    font_fallback__builder__CoalescedStrings__get_string_index
0x18002fe2c  mov     word ptr [rbp+0A0h+var_C0], ax
0x18002fe30  cmp     [rbp+0A0h+arg_28], 0
0x18002fe38  jz      loc_18002FF23
0x18002fe3e  mov     rax, [rbp+0A0h+var_68]
0x18002fe42  mov     rsi, [rax+70h]
0x18002fe46  mov     rax, [rax+78h]
0x18002fe4a  mov     r13, rax
0x18002fe4d  test    rax, rax
0x18002fe50  jz      short loc_18002FE83
0x18002fe52  lea     rbx, [rsi+r13*8]
0x18002fe56  xor     edi, edi
0x18002fe58  mov     r14, rsi
0x18002fe5b  nop     dword ptr [rax+rax+00h]
0x18002fe60  mov     rcx, [r14]
0x18002fe63  mov     rdx, [rbp+0A0h+arg_28]
0x18002fe6a  call    windows_core__unknown__impl$3__eq
0x18002fe6f  test    al, al
0x18002fe71  jnz     loc_18002FF2C
0x18002fe77  add     r14, 8
0x18002fe7b  inc     rdi
0x18002fe7e  cmp     r14, rbx
0x18002fe81  jnz     short loc_18002FE60
0x18002fe83  mov     rcx, [rbp+0A0h+arg_28]
0x18002fe8a  mov     rax, [rcx]
0x18002fe8d  mov     rax, [rax+8]
0x18002fe91  call    cs:__guard_dispatch_icall_fptr
0x18002fe97  mov     rdi, [rbp+0A0h+var_68]
0x18002fe9b  cmp     r13, [rdi+68h]
0x18002fe9f  mov     rbx, [rbp+0A0h+var_90]
0x18002fea3  jnz     short loc_18002FEB9
0x18002fea5  lea     rcx, [rdi+68h]
0x18002fea9  lea     rdx, off_180336258; "rust\\font_fallback\\src\\builder.rs"
0x18002feb0  call    alloc__raw_vec__RawVec_dwrite__font_collection__IDWriteFontCollection_alloc__alloc__Global___grow_one_dwrite__font_collection__IDWriteFontCollection_alloc__alloc__Global_
0x18002feb5  mov     rsi, [rdi+70h]
0x18002feb9  mov     rax, [rbp+0A0h+arg_28]
0x18002fec0  mov     [rsi+r13*8], rax
0x18002fec4  lea     rax, [r13+1]
0x18002fec8  mov     [rdi+78h], rax
0x18002fecc  jmp     short loc_18002FF33
0x18002fece  mov     [rbp+0A0h+var_F8], 0
0x18002fed6  mov     [rbp+0A0h+var_F0], 1
0x18002fede  mov     [rbp+0A0h+var_E8], 0
0x18002fee6  test    rbx, rbx
0x18002fee9  jnz     loc_18002FD21
0x18002feef  mov     [rbp+0A0h+lpMem], 0
0x18002fef7  mov     [rbp+0A0h+lpMem+8], 1
0x18002feff  mov     [rbp+0A0h+var_98], 0
0x18002ff07  cmp     qword ptr [rsi+10h], 0
0x18002ff0c  jz      loc_18002FD53
0x18002ff12  lea     rcx, off_1803366E8; "rust\\font_fallback_com\\src\\lib.rs"
0x18002ff19  call    core__cell__panic_already_borrowed
0x18002ff1e  jmp     loc_18003020E
0x18002ff23  xor     r13d, r13d
0x18002ff26  mov     rbx, [rbp+0A0h+var_90]
0x18002ff2a  jmp     short loc_18002FF36
0x18002ff2c  mov     r13, rdi
0x18002ff2f  mov     rbx, [rbp+0A0h+var_90]
0x18002ff33  inc     r13b
0x18002ff36  mov     rax, [rbp+0A0h+var_70]
0x18002ff3a  test    rax, rax
0x18002ff3d  jz      loc_18003006E
0x18002ff43  mulss   xmm6, cs:__real@42800000
0x18002ff4b  xorps   xmm0, xmm0
0x18002ff4e  maxss   xmm0, xmm6
0x18002ff52  movss   xmm1, cs:__real@437f0000
0x18002ff5a  minss   xmm1, xmm0
0x18002ff5e  cvttss2si ecx, xmm1
0x18002ff62  mov     dword ptr [rbp+0A0h+var_B8], ecx
0x18002ff65  lea     rax, [rbx+rax*8]
0x18002ff69  mov     [rbp+0A0h+var_B0], rax
0x18002ff6d  lea     rax, [rbx+8]
0x18002ff71  mov     rcx, [rbp+0A0h+var_68]
0x18002ff75  lea     r14, [rcx+80h]
0x18002ff7c  jmp     short loc_18002FF97
0x18002ff80  xor     eax, eax
0x18002ff82  mov     rbx, [rbp+0A0h+var_90]
0x18002ff86  cmp     rbx, [rbp+0A0h+var_B0]
0x18002ff8a  setnz   al
0x18002ff8d  lea     rax, [rbx+rax*8]
0x18002ff91  jz      loc_18003006E
0x18002ff97  mov     edx, [rbx]
0x18002ff99  mov     r15d, [rbx+4]
0x18002ff9d  mov     [rbp+0A0h+var_90], rax
0x18002ffa1  cmp     r15d, 10FFFFh
0x18002ffa8  mov     eax, 10FFFFh
0x18002ffad  cmovb   eax, r15d
0x18002ffb1  mov     dword ptr [rbp+0A0h+var_70], edx
0x18002ffb4  cmp     edx, eax
0x18002ffb6  ja      short loc_18002FF80
0x18002ffb8  mov     rax, [rbp+0A0h+var_68]
0x18002ffbc  mov     rax, [rax+60h]
0x18002ffc0  test    rax, rax
0x18002ffc3  jz      short loc_18002FF80
0x18002ffc5  mov     rcx, [rbp+0A0h+var_68]
0x18002ffc9  mov     r12, [rcx+58h]
0x18002ffcd  lea     rdi, [r12+rax*2]
  ... truncated ...
```
