# AslComputeCrc32

- ea: `0x18000b8ac`
- end: `0x18000b8e0`
- name: `AslComputeCrc32`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fea0`
- `0x180012270`

## callees

- `0x18000b8ac`

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
0x18000b8ac  xor     r9d, r9d
0x18000b8af  mov     r10, rdx
0x18000b8b2  not     ecx
0x18000b8b4  test    r8d, r8d
0x18000b8b7  jz      short loc_18000B8DB
0x18000b8b9  movzx   edx, byte ptr [r9+r10]
0x18000b8be  mov     eax, ecx
0x18000b8c0  xor     rdx, rax
0x18000b8c3  shr     ecx, 8
0x18000b8c6  movzx   eax, dl
0x18000b8c9  inc     r9d
0x18000b8cc  lea     rdx, AslpCrc32Table
0x18000b8d3  xor     ecx, [rdx+rax*4]
0x18000b8d6  cmp     r9d, r8d
0x18000b8d9  jb      short loc_18000B8B9
0x18000b8db  not     ecx
0x18000b8dd  mov     eax, ecx
0x18000b8df  retn
```
