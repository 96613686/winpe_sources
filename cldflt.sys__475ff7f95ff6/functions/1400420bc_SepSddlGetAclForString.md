# SepSddlGetAclForString

- ea: `0x1400420bc`
- end: `0x140042470`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140041fd8`

## callees

- `0x14001e600`
- `0x140041ee4`
- `0x1400420bc`
- `0x140042478`
- `0x140042530`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x140042280`
- `ntoskrnl!_wcsnicmp` at `0x1400422f9`
- `ntoskrnl!_wcsnicmp` at `0x140042280`
- `ntoskrnl!_wcsnicmp` at `0x1400422f9`
- `ntoskrnl!wcschr` at `0x1400420e7`
- `ntoskrnl!wcschr` at `0x1400420e7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004219e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400421e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004219e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400421e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042438`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042438`

## pseudocode

```c
__int64 __fastcall SepSddlGetAclForString(wchar_t *Str1, _QWORD *a2, wchar_t **a3)
{
  wchar_t *v5; // rsi
  wchar_t *v6; // rax
  unsigned int v8; // r8d
  __int64 v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // rcx
  int i; // r9d
  unsigned int v13; // r13d
  unsigned int SidForString; // ebx
  _QWORD *v15; // rax
  unsigned int v16; // r15d
  _WORD *PoolWithTag; // rax
  _WORD *v18; // rdi
  unsigned int v19; // r12d
  const wchar_t *v20; // rdi
  const wchar_t *j; // rdi
  unsigned int k; // esi
  __int64 v23; // r12
  wchar_t *v24; // rcx
  int v25; // edx
  const wchar_t *v26; // rsi
  _WORD *v27; // rcx
  ACCESS_MASK v28; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+A8h] [rbp+50h]
  int v30; // [rsp+B0h] [rbp+58h]
  const wchar_t *v31; // [rsp+B8h] [rbp+60h] BYREF

  *a2 = 0;
  v5 = Str1;
  v6 = wcschr(Str1, 0x3Au);
  *a3 = v6;
  if ( v6 == v5 )
    return 3221225485LL;
  v8 = 0;
  if ( v6 )
  {
    v10 = v6 - 1;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v5[v9] );
    v10 = &v5[v9];
  }
  *a3 = v10;
  v11 = v5;
  for ( i = 0; v11 < v10; ++v11 )
  {
    if ( *v11 == 59 )
    {
      ++v8;
    }
    else if ( *v11 != 32 )
    {
      i = 1;
    }
  }
  v13 = v8 / 5;
  if ( v8 != 5 * (v8 / 5) || !v8 && i )
    return (unsigned int)-1073741811;
  SidForString = 0;
  if ( v13 )
  {
    v16 = 48 * v13 + 8;
    if ( v16 > 0xFFFF )
      v16 = 0xFFFF;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v16, 0x6C416553u);
    *a2 = PoolWithTag;
    v18 = PoolWithTag;
    if ( PoolWithTag )
    {
      v30 = 8;
      memset(PoolWithTag, 0, v16);
      *v18 = 2;
      v18[1] = v16;
      v19 = 0;
      *((_DWORD *)v18 + 1) = 0;
      while ( 1 )
      {
        v29 = v19;
        if ( v19 >= v13 )
          break;
        v28 = 0;
        while ( *v5 == 32 )
          ++v5;
        v20 = v5 + 1;
        if ( *v5 != 40 )
          v20 = v5;
        while ( *v20 == 32 )
          ++v20;
        if ( _wcsnicmp(v20, L"A", 1u) )
          goto LABEL_69;
        for ( j = v20 + 2; *j == 32; ++j )
          ;
        if ( *j != 59 )
        {
LABEL_69:
          SidForString = -1073741811;
LABEL_70:
          v27 = (_WORD *)*a2;
LABEL_72:
          ExFreePoolWithTag(v27, 0);
          *a2 = 0;
          return SidForString;
        }
        do
          ++j;
        while ( *j == 32 );
LABEL_40:
        while ( *j != 59 )
        {
          for ( ; *j == 32; ++j )
            ;
          for ( k = 0; k < 8; ++k )
          {
            v23 = 2LL * k;
            if ( !_wcsnicmp(j, (&off_140028240)[v23], *((unsigned int *)&off_140028240 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_140028240 + 2 * v23 + 3);
              j += *((unsigned int *)&off_140028240 + 2 * v23 + 2);
              goto LABEL_40;
            }
          }
          v31 = j;
          SepSddlParseWideStringUlong(j, &v31, &v28);
          if ( v31 == j )
            goto LABEL_69;
          j = v31;
        }
        v24 = (wchar_t *)(j + 1);
        v25 = 2;
        do
        {
          while ( *v24 == 32 )
            ++v24;
          if ( *v24 != 59 )
            SidForString = -1073741811;
          ++v24;
          --v25;
        }
        while ( v25 );
        if ( SidForString )
          goto LABEL_70;
        while ( *v24 == 32 )
          ++v24;
        v31 = 0;
        SidForString = SepSddlGetSidForString(v24);
        if ( SidForString )
          break;
        v26 = v31;
        if ( !v31 )
          goto LABEL_62;
        while ( *v26 == 32 )
          ++v26;
        if ( *v26 != 41 )
        {
LABEL_62:
          SidForString = -1073741705;
          goto LABEL_70;
        }
        v5 = (wchar_t *)(v26 + 1);
        if ( *v5 == 40 )
          ++v5;
        v19 = v29 + 1;
      }
      v27 = (_WORD *)*a2;
      if ( SidForString )
        goto LABEL_72;
      v27[1] = v30;
      return SidForString;
    }
    return (unsigned int)-1073741670;
  }
  v15 = ExAllocatePoolWithTag(PagedPool, 8u, 0x6C416553u);
  *a2 = v15;
  if ( !v15 )
    return (unsigned int)-1073741670;
  *v15 = 524290;
  return SidForString;
}

