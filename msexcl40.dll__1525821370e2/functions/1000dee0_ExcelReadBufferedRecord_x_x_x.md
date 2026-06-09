# ExcelReadBufferedRecord(x,x,x)

- ea: `0x1000dee0`
- end: `0x1000df65`
- name: `_ExcelReadBufferedRecord@12`
- size: `133`
- prototype: `int __fastcall(int, int, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100082d0`
- `0x1000df70`

## callees

- `0x1000dee0`
- `0x10025986`
- `0x10025ed1`

## pseudocode

```c
int __fastcall ExcelReadBufferedRecord(int a1, int a2, _DWORD *a3)
{
  unsigned int v3; // esi
  size_t *v4; // edi
  _BYTE *v5; // eax
  int v6; // eax
  int result; // eax
  int v8; // [esp+8h] [ebp-4h] BYREF

  v3 = *(__int16 *)(a2 + 2);
  v4 = *(size_t **)(a1 + 20);
  if ( v3 <= g_cbCurrentSize )
  {
    v5 = pExcelRecordBuffer;
  }
  else
  {
    v5 = (_BYTE *)MemReAllocate(pExcelRecordBuffer);
    pExcelRecordBuffer = v5;
    if ( !v5 )
    {
      v6 = -2;
      goto LABEL_7;
    }
    g_cbCurrentSize = v3;
  }
  v6 = BFReadFile(v4, v5, v3, &v8);
  if ( !v6 )
  {
    *a3 = pExcelRecordBuffer;
    return 0;
  }
LABEL_7:
  result = dword_10001970[abs32(v6)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x1000dee0  mov     edi, edi
0x1000dee2  push    ebp
0x1000dee3  mov     ebp, esp
0x1000dee5  push    ecx
0x1000dee6  push    esi
0x1000dee7  movsx   esi, word ptr [edx+2]
0x1000deeb  push    edi
0x1000deec  mov     edi, [ecx+14h]
0x1000deef  cmp     esi, _g_cbCurrentSize
0x1000def5  jbe     short loc_1000DF1C
0x1000def7  mov     ecx, _pExcelRecordBuffer; Src
0x1000defd  mov     edx, esi
0x1000deff  call    _MemReAllocate@8; MemReAllocate(x,x)
0x1000df04  mov     _pExcelRecordBuffer, eax
0x1000df09  test    eax, eax
0x1000df0b  jnz     short loc_1000DF14
0x1000df0d  mov     eax, 0FFFFFFFEh
0x1000df12  jmp     short loc_1000DF33
0x1000df14  mov     _g_cbCurrentSize, esi
0x1000df1a  jmp     short loc_1000DF21
0x1000df1c  mov     eax, _pExcelRecordBuffer
0x1000df21  lea     ecx, [ebp+var_4]
0x1000df24  mov     edx, eax
0x1000df26  push    ecx
0x1000df27  push    esi
0x1000df28  mov     ecx, edi
0x1000df2a  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x1000df2f  test    eax, eax
0x1000df31  jz      short loc_1000DF51
0x1000df33  cdq
0x1000df34  mov     ecx, 0FFFFFFF6h
0x1000df39  xor     eax, edx
0x1000df3b  sub     eax, edx
0x1000df3d  mov     eax, ds:dword_10001970[eax*4]
0x1000df44  cmp     eax, ecx
0x1000df46  cmovz   eax, ecx
0x1000df49  pop     edi
0x1000df4a  pop     esi
0x1000df4b  mov     esp, ebp
0x1000df4d  pop     ebp
0x1000df4e  retn    4
0x1000df51  mov     ecx, [ebp+arg_0]
0x1000df54  mov     eax, _pExcelRecordBuffer
0x1000df59  pop     edi
0x1000df5a  pop     esi
0x1000df5b  mov     [ecx], eax
0x1000df5d  xor     eax, eax
0x1000df5f  mov     esp, ebp
0x1000df61  pop     ebp
0x1000df62  retn    4
```
