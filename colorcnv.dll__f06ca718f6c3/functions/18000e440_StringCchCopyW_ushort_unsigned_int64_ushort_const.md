# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000e440`
- end: `0x18000e4ab`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dfb0`
- `0x18000ff14`
- `0x180013b68`
- `0x1800149ec`

## callees

- `0x18000e440`

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
0x18000e440  xor     r10d, r10d
0x18000e443  mov     r9, rcx
0x18000e446  test    rdx, rdx
0x18000e449  jz      short loc_18000E49C
0x18000e44b  cmp     rdx, 7FFFFFFFh
0x18000e452  jbe     short loc_18000E45B
0x18000e454  mov     eax, 80070057h
0x18000e459  jmp     short loc_18000E4A6
0x18000e45b  mov     eax, 7FFFFFFEh
0x18000e460  test    rax, rax
0x18000e463  jz      short loc_18000E483
0x18000e465  movzx   ecx, word ptr [r8]
0x18000e469  test    cx, cx
0x18000e46c  jz      short loc_18000E483
0x18000e46e  mov     [r9], cx
0x18000e472  add     r8, 2
0x18000e476  add     r9, 2
0x18000e47a  dec     rax
0x18000e47d  sub     rdx, 1
0x18000e481  jnz     short loc_18000E460
0x18000e483  test    rdx, rdx
0x18000e486  lea     rcx, [r9-2]
0x18000e48a  cmovnz  rcx, r9
0x18000e48e  neg     rdx
0x18000e491  sbb     eax, eax
0x18000e493  not     eax
0x18000e495  and     eax, 8007007Ah
0x18000e49a  jmp     short loc_18000E4A6
0x18000e49c  mov     eax, 80070057h
0x18000e4a1  test    rdx, rdx
0x18000e4a4  jz      short locret_18000E4AA
0x18000e4a6  mov     [rcx], r10w
0x18000e4aa  retn
```
