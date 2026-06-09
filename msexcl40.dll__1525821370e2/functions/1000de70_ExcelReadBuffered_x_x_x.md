# ExcelReadBuffered(x,x,x)

- ea: `0x1000de70`
- end: `0x1000ded7`
- name: `_ExcelReadBuffered@12`
- size: `103`
- prototype: `int __fastcall(size_t *, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1000eec0`

## callees

- `0x1000de70`
- `0x10025986`
- `0x10025ed1`

## pseudocode

```c
int __fastcall ExcelReadBuffered(size_t *a1, unsigned int a2, _DWORD *a3)
{
  _BYTE *v5; // eax

  if ( a2 <= g_cbCurrentSize )
    return BFReadFile(a1, pExcelRecordBuffer, a2, a3);
  v5 = (_BYTE *)MemReAllocate(pExcelRecordBuffer);
  pExcelRecordBuffer = v5;
  if ( !v5 )
    return -2;
  g_cbCurrentSize = a2;
  return BFReadFile(a1, v5, a2, a3);
}

```

## disassembly

```asm
0x1000de70  mov     edi, edi
0x1000de72  push    ebp
0x1000de73  mov     ebp, esp
0x1000de75  push    ecx
0x1000de76  push    esi
0x1000de77  mov     esi, edx
0x1000de79  push    edi
0x1000de7a  mov     edi, ecx
0x1000de7c  cmp     esi, _g_cbCurrentSize
0x1000de82  jbe     short loc_1000DEBE
0x1000de84  mov     ecx, _pExcelRecordBuffer; Src
0x1000de8a  call    _MemReAllocate@8; MemReAllocate(x,x)
0x1000de8f  mov     _pExcelRecordBuffer, eax
0x1000de94  test    eax, eax
0x1000de96  jnz     short loc_1000DEA4
0x1000de98  mov     eax, 0FFFFFFFEh
0x1000de9d  pop     edi
0x1000de9e  pop     esi
0x1000de9f  pop     ecx
0x1000dea0  pop     ebp
0x1000dea1  retn    4
0x1000dea4  push    [ebp+arg_0]
0x1000dea7  mov     edx, eax
0x1000dea9  mov     _g_cbCurrentSize, esi
0x1000deaf  push    esi
0x1000deb0  mov     ecx, edi
0x1000deb2  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x1000deb7  pop     edi
0x1000deb8  pop     esi
0x1000deb9  pop     ecx
0x1000deba  pop     ebp
0x1000debb  retn    4
0x1000debe  push    [ebp+arg_0]
0x1000dec1  mov     eax, _pExcelRecordBuffer
0x1000dec6  mov     ecx, edi
0x1000dec8  push    esi
0x1000dec9  mov     edx, eax
0x1000decb  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x1000ded0  pop     edi
0x1000ded1  pop     esi
0x1000ded2  pop     ecx
0x1000ded3  pop     ebp
0x1000ded4  retn    4
```
