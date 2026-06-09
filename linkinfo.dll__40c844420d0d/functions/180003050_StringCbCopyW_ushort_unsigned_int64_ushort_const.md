# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180003050`
- end: `0x1800030be`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `110`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b00`
- `0x180004b50`

## callees

- `0x180003050`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  unsigned __int16 *v4; // r9
  __int64 v5; // rax
  unsigned __int16 *v6; // rax
  __int64 result; // rax

  v3 = a2 >> 1;
  v4 = a1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v4++ = *a3++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = v4 - 1;
    if ( v3 )
      v6 = v4;
    *v6 = 0;
    result = 2147942522LL;
    if ( v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003050  shr     rdx, 1
0x180003053  mov     r9, rcx
0x180003056  jz      short loc_1800030AD
0x180003058  cmp     rdx, 7FFFFFFFh
0x18000305f  ja      short loc_1800030A6
0x180003061  mov     eax, 7FFFFFFEh
0x180003066  test    rax, rax
0x180003069  jz      short loc_180003089
0x18000306b  movzx   ecx, word ptr [r8]
0x18000306f  test    cx, cx
0x180003072  jz      short loc_180003089
0x180003074  mov     [r9], cx
0x180003078  add     r8, 2
0x18000307c  add     r9, 2
0x180003080  dec     rax
0x180003083  sub     rdx, 1
0x180003087  jnz     short loc_180003066
0x180003089  test    rdx, rdx
0x18000308c  lea     rax, [r9-2]
0x180003090  cmovnz  rax, r9
0x180003094  xor     ecx, ecx
0x180003096  test    rdx, rdx
0x180003099  mov     [rax], cx
0x18000309c  mov     eax, 8007007Ah
0x1800030a1  cmovnz  eax, ecx
0x1800030a4  retn
0x1800030a6  mov     eax, 80070057h
0x1800030ab  jmp     short loc_1800030B7
0x1800030ad  mov     eax, 80070057h
0x1800030b2  test    rdx, rdx
0x1800030b5  jz      short locret_1800030A4
0x1800030b7  xor     ecx, ecx
0x1800030b9  mov     [r9], cx
0x1800030bd  retn
```
