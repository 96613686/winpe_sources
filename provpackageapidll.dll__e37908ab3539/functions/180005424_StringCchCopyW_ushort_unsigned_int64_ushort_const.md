# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005424`
- end: `0x18000548f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x180007370`
- `0x180007710`
- `0x1800077b0`
- `0x180007850`
- `0x180007c30`
- `0x180007ee0`
- `0x180007f78`
- `0x180009740`
- `0x180009c30`
- `0x180009d40`
- `0x180009e40`
- `0x180009f40`
- `0x18000a3c0`
- `0x18000a5b0`
- `0x18000d0c4`
- `0x18000d708`
- `0x18000da5c`
- `0x18000f040`
- `0x18000fc8c`
- `0x1800100a8`
- `0x180011c88`
- `0x180012444`
- `0x180014c70`
- `0x180016c50`
- `0x180017300`
- `0x180017f50`

## callees

- `0x180005424`

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
0x180005424  xor     r10d, r10d
0x180005427  mov     r9, rcx
0x18000542a  test    rdx, rdx
0x18000542d  jz      short loc_180005480
0x18000542f  cmp     rdx, 7FFFFFFFh
0x180005436  jbe     short loc_18000543F
0x180005438  mov     eax, 80070057h
0x18000543d  jmp     short loc_18000548A
0x18000543f  mov     eax, 7FFFFFFEh
0x180005444  test    rax, rax
0x180005447  jz      short loc_180005467
0x180005449  movzx   ecx, word ptr [r8]
0x18000544d  test    cx, cx
0x180005450  jz      short loc_180005467
0x180005452  mov     [r9], cx
0x180005456  add     r8, 2
0x18000545a  add     r9, 2
0x18000545e  dec     rax
0x180005461  sub     rdx, 1
0x180005465  jnz     short loc_180005444
0x180005467  test    rdx, rdx
0x18000546a  lea     rcx, [r9-2]
0x18000546e  cmovnz  rcx, r9
0x180005472  neg     rdx
0x180005475  sbb     eax, eax
0x180005477  not     eax
0x180005479  and     eax, 8007007Ah
0x18000547e  jmp     short loc_18000548A
0x180005480  mov     eax, 80070057h
0x180005485  test    rdx, rdx
0x180005488  jz      short locret_18000548E
0x18000548a  mov     [rcx], r10w
0x18000548e  retn
```
