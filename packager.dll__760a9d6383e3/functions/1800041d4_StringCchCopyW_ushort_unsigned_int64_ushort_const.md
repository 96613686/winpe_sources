# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800041d4`
- end: `0x18000423f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005470`
- `0x180005e30`
- `0x1800079ac`
- `0x1800096e0`
- `0x18000ae84`
- `0x18000afb4`

## callees

- `0x1800041d4`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800041d4  xor     r10d, r10d
0x1800041d7  mov     r9, rcx
0x1800041da  test    rdx, rdx
0x1800041dd  jz      short loc_180004230
0x1800041df  cmp     rdx, 7FFFFFFFh
0x1800041e6  jbe     short loc_1800041EF
0x1800041e8  mov     eax, 80070057h
0x1800041ed  jmp     short loc_18000423A
0x1800041ef  mov     eax, 7FFFFFFEh
0x1800041f4  test    rax, rax
0x1800041f7  jz      short loc_180004217
0x1800041f9  movzx   ecx, word ptr [r8]
0x1800041fd  test    cx, cx
0x180004200  jz      short loc_180004217
0x180004202  mov     [r9], cx
0x180004206  add     r8, 2
0x18000420a  add     r9, 2
0x18000420e  dec     rax
0x180004211  sub     rdx, 1
0x180004215  jnz     short loc_1800041F4
0x180004217  test    rdx, rdx
0x18000421a  lea     rcx, [r9-2]
0x18000421e  cmovnz  rcx, r9
0x180004222  neg     rdx
0x180004225  sbb     eax, eax
0x180004227  not     eax
0x180004229  and     eax, 8007007Ah
0x18000422e  jmp     short loc_18000423A
0x180004230  mov     eax, 80070057h
0x180004235  test    rdx, rdx
0x180004238  jz      short locret_18000423E
0x18000423a  mov     [rcx], r10w
0x18000423e  retn
```
