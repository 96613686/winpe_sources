# SepSddlDaclFromSDDLString

- ea: `0x1400113d4`
- end: `0x1400114b1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400119f4`

## callees

- `0x1400113d4`
- `0x1400114b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001147c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001147c`

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
0x1400113d4  mov     rax, rsp
0x1400113d7  mov     [rax+10h], rbx
0x1400113db  mov     [rax+20h], rbp
0x1400113df  push    rsi
0x1400113e0  push    rdi
0x1400113e1  push    r14
0x1400113e3  sub     rsp, 20h
0x1400113e7  xor     r14d, r14d
0x1400113ea  mov     rdi, r9
0x1400113ed  mov     [rax+8], r14
0x1400113f1  mov     rsi, r8
0x1400113f4  mov     [rax+18h], r14
0x1400113f8  mov     [r9], r14
0x1400113fb  mov     [r8], r14d
0x1400113fe  jmp     short loc_140011404
0x140011400  add     rcx, 2
0x140011404  movzx   eax, word ptr [rcx]
0x140011407  cmp     ax, 20h ; ' '
0x14001140b  jz      short loc_140011400
0x14001140d  cmp     ax, 44h ; 'D'
0x140011411  jnz     loc_140011498
0x140011417  lea     r9, [rcx+2]
0x14001141b  cmp     word ptr [r9], 3Ah ; ':'
0x140011420  jnz     short loc_140011498
0x140011422  cmp     word ptr [r9+2], 50h ; 'P'
0x140011428  lea     r8, [rsp+38h+arg_10]
0x14001142d  mov     edx, 8
0x140011432  mov     ebp, 1008h
0x140011437  cmovnz  r9, rcx
0x14001143b  cmovnz  ebp, edx
0x14001143e  lea     rdx, [rsp+38h+P]; int
0x140011443  lea     rcx, [r9+4]; Str1
0x140011447  call    SepSddlGetAclForString
0x14001144c  mov     ebx, eax
0x14001144e  test    eax, eax
0x140011450  jnz     short loc_140011470
0x140011452  mov     rcx, [rsp+38h+arg_10]
0x140011457  jmp     short loc_14001145D
0x140011459  lea     rcx, [rcx+2]
0x14001145d  movzx   eax, word ptr [rcx]
0x140011460  cmp     ax, 20h ; ' '
0x140011464  jz      short loc_140011459
0x140011466  test    ax, ax
0x140011469  jz      short loc_14001148C
0x14001146b  mov     ebx, 0C000000Dh
0x140011470  mov     rcx, [rsp+38h+P]; P
0x140011475  test    rcx, rcx
0x140011478  jz      short loc_140011488
0x14001147a  xor     edx, edx; Tag
0x14001147c  call    cs:__imp_ExFreePoolWithTag
0x140011483  nop     dword ptr [rax+rax+00h]
0x140011488  mov     eax, ebx
0x14001148a  jmp     short loc_14001149D
0x14001148c  mov     rax, [rsp+38h+P]
0x140011491  mov     [rdi], rax
0x140011494  mov     [rsi], ebp
0x140011496  jmp     short loc_140011488
0x140011498  mov     eax, 0C000000Dh
0x14001149d  mov     rbx, [rsp+38h+arg_8]
0x1400114a2  mov     rbp, [rsp+38h+arg_18]
0x1400114a7  add     rsp, 20h
0x1400114ab  pop     r14
0x1400114ad  pop     rdi
0x1400114ae  pop     rsi
0x1400114af  retn
```
