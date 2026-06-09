# CopyBufferPutBinary(x,x,x,x,x)

- ea: `0x100161d0`
- end: `0x1001627c`
- name: `_CopyBufferPutBinary@20`
- size: `172`
- prototype: `int __stdcall(int, int, void *Src, size_t Size, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x100161d0`
- `0x10016a10`
- `0x1002ba60`

## pseudocode

```c
int __stdcall CopyBufferPutBinary(int a1, int a2, void *Src, size_t Size, int a5)
{
  _DWORD *v5; // esi
  void *v6; // eax
  _DWORD *v8; // ecx
  _DWORD *v9; // eax

  RemoveCopyItem(a1, a2);
  v5 = (_DWORD *)MemAllocate(0x220u);
  if ( !v5 )
    return -1011;
  v5[1] = *(_DWORD *)(a2 + 24);
  v5[5] = a5;
  v5[2] = 9;
  v6 = (void *)MemAllocate(Size + 1);
  if ( !v6 )
  {
    MemFree(v5);
    return -1011;
  }
  v5[6] = Size;
  v5[7] = v6;
  memcpy(v6, Src, Size);
  *(_BYTE *)(v5[7] + v5[6]) = 0;
  v8 = 0;
  v9 = *(_DWORD **)(a1 + 68);
  if ( !v9 )
    goto LABEL_10;
  do
  {
    if ( v9[1] > v5[1] )
      break;
    v8 = v9;
    v9 = (_DWORD *)*v9;
  }
  while ( v9 );
  if ( v8 )
  {
    *v8 = v5;
    *v5 = v9;
    return 0;
  }
  else
  {
LABEL_10:
    *(_DWORD *)(a1 + 68) = v5;
    *v5 = v9;
    return 0;
  }
}

```

## disassembly

```asm
0x100161d0  push    ebx
0x100161d1  mov     ebx, [esp+4+arg_4]
0x100161d5  push    esi
0x100161d6  push    edi
0x100161d7  mov     edi, [esp+0Ch+arg_0]
0x100161db  push    ebx
0x100161dc  push    edi
0x100161dd  call    RemoveCopyItem
0x100161e2  push    220h; Size
0x100161e7  call    _MemAllocate@4; MemAllocate(x)
0x100161ec  mov     esi, eax
0x100161ee  test    esi, esi
0x100161f0  jz      short loc_1001621D
0x100161f2  mov     eax, [ebx+18h]
0x100161f5  mov     ebx, [esp+0Ch+Size]
0x100161f9  mov     [esi+4], eax
0x100161fc  mov     eax, [esp+0Ch+arg_10]
0x10016200  mov     [esi+14h], eax
0x10016203  lea     eax, [ebx+1]
0x10016206  mov     dword ptr [esi+8], 9
0x1001620d  push    eax; Size
0x1001620e  call    _MemAllocate@4; MemAllocate(x)
0x10016213  test    eax, eax
0x10016215  jnz     short loc_10016228
0x10016217  push    esi
0x10016218  call    _MemFree@4; MemFree(x)
0x1001621d  pop     edi
0x1001621e  pop     esi
0x1001621f  mov     eax, 0FFFFFC0Dh
0x10016224  pop     ebx
0x10016225  retn    14h
0x10016228  push    ebx; Size
0x10016229  push    [esp+10h+Src]; Src
0x1001622d  mov     [esi+18h], ebx
0x10016230  push    eax; void *
0x10016231  mov     [esi+1Ch], eax
0x10016234  call    _memcpy
0x10016239  mov     ecx, [esi+1Ch]
0x1001623c  add     esp, 0Ch
0x1001623f  mov     eax, [esi+18h]
0x10016242  mov     byte ptr [ecx+eax], 0
0x10016246  xor     ecx, ecx
0x10016248  mov     eax, [edi+44h]
0x1001624b  test    eax, eax
0x1001624d  jz      short loc_1001626F
0x1001624f  mov     edx, [esi+4]
0x10016252  cmp     [eax+4], edx
0x10016255  ja      short loc_1001625F
0x10016257  mov     ecx, eax
0x10016259  mov     eax, [eax]
0x1001625b  test    eax, eax
0x1001625d  jnz     short loc_10016252
0x1001625f  test    ecx, ecx
0x10016261  jz      short loc_1001626F
0x10016263  mov     [ecx], esi
0x10016265  pop     edi
0x10016266  mov     [esi], eax
0x10016268  xor     eax, eax
0x1001626a  pop     esi
0x1001626b  pop     ebx
0x1001626c  retn    14h
0x1001626f  mov     [edi+44h], esi
0x10016272  pop     edi
0x10016273  mov     [esi], eax
0x10016275  xor     eax, eax
0x10016277  pop     esi
0x10016278  pop     ebx
0x10016279  retn    14h
```
