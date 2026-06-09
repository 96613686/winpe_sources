# CopyBufferPutCurrency(x,x,x)

- ea: `0x10016380`
- end: `0x100163fb`
- name: `_CopyBufferPutCurrency@12`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x10016380`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutCurrency(int a1, int a2, _DWORD *a3)
{
  _DWORD *v3; // eax
  _DWORD *v4; // edx
  _DWORD *v6; // ecx
  _DWORD *v7; // eax

  RemoveCopyItem(a1, a2);
  v3 = MemAllocate(544);
  v4 = v3;
  if ( !v3 )
    return -1011;
  v3[1] = *(_DWORD *)(a2 + 24);
  v3[2] = 5;
  v3[6] = *a3;
  v6 = 0;
  v3[7] = a3[1];
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
0x10016380  push    esi
0x10016381  mov     esi, [esp+4+arg_4]
0x10016385  push    edi
0x10016386  mov     edi, [esp+8+arg_0]
0x1001638a  push    esi
0x1001638b  push    edi
0x1001638c  call    RemoveCopyItem
0x10016391  push    220h; Size
0x10016396  call    _MemAllocate@4; MemAllocate(x)
0x1001639b  mov     edx, eax
0x1001639d  test    edx, edx
0x1001639f  jnz     short loc_100163AB
0x100163a1  pop     edi
0x100163a2  mov     eax, 0FFFFFC0Dh
0x100163a7  pop     esi
0x100163a8  retn    0Ch
0x100163ab  mov     ecx, [esp+8+arg_8]
0x100163af  mov     eax, [esi+18h]
0x100163b2  mov     [edx+4], eax
0x100163b5  mov     dword ptr [edx+8], 5
0x100163bc  mov     eax, [ecx]
0x100163be  mov     [edx+18h], eax
0x100163c1  mov     eax, [ecx+4]
0x100163c4  xor     ecx, ecx
0x100163c6  mov     [edx+1Ch], eax
0x100163c9  mov     eax, [edi+44h]
0x100163cc  test    eax, eax
0x100163ce  jz      short loc_100163EF
0x100163d0  mov     esi, [edx+4]
0x100163d3  cmp     [eax+4], esi
0x100163d6  ja      short loc_100163E0
0x100163d8  mov     ecx, eax
0x100163da  mov     eax, [eax]
0x100163dc  test    eax, eax
0x100163de  jnz     short loc_100163D3
0x100163e0  test    ecx, ecx
0x100163e2  jz      short loc_100163EF
0x100163e4  mov     [ecx], edx
0x100163e6  pop     edi
0x100163e7  mov     [edx], eax
0x100163e9  xor     eax, eax
0x100163eb  pop     esi
0x100163ec  retn    0Ch
0x100163ef  mov     [edi+44h], edx
0x100163f2  pop     edi
0x100163f3  mov     [edx], eax
0x100163f5  xor     eax, eax
0x100163f7  pop     esi
0x100163f8  retn    0Ch
```
