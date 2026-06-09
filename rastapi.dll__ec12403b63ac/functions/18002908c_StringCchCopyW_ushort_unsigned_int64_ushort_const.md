# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18002908c`
- end: `0x1800290db`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003504`
- `0x180017740`

## callees

- `0x18002908c`

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
0x18002908c  mov     eax, 7FFFFFFEh
0x180029091  mov     r9d, 20h ; ' '
0x180029097  xor     r10d, r10d
0x18002909a  test    rax, rax
0x18002909d  jz      short loc_1800290BC
0x18002909f  movzx   edx, word ptr [r8]
0x1800290a3  test    dx, dx
0x1800290a6  jz      short loc_1800290BC
0x1800290a8  mov     [rcx], dx
0x1800290ab  add     r8, 2
0x1800290af  add     rcx, 2
0x1800290b3  dec     rax
0x1800290b6  sub     r9, 1
0x1800290ba  jnz     short loc_18002909A
0x1800290bc  mov     rax, r9
0x1800290bf  lea     rdx, [rcx-2]
0x1800290c3  neg     rax
0x1800290c6  sbb     eax, eax
0x1800290c8  not     eax
0x1800290ca  and     eax, 8007007Ah
0x1800290cf  test    r9, r9
0x1800290d2  cmovnz  rdx, rcx
0x1800290d6  mov     [rdx], r10w
0x1800290da  retn
```
