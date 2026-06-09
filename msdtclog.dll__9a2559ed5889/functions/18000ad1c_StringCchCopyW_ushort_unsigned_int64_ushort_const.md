# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000ad1c`
- end: `0x18000ad87`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adf8`
- `0x18000e090`
- `0x18000e574`
- `0x18000f744`
- `0x180010b74`
- `0x1800119e8`

## callees

- `0x18000ad1c`

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
0x18000ad1c  xor     r10d, r10d
0x18000ad1f  mov     r9, rcx
0x18000ad22  test    rdx, rdx
0x18000ad25  jz      short loc_18000AD78
0x18000ad27  cmp     rdx, 7FFFFFFFh
0x18000ad2e  jbe     short loc_18000AD37
0x18000ad30  mov     eax, 80070057h
0x18000ad35  jmp     short loc_18000AD82
0x18000ad37  mov     eax, 7FFFFFFEh
0x18000ad3c  test    rax, rax
0x18000ad3f  jz      short loc_18000AD5F
0x18000ad41  movzx   ecx, word ptr [r8]
0x18000ad45  test    cx, cx
0x18000ad48  jz      short loc_18000AD5F
0x18000ad4a  mov     [r9], cx
0x18000ad4e  add     r8, 2
0x18000ad52  add     r9, 2
0x18000ad56  dec     rax
0x18000ad59  sub     rdx, 1
0x18000ad5d  jnz     short loc_18000AD3C
0x18000ad5f  test    rdx, rdx
0x18000ad62  lea     rcx, [r9-2]
0x18000ad66  cmovnz  rcx, r9
0x18000ad6a  neg     rdx
0x18000ad6d  sbb     eax, eax
0x18000ad6f  not     eax
0x18000ad71  and     eax, 8007007Ah
0x18000ad76  jmp     short loc_18000AD82
0x18000ad78  mov     eax, 80070057h
0x18000ad7d  test    rdx, rdx
0x18000ad80  jz      short locret_18000AD86
0x18000ad82  mov     [rcx], r10w
0x18000ad86  retn
```
