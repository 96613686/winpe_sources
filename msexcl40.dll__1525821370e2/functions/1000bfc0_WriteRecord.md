# WriteRecord

- ea: `0x1000bfc0`
- end: `0x1000c024`
- name: `WriteRecord`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000ca90`
- `0x1000d590`

## callees

- `0x1000bfc0`
- `0x1002611f`

## pseudocode

```c
int __fastcall WriteRecord(int a1, int a2, int a3, char *a4)
{
  int v5; // eax
  int result; // eax

  *(_DWORD *)(a2 + 20) += *(__int16 *)(a3 + 2) + 4;
  if ( *(_DWORD *)(a2 + 24) != 1 )
    return 0;
  v5 = BFWriteFile(*(_DWORD *)(a1 + 20), (char *)a3, 4u);
  if ( !v5 )
  {
    v5 = BFWriteFile(*(_DWORD *)(a1 + 20), a4, *(__int16 *)(a3 + 2));
    if ( !v5 )
      return 0;
  }
  result = dword_10001970[abs32(v5)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x1000bfc0  mov     edi, edi
0x1000bfc2  push    ebp
0x1000bfc3  mov     ebp, esp
0x1000bfc5  push    esi
0x1000bfc6  mov     esi, [ebp+arg_0]
0x1000bfc9  push    edi
0x1000bfca  mov     edi, ecx
0x1000bfcc  movsx   eax, word ptr [esi+2]
0x1000bfd0  add     eax, 4
0x1000bfd3  add     [edx+14h], eax
0x1000bfd6  cmp     dword ptr [edx+18h], 1
0x1000bfda  jnz     short loc_1000C01C
0x1000bfdc  mov     ecx, [edi+14h]
0x1000bfdf  mov     edx, esi
0x1000bfe1  push    4
0x1000bfe3  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000bfe8  test    eax, eax
0x1000bfea  jz      short loc_1000C008
0x1000bfec  cdq
0x1000bfed  mov     ecx, 0FFFFFFF6h
0x1000bff2  xor     eax, edx
0x1000bff4  sub     eax, edx
0x1000bff6  mov     eax, ds:dword_10001970[eax*4]
0x1000bffd  cmp     eax, ecx
0x1000bfff  cmovz   eax, ecx
0x1000c002  pop     edi
0x1000c003  pop     esi
0x1000c004  pop     ebp
0x1000c005  retn    8
0x1000c008  movsx   eax, word ptr [esi+2]
0x1000c00c  mov     edx, [ebp+arg_4]
0x1000c00f  mov     ecx, [edi+14h]
0x1000c012  push    eax
0x1000c013  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000c018  test    eax, eax
0x1000c01a  jnz     short loc_1000BFEC
0x1000c01c  pop     edi
0x1000c01d  xor     eax, eax
0x1000c01f  pop     esi
0x1000c020  pop     ebp
0x1000c021  retn    8
```
