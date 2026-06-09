# SepSddlDaclFromSDDLString

- ea: `0x140043a84`
- end: `0x140043b61`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400440a4`

## callees

- `0x140043a84`
- `0x140043b68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043b2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043b2c`

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
0x140043a84  mov     rax, rsp
0x140043a87  mov     [rax+10h], rbx
0x140043a8b  mov     [rax+20h], rbp
0x140043a8f  push    rsi
0x140043a90  push    rdi
0x140043a91  push    r14
0x140043a93  sub     rsp, 20h
0x140043a97  xor     r14d, r14d
0x140043a9a  mov     rdi, r9
0x140043a9d  mov     [rax+8], r14
0x140043aa1  mov     rsi, r8
0x140043aa4  mov     [rax+18h], r14
0x140043aa8  mov     [r9], r14
0x140043aab  mov     [r8], r14d
0x140043aae  jmp     short loc_140043AB4
0x140043ab0  add     rcx, 2
0x140043ab4  movzx   eax, word ptr [rcx]
0x140043ab7  cmp     ax, 20h ; ' '
0x140043abb  jz      short loc_140043AB0
0x140043abd  cmp     ax, 44h ; 'D'
0x140043ac1  jnz     loc_140043B48
0x140043ac7  lea     r9, [rcx+2]
0x140043acb  cmp     word ptr [r9], 3Ah ; ':'
0x140043ad0  jnz     short loc_140043B48
0x140043ad2  cmp     word ptr [r9+2], 50h ; 'P'
0x140043ad8  lea     r8, [rsp+38h+arg_10]
0x140043add  mov     edx, 8
0x140043ae2  mov     ebp, 1008h
0x140043ae7  cmovnz  r9, rcx
0x140043aeb  cmovnz  ebp, edx
0x140043aee  lea     rdx, [rsp+38h+P]; int
0x140043af3  lea     rcx, [r9+4]; Str1
0x140043af7  call    SepSddlGetAclForString
0x140043afc  mov     ebx, eax
0x140043afe  test    eax, eax
0x140043b00  jnz     short loc_140043B20
0x140043b02  mov     rcx, [rsp+38h+arg_10]
0x140043b07  jmp     short loc_140043B0D
0x140043b09  lea     rcx, [rcx+2]
0x140043b0d  movzx   eax, word ptr [rcx]
0x140043b10  cmp     ax, 20h ; ' '
0x140043b14  jz      short loc_140043B09
0x140043b16  test    ax, ax
0x140043b19  jz      short loc_140043B3C
0x140043b1b  mov     ebx, 0C000000Dh
0x140043b20  mov     rcx, [rsp+38h+P]; P
0x140043b25  test    rcx, rcx
0x140043b28  jz      short loc_140043B38
0x140043b2a  xor     edx, edx; Tag
0x140043b2c  call    cs:__imp_ExFreePoolWithTag
0x140043b33  nop     dword ptr [rax+rax+00h]
0x140043b38  mov     eax, ebx
0x140043b3a  jmp     short loc_140043B4D
0x140043b3c  mov     rax, [rsp+38h+P]
0x140043b41  mov     [rdi], rax
0x140043b44  mov     [rsi], ebp
0x140043b46  jmp     short loc_140043B38
0x140043b48  mov     eax, 0C000000Dh
0x140043b4d  mov     rbx, [rsp+38h+arg_8]
0x140043b52  mov     rbp, [rsp+38h+arg_18]
0x140043b57  add     rsp, 20h
0x140043b5b  pop     r14
0x140043b5d  pop     rdi
0x140043b5e  pop     rsi
0x140043b5f  retn
```
