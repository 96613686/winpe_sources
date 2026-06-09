# GetAttestCert

- ea: `0x1004750f0`
- end: `0x100475429`
- name: `GetAttestCert`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100474030`

## callees

- `0x10040128c`
- `0x1004306f0`
- `0x100431464`
- `0x100473820`
- `0x1004750f0`
- `0x100475548`
- `0x1004768a4`
- `0x10047699c`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10047530d`
- `KERNEL32!GetLastError` at `0x10047530d`
- `CRYPT32!CertOpenStore` at `0x1004752ff`
- `CRYPT32!CertOpenStore` at `0x1004752ff`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004752b2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047539c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004753df`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004752b2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047539c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004753df`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HCERTSTORE __fastcall GetAttestCert(void (__fastcall **a1)(_QWORD, __int64, _QWORD), _WORD *a2)
{
  _WORD *v3; // rax
  __int64 i; // r8
  const wchar_t *v5; // rax
  __int64 v6; // r8
  void **v7; // rdx
  void *v8; // rdx
  HCERTSTORE v9; // rbx
  const wchar_t *v10; // rdx
  _BYTE *v11; // r8
  unsigned int v12; // ebx
  void *v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rbx
  char v16; // cl
  DWORD LastError; // ebx
  void *v18; // r8
  _BYTE *v19; // rdx
  void *v20; // rdx
  _BYTE v22[8]; // [rsp+38h] [rbp-69h] BYREF
  void *v23; // [rsp+40h] [rbp-61h] BYREF
  __int64 v24; // [rsp+48h] [rbp-59h]
  __int64 v25; // [rsp+50h] [rbp-51h]
  void *v26[2]; // [rsp+58h] [rbp-49h] BYREF
  __int64 v27; // [rsp+68h] [rbp-39h]
  int pvPara; // [rsp+70h] [rbp-31h] BYREF
  void *v29; // [rsp+78h] [rbp-29h]
  __int64 v30; // [rsp+80h] [rbp-21h]
  void *v31[2]; // [rsp+88h] [rbp-19h] BYREF
  __m128i si128; // [rsp+98h] [rbp-9h]
  _QWORD v33[3]; // [rsp+A8h] [rbp+7h] BYREF
  unsigned __int64 v34; // [rsp+C0h] [rbp+1Fh]

  v30 = -2;
  v33[2] = 0;
  v34 = 7;
  LOWORD(v33[0]) = 0;
  v3 = a2;
  for ( i = 0; *v3; ++v3 )
    ++i;
  std::basic_string<char16_t>::assign(v33, a2, i);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  v5 = L"/v2.0/signingCertificates";
  v6 = 0;
  do
  {
    ++v6;
    ++v5;
  }
  while ( *v5 );
  std::basic_string<char16_t>::assign(v31, L"/v2.0/signingCertificates", v6);
  v7 = v31;
  if ( si128.m128i_i64[1] >= 8uLL )
    v7 = (void **)v31[0];
  std::basic_string<char16_t>::append(v33, v7, si128.m128i_i64[0]);
  if ( si128.m128i_i64[1] >= 8uLL )
  {
    v8 = v31[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
      && (((__int64)v31[0] & 0x1F) != 0
       || (v8 = (void *)*((_QWORD *)v31[0] - 1), v8 >= v31[0])
       || (unsigned __int64)((char *)v31[0] - (char *)v8 - 8) > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v8);
  }
  v9 = 0;
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  v10 = (const wchar_t *)v33;
  if ( v34 >= 8 )
    v10 = (const wchar_t *)v33[0];
  if ( (unsigned int)GetURLContents(a1, v10, v26) )
  {
    v11 = v26[0];
    v12 = LODWORD(v26[1]) - LODWORD(v26[0]);
    v13 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    if ( (LODWORD(v26[1]) - LODWORD(v26[0])) / 3u )
    {
      _mm_lfence();
      std::vector<unsigned char>::_Reallocate_exactly(&v23, (LODWORD(v26[1]) - LODWORD(v26[0])) / 3u);
      v11 = v26[0];
      v13 = v23;
    }
    if ( v12 )
    {
      if ( *v11 == 91 )
      {
        v22[0] = 0;
        if ( v12 > 1 )
        {
          v14 = 1;
          v15 = v12 - 1;
          v16 = 0;
          do
          {
            if ( (unsigned __int8)(v11[v14] - 48) > 9u )
            {
              std::vector<unsigned char>::emplace_back<unsigned char const &>(&v23, v22);
              v16 = 0;
              v11 = v26[0];
            }
            else
            {
              v16 = v11[v14] + 10 * v16 - 48;
            }
            v22[0] = v16;
            ++v14;
            --v15;
          }
          while ( v15 );
          v13 = v23;
        }
      }
    }
    pvPara = v24 - (_DWORD)v13;
    v29 = v13;
    v9 = CertOpenStore((LPCSTR)5, 0, 0, 0, &pvPara);
    if ( !v9 )
    {
      LastError = GetLastError();
      v18 = v23;
      if ( !v23 )
      {
LABEL_36:
        (*a1)(a1, 102, LastError);
        v9 = 0;
        goto LABEL_44;
      }
      if ( (unsigned __int64)(v25 - (_QWORD)v23) < 0x1000
        || ((unsigned __int8)v23 & 0x1F) == 0
        && (v18 = (void *)*((_QWORD *)v23 - 1), v18 < v23)
        && (unsigned __int64)((_BYTE *)v23 - (_BYTE *)v18 - 8) <= 0x1F )
      {
        operator delete(v18);
        goto LABEL_36;
      }
LABEL_42:
      _invalid_parameter_noinfo_noreturn();
    }
    v19 = v23;
    if ( v23 )
    {
      if ( (unsigned __int64)(v25 - (_QWORD)v23) >= 0x1000 )
      {
        if ( ((unsigned __int8)v23 & 0x1F) != 0 )
          goto LABEL_42;
        v19 = (_BYTE *)*((_QWORD *)v23 - 1);
        if ( v19 >= v23 || (unsigned __int64)((_BYTE *)v23 - v19 - 8) > 0x1F )
          goto LABEL_42;
      }
      operator delete(v19);
    }
  }
LABEL_44:
  v20 = v26[0];
  if ( v26[0] )
  {
    if ( v27 - (unsigned __int64)v26[0] >= 0x1000 )
    {
      if ( ((__int64)v26[0] & 0x1F) != 0
        || (v20 = (void *)*((_QWORD *)v26[0] - 1), v20 >= v26[0])
        || (unsigned __int64)((char *)v26[0] - (char *)v20 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v20);
    *(_OWORD *)v26 = 0;
    v27 = 0;
  }
  std::basic_string<char16_t>::_Tidy_deallocate(v33);
  return v9;
}

```

## disassembly

```asm
0x1004750f0  mov     rax, rsp
0x1004750f3  push    rbp
0x1004750f4  push    rsi
0x1004750f5  push    rdi
0x1004750f6  push    r12
0x1004750f8  push    r14
0x1004750fa  lea     rbp, [rax-5Fh]
0x1004750fe  sub     rsp, 0D0h
0x100475105  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x10047510d  mov     [rax+18h], rbx
0x100475111  mov     rax, cs:__security_cookie
0x100475118  xor     rax, rsp
0x10047511b  mov     [rbp+57h+var_30], rax
0x10047511f  mov     rsi, rcx
0x100475122  xor     r14d, r14d
0x100475125  mov     [rbp+57h+var_40], r14
0x100475129  mov     [rbp+57h+var_38], 7
0x100475131  mov     word ptr [rbp+57h+var_50], r14w
0x100475136  mov     rax, rdx
0x100475139  mov     r8d, r14d
0x10047513c  cmp     [rdx], r14w
0x100475140  jz      short loc_10047514F
0x100475142  inc     r8
0x100475145  lea     rax, [rax+2]
0x100475149  cmp     [rax], r14w
0x10047514d  jnz     short loc_100475142
0x10047514f  lea     rcx, [rbp+57h+var_50]
0x100475153  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x100475158  nop
0x100475159  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100475161  movdqu  [rbp+57h+var_60], xmm0
0x100475166  mov     word ptr [rbp+57h+var_70], r14w
0x10047516b  lea     rdx, aV20Signingcert; "/v2.0/signingCertificates"
0x100475172  mov     rax, rdx
0x100475175  mov     r8, r14
0x100475178  inc     r8
0x10047517b  lea     rax, [rax+2]
0x10047517f  cmp     [rax], r14w
0x100475183  jnz     short loc_100475178
0x100475185  lea     rcx, [rbp+57h+var_70]
0x100475189  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x10047518e  nop
0x10047518f  lea     rdx, [rbp+57h+var_70]
0x100475193  cmp     qword ptr [rbp+57h+var_60+8], 8
0x100475198  cmovnb  rdx, [rbp+57h+var_70]
0x10047519d  mov     r8, qword ptr [rbp+57h+var_60]
0x1004751a1  lea     rcx, [rbp+57h+var_50]
0x1004751a5  call    ?append@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::append(char16_t const * const,unsigned __int64)
0x1004751aa  nop
0x1004751ab  mov     r12d, 1000h
0x1004751b1  mov     rax, qword ptr [rbp+57h+var_60+8]
0x1004751b5  cmp     rax, 8
0x1004751b9  jb      short loc_10047520F
0x1004751bb  inc     rax
0x1004751be  mov     rdx, [rbp+57h+var_70]
0x1004751c2  mov     rcx, rdx
0x1004751c5  mov     r8, 7FFFFFFFFFFFFFFFh
0x1004751cf  cmp     rax, r8
0x1004751d2  ja      loc_1004752B2
0x1004751d8  add     rax, rax
0x1004751db  cmp     rax, r12
0x1004751de  jb      short loc_100475207
0x1004751e0  test    cl, 1Fh
0x1004751e3  jnz     loc_1004752B2
0x1004751e9  mov     rdx, [rdx-8]
0x1004751ed  cmp     rdx, rcx
0x1004751f0  jnb     loc_1004752B2
0x1004751f6  sub     rcx, rdx
0x1004751f9  sub     rcx, 8
0x1004751fd  cmp     rcx, 1Fh
0x100475201  ja      loc_1004752B2
0x100475207  mov     rcx, rdx; void *
0x10047520a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x10047520f  mov     rbx, r14
0x100475212  mov     [rbp+57h+var_A0], r14
0x100475216  mov     [rbp+57h+var_A0+8], r14
0x10047521a  mov     [rbp+57h+var_90], r14
0x10047521e  lea     rdx, [rbp+57h+var_50]
0x100475222  cmp     [rbp+57h+var_38], 8
0x100475227  cmovnb  rdx, [rbp+57h+var_50]
0x10047522c  lea     r8, [rbp+57h+var_A0]
0x100475230  mov     rcx, rsi
0x100475233  call    GetURLContents
0x100475238  test    eax, eax
0x10047523a  jz      loc_1004753AC
0x100475240  mov     rbx, [rbp+57h+var_A0+8]
0x100475244  mov     r8, [rbp+57h+var_A0]
0x100475248  sub     rbx, r8
0x10047524b  mov     rcx, r14
0x10047524e  mov     [rbp+57h+var_B8], rcx
0x100475252  mov     [rbp+57h+var_B0], r14
0x100475256  mov     [rbp+57h+var_A8], r14
0x10047525a  mov     eax, 0AAAAAAABh
0x10047525f  mul     ebx
0x100475261  shr     edx, 1
0x100475263  jz      short loc_100475279
0x100475265  lfence
0x100475268  lea     rcx, [rbp+57h+var_B8]
0x10047526c  call    ?_Reallocate_exactly@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Reallocate_exactly(unsigned __int64)
0x100475271  mov     r8, [rbp+57h+var_A0]
0x100475275  mov     rcx, [rbp+57h+var_B8]
0x100475279  test    ebx, ebx
0x10047527b  jz      short loc_1004752DD
0x10047527d  cmp     byte ptr [r8], 5Bh ; '['
0x100475281  jnz     short loc_1004752DD
0x100475283  mov     [rbp+57h+var_C0], r14b
0x100475287  cmp     ebx, 1
0x10047528a  jbe     short loc_1004752DD
0x10047528c  mov     edi, 1
0x100475291  dec     ebx
0x100475293  mov     cl, r14b
0x100475296  mov     al, [rdi+r8]
0x10047529a  sub     al, 30h ; '0'
0x10047529c  cmp     al, 9
0x10047529e  ja      short loc_1004752B9
0x1004752a0  mov     al, cl
0x1004752a2  shl     al, 2
0x1004752a5  add     cl, al
0x1004752a7  add     cl, cl
0x1004752a9  sub     cl, 30h ; '0'
0x1004752ac  add     cl, [rdi+r8]
0x1004752b0  jmp     short loc_1004752CD
0x1004752b2  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004752b9  lea     rdx, [rbp+57h+var_C0]
0x1004752bd  lea     rcx, [rbp+57h+var_B8]
0x1004752c1  call    ??$emplace_back@AEBE@?$vector@EV?$allocator@E@std@@@std@@QEAA?A_TAEBE@Z
0x1004752c6  mov     cl, r14b
0x1004752c9  mov     r8, [rbp+57h+var_A0]
0x1004752cd  mov     [rbp+57h+var_C0], cl
0x1004752d0  inc     rdi
0x1004752d3  sub     rbx, 1
0x1004752d7  jnz     short loc_100475296
0x1004752d9  mov     rcx, [rbp+57h+var_B8]
0x1004752dd  mov     rax, [rbp+57h+var_B0]
0x1004752e1  sub     rax, rcx
0x1004752e4  mov     [rbp+57h+pvPara], eax
0x1004752e7  mov     [rbp+57h+var_80], rcx
0x1004752eb  lea     rax, [rbp+57h+pvPara]
0x1004752ef  mov     [rsp+20h], rax; pvPara
0x1004752f4  xor     r9d, r9d; dwFlags
0x1004752f7  xor     r8d, r8d; hCryptProv
0x1004752fa  xor     edx, edx; dwEncodingType
0x1004752fc  lea     ecx, [rdx+5]; lpszStoreProvider
0x1004752ff  call    cs:__imp_CertOpenStore
0x100475305  mov     rbx, rax
0x100475308  test    rax, rax
0x10047530b  jnz     short loc_100475369
0x10047530d  call    cs:__imp_GetLastError
0x100475313  mov     ebx, eax
0x100475315  mov     r8, [rbp+57h+var_B8]
0x100475319  test    r8, r8
0x10047531c  jz      short loc_100475350
0x10047531e  mov     rcx, [rbp+57h+var_A8]
0x100475322  sub     rcx, r8
0x100475325  mov     rdx, r8
0x100475328  cmp     rcx, r12
0x10047532b  jb      short loc_100475348
0x10047532d  test    dl, 1Fh
0x100475330  jnz     short loc_10047539C
0x100475332  mov     r8, [r8-8]
0x100475336  cmp     r8, rdx
0x100475339  jnb     short loc_10047539C
0x10047533b  sub     rdx, r8
0x10047533e  sub     rdx, 8
0x100475342  cmp     rdx, 1Fh
0x100475346  ja      short loc_10047539C
0x100475348  mov     rcx, r8; void *
0x10047534b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100475350  mov     r8d, ebx
0x100475353  mov     edx, 66h ; 'f'
0x100475358  mov     rcx, rsi
0x10047535b  mov     rax, [rsi]
0x10047535e  call    cs:__guard_dispatch_icall_fptr
0x100475364  mov     rbx, r14
0x100475367  jmp     short loc_1004753AC
0x100475369  mov     rdx, [rbp+57h+var_B8]
0x10047536d  test    rdx, rdx
0x100475370  jz      short loc_1004753AC
0x100475372  mov     rax, [rbp+57h+var_A8]
0x100475376  sub     rax, rdx
0x100475379  mov     rcx, rdx
0x10047537c  cmp     rax, r12
0x10047537f  jb      short loc_1004753A3
0x100475381  test    cl, 1Fh
0x100475384  jnz     short loc_10047539C
0x100475386  mov     rdx, [rdx-8]
0x10047538a  cmp     rdx, rcx
0x10047538d  jnb     short loc_10047539C
0x10047538f  sub     rcx, rdx
0x100475392  sub     rcx, 8
0x100475396  cmp     rcx, 1Fh
0x10047539a  jbe     short loc_1004753A3
0x10047539c  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004753a3  mov     rcx, rdx; void *
0x1004753a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1004753ab  nop
0x1004753ac  mov     rdx, [rbp+57h+var_A0]
0x1004753b0  test    rdx, rdx
0x1004753b3  jz      short loc_1004753FA
0x1004753b5  mov     rax, [rbp+57h+var_90]
0x1004753b9  sub     rax, rdx
0x1004753bc  mov     rcx, rdx
0x1004753bf  cmp     rax, r12
0x1004753c2  jb      short loc_1004753E6
0x1004753c4  test    cl, 1Fh
0x1004753c7  jnz     short loc_1004753DF
0x1004753c9  mov     rdx, [rdx-8]
0x1004753cd  cmp     rdx, rcx
0x1004753d0  jnb     short loc_1004753DF
0x1004753d2  sub     rcx, rdx
0x1004753d5  sub     rcx, 8
0x1004753d9  cmp     rcx, 1Fh
0x1004753dd  jbe     short loc_1004753E6
0x1004753df  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004753e6  mov     rcx, rdx; void *
0x1004753e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1004753ee  xorps   xmm0, xmm0
0x1004753f1  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x1004753f6  mov     [rbp+57h+var_90], r14
0x1004753fa  lea     rcx, [rbp+57h+var_50]
0x1004753fe  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x100475403  mov     rax, rbx
0x100475406  mov     rcx, [rbp+57h+var_30]
0x10047540a  xor     rcx, rsp; StackCookie
0x10047540d  call    __security_check_cookie
0x100475412  mov     rbx, [rsp+0F0h+arg_10]
0x10047541a  add     rsp, 0D0h
0x100475421  pop     r14
0x100475423  pop     r12
0x100475425  pop     rdi
0x100475426  pop     rsi
0x100475427  pop     rbp
0x100475428  retn
```
