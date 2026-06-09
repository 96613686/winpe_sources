# CopyBufferPutDecimal(x,x,x)

- ea: `0x10016480`
- end: `0x100164f9`
- name: `_CopyBufferPutDecimal@12`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x10016480`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutDecimal(int a1, int a2, const __m128i *a3)
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
  v3[2] = 16;
  *(__m128i *)(v3 + 6) = _mm_loadu_si128(a3);
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
0x10016480  push    esi
0x10016481  mov     esi, [esp+4+arg_4]
0x10016485  push    edi
0x10016486  mov     edi, [esp+8+arg_0]
0x1001648a  push    esi
0x1001648b  push    edi
0x1001648c  call    RemoveCopyItem
0x10016491  push    220h; Size
0x10016496  call    _MemAllocate@4; MemAllocate(x)
0x1001649b  mov     ecx, eax
0x1001649d  test    ecx, ecx
0x1001649f  jnz     short loc_100164AB
0x100164a1  pop     edi
0x100164a2  mov     eax, 0FFFFFC0Dh
0x100164a7  pop     esi
0x100164a8  retn    0Ch
0x100164ab  mov     eax, [esi+18h]
0x100164ae  xor     edx, edx
0x100164b0  mov     [ecx+4], eax
0x100164b3  mov     eax, [esp+8+arg_8]
0x100164b7  mov     dword ptr [ecx+8], 10h
0x100164be  movdqu  xmm0, xmmword ptr [eax]
0x100164c2  movdqu  xmmword ptr [ecx+18h], xmm0
0x100164c7  mov     eax, [edi+44h]
0x100164ca  test    eax, eax
0x100164cc  jz      short loc_100164ED
0x100164ce  mov     esi, [ecx+4]
0x100164d1  cmp     [eax+4], esi
0x100164d4  ja      short loc_100164DE
0x100164d6  mov     edx, eax
0x100164d8  mov     eax, [eax]
0x100164da  test    eax, eax
0x100164dc  jnz     short loc_100164D1
0x100164de  test    edx, edx
0x100164e0  jz      short loc_100164ED
0x100164e2  mov     [edx], ecx
0x100164e4  pop     edi
0x100164e5  mov     [ecx], eax
0x100164e7  xor     eax, eax
0x100164e9  pop     esi
0x100164ea  retn    0Ch
0x100164ed  mov     [edi+44h], ecx
0x100164f0  pop     edi
0x100164f1  mov     [ecx], eax
0x100164f3  xor     eax, eax
0x100164f5  pop     esi
0x100164f6  retn    0Ch
```
