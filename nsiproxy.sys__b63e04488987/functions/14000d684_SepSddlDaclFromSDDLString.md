# SepSddlDaclFromSDDLString

- ea: `0x14000d684`
- end: `0x14000d761`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000dca4`

## callees

- `0x14000d684`
- `0x14000d768`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d72c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d72c`

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
0x14000d684  mov     rax, rsp
0x14000d687  mov     [rax+10h], rbx
0x14000d68b  mov     [rax+20h], rbp
0x14000d68f  push    rsi
0x14000d690  push    rdi
0x14000d691  push    r14
0x14000d693  sub     rsp, 20h
0x14000d697  xor     r14d, r14d
0x14000d69a  mov     rdi, r9
0x14000d69d  mov     [rax+8], r14
0x14000d6a1  mov     rsi, r8
0x14000d6a4  mov     [rax+18h], r14
0x14000d6a8  mov     [r9], r14
0x14000d6ab  mov     [r8], r14d
0x14000d6ae  jmp     short loc_14000D6B4
0x14000d6b0  add     rcx, 2
0x14000d6b4  movzx   eax, word ptr [rcx]
0x14000d6b7  cmp     ax, 20h ; ' '
0x14000d6bb  jz      short loc_14000D6B0
0x14000d6bd  cmp     ax, 44h ; 'D'
0x14000d6c1  jnz     loc_14000D748
0x14000d6c7  lea     r9, [rcx+2]
0x14000d6cb  cmp     word ptr [r9], 3Ah ; ':'
0x14000d6d0  jnz     short loc_14000D748
0x14000d6d2  cmp     word ptr [r9+2], 50h ; 'P'
0x14000d6d8  lea     r8, [rsp+38h+arg_10]
0x14000d6dd  mov     edx, 8
0x14000d6e2  mov     ebp, 1008h
0x14000d6e7  cmovnz  r9, rcx
0x14000d6eb  cmovnz  ebp, edx
0x14000d6ee  lea     rdx, [rsp+38h+P]; int
0x14000d6f3  lea     rcx, [r9+4]; Str1
0x14000d6f7  call    SepSddlGetAclForString
0x14000d6fc  mov     ebx, eax
0x14000d6fe  test    eax, eax
0x14000d700  jnz     short loc_14000D720
0x14000d702  mov     rcx, [rsp+38h+arg_10]
0x14000d707  jmp     short loc_14000D70D
0x14000d709  lea     rcx, [rcx+2]
0x14000d70d  movzx   eax, word ptr [rcx]
0x14000d710  cmp     ax, 20h ; ' '
0x14000d714  jz      short loc_14000D709
0x14000d716  test    ax, ax
0x14000d719  jz      short loc_14000D73C
0x14000d71b  mov     ebx, 0C000000Dh
0x14000d720  mov     rcx, [rsp+38h+P]; P
0x14000d725  test    rcx, rcx
0x14000d728  jz      short loc_14000D738
0x14000d72a  xor     edx, edx; Tag
0x14000d72c  call    cs:__imp_ExFreePoolWithTag
0x14000d733  nop     dword ptr [rax+rax+00h]
0x14000d738  mov     eax, ebx
0x14000d73a  jmp     short loc_14000D74D
0x14000d73c  mov     rax, [rsp+38h+P]
0x14000d741  mov     [rdi], rax
0x14000d744  mov     [rsi], ebp
0x14000d746  jmp     short loc_14000D738
0x14000d748  mov     eax, 0C000000Dh
0x14000d74d  mov     rbx, [rsp+38h+arg_8]
0x14000d752  mov     rbp, [rsp+38h+arg_18]
0x14000d757  add     rsp, 20h
0x14000d75b  pop     r14
0x14000d75d  pop     rdi
0x14000d75e  pop     rsi
0x14000d75f  retn
```
