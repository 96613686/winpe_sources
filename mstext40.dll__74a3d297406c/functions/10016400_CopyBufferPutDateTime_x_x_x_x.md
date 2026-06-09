# CopyBufferPutDateTime(x,x,x,x)

- ea: `0x10016400`
- end: `0x10016478`
- name: `_CopyBufferPutDateTime@16`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x10016400`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutDateTime(int a1, int a2, __int64 a3)
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
  v3[2] = 8;
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
0x10016400  push    esi
0x10016401  mov     esi, [esp+4+arg_4]
0x10016405  push    edi
0x10016406  mov     edi, [esp+8+arg_0]
0x1001640a  push    esi
0x1001640b  push    edi
0x1001640c  call    RemoveCopyItem
0x10016411  push    220h; Size
0x10016416  call    _MemAllocate@4; MemAllocate(x)
0x1001641b  mov     ecx, eax
0x1001641d  test    ecx, ecx
0x1001641f  jnz     short loc_1001642B
0x10016421  pop     edi
0x10016422  mov     eax, 0FFFFFC0Dh
0x10016427  pop     esi
0x10016428  retn    10h
0x1001642b  mov     eax, [esi+18h]
0x1001642e  xor     edx, edx
0x10016430  movsd   xmm0, [esp+8+arg_8]
0x10016436  mov     [ecx+4], eax
0x10016439  mov     dword ptr [ecx+8], 8
0x10016440  movsd   qword ptr [ecx+18h], xmm0
0x10016445  mov     eax, [edi+44h]
0x10016448  test    eax, eax
0x1001644a  jz      short loc_1001646C
0x1001644c  mov     esi, [ecx+4]
0x1001644f  nop
0x10016450  cmp     [eax+4], esi
0x10016453  ja      short loc_1001645D
0x10016455  mov     edx, eax
0x10016457  mov     eax, [eax]
0x10016459  test    eax, eax
0x1001645b  jnz     short loc_10016450
0x1001645d  test    edx, edx
0x1001645f  jz      short loc_1001646C
0x10016461  mov     [edx], ecx
0x10016463  pop     edi
0x10016464  mov     [ecx], eax
0x10016466  xor     eax, eax
0x10016468  pop     esi
0x10016469  retn    10h
0x1001646c  mov     [edi+44h], ecx
0x1001646f  pop     edi
0x10016470  mov     [ecx], eax
0x10016472  xor     eax, eax
0x10016474  pop     esi
0x10016475  retn    10h
```
