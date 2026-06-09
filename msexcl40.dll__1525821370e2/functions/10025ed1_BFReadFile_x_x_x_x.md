# BFReadFile(x,x,x,x)

- ea: `0x10025ed1`
- end: `0x10025f80`
- name: `_BFReadFile@16`
- size: `175`
- prototype: `int __fastcall(size_t *, _BYTE *, int Size, _DWORD *)`
- caller_count: `11`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10007740`
- `0x10008210`
- `0x100082d0`
- `0x100088e0`
- `0x100092a0`
- `0x1000dc30`
- `0x1000de70`
- `0x1000dee0`
- `0x1000df70`
- `0x1000e600`
- `0x10012270`

## callees

- `0x10025bee`
- `0x10025d54`
- `0x10025df5`
- `0x10025ed1`
- `0x1003669c`

## pseudocode

```c
int __fastcall BFReadFile(size_t *a1, _BYTE *a2, int Size, _DWORD *a4)
{
  int result; // eax
  _BYTE *v6; // ecx
  _BYTE *v7; // esi
  size_t v8; // esi
  const void *v9; // [esp-8h] [ebp-18h]

  if ( Size < 0 )
    return -6;
  if ( !Size )
    return 0;
  v6 = (_BYTE *)a1[2];
  if ( Size <= a1[1] + *a1 - (_DWORD)v6 )
  {
    if ( Size == 1 )
    {
      *a2 = *v6;
      ++a1[2];
    }
    else
    {
      memcpy(a2, v6, Size);
      a1[2] += Size;
    }
    *a4 = Size;
    return 0;
  }
  v7 = &v6[a1[21] - a1[1]];
  if ( a1[23] != 1 || (result = WriteFileBlock(a1), result >= 0) )
  {
    a1[20] = (size_t)v7;
    OSSetFilePosition(a1, 0, v7);
    result = ReadFileBlock(a1);
    if ( result >= 0 )
    {
      v8 = *a1;
      if ( Size < *a1 )
        v8 = Size;
      v9 = (const void *)a1[2];
      *a4 = v8;
      memcpy(a2, v9, v8);
      a1[2] += v8;
      result = 0;
      if ( v8 != Size )
        return -14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10025ed1  mov     edi, edi
0x10025ed3  push    ebp
0x10025ed4  mov     ebp, esp
0x10025ed6  push    ecx
0x10025ed7  push    ebx
0x10025ed8  mov     ebx, [ebp+Size]
0x10025edb  mov     [ebp+var_4], edx
0x10025ede  push    esi
0x10025edf  push    edi
0x10025ee0  mov     edi, ecx
0x10025ee2  test    ebx, ebx
0x10025ee4  jns     short loc_10025EEB
0x10025ee6  push    0FFFFFFFAh
0x10025ee8  pop     eax
0x10025ee9  jmp     short loc_10025F1E
0x10025eeb  jz      short loc_10025F1C
0x10025eed  mov     eax, [edi]
0x10025eef  mov     ecx, [edi+8]
0x10025ef2  sub     eax, ecx
0x10025ef4  add     eax, [edi+4]
0x10025ef7  cmp     ebx, eax
0x10025ef9  ja      short loc_10025F25
0x10025efb  cmp     ebx, 1
0x10025efe  jnz     short loc_10025F09
0x10025f00  mov     al, [ecx]
0x10025f02  mov     [edx], al
0x10025f04  inc     dword ptr [edi+8]
0x10025f07  jmp     short loc_10025F17
0x10025f09  push    ebx; Size
0x10025f0a  push    ecx; Src
0x10025f0b  push    edx; void *
0x10025f0c  call    _memcpy
0x10025f11  add     esp, 0Ch
0x10025f14  add     [edi+8], ebx
0x10025f17  mov     eax, [ebp+arg_4]
0x10025f1a  mov     [eax], ebx
0x10025f1c  xor     eax, eax
0x10025f1e  pop     edi
0x10025f1f  pop     esi
0x10025f20  pop     ebx
0x10025f21  leave
0x10025f22  retn    8
0x10025f25  mov     esi, [edi+54h]
0x10025f28  sub     esi, [edi+4]
0x10025f2b  add     esi, ecx
0x10025f2d  cmp     dword ptr [edi+5Ch], 1
0x10025f31  jnz     short loc_10025F3E
0x10025f33  mov     ecx, edi
0x10025f35  call    WriteFileBlock
0x10025f3a  test    eax, eax
0x10025f3c  js      short loc_10025F1E
0x10025f3e  push    esi
0x10025f3f  xor     edx, edx
0x10025f41  mov     [edi+50h], esi
0x10025f44  mov     ecx, edi
0x10025f46  call    OSSetFilePosition
0x10025f4b  mov     ecx, edi
0x10025f4d  call    ReadFileBlock
0x10025f52  test    eax, eax
0x10025f54  js      short loc_10025F1E
0x10025f56  mov     esi, [edi]
0x10025f58  cmp     ebx, esi
0x10025f5a  mov     eax, [ebp+arg_4]
0x10025f5d  cmovb   esi, ebx
0x10025f60  push    esi; Size
0x10025f61  push    dword ptr [edi+8]; Src
0x10025f64  mov     [eax], esi
0x10025f66  push    [ebp+var_4]; void *
0x10025f69  call    _memcpy
0x10025f6e  add     [edi+8], esi
0x10025f71  add     esp, 0Ch
0x10025f74  xor     eax, eax
0x10025f76  cmp     esi, ebx
0x10025f78  push    0FFFFFFF2h
0x10025f7a  pop     ecx
0x10025f7b  cmovnz  eax, ecx
0x10025f7e  jmp     short loc_10025F1E
```
