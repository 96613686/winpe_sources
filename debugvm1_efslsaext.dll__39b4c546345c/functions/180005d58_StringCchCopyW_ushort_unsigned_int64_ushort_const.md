# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005d58`
- end: `0x180005dc3`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008544`
- `0x18000d41c`
- `0x18000ddd0`

## callees

- `0x180005d58`

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
0x180005d58  xor     r10d, r10d
0x180005d5b  mov     r9, rcx
0x180005d5e  test    rdx, rdx
0x180005d61  jz      short loc_180005DB4
0x180005d63  cmp     rdx, 7FFFFFFFh
0x180005d6a  jbe     short loc_180005D73
0x180005d6c  mov     eax, 80070057h
0x180005d71  jmp     short loc_180005DBE
0x180005d73  mov     eax, 7FFFFFFEh
0x180005d78  test    rax, rax
0x180005d7b  jz      short loc_180005D9B
0x180005d7d  movzx   ecx, word ptr [r8]
0x180005d81  test    cx, cx
0x180005d84  jz      short loc_180005D9B
0x180005d86  mov     [r9], cx
0x180005d8a  add     r8, 2
0x180005d8e  add     r9, 2
0x180005d92  dec     rax
0x180005d95  sub     rdx, 1
0x180005d99  jnz     short loc_180005D78
0x180005d9b  test    rdx, rdx
0x180005d9e  lea     rcx, [r9-2]
0x180005da2  cmovnz  rcx, r9
0x180005da6  neg     rdx
0x180005da9  sbb     eax, eax
0x180005dab  not     eax
0x180005dad  and     eax, 8007007Ah
0x180005db2  jmp     short loc_180005DBE
0x180005db4  mov     eax, 80070057h
0x180005db9  test    rdx, rdx
0x180005dbc  jz      short locret_180005DC2
0x180005dbe  mov     [rcx], r10w
0x180005dc2  retn
```
