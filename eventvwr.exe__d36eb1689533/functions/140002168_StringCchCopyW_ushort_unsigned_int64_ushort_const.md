# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140002168`
- end: `0x1400021d3`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001adc`
- `0x140001bf0`
- `0x140001c68`
- `0x140001f30`
- `0x1400023ac`

## callees

- `0x140002168`

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
0x140002168  xor     r10d, r10d
0x14000216b  mov     r9, rcx
0x14000216e  test    rdx, rdx
0x140002171  jz      short loc_1400021C4
0x140002173  cmp     rdx, 7FFFFFFFh
0x14000217a  jbe     short loc_140002183
0x14000217c  mov     eax, 80070057h
0x140002181  jmp     short loc_1400021CE
0x140002183  mov     eax, 7FFFFFFEh
0x140002188  test    rax, rax
0x14000218b  jz      short loc_1400021AB
0x14000218d  movzx   ecx, word ptr [r8]
0x140002191  test    cx, cx
0x140002194  jz      short loc_1400021AB
0x140002196  mov     [r9], cx
0x14000219a  add     r8, 2
0x14000219e  add     r9, 2
0x1400021a2  dec     rax
0x1400021a5  sub     rdx, 1
0x1400021a9  jnz     short loc_140002188
0x1400021ab  test    rdx, rdx
0x1400021ae  lea     rcx, [r9-2]
0x1400021b2  cmovnz  rcx, r9
0x1400021b6  neg     rdx
0x1400021b9  sbb     eax, eax
0x1400021bb  not     eax
0x1400021bd  and     eax, 8007007Ah
0x1400021c2  jmp     short loc_1400021CE
0x1400021c4  mov     eax, 80070057h
0x1400021c9  test    rdx, rdx
0x1400021cc  jz      short locret_1400021D2
0x1400021ce  mov     [rcx], r10w
0x1400021d2  retn
```
