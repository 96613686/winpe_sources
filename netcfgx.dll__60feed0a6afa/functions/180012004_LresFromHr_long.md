# LresFromHr(long)

- ea: `0x180012004`
- end: `0x18001202c`
- name: `?LresFromHr@@YA_JJ@Z`
- size: `40`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009368`
- `0x18000967c`
- `0x180009730`
- `0x1800115f0`

## callees

- `0x180012004`

## pseudocode

```c
__int64 __fastcall LresFromHr(int a1)
{
  __int64 result; // rax

  if ( a1 == -2147180479 )
    return 1;
  if ( a1 == -2147180478 )
    return 2;
  result = 0;
  if ( a1 < 0 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180012004  movsxd  rdx, ecx
0x180012007  cmp     edx, 8004A041h
0x18001200d  jnz     short loc_180012015
0x18001200f  mov     eax, 1
0x180012014  retn
0x180012015  cmp     edx, 8004A042h
0x18001201b  jnz     short loc_180012023
0x18001201d  mov     eax, 2
0x180012022  retn
0x180012023  xor     eax, eax
0x180012025  test    ecx, ecx
0x180012027  cmovs   rax, rdx
0x18001202b  retn
```
