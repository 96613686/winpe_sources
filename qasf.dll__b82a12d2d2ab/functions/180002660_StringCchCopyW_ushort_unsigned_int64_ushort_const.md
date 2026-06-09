# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180002660`
- end: `0x1800026cb`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002450`
- `0x1800033c0`
- `0x180004f90`
- `0x180009990`
- `0x18000aa50`
- `0x18000fae0`
- `0x180011580`
- `0x1800121e0`

## callees

- `0x180002660`

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
0x180002660  xor     r10d, r10d
0x180002663  mov     r9, rcx
0x180002666  test    rdx, rdx
0x180002669  jz      short loc_1800026BC
0x18000266b  cmp     rdx, 7FFFFFFFh
0x180002672  jbe     short loc_18000267B
0x180002674  mov     eax, 80070057h
0x180002679  jmp     short loc_1800026C6
0x18000267b  mov     eax, 7FFFFFFEh
0x180002680  test    rax, rax
0x180002683  jz      short loc_1800026A3
0x180002685  movzx   ecx, word ptr [r8]
0x180002689  test    cx, cx
0x18000268c  jz      short loc_1800026A3
0x18000268e  mov     [r9], cx
0x180002692  add     r8, 2
0x180002696  add     r9, 2
0x18000269a  dec     rax
0x18000269d  sub     rdx, 1
0x1800026a1  jnz     short loc_180002680
0x1800026a3  test    rdx, rdx
0x1800026a6  lea     rcx, [r9-2]
0x1800026aa  cmovnz  rcx, r9
0x1800026ae  neg     rdx
0x1800026b1  sbb     eax, eax
0x1800026b3  not     eax
0x1800026b5  and     eax, 8007007Ah
0x1800026ba  jmp     short loc_1800026C6
0x1800026bc  mov     eax, 80070057h
0x1800026c1  test    rdx, rdx
0x1800026c4  jz      short locret_1800026CA
0x1800026c6  mov     [rcx], r10w
0x1800026ca  retn
```
