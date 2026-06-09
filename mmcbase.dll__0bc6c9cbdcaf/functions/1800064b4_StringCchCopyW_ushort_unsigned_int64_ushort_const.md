# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800064b4`
- end: `0x18000651f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f90`
- `0x180006730`
- `0x180006d04`
- `0x18000811c`
- `0x18000cd38`
- `0x180011118`
- `0x180011290`
- `0x1800113b4`
- `0x180011470`
- `0x1800124a0`
- `0x180012834`
- `0x180014860`
- `0x1800173a4`
- `0x180017684`
- `0x180017d5c`
- `0x180017e40`

## callees

- `0x1800064b4`

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
0x1800064b4  xor     r10d, r10d
0x1800064b7  mov     r9, rcx
0x1800064ba  test    rdx, rdx
0x1800064bd  jz      short loc_180006510
0x1800064bf  cmp     rdx, 7FFFFFFFh
0x1800064c6  jbe     short loc_1800064CF
0x1800064c8  mov     eax, 80070057h
0x1800064cd  jmp     short loc_18000651A
0x1800064cf  mov     eax, 7FFFFFFEh
0x1800064d4  test    rax, rax
0x1800064d7  jz      short loc_1800064F7
0x1800064d9  movzx   ecx, word ptr [r8]
0x1800064dd  test    cx, cx
0x1800064e0  jz      short loc_1800064F7
0x1800064e2  mov     [r9], cx
0x1800064e6  add     r8, 2
0x1800064ea  add     r9, 2
0x1800064ee  dec     rax
0x1800064f1  sub     rdx, 1
0x1800064f5  jnz     short loc_1800064D4
0x1800064f7  test    rdx, rdx
0x1800064fa  lea     rcx, [r9-2]
0x1800064fe  cmovnz  rcx, r9
0x180006502  neg     rdx
0x180006505  sbb     eax, eax
0x180006507  not     eax
0x180006509  and     eax, 8007007Ah
0x18000650e  jmp     short loc_18000651A
0x180006510  mov     eax, 80070057h
0x180006515  test    rdx, rdx
0x180006518  jz      short locret_18000651E
0x18000651a  mov     [rcx], r10w
0x18000651e  retn
```
