# IsFullPath(ushort const *)

- ea: `0x180009900`
- end: `0x180009999`
- name: `?IsFullPath@@YAHPEBG@Z`
- size: `153`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009488`
- `0x180016834`

## callees

- `0x180009900`

## pseudocode

```c
_BOOL8 __fastcall IsFullPath(const unsigned __int16 *a1)
{
  const unsigned __int16 *v2; // rax
  __int64 v3; // rdx
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  const unsigned __int16 *i; // rax
  unsigned __int64 v7; // r8
  unsigned __int16 v9; // cx

  if ( !a1 )
    return 0;
  v2 = a1;
  v3 = 0x7FFFFFFF;
  while ( *v2 )
  {
    ++v2;
    if ( !--v3 )
    {
      v4 = 0;
      goto LABEL_7;
    }
  }
  v4 = 0x7FFFFFFF - v3;
LABEL_7:
  if ( v3 )
  {
    if ( v4 >= 2 && a1[1] == 58 )
    {
      v9 = *a1;
      if ( (unsigned __int16)(v9 - 97) <= 0x19u || (unsigned __int16)(v9 - 65) <= 0x19u )
        return 1;
    }
  }
  v5 = 0x7FFFFFFF;
  for ( i = a1; *i; ++i )
  {
    if ( !--v5 )
    {
      v7 = 0;
      return v5 && v7 >= 2 && *a1 == 92 && a1[1] == 92;
    }
  }
  v7 = 0x7FFFFFFF - v5;
  return v5 && v7 >= 2 && *a1 == 92 && a1[1] == 92;
}

```

## disassembly

```asm
0x180009900  mov     r9, rcx
0x180009903  test    rcx, rcx
0x180009906  jz      short loc_180009970
0x180009908  mov     r8d, 7FFFFFFFh
0x18000990e  mov     rax, rcx
0x180009911  mov     edx, r8d
0x180009914  cmp     word ptr [rax], 0
0x180009918  jz      short loc_180009928
0x18000991a  add     rax, 2
0x18000991e  sub     rdx, 1
0x180009922  jnz     short loc_180009914
0x180009924  xor     eax, eax
0x180009926  jmp     short loc_18000992E
0x180009928  mov     rax, r8
0x18000992b  sub     rax, rdx
0x18000992e  test    rdx, rdx
0x180009931  jz      short loc_180009940
0x180009933  cmp     rax, 2
0x180009937  jb      short loc_180009940
0x180009939  cmp     word ptr [rcx+2], 3Ah ; ':'
0x18000993e  jz      short loc_180009973
0x180009940  mov     rcx, r8
0x180009943  mov     rax, r9
0x180009946  cmp     word ptr [rax], 0
0x18000994a  jz      short loc_18000995B
0x18000994c  add     rax, 2
0x180009950  sub     rcx, 1
0x180009954  jnz     short loc_180009946
0x180009956  xor     r8d, r8d
0x180009959  jmp     short loc_18000995E
0x18000995b  sub     r8, rcx
0x18000995e  test    rcx, rcx
0x180009961  jz      short loc_180009970
0x180009963  cmp     r8, 2
0x180009967  jb      short loc_180009970
0x180009969  cmp     word ptr [r9], 5Ch ; '\'
0x18000996e  jz      short loc_18000998B
0x180009970  xor     eax, eax
0x180009972  retn
0x180009973  movzx   ecx, word ptr [rcx]
0x180009976  lea     eax, [rcx-61h]
0x180009979  cmp     ax, 19h
0x18000997d  jbe     short loc_180009993
0x18000997f  sub     cx, 41h ; 'A'
0x180009983  cmp     cx, 19h
0x180009987  ja      short loc_180009940
0x180009989  jmp     short loc_180009993
0x18000998b  cmp     word ptr [r9+2], 5Ch ; '\'
0x180009991  jnz     short loc_180009970
0x180009993  mov     eax, 1
0x180009998  retn
```
