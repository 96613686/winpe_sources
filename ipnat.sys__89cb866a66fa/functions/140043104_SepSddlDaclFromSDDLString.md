# SepSddlDaclFromSDDLString

- ea: `0x140043104`
- end: `0x1400431e1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140043734`

## callees

- `0x140043104`
- `0x1400431e8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400431ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400431ac`

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
0x140043104  mov     rax, rsp
0x140043107  mov     [rax+10h], rbx
0x14004310b  mov     [rax+20h], rbp
0x14004310f  push    rsi
0x140043110  push    rdi
0x140043111  push    r14
0x140043113  sub     rsp, 20h
0x140043117  xor     r14d, r14d
0x14004311a  mov     rdi, r9
0x14004311d  mov     [rax+8], r14
0x140043121  mov     rsi, r8
0x140043124  mov     [rax+18h], r14
0x140043128  mov     [r9], r14
0x14004312b  mov     [r8], r14d
0x14004312e  jmp     short loc_140043134
0x140043130  add     rcx, 2
0x140043134  movzx   eax, word ptr [rcx]
0x140043137  cmp     ax, 20h ; ' '
0x14004313b  jz      short loc_140043130
0x14004313d  cmp     ax, 44h ; 'D'
0x140043141  jnz     loc_1400431C8
0x140043147  lea     r9, [rcx+2]
0x14004314b  cmp     word ptr [r9], 3Ah ; ':'
0x140043150  jnz     short loc_1400431C8
0x140043152  cmp     word ptr [r9+2], 50h ; 'P'
0x140043158  lea     r8, [rsp+38h+arg_10]
0x14004315d  mov     edx, 8
0x140043162  mov     ebp, 1008h
0x140043167  cmovnz  r9, rcx
0x14004316b  cmovnz  ebp, edx
0x14004316e  lea     rdx, [rsp+38h+P]; int
0x140043173  lea     rcx, [r9+4]; Str1
0x140043177  call    SepSddlGetAclForString
0x14004317c  mov     ebx, eax
0x14004317e  test    eax, eax
0x140043180  jnz     short loc_1400431A0
0x140043182  mov     rcx, [rsp+38h+arg_10]
0x140043187  jmp     short loc_14004318D
0x140043189  lea     rcx, [rcx+2]
0x14004318d  movzx   eax, word ptr [rcx]
0x140043190  cmp     ax, 20h ; ' '
0x140043194  jz      short loc_140043189
0x140043196  test    ax, ax
0x140043199  jz      short loc_1400431BC
0x14004319b  mov     ebx, 0C000000Dh
0x1400431a0  mov     rcx, [rsp+38h+P]; P
0x1400431a5  test    rcx, rcx
0x1400431a8  jz      short loc_1400431B8
0x1400431aa  xor     edx, edx; Tag
0x1400431ac  call    cs:__imp_ExFreePoolWithTag
0x1400431b3  nop     dword ptr [rax+rax+00h]
0x1400431b8  mov     eax, ebx
0x1400431ba  jmp     short loc_1400431CD
0x1400431bc  mov     rax, [rsp+38h+P]
0x1400431c1  mov     [rdi], rax
0x1400431c4  mov     [rsi], ebp
0x1400431c6  jmp     short loc_1400431B8
0x1400431c8  mov     eax, 0C000000Dh
0x1400431cd  mov     rbx, [rsp+38h+arg_8]
0x1400431d2  mov     rbp, [rsp+38h+arg_18]
0x1400431d7  add     rsp, 20h
0x1400431db  pop     r14
0x1400431dd  pop     rdi
0x1400431de  pop     rsi
0x1400431df  retn
```
