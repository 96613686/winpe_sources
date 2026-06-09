# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180009f80`
- end: `0x180009feb`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001775c`
- `0x180017ab0`

## callees

- `0x180009f80`

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
0x180009f80  xor     r10d, r10d
0x180009f83  mov     r9, rcx
0x180009f86  test    rdx, rdx
0x180009f89  jz      short loc_180009FDC
0x180009f8b  cmp     rdx, 7FFFFFFFh
0x180009f92  jbe     short loc_180009F9B
0x180009f94  mov     eax, 80070057h
0x180009f99  jmp     short loc_180009FE6
0x180009f9b  mov     eax, 7FFFFFFEh
0x180009fa0  test    rax, rax
0x180009fa3  jz      short loc_180009FC3
0x180009fa5  movzx   ecx, word ptr [r8]
0x180009fa9  test    cx, cx
0x180009fac  jz      short loc_180009FC3
0x180009fae  mov     [r9], cx
0x180009fb2  add     r8, 2
0x180009fb6  add     r9, 2
0x180009fba  dec     rax
0x180009fbd  sub     rdx, 1
0x180009fc1  jnz     short loc_180009FA0
0x180009fc3  test    rdx, rdx
0x180009fc6  lea     rcx, [r9-2]
0x180009fca  cmovnz  rcx, r9
0x180009fce  neg     rdx
0x180009fd1  sbb     eax, eax
0x180009fd3  not     eax
0x180009fd5  and     eax, 8007007Ah
0x180009fda  jmp     short loc_180009FE6
0x180009fdc  mov     eax, 80070057h
0x180009fe1  test    rdx, rdx
0x180009fe4  jz      short locret_180009FEA
0x180009fe6  mov     [rcx], r10w
0x180009fea  retn
```
