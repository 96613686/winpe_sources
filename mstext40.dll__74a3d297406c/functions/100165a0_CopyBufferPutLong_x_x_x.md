# CopyBufferPutLong(x,x,x)

- ea: `0x100165a0`
- end: `0x10016618`
- name: `_CopyBufferPutLong@12`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x100165a0`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutLong(int a1, int a2, int a3)
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
  v3[2] = 4;
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
0x100165a0  push    esi
0x100165a1  mov     esi, [esp+4+arg_4]
0x100165a5  push    edi
0x100165a6  mov     edi, [esp+8+arg_0]
0x100165aa  push    esi
0x100165ab  push    edi
0x100165ac  call    RemoveCopyItem
0x100165b1  push    220h; Size
0x100165b6  call    _MemAllocate@4; MemAllocate(x)
0x100165bb  mov     ecx, eax
0x100165bd  test    ecx, ecx
0x100165bf  jnz     short loc_100165CB
0x100165c1  pop     edi
0x100165c2  mov     eax, 0FFFFFC0Dh
0x100165c7  pop     esi
0x100165c8  retn    0Ch
0x100165cb  mov     eax, [esi+18h]
0x100165ce  xor     edx, edx
0x100165d0  mov     [ecx+4], eax
0x100165d3  mov     eax, [esp+8+arg_8]
0x100165d7  mov     dword ptr [ecx+8], 4
0x100165de  mov     [ecx+18h], eax
0x100165e1  mov     eax, [edi+44h]
0x100165e4  test    eax, eax
0x100165e6  jz      short loc_1001660C
0x100165e8  mov     esi, [ecx+4]
0x100165eb  jmp     short loc_100165F0
0x100165f0  cmp     [eax+4], esi
0x100165f3  ja      short loc_100165FD
0x100165f5  mov     edx, eax
0x100165f7  mov     eax, [eax]
0x100165f9  test    eax, eax
0x100165fb  jnz     short loc_100165F0
0x100165fd  test    edx, edx
0x100165ff  jz      short loc_1001660C
0x10016601  mov     [edx], ecx
0x10016603  pop     edi
0x10016604  mov     [ecx], eax
0x10016606  xor     eax, eax
0x10016608  pop     esi
0x10016609  retn    0Ch
0x1001660c  mov     [edi+44h], ecx
0x1001660f  pop     edi
0x10016610  mov     [ecx], eax
0x10016612  xor     eax, eax
0x10016614  pop     esi
0x10016615  retn    0Ch
```
