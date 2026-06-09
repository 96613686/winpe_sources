# SepSddlDaclFromSDDLString

- ea: `0x140017c04`
- end: `0x140017ce1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140018214`

## callees

- `0x140017c04`
- `0x140017ce8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017cac`

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
      AclForString = SepSddlGetAclForString(v6 + 2, (const void **)&P, &v12);
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
0x140017c04  mov     rax, rsp
0x140017c07  mov     [rax+10h], rbx
0x140017c0b  mov     [rax+20h], rbp
0x140017c0f  push    rsi
0x140017c10  push    rdi
0x140017c11  push    r14
0x140017c13  sub     rsp, 20h
0x140017c17  xor     r14d, r14d
0x140017c1a  mov     rdi, r9
0x140017c1d  mov     [rax+8], r14
0x140017c21  mov     rsi, r8
0x140017c24  mov     [rax+18h], r14
0x140017c28  mov     [r9], r14
0x140017c2b  mov     [r8], r14d
0x140017c2e  jmp     short loc_140017C34
0x140017c30  add     rcx, 2
0x140017c34  movzx   eax, word ptr [rcx]
0x140017c37  cmp     ax, 20h ; ' '
0x140017c3b  jz      short loc_140017C30
0x140017c3d  cmp     ax, 44h ; 'D'
0x140017c41  jnz     loc_140017CC8
0x140017c47  lea     r9, [rcx+2]
0x140017c4b  cmp     word ptr [r9], 3Ah ; ':'
0x140017c50  jnz     short loc_140017CC8
0x140017c52  cmp     word ptr [r9+2], 50h ; 'P'
0x140017c58  lea     r8, [rsp+38h+arg_10]
0x140017c5d  mov     edx, 8
0x140017c62  mov     ebp, 1008h
0x140017c67  cmovnz  r9, rcx
0x140017c6b  cmovnz  ebp, edx
0x140017c6e  lea     rdx, [rsp+38h+P]; int
0x140017c73  lea     rcx, [r9+4]; Str1
0x140017c77  call    SepSddlGetAclForString
0x140017c7c  mov     ebx, eax
0x140017c7e  test    eax, eax
0x140017c80  jnz     short loc_140017CA0
0x140017c82  mov     rcx, [rsp+38h+arg_10]
0x140017c87  jmp     short loc_140017C8D
0x140017c89  lea     rcx, [rcx+2]
0x140017c8d  movzx   eax, word ptr [rcx]
0x140017c90  cmp     ax, 20h ; ' '
0x140017c94  jz      short loc_140017C89
0x140017c96  test    ax, ax
0x140017c99  jz      short loc_140017CBC
0x140017c9b  mov     ebx, 0C000000Dh
0x140017ca0  mov     rcx, [rsp+38h+P]; P
0x140017ca5  test    rcx, rcx
0x140017ca8  jz      short loc_140017CB8
0x140017caa  xor     edx, edx; Tag
0x140017cac  call    cs:__imp_ExFreePoolWithTag
0x140017cb3  nop     dword ptr [rax+rax+00h]
0x140017cb8  mov     eax, ebx
0x140017cba  jmp     short loc_140017CCD
0x140017cbc  mov     rax, [rsp+38h+P]
0x140017cc1  mov     [rdi], rax
0x140017cc4  mov     [rsi], ebp
0x140017cc6  jmp     short loc_140017CB8
0x140017cc8  mov     eax, 0C000000Dh
0x140017ccd  mov     rbx, [rsp+38h+arg_8]
0x140017cd2  mov     rbp, [rsp+38h+arg_18]
0x140017cd7  add     rsp, 20h
0x140017cdb  pop     r14
0x140017cdd  pop     rdi
0x140017cde  pop     rsi
0x140017cdf  retn
```
