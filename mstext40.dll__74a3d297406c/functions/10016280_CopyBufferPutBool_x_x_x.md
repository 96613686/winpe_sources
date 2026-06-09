# CopyBufferPutBool(x,x,x)

- ea: `0x10016280`
- end: `0x100162f8`
- name: `_CopyBufferPutBool@12`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x10016280`
- `0x10016a10`

## pseudocode

```c
int __stdcall CopyBufferPutBool(int a1, int a2, char a3)
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
  v3[2] = 1;
  *((_BYTE *)v3 + 24) = a3;
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
0x10016280  push    esi
0x10016281  mov     esi, [esp+4+arg_4]
0x10016285  push    edi
0x10016286  mov     edi, [esp+8+arg_0]
0x1001628a  push    esi
0x1001628b  push    edi
0x1001628c  call    RemoveCopyItem
0x10016291  push    220h; Size
0x10016296  call    _MemAllocate@4; MemAllocate(x)
0x1001629b  mov     ecx, eax
0x1001629d  test    ecx, ecx
0x1001629f  jnz     short loc_100162AB
0x100162a1  pop     edi
0x100162a2  mov     eax, 0FFFFFC0Dh
0x100162a7  pop     esi
0x100162a8  retn    0Ch
0x100162ab  mov     eax, [esi+18h]
0x100162ae  xor     edx, edx
0x100162b0  mov     [ecx+4], eax
0x100162b3  mov     al, [esp+8+arg_8]
0x100162b7  mov     dword ptr [ecx+8], 1
0x100162be  mov     [ecx+18h], al
0x100162c1  mov     eax, [edi+44h]
0x100162c4  test    eax, eax
0x100162c6  jz      short loc_100162EC
0x100162c8  mov     esi, [ecx+4]
0x100162cb  jmp     short loc_100162D0
0x100162d0  cmp     [eax+4], esi
0x100162d3  ja      short loc_100162DD
0x100162d5  mov     edx, eax
0x100162d7  mov     eax, [eax]
0x100162d9  test    eax, eax
0x100162db  jnz     short loc_100162D0
0x100162dd  test    edx, edx
0x100162df  jz      short loc_100162EC
0x100162e1  mov     [edx], ecx
0x100162e3  pop     edi
0x100162e4  mov     [ecx], eax
0x100162e6  xor     eax, eax
0x100162e8  pop     esi
0x100162e9  retn    0Ch
0x100162ec  mov     [edi+44h], ecx
0x100162ef  pop     edi
0x100162f0  mov     [ecx], eax
0x100162f2  xor     eax, eax
0x100162f4  pop     esi
0x100162f5  retn    0Ch
```
