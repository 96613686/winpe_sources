# SepSddlGetAclForString

- ea: `0x140021428`
- end: `0x1400217ce`
- name: `SepSddlGetAclForString`
- size: `934`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140021344`

## callees

- `0x14000302d`
- `0x1400068c0`
- `0x140021250`
- `0x140021428`
- `0x1400217d4`
- `0x140021884`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021796`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021796`
- `ntoskrnl!wcschr` at `0x140021453`
- `ntoskrnl!wcschr` at `0x140021453`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002150a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002154f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002150a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002154f`

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
        if ( wcsnicmp_0(v20, L"A", 1u) )
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
            if ( !wcsnicmp_0(j, (&off_14000C090)[v23], *((unsigned int *)&off_14000C090 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_14000C090 + 2 * v23 + 3);
              j += *((unsigned int *)&off_14000C090 + 2 * v23 + 2);
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
0x140021428  push    rbp
0x14002142a  push    rbx
0x14002142b  push    rsi
0x14002142c  push    rdi
0x14002142d  push    r12
0x14002142f  push    r13
0x140021431  push    r14
0x140021433  push    r15
0x140021435  mov     rbp, rsp
0x140021438  sub     rsp, 58h
0x14002143c  xor     r15d, r15d
0x14002143f  mov     r14, rdx
0x140021442  mov     [rdx], r15
0x140021445  mov     rbx, r8
0x140021448  mov     rsi, rcx
0x14002144b  mov     [rbp+var_18], r15
0x14002144f  lea     edx, [r15+3Ah]; Ch
0x140021453  call    cs:__imp_wcschr
0x14002145a  nop     dword ptr [rax+rax+00h]
0x14002145f  mov     [rbx], rax
0x140021462  cmp     rax, rsi
0x140021465  jnz     short loc_140021471
0x140021467  mov     eax, 0C000000Dh
0x14002146c  jmp     loc_1400217BC
0x140021471  mov     r8d, r15d
0x140021474  test    rax, rax
0x140021477  jnz     short loc_14002148D
0x140021479  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002147d  inc     rax
0x140021480  cmp     [rsi+rax*2], r15w
0x140021485  jnz     short loc_14002147D
0x140021487  lea     rax, [rsi+rax*2]
0x14002148b  jmp     short loc_140021491
0x14002148d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140021491  mov     [rbx], rax
0x140021494  mov     rcx, rsi
0x140021497  mov     r9d, r15d
0x14002149a  mov     r10d, 1
0x1400214a0  cmp     rsi, rax
0x1400214a3  jnb     short loc_1400214C4
0x1400214a5  movzx   edx, word ptr [rcx]
0x1400214a8  cmp     dx, 3Bh ; ';'
0x1400214ac  jnz     short loc_1400214B3
0x1400214ae  add     r8d, r10d
0x1400214b1  jmp     short loc_1400214BB
0x1400214b3  cmp     dx, 20h ; ' '
0x1400214b7  cmovnz  r9d, r10d
0x1400214bb  add     rcx, 2
0x1400214bf  cmp     rcx, rax
0x1400214c2  jb      short loc_1400214A5
0x1400214c4  mov     eax, 0CCCCCCCDh
0x1400214c9  mul     r8d
0x1400214cc  mov     r13d, edx
0x1400214cf  shr     r13d, 2
0x1400214d3  lea     ecx, ds:0[r13*4]
0x1400214db  add     ecx, r13d
0x1400214de  cmp     r8d, ecx
0x1400214e1  jnz     loc_1400217B5
0x1400214e7  test    r8d, r8d
0x1400214ea  jnz     short loc_1400214F5
0x1400214ec  test    r9d, r9d
0x1400214ef  jnz     loc_1400217B5
0x1400214f5  mov     ebx, r15d
0x1400214f8  mov     r8d, 6C416553h; Tag
0x1400214fe  mov     ecx, r10d; PoolType
0x140021501  test    r13d, r13d
0x140021504  jnz     short loc_14002152A
0x140021506  lea     edx, [r13+8]; NumberOfBytes
0x14002150a  call    cs:__imp_ExAllocatePoolWithTag
0x140021511  nop     dword ptr [rax+rax+00h]
0x140021516  mov     [r14], rax
0x140021519  test    rax, rax
0x14002151c  jz      short loc_140021566
0x14002151e  mov     qword ptr [rax], 80002h
0x140021525  jmp     loc_1400217BA
0x14002152a  mov     eax, 0FFFFh
0x14002152f  lea     r15d, ds:0[r13*2]
0x140021537  add     r15d, r13d
0x14002153a  shl     r15d, 4
0x14002153e  add     r15d, 8
0x140021542  cmp     r15d, eax
0x140021545  cmova   r15d, eax
0x140021549  mov     edx, r15d; NumberOfBytes
0x14002154c  mov     r12d, r15d
0x14002154f  call    cs:__imp_ExAllocatePoolWithTag
0x140021556  nop     dword ptr [rax+rax+00h]
0x14002155b  mov     [r14], rax
0x14002155e  mov     rdi, rax
0x140021561  test    rax, rax
0x140021564  jnz     short loc_140021570
0x140021566  mov     ebx, 0C000009Ah
0x14002156b  jmp     loc_1400217BA
0x140021570  mov     r8, r12; Size
0x140021573  mov     [rbp+arg_10], 8
0x14002157a  xor     edx, edx; Val
0x14002157c  mov     rcx, rdi; void *
0x14002157f  call    memset
0x140021584  xor     eax, eax
0x140021586  mov     word ptr [rdi], 2
0x14002158b  mov     [rdi+2], r15w
0x140021590  xor     r12d, r12d
0x140021593  mov     [rdi+4], eax
0x140021596  mov     r15d, 0C000000Dh
0x14002159c  mov     [rbp+arg_8], r12d
0x1400215a0  cmp     r12d, r13d
0x1400215a3  jnb     loc_14002178D
0x1400215a9  mov     [rbp+arg_0], 0
0x1400215b0  mov     r12w, 20h ; ' '
0x1400215b5  jmp     short loc_1400215BB
0x1400215b7  add     rsi, 2
0x1400215bb  movzx   eax, word ptr [rsi]
0x1400215be  cmp     ax, r12w
0x1400215c2  jz      short loc_1400215B7
0x1400215c4  cmp     ax, 28h ; '('
0x1400215c8  lea     rdi, [rsi+2]
0x1400215cc  cmovnz  rdi, rsi
0x1400215d0  jmp     short loc_1400215D6
0x1400215d2  add     rdi, 2
0x1400215d6  cmp     [rdi], r12w
0x1400215da  jz      short loc_1400215D2
0x1400215dc  mov     r8d, 1; MaxCount
0x1400215e2  lea     rdx, aA; "A"
0x1400215e9  mov     rcx, rdi; Str1
0x1400215ec  call    _wcsnicmp_0
0x1400215f1  test    eax, eax
0x1400215f3  jnz     loc_140021785
0x1400215f9  add     rdi, 4
0x1400215fd  jmp     short loc_140021603
0x1400215ff  add     rdi, 2
0x140021603  movzx   eax, word ptr [rdi]
0x140021606  cmp     ax, r12w
0x14002160a  jz      short loc_1400215FF
0x14002160c  cmp     ax, 3Bh ; ';'
0x140021610  jnz     loc_140021785
0x140021616  add     rdi, 2
0x14002161a  cmp     [rdi], r12w
0x14002161e  jz      short loc_140021616
0x140021620  lea     rcx, off_14000C090; "RC"
0x140021627  movzx   eax, word ptr [rdi]
0x14002162a  cmp     ax, 3Bh ; ';'
0x14002162e  jz      loc_1400216B9
0x140021634  cmp     ax, r12w
0x140021638  jnz     short loc_140021644
0x14002163a  add     rdi, 2
0x14002163e  cmp     [rdi], r12w
0x140021642  jz      short loc_14002163A
0x140021644  xor     esi, esi
0x140021646  cmp     esi, 8
0x140021649  jnb     short loc_14002168D
0x14002164b  mov     r12d, esi
0x14002164e  shl     r12, 4
0x140021652  mov     r8d, [r12+rcx+8]; MaxCount
0x140021657  mov     rdx, [r12+rcx]; Str2
0x14002165b  mov     rcx, rdi; Str1
0x14002165e  call    _wcsnicmp_0
0x140021663  lea     rcx, off_14000C090; "RC"
0x14002166a  test    eax, eax
0x14002166c  jz      short loc_140021672
0x14002166e  inc     esi
0x140021670  jmp     short loc_140021646
0x140021672  mov     eax, [rbp+arg_0]
0x140021675  or      eax, [r12+rcx+0Ch]
0x14002167a  mov     [rbp+arg_0], eax
0x14002167d  mov     eax, [r12+rcx+8]
0x140021682  mov     r12w, 20h ; ' '
0x140021687  lea     rdi, [rdi+rax*2]
0x14002168b  jmp     short loc_140021627
0x14002168d  lea     r8, [rbp+arg_0]
0x140021691  mov     [rbp+arg_18], rdi
0x140021695  lea     rdx, [rbp+arg_18]
0x140021699  mov     rcx, rdi
0x14002169c  call    SepSddlParseWideStringUlong
0x1400216a1  cmp     [rbp+arg_18], rdi
0x1400216a5  jz      loc_140021785
0x1400216ab  mov     rdi, [rbp+arg_18]
0x1400216af  mov     r12w, 20h ; ' '
0x1400216b4  jmp     loc_140021620
0x1400216b9  lea     rcx, [rdi+2]
0x1400216bd  test    ebx, ebx
0x1400216bf  jnz     loc_140021788
0x1400216c5  lea     edx, [rbx+2]
0x1400216c8  jmp     short loc_1400216CE
0x1400216ca  add     rcx, 2
0x1400216ce  movzx   eax, word ptr [rcx]
0x1400216d1  cmp     ax, r12w
0x1400216d5  jz      short loc_1400216CA
0x1400216d7  cmp     ax, 3Bh ; ';'
0x1400216db  cmovnz  ebx, r15d
0x1400216df  add     rcx, 2
0x1400216e3  sub     edx, 1
0x1400216e6  jnz     short loc_1400216CE
0x1400216e8  test    ebx, ebx
0x1400216ea  jnz     loc_140021788
0x1400216f0  jmp     short loc_1400216F6
0x1400216f2  add     rcx, 2; Str1
0x1400216f6  cmp     [rcx], r12w
0x1400216fa  jz      short loc_1400216F2
0x1400216fc  lea     r8, [rbp+arg_18]
0x140021700  mov     [rbp+arg_18], 0
0x140021708  lea     rdx, [rbp+var_18]
0x14002170c  call    SepSddlGetSidForString
0x140021711  mov     ebx, eax
0x140021713  test    eax, eax
0x140021715  jnz     short loc_14002178D
0x140021717  mov     rsi, [rbp+arg_18]
0x14002171b  test    rsi, rsi
0x14002171e  jnz     short loc_14002172B
0x140021720  mov     ebx, 0C0000077h
0x140021725  jmp     short loc_140021788
0x140021727  add     rsi, 2
0x14002172b  movzx   eax, word ptr [rsi]
0x14002172e  cmp     ax, r12w
0x140021732  jz      short loc_140021727
0x140021734  cmp     ax, 29h ; ')'
0x140021738  jnz     short loc_140021720
0x14002173a  mov     rcx, [rbp+var_18]
0x14002173e  mov     r12d, [rbp+arg_8]
0x140021742  test    rcx, rcx
0x140021745  jz      short loc_14002176F
0x140021747  mov     [rsp+58h+Sid], rcx; Sid
0x14002174c  lea     rdx, [rbp+arg_10]; int
0x140021750  mov     eax, r13d
0x140021753  mov     rcx, r14; int
0x140021756  sub     eax, r12d
0x140021759  mov     [rsp+58h+var_30], eax; int
0x14002175d  mov     eax, [rbp+arg_0]
0x140021760  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140021764  call    SepSddlAddAceToAcl
0x140021769  mov     ebx, eax
0x14002176b  test    eax, eax
0x14002176d  jnz     short loc_140021788
0x14002176f  add     rsi, 2
0x140021773  cmp     word ptr [rsi], 28h ; '('
0x140021777  jnz     short loc_14002177D
0x140021779  add     rsi, 2
0x14002177d  inc     r12d
0x140021780  jmp     loc_14002159C
0x140021785  mov     ebx, r15d
0x140021788  mov     rcx, [r14]
0x14002178b  jmp     short loc_140021794
0x14002178d  mov     rcx, [r14]; P
0x140021790  test    ebx, ebx
0x140021792  jz      short loc_1400217AB
0x140021794  xor     edx, edx; Tag
0x140021796  call    cs:__imp_ExFreePoolWithTag
0x14002179d  nop     dword ptr [rax+rax+00h]
0x1400217a2  mov     qword ptr [r14], 0
0x1400217a9  jmp     short loc_1400217BA
0x1400217ab  movzx   eax, word ptr [rbp+arg_10]
0x1400217af  mov     [rcx+2], ax
0x1400217b3  jmp     short loc_1400217BA
0x1400217b5  mov     ebx, 0C000000Dh
0x1400217ba  mov     eax, ebx
0x1400217bc  add     rsp, 58h
0x1400217c0  pop     r15
0x1400217c2  pop     r14
0x1400217c4  pop     r13
0x1400217c6  pop     r12
0x1400217c8  pop     rdi
0x1400217c9  pop     rsi
0x1400217ca  pop     rbx
0x1400217cb  pop     rbp
0x1400217cc  retn
```
