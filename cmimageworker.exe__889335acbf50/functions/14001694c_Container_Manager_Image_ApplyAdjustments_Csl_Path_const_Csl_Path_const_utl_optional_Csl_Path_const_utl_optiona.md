# Container::Manager::Image::ApplyAdjustments(Csl::Path const &,Csl::Path const &,utl::optional<Csl::Path> const &,utl::optional<Csl::Path> const &,bool)

- ea: `0x14001694c`
- end: `0x140016d97`
- name: `?ApplyAdjustments@Image@Manager@Container@@YAJAEBVPath@Csl@@0AEBV?$optional@VPath@Csl@@@utl@@1_N@Z`
- size: `1099`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x140005fbc`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140002b8c`
- `0x140006fe4`
- `0x14000c44c`
- `0x14000db70`
- `0x140011750`
- `0x140015f98`
- `0x14001694c`
- `0x140016da0`
- `0x14002e8cc`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::ApplyAdjustments(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rcx
  __int64 v5; // r15
  __m128i si128; // xmm6
  __int64 v7; // r13
  int EntireFile; // eax
  unsigned int v9; // edi
  char *v11; // rdi
  _QWORD *v12; // rcx
  size_t v13; // rsi
  void *v14; // r12
  char v15; // r14
  unsigned __int64 v16; // rax
  size_t v17; // r15
  _QWORD *v18; // rax
  _QWORD *v19; // r14
  size_t v20; // rax
  unsigned int v21; // esi
  bool v22; // zf
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // [rsp+20h] [rbp-E0h]
  _QWORD *Src; // [rsp+30h] [rbp-D0h]
  _QWORD v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v30[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v31[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  __m128i v33; // [rsp+90h] [rbp-70h] BYREF
  __m128i v34; // [rsp+A0h] [rbp-60h]
  __m128i v35; // [rsp+B0h] [rbp-50h]
  __m128i v36; // [rsp+C0h] [rbp-40h]
  __m128i v37; // [rsp+D0h] [rbp-30h]
  __m128i v38; // [rsp+E0h] [rbp-20h]
  _OWORD v39[7]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v4 = *a2;
  v5 = a4;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v7 = a3;
  *(__m128i *)v31 = si128;
  v32 = -1;
  EntireFile = Csl::ReadEntireFile(v4, v31);
  v9 = EntireFile;
  if ( EntireFile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)EntireFile,
      v26);
    if ( v31[0] != (void *)-1LL )
      operator delete(v31[0], (const struct std::nothrow_t *)&std::nothrow);
    return v9;
  }
  v11 = (char *)v31[0];
  v12 = v28;
  v13 = (char *)v31[1] - (char *)v31[0];
  Src = v28;
  v14 = (void *)((char *)v31[1] - (char *)v31[0]);
  LOBYTE(v28[0]) = 0;
  v15 = 1;
  if ( v31[1] != v31[0] )
  {
    if ( v13 <= 0xF )
    {
LABEL_14:
      memset_0(v12, 0, v13);
      goto LABEL_15;
    }
    v16 = (char *)v31[1] - (char *)v31[0];
    if ( v13 <= 0x1F )
      v16 = 31;
    if ( v16 > 0x7FFFFFFFFFFFFFEFLL )
      v16 = 0x7FFFFFFFFFFFFFEFLL;
    if ( v13 <= v16 )
    {
      v17 = (v16 + 16) & 0xFFFFFFFFFFFFFFF0uLL;
      v18 = operator new(v17, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v18;
      if ( v18 )
      {
        memcpy_0(v18, v28, 1u);
        v20 = v17 - 1;
        Src = v19;
        v5 = a4;
        v12 = v19;
        v7 = a3;
        v28[0] = (char *)v19 + v20;
        v15 = 1;
        goto LABEL_14;
      }
      v5 = a4;
    }
    v15 = 0;
    v14 = 0;
  }
LABEL_15:
  *((_BYTE *)Src + (_QWORD)v14) = 0;
  if ( !v15 )
  {
    v21 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v26);
LABEL_17:
    if ( Src != v28 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v22 = v11 + 1 == 0;
LABEL_20:
    if ( !v22 )
      operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
    return v21;
  }
  memcpy_0(Src, v11, v13);
  v29[0] = v30;
  v31[0] = Src;
  v29[1] = v30;
  v30[0] = 0;
  v31[1] = v14;
  v23 = Csl::StringToWideString(v31, v29);
  v21 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v23,
      v26);
    goto LABEL_27;
  }
  v33 = si128;
  v34 = si128;
  v35 = si128;
  v36 = si128;
  v37 = si128;
  v38 = si128;
  v24 = Csl::MarshalFromJson<Container::Manager::Image::ImageAdjustments>((__int64)v29[0]);
  v21 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v24,
      v26);
    Container::Manager::Image::ImageAdjustments::~ImageAdjustments((Container::Manager::Image::ImageAdjustments *)&v33);
