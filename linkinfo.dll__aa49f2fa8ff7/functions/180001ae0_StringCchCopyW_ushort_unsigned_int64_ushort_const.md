# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180001ae0`
- end: `0x180001b4e`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `110`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019e0`
- `0x180001bd0`
- `0x1800028c0`
- `0x1800031f0`
- `0x1800044f0`
- `0x180004840`
- `0x1800048ec`
- `0x1800049dc`

## callees

- `0x180001ae0`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001ae0  mov     r9, rcx
0x180001ae3  test    rdx, rdx
0x180001ae6  jz      short loc_180001B3D
0x180001ae8  cmp     rdx, 7FFFFFFFh
0x180001aef  ja      short loc_180001B36
0x180001af1  mov     eax, 7FFFFFFEh
0x180001af6  test    rax, rax
0x180001af9  jz      short loc_180001B19
0x180001afb  movzx   ecx, word ptr [r8]
0x180001aff  test    cx, cx
0x180001b02  jz      short loc_180001B19
0x180001b04  mov     [r9], cx
0x180001b08  add     r8, 2
0x180001b0c  add     r9, 2
0x180001b10  dec     rax
0x180001b13  sub     rdx, 1
0x180001b17  jnz     short loc_180001AF6
0x180001b19  test    rdx, rdx
0x180001b1c  lea     rax, [r9-2]
0x180001b20  cmovnz  rax, r9
0x180001b24  xor     ecx, ecx
0x180001b26  test    rdx, rdx
0x180001b29  mov     [rax], cx
0x180001b2c  mov     eax, 8007007Ah
0x180001b31  cmovnz  eax, ecx
0x180001b34  retn
0x180001b36  mov     eax, 80070057h
0x180001b3b  jmp     short loc_180001B47
0x180001b3d  mov     eax, 80070057h
0x180001b42  test    rdx, rdx
0x180001b45  jz      short locret_180001B34
0x180001b47  xor     ecx, ecx
0x180001b49  mov     [r9], cx
0x180001b4d  retn
```
