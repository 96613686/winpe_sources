# PostValidation(win_dox::Uri &)

- ea: `0x180018720`
- end: `0x180018fb1`
- name: `?PostValidation@@YAXAEAVUri@win_dox@@@Z`
- size: `2193`
- prototype: `void __fastcall(struct win_dox::Uri *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800160c4`

## callees

- `0x1800175b0`
- `0x180018720`
- `0x1800190e0`
- `0x1800195ac`
- `0x18002db70`
- `0x180074024`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800cdf2c`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800187c4`
- `msvcrt!memcpy_s` at `0x180018842`
- `msvcrt!memcpy_s` at `0x1800188c9`
- `msvcrt!memcpy_s` at `0x1800187c4`
- `msvcrt!memcpy_s` at `0x180018842`
- `msvcrt!memcpy_s` at `0x1800188c9`

## string_xrefs

- `0x180018e53`: `Part uri cannot be an empty string`
- `0x180018c9b`: `Part uri cannot begin with two forward slashes`
- `0x180018edf`: `Part uri cannot be a relationship to a relationship`
- `0x180018f6d`: `Part uri cannot end with a forward slash`
- `0x180018bf4`: `Part uri cannot have a segment that ends with a dot`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PostValidation(struct win_dox::Uri *a1)
{
  void **v1; // rcx
  void **v2; // rcx
  void **v3; // rcx
  void **v4; // r9
  void **v5; // rcx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rdi
  void **v8; // rax
  void **v9; // rcx
  void **v10; // rcx
  void **v11; // rcx
  void **v12; // rcx
  void **v13; // rax
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // rsi
  void **v16; // r14
  void **v17; // rax
  void **i; // rcx
  void **v19; // rax
  __int64 v20; // rdx
  __int16 *v21; // r8
  unsigned __int64 v22; // rcx
  void **v23; // rdi
  unsigned __int64 v24; // rax
  void **v25; // rdx
  void **j; // rdx
  void **v27; // rax
  unsigned __int64 v28; // r8
  void **v29; // r10
  void **v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rbx
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // r9
  void **v35; // rax
  _WORD *v36; // r10
  unsigned __int64 v37; // rax
  _WORD *v38; // rbx
  void **v39; // rax
  void **v40; // rax
  void **v41; // rax
  void **v42; // rax
  void **v43; // rax
  _WORD *v44; // r8
  __int16 *v45; // rdx
  __int64 v46; // rcx
  void **v47; // rax
  __int64 v48; // rax
  __int16 v49; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h]
  char v52[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v54; // [rsp+78h] [rbp-88h]
  unsigned __int64 v55; // [rsp+80h] [rbp-80h]
  char v56[8]; // [rsp+88h] [rbp-78h] BYREF
  void *Destination[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v58; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v59; // [rsp+A8h] [rbp-58h]
  char v60[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v61[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v63; // [rsp+D0h] [rbp-30h]
  char v64[8]; // [rsp+D8h] [rbp-28h] BYREF
  void *Source[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v66; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v67; // [rsp+F8h] [rbp-8h]
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  v51 = -2;
  win_dox::Uri::GetPath(a1, v64);
  v59 = 7;
  v58 = 0;
  LOWORD(Destination[0]) = 0;
  std::wstring::_Copy(v56, 12, 0);
  v1 = Destination;
  if ( v59 >= 8 )
    v1 = (void **)Destination[0];
  memcpy_s(v1, 2 * v59, L"/_RELS/_RELS", 0x18u);
  v2 = Destination;
  if ( v59 >= 8 )
    v2 = (void **)Destination[0];
  v58 = 12;
  *((_WORD *)v2 + 12) = 0;
  v63 = 7;
  v62 = 0;
  LOWORD(v61[0]) = 0;
  std::wstring::_Copy(v60, 10, 0);
  v3 = v61;
  if ( v63 >= 8 )
    v3 = (void **)v61[0];
  memcpy_s(v3, 2 * v63, L".RELS.RELS", 0x14u);
  v5 = v61;
  if ( v63 >= 8 )
    v5 = (void **)v61[0];
  v62 = 10;
  *((_WORD *)v5 + 10) = 0;
  v6 = 7;
  v55 = 7;
  v54 = 0;
  LOWORD(Block[0]) = 0;
  v7 = v66;
  if ( v66 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( v66 > 7 )
  {
    std::wstring::_Copy(v52, v66, v54);
    v6 = v55;
    if ( !v7 )
      goto LABEL_20;
    goto LABEL_12;
  }
  if ( v66 )
  {
LABEL_12:
    if ( v67 < 8 )
      v8 = Source;
    else
      v8 = (void **)Source[0];
    v9 = Block;
    if ( v6 >= 8 )
      v9 = (void **)Block[0];
    memcpy_s(v9, 2 * v6, v8, 2 * v7);
    v10 = Block;
    if ( v55 >= 8 )
      v10 = (void **)Block[0];
    v54 = v7;
    *((_WORD *)v10 + v7) = 0;
    goto LABEL_19;
  }
  v54 = 0;
  LOWORD(Block[0]) = 0;
LABEL_19:
  v6 = v55;
LABEL_20:
  v11 = Block;
  if ( v6 >= 8 )
    v11 = (void **)Block[0];
  v12 = (void **)((char *)v11 + 2 * v54);
  v13 = Block;
  if ( v6 >= 8 )
    v13 = (void **)Block[0];
  while ( v13 != v12 )
  {
    v4 = (void **)*(unsigned __int16 *)v13;
    if ( (unsigned __int16)((_WORD)v4 - 97) <= 0x19u )
      LOWORD(v4) = (_WORD)v4 - 32;
    *(_WORD *)v13 = (_WORD)v4;
    v13 = (void **)((char *)v13 + 2);
  }
  v14 = v54;
  if ( !v54 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x33Bu,
      0x80510001,
      (struct win_musl::TStringEllipseBase *)L"Part uri cannot be an empty string");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v49 = 47;
  v15 = v55;
  v16 = (void **)Block[0];
  if ( v55 < 8 )
    v17 = Block;
  else
    v17 = (void **)Block[0];
  for ( i = (void **)((char *)v17 + 2 * v54 - 2); *(_WORD *)i != 47; i = (void **)((char *)i - 2) )
  {
LABEL_33:
    if ( v55 < 8 )
      v19 = Block;
    else
      v19 = (void **)Block[0];
    if ( i == v19 )
    {
      v22 = -1;
      goto LABEL_42;
    }
  }
  v20 = 1;
  v21 = &v49;
  v4 = i;
  while ( v20 )
  {
    if ( *(_WORD *)v4 != *v21 )
      goto LABEL_33;
    v4 = (void **)((char *)v4 + 2);
    ++v21;
    --v20;
  }
  if ( v55 < 8 )
    v47 = Block;
  else
    v47 = (void **)Block[0];
  v22 = ((char *)i - (char *)v47) >> 1;
LABEL_42:
  if ( v59 < 8 )
    v23 = Destination;
  else
    v23 = (void **)Destination[0];
  if ( !v58 )
  {
    v31 = v54;
    if ( v22 < v54 )
      v31 = v22;
LABEL_63:
    if ( v31 != -1 && v58 + v31 == v22 )
    {
      v48 = std::wstring::rfind(v52, v60, -1, v4);
      if ( v48 != -1 && v62 + v48 == v14 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x350u,
          0x80510001,
          (struct win_musl::TStringEllipseBase *)L"Part uri cannot be a relationship to a relationship");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    goto LABEL_64;
  }
  if ( v58 <= v54 )
  {
    v24 = v54 - v58;
    if ( v22 < v54 - v58 )
      v24 = v22;
    if ( v55 < 8 )
      v25 = Block;
    else
      v25 = (void **)Block[0];
    for ( j = (void **)((char *)v25 + 2 * v24); *(_WORD *)j != *(_WORD *)v23; j = (void **)((char *)j - 2) )
    {
LABEL_52:
      if ( v55 < 8 )
        v27 = Block;
      else
        v27 = (void **)Block[0];
      if ( j == v27 )
        goto LABEL_64;
    }
    v28 = v58;
    v4 = v23;
    v29 = j;
    while ( v28 )
    {
      if ( *(_WORD *)v29 != *(_WORD *)v4 )
        goto LABEL_52;
      v29 = (void **)((char *)v29 + 2);
      v4 = (void **)((char *)v4 + 2);
      --v28;
    }
    if ( v55 < 8 )
      v30 = Block;
    else
      v30 = (void **)Block[0];
    v31 = ((char *)j - (char *)v30) >> 1;
    goto LABEL_63;
  }
LABEL_64:
  if ( v66 >= 2 )
  {
    v42 = Source;
    if ( v67 >= 8 )
      v42 = (void **)Source[0];
    if ( *(_WORD *)v42 == 47 )
    {
      v43 = Source;
      if ( v67 >= 8 )
        v43 = (void **)Source[0];
      if ( *((_WORD *)v43 + 1) == 47 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x358u,
          0x80510001,
          (struct win_musl::TStringEllipseBase *)L"Part uri cannot begin with two forward slashes");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
  }
  v32 = 0;
LABEL_66:
  while ( v32 != -1 )
  {
    v33 = v32 + 1;
    v50 = 47;
    if ( v33 < v14 )
    {
      v34 = v14 - v33;
      if ( v14 != v33 )
      {
        if ( v15 < 8 )
          v35 = Block;
        else
          v35 = v16;
        v36 = (_WORD *)v35 + v33;
LABEL_72:
        v37 = v34;
        v38 = v36;
        while ( v37 )
        {
          if ( *v38 == 47 )
          {
            v46 = 1;
            v45 = &v50;
            v44 = v38;
            while ( v46 )
            {
              if ( *v44 != *v45 )
              {
                v34 += -1 - (v38 - v36);
                v36 = v38 + 1;
                goto LABEL_72;
              }
              ++v44;
              ++v45;
              --v46;
            }
            if ( v15 < 8 )
              v39 = Block;
            else
              v39 = v16;
            v32 = ((char *)v38 - (char *)v39) >> 1;
            if ( v32 != -1 )
            {
              if ( v14 <= v32 - 1 )
                std::_String_base::_Xran();
              v41 = Block;
              if ( v15 >= 8 )
                v41 = v16;
              if ( *((_WORD *)v41 + v32 - 1) == 46 )
              {
                win_musl::detail::ThrowBuilder<SplException::THResultException>(
                  (SplException::TSystemException *)pExceptionObject,
                  0x36Bu,
                  0x80510001,
                  (struct win_musl::TStringEllipseBase *)L"Part uri cannot have a segment that ends with a dot");
                throw (SplException::THResultException *)pExceptionObject;
              }
              goto LABEL_66;
            }
            goto LABEL_82;
          }
          ++v38;
          --v37;
        }
      }
    }
    v32 = -1;
  }
LABEL_82:
  v40 = Block;
  if ( v15 >= 8 )
    v40 = v16;
  if ( *((_WORD *)v40 + v14 - 1) == 47 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x375u,
      0x80510001,
      (struct win_musl::TStringEllipseBase *)L"Part uri cannot end with a forward slash");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v15 >= 8 )
    operator delete(v16);
  v55 = 7;
  v54 = 0;
  LOWORD(Block[0]) = 0;
  if ( v63 >= 8 )
    operator delete(v61[0]);
  v63 = 7;
  v62 = 0;
  LOWORD(v61[0]) = 0;
  if ( v59 >= 8 )
    operator delete(Destination[0]);
  v59 = 7;
  v58 = 0;
  LOWORD(Destination[0]) = 0;
  if ( v67 >= 8 )
    operator delete(Source[0]);
}

```

## disassembly

```asm
0x180018720  push    rbp
0x180018722  push    rbx
0x180018723  push    rsi
0x180018724  push    rdi
0x180018725  push    r12
0x180018727  push    r13
0x180018729  push    r14
0x18001872b  push    r15
0x18001872d  lea     rbp, [rsp-0B8h]
0x180018735  sub     rsp, 1B8h
0x18001873c  mov     [rsp+1F0h+var_198], 0FFFFFFFFFFFFFFFEh
0x180018745  mov     rax, cs:__security_cookie
0x18001874c  xor     rax, rsp
0x18001874f  mov     [rbp+0F0h+var_50], rax
0x180018756  xor     r13d, r13d
0x180018759  lea     rdx, [rbp+0F0h+var_118]
0x18001875d  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x180018762  nop
0x180018763  mov     [rbp+0F0h+var_148], 7
0x18001876b  mov     ecx, r13d
0x18001876e  mov     [rbp+0F0h+var_150], rcx
0x180018772  mov     word ptr [rbp+0F0h+Destination], r13w
0x180018777  lea     rbx, aRelsRels_0; "/_RELS/_RELS"
0x18001877e  lea     rax, [rbp+0F0h+Destination]
0x180018782  cmp     rbx, rax
0x180018785  jb      short loc_180018794
0x180018787  lea     rax, [rbp+0F0h+Destination]
0x18001878b  cmp     rax, rbx
0x18001878e  ja      loc_180018CDF
0x180018794  xor     r8d, r8d
0x180018797  mov     edi, 0Ch
0x18001879c  mov     edx, edi
0x18001879e  lea     rcx, [rbp+0F0h+var_168]
0x1800187a2  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800187a7  mov     rdx, [rbp+0F0h+var_148]
0x1800187ab  lea     rcx, [rbp+0F0h+Destination]
0x1800187af  cmp     rdx, 8
0x1800187b3  cmovnb  rcx, [rbp+0F0h+Destination]; Destination
0x1800187b8  add     rdx, rdx; DestinationSize
0x1800187bb  mov     r9d, 18h; SourceSize
0x1800187c1  mov     r8, rbx; Source
0x1800187c4  call    cs:__imp_memcpy_s
0x1800187ca  lea     rcx, [rbp+0F0h+Destination]
0x1800187ce  cmp     [rbp+0F0h+var_148], 8
0x1800187d3  cmovnb  rcx, [rbp+0F0h+Destination]
0x1800187d8  mov     [rbp+0F0h+var_150], rdi
0x1800187dc  mov     [rcx+18h], r13w
0x1800187e1  mov     [rbp+0F0h+var_120], 7
0x1800187e9  mov     rcx, r13
0x1800187ec  mov     [rbp+0F0h+var_128], rcx
0x1800187f0  mov     word ptr [rbp+0F0h+var_138], r13w
0x1800187f5  lea     rbx, aRelsRels; ".RELS.RELS"
0x1800187fc  lea     rax, [rbp+0F0h+var_138]
0x180018800  cmp     rbx, rax
0x180018803  jb      short loc_180018812
0x180018805  lea     rax, [rbp+0F0h+var_138]
0x180018809  cmp     rax, rbx
0x18001880c  ja      loc_180018D25
0x180018812  xor     r8d, r8d
0x180018815  mov     edi, 0Ah
0x18001881a  mov     edx, edi
0x18001881c  lea     rcx, [rbp+0F0h+var_140]
0x180018820  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180018825  mov     rdx, [rbp+0F0h+var_120]
0x180018829  lea     rcx, [rbp+0F0h+var_138]
0x18001882d  cmp     rdx, 8
0x180018831  cmovnb  rcx, [rbp+0F0h+var_138]; Destination
0x180018836  add     rdx, rdx; DestinationSize
0x180018839  mov     r9d, 14h; SourceSize
0x18001883f  mov     r8, rbx; Source
0x180018842  call    cs:__imp_memcpy_s
0x180018848  lea     rcx, [rbp+0F0h+var_138]
0x18001884c  cmp     [rbp+0F0h+var_120], 8
0x180018851  cmovnb  rcx, [rbp+0F0h+var_138]
0x180018856  mov     [rbp+0F0h+var_128], rdi
0x18001885a  mov     [rcx+14h], r13w
0x18001885f  mov     r8d, 7
0x180018865  mov     [rbp+0F0h+var_170], r8
0x180018869  mov     [rsp+1F0h+var_178], r13
0x18001886e  mov     word ptr [rsp+1F0h+Block], r13w
0x180018874  mov     rdi, [rbp+0F0h+var_100]
0x180018878  mov     rax, 7FFFFFFFFFFFFFFEh
0x180018882  cmp     rdi, rax
0x180018885  ja      loc_180018E45
0x18001888b  cmp     r8, rdi
0x18001888e  jb      loc_180018C38
0x180018894  test    rdi, rdi
0x180018897  jz      loc_180018D6B
0x18001889d  cmp     [rbp+0F0h+var_F8], 8
0x1800188a2  jb      loc_180018D88
0x1800188a8  mov     rax, [rbp+0F0h+Source]
0x1800188ac  lea     rcx, [rsp+1F0h+Block]
0x1800188b1  cmp     r8, 8
0x1800188b5  cmovnb  rcx, [rsp+1F0h+Block]; Destination
0x1800188bb  lea     rbx, [rdi+rdi]
0x1800188bf  lea     rdx, [r8+r8]; DestinationSize
0x1800188c3  mov     r9, rbx; SourceSize
0x1800188c6  mov     r8, rax; Source
0x1800188c9  call    cs:__imp_memcpy_s
0x1800188cf  lea     rcx, [rsp+1F0h+Block]
0x1800188d4  cmp     [rbp+0F0h+var_170], 8
0x1800188d9  cmovnb  rcx, [rsp+1F0h+Block]
0x1800188df  mov     [rsp+1F0h+var_178], rdi
0x1800188e4  mov     [rcx+rbx], r13w
0x1800188e9  mov     r8, [rbp+0F0h+var_170]
0x1800188ed  lea     rcx, [rsp+1F0h+Block]
0x1800188f2  cmp     r8, 8
0x1800188f6  cmovnb  rcx, [rsp+1F0h+Block]
0x1800188fc  mov     rax, [rsp+1F0h+var_178]
0x180018901  lea     rcx, [rcx+rax*2]
0x180018905  lea     rax, [rsp+1F0h+Block]
0x18001890a  cmovnb  rax, [rsp+1F0h+Block]
0x180018910  cmp     rax, rcx
0x180018913  jz      short loc_180018935
0x180018915  movzx   r9d, word ptr [rax]
0x180018919  lea     r8d, [r9-61h]
0x18001891d  lea     edx, [r9-20h]
0x180018921  cmp     r8w, 19h
0x180018926  cmovbe  r9w, dx
0x18001892b  mov     [rax], r9w
0x18001892f  add     rax, 2
0x180018933  jmp     short loc_180018910
0x180018935  mov     r15, [rsp+1F0h+var_178]
0x18001893a  test    r15, r15
0x18001893d  jz      loc_180018E53
0x180018943  mov     r12d, 2Fh ; '/'
0x180018949  mov     [rsp+1F0h+var_1B0], r12w
0x18001894f  mov     rsi, [rbp+0F0h+var_170]
0x180018953  mov     r14, [rsp+1F0h+Block]
0x180018958  cmp     r15, 1
0x18001895c  jb      short loc_1800189C0
0x18001895e  cmp     rsi, 8
0x180018962  jb      loc_180018DA4
0x180018968  mov     rax, r14
0x18001896b  lea     rcx, [r15-1]
0x18001896f  lea     rcx, [rax+rcx*2]
0x180018973  cmp     [rcx], r12w
0x180018977  jz      short loc_180018991
0x180018979  cmp     rsi, 8
0x18001897d  jb      loc_180018AF1
0x180018983  mov     rax, r14
0x180018986  cmp     rcx, rax
0x180018989  jz      short loc_1800189C0
0x18001898b  sub     rcx, 2
0x18001898f  jmp     short loc_180018973
0x180018991  mov     edx, 1
0x180018996  lea     r8, [rsp+1F0h+var_1B0]
0x18001899b  mov     r9, rcx
0x18001899e  xchg    ax, ax
0x1800189a0  test    rdx, rdx
0x1800189a3  jz      loc_180018E0E
0x1800189a9  movzx   eax, word ptr [r8]
0x1800189ad  cmp     [r9], ax
0x1800189b1  jnz     short loc_180018979
0x1800189b3  add     r9, 2
0x1800189b7  add     r8, 2
0x1800189bb  dec     rdx
0x1800189be  jmp     short loc_1800189A0
0x1800189c0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800189c7  mov     rbx, [rbp+0F0h+var_150]
0x1800189cb  cmp     [rbp+0F0h+var_148], 8
0x1800189d0  jb      loc_180018D91
0x1800189d6  mov     rdi, [rbp+0F0h+Destination]
0x1800189da  test    rbx, rbx
0x1800189dd  jz      loc_180018E97
0x1800189e3  cmp     rbx, r15
0x1800189e6  ja      loc_180018A70
0x1800189ec  mov     rax, r15
0x1800189ef  sub     rax, rbx
0x1800189f2  cmp     rcx, rax
0x1800189f5  cmovb   rax, rcx
0x1800189f9  cmp     rsi, 8
0x1800189fd  jb      loc_180018DAE
0x180018a03  mov     rdx, r14
0x180018a06  lea     rdx, [rdx+rax*2]
0x180018a0a  movzx   r11d, word ptr [rdi]
0x180018a0e  xchg    ax, ax
0x180018a10  cmp     [rdx], r11w
0x180018a14  jz      short loc_180018A2E
0x180018a16  cmp     rsi, 8
0x180018a1a  jb      loc_180018AE7
0x180018a20  mov     rax, r14
0x180018a23  cmp     rdx, rax
0x180018a26  jz      short loc_180018A70
0x180018a28  sub     rdx, 2
0x180018a2c  jmp     short loc_180018A10
0x180018a2e  mov     r8, rbx
0x180018a31  mov     r9, rdi
0x180018a34  mov     r10, rdx
0x180018a37  test    r8, r8
0x180018a3a  jz      short loc_180018A53
0x180018a3c  movzx   eax, word ptr [r9]
0x180018a40  cmp     [r10], ax
0x180018a44  jnz     short loc_180018A16
0x180018a46  add     r10, 2
0x180018a4a  add     r9, 2
0x180018a4e  dec     r8
0x180018a51  jmp     short loc_180018A37
0x180018a53  cmp     rsi, 8
0x180018a57  jb      loc_180018DC2
0x180018a5d  mov     rax, r14
0x180018a60  sub     rdx, rax
0x180018a63  sar     rdx, 1
0x180018a66  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180018a6a  jnz     loc_180018EA6
0x180018a70  mov     r8, [rbp+0F0h+var_100]
0x180018a74  cmp     r8, 2
0x180018a78  jnb     loc_180018C5C
0x180018a7e  mov     rbx, r13
0x180018a81  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180018a85  jz      loc_180018B18
0x180018a8b  inc     rbx
0x180018a8e  mov     [rsp+1F0h+var_1A8], r12w
0x180018a94  cmp     rbx, r15
0x180018a97  jnb     short loc_180018ADE
0x180018a99  mov     r9, r15
0x180018a9c  sub     r9, rbx
0x180018a9f  cmp     r9, 1
0x180018aa3  jb      short loc_180018ADE
0x180018aa5  cmp     rsi, 8
0x180018aa9  jb      loc_180018D9A
0x180018aaf  mov     rax, r14
0x180018ab2  lea     r10, [rax+rbx*2]
0x180018ab6  nop     word ptr [rax+rax+00000000h]
0x180018ac0  mov     rax, r9
0x180018ac3  mov     rbx, r10
0x180018ac6  test    rax, rax
0x180018ac9  jz      short loc_180018ADE
0x180018acb  cmp     [rbx], r12w
0x180018acf  jz      loc_180018F43
0x180018ad5  add     rbx, 2
0x180018ad9  dec     rax
0x180018adc  jmp     short loc_180018AC6
0x180018ade  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180018ae5  jmp     short loc_180018A81
0x180018ae7  lea     rax, [rsp+1F0h+Block]
0x180018aec  jmp     loc_180018A23
0x180018af1  lea     rax, [rsp+1F0h+Block]
0x180018af6  jmp     loc_180018986
0x180018afb  cmp     rsi, 8
0x180018aff  jb      loc_180018DB8
0x180018b05  mov     rax, r14
0x180018b08  sub     rbx, rax
0x180018b0b  sar     rbx, 1
0x180018b0e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180018b12  jnz     loc_180018BCF
0x180018b18  lea     rax, [rsp+1F0h+Block]
0x180018b1d  cmp     rsi, 8
0x180018b21  cmovnb  rax, r14
0x180018b25  cmp     [rax+r15*2-2], r12w
0x180018b2b  jz      loc_180018F6D
0x180018b31  cmp     rsi, 8
0x180018b35  jnb     short loc_180018BA4
0x180018b37  mov     [rbp+0F0h+var_170], 7
0x180018b3f  mov     [rsp+1F0h+var_178], r13
0x180018b44  mov     word ptr [rsp+1F0h+Block], r13w
0x180018b4a  cmp     [rbp+0F0h+var_120], 8
0x180018b4f  jnb     short loc_180018BAE
0x180018b51  mov     [rbp+0F0h+var_120], 7
0x180018b59  mov     [rbp+0F0h+var_128], r13
0x180018b5d  mov     word ptr [rbp+0F0h+var_138], r13w
0x180018b62  cmp     [rbp+0F0h+var_148], 8
0x180018b67  jnb     short loc_180018BB9
0x180018b69  mov     [rbp+0F0h+var_148], 7
0x180018b71  mov     [rbp+0F0h+var_150], r13
0x180018b75  mov     word ptr [rbp+0F0h+Destination], r13w
0x180018b7a  cmp     [rbp+0F0h+var_F8], 8
0x180018b7f  jnb     short loc_180018BC4
0x180018b81  mov     rcx, [rbp+0F0h+var_50]
0x180018b88  xor     rcx, rsp; StackCookie
0x180018b8b  call    __security_check_cookie
0x180018b90  add     rsp, 1B8h
0x180018b97  pop     r15
0x180018b99  pop     r14
0x180018b9b  pop     r13
0x180018b9d  pop     r12
0x180018b9f  pop     rdi
0x180018ba0  pop     rsi
0x180018ba1  pop     rbx
0x180018ba2  pop     rbp
0x180018ba3  retn
0x180018ba4  mov     rcx, r14; Block
0x180018ba7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018bac  jmp     short loc_180018B37
0x180018bae  mov     rcx, [rbp+0F0h+var_138]; Block
0x180018bb2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018bb7  jmp     short loc_180018B51
0x180018bb9  mov     rcx, [rbp+0F0h+Destination]; Block
0x180018bbd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018bc2  jmp     short loc_180018B69
0x180018bc4  mov     rcx, [rbp+0F0h+Source]; Block
0x180018bc8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018bcd  jmp     short loc_180018B81
0x180018bcf  lea     rdi, [rbx-1]
0x180018bd3  cmp     r15, rdi
0x180018bd6  jbe     loc_180018F55
0x180018bdc  lea     rax, [rsp+1F0h+Block]
0x180018be1  cmp     rsi, 8
0x180018be5  cmovnb  rax, r14
0x180018be9  cmp     word ptr [rax+rdi*2], 2Eh ; '.'
  ... truncated ...
```
