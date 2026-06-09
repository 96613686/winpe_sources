# SepSddlGetAclForString

- ea: `0x14000f878`
- end: `0x14000fc2f`
- name: `SepSddlGetAclForString`
- size: `951`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000f794`

## callees

- `0x1400017c0`
- `0x14000f6a0`
- `0x14000f878`
- `0x14000fc38`
- `0x14000fcec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000fbfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fbfb`
- `ntoskrnl!wcschr` at `0x14000f8a3`
- `ntoskrnl!wcschr` at `0x14000f8a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f95a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f99f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f95a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f99f`
- `ntoskrnl!_wcsnicmp` at `0x14000fa36`
- `ntoskrnl!_wcsnicmp` at `0x14000faa6`
- `ntoskrnl!_wcsnicmp` at `0x14000fa36`
- `ntoskrnl!_wcsnicmp` at `0x14000faa6`

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
          if ( !_wcsnicmp(j, (&off_140011160)[v23], *((unsigned int *)&off_140011160 + 2 * v23 + 2)) )
          {
            LODWORD(v29) = *((_DWORD *)&off_140011160 + 2 * v23 + 3) | (unsigned int)v29;
            j += *((unsigned int *)&off_140011160 + 2 * v23 + 2);
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
0x14000f878  push    rbp
0x14000f87a  push    rbx
0x14000f87b  push    rsi
0x14000f87c  push    rdi
0x14000f87d  push    r12
0x14000f87f  push    r13
0x14000f881  push    r14
0x14000f883  push    r15
0x14000f885  mov     rbp, rsp
0x14000f888  sub     rsp, 58h
0x14000f88c  xor     r15d, r15d
0x14000f88f  mov     r14, rdx
0x14000f892  mov     [rdx], r15
0x14000f895  mov     rbx, r8
0x14000f898  mov     rsi, rcx
0x14000f89b  mov     [rbp+var_18], r15
0x14000f89f  lea     edx, [r15+3Ah]; Ch
0x14000f8a3  call    cs:__imp_wcschr
0x14000f8aa  nop     dword ptr [rax+rax+00h]
0x14000f8af  mov     [rbx], rax
0x14000f8b2  cmp     rax, rsi
0x14000f8b5  jnz     short loc_14000F8C1
0x14000f8b7  mov     eax, 0C000000Dh
0x14000f8bc  jmp     loc_14000FC1D
0x14000f8c1  mov     r8d, r15d
0x14000f8c4  test    rax, rax
0x14000f8c7  jnz     short loc_14000F8DD
0x14000f8c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f8cd  inc     rax
0x14000f8d0  cmp     [rsi+rax*2], r15w
0x14000f8d5  jnz     short loc_14000F8CD
0x14000f8d7  lea     rax, [rsi+rax*2]
0x14000f8db  jmp     short loc_14000F8E1
0x14000f8dd  add     rax, 0FFFFFFFFFFFFFFFEh
0x14000f8e1  mov     [rbx], rax
0x14000f8e4  mov     rcx, rsi
0x14000f8e7  mov     r9d, r15d
0x14000f8ea  mov     r10d, 1
0x14000f8f0  cmp     rsi, rax
0x14000f8f3  jnb     short loc_14000F914
0x14000f8f5  movzx   edx, word ptr [rcx]
0x14000f8f8  cmp     dx, 3Bh ; ';'
0x14000f8fc  jnz     short loc_14000F903
0x14000f8fe  add     r8d, r10d
0x14000f901  jmp     short loc_14000F90B
0x14000f903  cmp     dx, 20h ; ' '
0x14000f907  cmovnz  r9d, r10d
0x14000f90b  add     rcx, 2
0x14000f90f  cmp     rcx, rax
0x14000f912  jb      short loc_14000F8F5
0x14000f914  mov     eax, 0CCCCCCCDh
0x14000f919  mul     r8d
0x14000f91c  mov     r13d, edx
0x14000f91f  shr     r13d, 2
0x14000f923  lea     ecx, ds:0[r13*4]
0x14000f92b  add     ecx, r13d
0x14000f92e  cmp     r8d, ecx
0x14000f931  jnz     loc_14000FC16
0x14000f937  test    r8d, r8d
0x14000f93a  jnz     short loc_14000F945
0x14000f93c  test    r9d, r9d
0x14000f93f  jnz     loc_14000FC16
0x14000f945  mov     ebx, r15d
0x14000f948  mov     r8d, 6C416553h; Tag
0x14000f94e  mov     ecx, r10d; PoolType
0x14000f951  test    r13d, r13d
0x14000f954  jnz     short loc_14000F97A
0x14000f956  lea     edx, [r13+8]; NumberOfBytes
0x14000f95a  call    cs:__imp_ExAllocatePoolWithTag
0x14000f961  nop     dword ptr [rax+rax+00h]
0x14000f966  mov     [r14], rax
0x14000f969  test    rax, rax
0x14000f96c  jz      short loc_14000F9B6
0x14000f96e  mov     qword ptr [rax], 80002h
0x14000f975  jmp     loc_14000FC1B
0x14000f97a  mov     eax, 0FFFFh
0x14000f97f  lea     r15d, ds:0[r13*2]
0x14000f987  add     r15d, r13d
0x14000f98a  shl     r15d, 4
0x14000f98e  add     r15d, 8
0x14000f992  cmp     r15d, eax
0x14000f995  cmova   r15d, eax
0x14000f999  mov     edx, r15d; NumberOfBytes
0x14000f99c  mov     r12d, r15d
0x14000f99f  call    cs:__imp_ExAllocatePoolWithTag
0x14000f9a6  nop     dword ptr [rax+rax+00h]
0x14000f9ab  mov     [r14], rax
0x14000f9ae  mov     rdi, rax
0x14000f9b1  test    rax, rax
0x14000f9b4  jnz     short loc_14000F9C0
0x14000f9b6  mov     ebx, 0C000009Ah
0x14000f9bb  jmp     loc_14000FC1B
0x14000f9c0  mov     r8, r12; Size
0x14000f9c3  mov     [rbp+arg_10], 8
0x14000f9ca  xor     edx, edx; Val
0x14000f9cc  mov     rcx, rdi; void *
0x14000f9cf  call    memset
0x14000f9d4  xor     eax, eax
0x14000f9d6  mov     word ptr [rdi], 2
0x14000f9db  mov     [rdi+2], r15w
0x14000f9e0  mov     [rdi+4], eax
0x14000f9e3  mov     [rbp+arg_8], eax
0x14000f9e6  test    r13d, r13d
0x14000f9e9  jz      loc_14000FBEA
0x14000f9ef  mov     r15d, 0C000000Dh
0x14000f9f5  xor     r12d, r12d
0x14000f9f8  mov     dword ptr [rbp+arg_0], r12d
0x14000f9fc  jmp     short loc_14000FA02
0x14000f9fe  add     rsi, 2
0x14000fa02  movzx   eax, word ptr [rsi]
0x14000fa05  cmp     ax, 20h ; ' '
0x14000fa09  jz      short loc_14000F9FE
0x14000fa0b  lea     rdi, [rsi+2]
0x14000fa0f  cmp     ax, 28h ; '('
0x14000fa13  cmovnz  rdi, rsi
0x14000fa17  mov     si, 20h ; ' '
0x14000fa1b  jmp     short loc_14000FA21
0x14000fa1d  add     rdi, 2
0x14000fa21  cmp     [rdi], si
0x14000fa24  jz      short loc_14000FA1D
0x14000fa26  mov     r8d, 1; MaxCount
0x14000fa2c  lea     rdx, aA; "A"
0x14000fa33  mov     rcx, rdi; Str1
0x14000fa36  call    cs:__imp__wcsnicmp
0x14000fa3d  nop     dword ptr [rax+rax+00h]
0x14000fa42  test    eax, eax
0x14000fa44  jnz     loc_14000FBE2
0x14000fa4a  add     rdi, 4
0x14000fa4e  jmp     short loc_14000FA54
0x14000fa50  add     rdi, 2
0x14000fa54  movzx   eax, word ptr [rdi]
0x14000fa57  cmp     ax, si
0x14000fa5a  jz      short loc_14000FA50
0x14000fa5c  cmp     ax, 3Bh ; ';'
0x14000fa60  jnz     loc_14000FBE2
0x14000fa66  add     rdi, 2
0x14000fa6a  movzx   eax, word ptr [rdi]
0x14000fa6d  cmp     ax, si
0x14000fa70  jz      short loc_14000FA66
0x14000fa72  cmp     ax, 3Bh ; ';'
0x14000fa76  jz      loc_14000FB11
0x14000fa7c  cmp     ax, si
0x14000fa7f  jnz     short loc_14000FA8A
0x14000fa81  add     rdi, 2
0x14000fa85  cmp     [rdi], si
0x14000fa88  jz      short loc_14000FA81
0x14000fa8a  xor     esi, esi
0x14000fa8c  lea     rax, off_140011160; "RC"
0x14000fa93  mov     r12d, esi
0x14000fa96  shl     r12, 4
0x14000fa9a  mov     rcx, rdi; Str1
0x14000fa9d  mov     r8d, [r12+rax+8]; MaxCount
0x14000faa2  mov     rdx, [r12+rax]; Str2
0x14000faa6  call    cs:__imp__wcsnicmp
0x14000faad  nop     dword ptr [rax+rax+00h]
0x14000fab2  test    eax, eax
0x14000fab4  jz      short loc_14000FAE1
0x14000fab6  inc     esi
0x14000fab8  cmp     esi, 8
0x14000fabb  jb      short loc_14000FA8C
0x14000fabd  lea     r8, [rbp+arg_0]
0x14000fac1  mov     [rbp+arg_18], rdi
0x14000fac5  lea     rdx, [rbp+arg_18]
0x14000fac9  mov     rcx, rdi
0x14000facc  call    SepSddlParseWideStringUlong
0x14000fad1  cmp     [rbp+arg_18], rdi
0x14000fad5  jz      loc_14000FBE2
0x14000fadb  mov     rdi, [rbp+arg_18]
0x14000fadf  jmp     short loc_14000FAFC
0x14000fae1  mov     eax, dword ptr [rbp+arg_0]
0x14000fae4  lea     rcx, off_140011160; "RC"
0x14000faeb  or      eax, [r12+rcx+0Ch]
0x14000faf0  mov     dword ptr [rbp+arg_0], eax
0x14000faf3  mov     eax, [r12+rcx+8]
0x14000faf8  lea     rdi, [rdi+rax*2]
0x14000fafc  movzx   eax, word ptr [rdi]
0x14000faff  mov     si, 20h ; ' '
0x14000fb03  cmp     ax, 3Bh ; ';'
0x14000fb07  jnz     loc_14000FA7C
0x14000fb0d  mov     r12d, dword ptr [rbp+arg_0]
0x14000fb11  lea     rcx, [rdi+2]
0x14000fb15  test    ebx, ebx
0x14000fb17  jnz     loc_14000FBE5
0x14000fb1d  lea     edx, [rbx+2]
0x14000fb20  jmp     short loc_14000FB26
0x14000fb22  add     rcx, 2
0x14000fb26  movzx   eax, word ptr [rcx]
0x14000fb29  cmp     ax, si
0x14000fb2c  jz      short loc_14000FB22
0x14000fb2e  cmp     ax, 3Bh ; ';'
0x14000fb32  cmovnz  ebx, r15d
0x14000fb36  add     rcx, 2
0x14000fb3a  sub     edx, 1
0x14000fb3d  jnz     short loc_14000FB26
0x14000fb3f  test    ebx, ebx
0x14000fb41  jnz     loc_14000FBE5
0x14000fb47  jmp     short loc_14000FB4D
0x14000fb49  add     rcx, 2; Str1
0x14000fb4d  cmp     [rcx], si
0x14000fb50  jz      short loc_14000FB49
0x14000fb52  lea     r8, [rbp+arg_0]
0x14000fb56  mov     [rbp+arg_0], 0
0x14000fb5e  lea     rdx, [rbp+var_18]
0x14000fb62  call    SepSddlGetSidForString
0x14000fb67  mov     ebx, eax
0x14000fb69  test    eax, eax
0x14000fb6b  jnz     short loc_14000FBDD
0x14000fb6d  mov     rsi, [rbp+arg_0]
0x14000fb71  test    rsi, rsi
0x14000fb74  jnz     short loc_14000FB81
0x14000fb76  mov     ebx, 0C0000077h
0x14000fb7b  jmp     short loc_14000FBE5
0x14000fb7d  add     rsi, 2
0x14000fb81  movzx   eax, word ptr [rsi]
0x14000fb84  cmp     ax, 20h ; ' '
0x14000fb88  jz      short loc_14000FB7D
0x14000fb8a  cmp     ax, 29h ; ')'
0x14000fb8e  jnz     short loc_14000FB76
0x14000fb90  mov     rcx, [rbp+var_18]
0x14000fb94  mov     edi, [rbp+arg_8]
0x14000fb97  test    rcx, rcx
0x14000fb9a  jz      short loc_14000FBC1
0x14000fb9c  mov     [rsp+58h+Sid], rcx; Sid
0x14000fba1  lea     rdx, [rbp+arg_10]; int
0x14000fba5  mov     eax, r13d
0x14000fba8  mov     rcx, r14; int
0x14000fbab  sub     eax, edi
0x14000fbad  mov     [rsp+58h+var_30], eax; int
0x14000fbb1  mov     [rsp+58h+AccessMask], r12d; AccessMask
0x14000fbb6  call    SepSddlAddAceToAcl
0x14000fbbb  mov     ebx, eax
0x14000fbbd  test    eax, eax
0x14000fbbf  jnz     short loc_14000FBE5
0x14000fbc1  add     rsi, 2
0x14000fbc5  cmp     word ptr [rsi], 28h ; '('
0x14000fbc9  jnz     short loc_14000FBCF
0x14000fbcb  add     rsi, 2
0x14000fbcf  inc     edi
0x14000fbd1  mov     [rbp+arg_8], edi
0x14000fbd4  cmp     edi, r13d
0x14000fbd7  jb      loc_14000F9F5
0x14000fbdd  mov     ecx, [rbp+arg_10]
0x14000fbe0  jmp     short loc_14000FBEF
0x14000fbe2  mov     ebx, r15d
0x14000fbe5  mov     rax, [r14]
0x14000fbe8  jmp     short loc_14000FBF6
0x14000fbea  mov     ecx, 8
0x14000fbef  mov     rax, [r14]
0x14000fbf2  test    ebx, ebx
0x14000fbf4  jz      short loc_14000FC10
0x14000fbf6  xor     edx, edx; Tag
0x14000fbf8  mov     rcx, rax; P
0x14000fbfb  call    cs:__imp_ExFreePoolWithTag
0x14000fc02  nop     dword ptr [rax+rax+00h]
0x14000fc07  mov     qword ptr [r14], 0
0x14000fc0e  jmp     short loc_14000FC1B
0x14000fc10  mov     [rax+2], cx
0x14000fc14  jmp     short loc_14000FC1B
0x14000fc16  mov     ebx, 0C000000Dh
0x14000fc1b  mov     eax, ebx
0x14000fc1d  add     rsp, 58h
0x14000fc21  pop     r15
0x14000fc23  pop     r14
0x14000fc25  pop     r13
0x14000fc27  pop     r12
0x14000fc29  pop     rdi
0x14000fc2a  pop     rsi
0x14000fc2b  pop     rbx
0x14000fc2c  pop     rbp
0x14000fc2d  retn
```
