# SepSddlGetAclForString

- ea: `0x1400431e8`
- end: `0x14004359f`
- name: `SepSddlGetAclForString`
- size: `951`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140043104`

## callees

- `0x14002cbc0`
- `0x140043010`
- `0x1400431e8`
- `0x1400435a8`
- `0x14004365c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x140043213`
- `ntoskrnl!wcschr` at `0x140043213`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400432ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004330f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400432ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004330f`
- `ntoskrnl!_wcsnicmp` at `0x1400433a6`
- `ntoskrnl!_wcsnicmp` at `0x140043416`
- `ntoskrnl!_wcsnicmp` at `0x1400433a6`
- `ntoskrnl!_wcsnicmp` at `0x140043416`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004356b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004356b`

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
  _QWORD *PoolWithTag; // rax
  unsigned int v16; // r15d
  _WORD *v17; // rax
  _WORD *v18; // rdi
  const wchar_t *v19; // rdi
  const wchar_t *j; // rdi
  wchar_t v21; // ax
  unsigned int k; // esi
  __int64 v23; // r12
  wchar_t *v24; // rcx
  int v25; // edx
  _WORD *v26; // rsi
  int v27; // edi
  _WORD *v28; // rax
  _WORD *v29; // [rsp+A0h] [rbp+48h] BYREF
  int v30; // [rsp+A8h] [rbp+50h]
  int v31; // [rsp+B0h] [rbp+58h]
  const wchar_t *v32; // [rsp+B8h] [rbp+60h] BYREF

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
  if ( !v13 )
  {
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, 8u, 0x6C416553u);
    *a2 = PoolWithTag;
    if ( PoolWithTag )
    {
      *PoolWithTag = 524290;
      return SidForString;
    }
    return (unsigned int)-1073741670;
  }
  v16 = 48 * v13 + 8;
  if ( v16 > 0xFFFF )
    v16 = 0xFFFF;
  v17 = ExAllocatePoolWithTag(PagedPool, v16, 0x6C416553u);
  *a2 = v17;
  v18 = v17;
  if ( !v17 )
    return (unsigned int)-1073741670;
  v31 = 8;
  memset(v17, 0, v16);
  *v18 = 2;
  v18[1] = v16;
  *((_DWORD *)v18 + 1) = 0;
  v30 = 0;
  do
  {
    LODWORD(v29) = 0;
    while ( *v5 == 32 )
      ++v5;
    v19 = v5 + 1;
    if ( *v5 != 40 )
      v19 = v5;
    while ( *v19 == 32 )
      ++v19;
    if ( _wcsnicmp(v19, L"A", 1u) )
      goto LABEL_69;
    for ( j = v19 + 2; *j == 32; ++j )
      ;
    if ( *j != 59 )
    {
LABEL_69:
      SidForString = -1073741811;
      goto LABEL_70;
    }
    do
      v21 = *++j;
    while ( *j == 32 );
    if ( v21 != 59 )
    {
      do
      {
        if ( v21 == 32 )
        {
          do
            ++j;
          while ( *j == 32 );
        }
        for ( k = 0; k < 8; ++k )
        {
          v23 = 2LL * k;
          if ( !_wcsnicmp(j, (&off_140031160)[v23], *((unsigned int *)&off_140031160 + 2 * v23 + 2)) )
          {
            LODWORD(v29) = *((_DWORD *)&off_140031160 + 2 * v23 + 3) | (unsigned int)v29;
            j += *((unsigned int *)&off_140031160 + 2 * v23 + 2);
            goto LABEL_48;
          }
        }
        v32 = j;
        SepSddlParseWideStringUlong(j, &v32, &v29);
        if ( v32 == j )
          goto LABEL_69;
        j = v32;
LABEL_48:
        v21 = *j;
      }
      while ( *j != 59 );
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
    v29 = 0;
    SidForString = SepSddlGetSidForString(v24);
    if ( SidForString )
      break;
    v26 = v29;
    if ( !v29 )
      goto LABEL_61;
    while ( *v26 == 32 )
      ++v26;
    if ( *v26 != 41 )
    {
LABEL_61:
      SidForString = -1073741705;
LABEL_70:
      v28 = (_WORD *)*a2;
LABEL_72:
      ExFreePoolWithTag(v28, 0);
      *a2 = 0;
      return SidForString;
    }
    v27 = v30;
    v5 = v26 + 1;
    if ( *v5 == 40 )
      ++v5;
    ++v30;
  }
  while ( v27 + 1 < v13 );
  v28 = (_WORD *)*a2;
  if ( SidForString )
    goto LABEL_72;
  v28[1] = v31;
  return SidForString;
}

```

