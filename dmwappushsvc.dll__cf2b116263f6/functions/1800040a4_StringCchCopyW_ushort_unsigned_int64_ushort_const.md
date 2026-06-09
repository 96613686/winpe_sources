# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800040a4`
- end: `0x18000410f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030e4`
- `0x180008218`
- `0x18000bb38`
- `0x18000deb0`
- `0x18000e994`
- `0x18000faf0`
- `0x180010770`
- `0x180011608`

## callees

- `0x1800040a4`

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
0x1800040a4  xor     r10d, r10d
0x1800040a7  mov     r9, rcx
0x1800040aa  test    rdx, rdx
0x1800040ad  jz      short loc_180004100
0x1800040af  cmp     rdx, 7FFFFFFFh
0x1800040b6  jbe     short loc_1800040BF
0x1800040b8  mov     eax, 80070057h
0x1800040bd  jmp     short loc_18000410A
0x1800040bf  mov     eax, 7FFFFFFEh
0x1800040c4  test    rax, rax
0x1800040c7  jz      short loc_1800040E7
0x1800040c9  movzx   ecx, word ptr [r8]
0x1800040cd  test    cx, cx
0x1800040d0  jz      short loc_1800040E7
0x1800040d2  mov     [r9], cx
0x1800040d6  add     r8, 2
0x1800040da  add     r9, 2
0x1800040de  dec     rax
0x1800040e1  sub     rdx, 1
0x1800040e5  jnz     short loc_1800040C4
0x1800040e7  test    rdx, rdx
0x1800040ea  lea     rcx, [r9-2]
0x1800040ee  cmovnz  rcx, r9
0x1800040f2  neg     rdx
0x1800040f5  sbb     eax, eax
0x1800040f7  not     eax
0x1800040f9  and     eax, 8007007Ah
0x1800040fe  jmp     short loc_18000410A
0x180004100  mov     eax, 80070057h
0x180004105  test    rdx, rdx
0x180004108  jz      short locret_18000410E
0x18000410a  mov     [rcx], r10w
0x18000410e  retn
```
