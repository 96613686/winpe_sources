# SepSddlDaclFromSDDLString

- ea: `0x140045d44`
- end: `0x140045e21`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140046364`

## callees

- `0x140045d44`
- `0x140045e28`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140045dec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045dec`

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
0x140045d44  mov     rax, rsp
0x140045d47  mov     [rax+10h], rbx
0x140045d4b  mov     [rax+20h], rbp
0x140045d4f  push    rsi
0x140045d50  push    rdi
0x140045d51  push    r14
0x140045d53  sub     rsp, 20h
0x140045d57  xor     r14d, r14d
0x140045d5a  mov     rdi, r9
0x140045d5d  mov     [rax+8], r14
0x140045d61  mov     rsi, r8
0x140045d64  mov     [rax+18h], r14
0x140045d68  mov     [r9], r14
0x140045d6b  mov     [r8], r14d
0x140045d6e  jmp     short loc_140045D74
0x140045d70  add     rcx, 2
0x140045d74  movzx   eax, word ptr [rcx]
0x140045d77  cmp     ax, 20h ; ' '
0x140045d7b  jz      short loc_140045D70
0x140045d7d  cmp     ax, 44h ; 'D'
0x140045d81  jnz     loc_140045E08
0x140045d87  lea     r9, [rcx+2]
0x140045d8b  cmp     word ptr [r9], 3Ah ; ':'
0x140045d90  jnz     short loc_140045E08
0x140045d92  cmp     word ptr [r9+2], 50h ; 'P'
0x140045d98  lea     r8, [rsp+38h+arg_10]
0x140045d9d  mov     edx, 8
0x140045da2  mov     ebp, 1008h
0x140045da7  cmovnz  r9, rcx
0x140045dab  cmovnz  ebp, edx
0x140045dae  lea     rdx, [rsp+38h+P]; int
0x140045db3  lea     rcx, [r9+4]; Str1
0x140045db7  call    SepSddlGetAclForString
0x140045dbc  mov     ebx, eax
0x140045dbe  test    eax, eax
0x140045dc0  jnz     short loc_140045DE0
0x140045dc2  mov     rcx, [rsp+38h+arg_10]
0x140045dc7  jmp     short loc_140045DCD
0x140045dc9  lea     rcx, [rcx+2]
0x140045dcd  movzx   eax, word ptr [rcx]
0x140045dd0  cmp     ax, 20h ; ' '
0x140045dd4  jz      short loc_140045DC9
0x140045dd6  test    ax, ax
0x140045dd9  jz      short loc_140045DFC
0x140045ddb  mov     ebx, 0C000000Dh
0x140045de0  mov     rcx, [rsp+38h+P]; P
0x140045de5  test    rcx, rcx
0x140045de8  jz      short loc_140045DF8
0x140045dea  xor     edx, edx; Tag
0x140045dec  call    cs:__imp_ExFreePoolWithTag
0x140045df3  nop     dword ptr [rax+rax+00h]
0x140045df8  mov     eax, ebx
0x140045dfa  jmp     short loc_140045E0D
0x140045dfc  mov     rax, [rsp+38h+P]
0x140045e01  mov     [rdi], rax
0x140045e04  mov     [rsi], ebp
0x140045e06  jmp     short loc_140045DF8
0x140045e08  mov     eax, 0C000000Dh
0x140045e0d  mov     rbx, [rsp+38h+arg_8]
0x140045e12  mov     rbp, [rsp+38h+arg_18]
0x140045e17  add     rsp, 20h
0x140045e1b  pop     r14
0x140045e1d  pop     rdi
0x140045e1e  pop     rsi
0x140045e1f  retn
```