## disassembly

```asm
0x1400431e8  push    rbp
0x1400431ea  push    rbx
0x1400431eb  push    rsi
0x1400431ec  push    rdi
0x1400431ed  push    r12
0x1400431ef  push    r13
0x1400431f1  push    r14
0x1400431f3  push    r15
0x1400431f5  mov     rbp, rsp
0x1400431f8  sub     rsp, 58h
0x1400431fc  xor     r15d, r15d
0x1400431ff  mov     r14, rdx
0x140043202  mov     [rdx], r15
0x140043205  mov     rbx, r8
0x140043208  mov     rsi, rcx
0x14004320b  mov     [rbp+var_18], r15
0x14004320f  lea     edx, [r15+3Ah]; Ch
0x140043213  call    cs:__imp_wcschr
0x14004321a  nop     dword ptr [rax+rax+00h]
0x14004321f  mov     [rbx], rax
0x140043222  cmp     rax, rsi
0x140043225  jnz     short loc_140043231
0x140043227  mov     eax, 0C000000Dh
0x14004322c  jmp     loc_14004358D
0x140043231  mov     r8d, r15d
0x140043234  test    rax, rax
0x140043237  jnz     short loc_14004324D
0x140043239  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004323d  inc     rax
0x140043240  cmp     [rsi+rax*2], r15w
0x140043245  jnz     short loc_14004323D
0x140043247  lea     rax, [rsi+rax*2]
0x14004324b  jmp     short loc_140043251
0x14004324d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140043251  mov     [rbx], rax
0x140043254  mov     rcx, rsi
0x140043257  mov     r9d, r15d
0x14004325a  mov     r10d, 1
0x140043260  cmp     rsi, rax
0x140043263  jnb     short loc_140043284
0x140043265  movzx   edx, word ptr [rcx]
0x140043268  cmp     dx, 3Bh ; ';'
0x14004326c  jnz     short loc_140043273
0x14004326e  add     r8d, r10d
0x140043271  jmp     short loc_14004327B
0x140043273  cmp     dx, 20h ; ' '
0x140043277  cmovnz  r9d, r10d
0x14004327b  add     rcx, 2
0x14004327f  cmp     rcx, rax
0x140043282  jb      short loc_140043265
0x140043284  mov     eax, 0CCCCCCCDh
0x140043289  mul     r8d
0x14004328c  mov     r13d, edx
0x14004328f  shr     r13d, 2
0x140043293  lea     ecx, ds:0[r13*4]
0x14004329b  add     ecx, r13d
0x14004329e  cmp     r8d, ecx
0x1400432a1  jnz     loc_140043586
0x1400432a7  test    r8d, r8d
0x1400432aa  jnz     short loc_1400432B5
0x1400432ac  test    r9d, r9d
0x1400432af  jnz     loc_140043586
0x1400432b5  mov     ebx, r15d
0x1400432b8  mov     r8d, 6C416553h; Tag
0x1400432be  mov     ecx, r10d; PoolType
0x1400432c1  test    r13d, r13d
0x1400432c4  jnz     short loc_1400432EA
0x1400432c6  lea     edx, [r13+8]; NumberOfBytes
0x1400432ca  call    cs:__imp_ExAllocatePoolWithTag
0x1400432d1  nop     dword ptr [rax+rax+00h]
0x1400432d6  mov     [r14], rax
0x1400432d9  test    rax, rax
0x1400432dc  jz      short loc_140043326
0x1400432de  mov     qword ptr [rax], 80002h
0x1400432e5  jmp     loc_14004358B
0x1400432ea  mov     eax, 0FFFFh
0x1400432ef  lea     r15d, ds:0[r13*2]
0x1400432f7  add     r15d, r13d
0x1400432fa  shl     r15d, 4
0x1400432fe  add     r15d, 8
0x140043302  cmp     r15d, eax
0x140043305  cmova   r15d, eax
0x140043309  mov     edx, r15d; NumberOfBytes
0x14004330c  mov     r12d, r15d
0x14004330f  call    cs:__imp_ExAllocatePoolWithTag
0x140043316  nop     dword ptr [rax+rax+00h]
0x14004331b  mov     [r14], rax
0x14004331e  mov     rdi, rax
0x140043321  test    rax, rax
0x140043324  jnz     short loc_140043330
0x140043326  mov     ebx, 0C000009Ah
0x14004332b  jmp     loc_14004358B
0x140043330  mov     r8, r12; Size
0x140043333  mov     [rbp+arg_10], 8
0x14004333a  xor     edx, edx; Val
0x14004333c  mov     rcx, rdi; void *
0x14004333f  call    memset
0x140043344  xor     eax, eax
0x140043346  mov     word ptr [rdi], 2
0x14004334b  mov     [rdi+2], r15w
0x140043350  mov     [rdi+4], eax
0x140043353  mov     [rbp+arg_8], eax
0x140043356  test    r13d, r13d
0x140043359  jz      loc_14004355A
0x14004335f  mov     r15d, 0C000000Dh
0x140043365  xor     r12d, r12d
0x140043368  mov     dword ptr [rbp+arg_0], r12d
0x14004336c  jmp     short loc_140043372
0x14004336e  add     rsi, 2
0x140043372  movzx   eax, word ptr [rsi]
0x140043375  cmp     ax, 20h ; ' '
0x140043379  jz      short loc_14004336E
0x14004337b  lea     rdi, [rsi+2]
0x14004337f  cmp     ax, 28h ; '('
0x140043383  cmovnz  rdi, rsi
0x140043387  mov     si, 20h ; ' '
0x14004338b  jmp     short loc_140043391
0x14004338d  add     rdi, 2
0x140043391  cmp     [rdi], si
0x140043394  jz      short loc_14004338D
0x140043396  mov     r8d, 1; MaxCount
0x14004339c  lea     rdx, aA; "A"
0x1400433a3  mov     rcx, rdi; Str1
0x1400433a6  call    cs:__imp__wcsnicmp
0x1400433ad  nop     dword ptr [rax+rax+00h]
0x1400433b2  test    eax, eax
0x1400433b4  jnz     loc_140043552
0x1400433ba  add     rdi, 4
0x1400433be  jmp     short loc_1400433C4
0x1400433c0  add     rdi, 2
0x1400433c4  movzx   eax, word ptr [rdi]
0x1400433c7  cmp     ax, si
0x1400433ca  jz      short loc_1400433C0
0x1400433cc  cmp     ax, 3Bh ; ';'
0x1400433d0  jnz     loc_140043552
0x1400433d6  add     rdi, 2
0x1400433da  movzx   eax, word ptr [rdi]
0x1400433dd  cmp     ax, si
0x1400433e0  jz      short loc_1400433D6
0x1400433e2  cmp     ax, 3Bh ; ';'
0x1400433e6  jz      loc_140043481
0x1400433ec  cmp     ax, si
0x1400433ef  jnz     short loc_1400433FA
0x1400433f1  add     rdi, 2
0x1400433f5  cmp     [rdi], si
0x1400433f8  jz      short loc_1400433F1
0x1400433fa  xor     esi, esi
0x1400433fc  lea     rax, off_140031160; "RC"
0x140043403  mov     r12d, esi
0x140043406  shl     r12, 4
0x14004340a  mov     rcx, rdi; Str1
0x14004340d  mov     r8d, [r12+rax+8]; MaxCount
0x140043412  mov     rdx, [r12+rax]; Str2
0x140043416  call    cs:__imp__wcsnicmp
0x14004341d  nop     dword ptr [rax+rax+00h]
0x140043422  test    eax, eax
0x140043424  jz      short loc_140043451
0x140043426  inc     esi
0x140043428  cmp     esi, 8
0x14004342b  jb      short loc_1400433FC
0x14004342d  lea     r8, [rbp+arg_0]
0x140043431  mov     [rbp+arg_18], rdi
0x140043435  lea     rdx, [rbp+arg_18]
0x140043439  mov     rcx, rdi
0x14004343c  call    SepSddlParseWideStringUlong
0x140043441  cmp     [rbp+arg_18], rdi
0x140043445  jz      loc_140043552
0x14004344b  mov     rdi, [rbp+arg_18]
0x14004344f  jmp     short loc_14004346C
0x140043451  mov     eax, dword ptr [rbp+arg_0]
0x140043454  lea     rcx, off_140031160; "RC"
0x14004345b  or      eax, [r12+rcx+0Ch]
0x140043460  mov     dword ptr [rbp+arg_0], eax
0x140043463  mov     eax, [r12+rcx+8]
0x140043468  lea     rdi, [rdi+rax*2]
0x14004346c  movzx   eax, word ptr [rdi]
0x14004346f  mov     si, 20h ; ' '
0x140043473  cmp     ax, 3Bh ; ';'
0x140043477  jnz     loc_1400433EC
0x14004347d  mov     r12d, dword ptr [rbp+arg_0]
0x140043481  lea     rcx, [rdi+2]
0x140043485  test    ebx, ebx
0x140043487  jnz     loc_140043555
0x14004348d  lea     edx, [rbx+2]
0x140043490  jmp     short loc_140043496
0x140043492  add     rcx, 2
0x140043496  movzx   eax, word ptr [rcx]
0x140043499  cmp     ax, si
0x14004349c  jz      short loc_140043492
0x14004349e  cmp     ax, 3Bh ; ';'
0x1400434a2  cmovnz  ebx, r15d
0x1400434a6  add     rcx, 2
0x1400434aa  sub     edx, 1
0x1400434ad  jnz     short loc_140043496
0x1400434af  test    ebx, ebx
0x1400434b1  jnz     loc_140043555
0x1400434b7  jmp     short loc_1400434BD
0x1400434b9  add     rcx, 2; Str1
0x1400434bd  cmp     [rcx], si
0x1400434c0  jz      short loc_1400434B9
0x1400434c2  lea     r8, [rbp+arg_0]
0x1400434c6  mov     [rbp+arg_0], 0
0x1400434ce  lea     rdx, [rbp+var_18]
0x1400434d2  call    SepSddlGetSidForString
0x1400434d7  mov     ebx, eax
0x1400434d9  test    eax, eax
0x1400434db  jnz     short loc_14004354D
0x1400434dd  mov     rsi, [rbp+arg_0]
0x1400434e1  test    rsi, rsi
0x1400434e4  jnz     short loc_1400434F1
0x1400434e6  mov     ebx, 0C0000077h
0x1400434eb  jmp     short loc_140043555
0x1400434ed  add     rsi, 2
0x1400434f1  movzx   eax, word ptr [rsi]
0x1400434f4  cmp     ax, 20h ; ' '
0x1400434f8  jz      short loc_1400434ED
0x1400434fa  cmp     ax, 29h ; ')'
0x1400434fe  jnz     short loc_1400434E6
0x140043500  mov     rcx, [rbp+var_18]
0x140043504  mov     edi, [rbp+arg_8]
0x140043507  test    rcx, rcx
0x14004350a  jz      short loc_140043531
0x14004350c  mov     [rsp+58h+Sid], rcx; Sid
0x140043511  lea     rdx, [rbp+arg_10]; int
0x140043515  mov     eax, r13d
0x140043518  mov     rcx, r14; int
0x14004351b  sub     eax, edi
0x14004351d  mov     [rsp+58h+var_30], eax; int
0x140043521  mov     [rsp+58h+AccessMask], r12d; AccessMask
0x140043526  call    SepSddlAddAceToAcl
0x14004352b  mov     ebx, eax
0x14004352d  test    eax, eax
0x14004352f  jnz     short loc_140043555
0x140043531  add     rsi, 2
0x140043535  cmp     word ptr [rsi], 28h ; '('
0x140043539  jnz     short loc_14004353F
0x14004353b  add     rsi, 2
0x14004353f  inc     edi
0x140043541  mov     [rbp+arg_8], edi
0x140043544  cmp     edi, r13d
0x140043547  jb      loc_140043365
0x14004354d  mov     ecx, [rbp+arg_10]
0x140043550  jmp     short loc_14004355F
0x140043552  mov     ebx, r15d
0x140043555  mov     rax, [r14]
0x140043558  jmp     short loc_140043566
0x14004355a  mov     ecx, 8
0x14004355f  mov     rax, [r14]
0x140043562  test    ebx, ebx
0x140043564  jz      short loc_140043580
0x140043566  xor     edx, edx; Tag
0x140043568  mov     rcx, rax; P
0x14004356b  call    cs:__imp_ExFreePoolWithTag
0x140043572  nop     dword ptr [rax+rax+00h]
0x140043577  mov     qword ptr [r14], 0
0x14004357e  jmp     short loc_14004358B
0x140043580  mov     [rax+2], cx
0x140043584  jmp     short loc_14004358B
0x140043586  mov     ebx, 0C000000Dh
0x14004358b  mov     eax, ebx
0x14004358d  add     rsp, 58h
0x140043591  pop     r15
0x140043593  pop     r14
0x140043595  pop     r13
0x140043597  pop     r12
0x140043599  pop     rdi
0x14004359a  pop     rsi
0x14004359b  pop     rbx
0x14004359c  pop     rbp
0x14004359d  retn
```
