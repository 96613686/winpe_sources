# SepSddlGetAclForString

- ea: `0x140045e28`
- end: `0x1400461dc`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140045d44`

## callees

- `0x140031440`
- `0x140045c50`
- `0x140045e28`
- `0x1400461e4`
- `0x14004629c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400461a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400461a4`
- `ntoskrnl!wcschr` at `0x140045e53`
- `ntoskrnl!wcschr` at `0x140045e53`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045f0a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045f4f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045f0a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045f4f`
- `ntoskrnl!_wcsnicmp` at `0x140045fec`
- `ntoskrnl!_wcsnicmp` at `0x140046065`
- `ntoskrnl!_wcsnicmp` at `0x140045fec`
- `ntoskrnl!_wcsnicmp` at `0x140046065`

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
            if ( !_wcsnicmp(j, (&off_140038130)[v23], *((unsigned int *)&off_140038130 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_140038130 + 2 * v23 + 3);
              j += *((unsigned int *)&off_140038130 + 2 * v23 + 2);
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
0x140045e28  push    rbp
0x140045e2a  push    rbx
0x140045e2b  push    rsi
0x140045e2c  push    rdi
0x140045e2d  push    r12
0x140045e2f  push    r13
0x140045e31  push    r14
0x140045e33  push    r15
0x140045e35  mov     rbp, rsp
0x140045e38  sub     rsp, 58h
0x140045e3c  xor     r15d, r15d
0x140045e3f  mov     r14, rdx
0x140045e42  mov     [rdx], r15
0x140045e45  mov     rbx, r8
0x140045e48  mov     rsi, rcx
0x140045e4b  mov     [rbp+var_18], r15
0x140045e4f  lea     edx, [r15+3Ah]; Ch
0x140045e53  call    cs:__imp_wcschr
0x140045e5a  nop     dword ptr [rax+rax+00h]
0x140045e5f  mov     [rbx], rax
0x140045e62  cmp     rax, rsi
0x140045e65  jnz     short loc_140045E71
0x140045e67  mov     eax, 0C000000Dh
0x140045e6c  jmp     loc_1400461CA
0x140045e71  mov     r8d, r15d
0x140045e74  test    rax, rax
0x140045e77  jnz     short loc_140045E8D
0x140045e79  or      rax, 0FFFFFFFFFFFFFFFFh
0x140045e7d  inc     rax
0x140045e80  cmp     [rsi+rax*2], r15w
0x140045e85  jnz     short loc_140045E7D
0x140045e87  lea     rax, [rsi+rax*2]
0x140045e8b  jmp     short loc_140045E91
0x140045e8d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140045e91  mov     [rbx], rax
0x140045e94  mov     rcx, rsi
0x140045e97  mov     r9d, r15d
0x140045e9a  mov     r10d, 1
0x140045ea0  cmp     rsi, rax
0x140045ea3  jnb     short loc_140045EC4
0x140045ea5  movzx   edx, word ptr [rcx]
0x140045ea8  cmp     dx, 3Bh ; ';'
0x140045eac  jnz     short loc_140045EB3
0x140045eae  add     r8d, r10d
0x140045eb1  jmp     short loc_140045EBB
0x140045eb3  cmp     dx, 20h ; ' '
0x140045eb7  cmovnz  r9d, r10d
0x140045ebb  add     rcx, 2
0x140045ebf  cmp     rcx, rax
0x140045ec2  jb      short loc_140045EA5
0x140045ec4  mov     eax, 0CCCCCCCDh
0x140045ec9  mul     r8d
0x140045ecc  mov     r13d, edx
0x140045ecf  shr     r13d, 2
0x140045ed3  lea     ecx, ds:0[r13*4]
0x140045edb  add     ecx, r13d
0x140045ede  cmp     r8d, ecx
0x140045ee1  jnz     loc_1400461C3
0x140045ee7  test    r8d, r8d
0x140045eea  jnz     short loc_140045EF5
0x140045eec  test    r9d, r9d
0x140045eef  jnz     loc_1400461C3
0x140045ef5  mov     ebx, r15d
0x140045ef8  mov     r8d, 6C416553h; Tag
0x140045efe  mov     ecx, r10d; PoolType
0x140045f01  test    r13d, r13d
0x140045f04  jnz     short loc_140045F2A
0x140045f06  lea     edx, [r13+8]; NumberOfBytes
0x140045f0a  call    cs:__imp_ExAllocatePoolWithTag
0x140045f11  nop     dword ptr [rax+rax+00h]
0x140045f16  mov     [r14], rax
0x140045f19  test    rax, rax
0x140045f1c  jz      short loc_140045F66
0x140045f1e  mov     qword ptr [rax], 80002h
0x140045f25  jmp     loc_1400461C8
0x140045f2a  mov     eax, 0FFFFh
0x140045f2f  lea     r15d, ds:0[r13*2]
0x140045f37  add     r15d, r13d
0x140045f3a  shl     r15d, 4
0x140045f3e  add     r15d, 8
0x140045f42  cmp     r15d, eax
0x140045f45  cmova   r15d, eax
0x140045f49  mov     edx, r15d; NumberOfBytes
0x140045f4c  mov     r12d, r15d
0x140045f4f  call    cs:__imp_ExAllocatePoolWithTag
0x140045f56  nop     dword ptr [rax+rax+00h]
0x140045f5b  mov     [r14], rax
0x140045f5e  mov     rdi, rax
0x140045f61  test    rax, rax
0x140045f64  jnz     short loc_140045F70
0x140045f66  mov     ebx, 0C000009Ah
0x140045f6b  jmp     loc_1400461C8
0x140045f70  mov     r8, r12; Size
0x140045f73  mov     [rbp+arg_10], 8
0x140045f7a  xor     edx, edx; Val
0x140045f7c  mov     rcx, rdi; void *
0x140045f7f  call    memset
0x140045f84  xor     eax, eax
0x140045f86  mov     word ptr [rdi], 2
0x140045f8b  mov     [rdi+2], r15w
0x140045f90  xor     r12d, r12d
0x140045f93  mov     [rdi+4], eax
0x140045f96  mov     r15d, 0C000000Dh
0x140045f9c  mov     [rbp+arg_8], r12d
0x140045fa0  cmp     r12d, r13d
0x140045fa3  jnb     loc_14004619B
0x140045fa9  mov     [rbp+arg_0], 0
0x140045fb0  mov     r12w, 20h ; ' '
0x140045fb5  jmp     short loc_140045FBB
0x140045fb7  add     rsi, 2
0x140045fbb  movzx   eax, word ptr [rsi]
0x140045fbe  cmp     ax, r12w
0x140045fc2  jz      short loc_140045FB7
0x140045fc4  cmp     ax, 28h ; '('
0x140045fc8  lea     rdi, [rsi+2]
0x140045fcc  cmovnz  rdi, rsi
0x140045fd0  jmp     short loc_140045FD6
0x140045fd2  add     rdi, 2
0x140045fd6  cmp     [rdi], r12w
0x140045fda  jz      short loc_140045FD2
0x140045fdc  mov     r8d, 1; MaxCount
0x140045fe2  lea     rdx, aA; "A"
0x140045fe9  mov     rcx, rdi; Str1
0x140045fec  call    cs:__imp__wcsnicmp
0x140045ff3  nop     dword ptr [rax+rax+00h]
0x140045ff8  test    eax, eax
0x140045ffa  jnz     loc_140046193
0x140046000  add     rdi, 4
0x140046004  jmp     short loc_14004600A
0x140046006  add     rdi, 2
0x14004600a  movzx   eax, word ptr [rdi]
0x14004600d  cmp     ax, r12w
0x140046011  jz      short loc_140046006
0x140046013  cmp     ax, 3Bh ; ';'
0x140046017  jnz     loc_140046193
0x14004601d  add     rdi, 2
0x140046021  cmp     [rdi], r12w
0x140046025  jz      short loc_14004601D
0x140046027  lea     rcx, off_140038130; "RC"
0x14004602e  movzx   eax, word ptr [rdi]
0x140046031  cmp     ax, 3Bh ; ';'
0x140046035  jz      loc_1400460C7
0x14004603b  cmp     ax, r12w
0x14004603f  jnz     short loc_14004604B
0x140046041  add     rdi, 2
0x140046045  cmp     [rdi], r12w
0x140046049  jz      short loc_140046041
0x14004604b  xor     esi, esi
0x14004604d  cmp     esi, 8
0x140046050  jnb     short loc_14004609B
0x140046052  mov     r12d, esi
0x140046055  shl     r12, 4
0x140046059  mov     r8d, [r12+rcx+8]; MaxCount
0x14004605e  mov     rdx, [r12+rcx]; Str2
0x140046062  mov     rcx, rdi; Str1
0x140046065  call    cs:__imp__wcsnicmp
0x14004606c  nop     dword ptr [rax+rax+00h]
0x140046071  lea     rcx, off_140038130; "RC"
0x140046078  test    eax, eax
0x14004607a  jz      short loc_140046080
0x14004607c  inc     esi
0x14004607e  jmp     short loc_14004604D
0x140046080  mov     eax, [rbp+arg_0]
0x140046083  or      eax, [r12+rcx+0Ch]
0x140046088  mov     [rbp+arg_0], eax
0x14004608b  mov     eax, [r12+rcx+8]
0x140046090  mov     r12w, 20h ; ' '
0x140046095  lea     rdi, [rdi+rax*2]
0x140046099  jmp     short loc_14004602E
0x14004609b  lea     r8, [rbp+arg_0]
0x14004609f  mov     [rbp+arg_18], rdi
0x1400460a3  lea     rdx, [rbp+arg_18]
0x1400460a7  mov     rcx, rdi
0x1400460aa  call    SepSddlParseWideStringUlong
0x1400460af  cmp     [rbp+arg_18], rdi
0x1400460b3  jz      loc_140046193
0x1400460b9  mov     rdi, [rbp+arg_18]
0x1400460bd  mov     r12w, 20h ; ' '
0x1400460c2  jmp     loc_140046027
0x1400460c7  lea     rcx, [rdi+2]
0x1400460cb  test    ebx, ebx
0x1400460cd  jnz     loc_140046196
0x1400460d3  lea     edx, [rbx+2]
0x1400460d6  jmp     short loc_1400460DC
0x1400460d8  add     rcx, 2
0x1400460dc  movzx   eax, word ptr [rcx]
0x1400460df  cmp     ax, r12w
0x1400460e3  jz      short loc_1400460D8
0x1400460e5  cmp     ax, 3Bh ; ';'
0x1400460e9  cmovnz  ebx, r15d
0x1400460ed  add     rcx, 2
0x1400460f1  sub     edx, 1
0x1400460f4  jnz     short loc_1400460DC
0x1400460f6  test    ebx, ebx
0x1400460f8  jnz     loc_140046196
0x1400460fe  jmp     short loc_140046104
0x140046100  add     rcx, 2; Str1
0x140046104  cmp     [rcx], r12w
0x140046108  jz      short loc_140046100
0x14004610a  lea     r8, [rbp+arg_18]
0x14004610e  mov     [rbp+arg_18], 0
0x140046116  lea     rdx, [rbp+var_18]
0x14004611a  call    SepSddlGetSidForString
0x14004611f  mov     ebx, eax
0x140046121  test    eax, eax
0x140046123  jnz     short loc_14004619B
0x140046125  mov     rsi, [rbp+arg_18]
0x140046129  test    rsi, rsi
0x14004612c  jnz     short loc_140046139
0x14004612e  mov     ebx, 0C0000077h
0x140046133  jmp     short loc_140046196
0x140046135  add     rsi, 2
0x140046139  movzx   eax, word ptr [rsi]
0x14004613c  cmp     ax, r12w
0x140046140  jz      short loc_140046135
0x140046142  cmp     ax, 29h ; ')'
0x140046146  jnz     short loc_14004612E
0x140046148  mov     rcx, [rbp+var_18]
0x14004614c  mov     r12d, [rbp+arg_8]
0x140046150  test    rcx, rcx
0x140046153  jz      short loc_14004617D
0x140046155  mov     [rsp+58h+Sid], rcx; Sid
0x14004615a  lea     rdx, [rbp+arg_10]; int
0x14004615e  mov     eax, r13d
0x140046161  mov     rcx, r14; int
0x140046164  sub     eax, r12d
0x140046167  mov     [rsp+58h+var_30], eax; int
0x14004616b  mov     eax, [rbp+arg_0]
0x14004616e  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140046172  call    SepSddlAddAceToAcl
0x140046177  mov     ebx, eax
0x140046179  test    eax, eax
0x14004617b  jnz     short loc_140046196
0x14004617d  add     rsi, 2
0x140046181  cmp     word ptr [rsi], 28h ; '('
0x140046185  jnz     short loc_14004618B
0x140046187  add     rsi, 2
0x14004618b  inc     r12d
0x14004618e  jmp     loc_140045F9C
0x140046193  mov     ebx, r15d
0x140046196  mov     rcx, [r14]
0x140046199  jmp     short loc_1400461A2
0x14004619b  mov     rcx, [r14]; P
0x14004619e  test    ebx, ebx
0x1400461a0  jz      short loc_1400461B9
0x1400461a2  xor     edx, edx; Tag
0x1400461a4  call    cs:__imp_ExFreePoolWithTag
0x1400461ab  nop     dword ptr [rax+rax+00h]
0x1400461b0  mov     qword ptr [r14], 0
0x1400461b7  jmp     short loc_1400461C8
0x1400461b9  movzx   eax, word ptr [rbp+arg_10]
0x1400461bd  mov     [rcx+2], ax
0x1400461c1  jmp     short loc_1400461C8
0x1400461c3  mov     ebx, 0C000000Dh
0x1400461c8  mov     eax, ebx
0x1400461ca  add     rsp, 58h
0x1400461ce  pop     r15
0x1400461d0  pop     r14
0x1400461d2  pop     r13
0x1400461d4  pop     r12
0x1400461d6  pop     rdi
0x1400461d7  pop     rsi
0x1400461d8  pop     rbx
0x1400461d9  pop     rbp
0x1400461da  retn
```
