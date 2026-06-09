# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180007ae0`
- end: `0x180007b4b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000312c`
- `0x180003894`
- `0x1800039c8`
- `0x1800051b4`
- `0x180005ef4`
- `0x180008250`
- `0x1800189a0`

## callees

- `0x180007ae0`

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
0x180007ae0  xor     r10d, r10d
0x180007ae3  mov     r9, rcx
0x180007ae6  test    rdx, rdx
0x180007ae9  jz      short loc_180007B3C
0x180007aeb  cmp     rdx, 7FFFFFFFh
0x180007af2  jbe     short loc_180007AFB
0x180007af4  mov     eax, 80070057h
0x180007af9  jmp     short loc_180007B46
0x180007afb  mov     eax, 7FFFFFFEh
0x180007b00  test    rax, rax
0x180007b03  jz      short loc_180007B23
0x180007b05  movzx   ecx, word ptr [r8]
0x180007b09  test    cx, cx
0x180007b0c  jz      short loc_180007B23
0x180007b0e  mov     [r9], cx
0x180007b12  add     r8, 2
0x180007b16  add     r9, 2
0x180007b1a  dec     rax
0x180007b1d  sub     rdx, 1
0x180007b21  jnz     short loc_180007B00
0x180007b23  test    rdx, rdx
0x180007b26  lea     rcx, [r9-2]
0x180007b2a  cmovnz  rcx, r9
0x180007b2e  neg     rdx
0x180007b31  sbb     eax, eax
0x180007b33  not     eax
0x180007b35  and     eax, 8007007Ah
0x180007b3a  jmp     short loc_180007B46
0x180007b3c  mov     eax, 80070057h
0x180007b41  test    rdx, rdx
0x180007b44  jz      short locret_180007B4A
0x180007b46  mov     [rcx], r10w
0x180007b4a  retn
```
