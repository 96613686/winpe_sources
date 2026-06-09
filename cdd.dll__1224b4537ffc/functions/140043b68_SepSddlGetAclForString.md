# SepSddlGetAclForString

- ea: `0x140043b68`
- end: `0x140043f1c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140043a84`

## callees

- `0x140037640`
- `0x140043990`
- `0x140043b68`
- `0x140043f24`
- `0x140043fdc`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x140043d2c`
- `ntoskrnl!_wcsnicmp` at `0x140043da5`
- `ntoskrnl!_wcsnicmp` at `0x140043d2c`
- `ntoskrnl!_wcsnicmp` at `0x140043da5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043c4a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043c8f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043c4a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043c8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043ee4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043ee4`
- `ntoskrnl!wcschr` at `0x140043b93`
- `ntoskrnl!wcschr` at `0x140043b93`

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
            if ( !_wcsnicmp(j, (&off_14003E270)[v23], *((unsigned int *)&off_14003E270 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_14003E270 + 2 * v23 + 3);
              j += *((unsigned int *)&off_14003E270 + 2 * v23 + 2);
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
0x140043b68  push    rbp
0x140043b6a  push    rbx
0x140043b6b  push    rsi
0x140043b6c  push    rdi
0x140043b6d  push    r12
0x140043b6f  push    r13
0x140043b71  push    r14
0x140043b73  push    r15
0x140043b75  mov     rbp, rsp
0x140043b78  sub     rsp, 58h
0x140043b7c  xor     r15d, r15d
0x140043b7f  mov     r14, rdx
0x140043b82  mov     [rdx], r15
0x140043b85  mov     rbx, r8
0x140043b88  mov     rsi, rcx
0x140043b8b  mov     [rbp+var_18], r15
0x140043b8f  lea     edx, [r15+3Ah]; Ch
0x140043b93  call    cs:__imp_wcschr
0x140043b9a  nop     dword ptr [rax+rax+00h]
0x140043b9f  mov     [rbx], rax
0x140043ba2  cmp     rax, rsi
0x140043ba5  jnz     short loc_140043BB1
0x140043ba7  mov     eax, 0C000000Dh
0x140043bac  jmp     loc_140043F0A
0x140043bb1  mov     r8d, r15d
0x140043bb4  test    rax, rax
0x140043bb7  jnz     short loc_140043BCD
0x140043bb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x140043bbd  inc     rax
0x140043bc0  cmp     [rsi+rax*2], r15w
0x140043bc5  jnz     short loc_140043BBD
0x140043bc7  lea     rax, [rsi+rax*2]
0x140043bcb  jmp     short loc_140043BD1
0x140043bcd  add     rax, 0FFFFFFFFFFFFFFFEh
0x140043bd1  mov     [rbx], rax
0x140043bd4  mov     rcx, rsi
0x140043bd7  mov     r9d, r15d
0x140043bda  mov     r10d, 1
0x140043be0  cmp     rsi, rax
0x140043be3  jnb     short loc_140043C04
0x140043be5  movzx   edx, word ptr [rcx]
0x140043be8  cmp     dx, 3Bh ; ';'
0x140043bec  jnz     short loc_140043BF3
0x140043bee  add     r8d, r10d
0x140043bf1  jmp     short loc_140043BFB
0x140043bf3  cmp     dx, 20h ; ' '
0x140043bf7  cmovnz  r9d, r10d
0x140043bfb  add     rcx, 2
0x140043bff  cmp     rcx, rax
0x140043c02  jb      short loc_140043BE5
0x140043c04  mov     eax, 0CCCCCCCDh
0x140043c09  mul     r8d
0x140043c0c  mov     r13d, edx
0x140043c0f  shr     r13d, 2
0x140043c13  lea     ecx, ds:0[r13*4]
0x140043c1b  add     ecx, r13d
0x140043c1e  cmp     r8d, ecx
0x140043c21  jnz     loc_140043F03
0x140043c27  test    r8d, r8d
0x140043c2a  jnz     short loc_140043C35
0x140043c2c  test    r9d, r9d
0x140043c2f  jnz     loc_140043F03
0x140043c35  mov     ebx, r15d
0x140043c38  mov     r8d, 6C416553h; Tag
0x140043c3e  mov     ecx, r10d; PoolType
0x140043c41  test    r13d, r13d
0x140043c44  jnz     short loc_140043C6A
0x140043c46  lea     edx, [r13+8]; NumberOfBytes
0x140043c4a  call    cs:__imp_ExAllocatePoolWithTag
0x140043c51  nop     dword ptr [rax+rax+00h]
0x140043c56  mov     [r14], rax
0x140043c59  test    rax, rax
0x140043c5c  jz      short loc_140043CA6
0x140043c5e  mov     qword ptr [rax], 80002h
0x140043c65  jmp     loc_140043F08
0x140043c6a  mov     eax, 0FFFFh
0x140043c6f  lea     r15d, ds:0[r13*2]
0x140043c77  add     r15d, r13d
0x140043c7a  shl     r15d, 4
0x140043c7e  add     r15d, 8
0x140043c82  cmp     r15d, eax
0x140043c85  cmova   r15d, eax
0x140043c89  mov     edx, r15d; NumberOfBytes
0x140043c8c  mov     r12d, r15d
0x140043c8f  call    cs:__imp_ExAllocatePoolWithTag
0x140043c96  nop     dword ptr [rax+rax+00h]
0x140043c9b  mov     [r14], rax
0x140043c9e  mov     rdi, rax
0x140043ca1  test    rax, rax
0x140043ca4  jnz     short loc_140043CB0
0x140043ca6  mov     ebx, 0C000009Ah
0x140043cab  jmp     loc_140043F08
0x140043cb0  mov     r8, r12; Size
0x140043cb3  mov     [rbp+arg_10], 8
0x140043cba  xor     edx, edx; Val
0x140043cbc  mov     rcx, rdi; void *
0x140043cbf  call    memset
0x140043cc4  xor     eax, eax
0x140043cc6  mov     word ptr [rdi], 2
0x140043ccb  mov     [rdi+2], r15w
0x140043cd0  xor     r12d, r12d
0x140043cd3  mov     [rdi+4], eax
0x140043cd6  mov     r15d, 0C000000Dh
0x140043cdc  mov     [rbp+arg_8], r12d
0x140043ce0  cmp     r12d, r13d
0x140043ce3  jnb     loc_140043EDB
0x140043ce9  mov     [rbp+arg_0], 0
0x140043cf0  mov     r12w, 20h ; ' '
0x140043cf5  jmp     short loc_140043CFB
0x140043cf7  add     rsi, 2
0x140043cfb  movzx   eax, word ptr [rsi]
0x140043cfe  cmp     ax, r12w
0x140043d02  jz      short loc_140043CF7
0x140043d04  cmp     ax, 28h ; '('
0x140043d08  lea     rdi, [rsi+2]
0x140043d0c  cmovnz  rdi, rsi
0x140043d10  jmp     short loc_140043D16
0x140043d12  add     rdi, 2
0x140043d16  cmp     [rdi], r12w
0x140043d1a  jz      short loc_140043D12
0x140043d1c  mov     r8d, 1; MaxCount
0x140043d22  lea     rdx, aA; "A"
0x140043d29  mov     rcx, rdi; Str1
0x140043d2c  call    cs:__imp__wcsnicmp
0x140043d33  nop     dword ptr [rax+rax+00h]
0x140043d38  test    eax, eax
0x140043d3a  jnz     loc_140043ED3
0x140043d40  add     rdi, 4
0x140043d44  jmp     short loc_140043D4A
0x140043d46  add     rdi, 2
0x140043d4a  movzx   eax, word ptr [rdi]
0x140043d4d  cmp     ax, r12w
0x140043d51  jz      short loc_140043D46
0x140043d53  cmp     ax, 3Bh ; ';'
0x140043d57  jnz     loc_140043ED3
0x140043d5d  add     rdi, 2
0x140043d61  cmp     [rdi], r12w
0x140043d65  jz      short loc_140043D5D
0x140043d67  lea     rcx, off_14003E270; "RC"
0x140043d6e  movzx   eax, word ptr [rdi]
0x140043d71  cmp     ax, 3Bh ; ';'
0x140043d75  jz      loc_140043E07
0x140043d7b  cmp     ax, r12w
0x140043d7f  jnz     short loc_140043D8B
0x140043d81  add     rdi, 2
0x140043d85  cmp     [rdi], r12w
0x140043d89  jz      short loc_140043D81
0x140043d8b  xor     esi, esi
0x140043d8d  cmp     esi, 8
0x140043d90  jnb     short loc_140043DDB
0x140043d92  mov     r12d, esi
0x140043d95  shl     r12, 4
0x140043d99  mov     r8d, [r12+rcx+8]; MaxCount
0x140043d9e  mov     rdx, [r12+rcx]; Str2
0x140043da2  mov     rcx, rdi; Str1
0x140043da5  call    cs:__imp__wcsnicmp
0x140043dac  nop     dword ptr [rax+rax+00h]
0x140043db1  lea     rcx, off_14003E270; "RC"
0x140043db8  test    eax, eax
0x140043dba  jz      short loc_140043DC0
0x140043dbc  inc     esi
0x140043dbe  jmp     short loc_140043D8D
0x140043dc0  mov     eax, [rbp+arg_0]
0x140043dc3  or      eax, [r12+rcx+0Ch]
0x140043dc8  mov     [rbp+arg_0], eax
0x140043dcb  mov     eax, [r12+rcx+8]
0x140043dd0  mov     r12w, 20h ; ' '
0x140043dd5  lea     rdi, [rdi+rax*2]
0x140043dd9  jmp     short loc_140043D6E
0x140043ddb  lea     r8, [rbp+arg_0]
0x140043ddf  mov     [rbp+arg_18], rdi
0x140043de3  lea     rdx, [rbp+arg_18]
0x140043de7  mov     rcx, rdi
0x140043dea  call    SepSddlParseWideStringUlong
0x140043def  cmp     [rbp+arg_18], rdi
0x140043df3  jz      loc_140043ED3
0x140043df9  mov     rdi, [rbp+arg_18]
0x140043dfd  mov     r12w, 20h ; ' '
0x140043e02  jmp     loc_140043D67
0x140043e07  lea     rcx, [rdi+2]
0x140043e0b  test    ebx, ebx
0x140043e0d  jnz     loc_140043ED6
0x140043e13  lea     edx, [rbx+2]
0x140043e16  jmp     short loc_140043E1C
0x140043e18  add     rcx, 2
0x140043e1c  movzx   eax, word ptr [rcx]
0x140043e1f  cmp     ax, r12w
0x140043e23  jz      short loc_140043E18
0x140043e25  cmp     ax, 3Bh ; ';'
0x140043e29  cmovnz  ebx, r15d
0x140043e2d  add     rcx, 2
0x140043e31  sub     edx, 1
0x140043e34  jnz     short loc_140043E1C
0x140043e36  test    ebx, ebx
0x140043e38  jnz     loc_140043ED6
0x140043e3e  jmp     short loc_140043E44
0x140043e40  add     rcx, 2; Str1
0x140043e44  cmp     [rcx], r12w
0x140043e48  jz      short loc_140043E40
0x140043e4a  lea     r8, [rbp+arg_18]
0x140043e4e  mov     [rbp+arg_18], 0
0x140043e56  lea     rdx, [rbp+var_18]
0x140043e5a  call    SepSddlGetSidForString
0x140043e5f  mov     ebx, eax
0x140043e61  test    eax, eax
0x140043e63  jnz     short loc_140043EDB
0x140043e65  mov     rsi, [rbp+arg_18]
0x140043e69  test    rsi, rsi
0x140043e6c  jnz     short loc_140043E79
0x140043e6e  mov     ebx, 0C0000077h
0x140043e73  jmp     short loc_140043ED6
0x140043e75  add     rsi, 2
0x140043e79  movzx   eax, word ptr [rsi]
0x140043e7c  cmp     ax, r12w
0x140043e80  jz      short loc_140043E75
0x140043e82  cmp     ax, 29h ; ')'
0x140043e86  jnz     short loc_140043E6E
0x140043e88  mov     rcx, [rbp+var_18]
0x140043e8c  mov     r12d, [rbp+arg_8]
0x140043e90  test    rcx, rcx
0x140043e93  jz      short loc_140043EBD
0x140043e95  mov     [rsp+58h+Sid], rcx; Sid
0x140043e9a  lea     rdx, [rbp+arg_10]; int
0x140043e9e  mov     eax, r13d
0x140043ea1  mov     rcx, r14; int
0x140043ea4  sub     eax, r12d
0x140043ea7  mov     [rsp+58h+var_30], eax; int
0x140043eab  mov     eax, [rbp+arg_0]
0x140043eae  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140043eb2  call    SepSddlAddAceToAcl
0x140043eb7  mov     ebx, eax
0x140043eb9  test    eax, eax
0x140043ebb  jnz     short loc_140043ED6
0x140043ebd  add     rsi, 2
0x140043ec1  cmp     word ptr [rsi], 28h ; '('
0x140043ec5  jnz     short loc_140043ECB
0x140043ec7  add     rsi, 2
0x140043ecb  inc     r12d
0x140043ece  jmp     loc_140043CDC
0x140043ed3  mov     ebx, r15d
0x140043ed6  mov     rcx, [r14]
0x140043ed9  jmp     short loc_140043EE2
0x140043edb  mov     rcx, [r14]; P
0x140043ede  test    ebx, ebx
0x140043ee0  jz      short loc_140043EF9
0x140043ee2  xor     edx, edx; Tag
0x140043ee4  call    cs:__imp_ExFreePoolWithTag
0x140043eeb  nop     dword ptr [rax+rax+00h]
0x140043ef0  mov     qword ptr [r14], 0
0x140043ef7  jmp     short loc_140043F08
0x140043ef9  movzx   eax, word ptr [rbp+arg_10]
0x140043efd  mov     [rcx+2], ax
0x140043f01  jmp     short loc_140043F08
0x140043f03  mov     ebx, 0C000000Dh
0x140043f08  mov     eax, ebx
0x140043f0a  add     rsp, 58h
0x140043f0e  pop     r15
0x140043f10  pop     r14
0x140043f12  pop     r13
0x140043f14  pop     r12
0x140043f16  pop     rdi
0x140043f17  pop     rsi
0x140043f18  pop     rbx
0x140043f19  pop     rbp
0x140043f1a  retn
```
