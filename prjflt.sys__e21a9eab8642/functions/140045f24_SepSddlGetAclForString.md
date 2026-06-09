# SepSddlGetAclForString

- ea: `0x140045f24`
- end: `0x1400462db`
- name: `SepSddlGetAclForString`
- size: `951`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140045e40`

## callees

- `0x14000be80`
- `0x140045d4c`
- `0x140045f24`
- `0x1400462e4`
- `0x140046398`

## import_xrefs

- `ntoskrnl!wcschr` at `0x140045f4f`
- `ntoskrnl!wcschr` at `0x140045f4f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046006`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004604b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046006`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004604b`
- `ntoskrnl!_wcsnicmp` at `0x1400460e2`
- `ntoskrnl!_wcsnicmp` at `0x140046152`
- `ntoskrnl!_wcsnicmp` at `0x1400460e2`
- `ntoskrnl!_wcsnicmp` at `0x140046152`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400462a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400462a7`

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
          if ( !_wcsnicmp(j, (&off_14001A0A0)[v23], *((unsigned int *)&off_14001A0A0 + 2 * v23 + 2)) )
          {
            LODWORD(v29) = *((_DWORD *)&off_14001A0A0 + 2 * v23 + 3) | (unsigned int)v29;
            j += *((unsigned int *)&off_14001A0A0 + 2 * v23 + 2);
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
0x140045f24  push    rbp
0x140045f26  push    rbx
0x140045f27  push    rsi
0x140045f28  push    rdi
0x140045f29  push    r12
0x140045f2b  push    r13
0x140045f2d  push    r14
0x140045f2f  push    r15
0x140045f31  mov     rbp, rsp
0x140045f34  sub     rsp, 58h
0x140045f38  xor     r15d, r15d
0x140045f3b  mov     r14, rdx
0x140045f3e  mov     [rdx], r15
0x140045f41  mov     rbx, r8
0x140045f44  mov     rsi, rcx
0x140045f47  mov     [rbp+var_18], r15
0x140045f4b  lea     edx, [r15+3Ah]; Ch
0x140045f4f  call    cs:__imp_wcschr
0x140045f56  nop     dword ptr [rax+rax+00h]
0x140045f5b  mov     [rbx], rax
0x140045f5e  cmp     rax, rsi
0x140045f61  jnz     short loc_140045F6D
0x140045f63  mov     eax, 0C000000Dh
0x140045f68  jmp     loc_1400462C9
0x140045f6d  mov     r8d, r15d
0x140045f70  test    rax, rax
0x140045f73  jnz     short loc_140045F89
0x140045f75  or      rax, 0FFFFFFFFFFFFFFFFh
0x140045f79  inc     rax
0x140045f7c  cmp     [rsi+rax*2], r15w
0x140045f81  jnz     short loc_140045F79
0x140045f83  lea     rax, [rsi+rax*2]
0x140045f87  jmp     short loc_140045F8D
0x140045f89  add     rax, 0FFFFFFFFFFFFFFFEh
0x140045f8d  mov     [rbx], rax
0x140045f90  mov     rcx, rsi
0x140045f93  mov     r9d, r15d
0x140045f96  mov     r10d, 1
0x140045f9c  cmp     rsi, rax
0x140045f9f  jnb     short loc_140045FC0
0x140045fa1  movzx   edx, word ptr [rcx]
0x140045fa4  cmp     dx, 3Bh ; ';'
0x140045fa8  jnz     short loc_140045FAF
0x140045faa  add     r8d, r10d
0x140045fad  jmp     short loc_140045FB7
0x140045faf  cmp     dx, 20h ; ' '
0x140045fb3  cmovnz  r9d, r10d
0x140045fb7  add     rcx, 2
0x140045fbb  cmp     rcx, rax
0x140045fbe  jb      short loc_140045FA1
0x140045fc0  mov     eax, 0CCCCCCCDh
0x140045fc5  mul     r8d
0x140045fc8  mov     r13d, edx
0x140045fcb  shr     r13d, 2
0x140045fcf  lea     ecx, ds:0[r13*4]
0x140045fd7  add     ecx, r13d
0x140045fda  cmp     r8d, ecx
0x140045fdd  jnz     loc_1400462C2
0x140045fe3  test    r8d, r8d
0x140045fe6  jnz     short loc_140045FF1
0x140045fe8  test    r9d, r9d
0x140045feb  jnz     loc_1400462C2
0x140045ff1  mov     ebx, r15d
0x140045ff4  mov     r8d, 6C416553h; Tag
0x140045ffa  mov     ecx, r10d; PoolType
0x140045ffd  test    r13d, r13d
0x140046000  jnz     short loc_140046026
0x140046002  lea     edx, [r13+8]; NumberOfBytes
0x140046006  call    cs:__imp_ExAllocatePoolWithTag
0x14004600d  nop     dword ptr [rax+rax+00h]
0x140046012  mov     [r14], rax
0x140046015  test    rax, rax
0x140046018  jz      short loc_140046062
0x14004601a  mov     qword ptr [rax], 80002h
0x140046021  jmp     loc_1400462C7
0x140046026  mov     eax, 0FFFFh
0x14004602b  lea     r15d, ds:0[r13*2]
0x140046033  add     r15d, r13d
0x140046036  shl     r15d, 4
0x14004603a  add     r15d, 8
0x14004603e  cmp     r15d, eax
0x140046041  cmova   r15d, eax
0x140046045  mov     edx, r15d; NumberOfBytes
0x140046048  mov     r12d, r15d
0x14004604b  call    cs:__imp_ExAllocatePoolWithTag
0x140046052  nop     dword ptr [rax+rax+00h]
0x140046057  mov     [r14], rax
0x14004605a  mov     rdi, rax
0x14004605d  test    rax, rax
0x140046060  jnz     short loc_14004606C
0x140046062  mov     ebx, 0C000009Ah
0x140046067  jmp     loc_1400462C7
0x14004606c  mov     r8, r12; Size
0x14004606f  mov     [rbp+arg_10], 8
0x140046076  xor     edx, edx; Val
0x140046078  mov     rcx, rdi; void *
0x14004607b  call    memset
0x140046080  xor     eax, eax
0x140046082  mov     word ptr [rdi], 2
0x140046087  mov     [rdi+2], r15w
0x14004608c  mov     [rdi+4], eax
0x14004608f  mov     [rbp+arg_8], eax
0x140046092  test    r13d, r13d
0x140046095  jz      loc_140046296
0x14004609b  mov     r15d, 0C000000Dh
0x1400460a1  xor     r12d, r12d
0x1400460a4  mov     dword ptr [rbp+arg_0], r12d
0x1400460a8  jmp     short loc_1400460AE
0x1400460aa  add     rsi, 2
0x1400460ae  movzx   eax, word ptr [rsi]
0x1400460b1  cmp     ax, 20h ; ' '
0x1400460b5  jz      short loc_1400460AA
0x1400460b7  lea     rdi, [rsi+2]
0x1400460bb  cmp     ax, 28h ; '('
0x1400460bf  cmovnz  rdi, rsi
0x1400460c3  mov     si, 20h ; ' '
0x1400460c7  jmp     short loc_1400460CD
0x1400460c9  add     rdi, 2
0x1400460cd  cmp     [rdi], si
0x1400460d0  jz      short loc_1400460C9
0x1400460d2  mov     r8d, 1; MaxCount
0x1400460d8  lea     rdx, aA; "A"
0x1400460df  mov     rcx, rdi; Str1
0x1400460e2  call    cs:__imp__wcsnicmp
0x1400460e9  nop     dword ptr [rax+rax+00h]
0x1400460ee  test    eax, eax
0x1400460f0  jnz     loc_14004628E
0x1400460f6  add     rdi, 4
0x1400460fa  jmp     short loc_140046100
0x1400460fc  add     rdi, 2
0x140046100  movzx   eax, word ptr [rdi]
0x140046103  cmp     ax, si
0x140046106  jz      short loc_1400460FC
0x140046108  cmp     ax, 3Bh ; ';'
0x14004610c  jnz     loc_14004628E
0x140046112  add     rdi, 2
0x140046116  movzx   eax, word ptr [rdi]
0x140046119  cmp     ax, si
0x14004611c  jz      short loc_140046112
0x14004611e  cmp     ax, 3Bh ; ';'
0x140046122  jz      loc_1400461BD
0x140046128  cmp     ax, si
0x14004612b  jnz     short loc_140046136
0x14004612d  add     rdi, 2
0x140046131  cmp     [rdi], si
0x140046134  jz      short loc_14004612D
0x140046136  xor     esi, esi
0x140046138  lea     rax, off_14001A0A0; "RC"
0x14004613f  mov     r12d, esi
0x140046142  shl     r12, 4
0x140046146  mov     rcx, rdi; Str1
0x140046149  mov     r8d, [r12+rax+8]; MaxCount
0x14004614e  mov     rdx, [r12+rax]; Str2
0x140046152  call    cs:__imp__wcsnicmp
0x140046159  nop     dword ptr [rax+rax+00h]
0x14004615e  test    eax, eax
0x140046160  jz      short loc_14004618D
0x140046162  inc     esi
0x140046164  cmp     esi, 8
0x140046167  jb      short loc_140046138
0x140046169  lea     r8, [rbp+arg_0]
0x14004616d  mov     [rbp+arg_18], rdi
0x140046171  lea     rdx, [rbp+arg_18]
0x140046175  mov     rcx, rdi
0x140046178  call    SepSddlParseWideStringUlong
0x14004617d  cmp     [rbp+arg_18], rdi
0x140046181  jz      loc_14004628E
0x140046187  mov     rdi, [rbp+arg_18]
0x14004618b  jmp     short loc_1400461A8
0x14004618d  mov     eax, dword ptr [rbp+arg_0]
0x140046190  lea     rcx, off_14001A0A0; "RC"
0x140046197  or      eax, [r12+rcx+0Ch]
0x14004619c  mov     dword ptr [rbp+arg_0], eax
0x14004619f  mov     eax, [r12+rcx+8]
0x1400461a4  lea     rdi, [rdi+rax*2]
0x1400461a8  movzx   eax, word ptr [rdi]
0x1400461ab  mov     si, 20h ; ' '
0x1400461af  cmp     ax, 3Bh ; ';'
0x1400461b3  jnz     loc_140046128
0x1400461b9  mov     r12d, dword ptr [rbp+arg_0]
0x1400461bd  lea     rcx, [rdi+2]
0x1400461c1  test    ebx, ebx
0x1400461c3  jnz     loc_140046291
0x1400461c9  lea     edx, [rbx+2]
0x1400461cc  jmp     short loc_1400461D2
0x1400461ce  add     rcx, 2
0x1400461d2  movzx   eax, word ptr [rcx]
0x1400461d5  cmp     ax, si
0x1400461d8  jz      short loc_1400461CE
0x1400461da  cmp     ax, 3Bh ; ';'
0x1400461de  cmovnz  ebx, r15d
0x1400461e2  add     rcx, 2
0x1400461e6  sub     edx, 1
0x1400461e9  jnz     short loc_1400461D2
0x1400461eb  test    ebx, ebx
0x1400461ed  jnz     loc_140046291
0x1400461f3  jmp     short loc_1400461F9
0x1400461f5  add     rcx, 2; Str1
0x1400461f9  cmp     [rcx], si
0x1400461fc  jz      short loc_1400461F5
0x1400461fe  lea     r8, [rbp+arg_0]
0x140046202  mov     [rbp+arg_0], 0
0x14004620a  lea     rdx, [rbp+var_18]
0x14004620e  call    SepSddlGetSidForString
0x140046213  mov     ebx, eax
0x140046215  test    eax, eax
0x140046217  jnz     short loc_140046289
0x140046219  mov     rsi, [rbp+arg_0]
0x14004621d  test    rsi, rsi
0x140046220  jnz     short loc_14004622D
0x140046222  mov     ebx, 0C0000077h
0x140046227  jmp     short loc_140046291
0x140046229  add     rsi, 2
0x14004622d  movzx   eax, word ptr [rsi]
0x140046230  cmp     ax, 20h ; ' '
0x140046234  jz      short loc_140046229
0x140046236  cmp     ax, 29h ; ')'
0x14004623a  jnz     short loc_140046222
0x14004623c  mov     rcx, [rbp+var_18]
0x140046240  mov     edi, [rbp+arg_8]
0x140046243  test    rcx, rcx
0x140046246  jz      short loc_14004626D
0x140046248  mov     [rsp+58h+Sid], rcx; Sid
0x14004624d  lea     rdx, [rbp+arg_10]; int
0x140046251  mov     eax, r13d
0x140046254  mov     rcx, r14; int
0x140046257  sub     eax, edi
0x140046259  mov     [rsp+58h+var_30], eax; int
0x14004625d  mov     [rsp+58h+AccessMask], r12d; AccessMask
0x140046262  call    SepSddlAddAceToAcl
0x140046267  mov     ebx, eax
0x140046269  test    eax, eax
0x14004626b  jnz     short loc_140046291
0x14004626d  add     rsi, 2
0x140046271  cmp     word ptr [rsi], 28h ; '('
0x140046275  jnz     short loc_14004627B
0x140046277  add     rsi, 2
0x14004627b  inc     edi
0x14004627d  mov     [rbp+arg_8], edi
0x140046280  cmp     edi, r13d
0x140046283  jb      loc_1400460A1
0x140046289  mov     ecx, [rbp+arg_10]
0x14004628c  jmp     short loc_14004629B
0x14004628e  mov     ebx, r15d
0x140046291  mov     rax, [r14]
0x140046294  jmp     short loc_1400462A2
0x140046296  mov     ecx, 8
0x14004629b  mov     rax, [r14]
0x14004629e  test    ebx, ebx
0x1400462a0  jz      short loc_1400462BC
0x1400462a2  xor     edx, edx; Tag
0x1400462a4  mov     rcx, rax; P
0x1400462a7  call    cs:__imp_ExFreePoolWithTag
0x1400462ae  nop     dword ptr [rax+rax+00h]
0x1400462b3  mov     qword ptr [r14], 0
0x1400462ba  jmp     short loc_1400462C7
0x1400462bc  mov     [rax+2], cx
0x1400462c0  jmp     short loc_1400462C7
0x1400462c2  mov     ebx, 0C000000Dh
0x1400462c7  mov     eax, ebx
0x1400462c9  add     rsp, 58h
0x1400462cd  pop     r15
0x1400462cf  pop     r14
0x1400462d1  pop     r13
0x1400462d3  pop     r12
0x1400462d5  pop     rdi
0x1400462d6  pop     rsi
0x1400462d7  pop     rbx
0x1400462d8  pop     rbp
0x1400462d9  retn
```
