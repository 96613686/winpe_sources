# Rust_CreateTextFormat

- ea: `0x18000a000`
- end: `0x18000a831`
- name: `Rust_CreateTextFormat`
- size: `2097`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, __int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1802ea4cc`

## callees

- `0x18000a000`
- `0x18000ace0`
- `0x18000aef0`
- `0x180042930`
- `0x1800d97e0`
- `0x1800dc910`
- `0x18021e1b6`
- `0x180316190`
- `0x180316232`
- `0x180316255`
- `0x1803163f0`
- `0x180316a30`
- `0x180316ae0`

## import_xrefs

- `kernel32!HeapFree` at `0x18000a64f`
- `kernel32!HeapFree` at `0x18000a64f`
- `kernel32!GetProcessHeap` at `0x18000a368`
- `kernel32!GetProcessHeap` at `0x18000a63d`
- `kernel32!GetProcessHeap` at `0x18000a368`
- `kernel32!GetProcessHeap` at `0x18000a63d`
- `oleaut32!GetErrorInfo` at `0x18000a175`
- `oleaut32!GetErrorInfo` at `0x18000a175`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a379`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a379`

## string_xrefs

- `0x18000a79b`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x18000a107`: `assertion failed: !p.is_null()called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\os\out\rust\cargo_home\amd64fre\registry\src\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\windows-core-0.62.2\src\imp\ref_count.rs`
- `0x18000a781`: `assertion failed: !p.is_null()called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\os\out\rust\cargo_home\amd64fre\registry\src\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\windows-core-0.62.2\src\imp\ref_count.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Rust_CreateTextFormat(
        _WORD *Src,
        IErrorInfo *a2,
        __int64 a3,
        float a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        unsigned int a9,
        IErrorInfo **a10)
{
  __int64 v12; // r10
  __int64 v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // r15
  __int64 v16; // r13
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // rdi
  char v19; // bl
  IErrorInfo *v20; // rdi
  unsigned int v21; // esi
  __int64 v22; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  _WORD *v28; // rdx
  IErrorInfo *v29; // rbx
  IErrorInfo *v30; // rax
  unsigned __int64 v31; // r13
  IErrorInfo *v32; // r14
  HANDLE ProcessHeap; // rax
  __int64 v34; // rbx
  unsigned __int64 v35; // r8
  bool v36; // di
  unsigned __int64 v37; // r12
  __int16 lpVtbl; // ax
  unsigned __int64 v39; // r14
  __int64 v40; // rbx
  char v41; // r13
  __int64 v42; // rax
  IErrorInfo *v43; // rcx
  HANDLE v44; // rax
  IErrorInfo *v45; // rax
  __int64 v46; // r14
  IErrorInfo *v47; // rdi
  __int128 v48; // [rsp+20h] [rbp-60h]
  IErrorInfo *pperrinfo[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v50; // [rsp+68h] [rbp-18h]
  __int64 v51; // [rsp+70h] [rbp-10h]
  __int64 v52; // [rsp+78h] [rbp-8h]
  __int64 v53; // [rsp+80h] [rbp+0h]
  __int128 v54; // [rsp+88h] [rbp+8h]
  IErrorInfo *v55; // [rsp+98h] [rbp+18h]
  __int64 v56; // [rsp+A0h] [rbp+20h]
  __int64 v57; // [rsp+A8h] [rbp+28h]
  __int128 v58; // [rsp+B0h] [rbp+30h]
  __int128 v59; // [rsp+C0h] [rbp+40h]
  __int128 v60; // [rsp+D0h] [rbp+50h]
  float v61; // [rsp+E0h] [rbp+60h]
  float v62; // [rsp+E4h] [rbp+64h]
  int v63; // [rsp+E8h] [rbp+68h]
  int v64; // [rsp+ECh] [rbp+6Ch]
  unsigned int v65; // [rsp+F0h] [rbp+70h]
  __int128 v66; // [rsp+F4h] [rbp+74h]
  __int128 v67; // [rsp+104h] [rbp+84h]
  __int16 v68; // [rsp+114h] [rbp+94h]
  char v69; // [rsp+116h] [rbp+96h]
  __int64 v70; // [rsp+118h] [rbp+98h]
  __int64 v71; // [rsp+120h] [rbp+A0h]
  IErrorInfo *v72; // [rsp+128h] [rbp+A8h]
  LPVOID lpMem; // [rsp+130h] [rbp+B0h]
  __int64 v74; // [rsp+138h] [rbp+B8h]
  __int64 v75; // [rsp+140h] [rbp+C0h]
  __int64 v76; // [rsp+148h] [rbp+C8h]
  IErrorInfo *v77; // [rsp+150h] [rbp+D0h]
  char v78; // [rsp+15Fh] [rbp+DFh]
  __int64 v79; // [rsp+160h] [rbp+E0h]

  v79 = -2;
  v12 = a6;
  if ( !a6 )
  {
    v13 = 4;
    if ( Src )
      goto LABEL_4;
LABEL_12:
    core::panicking::panic(
      "assertion failed: !p.is_null()called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out"
      "\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2"
      "\\src\\imp\\ref_count.rs",
      30,
      &off_180349218);
  }
  v13 = a5;
  if ( !a5 )
  {
    try
    {
      core::panicking::panic(
        "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_ut"
        "ils\\src\\lib.rs",
        32,
        &off_1803491E0);
    }
    catch ( ... )
    {
      core::panicking::panic_cannot_unwind();
    }
  }
  if ( !Src )
    goto LABEL_12;
LABEL_4:
  v14 = a9;
  v15 = 0;
  do
    v16 = v15++;
  while ( Src[v16] );
  if ( !a2 )
    core::panicking::panic(
      "assertion failed: !p.is_null()called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out"
      "\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2"
      "\\src\\imp\\ref_count.rs",
      30,
      &off_180349218);
  v77 = (IErrorInfo *)v13;
  v74 = a3;
  v17 = 0;
  do
    v18 = v17++;
  while ( *((_WORD *)&a2->lpVtbl + v18) );
  if ( v74 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v74 + 8LL))(v74, a9);
    v12 = a6;
    v14 = a9;
  }
  else
  {
    v74 = 0;
  }
  if ( v14 >= 3 || (unsigned int)(a7 - 1) >= 0x3E7 || (unsigned int)(a8 - 10) < 0xFFFFFFF7 || a4 <= 0.0 )
  {
    pperrinfo[0] = 0;
    v19 = 0;
    GetErrorInfo(0, pperrinfo);
    v20 = pperrinfo[0];
    v21 = -2147024809;
    v22 = v74;
    if ( !v74 )
      goto LABEL_18;
    goto LABEL_17;
  }
  if ( v12 )
  {
    v24 = alloc::sync::Arc_slice2__dwrite_min::variable::FontAxisValue__alloc::alloc::Global_::from_iter_exact_dwrite_min::variable::FontAxisValue_core::iter::adapters::cloned::Cloned_core::slice::iter::Iter_dwrite_min::variable::FontAxisValue_____(
            v77,
            &v77[v12],
            v12);
    v71 = v25;
    v75 = v24;
  }
  else
  {
    v75 = 0;
  }
  if ( v15 < 0 || (unsigned __int64)(2 * v15) > 0x7FFFFFFFFFFFFFFELL )
  {
    v26 = 0;
    goto LABEL_28;
  }
  if ( 2 * v15 )
  {
    v27 = std::sys::alloc::windows::process_heap_alloc(0, 2 * v15);
    v77 = (IErrorInfo *)v15;
    if ( !v27 )
    {
      v26 = 2;
LABEL_28:
      alloc::raw_vec::handle_error(v26, 2 * v15, &off_180348EC0);
    }
  }
  else
  {
    v27 = 2;
    v77 = 0;
  }
  v28 = Src;
  v29 = (IErrorInfo *)v27;
  memcpy_0((void *)v27, v28, 2 * v15);
  v30 = v29;
  pperrinfo[0] = v77;
  pperrinfo[1] = v29;
  v50 = v15;
  if ( v15 )
  {
    if ( !*((_WORD *)v29 + v15 - 1) )
      goto LABEL_43;
    if ( (IErrorInfo *)v15 == v77 )
    {
      v78 = 0;
      alloc::raw_vec::RawVec_u16_alloc::alloc::Global_::grow_one_u16_alloc::alloc::Global_(pperrinfo, &off_1803372E8);
      v30 = pperrinfo[1];
    }
    *((_WORD *)&v30->lpVtbl + v15) = 0;
    v31 = v16 + 2;
    v50 = v31;
    v32 = pperrinfo[1];
    v15 = v31;
    v30 = pperrinfo[1];
    if ( pperrinfo[0] <= (IErrorInfo *)v31 )
      goto LABEL_43;
LABEL_42:
    ProcessHeap = GetProcessHeap();
    v30 = (IErrorInfo *)HeapReAlloc(ProcessHeap, 0, v32, 2 * v31);
    v15 = v31;
    if ( !v30 )
    {
      v77 = v32;
      alloc::alloc::handle_alloc_error(2, 2 * v31);
    }
    goto LABEL_43;
  }
  if ( !v77 )
  {
    v78 = 0;
    alloc::raw_vec::RawVec_u16_alloc::alloc::Global_::grow_one_u16_alloc::alloc::Global_(pperrinfo, &off_1803372E8);
    v30 = pperrinfo[1];
  }
  LOWORD(v30->lpVtbl) = 0;
  v50 = 1;
  v32 = pperrinfo[1];
  v31 = 1;
  v15 = 1;
  v30 = pperrinfo[1];
  if ( pperrinfo[0] >= (IErrorInfo *)2 )
    goto LABEL_42;
LABEL_43:
  v72 = v30;
  v34 = v74;
  if ( !v74 )
  {
    v76 = 0;
    if ( v17 )
      goto LABEL_45;
LABEL_82:
    core::slice::index::slice_end_index_len_fail(v18, 0, &off_180349218);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 8LL))(v74);
  v76 = v34;
  if ( !v17 )
    goto LABEL_82;
LABEL_45:
  pperrinfo[0] = 0;
  pperrinfo[1] = (IErrorInfo *)1;
  v50 = 0;
  v35 = (v18 >> 1) + (v18 & 1);
  if ( v35 )
    alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__0(pperrinfo, 0, v35, 1);
  v77 = (IErrorInfo *)((char *)a2 + 2 * v18);
  v36 = 0;
  while ( 1 )
  {
    if ( v36 )
    {
      LOWORD(v37) = (_WORD)lpMem;
      goto LABEL_54;
    }
    if ( a2 == v77 )
      break;
    LOWORD(v37) = a2->lpVtbl;
    a2 = (IErrorInfo *)((char *)a2 + 2);
LABEL_54:
    if ( (v37 & 0xF800) == 0xD800 )
    {
      v36 = (unsigned __int16)v37 < 0xDC00u && a2 != v77;
      if ( !v36 )
        goto LABEL_58;
      lpVtbl = (__int16)a2->lpVtbl;
      a2 = (IErrorInfo *)((char *)a2 + 2);
      if ( (unsigned __int16)(lpVtbl + 0x2000) < 0xFC00u )
      {
        LOWORD(lpMem) = lpVtbl;
LABEL_58:
        v39 = 3;
        LODWORD(v37) = 65533;
        v40 = v50;
        v41 = 0;
        goto LABEL_67;
      }
      v37 = lpVtbl & 0x3FF | ((((v37 & 0x3FF) << 26) + 0x100000000LL) >> 16);
    }
    else
    {
      v37 = (unsigned __int16)v37;
    }
    v40 = v50;
    if ( v37 >= 0x80 )
    {
      if ( v37 >= 0x800 )
        v39 = (__PAIR128__(4, v37) - 0x10000) >> 64;
      else
        v39 = 2;
      v41 = 0;
    }
    else
    {
      v39 = 1;
      v41 = 1;
    }
    v36 = 0;
LABEL_67:
    v42 = v40;
    if ( (IErrorInfo *)v39 > (IErrorInfo *)((char *)pperrinfo[0] - v40) )
    {
      alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__0(pperrinfo, v40, v39, 1);
      v42 = v50;
    }
    v43 = pperrinfo[1];
    if ( v41 )
    {
      *((_BYTE *)&pperrinfo[1]->lpVtbl + v42) = v37;
    }
    else if ( (unsigned int)v37 >= 0x800 )
    {
      if ( (unsigned int)v37 >= 0x10000 )
      {
        *((_BYTE *)&pperrinfo[1]->lpVtbl + v42) = ((unsigned int)v37 >> 18) | 0xF0;
        *((_BYTE *)&v43->lpVtbl + v42 + 1) = ((unsigned int)v37 >> 12) & 0x3F | 0x80;
        *((_BYTE *)&v43->lpVtbl + v42 + 2) = ((unsigned int)v37 >> 6) & 0x3F | 0x80;
        *((_BYTE *)&v43->lpVtbl + v42 + 3) = v37 & 0x3F | 0x80;
      }
      else
      {
        *((_BYTE *)&pperrinfo[1]->lpVtbl + v42) = ((unsigned int)v37 >> 12) | 0xE0;
        *((_BYTE *)&v43->lpVtbl + v42 + 1) = ((unsigned int)v37 >> 6) & 0x3F | 0x80;
        *((_BYTE *)&v43->lpVtbl + v42 + 2) = v37 & 0x3F | 0x80;
      }
    }
    else
    {
      *((_BYTE *)&pperrinfo[1]->lpVtbl + v42) = ((unsigned int)v37 >> 6) | 0xC0;
      *((_BYTE *)&v43->lpVtbl + v42 + 1) = v37 & 0x3F | 0x80;
    }
    v50 = v40 + v39;
  }
  v77 = pperrinfo[0];
  lpMem = pperrinfo[1];
  langtag::parse_language_tag(pperrinfo, pperrinfo[1], v50);
  v48 = *(_OWORD *)pperrinfo;
  if ( v77 )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, lpMem);
  }
  pperrinfo[0] = (IErrorInfo *)off_180335468;
  pperrinfo[1] = (IErrorInfo *)off_180335498;
  v50 = (__int64)off_1803355F0;
  v51 = 0;
  v52 = v75;
  v53 = v71;
  v54 = v48;
  v55 = v72;
  v56 = v15;
  v57 = v76;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = a4;
  v62 = 4.0 * a4;
  v63 = a7;
  v64 = a8;
  v65 = a9;
  v67 = 0;
  v66 = 0;
  v68 = 0;
  v69 = 1;
  v70 = 1;
  v45 = (IErrorInfo *)std::sys::alloc::windows::process_heap_alloc(0, 200);
  v46 = v74;
  if ( !v45 )
    alloc::alloc::handle_alloc_error(8, 200);
  v47 = v45;
  memcpy_0(v45, pperrinfo, 0xC8u);
  v20 = v47 + 1;
  v19 = 1;
  v21 = 0;
  v22 = v46;
  if ( v46 )
LABEL_17:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_18:
  if ( v19 )
  {
    *a10 = v20;
    return 0;
  }
  else
  {
    *a10 = 0;
    if ( v20 )
      ((void (__fastcall *)(IErrorInfo *))v20->lpVtbl->Release)(v20);
  }
  return v21;
}

```

