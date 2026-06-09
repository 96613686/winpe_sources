# SepSddlGetAclForString

- ea: `0x14000d768`
- end: `0x14000db1c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000d684`

## callees

- `0x140006980`
- `0x14000d590`
- `0x14000d768`
- `0x14000db24`
- `0x14000dbdc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000dae4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dae4`
- `ntoskrnl!wcschr` at `0x14000d793`
- `ntoskrnl!wcschr` at `0x14000d793`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d84a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d88f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d84a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d88f`
- `ntoskrnl!_wcsnicmp` at `0x14000d92c`
- `ntoskrnl!_wcsnicmp` at `0x14000d9a5`
- `ntoskrnl!_wcsnicmp` at `0x14000d92c`
- `ntoskrnl!_wcsnicmp` at `0x14000d9a5`

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
            if ( !_wcsnicmp(j, (&off_14000A000)[v23], *((unsigned int *)&off_14000A000 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_14000A000 + 2 * v23 + 3);
              j += *((unsigned int *)&off_14000A000 + 2 * v23 + 2);
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
0x14000d768  push    rbp
0x14000d76a  push    rbx
0x14000d76b  push    rsi
0x14000d76c  push    rdi
0x14000d76d  push    r12
0x14000d76f  push    r13
0x14000d771  push    r14
0x14000d773  push    r15
0x14000d775  mov     rbp, rsp
0x14000d778  sub     rsp, 58h
0x14000d77c  xor     r15d, r15d
0x14000d77f  mov     r14, rdx
0x14000d782  mov     [rdx], r15
0x14000d785  mov     rbx, r8
0x14000d788  mov     rsi, rcx
0x14000d78b  mov     [rbp+var_18], r15
0x14000d78f  lea     edx, [r15+3Ah]; Ch
0x14000d793  call    cs:__imp_wcschr
0x14000d79a  nop     dword ptr [rax+rax+00h]
0x14000d79f  mov     [rbx], rax
0x14000d7a2  cmp     rax, rsi
0x14000d7a5  jnz     short loc_14000D7B1
0x14000d7a7  mov     eax, 0C000000Dh
0x14000d7ac  jmp     loc_14000DB0A
0x14000d7b1  mov     r8d, r15d
0x14000d7b4  test    rax, rax
0x14000d7b7  jnz     short loc_14000D7CD
0x14000d7b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d7bd  inc     rax
0x14000d7c0  cmp     [rsi+rax*2], r15w
0x14000d7c5  jnz     short loc_14000D7BD
0x14000d7c7  lea     rax, [rsi+rax*2]
0x14000d7cb  jmp     short loc_14000D7D1
0x14000d7cd  add     rax, 0FFFFFFFFFFFFFFFEh
0x14000d7d1  mov     [rbx], rax
0x14000d7d4  mov     rcx, rsi
0x14000d7d7  mov     r9d, r15d
0x14000d7da  mov     r10d, 1
0x14000d7e0  cmp     rsi, rax
0x14000d7e3  jnb     short loc_14000D804
0x14000d7e5  movzx   edx, word ptr [rcx]
0x14000d7e8  cmp     dx, 3Bh ; ';'
0x14000d7ec  jnz     short loc_14000D7F3
0x14000d7ee  add     r8d, r10d
0x14000d7f1  jmp     short loc_14000D7FB
0x14000d7f3  cmp     dx, 20h ; ' '
0x14000d7f7  cmovnz  r9d, r10d
0x14000d7fb  add     rcx, 2
0x14000d7ff  cmp     rcx, rax
0x14000d802  jb      short loc_14000D7E5
0x14000d804  mov     eax, 0CCCCCCCDh
0x14000d809  mul     r8d
0x14000d80c  mov     r13d, edx
0x14000d80f  shr     r13d, 2
0x14000d813  lea     ecx, ds:0[r13*4]
0x14000d81b  add     ecx, r13d
0x14000d81e  cmp     r8d, ecx
0x14000d821  jnz     loc_14000DB03
0x14000d827  test    r8d, r8d
0x14000d82a  jnz     short loc_14000D835
0x14000d82c  test    r9d, r9d
0x14000d82f  jnz     loc_14000DB03
0x14000d835  mov     ebx, r15d
0x14000d838  mov     r8d, 6C416553h; Tag
0x14000d83e  mov     ecx, r10d; PoolType
0x14000d841  test    r13d, r13d
0x14000d844  jnz     short loc_14000D86A
0x14000d846  lea     edx, [r13+8]; NumberOfBytes
0x14000d84a  call    cs:__imp_ExAllocatePoolWithTag
0x14000d851  nop     dword ptr [rax+rax+00h]
0x14000d856  mov     [r14], rax
0x14000d859  test    rax, rax
0x14000d85c  jz      short loc_14000D8A6
0x14000d85e  mov     qword ptr [rax], 80002h
0x14000d865  jmp     loc_14000DB08
0x14000d86a  mov     eax, 0FFFFh
0x14000d86f  lea     r15d, ds:0[r13*2]
0x14000d877  add     r15d, r13d
0x14000d87a  shl     r15d, 4
0x14000d87e  add     r15d, 8
0x14000d882  cmp     r15d, eax
0x14000d885  cmova   r15d, eax
0x14000d889  mov     edx, r15d; NumberOfBytes
0x14000d88c  mov     r12d, r15d
0x14000d88f  call    cs:__imp_ExAllocatePoolWithTag
0x14000d896  nop     dword ptr [rax+rax+00h]
0x14000d89b  mov     [r14], rax
0x14000d89e  mov     rdi, rax
0x14000d8a1  test    rax, rax
0x14000d8a4  jnz     short loc_14000D8B0
0x14000d8a6  mov     ebx, 0C000009Ah
0x14000d8ab  jmp     loc_14000DB08
0x14000d8b0  mov     r8, r12; Size
0x14000d8b3  mov     [rbp+arg_10], 8
0x14000d8ba  xor     edx, edx; Val
0x14000d8bc  mov     rcx, rdi; void *
0x14000d8bf  call    memset
0x14000d8c4  xor     eax, eax
0x14000d8c6  mov     word ptr [rdi], 2
0x14000d8cb  mov     [rdi+2], r15w
0x14000d8d0  xor     r12d, r12d
0x14000d8d3  mov     [rdi+4], eax
0x14000d8d6  mov     r15d, 0C000000Dh
0x14000d8dc  mov     [rbp+arg_8], r12d
0x14000d8e0  cmp     r12d, r13d
0x14000d8e3  jnb     loc_14000DADB
0x14000d8e9  mov     [rbp+arg_0], 0
0x14000d8f0  mov     r12w, 20h ; ' '
0x14000d8f5  jmp     short loc_14000D8FB
0x14000d8f7  add     rsi, 2
0x14000d8fb  movzx   eax, word ptr [rsi]
0x14000d8fe  cmp     ax, r12w
0x14000d902  jz      short loc_14000D8F7
0x14000d904  cmp     ax, 28h ; '('
0x14000d908  lea     rdi, [rsi+2]
0x14000d90c  cmovnz  rdi, rsi
0x14000d910  jmp     short loc_14000D916
0x14000d912  add     rdi, 2
0x14000d916  cmp     [rdi], r12w
0x14000d91a  jz      short loc_14000D912
0x14000d91c  mov     r8d, 1; MaxCount
0x14000d922  lea     rdx, aA; "A"
0x14000d929  mov     rcx, rdi; Str1
0x14000d92c  call    cs:__imp__wcsnicmp
0x14000d933  nop     dword ptr [rax+rax+00h]
0x14000d938  test    eax, eax
0x14000d93a  jnz     loc_14000DAD3
0x14000d940  add     rdi, 4
0x14000d944  jmp     short loc_14000D94A
0x14000d946  add     rdi, 2
0x14000d94a  movzx   eax, word ptr [rdi]
0x14000d94d  cmp     ax, r12w
0x14000d951  jz      short loc_14000D946
0x14000d953  cmp     ax, 3Bh ; ';'
0x14000d957  jnz     loc_14000DAD3
0x14000d95d  add     rdi, 2
0x14000d961  cmp     [rdi], r12w
0x14000d965  jz      short loc_14000D95D
0x14000d967  lea     rcx, off_14000A000; "RC"
0x14000d96e  movzx   eax, word ptr [rdi]
0x14000d971  cmp     ax, 3Bh ; ';'
0x14000d975  jz      loc_14000DA07
0x14000d97b  cmp     ax, r12w
0x14000d97f  jnz     short loc_14000D98B
0x14000d981  add     rdi, 2
0x14000d985  cmp     [rdi], r12w
0x14000d989  jz      short loc_14000D981
0x14000d98b  xor     esi, esi
0x14000d98d  cmp     esi, 8
0x14000d990  jnb     short loc_14000D9DB
0x14000d992  mov     r12d, esi
0x14000d995  shl     r12, 4
0x14000d999  mov     r8d, [r12+rcx+8]; MaxCount
0x14000d99e  mov     rdx, [r12+rcx]; Str2
0x14000d9a2  mov     rcx, rdi; Str1
0x14000d9a5  call    cs:__imp__wcsnicmp
0x14000d9ac  nop     dword ptr [rax+rax+00h]
0x14000d9b1  lea     rcx, off_14000A000; "RC"
0x14000d9b8  test    eax, eax
0x14000d9ba  jz      short loc_14000D9C0
0x14000d9bc  inc     esi
0x14000d9be  jmp     short loc_14000D98D
0x14000d9c0  mov     eax, [rbp+arg_0]
0x14000d9c3  or      eax, [r12+rcx+0Ch]
0x14000d9c8  mov     [rbp+arg_0], eax
0x14000d9cb  mov     eax, [r12+rcx+8]
0x14000d9d0  mov     r12w, 20h ; ' '
0x14000d9d5  lea     rdi, [rdi+rax*2]
0x14000d9d9  jmp     short loc_14000D96E
0x14000d9db  lea     r8, [rbp+arg_0]
0x14000d9df  mov     [rbp+arg_18], rdi
0x14000d9e3  lea     rdx, [rbp+arg_18]
0x14000d9e7  mov     rcx, rdi
0x14000d9ea  call    SepSddlParseWideStringUlong
0x14000d9ef  cmp     [rbp+arg_18], rdi
0x14000d9f3  jz      loc_14000DAD3
0x14000d9f9  mov     rdi, [rbp+arg_18]
0x14000d9fd  mov     r12w, 20h ; ' '
0x14000da02  jmp     loc_14000D967
0x14000da07  lea     rcx, [rdi+2]
0x14000da0b  test    ebx, ebx
0x14000da0d  jnz     loc_14000DAD6
0x14000da13  lea     edx, [rbx+2]
0x14000da16  jmp     short loc_14000DA1C
0x14000da18  add     rcx, 2
0x14000da1c  movzx   eax, word ptr [rcx]
0x14000da1f  cmp     ax, r12w
0x14000da23  jz      short loc_14000DA18
0x14000da25  cmp     ax, 3Bh ; ';'
0x14000da29  cmovnz  ebx, r15d
0x14000da2d  add     rcx, 2
0x14000da31  sub     edx, 1
0x14000da34  jnz     short loc_14000DA1C
0x14000da36  test    ebx, ebx
0x14000da38  jnz     loc_14000DAD6
0x14000da3e  jmp     short loc_14000DA44
0x14000da40  add     rcx, 2; Str1
0x14000da44  cmp     [rcx], r12w
0x14000da48  jz      short loc_14000DA40
0x14000da4a  lea     r8, [rbp+arg_18]
0x14000da4e  mov     [rbp+arg_18], 0
0x14000da56  lea     rdx, [rbp+var_18]
0x14000da5a  call    SepSddlGetSidForString
0x14000da5f  mov     ebx, eax
0x14000da61  test    eax, eax
0x14000da63  jnz     short loc_14000DADB
0x14000da65  mov     rsi, [rbp+arg_18]
0x14000da69  test    rsi, rsi
0x14000da6c  jnz     short loc_14000DA79
0x14000da6e  mov     ebx, 0C0000077h
0x14000da73  jmp     short loc_14000DAD6
0x14000da75  add     rsi, 2
0x14000da79  movzx   eax, word ptr [rsi]
0x14000da7c  cmp     ax, r12w
0x14000da80  jz      short loc_14000DA75
0x14000da82  cmp     ax, 29h ; ')'
0x14000da86  jnz     short loc_14000DA6E
0x14000da88  mov     rcx, [rbp+var_18]
0x14000da8c  mov     r12d, [rbp+arg_8]
0x14000da90  test    rcx, rcx
0x14000da93  jz      short loc_14000DABD
0x14000da95  mov     [rsp+58h+Sid], rcx; Sid
0x14000da9a  lea     rdx, [rbp+arg_10]; int
0x14000da9e  mov     eax, r13d
0x14000daa1  mov     rcx, r14; int
0x14000daa4  sub     eax, r12d
0x14000daa7  mov     [rsp+58h+var_30], eax; int
0x14000daab  mov     eax, [rbp+arg_0]
0x14000daae  mov     [rsp+58h+AccessMask], eax; AccessMask
0x14000dab2  call    SepSddlAddAceToAcl
0x14000dab7  mov     ebx, eax
0x14000dab9  test    eax, eax
0x14000dabb  jnz     short loc_14000DAD6
0x14000dabd  add     rsi, 2
0x14000dac1  cmp     word ptr [rsi], 28h ; '('
0x14000dac5  jnz     short loc_14000DACB
0x14000dac7  add     rsi, 2
0x14000dacb  inc     r12d
0x14000dace  jmp     loc_14000D8DC
0x14000dad3  mov     ebx, r15d
0x14000dad6  mov     rcx, [r14]
0x14000dad9  jmp     short loc_14000DAE2
0x14000dadb  mov     rcx, [r14]; P
0x14000dade  test    ebx, ebx
0x14000dae0  jz      short loc_14000DAF9
0x14000dae2  xor     edx, edx; Tag
0x14000dae4  call    cs:__imp_ExFreePoolWithTag
0x14000daeb  nop     dword ptr [rax+rax+00h]
0x14000daf0  mov     qword ptr [r14], 0
0x14000daf7  jmp     short loc_14000DB08
0x14000daf9  movzx   eax, word ptr [rbp+arg_10]
0x14000dafd  mov     [rcx+2], ax
0x14000db01  jmp     short loc_14000DB08
0x14000db03  mov     ebx, 0C000000Dh
0x14000db08  mov     eax, ebx
0x14000db0a  add     rsp, 58h
0x14000db0e  pop     r15
0x14000db10  pop     r14
0x14000db12  pop     r13
0x14000db14  pop     r12
0x14000db16  pop     rdi
0x14000db17  pop     rsi
0x14000db18  pop     rbx
0x14000db19  pop     rbp
0x14000db1a  retn
```
