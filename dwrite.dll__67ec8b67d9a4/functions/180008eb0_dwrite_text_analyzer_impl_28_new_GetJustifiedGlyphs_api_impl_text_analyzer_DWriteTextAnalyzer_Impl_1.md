# dwrite::text_analyzer::impl$28::new::GetJustifiedGlyphs_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_

- ea: `0x180008eb0`
- end: `0x1800094c5`
- name: `dwrite::text_analyzer::impl$28::new::GetJustifiedGlyphs_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_`
- size: `1557`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180008eb0`
- `0x180022de0`
- `0x180056990`
- `0x180316190`
- `0x180316ae0`
- `0x180316ee0`

## import_xrefs

- `oleaut32!GetErrorInfo` at `0x180008fc1`
- `oleaut32!GetErrorInfo` at `0x1800092cf`
- `oleaut32!GetErrorInfo` at `0x180009433`
- `oleaut32!GetErrorInfo` at `0x180008fc1`
- `oleaut32!GetErrorInfo` at `0x1800092cf`
- `oleaut32!GetErrorInfo` at `0x180009433`

## string_xrefs

- `0x18000913b`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x18000935a`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x180009390`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x1800093c6`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x1800093fc`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall dwrite::text_analyzer::impl_28::new::GetJustifiedGlyphs_api_impl::text_analyzer::DWriteTextAnalyzer_Impl__1_(
        __int64 a1,
        _QWORD *a2,
        float a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        void *Src,
        __int64 a10,
        void *a11,
        void *a12,
        __int64 a13,
        _DWORD *a14,
        __int64 a15,
        void *a16,
        void *a17,
        void *a18)
{
  __int64 v18; // r8
  __int64 v19; // r13
  __int64 v20; // r15
  __int64 v21; // r12
  unsigned __int64 v22; // rsi
  unsigned int v23; // r10d
  _QWORD *v24; // rdi
  bool v25; // cl
  IErrorInfo *v26; // rcx
  unsigned int v27; // ebx
  __int64 result; // rax
  int v29; // eax
  __int64 (*v30)(void); // rax
  void (__fastcall *v31)(_QWORD *); // rax
  _QWORD *v32; // r11
  unsigned __int64 *v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // r14d
  IErrorInfo *v37; // rdi
  _QWORD *v38; // rdx
  IErrorInfo *v39; // r14
  IErrorInfo *v40; // r14
  int v41; // esi
  _QWORD *v42; // rdx
  __int64 v43; // [rsp+E0h] [rbp+60h] BYREF
  unsigned __int64 v44; // [rsp+E8h] [rbp+68h] BYREF
  _QWORD *v45; // [rsp+F0h] [rbp+70h]
  __int64 v46; // [rsp+F8h] [rbp+78h]
  _QWORD *v47; // [rsp+100h] [rbp+80h]
  IErrorInfo *pperrinfo; // [rsp+108h] [rbp+88h] BYREF
  int v49; // [rsp+110h] [rbp+90h]
  __int64 v50; // [rsp+118h] [rbp+98h]
  _QWORD *v51; // [rsp+120h] [rbp+A0h]
  char v52; // [rsp+12Fh] [rbp+AFh]
  __int64 v53; // [rsp+130h] [rbp+B0h]
  __int64 v54; // [rsp+138h] [rbp+B8h] BYREF

  v53 = -2;
  *a14 = 0;
  if ( a3 < 0.0 )
    goto LABEL_8;
  v18 = a15;
  if ( (_DWORD)a5 )
  {
    if ( a8 == 0 || a15 == 0 )
      goto LABEL_8;
  }
  v19 = (__int64)a18;
  v20 = (__int64)a17;
  v21 = (__int64)a16;
  LODWORD(v22) = a7;
  if ( (_DWORD)a7 )
  {
    if ( a16 == 0 || a17 == 0 || a18 == 0 )
      goto LABEL_8;
  }
  v23 = a6;
  if ( !(_DWORD)a6 )
    return 0;
  v24 = a2;
  v25 = Src != 0 && a10 != 0;
  if ( a13 == 0 || !v25 || a11 == 0 || a12 == 0 )
  {
LABEL_8:
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    v26 = pperrinfo;
    v27 = -2147024809;
LABEL_9:
    if ( v26 )
      ((void (__fastcall *)(IErrorInfo *))v26->lpVtbl->Release)(v26);
    return v27;
  }
  try
  {
    v44 = 0;
    if ( a2 )
    {
      v45 = a4;
      (*(void (__fastcall **)(_QWORD *))(*a2 + 8LL))(a2);
      v43 = 0;
      v29 = (*(__int64 (__fastcall **)(_QWORD *, int *, __int64 *))*v24)(v24, &dword_1803B3704, &v43);
      v51 = v24;
      if ( v29 < 0 )
      {
        v41 = v29;
      }
      else
      {
        if ( v43 )
        {
          v30 = *(__int64 (**)(void))(*(_QWORD *)v43 + 544LL);
          v50 = v43;
          v22 = v30();
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v22 + 8LL))(v22);
          v31 = *(void (__fastcall **)(_QWORD *))(*v51 + 16LL);
          v44 = v22;
          v31(v51);
          v32 = (_QWORD *)v22;
          LOBYTE(v24) = 1;
          v33 = &v44;
          LODWORD(a4) = (_DWORD)v45;
          LODWORD(v22) = a7;
          v18 = a15;
          v23 = a6;
LABEL_18:
          v34 = 2;
          v35 = 2;
          if ( (_DWORD)a5 )
          {
            v34 = a8;
            if ( !a8 )
            {
              v47 = v32;
              v46 = v50;
              v52 = (char)v24;
              core::panicking::panic(
                "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\in"
                "terop_utils\\src\\lib.rs",
                32,
                &off_1803491E0);
            }
            v35 = v18;
            if ( !v18 )
            {
              v47 = v32;
              v46 = v50;
              v52 = (char)v24;
              core::panicking::panic(
                "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\in"
                "terop_utils\\src\\lib.rs",
                32,
                &off_180348CA0);
            }
          }
          if ( (_DWORD)v22 )
          {
            if ( !a16 )
            {
              v47 = v32;
              v46 = v50;
              v52 = (char)v24;
              core::panicking::panic(
                "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\in"
                "terop_utils\\src\\lib.rs",
                32,
                &off_180348CA0);
            }
            if ( !a17 )
            {
              v47 = v32;
              v46 = v50;
              v52 = (char)v24;
              core::panicking::panic(
                "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\in"
                "terop_utils\\src\\lib.rs",
                32,
                &off_180348CA0);
            }
            if ( !a18 )
            {
              v47 = v32;
              v46 = v50;
              v52 = (char)v24;
              core::panicking::panic(
                "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\in"
                "terop_utils\\src\\lib.rs",
                32,
                &off_180348CA0);
            }
          }
          else
          {
            v20 = 4;
            v21 = 2;
            v19 = 4;
          }
          v22 = (unsigned int)v22;
          v51 = v32;
          v47 = v32;
          v46 = v50;
          v45 = v24;
          v52 = (char)v24;
          layout::justification::get_justified_glyphs(
            (int)&pperrinfo,
            (int)v33,
            a5,
            (int)a4,
            (unsigned int)a5,
            v23,
            (unsigned int)v22,
            (void *)v34,
            (unsigned int)a5,
            Src,
            v23,
            a10,
            v23,
            a11,
            v23,
            a12,
            v23,
            a13,
            v23,
            (void *)v35,
            (unsigned int)a5,
            (void *)v21,
            (unsigned int)v22,
            (void *)v20,
            (unsigned int)v22,
            (void *)v19,
            (unsigned int)v22);
          goto LABEL_59;
        }
        v41 = -2147467261;
      }
      pperrinfo = 0;
      GetErrorInfo(0, &pperrinfo);
      v49 = v41;
      core::result::unwrap_failed(
        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
        43,
        (unsigned int)&pperrinfo,
        (unsigned int)&off_180335008,
        (__int64)&off_1803350B8);
    }
    v32 = 0;
    LODWORD(v33) = 0;
    v24 = 0;
    goto LABEL_18;
  }
  catch ( __int64 v54 )
  {
    v50 = std::panicking::catch_unwind::cleanup(v54);
    v51 = v42;
    if ( *v51 )
      ((void (__fastcall *)(__int64))*v51)(v50);
    if ( v51[1] )
      sub_180022DE0(v50, v51[2]);
    return 2147500037LL;
  }
  catch ( ... )
  {
    std::panicking::__rust_foreign_exception();
  }
LABEL_59:
  v36 = v49;
  v37 = pperrinfo;
  if ( v49 )
  {
    if ( (_BYTE)v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 )
      (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
    v27 = 0;
    if ( v36 != 1398755147 )
      v27 = v36;
    v26 = v37;
    goto LABEL_9;
  }
  *a14 = (_DWORD)pperrinfo;
  if ( (unsigned __int64)v37 <= v22 )
  {
    v27 = 0;
  }
  else
  {
    pperrinfo = 0;
    GetErrorInfo(0, &pperrinfo);
    v26 = pperrinfo;
    v27 = -2147024774;
  }
  v38 = v51;
  if ( (_BYTE)v45 )
  {
    v39 = v26;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v38 = v51;
    v26 = v39;
  }
  if ( v38 )
  {
    v40 = v26;
    (*(void (__fastcall **)(_QWORD *))(*v38 + 16LL))(v38);
    v26 = v40;
  }
  result = 0;
  if ( (unsigned __int64)v37 > v22 )
    goto LABEL_9;
  return result;
}

```

