# SepSddlDaclFromSDDLString

- ea: `0x140021344`
- end: `0x140021421`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002194c`

## callees

- `0x140021344`
- `0x140021428`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400213ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400213ec`

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
0x140021344  mov     rax, rsp
0x140021347  mov     [rax+10h], rbx
0x14002134b  mov     [rax+20h], rbp
0x14002134f  push    rsi
0x140021350  push    rdi
0x140021351  push    r14
0x140021353  sub     rsp, 20h
0x140021357  xor     r14d, r14d
0x14002135a  mov     rdi, r9
0x14002135d  mov     [rax+8], r14
0x140021361  mov     rsi, r8
0x140021364  mov     [rax+18h], r14
0x140021368  mov     [r9], r14
0x14002136b  mov     [r8], r14d
0x14002136e  jmp     short loc_140021374
0x140021370  add     rcx, 2
0x140021374  movzx   eax, word ptr [rcx]
0x140021377  cmp     ax, 20h ; ' '
0x14002137b  jz      short loc_140021370
0x14002137d  cmp     ax, 44h ; 'D'
0x140021381  jnz     loc_140021408
0x140021387  lea     r9, [rcx+2]
0x14002138b  cmp     word ptr [r9], 3Ah ; ':'
0x140021390  jnz     short loc_140021408
0x140021392  cmp     word ptr [r9+2], 50h ; 'P'
0x140021398  lea     r8, [rsp+38h+arg_10]
0x14002139d  mov     edx, 8
0x1400213a2  mov     ebp, 1008h
0x1400213a7  cmovnz  r9, rcx
0x1400213ab  cmovnz  ebp, edx
0x1400213ae  lea     rdx, [rsp+38h+P]; int
0x1400213b3  lea     rcx, [r9+4]; Str1
0x1400213b7  call    SepSddlGetAclForString
0x1400213bc  mov     ebx, eax
0x1400213be  test    eax, eax
0x1400213c0  jnz     short loc_1400213E0
0x1400213c2  mov     rcx, [rsp+38h+arg_10]
0x1400213c7  jmp     short loc_1400213CD
0x1400213c9  lea     rcx, [rcx+2]
0x1400213cd  movzx   eax, word ptr [rcx]
0x1400213d0  cmp     ax, 20h ; ' '
0x1400213d4  jz      short loc_1400213C9
0x1400213d6  test    ax, ax
0x1400213d9  jz      short loc_1400213FC
0x1400213db  mov     ebx, 0C000000Dh
0x1400213e0  mov     rcx, [rsp+38h+P]; P
0x1400213e5  test    rcx, rcx
0x1400213e8  jz      short loc_1400213F8
0x1400213ea  xor     edx, edx; Tag
0x1400213ec  call    cs:__imp_ExFreePoolWithTag
0x1400213f3  nop     dword ptr [rax+rax+00h]
0x1400213f8  mov     eax, ebx
0x1400213fa  jmp     short loc_14002140D
0x1400213fc  mov     rax, [rsp+38h+P]
0x140021401  mov     [rdi], rax
0x140021404  mov     [rsi], ebp
0x140021406  jmp     short loc_1400213F8
0x140021408  mov     eax, 0C000000Dh
0x14002140d  mov     rbx, [rsp+38h+arg_8]
0x140021412  mov     rbp, [rsp+38h+arg_18]
0x140021417  add     rsp, 20h
0x14002141b  pop     r14
0x14002141d  pop     rdi
0x14002141e  pop     rsi
0x14002141f  retn
```
