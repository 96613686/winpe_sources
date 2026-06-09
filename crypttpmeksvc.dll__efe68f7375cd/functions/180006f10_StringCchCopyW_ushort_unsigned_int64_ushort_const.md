# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006f10`
- end: `0x180006f7b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006f84`
- `0x180008f38`

## callees

- `0x180006f10`

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
0x180006f10  xor     r10d, r10d
0x180006f13  mov     r9, rcx
0x180006f16  test    rdx, rdx
0x180006f19  jz      short loc_180006F6C
0x180006f1b  cmp     rdx, 7FFFFFFFh
0x180006f22  jbe     short loc_180006F2B
0x180006f24  mov     eax, 80070057h
0x180006f29  jmp     short loc_180006F76
0x180006f2b  mov     eax, 7FFFFFFEh
0x180006f30  test    rax, rax
0x180006f33  jz      short loc_180006F53
0x180006f35  movzx   ecx, word ptr [r8]
0x180006f39  test    cx, cx
0x180006f3c  jz      short loc_180006F53
0x180006f3e  mov     [r9], cx
0x180006f42  add     r8, 2
0x180006f46  add     r9, 2
0x180006f4a  dec     rax
0x180006f4d  sub     rdx, 1
0x180006f51  jnz     short loc_180006F30
0x180006f53  test    rdx, rdx
0x180006f56  lea     rcx, [r9-2]
0x180006f5a  cmovnz  rcx, r9
0x180006f5e  neg     rdx
0x180006f61  sbb     eax, eax
0x180006f63  not     eax
0x180006f65  and     eax, 8007007Ah
0x180006f6a  jmp     short loc_180006F76
0x180006f6c  mov     eax, 80070057h
0x180006f71  test    rdx, rdx
0x180006f74  jz      short locret_180006F7A
0x180006f76  mov     [rcx], r10w
0x180006f7a  retn
```
