# SepSddlDaclFromSDDLString

- ea: `0x1400095f4`
- end: `0x1400096d1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140009c14`

## callees

- `0x1400095f4`
- `0x1400096d8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000969c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000969c`

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
0x1400095f4  mov     rax, rsp
0x1400095f7  mov     [rax+10h], rbx
0x1400095fb  mov     [rax+20h], rbp
0x1400095ff  push    rsi
0x140009600  push    rdi
0x140009601  push    r14
0x140009603  sub     rsp, 20h
0x140009607  xor     r14d, r14d
0x14000960a  mov     rdi, r9
0x14000960d  mov     [rax+8], r14
0x140009611  mov     rsi, r8
0x140009614  mov     [rax+18h], r14
0x140009618  mov     [r9], r14
0x14000961b  mov     [r8], r14d
0x14000961e  jmp     short loc_140009624
0x140009620  add     rcx, 2
0x140009624  movzx   eax, word ptr [rcx]
0x140009627  cmp     ax, 20h ; ' '
0x14000962b  jz      short loc_140009620
0x14000962d  cmp     ax, 44h ; 'D'
0x140009631  jnz     loc_1400096B8
0x140009637  lea     r9, [rcx+2]
0x14000963b  cmp     word ptr [r9], 3Ah ; ':'
0x140009640  jnz     short loc_1400096B8
0x140009642  cmp     word ptr [r9+2], 50h ; 'P'
0x140009648  lea     r8, [rsp+38h+arg_10]
0x14000964d  mov     edx, 8
0x140009652  mov     ebp, 1008h
0x140009657  cmovnz  r9, rcx
0x14000965b  cmovnz  ebp, edx
0x14000965e  lea     rdx, [rsp+38h+P]; int
0x140009663  lea     rcx, [r9+4]; Str1
0x140009667  call    SepSddlGetAclForString
0x14000966c  mov     ebx, eax
0x14000966e  test    eax, eax
0x140009670  jnz     short loc_140009690
0x140009672  mov     rcx, [rsp+38h+arg_10]
0x140009677  jmp     short loc_14000967D
0x140009679  lea     rcx, [rcx+2]
0x14000967d  movzx   eax, word ptr [rcx]
0x140009680  cmp     ax, 20h ; ' '
0x140009684  jz      short loc_140009679
0x140009686  test    ax, ax
0x140009689  jz      short loc_1400096AC
0x14000968b  mov     ebx, 0C000000Dh
0x140009690  mov     rcx, [rsp+38h+P]; P
0x140009695  test    rcx, rcx
0x140009698  jz      short loc_1400096A8
0x14000969a  xor     edx, edx; Tag
0x14000969c  call    cs:__imp_ExFreePoolWithTag
0x1400096a3  nop     dword ptr [rax+rax+00h]
0x1400096a8  mov     eax, ebx
0x1400096aa  jmp     short loc_1400096BD
0x1400096ac  mov     rax, [rsp+38h+P]
0x1400096b1  mov     [rdi], rax
0x1400096b4  mov     [rsi], ebp
0x1400096b6  jmp     short loc_1400096A8
0x1400096b8  mov     eax, 0C000000Dh
0x1400096bd  mov     rbx, [rsp+38h+arg_8]
0x1400096c2  mov     rbp, [rsp+38h+arg_18]
0x1400096c7  add     rsp, 20h
0x1400096cb  pop     r14
0x1400096cd  pop     rdi
0x1400096ce  pop     rsi
0x1400096cf  retn
```
