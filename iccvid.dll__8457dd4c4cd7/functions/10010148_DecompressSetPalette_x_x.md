# DecompressSetPalette(x,x)

- ea: `0x10010148`
- end: `0x100101ec`
- name: `_DecompressSetPalette@8`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x1000552a`
- `0x10010148`
- `0x1001358d`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100101ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100101ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10010172`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10010172`

## pseudocode

```c
int __fastcall DecompressSetPalette(int a1, int a2)
{
  HLOCAL v5; // edi
  int v6; // edx
  _DWORD *v7; // ecx

  if ( a2 )
  {
    if ( *(_WORD *)(a2 + 14) != 8 )
      return -2;
    v5 = *(HLOCAL *)(a1 + 100);
    if ( !v5 )
    {
      v5 = LocalAlloc(0x40u, 0x400u);
      *(_DWORD *)(a1 + 100) = v5;
      if ( !v5 )
        return -3;
    }
    v6 = 256;
    if ( (unsigned int)(*(_DWORD *)(a2 + 32) - 1) <= 0xFE )
      v6 = *(_DWORD *)(a2 + 32);
    *(_DWORD *)(a1 + 96) = v6;
    memcpy(v5, (const void *)(a2 + *(_DWORD *)a2), 4 * v6);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 100) )
    {
      LocalFree(*(HLOCAL *)(a1 + 100));
      *(_DWORD *)(a1 + 100) = 0;
    }
    *(_DWORD *)(a1 + 96) = 0;
  }
  v7 = *(_DWORD **)(a1 + 92);
  if ( v7 )
  {
    if ( !*(_DWORD *)(a1 + 112) )
      CVDecompressSetPalette(v7, *(_DWORD *)(a1 + 96));
  }
  return 0;
}

```

## disassembly

```asm
0x10010148  mov     edi, edi
0x1001014a  push    ebx
0x1001014b  push    esi
0x1001014c  mov     ebx, edx
0x1001014e  mov     esi, ecx
0x10010150  push    edi
0x10010151  test    ebx, ebx
0x10010153  jz      short loc_100101B1
0x10010155  cmp     word ptr [ebx+0Eh], 8
0x1001015a  jz      short loc_10010164
0x1001015c  push    0FFFFFFFEh
0x1001015e  pop     eax
0x1001015f  jmp     loc_100101E8
0x10010164  mov     edi, [esi+64h]
0x10010167  test    edi, edi
0x10010169  jnz     short loc_10010185
0x1001016b  push    400h; uBytes
0x10010170  push    40h ; '@'; uFlags
0x10010172  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x10010178  mov     edi, eax
0x1001017a  mov     [esi+64h], edi
0x1001017d  test    edi, edi
0x1001017f  jnz     short loc_10010185
0x10010181  push    0FFFFFFFDh
0x10010183  jmp     short loc_1001015E
0x10010185  mov     ecx, [ebx+20h]
0x10010188  mov     edx, 100h
0x1001018d  lea     eax, [ecx-1]
0x10010190  cmp     eax, 0FEh
0x10010195  cmovbe  edx, ecx
0x10010198  mov     eax, edx
0x1001019a  mov     [esi+60h], edx
0x1001019d  shl     eax, 2
0x100101a0  push    eax; Size
0x100101a1  mov     eax, [ebx]
0x100101a3  add     eax, ebx
0x100101a5  push    eax; Src
0x100101a6  push    edi; void *
0x100101a7  call    _memcpy
0x100101ac  add     esp, 0Ch
0x100101af  jmp     short loc_100101CE
0x100101b1  cmp     dword ptr [esi+64h], 0
0x100101b5  jz      short loc_100101C7
0x100101b7  push    dword ptr [esi+64h]; hMem
0x100101ba  call    ds:__imp__LocalFree@4; LocalFree(x)
0x100101c0  mov     dword ptr [esi+64h], 0
0x100101c7  mov     dword ptr [esi+60h], 0
0x100101ce  mov     ecx, [esi+5Ch]
0x100101d1  test    ecx, ecx
0x100101d3  jz      short loc_100101E6
0x100101d5  cmp     dword ptr [esi+70h], 0
0x100101d9  jnz     short loc_100101E6
0x100101db  push    dword ptr [esi+60h]
0x100101de  mov     edx, [esi+64h]
0x100101e1  call    _CVDecompressSetPalette@12; CVDecompressSetPalette(x,x,x)
0x100101e6  xor     eax, eax
0x100101e8  pop     edi
0x100101e9  pop     esi
0x100101ea  pop     ebx
0x100101eb  retn
```
