# CopyBufferPutShort(x,x,x)

- ea: `0x100166e0`
- end: `0x10016758`
- name: `_CopyBufferPutShort@12`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x100166e0`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutShort(int a1, int a2, __int16 a3)
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
  v3[2] = 3;
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
0x100166e0  push    esi
0x100166e1  mov     esi, [esp+4+arg_4]
0x100166e5  push    edi
0x100166e6  mov     edi, [esp+8+arg_0]
0x100166ea  push    esi
0x100166eb  push    edi
0x100166ec  call    RemoveCopyItem
0x100166f1  push    220h; Size
0x100166f6  call    _MemAllocate@4; MemAllocate(x)
0x100166fb  mov     ecx, eax
0x100166fd  test    ecx, ecx
0x100166ff  jnz     short loc_1001670B
0x10016701  pop     edi
0x10016702  mov     eax, 0FFFFFC0Dh
0x10016707  pop     esi
0x10016708  retn    0Ch
0x1001670b  mov     eax, [esi+18h]
0x1001670e  xor     edx, edx
0x10016710  mov     [ecx+4], eax
0x10016713  mov     eax, [esp+8+arg_8]
0x10016717  cwde
0x10016718  mov     dword ptr [ecx+8], 3
0x1001671f  mov     [ecx+18h], eax
0x10016722  mov     eax, [edi+44h]
0x10016725  test    eax, eax
0x10016727  jz      short loc_1001674C
0x10016729  mov     esi, [ecx+4]
0x1001672c  lea     esp, [esp+0]
0x10016730  cmp     [eax+4], esi
0x10016733  ja      short loc_1001673D
0x10016735  mov     edx, eax
0x10016737  mov     eax, [eax]
0x10016739  test    eax, eax
0x1001673b  jnz     short loc_10016730
0x1001673d  test    edx, edx
0x1001673f  jz      short loc_1001674C
0x10016741  mov     [edx], ecx
0x10016743  pop     edi
0x10016744  mov     [ecx], eax
0x10016746  xor     eax, eax
0x10016748  pop     esi
0x10016749  retn    0Ch
0x1001674c  mov     [edi+44h], ecx
0x1001674f  pop     edi
0x10016750  mov     [ecx], eax
0x10016752  xor     eax, eax
0x10016754  pop     esi
0x10016755  retn    0Ch
```