```

## disassembly

```asm
0x1400420bc  push    rbp
0x1400420be  push    rbx
0x1400420bf  push    rsi
0x1400420c0  push    rdi
0x1400420c1  push    r12
0x1400420c3  push    r13
0x1400420c5  push    r14
0x1400420c7  push    r15
0x1400420c9  mov     rbp, rsp
0x1400420cc  sub     rsp, 58h
0x1400420d0  xor     r15d, r15d
0x1400420d3  mov     r14, rdx
0x1400420d6  mov     [rdx], r15
0x1400420d9  mov     rbx, r8
0x1400420dc  mov     rsi, rcx
0x1400420df  mov     [rbp+var_18], r15
0x1400420e3  lea     edx, [r15+3Ah]; Ch
0x1400420e7  call    cs:__imp_wcschr
0x1400420ee  nop     dword ptr [rax+rax+00h]
0x1400420f3  mov     [rbx], rax
0x1400420f6  cmp     rax, rsi
0x1400420f9  jnz     short loc_140042105
0x1400420fb  mov     eax, 0C000000Dh
0x140042100  jmp     loc_14004245E
0x140042105  mov     r8d, r15d
0x140042108  test    rax, rax
0x14004210b  jnz     short loc_140042121
0x14004210d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140042111  inc     rax
0x140042114  cmp     [rsi+rax*2], r15w
0x140042119  jnz     short loc_140042111
0x14004211b  lea     rax, [rsi+rax*2]
0x14004211f  jmp     short loc_140042125
0x140042121  add     rax, 0FFFFFFFFFFFFFFFEh
0x140042125  mov     [rbx], rax
0x140042128  mov     rcx, rsi
0x14004212b  mov     r9d, r15d
0x14004212e  mov     r10d, 1
0x140042134  cmp     rsi, rax
0x140042137  jnb     short loc_140042158
0x140042139  movzx   edx, word ptr [rcx]
0x14004213c  cmp     dx, 3Bh ; ';'
0x140042140  jnz     short loc_140042147
0x140042142  add     r8d, r10d
0x140042145  jmp     short loc_14004214F
0x140042147  cmp     dx, 20h ; ' '
0x14004214b  cmovnz  r9d, r10d
0x14004214f  add     rcx, 2
0x140042153  cmp     rcx, rax
0x140042156  jb      short loc_140042139
0x140042158  mov     eax, 0CCCCCCCDh
0x14004215d  mul     r8d
0x140042160  mov     r13d, edx
0x140042163  shr     r13d, 2
0x140042167  lea     ecx, ds:0[r13*4]
0x14004216f  add     ecx, r13d
0x140042172  cmp     r8d, ecx
0x140042175  jnz     loc_140042457
0x14004217b  test    r8d, r8d
0x14004217e  jnz     short loc_140042189
0x140042180  test    r9d, r9d
0x140042183  jnz     loc_140042457
0x140042189  mov     ebx, r15d
0x14004218c  mov     r8d, 6C416553h; Tag
0x140042192  mov     ecx, r10d; PoolType
0x140042195  test    r13d, r13d
0x140042198  jnz     short loc_1400421BE
0x14004219a  lea     edx, [r13+8]; NumberOfBytes
0x14004219e  call    cs:__imp_ExAllocatePoolWithTag
0x1400421a5  nop     dword ptr [rax+rax+00h]
0x1400421aa  mov     [r14], rax
0x1400421ad  test    rax, rax
0x1400421b0  jz      short loc_1400421FA
0x1400421b2  mov     qword ptr [rax], 80002h
0x1400421b9  jmp     loc_14004245C
0x1400421be  mov     eax, 0FFFFh
0x1400421c3  lea     r15d, ds:0[r13*2]
0x1400421cb  add     r15d, r13d
0x1400421ce  shl     r15d, 4
0x1400421d2  add     r15d, 8
0x1400421d6  cmp     r15d, eax
0x1400421d9  cmova   r15d, eax
0x1400421dd  mov     edx, r15d; NumberOfBytes
0x1400421e0  mov     r12d, r15d
0x1400421e3  call    cs:__imp_ExAllocatePoolWithTag
0x1400421ea  nop     dword ptr [rax+rax+00h]
0x1400421ef  mov     [r14], rax
0x1400421f2  mov     rdi, rax
0x1400421f5  test    rax, rax
0x1400421f8  jnz     short loc_140042204
0x1400421fa  mov     ebx, 0C000009Ah
0x1400421ff  jmp     loc_14004245C
0x140042204  mov     r8, r12; Size
0x140042207  mov     [rbp+arg_10], 8
0x14004220e  xor     edx, edx; Val
0x140042210  mov     rcx, rdi; void *
0x140042213  call    memset
0x140042218  xor     eax, eax
0x14004221a  mov     word ptr [rdi], 2
0x14004221f  mov     [rdi+2], r15w
0x140042224  xor     r12d, r12d
0x140042227  mov     [rdi+4], eax
0x14004222a  mov     r15d, 0C000000Dh
0x140042230  mov     [rbp+arg_8], r12d
0x140042234  cmp     r12d, r13d
0x140042237  jnb     loc_14004242F
0x14004223d  mov     [rbp+arg_0], 0
0x140042244  mov     r12w, 20h ; ' '
0x140042249  jmp     short loc_14004224F
0x14004224b  add     rsi, 2
0x14004224f  movzx   eax, word ptr [rsi]
0x140042252  cmp     ax, r12w
0x140042256  jz      short loc_14004224B
0x140042258  cmp     ax, 28h ; '('
0x14004225c  lea     rdi, [rsi+2]
0x140042260  cmovnz  rdi, rsi
0x140042264  jmp     short loc_14004226A
0x140042266  add     rdi, 2
0x14004226a  cmp     [rdi], r12w
0x14004226e  jz      short loc_140042266
0x140042270  mov     r8d, 1; MaxCount
0x140042276  lea     rdx, aA; "A"
0x14004227d  mov     rcx, rdi; Str1
0x140042280  call    cs:__imp__wcsnicmp
0x140042287  nop     dword ptr [rax+rax+00h]
0x14004228c  test    eax, eax
0x14004228e  jnz     loc_140042427
0x140042294  add     rdi, 4
0x140042298  jmp     short loc_14004229E
0x14004229a  add     rdi, 2
0x14004229e  movzx   eax, word ptr [rdi]
0x1400422a1  cmp     ax, r12w
0x1400422a5  jz      short loc_14004229A
0x1400422a7  cmp     ax, 3Bh ; ';'
0x1400422ab  jnz     loc_140042427
0x1400422b1  add     rdi, 2
0x1400422b5  cmp     [rdi], r12w
0x1400422b9  jz      short loc_1400422B1
0x1400422bb  lea     rcx, off_140028240; "RC"
0x1400422c2  movzx   eax, word ptr [rdi]
0x1400422c5  cmp     ax, 3Bh ; ';'
0x1400422c9  jz      loc_14004235B
0x1400422cf  cmp     ax, r12w
0x1400422d3  jnz     short loc_1400422DF
0x1400422d5  add     rdi, 2
0x1400422d9  cmp     [rdi], r12w
0x1400422dd  jz      short loc_1400422D5
0x1400422df  xor     esi, esi
0x1400422e1  cmp     esi, 8
0x1400422e4  jnb     short loc_14004232F
0x1400422e6  mov     r12d, esi
0x1400422e9  shl     r12, 4
0x1400422ed  mov     r8d, [r12+rcx+8]; MaxCount
0x1400422f2  mov     rdx, [r12+rcx]; Str2
0x1400422f6  mov     rcx, rdi; Str1
0x1400422f9  call    cs:__imp__wcsnicmp
0x140042300  nop     dword ptr [rax+rax+00h]
0x140042305  lea     rcx, off_140028240; "RC"
0x14004230c  test    eax, eax
0x14004230e  jz      short loc_140042314
0x140042310  inc     esi
0x140042312  jmp     short loc_1400422E1
0x140042314  mov     eax, [rbp+arg_0]
0x140042317  or      eax, [r12+rcx+0Ch]
0x14004231c  mov     [rbp+arg_0], eax
0x14004231f  mov     eax, [r12+rcx+8]
0x140042324  mov     r12w, 20h ; ' '
0x140042329  lea     rdi, [rdi+rax*2]
0x14004232d  jmp     short loc_1400422C2
0x14004232f  lea     r8, [rbp+arg_0]
0x140042333  mov     [rbp+arg_18], rdi
0x140042337  lea     rdx, [rbp+arg_18]
0x14004233b  mov     rcx, rdi
0x14004233e  call    SepSddlParseWideStringUlong
0x140042343  cmp     [rbp+arg_18], rdi
0x140042347  jz      loc_140042427
0x14004234d  mov     rdi, [rbp+arg_18]
0x140042351  mov     r12w, 20h ; ' '
0x140042356  jmp     loc_1400422BB
0x14004235b  lea     rcx, [rdi+2]
0x14004235f  test    ebx, ebx
0x140042361  jnz     loc_14004242A
0x140042367  lea     edx, [rbx+2]
0x14004236a  jmp     short loc_140042370
0x14004236c  add     rcx, 2
0x140042370  movzx   eax, word ptr [rcx]
0x140042373  cmp     ax, r12w
0x140042377  jz      short loc_14004236C
0x140042379  cmp     ax, 3Bh ; ';'
0x14004237d  cmovnz  ebx, r15d
0x140042381  add     rcx, 2
0x140042385  sub     edx, 1
0x140042388  jnz     short loc_140042370
0x14004238a  test    ebx, ebx
0x14004238c  jnz     loc_14004242A
0x140042392  jmp     short loc_140042398
0x140042394  add     rcx, 2; Str1
0x140042398  cmp     [rcx], r12w
0x14004239c  jz      short loc_140042394
0x14004239e  lea     r8, [rbp+arg_18]
0x1400423a2  mov     [rbp+arg_18], 0
0x1400423aa  lea     rdx, [rbp+var_18]
0x1400423ae  call    SepSddlGetSidForString
0x1400423b3  mov     ebx, eax
0x1400423b5  test    eax, eax
0x1400423b7  jnz     short loc_14004242F
0x1400423b9  mov     rsi, [rbp+arg_18]
0x1400423bd  test    rsi, rsi
0x1400423c0  jnz     short loc_1400423CD
0x1400423c2  mov     ebx, 0C0000077h
0x1400423c7  jmp     short loc_14004242A
0x1400423c9  add     rsi, 2
0x1400423cd  movzx   eax, word ptr [rsi]
0x1400423d0  cmp     ax, r12w
0x1400423d4  jz      short loc_1400423C9
0x1400423d6  cmp     ax, 29h ; ')'
0x1400423da  jnz     short loc_1400423C2
0x1400423dc  mov     rcx, [rbp+var_18]
0x1400423e0  mov     r12d, [rbp+arg_8]
0x1400423e4  test    rcx, rcx
0x1400423e7  jz      short loc_140042411
0x1400423e9  mov     [rsp+58h+Sid], rcx; Sid
0x1400423ee  lea     rdx, [rbp+arg_10]; int
0x1400423f2  mov     eax, r13d
0x1400423f5  mov     rcx, r14; int
0x1400423f8  sub     eax, r12d
0x1400423fb  mov     [rsp+58h+var_30], eax; int
0x1400423ff  mov     eax, [rbp+arg_0]
0x140042402  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140042406  call    SepSddlAddAceToAcl
0x14004240b  mov     ebx, eax
0x14004240d  test    eax, eax
0x14004240f  jnz     short loc_14004242A
0x140042411  add     rsi, 2
0x140042415  cmp     word ptr [rsi], 28h ; '('
0x140042419  jnz     short loc_14004241F
0x14004241b  add     rsi, 2
0x14004241f  inc     r12d
0x140042422  jmp     loc_140042230
0x140042427  mov     ebx, r15d
0x14004242a  mov     rcx, [r14]
0x14004242d  jmp     short loc_140042436
0x14004242f  mov     rcx, [r14]; P
0x140042432  test    ebx, ebx
0x140042434  jz      short loc_14004244D
0x140042436  xor     edx, edx; Tag
0x140042438  call    cs:__imp_ExFreePoolWithTag
0x14004243f  nop     dword ptr [rax+rax+00h]
0x140042444  mov     qword ptr [r14], 0
0x14004244b  jmp     short loc_14004245C
0x14004244d  movzx   eax, word ptr [rbp+arg_10]
0x140042451  mov     [rcx+2], ax
0x140042455  jmp     short loc_14004245C
0x140042457  mov     ebx, 0C000000Dh
0x14004245c  mov     eax, ebx
0x14004245e  add     rsp, 58h
0x140042462  pop     r15
0x140042464  pop     r14
0x140042466  pop     r13
0x140042468  pop     r12
0x14004246a  pop     rdi
0x14004246b  pop     rsi
0x14004246c  pop     rbx
0x14004246d  pop     rbp
0x14004246e  retn
```
