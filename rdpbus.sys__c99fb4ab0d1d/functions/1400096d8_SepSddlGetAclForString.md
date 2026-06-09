# SepSddlGetAclForString

- ea: `0x1400096d8`
- end: `0x140009a8c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400095f4`

## callees

- `0x140002940`
- `0x140009500`
- `0x1400096d8`
- `0x140009a94`
- `0x140009b4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009a54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009a54`
- `ntoskrnl!wcschr` at `0x140009703`
- `ntoskrnl!wcschr` at `0x140009703`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400097ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400097ff`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400097ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400097ff`
- `ntoskrnl!_wcsnicmp` at `0x14000989c`
- `ntoskrnl!_wcsnicmp` at `0x140009915`
- `ntoskrnl!_wcsnicmp` at `0x14000989c`
- `ntoskrnl!_wcsnicmp` at `0x140009915`

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
            if ( !_wcsnicmp(j, (&off_140005010)[v23], *((unsigned int *)&off_140005010 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_140005010 + 2 * v23 + 3);
              j += *((unsigned int *)&off_140005010 + 2 * v23 + 2);
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
0x1400096d8  push    rbp
0x1400096da  push    rbx
0x1400096db  push    rsi
0x1400096dc  push    rdi
0x1400096dd  push    r12
0x1400096df  push    r13
0x1400096e1  push    r14
0x1400096e3  push    r15
0x1400096e5  mov     rbp, rsp
0x1400096e8  sub     rsp, 58h
0x1400096ec  xor     r15d, r15d
0x1400096ef  mov     r14, rdx
0x1400096f2  mov     [rdx], r15
0x1400096f5  mov     rbx, r8
0x1400096f8  mov     rsi, rcx
0x1400096fb  mov     [rbp+var_18], r15
0x1400096ff  lea     edx, [r15+3Ah]; Ch
0x140009703  call    cs:__imp_wcschr
0x14000970a  nop     dword ptr [rax+rax+00h]
0x14000970f  mov     [rbx], rax
0x140009712  cmp     rax, rsi
0x140009715  jnz     short loc_140009721
0x140009717  mov     eax, 0C000000Dh
0x14000971c  jmp     loc_140009A7A
0x140009721  mov     r8d, r15d
0x140009724  test    rax, rax
0x140009727  jnz     short loc_14000973D
0x140009729  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000972d  inc     rax
0x140009730  cmp     [rsi+rax*2], r15w
0x140009735  jnz     short loc_14000972D
0x140009737  lea     rax, [rsi+rax*2]
0x14000973b  jmp     short loc_140009741
0x14000973d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140009741  mov     [rbx], rax
0x140009744  mov     rcx, rsi
0x140009747  mov     r9d, r15d
0x14000974a  mov     r10d, 1
0x140009750  cmp     rsi, rax
0x140009753  jnb     short loc_140009774
0x140009755  movzx   edx, word ptr [rcx]
0x140009758  cmp     dx, 3Bh ; ';'
0x14000975c  jnz     short loc_140009763
0x14000975e  add     r8d, r10d
0x140009761  jmp     short loc_14000976B
0x140009763  cmp     dx, 20h ; ' '
0x140009767  cmovnz  r9d, r10d
0x14000976b  add     rcx, 2
0x14000976f  cmp     rcx, rax
0x140009772  jb      short loc_140009755
0x140009774  mov     eax, 0CCCCCCCDh
0x140009779  mul     r8d
0x14000977c  mov     r13d, edx
0x14000977f  shr     r13d, 2
0x140009783  lea     ecx, ds:0[r13*4]
0x14000978b  add     ecx, r13d
0x14000978e  cmp     r8d, ecx
0x140009791  jnz     loc_140009A73
0x140009797  test    r8d, r8d
0x14000979a  jnz     short loc_1400097A5
0x14000979c  test    r9d, r9d
0x14000979f  jnz     loc_140009A73
0x1400097a5  mov     ebx, r15d
0x1400097a8  mov     r8d, 6C416553h; Tag
0x1400097ae  mov     ecx, r10d; PoolType
0x1400097b1  test    r13d, r13d
0x1400097b4  jnz     short loc_1400097DA
0x1400097b6  lea     edx, [r13+8]; NumberOfBytes
0x1400097ba  call    cs:__imp_ExAllocatePoolWithTag
0x1400097c1  nop     dword ptr [rax+rax+00h]
0x1400097c6  mov     [r14], rax
0x1400097c9  test    rax, rax
0x1400097cc  jz      short loc_140009816
0x1400097ce  mov     qword ptr [rax], 80002h
0x1400097d5  jmp     loc_140009A78
0x1400097da  mov     eax, 0FFFFh
0x1400097df  lea     r15d, ds:0[r13*2]
0x1400097e7  add     r15d, r13d
0x1400097ea  shl     r15d, 4
0x1400097ee  add     r15d, 8
0x1400097f2  cmp     r15d, eax
0x1400097f5  cmova   r15d, eax
0x1400097f9  mov     edx, r15d; NumberOfBytes
0x1400097fc  mov     r12d, r15d
0x1400097ff  call    cs:__imp_ExAllocatePoolWithTag
0x140009806  nop     dword ptr [rax+rax+00h]
0x14000980b  mov     [r14], rax
0x14000980e  mov     rdi, rax
0x140009811  test    rax, rax
0x140009814  jnz     short loc_140009820
0x140009816  mov     ebx, 0C000009Ah
0x14000981b  jmp     loc_140009A78
0x140009820  mov     r8, r12; Size
0x140009823  mov     [rbp+arg_10], 8
0x14000982a  xor     edx, edx; Val
0x14000982c  mov     rcx, rdi; void *
0x14000982f  call    memset
0x140009834  xor     eax, eax
0x140009836  mov     word ptr [rdi], 2
0x14000983b  mov     [rdi+2], r15w
0x140009840  xor     r12d, r12d
0x140009843  mov     [rdi+4], eax
0x140009846  mov     r15d, 0C000000Dh
0x14000984c  mov     [rbp+arg_8], r12d
0x140009850  cmp     r12d, r13d
0x140009853  jnb     loc_140009A4B
0x140009859  mov     [rbp+arg_0], 0
0x140009860  mov     r12w, 20h ; ' '
0x140009865  jmp     short loc_14000986B
0x140009867  add     rsi, 2
0x14000986b  movzx   eax, word ptr [rsi]
0x14000986e  cmp     ax, r12w
0x140009872  jz      short loc_140009867
0x140009874  cmp     ax, 28h ; '('
0x140009878  lea     rdi, [rsi+2]
0x14000987c  cmovnz  rdi, rsi
0x140009880  jmp     short loc_140009886
0x140009882  add     rdi, 2
0x140009886  cmp     [rdi], r12w
0x14000988a  jz      short loc_140009882
0x14000988c  mov     r8d, 1; MaxCount
0x140009892  lea     rdx, aA; "A"
0x140009899  mov     rcx, rdi; Str1
0x14000989c  call    cs:__imp__wcsnicmp
0x1400098a3  nop     dword ptr [rax+rax+00h]
0x1400098a8  test    eax, eax
0x1400098aa  jnz     loc_140009A43
0x1400098b0  add     rdi, 4
0x1400098b4  jmp     short loc_1400098BA
0x1400098b6  add     rdi, 2
0x1400098ba  movzx   eax, word ptr [rdi]
0x1400098bd  cmp     ax, r12w
0x1400098c1  jz      short loc_1400098B6
0x1400098c3  cmp     ax, 3Bh ; ';'
0x1400098c7  jnz     loc_140009A43
0x1400098cd  add     rdi, 2
0x1400098d1  cmp     [rdi], r12w
0x1400098d5  jz      short loc_1400098CD
0x1400098d7  lea     rcx, off_140005010; "RC"
0x1400098de  movzx   eax, word ptr [rdi]
0x1400098e1  cmp     ax, 3Bh ; ';'
0x1400098e5  jz      loc_140009977
0x1400098eb  cmp     ax, r12w
0x1400098ef  jnz     short loc_1400098FB
0x1400098f1  add     rdi, 2
0x1400098f5  cmp     [rdi], r12w
0x1400098f9  jz      short loc_1400098F1
0x1400098fb  xor     esi, esi
0x1400098fd  cmp     esi, 8
0x140009900  jnb     short loc_14000994B
0x140009902  mov     r12d, esi
0x140009905  shl     r12, 4
0x140009909  mov     r8d, [r12+rcx+8]; MaxCount
0x14000990e  mov     rdx, [r12+rcx]; Str2
0x140009912  mov     rcx, rdi; Str1
0x140009915  call    cs:__imp__wcsnicmp
0x14000991c  nop     dword ptr [rax+rax+00h]
0x140009921  lea     rcx, off_140005010; "RC"
0x140009928  test    eax, eax
0x14000992a  jz      short loc_140009930
0x14000992c  inc     esi
0x14000992e  jmp     short loc_1400098FD
0x140009930  mov     eax, [rbp+arg_0]
0x140009933  or      eax, [r12+rcx+0Ch]
0x140009938  mov     [rbp+arg_0], eax
0x14000993b  mov     eax, [r12+rcx+8]
0x140009940  mov     r12w, 20h ; ' '
0x140009945  lea     rdi, [rdi+rax*2]
0x140009949  jmp     short loc_1400098DE
0x14000994b  lea     r8, [rbp+arg_0]
0x14000994f  mov     [rbp+arg_18], rdi
0x140009953  lea     rdx, [rbp+arg_18]
0x140009957  mov     rcx, rdi
0x14000995a  call    SepSddlParseWideStringUlong
0x14000995f  cmp     [rbp+arg_18], rdi
0x140009963  jz      loc_140009A43
0x140009969  mov     rdi, [rbp+arg_18]
0x14000996d  mov     r12w, 20h ; ' '
0x140009972  jmp     loc_1400098D7
0x140009977  lea     rcx, [rdi+2]
0x14000997b  test    ebx, ebx
0x14000997d  jnz     loc_140009A46
0x140009983  lea     edx, [rbx+2]
0x140009986  jmp     short loc_14000998C
0x140009988  add     rcx, 2
0x14000998c  movzx   eax, word ptr [rcx]
0x14000998f  cmp     ax, r12w
0x140009993  jz      short loc_140009988
0x140009995  cmp     ax, 3Bh ; ';'
0x140009999  cmovnz  ebx, r15d
0x14000999d  add     rcx, 2
0x1400099a1  sub     edx, 1
0x1400099a4  jnz     short loc_14000998C
0x1400099a6  test    ebx, ebx
0x1400099a8  jnz     loc_140009A46
0x1400099ae  jmp     short loc_1400099B4
0x1400099b0  add     rcx, 2; Str1
0x1400099b4  cmp     [rcx], r12w
0x1400099b8  jz      short loc_1400099B0
0x1400099ba  lea     r8, [rbp+arg_18]
0x1400099be  mov     [rbp+arg_18], 0
0x1400099c6  lea     rdx, [rbp+var_18]
0x1400099ca  call    SepSddlGetSidForString
0x1400099cf  mov     ebx, eax
0x1400099d1  test    eax, eax
0x1400099d3  jnz     short loc_140009A4B
0x1400099d5  mov     rsi, [rbp+arg_18]
0x1400099d9  test    rsi, rsi
0x1400099dc  jnz     short loc_1400099E9
0x1400099de  mov     ebx, 0C0000077h
0x1400099e3  jmp     short loc_140009A46
0x1400099e5  add     rsi, 2
0x1400099e9  movzx   eax, word ptr [rsi]
0x1400099ec  cmp     ax, r12w
0x1400099f0  jz      short loc_1400099E5
0x1400099f2  cmp     ax, 29h ; ')'
0x1400099f6  jnz     short loc_1400099DE
0x1400099f8  mov     rcx, [rbp+var_18]
0x1400099fc  mov     r12d, [rbp+arg_8]
0x140009a00  test    rcx, rcx
0x140009a03  jz      short loc_140009A2D
0x140009a05  mov     [rsp+58h+Sid], rcx; Sid
0x140009a0a  lea     rdx, [rbp+arg_10]; int
0x140009a0e  mov     eax, r13d
0x140009a11  mov     rcx, r14; int
0x140009a14  sub     eax, r12d
0x140009a17  mov     [rsp+58h+var_30], eax; int
0x140009a1b  mov     eax, [rbp+arg_0]
0x140009a1e  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140009a22  call    SepSddlAddAceToAcl
0x140009a27  mov     ebx, eax
0x140009a29  test    eax, eax
0x140009a2b  jnz     short loc_140009A46
0x140009a2d  add     rsi, 2
0x140009a31  cmp     word ptr [rsi], 28h ; '('
0x140009a35  jnz     short loc_140009A3B
0x140009a37  add     rsi, 2
0x140009a3b  inc     r12d
0x140009a3e  jmp     loc_14000984C
0x140009a43  mov     ebx, r15d
0x140009a46  mov     rcx, [r14]
0x140009a49  jmp     short loc_140009A52
0x140009a4b  mov     rcx, [r14]; P
0x140009a4e  test    ebx, ebx
0x140009a50  jz      short loc_140009A69
0x140009a52  xor     edx, edx; Tag
0x140009a54  call    cs:__imp_ExFreePoolWithTag
0x140009a5b  nop     dword ptr [rax+rax+00h]
0x140009a60  mov     qword ptr [r14], 0
0x140009a67  jmp     short loc_140009A78
0x140009a69  movzx   eax, word ptr [rbp+arg_10]
0x140009a6d  mov     [rcx+2], ax
0x140009a71  jmp     short loc_140009A78
0x140009a73  mov     ebx, 0C000000Dh
0x140009a78  mov     eax, ebx
0x140009a7a  add     rsp, 58h
0x140009a7e  pop     r15
0x140009a80  pop     r14
0x140009a82  pop     r13
0x140009a84  pop     r12
0x140009a86  pop     rdi
0x140009a87  pop     rsi
0x140009a88  pop     rbx
0x140009a89  pop     rbp
0x140009a8a  retn
```
