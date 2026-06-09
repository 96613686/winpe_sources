# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180017d9c`
- end: `0x180017deb`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002cc0`

## callees

- `0x180017d9c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 32;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = a1 - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = a1;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x180017d9c  mov     eax, 7FFFFFFEh
0x180017da1  mov     r9d, 20h ; ' '
0x180017da7  xor     r10d, r10d
0x180017daa  test    rax, rax
0x180017dad  jz      short loc_180017DCC
0x180017daf  movzx   edx, word ptr [r8]
0x180017db3  test    dx, dx
0x180017db6  jz      short loc_180017DCC
0x180017db8  mov     [rcx], dx
0x180017dbb  add     r8, 2
0x180017dbf  add     rcx, 2
0x180017dc3  dec     rax
0x180017dc6  sub     r9, 1
0x180017dca  jnz     short loc_180017DAA
0x180017dcc  mov     rax, r9
0x180017dcf  lea     rdx, [rcx-2]
0x180017dd3  neg     rax
0x180017dd6  sbb     eax, eax
0x180017dd8  not     eax
0x180017dda  and     eax, 8007007Ah
0x180017ddf  test    r9, r9
0x180017de2  cmovnz  rdx, rcx
0x180017de6  mov     [rdx], r10w
0x180017dea  retn
```
