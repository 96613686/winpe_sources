# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005ffc`
- end: `0x140006067`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a0d4`

## callees

- `0x140005ffc`

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
0x140005ffc  xor     r10d, r10d
0x140005fff  mov     r9, rcx
0x140006002  test    rdx, rdx
0x140006005  jz      short loc_140006058
0x140006007  cmp     rdx, 7FFFFFFFh
0x14000600e  jbe     short loc_140006017
0x140006010  mov     eax, 80070057h
0x140006015  jmp     short loc_140006062
0x140006017  mov     eax, 7FFFFFFEh
0x14000601c  test    rax, rax
0x14000601f  jz      short loc_14000603F
0x140006021  movzx   ecx, word ptr [r8]
0x140006025  test    cx, cx
0x140006028  jz      short loc_14000603F
0x14000602a  mov     [r9], cx
0x14000602e  add     r8, 2
0x140006032  add     r9, 2
0x140006036  dec     rax
0x140006039  sub     rdx, 1
0x14000603d  jnz     short loc_14000601C
0x14000603f  test    rdx, rdx
0x140006042  lea     rcx, [r9-2]
0x140006046  cmovnz  rcx, r9
0x14000604a  neg     rdx
0x14000604d  sbb     eax, eax
0x14000604f  not     eax
0x140006051  and     eax, 8007007Ah
0x140006056  jmp     short loc_140006062
0x140006058  mov     eax, 80070057h
0x14000605d  test    rdx, rdx
0x140006060  jz      short locret_140006066
0x140006062  mov     [rcx], r10w
0x140006066  retn
```
