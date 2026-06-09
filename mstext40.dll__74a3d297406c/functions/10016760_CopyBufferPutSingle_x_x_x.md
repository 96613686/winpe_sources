# CopyBufferPutSingle(x,x,x)

- ea: `0x10016760`
- end: `0x100167da`
- name: `_CopyBufferPutSingle@12`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x10016760`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutSingle(int a1, int a2, float a3)
{
  _DWORD *v3; // eax
  _DWORD *v4; // ecx
  _DWORD *v6; // edx
  _DWORD *v7; // eax

  RemoveCopyItem(a1, a2);
  v3 = MemAllocate(544);
  v4 = v3;
  if ( !v3 )
    return -1011;
  v6 = 0;
  v3[1] = *(_DWORD *)(a2 + 24);
  v3[2] = 6;
  *((double *)v3 + 3) = a3;
  v7 = *(_DWORD **)(a1 + 68);
  if ( !v7 )
    goto LABEL_8;
  do
  {
    if ( v7[1] > v4[1] )
      break;
    v6 = v7;
    v7 = (_DWORD *)*v7;
  }
  while ( v7 );
  if ( v6 )
  {
    *v6 = v4;
    *v4 = v7;
    return 0;
  }
  else
  {
LABEL_8:
    *(_DWORD *)(a1 + 68) = v4;
    *v4 = v7;
    return 0;
  }
}

```

## disassembly

```asm
0x10016760  push    esi
0x10016761  mov     esi, [esp+4+arg_4]
0x10016765  push    edi
0x10016766  mov     edi, [esp+8+arg_0]
0x1001676a  push    esi
0x1001676b  push    edi
0x1001676c  call    RemoveCopyItem
0x10016771  push    220h; Size
0x10016776  call    _MemAllocate@4; MemAllocate(x)
0x1001677b  mov     ecx, eax
0x1001677d  test    ecx, ecx
0x1001677f  jnz     short loc_1001678B
0x10016781  pop     edi
0x10016782  mov     eax, 0FFFFFC0Dh
0x10016787  pop     esi
0x10016788  retn    0Ch
0x1001678b  movss   xmm0, [esp+8+arg_8]
0x10016791  xor     edx, edx
0x10016793  mov     eax, [esi+18h]
0x10016796  cvtps2pd xmm0, xmm0
0x10016799  mov     [ecx+4], eax
0x1001679c  mov     dword ptr [ecx+8], 6
0x100167a3  movsd   qword ptr [ecx+18h], xmm0
0x100167a8  mov     eax, [edi+44h]
0x100167ab  test    eax, eax
0x100167ad  jz      short loc_100167CE
0x100167af  mov     esi, [ecx+4]
0x100167b2  cmp     [eax+4], esi
0x100167b5  ja      short loc_100167BF
0x100167b7  mov     edx, eax
0x100167b9  mov     eax, [eax]
0x100167bb  test    eax, eax
0x100167bd  jnz     short loc_100167B2
0x100167bf  test    edx, edx
0x100167c1  jz      short loc_100167CE
0x100167c3  mov     [edx], ecx
0x100167c5  pop     edi
0x100167c6  mov     [ecx], eax
0x100167c8  xor     eax, eax
0x100167ca  pop     esi
0x100167cb  retn    0Ch
0x100167ce  mov     [edi+44h], ecx
0x100167d1  pop     edi
0x100167d2  mov     [ecx], eax
0x100167d4  xor     eax, eax
0x100167d6  pop     esi
0x100167d7  retn    0Ch
```
