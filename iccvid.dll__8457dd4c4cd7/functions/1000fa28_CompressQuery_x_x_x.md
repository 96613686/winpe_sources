# CompressQuery(x,x,x)

- ea: `0x1000fa28`
- end: `0x1000fa80`
- name: `_CompressQuery@12`
- size: `88`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100093a0`
- `0x1000fa86`
- `0x1000fbcc`
- `0x1000fc97`

## callees

- `0x1000f82f`
- `0x1000fa28`

## pseudocode

```c
int __fastcall CompressQuery(int a1, int a2, int a3)
{
  int v4; // ecx

  if ( !a2 || (unsigned int)DecompressedDibType(a2) > 4 )
    return -2;
  if ( !a3 )
    return 0;
  v4 = ((*(_BYTE *)(a3 + 14) & 0x1F) == 8) + 1;
  if ( *(_DWORD *)(a3 + 16) != 1684633187 )
    v4 = 0;
  if ( v4 && *(_DWORD *)(a3 + 4) == *(_DWORD *)(a2 + 4) && *(_DWORD *)(a3 + 8) == *(_DWORD *)(a2 + 8) )
    return 0;
  else
    return -2;
}

```

## disassembly

```asm
0x1000fa28  mov     edi, edi
0x1000fa2a  push    ebp
0x1000fa2b  mov     ebp, esp
0x1000fa2d  push    esi
0x1000fa2e  mov     esi, edx
0x1000fa30  test    esi, esi
0x1000fa32  jz      short loc_1000FA78
0x1000fa34  mov     ecx, esi
0x1000fa36  call    _DecompressedDibType@4; DecompressedDibType(x)
0x1000fa3b  cmp     eax, 4
0x1000fa3e  ja      short loc_1000FA78
0x1000fa40  mov     edx, [ebp+arg_0]
0x1000fa43  test    edx, edx
0x1000fa45  jz      short loc_1000FA74
0x1000fa47  mov     al, [edx+0Eh]
0x1000fa4a  xor     ecx, ecx
0x1000fa4c  and     al, 1Fh
0x1000fa4e  cmp     al, 8
0x1000fa50  setz    cl
0x1000fa53  xor     eax, eax
0x1000fa55  inc     ecx
0x1000fa56  cmp     dword ptr [edx+10h], 64697663h
0x1000fa5d  cmovnz  ecx, eax
0x1000fa60  test    ecx, ecx
0x1000fa62  jz      short loc_1000FA78
0x1000fa64  mov     eax, [edx+4]
0x1000fa67  cmp     eax, [esi+4]
0x1000fa6a  jnz     short loc_1000FA78
0x1000fa6c  mov     eax, [edx+8]
0x1000fa6f  cmp     eax, [esi+8]
0x1000fa72  jnz     short loc_1000FA78
0x1000fa74  xor     eax, eax
0x1000fa76  jmp     short loc_1000FA7B
0x1000fa78  push    0FFFFFFFEh
0x1000fa7a  pop     eax
0x1000fa7b  pop     esi
0x1000fa7c  pop     ebp
0x1000fa7d  retn    4
```
