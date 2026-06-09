# CopyBufferPutByte(x,x,x)

- ea: `0x10016300`
- end: `0x10016378`
- name: `_CopyBufferPutByte@12`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x10016300`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutByte(int a1, int a2, unsigned __int8 a3)
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
  v3[2] = 2;
  v3[6] = a3;
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
0x10016300  push    esi
0x10016301  mov     esi, [esp+4+arg_4]
0x10016305  push    edi
0x10016306  mov     edi, [esp+8+arg_0]
0x1001630a  push    esi
0x1001630b  push    edi
0x1001630c  call    RemoveCopyItem
0x10016311  push    220h; Size
0x10016316  call    _MemAllocate@4; MemAllocate(x)
0x1001631b  mov     ecx, eax
0x1001631d  test    ecx, ecx
0x1001631f  jnz     short loc_1001632B
0x10016321  pop     edi
0x10016322  mov     eax, 0FFFFFC0Dh
0x10016327  pop     esi
0x10016328  retn    0Ch
0x1001632b  mov     eax, [esi+18h]
0x1001632e  xor     edx, edx
0x10016330  mov     [ecx+4], eax
0x10016333  mov     eax, [esp+8+arg_8]
0x10016337  movzx   eax, al
0x1001633a  mov     dword ptr [ecx+8], 2
0x10016341  mov     [ecx+18h], eax
0x10016344  mov     eax, [edi+44h]
0x10016347  test    eax, eax
0x10016349  jz      short loc_1001636C
0x1001634b  mov     esi, [ecx+4]
0x1001634e  mov     edi, edi
0x10016350  cmp     [eax+4], esi
0x10016353  ja      short loc_1001635D
0x10016355  mov     edx, eax
0x10016357  mov     eax, [eax]
0x10016359  test    eax, eax
0x1001635b  jnz     short loc_10016350
0x1001635d  test    edx, edx
0x1001635f  jz      short loc_1001636C
0x10016361  mov     [edx], ecx
0x10016363  pop     edi
0x10016364  mov     [ecx], eax
0x10016366  xor     eax, eax
0x10016368  pop     esi
0x10016369  retn    0Ch
0x1001636c  mov     [edi+44h], ecx
0x1001636f  pop     edi
0x10016370  mov     [ecx], eax
0x10016372  xor     eax, eax
0x10016374  pop     esi
0x10016375  retn    0Ch
```
