# ExcelReadRecordHeader(x,x)

- ea: `0x1000dcc0`
- end: `0x1000dd80`
- name: `_ExcelReadRecordHeader@8`
- size: `192`
- prototype: `int __fastcall(int, __int16 *)`
- caller_count: `21`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10008210`
- `0x100082d0`
- `0x100088e0`
- `0x100094b0`
- `0x1000e600`
- `0x1000eec0`
- `0x1000fbf0`
- `0x1000fdf0`
- `0x100102c0`
- `0x10010700`
- `0x10010790`
- `0x10011010`
- `0x10011a70`
- `0x10011e70`
- `0x10012270`
- `0x10013490`
- `0x10013d10`
- `0x10016240`
- `0x100163d0`
- `0x10017b00`
- `0x100181b0`

## callees

- `0x1000dcc0`
- `0x10025bee`
- `0x10025d54`
- `0x10025df5`
- `0x1003669c`

## pseudocode

```c
int __fastcall ExcelReadRecordHeader(int a1, __int16 *a2)
{
  int v2; // eax
  int result; // eax
  int v5; // edi
  _DWORD *v6; // ecx
  int v7; // edx
  char *v8; // esi
  int FileBlock; // eax
  size_t v10; // esi

  v2 = *(_DWORD *)(a1 + 40);
  if ( v2 )
  {
    *(_DWORD *)a2 = *(_DWORD *)(*(_DWORD *)(v2 + 8) + 4);
    return 0;
  }
  v5 = *(_DWORD *)(a1 + 20);
  v6 = *(_DWORD **)(v5 + 8);
  v7 = *(_DWORD *)(v5 + 4);
  if ( (unsigned int)(v7 + *(_DWORD *)v5 - (_DWORD)v6) < 4 )
  {
    v8 = (char *)v6 + *(_DWORD *)(v5 + 84) - v7;
    if ( *(_DWORD *)(v5 + 92) != 1 || (FileBlock = WriteFileBlock(v5), FileBlock >= 0) )
    {
      *(_DWORD *)(v5 + 80) = v8;
      OSSetFilePosition(v5, 0, v8);
      FileBlock = ReadFileBlock(v5);
      if ( FileBlock >= 0 )
      {
        v10 = *(_DWORD *)v5;
        if ( *(_DWORD *)v5 > 4u )
          v10 = 4;
        memcpy(a2, *(const void **)(v5 + 8), v10);
        *(_DWORD *)(v5 + 8) += v10;
        if ( v10 == 4 )
          goto LABEL_6;
        FileBlock = -14;
      }
    }
    result = dword_10001970[abs32(FileBlock)];
    if ( result == -10 )
      return -10;
    return result;
  }
  *(_DWORD *)a2 = *v6;
  *(_DWORD *)(v5 + 8) += 4;
LABEL_6:
  if ( !a2 || a2[1] >= 0 )
    return 0;
  a2[1] = 0;
  return -10;
}

```

## disassembly

```asm
0x1000dcc0  mov     eax, [ecx+28h]
0x1000dcc3  push    ebx
0x1000dcc4  mov     ebx, edx
0x1000dcc6  push    esi
0x1000dcc7  push    edi
0x1000dcc8  test    eax, eax
0x1000dcca  jz      short loc_1000DCDA
0x1000dccc  mov     eax, [eax+8]
0x1000dccf  mov     eax, [eax+4]
0x1000dcd2  mov     [ebx], eax
0x1000dcd4  xor     eax, eax
0x1000dcd6  pop     edi
0x1000dcd7  pop     esi
0x1000dcd8  pop     ebx
0x1000dcd9  retn
0x1000dcda  mov     edi, [ecx+14h]
0x1000dcdd  mov     eax, [edi]
0x1000dcdf  mov     ecx, [edi+8]
0x1000dce2  sub     eax, ecx
0x1000dce4  mov     edx, [edi+4]
0x1000dce7  add     eax, edx
0x1000dce9  cmp     eax, 4
0x1000dcec  jb      short loc_1000DD10
0x1000dcee  mov     eax, [ecx]
0x1000dcf0  mov     [ebx], eax
0x1000dcf2  add     dword ptr [edi+8], 4
0x1000dcf6  test    ebx, ebx
0x1000dcf8  jz      short loc_1000DCD4
0x1000dcfa  cmp     word ptr [ebx+2], 0
0x1000dcff  jge     short loc_1000DCD4
0x1000dd01  xor     eax, eax
0x1000dd03  mov     [ebx+2], ax
0x1000dd07  mov     eax, 0FFFFFFF6h
0x1000dd0c  pop     edi
0x1000dd0d  pop     esi
0x1000dd0e  pop     ebx
0x1000dd0f  retn
0x1000dd10  mov     esi, [edi+54h]
0x1000dd13  sub     esi, edx
0x1000dd15  add     esi, ecx
0x1000dd17  cmp     dword ptr [edi+5Ch], 1
0x1000dd1b  jnz     short loc_1000DD28
0x1000dd1d  mov     ecx, edi
0x1000dd1f  call    WriteFileBlock
0x1000dd24  test    eax, eax
0x1000dd26  js      short loc_1000DD66
0x1000dd28  push    esi
0x1000dd29  xor     edx, edx
0x1000dd2b  mov     [edi+50h], esi
0x1000dd2e  mov     ecx, edi
0x1000dd30  call    OSSetFilePosition
0x1000dd35  mov     ecx, edi
0x1000dd37  call    ReadFileBlock
0x1000dd3c  test    eax, eax
0x1000dd3e  js      short loc_1000DD66
0x1000dd40  mov     esi, [edi]
0x1000dd42  mov     eax, 4
0x1000dd47  cmp     esi, eax
0x1000dd49  cmova   esi, eax
0x1000dd4c  push    esi; Size
0x1000dd4d  push    dword ptr [edi+8]; Src
0x1000dd50  push    ebx; void *
0x1000dd51  call    _memcpy
0x1000dd56  add     [edi+8], esi
0x1000dd59  add     esp, 0Ch
0x1000dd5c  cmp     esi, 4
0x1000dd5f  jz      short loc_1000DCF6
0x1000dd61  mov     eax, 0FFFFFFF2h
0x1000dd66  cdq
0x1000dd67  mov     ecx, 0FFFFFFF6h
0x1000dd6c  xor     eax, edx
0x1000dd6e  sub     eax, edx
0x1000dd70  pop     edi
0x1000dd71  pop     esi
0x1000dd72  pop     ebx
0x1000dd73  mov     eax, ds:dword_10001970[eax*4]
0x1000dd7a  cmp     eax, ecx
0x1000dd7c  cmovz   eax, ecx
0x1000dd7f  retn
```