## disassembly

```asm
0x180008eb0  push    rbp
0x180008eb1  push    r15
0x180008eb3  push    r14
0x180008eb5  push    r13
0x180008eb7  push    r12
0x180008eb9  push    rsi
0x180008eba  push    rdi
0x180008ebb  push    rbx
0x180008ebc  sub     rsp, 158h
0x180008ec3  lea     rbp, [rsp+80h]
0x180008ecb  movaps  [rbp+110h+var_50], xmm6
0x180008ed2  mov     [rbp+110h+var_60], 0FFFFFFFFFFFFFFFEh
0x180008edd  mov     rbx, [rbp+110h+arg_68]
0x180008ee4  mov     dword ptr [rbx], 0
0x180008eea  xorps   xmm0, xmm0
0x180008eed  ucomiss xmm2, xmm0
0x180008ef0  jb      loc_180008FAD
0x180008ef6  mov     r8, [rbp+110h+arg_70]
0x180008efd  mov     r14d, dword ptr [rbp+110h+arg_20]
0x180008f04  test    r14d, r14d
0x180008f07  jz      short loc_180008F22
0x180008f09  cmp     [rbp+110h+arg_38], 0
0x180008f11  setz    al
0x180008f14  test    r8, r8
0x180008f17  setz    cl
0x180008f1a  or      cl, al
0x180008f1c  jnz     loc_180008FAD
0x180008f22  mov     r13, [rbp+110h+arg_88]
0x180008f29  mov     r15, [rbp+110h+arg_80]
0x180008f30  mov     r12, [rbp+110h+arg_78]
0x180008f37  mov     esi, dword ptr [rbp+110h+arg_30]
0x180008f3d  test    esi, esi
0x180008f3f  jz      short loc_180008F59
0x180008f41  test    r12, r12
0x180008f44  setz    al
0x180008f47  test    r15, r15
0x180008f4a  setz    cl
0x180008f4d  or      cl, al
0x180008f4f  test    r13, r13
0x180008f52  setz    al
0x180008f55  or      al, cl
0x180008f57  jnz     short loc_180008FAD
0x180008f59  mov     r10d, dword ptr [rbp+110h+arg_28]
0x180008f60  test    r10d, r10d
0x180008f63  jz      loc_180009002
0x180008f69  mov     rdi, rdx
0x180008f6c  cmp     [rbp+110h+arg_40], 0
0x180008f74  setnz   al
0x180008f77  cmp     [rbp+110h+arg_48], 0
0x180008f7f  setnz   cl
0x180008f82  and     cl, al
0x180008f84  cmp     [rbp+110h+arg_50], 0
0x180008f8c  setnz   al
0x180008f8f  cmp     [rbp+110h+arg_58], 0
0x180008f97  setnz   dl
0x180008f9a  and     dl, al
0x180008f9c  and     dl, cl
0x180008f9e  cmp     [rbp+110h+arg_60], 0
0x180008fa6  setnz   al
0x180008fa9  test    dl, al
0x180008fab  jnz     short loc_180009006
0x180008fad  mov     [rbp+110h+pperrinfo], 0
0x180008fb8  lea     rdx, [rbp+110h+pperrinfo]; pperrinfo
0x180008fbf  xor     ecx, ecx; dwReserved
0x180008fc1  call    cs:__imp_GetErrorInfo
0x180008fc7  mov     rcx, [rbp+110h+pperrinfo]
0x180008fce  mov     ebx, 80070057h
0x180008fd3  test    rcx, rcx
0x180008fd6  jz      short loc_180008FE5
0x180008fd8  mov     rax, [rcx]
0x180008fdb  mov     rax, [rax+10h]
0x180008fdf  call    cs:__guard_dispatch_icall_fptr
0x180008fe5  mov     eax, ebx
0x180008fe7  movaps  xmm6, [rbp+110h+var_50]
0x180008fee  add     rsp, 158h
0x180008ff5  pop     rbx
0x180008ff6  pop     rdi
0x180008ff7  pop     rsi
0x180008ff8  pop     r12
0x180008ffa  pop     r13
0x180008ffc  pop     r14
0x180008ffe  pop     r15
0x180009000  pop     rbp
0x180009001  retn
0x180009002  xor     eax, eax
0x180009004  jmp     short loc_180008FE7
0x180009006  mov     [rbp+110h+var_A8], 0
0x18000900e  test    rdi, rdi
0x180009011  jz      loc_1800090D5
0x180009017  mov     rcx, rdi
0x18000901a  mov     [rbp+110h+var_A0], r9
0x18000901e  movaps  xmm6, xmm2
0x180009021  mov     rax, [rdi]
0x180009024  mov     rax, [rax+8]
0x180009028  call    cs:__guard_dispatch_icall_fptr
0x18000902e  mov     [rbp+110h+var_B0], 0
0x180009036  mov     rax, [rdi]
0x180009039  mov     rax, [rax]
0x18000903c  lea     rdx, dword_1803B3704
0x180009043  lea     r8, [rbp+110h+var_B0]
0x180009047  mov     rcx, rdi
0x18000904a  call    cs:__guard_dispatch_icall_fptr
0x180009050  test    eax, eax
0x180009052  mov     [rbp+110h+var_70], rdi
0x180009059  js      loc_180009416
0x18000905f  mov     rcx, [rbp+110h+var_B0]
0x180009063  test    rcx, rcx
0x180009066  jz      loc_18000941A
0x18000906c  mov     rax, [rcx]
0x18000906f  mov     rax, [rax+220h]
0x180009076  mov     [rbp+110h+var_78], rcx
0x18000907d  call    cs:__guard_dispatch_icall_fptr
0x180009083  mov     rsi, rax
0x180009086  mov     rax, [rax]
0x180009089  mov     rax, [rax+8]
0x18000908d  mov     rcx, rsi
0x180009090  call    cs:__guard_dispatch_icall_fptr
0x180009096  mov     rcx, [rbp+110h+var_70]
0x18000909d  mov     rax, [rcx]
0x1800090a0  mov     rax, [rax+10h]
0x1800090a4  mov     [rbp+110h+var_A8], rsi
0x1800090a8  call    cs:__guard_dispatch_icall_fptr
0x1800090ae  mov     r11, rsi
0x1800090b1  mov     dil, 1
0x1800090b4  lea     rdx, [rbp+110h+var_A8]
0x1800090b8  movaps  xmm2, xmm6
0x1800090bb  mov     r9, [rbp+110h+var_A0]
0x1800090bf  mov     esi, dword ptr [rbp+110h+arg_30]
0x1800090c5  mov     r8, [rbp+110h+arg_70]
0x1800090cc  mov     r10d, dword ptr [rbp+110h+arg_28]
0x1800090d3  jmp     short loc_1800090DC
0x1800090d5  xor     r11d, r11d
0x1800090d8  xor     edx, edx; int
0x1800090da  xor     edi, edi
0x1800090dc  mov     eax, 2
0x1800090e1  mov     ecx, 2
0x1800090e6  test    r14d, r14d
0x1800090e9  jz      short loc_180009107
0x1800090eb  mov     rax, [rbp+110h+arg_38]
0x1800090f2  test    rax, rax
0x1800090f5  jz      loc_180009341
0x1800090fb  mov     rcx, r8
0x1800090fe  test    r8, r8
0x180009101  jz      loc_180009377
0x180009107  test    esi, esi
0x180009109  jz      short loc_180009158
0x18000910b  test    r12, r12
0x18000910e  jz      loc_1800093AD
0x180009114  test    r15, r15
0x180009117  jz      loc_1800093E3
0x18000911d  test    r13, r13
0x180009120  jnz     short loc_18000916A
0x180009122  mov     [rbp+110h+var_90], r11
0x180009129  mov     rax, [rbp+110h+var_78]
0x180009130  mov     [rbp+110h+var_98], rax
0x180009134  mov     [rbp+110h+var_61], dil
0x18000913b  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x180009142  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x180009149  mov     edx, 20h ; ' '
0x18000914e  call    core__panicking__panic
0x180009153  jmp     loc_180009478
0x180009158  mov     r15d, 4
0x18000915e  mov     r12d, 2
0x180009164  mov     r13d, 4
0x18000916a  mov     r8d, r14d; int
0x18000916d  mov     r10d, r10d
0x180009170  mov     esi, esi
0x180009172  mov     [rbp+110h+var_70], r11
0x180009179  mov     [rbp+110h+var_90], r11
0x180009180  mov     r11, [rbp+110h+var_78]
0x180009187  mov     [rbp+110h+var_98], r11
0x18000918b  mov     [rbp+110h+var_A0], rdi
0x18000918f  mov     [rbp+110h+var_61], dil
0x180009196  mov     [rsp+190h+var_C8], r13; void *
0x18000919e  mov     [rsp+190h+var_D8], r15; void *
0x1800091a6  mov     [rsp+190h+var_E8], r12; void *
0x1800091ae  mov     [rsp+190h+var_F8], rcx; void *
0x1800091b6  mov     rcx, [rbp+110h+arg_60]
0x1800091bd  mov     [rsp+190h+var_108], rcx; __int64
0x1800091c5  mov     rcx, [rbp+110h+arg_58]
0x1800091cc  mov     [rsp+190h+var_118], rcx; void *
0x1800091d1  mov     rcx, [rbp+110h+arg_50]
0x1800091d8  mov     [rsp+190h+var_128], rcx; void *
0x1800091dd  mov     rcx, [rbp+110h+arg_48]
0x1800091e4  mov     [rsp+190h+var_138], rcx; __int64
0x1800091e9  mov     rcx, [rbp+110h+arg_40]
0x1800091f0  mov     [rsp+190h+Src], rcx; Src
0x1800091f5  mov     [rsp+190h+var_158], rax; void *
0x1800091fa  mov     [rsp+190h+var_100], r10; __int64
0x180009202  mov     [rsp+190h+var_110], r10; __int64
0x18000920a  mov     [rsp+190h+var_120], r10; __int64
0x18000920f  mov     [rsp+190h+var_130], r10; __int64
0x180009214  mov     [rsp+190h+var_140], r10; __int64
0x180009219  mov     [rsp+190h+var_168], r10; __int64
0x18000921e  mov     [rsp+190h+var_C0], rsi; __int64
0x180009226  mov     [rsp+190h+var_D0], rsi; __int64
0x18000922e  mov     [rsp+190h+var_E0], rsi; __int64
0x180009236  mov     [rsp+190h+var_F0], r8; __int64
0x18000923e  mov     [rsp+190h+var_150], r8; __int64
0x180009243  mov     [rsp+190h+var_160], rsi; __int64
0x180009248  mov     [rsp+190h+var_170], r8; __int64
0x18000924d  lea     rcx, [rbp+110h+pperrinfo]; int
0x180009254  call    layout__justification__get_justified_glyphs
0x180009259  mov     r14d, [rbp+110h+var_80]
0x180009260  mov     rdi, [rbp+110h+pperrinfo]
0x180009267  test    r14d, r14d
0x18000926a  jz      short loc_1800092B4
0x18000926c  cmp     byte ptr [rbp+110h+var_A0], 0
0x180009270  jz      short loc_180009286
0x180009272  mov     rcx, [rbp+110h+var_78]
0x180009279  mov     rax, [rcx]
0x18000927c  mov     rax, [rax+10h]
0x180009280  call    cs:__guard_dispatch_icall_fptr
0x180009286  mov     rcx, [rbp+110h+var_70]
0x18000928d  test    rcx, rcx
0x180009290  jz      short loc_18000929F
0x180009292  mov     rax, [rcx]
0x180009295  mov     rax, [rax+10h]
0x180009299  call    cs:__guard_dispatch_icall_fptr
0x18000929f  xor     ebx, ebx
0x1800092a1  cmp     r14d, 535F4F4Bh
0x1800092a8  cmovnz  ebx, r14d
0x1800092ac  mov     rcx, rdi
0x1800092af  jmp     loc_180008FD3
0x1800092b4  mov     [rbx], edi
0x1800092b6  cmp     rdi, rsi
0x1800092b9  jbe     short loc_1800092E3
0x1800092bb  mov     [rbp+110h+pperrinfo], 0
0x1800092c6  lea     rdx, [rbp+110h+pperrinfo]; pperrinfo
0x1800092cd  xor     ecx, ecx; dwReserved
0x1800092cf  call    cs:__imp_GetErrorInfo
0x1800092d5  mov     rcx, [rbp+110h+pperrinfo]
0x1800092dc  mov     ebx, 8007007Ah
0x1800092e1  jmp     short loc_1800092E5
0x1800092e3  xor     ebx, ebx
0x1800092e5  mov     rdx, [rbp+110h+var_70]
0x1800092ec  cmp     byte ptr [rbp+110h+var_A0], 0
0x1800092f0  jz      short loc_180009316
0x1800092f2  mov     rdx, [rbp+110h+var_78]
0x1800092f9  mov     rax, [rdx]
0x1800092fc  mov     rax, [rax+10h]
0x180009300  mov     r14, rcx
0x180009303  mov     rcx, rdx
0x180009306  call    cs:__guard_dispatch_icall_fptr
0x18000930c  mov     rdx, [rbp+110h+var_70]
0x180009313  mov     rcx, r14
0x180009316  test    rdx, rdx
0x180009319  jz      short loc_180009331
0x18000931b  mov     rax, [rdx]
0x18000931e  mov     rax, [rax+10h]
0x180009322  mov     r14, rcx
0x180009325  mov     rcx, rdx
0x180009328  call    cs:__guard_dispatch_icall_fptr
0x18000932e  mov     rcx, r14
0x180009331  xor     eax, eax
0x180009333  cmp     rdi, rsi
0x180009336  ja      loc_180008FD3
0x18000933c  jmp     loc_180008FE7
0x180009341  mov     [rbp+110h+var_90], r11
0x180009348  mov     rax, [rbp+110h+var_78]
0x18000934f  mov     [rbp+110h+var_98], rax
0x180009353  mov     [rbp+110h+var_61], dil
0x18000935a  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x180009361  lea     r8, off_1803491E0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x180009368  mov     edx, 20h ; ' '
0x18000936d  call    core__panicking__panic
0x180009372  jmp     loc_180009478
0x180009377  mov     [rbp+110h+var_90], r11
0x18000937e  mov     rax, [rbp+110h+var_78]
0x180009385  mov     [rbp+110h+var_98], rax
0x180009389  mov     [rbp+110h+var_61], dil
0x180009390  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x180009397  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18000939e  mov     edx, 20h ; ' '
0x1800093a3  call    core__panicking__panic
0x1800093a8  jmp     loc_180009478
0x1800093ad  mov     [rbp+110h+var_90], r11
0x1800093b4  mov     rax, [rbp+110h+var_78]
0x1800093bb  mov     [rbp+110h+var_98], rax
0x1800093bf  mov     [rbp+110h+var_61], dil
0x1800093c6  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x1800093cd  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x1800093d4  mov     edx, 20h ; ' '
0x1800093d9  call    core__panicking__panic
0x1800093de  jmp     loc_180009478
0x1800093e3  mov     [rbp+110h+var_90], r11
0x1800093ea  mov     rax, [rbp+110h+var_78]
0x1800093f1  mov     [rbp+110h+var_98], rax
0x1800093f5  mov     [rbp+110h+var_61], dil
0x1800093fc  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x180009403  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18000940a  mov     edx, 20h ; ' '
0x18000940f  call    core__panicking__panic
0x180009414  jmp     short loc_180009478
0x180009416  mov     esi, eax
0x180009418  jmp     short loc_18000941F
0x18000941a  mov     esi, 80004003h
0x18000941f  mov     [rbp+110h+pperrinfo], 0
0x18000942a  lea     rdx, [rbp+110h+pperrinfo]; pperrinfo
0x180009431  xor     ecx, ecx; dwReserved
  ... truncated ...
```
