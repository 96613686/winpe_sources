# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800060c8`
- end: `0x180006133`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006724`
- `0x180006db4`
- `0x18000de40`

## callees

- `0x1800060c8`

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
0x1800060c8  xor     r10d, r10d
0x1800060cb  mov     r9, rcx
0x1800060ce  test    rdx, rdx
0x1800060d1  jz      short loc_180006124
0x1800060d3  cmp     rdx, 7FFFFFFFh
0x1800060da  jbe     short loc_1800060E3
0x1800060dc  mov     eax, 80070057h
0x1800060e1  jmp     short loc_18000612E
0x1800060e3  mov     eax, 7FFFFFFEh
0x1800060e8  test    rax, rax
0x1800060eb  jz      short loc_18000610B
0x1800060ed  movzx   ecx, word ptr [r8]
0x1800060f1  test    cx, cx
0x1800060f4  jz      short loc_18000610B
0x1800060f6  mov     [r9], cx
0x1800060fa  add     r8, 2
0x1800060fe  add     r9, 2
0x180006102  dec     rax
0x180006105  sub     rdx, 1
0x180006109  jnz     short loc_1800060E8
0x18000610b  test    rdx, rdx
0x18000610e  lea     rcx, [r9-2]
0x180006112  cmovnz  rcx, r9
0x180006116  neg     rdx
0x180006119  sbb     eax, eax
0x18000611b  not     eax
0x18000611d  and     eax, 8007007Ah
0x180006122  jmp     short loc_18000612E
0x180006124  mov     eax, 80070057h
0x180006129  test    rdx, rdx
0x18000612c  jz      short locret_180006132
0x18000612e  mov     [rcx], r10w
0x180006132  retn
```
