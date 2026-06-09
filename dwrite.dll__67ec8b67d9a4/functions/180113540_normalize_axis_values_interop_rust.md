# normalize_axis_values_interop_rust

- ea: `0x180113540`
- end: `0x1801138fd`
- name: `normalize_axis_values_interop_rust`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x1802dbc28`

## callees

- `0x180022de0`
- `0x18010fd20`
- `0x1801108d0`
- `0x180110cf0`
- `0x180113540`
- `0x180316190`
- `0x180316ae0`
- `0x180318360`

## import_xrefs

- `kernel32!HeapFree` at `0x180113735`
- `kernel32!HeapFree` at `0x180113798`
- `kernel32!HeapFree` at `0x1801137b3`
- `kernel32!HeapFree` at `0x1801137cf`
- `kernel32!HeapFree` at `0x180113735`
- `kernel32!HeapFree` at `0x180113798`
- `kernel32!HeapFree` at `0x1801137b3`
- `kernel32!HeapFree` at `0x1801137cf`
- `kernel32!GetProcessHeap` at `0x180113726`
- `kernel32!GetProcessHeap` at `0x18011378a`
- `kernel32!GetProcessHeap` at `0x1801137a5`
- `kernel32!GetProcessHeap` at `0x1801137c0`
- `kernel32!GetProcessHeap` at `0x180113726`
- `kernel32!GetProcessHeap` at `0x18011378a`
- `kernel32!GetProcessHeap` at `0x1801137a5`
- `kernel32!GetProcessHeap` at `0x1801137c0`

## string_xrefs

- `0x180113603`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x1801137eb`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x180113805`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall normalize_axis_values_interop_rust(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        _QWORD *a8,
        __int64 *a9,
        _QWORD *a10,
        __int64 *a11,
        __int64 *a12)
{
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r12
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // rbx
  LPVOID v20; // r14
  __int64 v21; // r15
  __int64 v22; // r12
  __int64 v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rsi
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  __int64 result; // rax
  __int64 v30; // rcx
  int v31; // r10d
  int *v32; // r9
  int v33; // r8d
  __int64 v34; // r11
  _DWORD *v35; // r10
  int v36; // r11d
  int v37; // r9d
  void *v38; // rdx
  _QWORD v39[2]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v40[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v41; // [rsp+50h] [rbp-30h]
  __int64 v42; // [rsp+58h] [rbp-28h] BYREF
  LPVOID v43; // [rsp+60h] [rbp-20h]
  __int64 v44; // [rsp+68h] [rbp-18h]
  _QWORD *v45; // [rsp+70h] [rbp-10h] BYREF
  __int64 v46; // [rsp+78h] [rbp-8h]
  __int64 v47; // [rsp+80h] [rbp+0h]
  __int64 v48; // [rsp+88h] [rbp+8h]
  LPVOID lpMem; // [rsp+90h] [rbp+10h]
  __int64 v50; // [rsp+98h] [rbp+18h]
  __int64 v51; // [rsp+A0h] [rbp+20h] BYREF

  try
  {
    v50 = -2;
    *a7 = 0;
    *a8 = 0;
    *a9 = 0;
    *a10 = 0;
    *a11 = 0;
    *a12 = 0;
    v14 = 1;
    v15 = 1;
    if ( a1 )
    {
      v15 = a2;
      if ( !a2 )
        core::panicking::panic(
          "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_"
          "utils\\src\\lib.rs",
          32,
          &off_1803491E0);
    }
    if ( a3 )
    {
      v14 = a4;
      if ( !a4 )
        core::panicking::panic(
          "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_"
          "utils\\src\\lib.rs",
          32,
          &off_1803491E0);
    }
    if ( a5 )
    {
      v16 = a6;
      if ( !a6 )
        core::panicking::panic(
          "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_"
          "utils\\src\\lib.rs",
          32,
          &off_1803491E0);
    }
    else
    {
      v16 = 4;
    }
    v40[0] = v15;
    v40[1] = a1;
    v39[0] = v14;
    v39[1] = a3;
    v45 = v40;
    v46 = (__int64)&qword_1803491F8;
    variation::fvar::get_fvar_axis_info(&v42, &v45, 0, (unsigned int)a1);
    if ( !__OFSUB__(-v42, 1) )
    {
      v48 = v42;
      lpMem = v43;
      LODWORD(v17) = v44;
      v45 = 0;
      v46 = 4;
      v47 = 0;
      if ( v44 )
      {
        v41 = v44;
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2((unsigned int)&v45, 0, v44, 4, 8);
        v18 = v46;
        v19 = v47;
        v30 = 0;
        v17 = v41;
        do
        {
          v32 = (int *)((char *)lpMem + 24 * v30);
          v33 = *v32;
          if ( a5 )
          {
            v34 = 8 * a5;
            v35 = (_DWORD *)v16;
            while ( *v35 != v33 )
            {
              v35 += 2;
              v34 -= 8;
              if ( !v34 )
                goto LABEL_29;
            }
            v36 = v35[1];
            v31 = v32[3];
            if ( v36 < v31 )
              v31 = v36;
            v37 = v32[2];
            if ( v36 <= v37 )
              v31 = v37;
          }
          else
          {
LABEL_29:
            v31 = v32[1];
          }
          *(_DWORD *)(v18 + 8 * v19) = v33;
          *(_DWORD *)(v18 + 8 * v19++ + 4) = v31;
          ++v30;
        }
        while ( v30 != v17 );
      }
      else
      {
        v18 = 4;
        v19 = 0;
      }
      v47 = v19;
      v42 = 0;
      v43 = (LPVOID)4;
      v44 = 0;
      if ( (unsigned __int16)variation::fvar::normalize_axis_values((_DWORD)lpMem, v17, v18, v19, (__int64)&v42) == 5119
        && (v20 = v43,
            v21 = v44,
            (unsigned __int16)variation::avar::apply_axis_variations(
                                (unsigned int)v39,
                                (unsigned int)&qword_1803491F8,
                                0,
                                a3,
                                (__int64)v43,
                                v44) == 5119) )
      {
        v22 = (__int64)v45;
        v23 = v42;
        if ( v48 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, lpMem);
        }
        if ( !__OFSUB__(-v22, 1) )
        {
          *a7 = v18;
          *a8 = v19;
          *a9 = v22;
          *a10 = v20;
          *a11 = v21;
          *a12 = v23;
        }
      }
      else
      {
        if ( v42 )
        {
          v25 = v43;
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v25);
        }
        if ( v45 )
        {
          v27 = GetProcessHeap();
          HeapFree(v27, 0, (LPVOID)v18);
        }
        if ( v48 )
        {
          v28 = GetProcessHeap();
          HeapFree(v28, 0, lpMem);
        }
      }
    }
  }
  catch ( __int64 v51 )
  {
    v48 = std::panicking::catch_unwind::cleanup(v51);
    lpMem = v38;
    if ( *(_QWORD *)lpMem )
      (*(void (__fastcall **)(__int64))lpMem)(v48);
    result = 2147500037LL;
    if ( *((_QWORD *)lpMem + 1) )
    {
      sub_180022DE0(v48, *((_QWORD *)lpMem + 2));
      return 2147500037LL;
    }
    return result;
  }
  catch ( ... )
  {
    std::panicking::__rust_foreign_exception();
  }
  return 0;
}

```

