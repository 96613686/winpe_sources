# SepSddlGetAclForString

- ea: `0x140041fcc`
- end: `0x140042380`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140041ee8`

## callees

- `0x14001e580`
- `0x140041df4`
- `0x140041fcc`
- `0x140042388`
- `0x140042440`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x140042190`
- `ntoskrnl!_wcsnicmp` at `0x140042209`
- `ntoskrnl!_wcsnicmp` at `0x140042190`
- `ntoskrnl!_wcsnicmp` at `0x140042209`
- `ntoskrnl!wcschr` at `0x140041ff7`
- `ntoskrnl!wcschr` at `0x140041ff7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400420ae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400420f3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400420ae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400420f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042348`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042348`

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
0x140041fcc  push    rbp
0x140041fce  push    rbx
0x140041fcf  push    rsi
0x140041fd0  push    rdi
0x140041fd1  push    r12
0x140041fd3  push    r13
0x140041fd5  push    r14
0x140041fd7  push    r15
0x140041fd9  mov     rbp, rsp
0x140041fdc  sub     rsp, 58h
0x140041fe0  xor     r15d, r15d
0x140041fe3  mov     r14, rdx
0x140041fe6  mov     [rdx], r15
0x140041fe9  mov     rbx, r8
0x140041fec  mov     rsi, rcx
0x140041fef  mov     [rbp+var_18], r15
0x140041ff3  lea     edx, [r15+3Ah]; Ch
0x140041ff7  call    cs:__imp_wcschr
0x140041ffe  nop     dword ptr [rax+rax+00h]
0x140042003  mov     [rbx], rax
0x140042006  cmp     rax, rsi
0x140042009  jnz     short loc_140042015
0x14004200b  mov     eax, 0C000000Dh
0x140042010  jmp     loc_14004236E
0x140042015  mov     r8d, r15d
0x140042018  test    rax, rax
0x14004201b  jnz     short loc_140042031
0x14004201d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140042021  inc     rax
0x140042024  cmp     [rsi+rax*2], r15w
0x140042029  jnz     short loc_140042021
0x14004202b  lea     rax, [rsi+rax*2]
0x14004202f  jmp     short loc_140042035
0x140042031  add     rax, 0FFFFFFFFFFFFFFFEh
0x140042035  mov     [rbx], rax
0x140042038  mov     rcx, rsi
0x14004203b  mov     r9d, r15d
0x14004203e  mov     r10d, 1
0x140042044  cmp     rsi, rax
0x140042047  jnb     short loc_140042068
0x140042049  movzx   edx, word ptr [rcx]
0x14004204c  cmp     dx, 3Bh ; ';'
0x140042050  jnz     short loc_140042057
0x140042052  add     r8d, r10d
0x140042055  jmp     short loc_14004205F
0x140042057  cmp     dx, 20h ; ' '
0x14004205b  cmovnz  r9d, r10d
0x14004205f  add     rcx, 2
0x140042063  cmp     rcx, rax
0x140042066  jb      short loc_140042049
0x140042068  mov     eax, 0CCCCCCCDh
0x14004206d  mul     r8d
0x140042070  mov     r13d, edx
0x140042073  shr     r13d, 2
0x140042077  lea     ecx, ds:0[r13*4]
0x14004207f  add     ecx, r13d
0x140042082  cmp     r8d, ecx
0x140042085  jnz     loc_140042367
0x14004208b  test    r8d, r8d
0x14004208e  jnz     short loc_140042099
0x140042090  test    r9d, r9d
0x140042093  jnz     loc_140042367
0x140042099  mov     ebx, r15d
0x14004209c  mov     r8d, 6C416553h; Tag
0x1400420a2  mov     ecx, r10d; PoolType
0x1400420a5  test    r13d, r13d
0x1400420a8  jnz     short loc_1400420CE
0x1400420aa  lea     edx, [r13+8]; NumberOfBytes
0x1400420ae  call    cs:__imp_ExAllocatePoolWithTag
0x1400420b5  nop     dword ptr [rax+rax+00h]
0x1400420ba  mov     [r14], rax
0x1400420bd  test    rax, rax
0x1400420c0  jz      short loc_14004210A
0x1400420c2  mov     qword ptr [rax], 80002h
0x1400420c9  jmp     loc_14004236C
0x1400420ce  mov     eax, 0FFFFh
0x1400420d3  lea     r15d, ds:0[r13*2]
0x1400420db  add     r15d, r13d
0x1400420de  shl     r15d, 4
0x1400420e2  add     r15d, 8
0x1400420e6  cmp     r15d, eax
0x1400420e9  cmova   r15d, eax
0x1400420ed  mov     edx, r15d; NumberOfBytes
0x1400420f0  mov     r12d, r15d
0x1400420f3  call    cs:__imp_ExAllocatePoolWithTag
0x1400420fa  nop     dword ptr [rax+rax+00h]
0x1400420ff  mov     [r14], rax
0x140042102  mov     rdi, rax
0x140042105  test    rax, rax
0x140042108  jnz     short loc_140042114
0x14004210a  mov     ebx, 0C000009Ah
0x14004210f  jmp     loc_14004236C
0x140042114  mov     r8, r12; Size
0x140042117  mov     [rbp+arg_10], 8
0x14004211e  xor     edx, edx; Val
0x140042120  mov     rcx, rdi; void *
0x140042123  call    memset
0x140042128  xor     eax, eax
0x14004212a  mov     word ptr [rdi], 2
0x14004212f  mov     [rdi+2], r15w
0x140042134  xor     r12d, r12d
0x140042137  mov     [rdi+4], eax
0x14004213a  mov     r15d, 0C000000Dh
0x140042140  mov     [rbp+arg_8], r12d
0x140042144  cmp     r12d, r13d
0x140042147  jnb     loc_14004233F
0x14004214d  mov     [rbp+arg_0], 0
0x140042154  mov     r12w, 20h ; ' '
0x140042159  jmp     short loc_14004215F
0x14004215b  add     rsi, 2
0x14004215f  movzx   eax, word ptr [rsi]
0x140042162  cmp     ax, r12w
0x140042166  jz      short loc_14004215B
0x140042168  cmp     ax, 28h ; '('
0x14004216c  lea     rdi, [rsi+2]
0x140042170  cmovnz  rdi, rsi
0x140042174  jmp     short loc_14004217A
0x140042176  add     rdi, 2
0x14004217a  cmp     [rdi], r12w
0x14004217e  jz      short loc_140042176
0x140042180  mov     r8d, 1; MaxCount
0x140042186  lea     rdx, aA; "A"
0x14004218d  mov     rcx, rdi; Str1
0x140042190  call    cs:__imp__wcsnicmp
0x140042197  nop     dword ptr [rax+rax+00h]
0x14004219c  test    eax, eax
0x14004219e  jnz     loc_140042337
0x1400421a4  add     rdi, 4
0x1400421a8  jmp     short loc_1400421AE
0x1400421aa  add     rdi, 2
0x1400421ae  movzx   eax, word ptr [rdi]
0x1400421b1  cmp     ax, r12w
0x1400421b5  jz      short loc_1400421AA
0x1400421b7  cmp     ax, 3Bh ; ';'
0x1400421bb  jnz     loc_140042337
0x1400421c1  add     rdi, 2
0x1400421c5  cmp     [rdi], r12w
0x1400421c9  jz      short loc_1400421C1
0x1400421cb  lea     rcx, off_140028240; "RC"
0x1400421d2  movzx   eax, word ptr [rdi]
0x1400421d5  cmp     ax, 3Bh ; ';'
0x1400421d9  jz      loc_14004226B
0x1400421df  cmp     ax, r12w
0x1400421e3  jnz     short loc_1400421EF
0x1400421e5  add     rdi, 2
0x1400421e9  cmp     [rdi], r12w
0x1400421ed  jz      short loc_1400421E5
0x1400421ef  xor     esi, esi
0x1400421f1  cmp     esi, 8
0x1400421f4  jnb     short loc_14004223F
0x1400421f6  mov     r12d, esi
0x1400421f9  shl     r12, 4
0x1400421fd  mov     r8d, [r12+rcx+8]; MaxCount
0x140042202  mov     rdx, [r12+rcx]; Str2
0x140042206  mov     rcx, rdi; Str1
0x140042209  call    cs:__imp__wcsnicmp
0x140042210  nop     dword ptr [rax+rax+00h]
0x140042215  lea     rcx, off_140028240; "RC"
0x14004221c  test    eax, eax
0x14004221e  jz      short loc_140042224
0x140042220  inc     esi
0x140042222  jmp     short loc_1400421F1
0x140042224  mov     eax, [rbp+arg_0]
0x140042227  or      eax, [r12+rcx+0Ch]
0x14004222c  mov     [rbp+arg_0], eax
0x14004222f  mov     eax, [r12+rcx+8]
0x140042234  mov     r12w, 20h ; ' '
0x140042239  lea     rdi, [rdi+rax*2]
0x14004223d  jmp     short loc_1400421D2
0x14004223f  lea     r8, [rbp+arg_0]
0x140042243  mov     [rbp+arg_18], rdi
0x140042247  lea     rdx, [rbp+arg_18]
0x14004224b  mov     rcx, rdi
0x14004224e  call    SepSddlParseWideStringUlong
0x140042253  cmp     [rbp+arg_18], rdi
0x140042257  jz      loc_140042337
0x14004225d  mov     rdi, [rbp+arg_18]
0x140042261  mov     r12w, 20h ; ' '
0x140042266  jmp     loc_1400421CB
0x14004226b  lea     rcx, [rdi+2]
0x14004226f  test    ebx, ebx
0x140042271  jnz     loc_14004233A
0x140042277  lea     edx, [rbx+2]
0x14004227a  jmp     short loc_140042280
0x14004227c  add     rcx, 2
0x140042280  movzx   eax, word ptr [rcx]
0x140042283  cmp     ax, r12w
0x140042287  jz      short loc_14004227C
0x140042289  cmp     ax, 3Bh ; ';'
0x14004228d  cmovnz  ebx, r15d
0x140042291  add     rcx, 2
0x140042295  sub     edx, 1
0x140042298  jnz     short loc_140042280
0x14004229a  test    ebx, ebx
0x14004229c  jnz     loc_14004233A
0x1400422a2  jmp     short loc_1400422A8
0x1400422a4  add     rcx, 2; Str1
0x1400422a8  cmp     [rcx], r12w
0x1400422ac  jz      short loc_1400422A4
0x1400422ae  lea     r8, [rbp+arg_18]
0x1400422b2  mov     [rbp+arg_18], 0
0x1400422ba  lea     rdx, [rbp+var_18]
0x1400422be  call    SepSddlGetSidForString
0x1400422c3  mov     ebx, eax
0x1400422c5  test    eax, eax
0x1400422c7  jnz     short loc_14004233F
0x1400422c9  mov     rsi, [rbp+arg_18]
0x1400422cd  test    rsi, rsi
0x1400422d0  jnz     short loc_1400422DD
0x1400422d2  mov     ebx, 0C0000077h
0x1400422d7  jmp     short loc_14004233A
0x1400422d9  add     rsi, 2
0x1400422dd  movzx   eax, word ptr [rsi]
0x1400422e0  cmp     ax, r12w
0x1400422e4  jz      short loc_1400422D9
0x1400422e6  cmp     ax, 29h ; ')'
0x1400422ea  jnz     short loc_1400422D2
0x1400422ec  mov     rcx, [rbp+var_18]
0x1400422f0  mov     r12d, [rbp+arg_8]
0x1400422f4  test    rcx, rcx
0x1400422f7  jz      short loc_140042321
0x1400422f9  mov     [rsp+58h+Sid], rcx; Sid
0x1400422fe  lea     rdx, [rbp+arg_10]; int
0x140042302  mov     eax, r13d
0x140042305  mov     rcx, r14; int
0x140042308  sub     eax, r12d
0x14004230b  mov     [rsp+58h+var_30], eax; int
0x14004230f  mov     eax, [rbp+arg_0]
0x140042312  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140042316  call    SepSddlAddAceToAcl
0x14004231b  mov     ebx, eax
0x14004231d  test    eax, eax
0x14004231f  jnz     short loc_14004233A
0x140042321  add     rsi, 2
0x140042325  cmp     word ptr [rsi], 28h ; '('
0x140042329  jnz     short loc_14004232F
0x14004232b  add     rsi, 2
0x14004232f  inc     r12d
0x140042332  jmp     loc_140042140
0x140042337  mov     ebx, r15d
0x14004233a  mov     rcx, [r14]
0x14004233d  jmp     short loc_140042346
0x14004233f  mov     rcx, [r14]; P
0x140042342  test    ebx, ebx
0x140042344  jz      short loc_14004235D
0x140042346  xor     edx, edx; Tag
0x140042348  call    cs:__imp_ExFreePoolWithTag
0x14004234f  nop     dword ptr [rax+rax+00h]
0x140042354  mov     qword ptr [r14], 0
0x14004235b  jmp     short loc_14004236C
0x14004235d  movzx   eax, word ptr [rbp+arg_10]
0x140042361  mov     [rcx+2], ax
0x140042365  jmp     short loc_14004236C
0x140042367  mov     ebx, 0C000000Dh
0x14004236c  mov     eax, ebx
0x14004236e  add     rsp, 58h
0x140042372  pop     r15
0x140042374  pop     r14
0x140042376  pop     r13
0x140042378  pop     r12
0x14004237a  pop     rdi
0x14004237b  pop     rsi
0x14004237c  pop     rbx
0x14004237d  pop     rbp
0x14004237e  retn
```
