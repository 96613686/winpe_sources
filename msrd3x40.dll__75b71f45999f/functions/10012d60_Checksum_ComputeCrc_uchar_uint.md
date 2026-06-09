# Checksum::ComputeCrc(uchar *,uint)

- ea: `0x10012d60`
- end: `0x10012da7`
- name: `?ComputeCrc@Checksum@@QAEGPAEI@Z`
- size: `71`
- prototype: `unsigned __int16 __thiscall(Checksum *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1001a270`
- `0x1001b490`
- `0x1001d9a0`
- `0x1001db50`
- `0x1002fc20`
- `0x1004c8f0`
- `0x1004ccb0`
- `0x10058210`

## callees

- `0x10012d60`

## pseudocode

```c
unsigned int __thiscall Checksum::ComputeCrc(Checksum *this, unsigned __int8 *a2, unsigned int a3)
{
  unsigned int v3; // esi
  unsigned int result; // eax

  v3 = a3;
  for ( result = 0; v3; --v3 )
    result = (unsigned __int16)((unsigned __int8)byte_10003920[result >> 8]
                              ^ (*a2++ + ((_WORD)result << 8))
                              ^ (4
                               * ((unsigned __int8)byte_10003920[result >> 8]
                                ^ (unsigned __int16)((unsigned __int8)byte_10003920[result >> 8] << 13))));
  return result;
}

```

## disassembly

```asm
0x10012d60  mov     edi, edi
0x10012d62  push    ebp
0x10012d63  mov     ebp, esp
0x10012d65  push    esi
0x10012d66  mov     esi, [ebp+arg_4]
0x10012d69  xor     eax, eax
0x10012d6b  test    esi, esi
0x10012d6d  jz      short loc_10012DA2
0x10012d6f  push    edi
0x10012d70  mov     edi, [ebp+arg_0]
0x10012d73  mov     ecx, eax
0x10012d75  lea     edi, [edi+1]
0x10012d78  shr     ecx, 8
0x10012d7b  shl     eax, 8
0x10012d7e  movzx   edx, ds:byte_10003920[ecx]
0x10012d85  movzx   ecx, byte ptr [edi-1]
0x10012d89  add     eax, ecx
0x10012d8b  mov     ecx, edx
0x10012d8d  shl     ecx, 0Dh
0x10012d90  xor     ecx, edx
0x10012d92  shl     ecx, 2
0x10012d95  xor     ecx, eax
0x10012d97  xor     ecx, edx
0x10012d99  movzx   eax, cx
0x10012d9c  sub     esi, 1
0x10012d9f  jnz     short loc_10012D73
0x10012da1  pop     edi
0x10012da2  pop     esi
0x10012da3  pop     ebp
0x10012da4  retn    8
```
