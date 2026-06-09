# CopyBufferPutDouble(x,x,x,x)

- ea: `0x10016500`
- end: `0x10016578`
- name: `_CopyBufferPutDouble@16`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x10016500`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutDouble(int a1, int a2, __int64 a3)
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
  v3[2] = 7;
  *((_QWORD *)v3 + 3) = a3;
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
0x10016500  push    esi
0x10016501  mov     esi, [esp+4+arg_4]
0x10016505  push    edi
0x10016506  mov     edi, [esp+8+arg_0]
0x1001650a  push    esi
0x1001650b  push    edi
0x1001650c  call    RemoveCopyItem
0x10016511  push    220h; Size
0x10016516  call    _MemAllocate@4; MemAllocate(x)
0x1001651b  mov     ecx, eax
0x1001651d  test    ecx, ecx
0x1001651f  jnz     short loc_1001652B
0x10016521  pop     edi
0x10016522  mov     eax, 0FFFFFC0Dh
0x10016527  pop     esi
0x10016528  retn    10h
0x1001652b  mov     eax, [esi+18h]
0x1001652e  xor     edx, edx
0x10016530  movsd   xmm0, [esp+8+arg_8]
0x10016536  mov     [ecx+4], eax
0x10016539  mov     dword ptr [ecx+8], 7
0x10016540  movsd   qword ptr [ecx+18h], xmm0
0x10016545  mov     eax, [edi+44h]
0x10016548  test    eax, eax
0x1001654a  jz      short loc_1001656C
0x1001654c  mov     esi, [ecx+4]
0x1001654f  nop
0x10016550  cmp     [eax+4], esi
0x10016553  ja      short loc_1001655D
0x10016555  mov     edx, eax
0x10016557  mov     eax, [eax]
0x10016559  test    eax, eax
0x1001655b  jnz     short loc_10016550
0x1001655d  test    edx, edx
0x1001655f  jz      short loc_1001656C
0x10016561  mov     [edx], ecx
0x10016563  pop     edi
0x10016564  mov     [ecx], eax
0x10016566  xor     eax, eax
0x10016568  pop     esi
0x10016569  retn    10h
0x1001656c  mov     [edi+44h], ecx
0x1001656f  pop     edi
0x10016570  mov     [ecx], eax
0x10016572  xor     eax, eax
0x10016574  pop     esi
0x10016575  retn    10h
```