LABEL_27:
    if ( v29[0] != v30 )
      operator delete(v29[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_17;
  }
  v39[0] = v33;
  v39[1] = v34;
  v39[2] = v35;
  v39[3] = v36;
  v39[4] = v37;
  v39[5] = v38;
  v33 = si128;
  v34.m128i_i64[0] = -1;
  v34.m128i_i64[1] = -1;
  v35 = si128;
  v36 = si128;
  v37.m128i_i64[0] = -1;
  v37.m128i_i64[1] = -1;
  v38 = si128;
  LOBYTE(v26) = 0;
  v25 = Container::Manager::Image::ApplyAdjustments(a1, v39, v7, v5);
  v21 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v25,
      v26);
    Container::Manager::Image::ImageAdjustments::~ImageAdjustments((Container::Manager::Image::ImageAdjustments *)&v33);
    if ( v29[0] != v30 )
      operator delete(v29[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( Src != v28 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v22 = v11 == (char *)-1LL;
    goto LABEL_20;
  }
  Container::Manager::Image::ImageAdjustments::~ImageAdjustments((Container::Manager::Image::ImageAdjustments *)&v33);
  if ( v29[0] != v30 )
    operator delete(v29[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( Src != v28 )
    operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
  if ( v11 != (char *)-1LL )
    operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x14001694c  mov     rax, rsp
0x14001694f  mov     [rax+10h], rbx
0x140016953  mov     [rax+20h], r9
0x140016957  mov     [rax+18h], r8
0x14001695b  mov     [rax+8], rcx
0x14001695f  push    rbp
0x140016960  push    rsi
0x140016961  push    rdi
0x140016962  push    r12
0x140016964  push    r13
0x140016966  push    r14
0x140016968  push    r15
0x14001696a  lea     rbp, [rsp-60h]
0x14001696f  sub     rsp, 160h
0x140016976  mov     rcx, [rdx]
0x140016979  mov     r15, r9
0x14001697c  movaps  xmmword ptr [rax-48h], xmm6
0x140016980  lea     rdx, [rsp+190h+var_120]
0x140016985  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001698d  mov     r13, r8
0x140016990  movdqu  xmmword ptr [rsp+190h+var_120], xmm6
0x140016996  mov     [rbp+90h+var_110], 0FFFFFFFFFFFFFFFFh
0x14001699e  call    ?ReadEntireFile@Csl@@YAJPEBGAEAV?$vector@EV?$allocator@E@utl@@@utl@@@Z; Csl::ReadEntireFile(ushort const *,utl::vector<uchar,utl::allocator<uchar>> &)
0x1400169a3  mov     edi, eax
0x1400169a5  test    eax, eax
0x1400169a7  jns     short loc_1400169E2
0x1400169a9  mov     rcx, [rbp+98h]; this
0x1400169b0  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400169b7  mov     r9d, eax; char *
0x1400169ba  mov     edx, 4E0h; void *
0x1400169bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400169c4  mov     rcx, [rsp+190h+var_120]; void *
0x1400169c9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400169cd  jz      short loc_1400169DB
0x1400169cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400169d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400169db  mov     eax, edi
0x1400169dd  jmp     loc_140016D76
0x1400169e2  mov     rsi, [rsp+190h+var_120+8]
0x1400169e7  lea     rax, [rsp+190h+var_150]
0x1400169ec  mov     rdi, [rsp+190h+var_120]
0x1400169f1  lea     rcx, [rsp+190h+var_150]
0x1400169f6  sub     rsi, rdi
0x1400169f9  mov     [rsp+190h+Src], rax
0x1400169fe  mov     r12, rsi
0x140016a01  mov     [rsp+190h+var_158], rcx
0x140016a06  mov     byte ptr [rsp+190h+var_150], 0
0x140016a0b  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140016a12  mov     r14b, 1
0x140016a15  jz      loc_140016ACD
0x140016a1b  cmp     rsi, 0Fh
0x140016a1f  jbe     loc_140016AC3
0x140016a25  mov     ecx, 1Fh
0x140016a2a  mov     rax, rsi
0x140016a2d  cmp     rsi, rcx
0x140016a30  cmovbe  rax, rcx
0x140016a34  mov     rcx, 7FFFFFFFFFFFFFEFh
0x140016a3e  cmp     rax, rcx
0x140016a41  cmova   rax, rcx
0x140016a45  cmp     rsi, rax
0x140016a48  ja      loc_140016B38
0x140016a4e  lea     r15, [rax+10h]
0x140016a52  mov     rdx, rbx; struct std::nothrow_t *
0x140016a55  and     r15, 0FFFFFFFFFFFFFFF0h
0x140016a59  mov     rcx, r15; unsigned __int64
0x140016a5c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140016a61  mov     r14, rax
0x140016a64  test    rax, rax
0x140016a67  jz      loc_140016B31
0x140016a6d  mov     r13, [rsp+190h+var_158]
0x140016a72  mov     rcx, rax; void *
0x140016a75  mov     rdx, [rsp+190h+Src]; Src
0x140016a7a  sub     r13, rdx
0x140016a7d  lea     r8, [r13+1]; Size
0x140016a81  call    memcpy_0
0x140016a86  mov     rcx, [rsp+190h+Src]; void *
0x140016a8b  lea     rax, [rsp+190h+var_150]
0x140016a90  cmp     rcx, rax
0x140016a93  jz      short loc_140016A9D
0x140016a95  mov     rdx, rbx; struct std::nothrow_t *
0x140016a98  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016a9d  lea     rax, [r15-1]
0x140016aa1  mov     [rsp+190h+Src], r14
0x140016aa6  mov     r15, [rbp+90h+arg_18]
0x140016aad  lea     rcx, [r14+r13]; void *
0x140016ab1  mov     r13, [rbp+90h+arg_10]
0x140016ab8  add     rax, r14
0x140016abb  mov     [rsp+190h+var_150], rax
0x140016ac0  mov     r14b, 1
0x140016ac3  mov     r8, rsi; Size
0x140016ac6  xor     edx, edx; Val
0x140016ac8  call    memset_0
0x140016acd  mov     rcx, [rsp+190h+Src]
0x140016ad2  add     rcx, r12
0x140016ad5  mov     [rsp+190h+var_158], rcx
0x140016ada  mov     byte ptr [rcx], 0
0x140016add  test    r14b, r14b
0x140016ae0  jnz     short loc_140016B40
0x140016ae2  mov     rcx, [rbp+98h]; this
0x140016ae9  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016af0  mov     esi, 8007000Eh
0x140016af5  mov     edx, 4E3h; void *
0x140016afa  mov     r9d, esi; char *
0x140016afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016b02  mov     rcx, [rsp+190h+Src]; void *
0x140016b07  lea     rax, [rsp+190h+var_150]
0x140016b0c  cmp     rcx, rax
0x140016b0f  jz      short loc_140016B19
0x140016b11  mov     rdx, rbx; struct std::nothrow_t *
0x140016b14  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016b19  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140016b1d  jz      short loc_140016B2A
0x140016b1f  mov     rdx, rbx; struct std::nothrow_t *
0x140016b22  mov     rcx, rdi; void *
0x140016b25  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016b2a  mov     eax, esi
0x140016b2c  jmp     loc_140016D76
0x140016b31  mov     r15, [rbp+90h+arg_18]
0x140016b38  xor     r14b, r14b
0x140016b3b  xor     r12d, r12d
0x140016b3e  jmp     short loc_140016ACD
0x140016b40  mov     rcx, [rsp+190h+Src]; void *
0x140016b45  mov     r8, rsi; Size
0x140016b48  mov     rdx, rdi; Src
0x140016b4b  call    memcpy_0
0x140016b50  mov     rcx, [rsp+190h+Src]
0x140016b55  lea     rax, [rsp+190h+var_130]
0x140016b5a  mov     [rsp+190h+var_140], rax
0x140016b5f  lea     rdx, [rsp+190h+var_140]
0x140016b64  lea     rax, [rsp+190h+var_130]
0x140016b69  mov     [rsp+190h+var_120], rcx
0x140016b6e  mov     [rsp+190h+var_138], rax
0x140016b73  xor     eax, eax
0x140016b75  mov     [rsp+190h+var_130], ax
0x140016b7a  mov     rax, [rsp+190h+var_158]
0x140016b7f  sub     rax, rcx
0x140016b82  lea     rcx, [rsp+190h+var_120]
0x140016b87  mov     [rsp+190h+var_120+8], rax
0x140016b8c  call    ?StringToWideString@Csl@@YAJAEBV?$basic_string_view@DU?$char_traits@D@utl@@@utl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@Z; Csl::StringToWideString(utl::basic_string_view<char,utl::char_traits<char>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x140016b91  mov     esi, eax
0x140016b93  test    eax, eax
0x140016b95  jns     short loc_140016BD2
0x140016b97  mov     rcx, [rbp+98h]; this
0x140016b9e  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016ba5  mov     r9d, eax; char *
0x140016ba8  mov     edx, 4EAh; void *
0x140016bad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016bb2  mov     rcx, [rsp+190h+var_140]; void *
0x140016bb7  lea     rax, [rsp+190h+var_130]
0x140016bbc  cmp     rcx, rax
0x140016bbf  jz      loc_140016B02
0x140016bc5  mov     rdx, rbx; struct std::nothrow_t *
0x140016bc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016bcd  jmp     loc_140016B02
0x140016bd2  mov     rcx, [rsp+190h+var_140]
0x140016bd7  lea     rdx, [rbp+90h+var_100]
0x140016bdb  movdqa  [rbp+90h+var_100], xmm6
0x140016be0  movdqa  [rbp+90h+var_F0], xmm6
0x140016be5  movdqa  [rbp+90h+var_E0], xmm6
0x140016bea  movdqa  [rbp+90h+var_D0], xmm6
0x140016bef  movdqa  [rbp+90h+var_C0], xmm6
0x140016bf4  movdqa  [rbp+90h+var_B0], xmm6
0x140016bf9  call    ??$MarshalFromJson@UImageAdjustments@Image@Manager@Container@@@Csl@@YAJPEBGAEAUImageAdjustments@Image@Manager@Container@@@Z; Csl::MarshalFromJson<Container::Manager::Image::ImageAdjustments>(ushort const *,Container::Manager::Image::ImageAdjustments &)
0x140016bfe  mov     esi, eax
0x140016c00  test    eax, eax
0x140016c02  jns     short loc_140016C2A
0x140016c04  mov     rcx, [rbp+98h]; this
0x140016c0b  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016c12  mov     r9d, eax; char *
0x140016c15  mov     edx, 4EEh; void *
0x140016c1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016c1f  lea     rcx, [rbp+90h+var_100]; this
0x140016c23  call    ??1ImageAdjustments@Image@Manager@Container@@QEAA@XZ; Container::Manager::Image::ImageAdjustments::~ImageAdjustments(void)
0x140016c28  jmp     short loc_140016BB2
0x140016c2a  mov     rax, qword ptr [rbp+90h+var_100]
0x140016c2e  lea     rdx, [rbp+90h+var_A0]
0x140016c32  mov     rcx, [rbp+90h+arg_0]
0x140016c39  or      r14, 0FFFFFFFFFFFFFFFFh
0x140016c3d  mov     qword ptr [rbp+90h+var_A0], rax
0x140016c41  mov     r9, r15
0x140016c44  mov     rax, qword ptr [rbp+90h+var_100+8]
0x140016c48  mov     r8, r13
0x140016c4b  mov     qword ptr [rbp+90h+var_A0+8], rax
0x140016c4f  mov     rax, qword ptr [rbp+90h+var_F0]
0x140016c53  mov     qword ptr [rbp+90h+var_90], rax
0x140016c57  mov     rax, qword ptr [rbp+90h+var_F0+8]
0x140016c5b  mov     qword ptr [rbp+90h+var_90+8], rax
0x140016c5f  mov     rax, qword ptr [rbp+90h+var_E0]
0x140016c63  mov     qword ptr [rbp+90h+var_80], rax
0x140016c67  mov     rax, qword ptr [rbp+90h+var_E0+8]
0x140016c6b  mov     qword ptr [rbp+90h+var_80+8], rax
0x140016c6f  mov     rax, qword ptr [rbp+90h+var_D0]
0x140016c73  mov     qword ptr [rbp+90h+var_70], rax
0x140016c77  mov     rax, qword ptr [rbp+90h+var_D0+8]
0x140016c7b  mov     qword ptr [rbp+90h+var_70+8], rax
0x140016c7f  mov     rax, qword ptr [rbp+90h+var_C0]
0x140016c83  mov     qword ptr [rbp+90h+var_60], rax
0x140016c87  mov     rax, qword ptr [rbp+90h+var_C0+8]
0x140016c8b  mov     qword ptr [rbp+90h+var_60+8], rax
0x140016c8f  mov     rax, qword ptr [rbp+90h+var_B0]
0x140016c93  mov     qword ptr [rbp+90h+var_50], rax
0x140016c97  mov     rax, qword ptr [rbp+90h+var_B0+8]
0x140016c9b  mov     qword ptr [rbp+90h+var_50+8], rax
0x140016c9f  movdqa  [rbp+90h+var_100], xmm6
0x140016ca4  mov     qword ptr [rbp+90h+var_F0], r14
0x140016ca8  mov     qword ptr [rbp+90h+var_F0+8], r14
0x140016cac  movdqa  [rbp+90h+var_E0], xmm6
0x140016cb1  movdqa  [rbp+90h+var_D0], xmm6
0x140016cb6  mov     qword ptr [rbp+90h+var_C0], r14
0x140016cba  mov     qword ptr [rbp+90h+var_C0+8], r14
0x140016cbe  movdqa  [rbp+90h+var_B0], xmm6
0x140016cc3  mov     byte ptr [rsp+190h+var_170], 0; int
0x140016cc8  call    ?ApplyAdjustments@Image@Manager@Container@@YAJAEBVPath@Csl@@UImageAdjustments@123@AEBV?$optional@VPath@Csl@@@utl@@2_N@Z; Container::Manager::Image::ApplyAdjustments(Csl::Path const &,Container::Manager::Image::ImageAdjustments,utl::optional<Csl::Path> const &,utl::optional<Csl::Path> const &,bool)
0x140016ccd  mov     esi, eax
0x140016ccf  test    eax, eax
0x140016cd1  jns     short loc_140016D2D
0x140016cd3  mov     rcx, [rbp+98h]; this
0x140016cda  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140016ce1  mov     r9d, eax; char *
0x140016ce4  mov     edx, 4F4h; void *
0x140016ce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016cee  lea     rcx, [rbp+90h+var_100]; this
0x140016cf2  call    ??1ImageAdjustments@Image@Manager@Container@@QEAA@XZ; Container::Manager::Image::ImageAdjustments::~ImageAdjustments(void)
0x140016cf7  mov     rcx, [rsp+190h+var_140]; void *
0x140016cfc  lea     rax, [rsp+190h+var_130]
0x140016d01  cmp     rcx, rax
0x140016d04  jz      short loc_140016D0E
0x140016d06  mov     rdx, rbx; struct std::nothrow_t *
0x140016d09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016d0e  mov     rcx, [rsp+190h+Src]; void *
0x140016d13  lea     rax, [rsp+190h+var_150]
0x140016d18  cmp     rcx, rax
0x140016d1b  jz      short loc_140016D25
0x140016d1d  mov     rdx, rbx; struct std::nothrow_t *
0x140016d20  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016d25  cmp     rdi, r14
0x140016d28  jmp     loc_140016B1D
0x140016d2d  lea     rcx, [rbp+90h+var_100]; this
0x140016d31  call    ??1ImageAdjustments@Image@Manager@Container@@QEAA@XZ; Container::Manager::Image::ImageAdjustments::~ImageAdjustments(void)
0x140016d36  mov     rcx, [rsp+190h+var_140]; void *
0x140016d3b  lea     rax, [rsp+190h+var_130]
0x140016d40  cmp     rcx, rax
0x140016d43  jz      short loc_140016D4D
0x140016d45  mov     rdx, rbx; struct std::nothrow_t *
0x140016d48  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016d4d  mov     rcx, [rsp+190h+Src]; void *
0x140016d52  lea     rax, [rsp+190h+var_150]
0x140016d57  cmp     rcx, rax
0x140016d5a  jz      short loc_140016D64
0x140016d5c  mov     rdx, rbx; struct std::nothrow_t *
0x140016d5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016d64  cmp     rdi, r14
0x140016d67  jz      short loc_140016D74
0x140016d69  mov     rdx, rbx; struct std::nothrow_t *
0x140016d6c  mov     rcx, rdi; void *
0x140016d6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016d74  xor     eax, eax
0x140016d76  lea     r11, [rsp+190h+var_30]
0x140016d7e  mov     rbx, [r11+48h]
0x140016d82  movaps  xmm6, xmmword ptr [r11-10h]
0x140016d87  mov     rsp, r11
0x140016d8a  pop     r15
0x140016d8c  pop     r14
0x140016d8e  pop     r13
0x140016d90  pop     r12
0x140016d92  pop     rdi
0x140016d93  pop     rsi
0x140016d94  pop     rbp
0x140016d95  retn
```
