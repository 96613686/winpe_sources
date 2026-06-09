# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800069b8`
- end: `0x180006a23`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180008fe8`
- `0x1800090b4`
- `0x1800099f0`
- `0x18000a8bc`
- `0x18000ab50`
- `0x18000ae10`
- `0x18000af5c`
- `0x180010a00`

## callees

- `0x1800069b8`

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
0x1800069b8  xor     r10d, r10d
0x1800069bb  mov     r9, rcx
0x1800069be  test    rdx, rdx
0x1800069c1  jz      short loc_180006A14
0x1800069c3  cmp     rdx, 7FFFFFFFh
0x1800069ca  jbe     short loc_1800069D3
0x1800069cc  mov     eax, 80070057h
0x1800069d1  jmp     short loc_180006A1E
0x1800069d3  mov     eax, 7FFFFFFEh
0x1800069d8  test    rax, rax
0x1800069db  jz      short loc_1800069FB
0x1800069dd  movzx   ecx, word ptr [r8]
0x1800069e1  test    cx, cx
0x1800069e4  jz      short loc_1800069FB
0x1800069e6  mov     [r9], cx
0x1800069ea  add     r8, 2
0x1800069ee  add     r9, 2
0x1800069f2  dec     rax
0x1800069f5  sub     rdx, 1
0x1800069f9  jnz     short loc_1800069D8
0x1800069fb  test    rdx, rdx
0x1800069fe  lea     rcx, [r9-2]
0x180006a02  cmovnz  rcx, r9
0x180006a06  neg     rdx
0x180006a09  sbb     eax, eax
0x180006a0b  not     eax
0x180006a0d  and     eax, 8007007Ah
0x180006a12  jmp     short loc_180006A1E
0x180006a14  mov     eax, 80070057h
0x180006a19  test    rdx, rdx
0x180006a1c  jz      short locret_180006A22
0x180006a1e  mov     [rcx], r10w
0x180006a22  retn
```