## disassembly

```asm
0x18000a000  push    rbp
0x18000a001  push    r15
0x18000a003  push    r14
0x18000a005  push    r13
0x18000a007  push    r12
0x18000a009  push    rsi
0x18000a00a  push    rdi
0x18000a00b  push    rbx
0x18000a00c  sub     rsp, 198h
0x18000a013  lea     rbp, [rsp+80h]
0x18000a01b  movaps  [rbp+150h+var_50], xmm7
0x18000a022  movaps  [rbp+150h+var_60], xmm6
0x18000a029  mov     [rbp+150h+var_70], 0FFFFFFFFFFFFFFFEh
0x18000a034  movaps  xmm6, xmm3
0x18000a037  mov     rsi, rdx
0x18000a03a  mov     rbx, rcx
0x18000a03d  mov     r10, [rbp+150h+arg_28]
0x18000a044  test    r10, r10
0x18000a047  jz      loc_18000A0F9
0x18000a04d  mov     rcx, [rbp+150h+arg_20]
0x18000a054  test    rcx, rcx
0x18000a057  jz      loc_18000A79B
0x18000a05d  test    rbx, rbx
0x18000a060  jz      loc_18000A107
0x18000a066  mov     edx, [rbp+150h+arg_40]
0x18000a06c  mov     r14d, [rbp+150h+arg_30]
0x18000a073  mov     rax, 0FFFFFFFF00000000h
0x18000a07d  and     rax, r10
0x18000a080  xor     r15d, r15d
0x18000a083  nop     word ptr [rax+rax+00000000h]
0x18000a090  mov     r13, r15
0x18000a093  inc     r15
0x18000a096  cmp     word ptr [rbx+r13*2], 0
0x18000a09c  jnz     short loc_18000A090
0x18000a09e  test    rsi, rsi
0x18000a0a1  jz      loc_18000A781
0x18000a0a7  mov     [rbp+150h+var_80], rcx
0x18000a0ae  mov     [rbp+150h+var_98], r8
0x18000a0b5  xor     r12d, r12d
0x18000a0b8  nop     dword ptr [rax+rax+00000000h]
0x18000a0c0  mov     rdi, r12
0x18000a0c3  inc     r12
0x18000a0c6  cmp     word ptr [rsi+rdi*2], 0
0x18000a0cb  jnz     short loc_18000A0C0
0x18000a0cd  mov     [rbp+150h+var_198], rax
0x18000a0d1  mov     rcx, [rbp+150h+var_98]
0x18000a0d8  test    rcx, rcx
0x18000a0db  jz      short loc_18000A124
0x18000a0dd  mov     rax, [rcx]
0x18000a0e0  mov     rax, [rax+8]
0x18000a0e4  call    cs:__guard_dispatch_icall_fptr
0x18000a0ea  mov     r10, [rbp+150h+arg_28]
0x18000a0f1  mov     edx, [rbp+150h+arg_40]
0x18000a0f7  jmp     short loc_18000A12F
0x18000a0f9  mov     ecx, 4
0x18000a0fe  test    rbx, rbx
0x18000a101  jnz     loc_18000A066
0x18000a107  lea     rcx, aAssertionFaile_1; "assertion failed: !p.is_null()called `R"...
0x18000a10e  lea     r8, off_180349218; "d:\\os\\out\\rust\\cargo_home\\amd64fre"...
0x18000a115  mov     edx, 1Eh
0x18000a11a  call    core__panicking__panic
0x18000a11f  jmp     loc_18000A7F0
0x18000a124  mov     [rbp+150h+var_98], 0
0x18000a12f  lea     eax, [r14-1]
0x18000a133  cmp     eax, 3E7h
0x18000a138  setb    al
0x18000a13b  cmp     edx, 3
0x18000a13e  setb    cl
0x18000a141  test    al, cl
0x18000a143  jz      short loc_18000A165
0x18000a145  mov     eax, [rbp+150h+arg_38]
0x18000a14b  add     eax, 0FFFFFFF6h
0x18000a14e  cmp     eax, 0FFFFFFF7h
0x18000a151  setb    al
0x18000a154  xorps   xmm0, xmm0
0x18000a157  ucomiss xmm6, xmm0
0x18000a15a  setbe   cl
0x18000a15d  or      cl, al
0x18000a15f  jz      loc_18000A206
0x18000a165  mov     [rbp+150h+pperrinfo], 0
0x18000a16d  xor     ebx, ebx
0x18000a16f  lea     rdx, [rbp+150h+pperrinfo]; pperrinfo
0x18000a173  xor     ecx, ecx; dwReserved
0x18000a175  call    cs:__imp_GetErrorInfo
0x18000a17b  mov     rdi, [rbp+150h+pperrinfo]
0x18000a17f  mov     esi, 80070057h
0x18000a184  mov     rcx, [rbp+150h+var_98]
0x18000a18b  test    rcx, rcx
0x18000a18e  jz      short loc_18000A19D
0x18000a190  mov     rax, [rcx]
0x18000a193  mov     rax, [rax+10h]
0x18000a197  call    cs:__guard_dispatch_icall_fptr
0x18000a19d  mov     rax, [rbp+150h+var_198]
0x18000a1a1  or      rax, rsi
0x18000a1a4  mov     [rbp+150h+var_188], rdi
0x18000a1a8  mov     [rbp+150h+var_180], rax
0x18000a1ac  mov     [rbp+150h+var_190], 0
0x18000a1b4  mov     rax, [rbp+150h+arg_48]
0x18000a1bb  test    bl, bl
0x18000a1bd  jz      short loc_18000A1C6
0x18000a1bf  mov     [rax], rdi
0x18000a1c2  xor     esi, esi
0x18000a1c4  jmp     short loc_18000A1E2
0x18000a1c6  mov     qword ptr [rax], 0
0x18000a1cd  test    rdi, rdi
0x18000a1d0  jz      short loc_18000A1E2
0x18000a1d2  mov     rax, [rdi]
0x18000a1d5  mov     rax, [rax+10h]
0x18000a1d9  mov     rcx, rdi
0x18000a1dc  call    cs:__guard_dispatch_icall_fptr
0x18000a1e2  mov     eax, esi
0x18000a1e4  movaps  xmm6, [rbp+150h+var_60]
0x18000a1eb  movaps  xmm7, [rbp+150h+var_50]
0x18000a1f2  add     rsp, 198h
0x18000a1f9  pop     rbx
0x18000a1fa  pop     rdi
0x18000a1fb  pop     rsi
0x18000a1fc  pop     r12
0x18000a1fe  pop     r13
0x18000a200  pop     r14
0x18000a202  pop     r15
0x18000a204  pop     rbp
0x18000a205  retn
0x18000a206  test    r10, r10
0x18000a209  jz      short loc_18000A22E
0x18000a20b  mov     rcx, [rbp+150h+var_80]
0x18000a212  lea     rdx, [rcx+r10*8]
0x18000a216  mov     r8, r10
0x18000a219  call    alloc__sync__Arc_slice2$_dwrite_min__variable__FontAxisValue__alloc__alloc__Global___from_iter_exact_dwrite_min__variable__FontAxisValue_core__iter__adapters__cloned__Cloned_core__slice__iter__Iter_dwrite_min__variable__FontAxisValue_____
0x18000a21e  mov     [rbp+150h+var_B0], rdx
0x18000a225  mov     [rbp+150h+var_90], rax
0x18000a22c  jmp     short loc_18000A239
0x18000a22e  mov     [rbp+150h+var_90], 0
0x18000a239  lea     r14, [r15+r15]
0x18000a23d  test    r15, r15
0x18000a240  sets    al
0x18000a243  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18000a24d  cmp     r14, rcx
0x18000a250  setnbe  cl
0x18000a253  or      cl, al
0x18000a255  jz      short loc_18000A26D
0x18000a257  xor     ecx, ecx
0x18000a259  lea     r8, off_180348EC0; "D:\\os\\tools\\Rust\\vpack\\rust.tools"...
0x18000a260  mov     rdx, r14
0x18000a263  call    alloc__raw_vec__handle_error
0x18000a268  jmp     loc_18000A7F0
0x18000a26d  test    r14, r14
0x18000a270  jz      short loc_18000A292
0x18000a272  xor     ecx, ecx
0x18000a274  mov     rdx, r14
0x18000a277  call    std__sys__alloc__windows__process_heap_alloc
0x18000a27c  mov     rcx, rax
0x18000a27f  mov     [rbp+150h+var_80], r15
0x18000a286  test    rax, rax
0x18000a289  jnz     short loc_18000A2A2
0x18000a28b  mov     ecx, 2
0x18000a290  jmp     short loc_18000A259
0x18000a292  mov     ecx, 2; void *
0x18000a297  mov     [rbp+150h+var_80], 0
0x18000a2a2  mov     rdx, rbx; Src
0x18000a2a5  mov     r8, r14; Size
0x18000a2a8  mov     rbx, rcx
0x18000a2ab  call    memcpy_0
0x18000a2b0  mov     rax, rbx
0x18000a2b3  mov     rcx, [rbp+150h+var_80]
0x18000a2ba  mov     [rbp+150h+pperrinfo], rcx
0x18000a2be  mov     [rbp+150h+pperrinfo+8], rbx
0x18000a2c2  mov     [rbp+150h+var_168], r15
0x18000a2c6  test    r15, r15
0x18000a2c9  jz      short loc_18000A319
0x18000a2cb  cmp     word ptr [rax+r15*2-2], 0
0x18000a2d2  jz      loc_18000A38B
0x18000a2d8  cmp     r15, rcx
0x18000a2db  jnz     short loc_18000A2F8
0x18000a2dd  mov     [rbp+150h+var_71], 0
0x18000a2e4  lea     rdx, off_1803372E8; "d:\\os\\out\\rust\\cargo_home\\amd64fre"...
0x18000a2eb  lea     rcx, [rbp+150h+pperrinfo]
0x18000a2ef  call    alloc__raw_vec__RawVec_u16_alloc__alloc__Global___grow_one_u16_alloc__alloc__Global_
0x18000a2f4  mov     rax, [rbp+150h+pperrinfo+8]
0x18000a2f8  mov     word ptr [rax+r15*2], 0
0x18000a2ff  add     r13, 2
0x18000a303  mov     [rbp+150h+var_168], r13
0x18000a307  mov     r14, [rbp+150h+pperrinfo+8]
0x18000a30b  mov     r15, r13
0x18000a30e  mov     rax, r14
0x18000a311  cmp     [rbp+150h+pperrinfo], r13
0x18000a315  ja      short loc_18000A360
0x18000a317  jmp     short loc_18000A38B
0x18000a319  test    rcx, rcx
0x18000a31c  jnz     short loc_18000A339
0x18000a31e  mov     [rbp+150h+var_71], 0
0x18000a325  lea     rdx, off_1803372E8; "d:\\os\\out\\rust\\cargo_home\\amd64fre"...
0x18000a32c  lea     rcx, [rbp+150h+pperrinfo]
0x18000a330  call    alloc__raw_vec__RawVec_u16_alloc__alloc__Global___grow_one_u16_alloc__alloc__Global_
0x18000a335  mov     rax, [rbp+150h+pperrinfo+8]
0x18000a339  mov     word ptr [rax], 0
0x18000a33e  mov     [rbp+150h+var_168], 1
0x18000a346  mov     r14, [rbp+150h+pperrinfo+8]
0x18000a34a  mov     r13d, 1
0x18000a350  cmp     [rbp+150h+pperrinfo], 2
0x18000a355  mov     r15d, 1
0x18000a35b  mov     rax, r14
0x18000a35e  jb      short loc_18000A38B
0x18000a360  lea     rbx, ds:0[r13*2]
0x18000a368  call    cs:__imp_GetProcessHeap
0x18000a36e  mov     rcx, rax; hHeap
0x18000a371  xor     edx, edx; dwFlags
0x18000a373  mov     r8, r14; lpMem
0x18000a376  mov     r9, rbx; dwBytes
0x18000a379  call    cs:__imp_HeapReAlloc
0x18000a37f  mov     r15, r13
0x18000a382  test    rax, rax
0x18000a385  jz      loc_18000A7DC
0x18000a38b  mov     [rbp+150h+var_A8], rax
0x18000a392  mov     rbx, [rbp+150h+var_98]
0x18000a399  test    rbx, rbx
0x18000a39c  jz      loc_18000A75A
0x18000a3a2  mov     rax, [rbx]
0x18000a3a5  mov     rax, [rax+8]
0x18000a3a9  mov     rcx, rbx
0x18000a3ac  call    cs:__guard_dispatch_icall_fptr
0x18000a3b2  mov     [rbp+150h+var_88], rbx
0x18000a3b9  test    r12, r12
0x18000a3bc  jz      loc_18000A76E
0x18000a3c2  mov     [rbp+150h+pperrinfo], 0
0x18000a3ca  mov     [rbp+150h+pperrinfo+8], 1
0x18000a3d2  mov     [rbp+150h+var_168], 0
0x18000a3da  mov     rax, rdi
0x18000a3dd  shr     rax, 1
0x18000a3e0  mov     r8d, edi
0x18000a3e3  and     r8d, 1
0x18000a3e7  add     r8, rax
0x18000a3ea  jnz     loc_18000A7B5
0x18000a3f0  lea     rax, [rsi+rdi*2]
0x18000a3f4  mov     [rbp+150h+var_80], rax
0x18000a3fb  xor     edi, edi
0x18000a3fd  lea     r8, [rbp+150h+pperrinfo]
0x18000a401  jmp     short loc_18000A41B
0x18000a410  mov     [rcx+rax], r12b
0x18000a414  add     r14, rbx
0x18000a417  mov     [rbp+150h+var_168], r14
0x18000a41b  test    dil, 1
0x18000a41f  jz      short loc_18000A430
0x18000a421  mov     r12w, word ptr [rbp+150h+lpMem]
0x18000a429  jmp     short loc_18000A445
0x18000a430  cmp     rsi, [rbp+150h+var_80]
0x18000a437  jz      loc_18000A5FC
0x18000a43d  movzx   r12d, word ptr [rsi]
0x18000a441  add     rsi, 2
0x18000a445  mov     eax, r12d
0x18000a448  and     eax, 0F800h
0x18000a44d  cmp     eax, 0D800h
0x18000a452  jnz     short loc_18000A4B0
0x18000a454  movzx   eax, r12w
0x18000a458  cmp     eax, 0DC00h
0x18000a45d  setb    al
0x18000a460  cmp     rsi, [rbp+150h+var_80]
0x18000a467  setnz   dil
0x18000a46b  and     dil, al
0x18000a46e  cmp     dil, 1
0x18000a472  jnz     short loc_18000A499
0x18000a474  movzx   eax, word ptr [rsi]
0x18000a477  add     rsi, 2
0x18000a47b  mov     ecx, eax
0x18000a47d  add     ecx, 2000h
0x18000a483  movzx   ecx, cx
0x18000a486  cmp     ecx, 0FC00h
0x18000a48c  jnb     loc_18000A574
0x18000a492  mov     word ptr [rbp+150h+lpMem], ax
0x18000a499  mov     r14d, 3
0x18000a49f  mov     r12d, 0FFFDh
0x18000a4a5  mov     rbx, [rbp+150h+var_168]
0x18000a4a9  xor     r13d, r13d
0x18000a4ac  jmp     short loc_18000A4F7
0x18000a4b0  movzx   r12d, r12w
0x18000a4b4  mov     rbx, [rbp+150h+var_168]
0x18000a4b8  cmp     r12, 80h
0x18000a4bf  jnb     short loc_18000A4D0
0x18000a4c1  mov     r14d, 1
0x18000a4c7  mov     r13b, 1
0x18000a4ca  jmp     short loc_18000A4F5
0x18000a4d0  cmp     r12, 800h
0x18000a4d7  jnb     short loc_18000A4E1
0x18000a4d9  mov     r14d, 2
0x18000a4df  jmp     short loc_18000A4F2
0x18000a4e1  cmp     r12, 10000h
0x18000a4e8  mov     r14d, 4
0x18000a4ee  sbb     r14, 0
0x18000a4f2  xor     r13d, r13d
0x18000a4f5  xor     edi, edi
0x18000a4f7  mov     rcx, [rbp+150h+pperrinfo]
0x18000a4fb  sub     rcx, rbx
0x18000a4fe  mov     rax, rbx
0x18000a501  cmp     r14, rcx
0x18000a504  ja      loc_18000A5DB
0x18000a50a  mov     rcx, [rbp+150h+pperrinfo+8]
0x18000a50e  test    r13b, r13b
0x18000a511  jnz     loc_18000A410
0x18000a517  mov     edx, r12d
0x18000a51a  cmp     r12d, 800h
  ... truncated ...
```
