# CopyBufferPutLongText(x,x,x,x,x)

- ea: `0x10016620`
- end: `0x100166da`
- name: `_CopyBufferPutLongText@20`
- size: `186`
- prototype: `int __stdcall(int, int, void *Src, size_t Size, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x10016620`
- `0x10016a10`
- `0x1002ba60`

## pseudocode

```c
int __stdcall CopyBufferPutLongText(int a1, int a2, void *Src, size_t Size, int a5)
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
  v5[2] = 12;
  v6 = (void *)MemAllocate(Size + 2);
  if ( !v6 )
  {
    MemFree(v5);
    return -1011;
  }
  v5[7] = v6;
  v5[6] = Size >> 1;
  memcpy(v6, Src, Size);
  *(_WORD *)(v5[7] + 2 * v5[6]) = 0;
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
0x10016620  push    ebx
0x10016621  mov     ebx, [esp+4+arg_4]
0x10016625  push    esi
0x10016626  push    edi
0x10016627  mov     edi, [esp+0Ch+arg_0]
0x1001662b  push    ebx
0x1001662c  push    edi
0x1001662d  call    RemoveCopyItem
0x10016632  push    220h; Size
0x10016637  call    _MemAllocate@4; MemAllocate(x)
0x1001663c  mov     esi, eax
0x1001663e  test    esi, esi
0x10016640  jz      short loc_1001666F
0x10016642  mov     eax, [ebx+18h]
0x10016645  mov     ebx, [esp+0Ch+Size]
0x10016649  mov     [esi+4], eax
0x1001664c  mov     eax, [esp+0Ch+arg_10]
0x10016650  mov     [esi+14h], eax
0x10016653  lea     eax, [ebx+2]
0x10016656  mov     dword ptr [esi+8], 0Ch
0x1001665d  push    eax; Size
0x1001665e  call    _MemAllocate@4; MemAllocate(x)
0x10016663  mov     ecx, eax
0x10016665  test    ecx, ecx
0x10016667  jnz     short loc_1001667A
0x10016669  push    esi
0x1001666a  call    _MemFree@4; MemFree(x)
0x1001666f  pop     edi
0x10016670  pop     esi
0x10016671  mov     eax, 0FFFFFC0Dh
0x10016676  pop     ebx
0x10016677  retn    14h
0x1001667a  push    ebx; Size
0x1001667b  push    [esp+10h+Src]; Src
0x1001667f  mov     eax, ebx
0x10016681  mov     [esi+1Ch], ecx
0x10016684  shr     eax, 1
0x10016686  push    ecx; void *
0x10016687  mov     [esi+18h], eax
0x1001668a  call    _memcpy
0x1001668f  mov     ecx, [esi+18h]
0x10016692  xor     edx, edx
0x10016694  mov     eax, [esi+1Ch]
0x10016697  add     esp, 0Ch
0x1001669a  mov     [eax+ecx*2], dx
0x1001669e  xor     ecx, ecx
0x100166a0  mov     eax, [edi+44h]
0x100166a3  test    eax, eax
0x100166a5  jz      short loc_100166CD
0x100166a7  mov     edx, [esi+4]
0x100166aa  lea     ebx, [ebx+0]
0x100166b0  cmp     [eax+4], edx
0x100166b3  ja      short loc_100166BD
0x100166b5  mov     ecx, eax
0x100166b7  mov     eax, [eax]
0x100166b9  test    eax, eax
0x100166bb  jnz     short loc_100166B0
0x100166bd  test    ecx, ecx
0x100166bf  jz      short loc_100166CD
0x100166c1  mov     [ecx], esi
0x100166c3  pop     edi
0x100166c4  mov     [esi], eax
0x100166c6  xor     eax, eax
0x100166c8  pop     esi
0x100166c9  pop     ebx
0x100166ca  retn    14h
0x100166cd  mov     [edi+44h], esi
0x100166d0  pop     edi
0x100166d1  mov     [esi], eax
0x100166d3  xor     eax, eax
0x100166d5  pop     esi
0x100166d6  pop     ebx
0x100166d7  retn    14h
```
