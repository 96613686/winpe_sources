# SepSddlGetAclForString

- ea: `0x1400114b8`
- end: `0x14001186c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400113d4`

## callees

- `0x140003d80`
- `0x1400112e0`
- `0x1400114b8`
- `0x140011874`
- `0x14001192c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x1400114e3`
- `ntoskrnl!wcschr` at `0x1400114e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001159a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400115df`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001159a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400115df`
- `ntoskrnl!_wcsnicmp` at `0x14001167c`
- `ntoskrnl!_wcsnicmp` at `0x1400116f5`
- `ntoskrnl!_wcsnicmp` at `0x14001167c`
- `ntoskrnl!_wcsnicmp` at `0x1400116f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011834`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011834`

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
            if ( !_wcsnicmp(j, (&off_140009040)[v23], *((unsigned int *)&off_140009040 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_140009040 + 2 * v23 + 3);
              j += *((unsigned int *)&off_140009040 + 2 * v23 + 2);
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
0x1400114b8  push    rbp
0x1400114ba  push    rbx
0x1400114bb  push    rsi
0x1400114bc  push    rdi
0x1400114bd  push    r12
0x1400114bf  push    r13
0x1400114c1  push    r14
0x1400114c3  push    r15
0x1400114c5  mov     rbp, rsp
0x1400114c8  sub     rsp, 58h
0x1400114cc  xor     r15d, r15d
0x1400114cf  mov     r14, rdx
0x1400114d2  mov     [rdx], r15
0x1400114d5  mov     rbx, r8
0x1400114d8  mov     rsi, rcx
0x1400114db  mov     [rbp+var_18], r15
0x1400114df  lea     edx, [r15+3Ah]; Ch
0x1400114e3  call    cs:__imp_wcschr
0x1400114ea  nop     dword ptr [rax+rax+00h]
0x1400114ef  mov     [rbx], rax
0x1400114f2  cmp     rax, rsi
0x1400114f5  jnz     short loc_140011501
0x1400114f7  mov     eax, 0C000000Dh
0x1400114fc  jmp     loc_14001185A
0x140011501  mov     r8d, r15d
0x140011504  test    rax, rax
0x140011507  jnz     short loc_14001151D
0x140011509  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001150d  inc     rax
0x140011510  cmp     [rsi+rax*2], r15w
0x140011515  jnz     short loc_14001150D
0x140011517  lea     rax, [rsi+rax*2]
0x14001151b  jmp     short loc_140011521
0x14001151d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140011521  mov     [rbx], rax
0x140011524  mov     rcx, rsi
0x140011527  mov     r9d, r15d
0x14001152a  mov     r10d, 1
0x140011530  cmp     rsi, rax
0x140011533  jnb     short loc_140011554
0x140011535  movzx   edx, word ptr [rcx]
0x140011538  cmp     dx, 3Bh ; ';'
0x14001153c  jnz     short loc_140011543
0x14001153e  add     r8d, r10d
0x140011541  jmp     short loc_14001154B
0x140011543  cmp     dx, 20h ; ' '
0x140011547  cmovnz  r9d, r10d
0x14001154b  add     rcx, 2
0x14001154f  cmp     rcx, rax
0x140011552  jb      short loc_140011535
0x140011554  mov     eax, 0CCCCCCCDh
0x140011559  mul     r8d
0x14001155c  mov     r13d, edx
0x14001155f  shr     r13d, 2
0x140011563  lea     ecx, ds:0[r13*4]
0x14001156b  add     ecx, r13d
0x14001156e  cmp     r8d, ecx
0x140011571  jnz     loc_140011853
0x140011577  test    r8d, r8d
0x14001157a  jnz     short loc_140011585
0x14001157c  test    r9d, r9d
0x14001157f  jnz     loc_140011853
0x140011585  mov     ebx, r15d
0x140011588  mov     r8d, 6C416553h; Tag
0x14001158e  mov     ecx, r10d; PoolType
0x140011591  test    r13d, r13d
0x140011594  jnz     short loc_1400115BA
0x140011596  lea     edx, [r13+8]; NumberOfBytes
0x14001159a  call    cs:__imp_ExAllocatePoolWithTag
0x1400115a1  nop     dword ptr [rax+rax+00h]
0x1400115a6  mov     [r14], rax
0x1400115a9  test    rax, rax
0x1400115ac  jz      short loc_1400115F6
0x1400115ae  mov     qword ptr [rax], 80002h
0x1400115b5  jmp     loc_140011858
0x1400115ba  mov     eax, 0FFFFh
0x1400115bf  lea     r15d, ds:0[r13*2]
0x1400115c7  add     r15d, r13d
0x1400115ca  shl     r15d, 4
0x1400115ce  add     r15d, 8
0x1400115d2  cmp     r15d, eax
0x1400115d5  cmova   r15d, eax
0x1400115d9  mov     edx, r15d; NumberOfBytes
0x1400115dc  mov     r12d, r15d
0x1400115df  call    cs:__imp_ExAllocatePoolWithTag
0x1400115e6  nop     dword ptr [rax+rax+00h]
0x1400115eb  mov     [r14], rax
0x1400115ee  mov     rdi, rax
0x1400115f1  test    rax, rax
0x1400115f4  jnz     short loc_140011600
0x1400115f6  mov     ebx, 0C000009Ah
0x1400115fb  jmp     loc_140011858
0x140011600  mov     r8, r12; Size
0x140011603  mov     [rbp+arg_10], 8
0x14001160a  xor     edx, edx; Val
0x14001160c  mov     rcx, rdi; void *
0x14001160f  call    memset
0x140011614  xor     eax, eax
0x140011616  mov     word ptr [rdi], 2
0x14001161b  mov     [rdi+2], r15w
0x140011620  xor     r12d, r12d
0x140011623  mov     [rdi+4], eax
0x140011626  mov     r15d, 0C000000Dh
0x14001162c  mov     [rbp+arg_8], r12d
0x140011630  cmp     r12d, r13d
0x140011633  jnb     loc_14001182B
0x140011639  mov     [rbp+arg_0], 0
0x140011640  mov     r12w, 20h ; ' '
0x140011645  jmp     short loc_14001164B
0x140011647  add     rsi, 2
0x14001164b  movzx   eax, word ptr [rsi]
0x14001164e  cmp     ax, r12w
0x140011652  jz      short loc_140011647
0x140011654  cmp     ax, 28h ; '('
0x140011658  lea     rdi, [rsi+2]
0x14001165c  cmovnz  rdi, rsi
0x140011660  jmp     short loc_140011666
0x140011662  add     rdi, 2
0x140011666  cmp     [rdi], r12w
0x14001166a  jz      short loc_140011662
0x14001166c  mov     r8d, 1; MaxCount
0x140011672  lea     rdx, aA; "A"
0x140011679  mov     rcx, rdi; Str1
0x14001167c  call    cs:__imp__wcsnicmp
0x140011683  nop     dword ptr [rax+rax+00h]
0x140011688  test    eax, eax
0x14001168a  jnz     loc_140011823
0x140011690  add     rdi, 4
0x140011694  jmp     short loc_14001169A
0x140011696  add     rdi, 2
0x14001169a  movzx   eax, word ptr [rdi]
0x14001169d  cmp     ax, r12w
0x1400116a1  jz      short loc_140011696
0x1400116a3  cmp     ax, 3Bh ; ';'
0x1400116a7  jnz     loc_140011823
0x1400116ad  add     rdi, 2
0x1400116b1  cmp     [rdi], r12w
0x1400116b5  jz      short loc_1400116AD
0x1400116b7  lea     rcx, off_140009040; "RC"
0x1400116be  movzx   eax, word ptr [rdi]
0x1400116c1  cmp     ax, 3Bh ; ';'
0x1400116c5  jz      loc_140011757
0x1400116cb  cmp     ax, r12w
0x1400116cf  jnz     short loc_1400116DB
0x1400116d1  add     rdi, 2
0x1400116d5  cmp     [rdi], r12w
0x1400116d9  jz      short loc_1400116D1
0x1400116db  xor     esi, esi
0x1400116dd  cmp     esi, 8
0x1400116e0  jnb     short loc_14001172B
0x1400116e2  mov     r12d, esi
0x1400116e5  shl     r12, 4
0x1400116e9  mov     r8d, [r12+rcx+8]; MaxCount
0x1400116ee  mov     rdx, [r12+rcx]; Str2
0x1400116f2  mov     rcx, rdi; Str1
0x1400116f5  call    cs:__imp__wcsnicmp
0x1400116fc  nop     dword ptr [rax+rax+00h]
0x140011701  lea     rcx, off_140009040; "RC"
0x140011708  test    eax, eax
0x14001170a  jz      short loc_140011710
0x14001170c  inc     esi
0x14001170e  jmp     short loc_1400116DD
0x140011710  mov     eax, [rbp+arg_0]
0x140011713  or      eax, [r12+rcx+0Ch]
0x140011718  mov     [rbp+arg_0], eax
0x14001171b  mov     eax, [r12+rcx+8]
0x140011720  mov     r12w, 20h ; ' '
0x140011725  lea     rdi, [rdi+rax*2]
0x140011729  jmp     short loc_1400116BE
0x14001172b  lea     r8, [rbp+arg_0]
0x14001172f  mov     [rbp+arg_18], rdi
0x140011733  lea     rdx, [rbp+arg_18]
0x140011737  mov     rcx, rdi
0x14001173a  call    SepSddlParseWideStringUlong
0x14001173f  cmp     [rbp+arg_18], rdi
0x140011743  jz      loc_140011823
0x140011749  mov     rdi, [rbp+arg_18]
0x14001174d  mov     r12w, 20h ; ' '
0x140011752  jmp     loc_1400116B7
0x140011757  lea     rcx, [rdi+2]
0x14001175b  test    ebx, ebx
0x14001175d  jnz     loc_140011826
0x140011763  lea     edx, [rbx+2]
0x140011766  jmp     short loc_14001176C
0x140011768  add     rcx, 2
0x14001176c  movzx   eax, word ptr [rcx]
0x14001176f  cmp     ax, r12w
0x140011773  jz      short loc_140011768
0x140011775  cmp     ax, 3Bh ; ';'
0x140011779  cmovnz  ebx, r15d
0x14001177d  add     rcx, 2
0x140011781  sub     edx, 1
0x140011784  jnz     short loc_14001176C
0x140011786  test    ebx, ebx
0x140011788  jnz     loc_140011826
0x14001178e  jmp     short loc_140011794
0x140011790  add     rcx, 2; Str1
0x140011794  cmp     [rcx], r12w
0x140011798  jz      short loc_140011790
0x14001179a  lea     r8, [rbp+arg_18]
0x14001179e  mov     [rbp+arg_18], 0
0x1400117a6  lea     rdx, [rbp+var_18]
0x1400117aa  call    SepSddlGetSidForString
0x1400117af  mov     ebx, eax
0x1400117b1  test    eax, eax
0x1400117b3  jnz     short loc_14001182B
0x1400117b5  mov     rsi, [rbp+arg_18]
0x1400117b9  test    rsi, rsi
0x1400117bc  jnz     short loc_1400117C9
0x1400117be  mov     ebx, 0C0000077h
0x1400117c3  jmp     short loc_140011826
0x1400117c5  add     rsi, 2
0x1400117c9  movzx   eax, word ptr [rsi]
0x1400117cc  cmp     ax, r12w
0x1400117d0  jz      short loc_1400117C5
0x1400117d2  cmp     ax, 29h ; ')'
0x1400117d6  jnz     short loc_1400117BE
0x1400117d8  mov     rcx, [rbp+var_18]
0x1400117dc  mov     r12d, [rbp+arg_8]
0x1400117e0  test    rcx, rcx
0x1400117e3  jz      short loc_14001180D
0x1400117e5  mov     [rsp+58h+Sid], rcx; Sid
0x1400117ea  lea     rdx, [rbp+arg_10]; int
0x1400117ee  mov     eax, r13d
0x1400117f1  mov     rcx, r14; int
0x1400117f4  sub     eax, r12d
0x1400117f7  mov     [rsp+58h+var_30], eax; int
0x1400117fb  mov     eax, [rbp+arg_0]
0x1400117fe  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140011802  call    SepSddlAddAceToAcl
0x140011807  mov     ebx, eax
0x140011809  test    eax, eax
0x14001180b  jnz     short loc_140011826
0x14001180d  add     rsi, 2
0x140011811  cmp     word ptr [rsi], 28h ; '('
0x140011815  jnz     short loc_14001181B
0x140011817  add     rsi, 2
0x14001181b  inc     r12d
0x14001181e  jmp     loc_14001162C
0x140011823  mov     ebx, r15d
0x140011826  mov     rcx, [r14]
0x140011829  jmp     short loc_140011832
0x14001182b  mov     rcx, [r14]; P
0x14001182e  test    ebx, ebx
0x140011830  jz      short loc_140011849
0x140011832  xor     edx, edx; Tag
0x140011834  call    cs:__imp_ExFreePoolWithTag
0x14001183b  nop     dword ptr [rax+rax+00h]
0x140011840  mov     qword ptr [r14], 0
0x140011847  jmp     short loc_140011858
0x140011849  movzx   eax, word ptr [rbp+arg_10]
0x14001184d  mov     [rcx+2], ax
0x140011851  jmp     short loc_140011858
0x140011853  mov     ebx, 0C000000Dh
0x140011858  mov     eax, ebx
0x14001185a  add     rsp, 58h
0x14001185e  pop     r15
0x140011860  pop     r14
0x140011862  pop     r13
0x140011864  pop     r12
0x140011866  pop     rdi
0x140011867  pop     rsi
0x140011868  pop     rbx
0x140011869  pop     rbp
0x14001186a  retn
```