## disassembly

```asm
0x180113540  push    rbp
0x180113541  push    r15
0x180113543  push    r14
0x180113545  push    r13
0x180113547  push    r12
0x180113549  push    rsi
0x18011354a  push    rdi
0x18011354b  push    rbx
0x18011354c  sub     rsp, 0A8h
0x180113553  lea     rbp, [rsp+80h]
0x18011355b  mov     [rbp+60h+var_48], 0FFFFFFFFFFFFFFFEh
0x180113563  mov     rsi, r8
0x180113566  mov     rax, rcx
0x180113569  mov     rcx, [rbp+60h+arg_58]
0x180113570  mov     r8, [rbp+60h+arg_50]
0x180113577  mov     r10, [rbp+60h+arg_48]
0x18011357e  mov     r11, [rbp+60h+arg_40]
0x180113585  mov     rdi, [rbp+60h+arg_38]
0x18011358c  mov     r13, [rbp+60h+arg_30]
0x180113593  mov     qword ptr [r13+0], 0
0x18011359b  mov     qword ptr [rdi], 0
0x1801135a2  mov     qword ptr [r11], 0
0x1801135a9  mov     qword ptr [r10], 0
0x1801135b0  mov     qword ptr [r8], 0
0x1801135b7  mov     qword ptr [rcx], 0
0x1801135be  mov     ecx, 1
0x1801135c3  mov     r8d, 1
0x1801135c9  test    rax, rax
0x1801135cc  jz      short loc_1801135DA
0x1801135ce  mov     r8, rdx
0x1801135d1  test    rdx, rdx
0x1801135d4  jz      loc_1801137EB
0x1801135da  test    rsi, rsi
0x1801135dd  jz      short loc_1801135EB
0x1801135df  mov     rcx, r9
0x1801135e2  test    r9, r9
0x1801135e5  jz      loc_180113805
0x1801135eb  mov     r15, [rbp+60h+arg_20]
0x1801135f2  test    r15, r15
0x1801135f5  jz      short loc_180113620
0x1801135f7  mov     r12, [rbp+60h+arg_28]
0x1801135fe  test    r12, r12
0x180113601  jnz     short loc_180113626
0x180113603  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18011360a  lea     r8, off_1803491E0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x180113611  mov     edx, 20h ; ' '
0x180113616  call    core__panicking__panic
0x18011361b  jmp     loc_18011381D
0x180113620  mov     r12d, 4
0x180113626  mov     [rbp+60h+var_A0], r8
0x18011362a  mov     [rbp+60h+var_98], rax
0x18011362e  mov     [rbp+60h+var_B0], rcx
0x180113632  mov     [rbp+60h+var_A8], rsi
0x180113636  lea     rcx, [rbp+60h+var_A0]
0x18011363a  mov     [rbp+60h+var_70], rcx
0x18011363e  lea     rcx, qword_1803491F8
0x180113645  mov     [rbp+60h+var_68], rcx
0x180113649  lea     r14, [rbp+60h+var_88]
0x18011364d  lea     rdx, [rbp+60h+var_70]
0x180113651  mov     rcx, r14
0x180113654  xor     r8d, r8d
0x180113657  mov     r9d, eax
0x18011365a  call    variation__fvar__get_fvar_axis_info
0x18011365f  mov     rcx, [rbp+60h+var_88]
0x180113663  mov     rax, rcx
0x180113666  neg     rax
0x180113669  jo      loc_1801137D5
0x18011366f  mov     [rbp+60h+var_58], rcx
0x180113673  mov     rax, [rbp+60h+var_80]
0x180113677  mov     [rbp+60h+lpMem], rax
0x18011367b  mov     rdx, [rbp+60h+var_78]
0x18011367f  mov     [rbp+60h+var_70], 0
0x180113687  mov     [rbp+60h+var_68], 4
0x18011368f  mov     [rbp+60h+var_60], 0
0x180113697  test    rdx, rdx
0x18011369a  jnz     loc_18011381F
0x1801136a0  mov     edi, 4
0x1801136a5  xor     ebx, ebx
0x1801136a7  mov     [rbp+60h+var_60], rbx
0x1801136ab  mov     [rbp+60h+var_88], 0
0x1801136b3  mov     [rbp+60h+var_80], 4
0x1801136bb  mov     [rbp+60h+var_78], 0
0x1801136c3  mov     [rsp+0E0h+var_C0], r14
0x1801136c8  mov     rcx, [rbp+60h+lpMem]
0x1801136cc  mov     r8, rdi
0x1801136cf  mov     r9, rbx
0x1801136d2  call    variation__fvar__normalize_axis_values
0x1801136d7  movzx   eax, ax
0x1801136da  cmp     eax, 13FFh
0x1801136df  jnz     loc_18011377F
0x1801136e5  mov     r14, [rbp+60h+var_80]
0x1801136e9  mov     r15, [rbp+60h+var_78]
0x1801136ed  mov     [rsp+0E0h+var_B8], r15
0x1801136f2  mov     [rsp+0E0h+var_C0], r14
0x1801136f7  lea     rdx, qword_1803491F8
0x1801136fe  lea     rcx, [rbp+60h+var_B0]
0x180113702  xor     r8d, r8d
0x180113705  mov     r9d, esi
0x180113708  call    variation__avar__apply_axis_variations
0x18011370d  movzx   eax, ax
0x180113710  cmp     eax, 13FFh
0x180113715  jnz     short loc_18011377F
0x180113717  mov     r12, [rbp+60h+var_70]
0x18011371b  mov     rsi, [rbp+60h+var_88]
0x18011371f  cmp     [rbp+60h+var_58], 0
0x180113724  jz      short loc_18011373B
0x180113726  call    cs:__imp_GetProcessHeap
0x18011372c  mov     rcx, rax; hHeap
0x18011372f  xor     edx, edx; dwFlags
0x180113731  mov     r8, [rbp+60h+lpMem]; lpMem
0x180113735  call    cs:__imp_HeapFree
0x18011373b  mov     rax, r12
0x18011373e  neg     rax
0x180113741  jo      loc_1801137D5
0x180113747  mov     [r13+0], rdi
0x18011374b  mov     rax, [rbp+60h+arg_38]
0x180113752  mov     [rax], rbx
0x180113755  mov     rax, [rbp+60h+arg_40]
0x18011375c  mov     [rax], r12
0x18011375f  mov     rax, [rbp+60h+arg_48]
0x180113766  mov     [rax], r14
0x180113769  mov     rax, [rbp+60h+arg_50]
0x180113770  mov     [rax], r15
0x180113773  mov     rax, [rbp+60h+arg_58]
0x18011377a  mov     [rax], rsi
0x18011377d  jmp     short loc_1801137D5
0x18011377f  cmp     [rbp+60h+var_88], 0
0x180113784  jz      short loc_18011379E
0x180113786  mov     rsi, [rbp+60h+var_80]
0x18011378a  call    cs:__imp_GetProcessHeap
0x180113790  mov     rcx, rax; hHeap
0x180113793  xor     edx, edx; dwFlags
0x180113795  mov     r8, rsi; lpMem
0x180113798  call    cs:__imp_HeapFree
0x18011379e  cmp     [rbp+60h+var_70], 0
0x1801137a3  jz      short loc_1801137B9
0x1801137a5  call    cs:__imp_GetProcessHeap
0x1801137ab  mov     rcx, rax; hHeap
0x1801137ae  xor     edx, edx; dwFlags
0x1801137b0  mov     r8, rdi; lpMem
0x1801137b3  call    cs:__imp_HeapFree
0x1801137b9  cmp     [rbp+60h+var_58], 0
0x1801137be  jz      short loc_1801137D5
0x1801137c0  call    cs:__imp_GetProcessHeap
0x1801137c6  mov     rcx, rax; hHeap
0x1801137c9  xor     edx, edx; dwFlags
0x1801137cb  mov     r8, [rbp+60h+lpMem]; lpMem
0x1801137cf  call    cs:__imp_HeapFree
0x1801137d5  xor     eax, eax
0x1801137d7  add     rsp, 0A8h
0x1801137de  pop     rbx
0x1801137df  pop     rdi
0x1801137e0  pop     rsi
0x1801137e1  pop     r12
0x1801137e3  pop     r13
0x1801137e5  pop     r14
0x1801137e7  pop     r15
0x1801137e9  pop     rbp
0x1801137ea  retn
0x1801137eb  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x1801137f2  lea     r8, off_1803491E0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x1801137f9  mov     edx, 20h ; ' '
0x1801137fe  call    core__panicking__panic
0x180113803  jmp     short loc_18011381D
0x180113805  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18011380c  lea     r8, off_1803491E0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x180113813  mov     edx, 20h ; ' '
0x180113818  call    core__panicking__panic
0x18011381d  ud2
0x18011381f  mov     [rsp+0E0h+var_C0], 8
0x180113828  lea     rcx, [rbp+60h+var_70]
0x18011382c  mov     r9d, 4
0x180113832  mov     r8, rdx
0x180113835  xor     edx, edx
0x180113837  mov     [rbp+60h+var_90], r8
0x18011383b  call    alloc__raw_vec__impl$4__reserve__do_reserve_and_handle_alloc__alloc__Global__2
0x180113840  mov     rdi, [rbp+60h+var_68]
0x180113844  mov     rbx, [rbp+60h+var_60]
0x180113848  lea     rax, ds:0[r15*8]
0x180113850  xor     ecx, ecx
0x180113852  mov     rdx, [rbp+60h+var_90]
0x180113856  jmp     short loc_180113874
0x180113858  mov     r10d, [r9+4]
0x18011385c  mov     [rdi+rbx*8], r8d
0x180113860  mov     [rdi+rbx*8+4], r10d
0x180113865  inc     rbx
0x180113868  inc     rcx
0x18011386b  cmp     rcx, rdx
0x18011386e  jz      loc_1801136A7
0x180113874  lea     r8, [rcx+rcx*2]
0x180113878  mov     r10, [rbp+60h+lpMem]
0x18011387c  lea     r9, [r10+r8*8]
0x180113880  mov     r8d, [r10+r8*8]
0x180113884  test    r15, r15
0x180113887  jz      short loc_180113858
0x180113889  mov     r11, rax
0x18011388c  mov     r10, r12
0x18011388f  cmp     [r10], r8d
0x180113892  jz      short loc_1801138A0
0x180113894  add     r10, 8
0x180113898  add     r11, 0FFFFFFFFFFFFFFF8h
0x18011389c  jnz     short loc_18011388F
0x18011389e  jmp     short loc_180113858
0x1801138a0  mov     r11d, [r10+4]
0x1801138a4  mov     r10d, [r9+0Ch]
0x1801138a8  cmp     r11d, r10d
0x1801138ab  cmovl   r10d, r11d
0x1801138af  mov     r9d, [r9+8]
0x1801138b3  cmp     r11d, r9d
0x1801138b6  cmovle  r10d, r9d
0x1801138ba  jmp     short loc_18011385C
0x1801138bc  mov     rax, [rbp+60h+lpMem]
0x1801138c0  mov     rax, [rax]
0x1801138c3  test    rax, rax
0x1801138c6  jz      short loc_1801138D2
0x1801138c8  mov     rcx, [rbp+60h+var_58]
0x1801138cc  call    cs:__guard_dispatch_icall_fptr
0x1801138d2  mov     eax, 80004005h
0x1801138d7  mov     rcx, [rbp+60h+lpMem]
0x1801138db  cmp     qword ptr [rcx+8], 0
0x1801138e0  jz      loc_1801137D7
0x1801138e6  mov     rdx, [rcx+10h]
0x1801138ea  mov     rcx, [rbp+60h+var_58]
0x1801138ee  call    sub_180022DE0
0x1801138f3  mov     eax, 80004005h
0x1801138f8  jmp     loc_1801137D7
```
