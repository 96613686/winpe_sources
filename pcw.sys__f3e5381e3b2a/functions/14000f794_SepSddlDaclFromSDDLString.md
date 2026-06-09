# SepSddlDaclFromSDDLString

- ea: `0x14000f794`
- end: `0x14000f871`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000fdc4`

## callees

- `0x14000f794`
- `0x14000f878`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f83c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f83c`

## pseudocode

```c
__int64 __fastcall SepSddlDaclFromSDDLString(_WORD *a1, __int64 a2, int *a3, PVOID *a4)
{
  _WORD *v6; // r9
  int v7; // ebp
  unsigned int AclForString; // ebx
  wchar_t *i; // rcx
  PVOID P; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *v12; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  v12 = 0;
  *a4 = 0;
  *a3 = 0;
  while ( *a1 == 32 )
    ++a1;
  if ( *a1 == 68 )
  {
    v6 = a1 + 1;
    if ( a1[1] == 58 )
    {
      v7 = 4104;
      if ( a1[2] != 80 )
      {
        v6 = a1;
        v7 = 8;
      }
      AclForString = SepSddlGetAclForString(v6 + 2, &P, &v12);
      if ( !AclForString )
      {
        for ( i = v12; *i == 32; ++i )
          ;
        if ( !*i )
        {
          *a4 = P;
          *a3 = v7;
          return AclForString;
        }
        AclForString = -1073741811;
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      return AclForString;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14000f794  mov     rax, rsp
0x14000f797  mov     [rax+10h], rbx
0x14000f79b  mov     [rax+20h], rbp
0x14000f79f  push    rsi
0x14000f7a0  push    rdi
0x14000f7a1  push    r14
0x14000f7a3  sub     rsp, 20h
0x14000f7a7  xor     r14d, r14d
0x14000f7aa  mov     rdi, r9
0x14000f7ad  mov     [rax+8], r14
0x14000f7b1  mov     rsi, r8
0x14000f7b4  mov     [rax+18h], r14
0x14000f7b8  mov     [r9], r14
0x14000f7bb  mov     [r8], r14d
0x14000f7be  jmp     short loc_14000F7C4
0x14000f7c0  add     rcx, 2
0x14000f7c4  movzx   eax, word ptr [rcx]
0x14000f7c7  cmp     ax, 20h ; ' '
0x14000f7cb  jz      short loc_14000F7C0
0x14000f7cd  cmp     ax, 44h ; 'D'
0x14000f7d1  jnz     loc_14000F858
0x14000f7d7  lea     r9, [rcx+2]
0x14000f7db  cmp     word ptr [r9], 3Ah ; ':'
0x14000f7e0  jnz     short loc_14000F858
0x14000f7e2  cmp     word ptr [r9+2], 50h ; 'P'
0x14000f7e8  lea     r8, [rsp+38h+arg_10]
0x14000f7ed  mov     edx, 8
0x14000f7f2  mov     ebp, 1008h
0x14000f7f7  cmovnz  r9, rcx
0x14000f7fb  cmovnz  ebp, edx
0x14000f7fe  lea     rdx, [rsp+38h+P]; int
0x14000f803  lea     rcx, [r9+4]; Str1
0x14000f807  call    SepSddlGetAclForString
0x14000f80c  mov     ebx, eax
0x14000f80e  test    eax, eax
0x14000f810  jnz     short loc_14000F830
0x14000f812  mov     rcx, [rsp+38h+arg_10]
0x14000f817  jmp     short loc_14000F81D
0x14000f819  lea     rcx, [rcx+2]
0x14000f81d  movzx   eax, word ptr [rcx]
0x14000f820  cmp     ax, 20h ; ' '
0x14000f824  jz      short loc_14000F819
0x14000f826  test    ax, ax
0x14000f829  jz      short loc_14000F84C
0x14000f82b  mov     ebx, 0C000000Dh
0x14000f830  mov     rcx, [rsp+38h+P]; P
0x14000f835  test    rcx, rcx
0x14000f838  jz      short loc_14000F848
0x14000f83a  xor     edx, edx; Tag
0x14000f83c  call    cs:__imp_ExFreePoolWithTag
0x14000f843  nop     dword ptr [rax+rax+00h]
0x14000f848  mov     eax, ebx
0x14000f84a  jmp     short loc_14000F85D
0x14000f84c  mov     rax, [rsp+38h+P]
0x14000f851  mov     [rdi], rax
0x14000f854  mov     [rsi], ebp
0x14000f856  jmp     short loc_14000F848
0x14000f858  mov     eax, 0C000000Dh
0x14000f85d  mov     rbx, [rsp+38h+arg_8]
0x14000f862  mov     rbp, [rsp+38h+arg_18]
0x14000f867  add     rsp, 20h
0x14000f86b  pop     r14
0x14000f86d  pop     rdi
0x14000f86e  pop     rsi
0x14000f86f  retn
```
