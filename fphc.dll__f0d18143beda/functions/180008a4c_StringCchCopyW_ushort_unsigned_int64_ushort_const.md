# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008a4c`
- end: `0x180008ab7`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800067f0`
- `0x180006970`
- `0x180008ac0`
- `0x180009e80`
- `0x18000dec4`

## callees

- `0x180008a4c`

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
0x180008a4c  xor     r10d, r10d
0x180008a4f  mov     r9, rcx
0x180008a52  test    rdx, rdx
0x180008a55  jz      short loc_180008AA8
0x180008a57  cmp     rdx, 7FFFFFFFh
0x180008a5e  jbe     short loc_180008A67
0x180008a60  mov     eax, 80070057h
0x180008a65  jmp     short loc_180008AB2
0x180008a67  mov     eax, 7FFFFFFEh
0x180008a6c  test    rax, rax
0x180008a6f  jz      short loc_180008A8F
0x180008a71  movzx   ecx, word ptr [r8]
0x180008a75  test    cx, cx
0x180008a78  jz      short loc_180008A8F
0x180008a7a  mov     [r9], cx
0x180008a7e  add     r8, 2
0x180008a82  add     r9, 2
0x180008a86  dec     rax
0x180008a89  sub     rdx, 1
0x180008a8d  jnz     short loc_180008A6C
0x180008a8f  test    rdx, rdx
0x180008a92  lea     rcx, [r9-2]
0x180008a96  cmovnz  rcx, r9
0x180008a9a  neg     rdx
0x180008a9d  sbb     eax, eax
0x180008a9f  not     eax
0x180008aa1  and     eax, 8007007Ah
0x180008aa6  jmp     short loc_180008AB2
0x180008aa8  mov     eax, 80070057h
0x180008aad  test    rdx, rdx
0x180008ab0  jz      short locret_180008AB6
0x180008ab2  mov     [rcx], r10w
0x180008ab6  retn
```
