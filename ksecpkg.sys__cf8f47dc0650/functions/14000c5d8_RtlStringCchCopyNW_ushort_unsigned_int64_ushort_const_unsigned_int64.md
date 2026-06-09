# RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x14000c5d8`
- end: `0x14000c635`
- name: `?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `93`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c6fc`
- `0x14000ca84`
- `0x14000ce40`
- `0x14000d200`
- `0x14000d5d8`

## callees

- `0x14000c5d8`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyNW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, unsigned __int64 a4)
{
  __int64 result; // rax
  __int64 v6; // r8
  unsigned __int16 *v7; // rax

  if ( a4 <= 0x7FFFFFFE )
  {
    v6 = 64;
    do
    {
      if ( !a4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --a4;
      --v6;
    }
    while ( v6 );
    v7 = a1 - 1;
    if ( v6 )
      v7 = a1;
    *v7 = 0;
    return v6 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000c5d8  xor     edx, edx
0x14000c5da  mov     rax, r8
0x14000c5dd  cmp     r9, 7FFFFFFEh
0x14000c5e4  jbe     short loc_14000C5F0
0x14000c5e6  mov     eax, 0C000000Dh
0x14000c5eb  mov     [rcx], dx
0x14000c5ee  retn
0x14000c5f0  mov     r8d, 40h ; '@'
0x14000c5f6  test    r9, r9
0x14000c5f9  jz      short loc_14000C61A
0x14000c5fb  movzx   r10d, word ptr [rax]
0x14000c5ff  test    r10w, r10w
0x14000c603  jz      short loc_14000C61A
0x14000c605  mov     [rcx], r10w
0x14000c609  add     rax, 2
0x14000c60d  add     rcx, 2
0x14000c611  dec     r9
0x14000c614  sub     r8, 1
0x14000c618  jnz     short loc_14000C5F6
0x14000c61a  test    r8, r8
0x14000c61d  lea     rax, [rcx-2]
0x14000c621  cmovnz  rax, rcx
0x14000c625  neg     r8
0x14000c628  mov     [rax], dx
0x14000c62b  sbb     eax, eax
0x14000c62d  not     eax
0x14000c62f  and     eax, 80000005h
0x14000c634  retn
```
