# BFReadFile(x,x,x,x)

- ea: `0x1001d6a0`
- end: `0x1001d76e`
- name: `_BFReadFile@16`
- size: `206`
- prototype: `int __stdcall(int, void *, size_t Size, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100288d0`
- `0x10028a60`

## callees

- `0x1000ba90`
- `0x1001d6a0`
- `0x1001da00`
- `0x1001da60`
- `0x1002ba60`

## pseudocode

```c
int __stdcall BFReadFile(int a1, _BYTE *a2, int Size, _DWORD *a4)
{
  int result; // eax
  _BYTE *v5; // ecx
  int v6; // edx
  LONG v7; // esi
  size_t v8; // eax
  void *v9; // [esp-14h] [ebp-18h]

  if ( Size < 0 )
    return -6;
  if ( !Size )
    return 0;
  v5 = *(_BYTE **)(a1 + 8);
  v6 = *(_DWORD *)(a1 + 4);
  if ( Size > (unsigned int)(v6 + *(_DWORD *)a1 - (_DWORD)v5) )
  {
    v7 = (LONG)&v5[*(_DWORD *)(a1 + 72) - v6];
    if ( *(_DWORD *)(a1 + 80) != 1 || (result = WriteFileBlock(a1), result >= 0) )
    {
      v9 = *(void **)(a1 + 20);
      *(_DWORD *)(a1 + 68) = v7;
      DOSSetFilePosition(v9, 0, v7);
      result = ReadFileBlock(a1);
      if ( result >= 0 )
      {
        v8 = *(_DWORD *)a1;
        if ( (unsigned int)Size < *(_DWORD *)a1 )
          v8 = Size;
        *a4 = v8;
        memcpy(a2, *(const void **)(a1 + 8), v8);
        *(_DWORD *)(a1 + 8) += *a4;
        result = 0;
        if ( *a4 != Size )
          return -14;
      }
    }
  }
  else
  {
    if ( Size == 1 )
    {
      *a2 = *v5;
      ++*(_DWORD *)(a1 + 8);
      *a4 = 1;
    }
    else
    {
      memcpy(a2, v5, Size);
      *(_DWORD *)(a1 + 8) += Size;
      *a4 = Size;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1001d6a0  push    ebx
0x1001d6a1  mov     ebx, [esp+4+Size]
0x1001d6a5  test    ebx, ebx
0x1001d6a7  jns     short loc_1001D6B2
0x1001d6a9  mov     eax, 0FFFFFFFAh
0x1001d6ae  pop     ebx
0x1001d6af  retn    10h
0x1001d6b2  jnz     short loc_1001D6BA
0x1001d6b4  xor     eax, eax
0x1001d6b6  pop     ebx
0x1001d6b7  retn    10h
0x1001d6ba  push    edi
0x1001d6bb  mov     edi, [esp+8+arg_0]
0x1001d6bf  mov     eax, [edi]
0x1001d6c1  mov     ecx, [edi+8]
0x1001d6c4  sub     eax, ecx
0x1001d6c6  mov     edx, [edi+4]
0x1001d6c9  add     eax, edx
0x1001d6cb  cmp     ebx, eax
0x1001d6cd  ja      short loc_1001D70A
0x1001d6cf  cmp     ebx, 1
0x1001d6d2  jnz     short loc_1001D6EC
0x1001d6d4  mov     eax, [esp+8+arg_4]
0x1001d6d8  mov     cl, [ecx]
0x1001d6da  mov     [eax], cl
0x1001d6dc  mov     eax, [esp+8+arg_C]
0x1001d6e0  inc     dword ptr [edi+8]
0x1001d6e3  pop     edi
0x1001d6e4  mov     [eax], ebx
0x1001d6e6  xor     eax, eax
0x1001d6e8  pop     ebx
0x1001d6e9  retn    10h
0x1001d6ec  push    ebx; Size
0x1001d6ed  push    ecx; Src
0x1001d6ee  push    [esp+10h+arg_4]; void *
0x1001d6f2  call    _memcpy
0x1001d6f7  mov     eax, [esp+14h+arg_C]
0x1001d6fb  add     esp, 0Ch
0x1001d6fe  add     [edi+8], ebx
0x1001d701  mov     [eax], ebx
0x1001d703  xor     eax, eax
0x1001d705  pop     edi
0x1001d706  pop     ebx
0x1001d707  retn    10h
0x1001d70a  push    esi
0x1001d70b  mov     esi, [edi+48h]
0x1001d70e  sub     esi, edx
0x1001d710  add     esi, ecx
0x1001d712  cmp     dword ptr [edi+50h], 1
0x1001d716  jnz     short loc_1001D722
0x1001d718  push    edi
0x1001d719  call    WriteFileBlock
0x1001d71e  test    eax, eax
0x1001d720  js      short loc_1001D768
0x1001d722  push    esi; lDistanceToMove
0x1001d723  push    0; dwMoveMethod
0x1001d725  push    dword ptr [edi+14h]; hFile
0x1001d728  mov     [edi+44h], esi
0x1001d72b  call    _DOSSetFilePosition@12; DOSSetFilePosition(x,x,x)
0x1001d730  push    edi
0x1001d731  call    ReadFileBlock
0x1001d736  test    eax, eax
0x1001d738  js      short loc_1001D768
0x1001d73a  mov     eax, [edi]
0x1001d73c  cmp     ebx, eax
0x1001d73e  mov     esi, [esp+0Ch+arg_C]
0x1001d742  cmovb   eax, ebx
0x1001d745  push    eax; Size
0x1001d746  mov     [esi], eax
0x1001d748  push    dword ptr [edi+8]; Src
0x1001d74b  push    [esp+14h+arg_4]; void *
0x1001d74f  call    _memcpy
0x1001d754  mov     eax, [esi]
0x1001d756  add     esp, 0Ch
0x1001d759  add     [edi+8], eax
0x1001d75c  mov     ecx, 0FFFFFFF2h
0x1001d761  xor     eax, eax
0x1001d763  cmp     [esi], ebx
0x1001d765  cmovnz  eax, ecx
0x1001d768  pop     esi
0x1001d769  pop     edi
0x1001d76a  pop     ebx
0x1001d76b  retn    10h
```
