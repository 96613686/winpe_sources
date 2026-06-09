# ReadFileBlock

- ea: `0x1001da00`
- end: `0x1001da5c`
- name: `ReadFileBlock`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1001d6a0`
- `0x1001d770`

## callees

- `0x1000ba30`
- `0x1001da00`

## pseudocode

```c
int __thiscall ReadFileBlock(void *this, int a2)
{
  DWORD v2; // ecx
  int result; // eax
  int v4; // edx
  int v5; // eax
  void *v6; // [esp-8h] [ebp-Ch]
  DWORD v7; // [esp-4h] [ebp-8h]

  v7 = *(_DWORD *)(a2 + 52);
  v6 = *(void **)(a2 + 4);
  *(_DWORD *)(a2 + 72) = *(_DWORD *)(a2 + 68);
  v2 = DOSReadFile(this, *(HANDLE *)(a2 + 20), v6, v7);
  if ( v2 == 0xFFFF )
    return -5;
  v4 = *(_DWORD *)(a2 + 68);
  if ( v4 + *(_DWORD *)(a2 + 52) > *(_DWORD *)(a2 + 76) )
    v2 = *(_DWORD *)(a2 + 76) - v4;
  *(_DWORD *)a2 = v2;
  *(_DWORD *)(a2 + 68) = v4 + v2;
  v5 = *(_DWORD *)(a2 + 4);
  *(_DWORD *)(a2 + 8) = v5;
  *(_DWORD *)(a2 + 56) = v5;
  result = 0;
  *(_DWORD *)(a2 + 64) = 1;
  return result;
}

```

## disassembly

```asm
0x1001da00  push    esi
0x1001da01  mov     esi, [esp+4+arg_0]
0x1001da05  push    dword ptr [esi+34h]; nNumberOfBytesToRead
0x1001da08  mov     eax, [esi+44h]
0x1001da0b  push    dword ptr [esi+4]; lpBuffer
0x1001da0e  mov     [esi+48h], eax
0x1001da11  push    dword ptr [esi+14h]; hFile
0x1001da14  call    _DOSReadFile@12; DOSReadFile(x,x,x)
0x1001da19  mov     ecx, eax
0x1001da1b  cmp     ecx, 0FFFFh
0x1001da21  jnz     short loc_1001DA2C
0x1001da23  mov     eax, 0FFFFFFFBh
0x1001da28  pop     esi
0x1001da29  retn    4
0x1001da2c  mov     eax, [esi+34h]
0x1001da2f  mov     edx, [esi+44h]
0x1001da32  add     eax, edx
0x1001da34  cmp     eax, [esi+4Ch]
0x1001da37  jle     short loc_1001DA3E
0x1001da39  mov     ecx, [esi+4Ch]
0x1001da3c  sub     ecx, edx
0x1001da3e  lea     eax, [edx+ecx]
0x1001da41  mov     [esi], ecx
0x1001da43  mov     [esi+44h], eax
0x1001da46  mov     eax, [esi+4]
0x1001da49  mov     [esi+8], eax
0x1001da4c  mov     [esi+38h], eax
0x1001da4f  xor     eax, eax
0x1001da51  mov     dword ptr [esi+40h], 1
0x1001da58  pop     esi
0x1001da59  retn    4
```
