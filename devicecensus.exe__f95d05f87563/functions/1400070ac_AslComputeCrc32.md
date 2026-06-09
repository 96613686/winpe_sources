# AslComputeCrc32

- ea: `0x1400070ac`
- end: `0x1400070e0`
- name: `AslComputeCrc32`
- size: `52`
- prototype: `__int64 __fastcall(int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d31c`
- `0x140010fd4`

## callees

- `0x1400070ac`

## pseudocode

```c
__int64 __fastcall AslComputeCrc32(int a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r9
  unsigned int i; // ecx
  __int64 v5; // rax

  v3 = 0;
  for ( i = ~a1; (unsigned int)v3 < a3; i = *((_DWORD *)AslpCrc32Table + v5) ^ (i >> 8) )
  {
    v5 = (unsigned __int8)(i ^ *(_BYTE *)(v3 + a2));
    v3 = (unsigned int)(v3 + 1);
  }
  return ~i;
}

```

## disassembly

```asm
0x1400070ac  xor     r9d, r9d
0x1400070af  mov     r10, rdx
0x1400070b2  not     ecx
0x1400070b4  test    r8d, r8d
0x1400070b7  jz      short loc_1400070DB
0x1400070b9  movzx   edx, byte ptr [r9+r10]
0x1400070be  mov     eax, ecx
0x1400070c0  xor     rdx, rax
0x1400070c3  shr     ecx, 8
0x1400070c6  movzx   eax, dl
0x1400070c9  inc     r9d
0x1400070cc  lea     rdx, AslpCrc32Table
0x1400070d3  xor     ecx, [rdx+rax*4]
0x1400070d6  cmp     r9d, r8d
0x1400070d9  jb      short loc_1400070B9
0x1400070db  not     ecx
0x1400070dd  mov     eax, ecx
0x1400070df  retn
```
