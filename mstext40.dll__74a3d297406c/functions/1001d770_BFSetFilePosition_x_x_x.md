# BFSetFilePosition(x,x,x)

- ea: `0x1001d770`
- end: `0x1001d82c`
- name: `_BFSetFilePosition@12`
- size: `188`
- prototype: `int __stdcall(int, int, LONG lDistanceToMove)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1001e1e0`
- `0x1001ff80`
- `0x10028a60`

## callees

- `0x1000ba90`
- `0x1001d770`
- `0x1001da00`
- `0x1001da60`

## pseudocode

```c
int __stdcall BFSetFilePosition(int *a1, int a2, LONG lDistanceToMove)
{
  LONG v3; // edx
  int v4; // ebp
  int v5; // ebx
  LONG v6; // edi
  int result; // eax
  int v8; // ecx
  void *v9; // [esp-Ch] [ebp-1Ch]

  v3 = a1[18];
  v4 = v3 - a1[1];
  v5 = a1[2] + v4;
  if ( a2 )
  {
    if ( a2 == 2 )
      v6 = lDistanceToMove + a1[19];
    else
      v6 = v5 + lDistanceToMove;
  }
  else
  {
    v6 = lDistanceToMove;
  }
  if ( v6 == v5 )
    return 0;
  if ( v6 >= v3 && v6 <= v3 + *a1 - 1 )
  {
    result = 0;
    a1[2] = v6 - v4;
    return result;
  }
  if ( v3 + *a1 == a1[19] && v6 >= v3 && v6 <= v3 + a1[13] - 1 )
  {
    a1[2] = v6 - v4;
    v8 = v6 - v4 - a1[1];
    a1[19] = v6;
    result = 0;
    *a1 = v8;
    return result;
  }
  if ( a1[20] != 1 || (result = WriteFileBlock(a1), result >= 0) )
  {
    v9 = (void *)a1[5];
    a1[17] = v6;
    DOSSetFilePosition(v9, 0, v6);
    result = ReadFileBlock(a1);
    if ( result >= 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1001d770  mov     eax, [esp+arg_4]
0x1001d774  push    ebx
0x1001d775  push    ebp
0x1001d776  push    esi
0x1001d777  mov     esi, [esp+0Ch+arg_0]
0x1001d77b  push    edi
0x1001d77c  mov     edx, [esi+48h]
0x1001d77f  mov     ebp, edx
0x1001d781  sub     ebp, [esi+4]
0x1001d784  mov     ecx, [esi+8]
0x1001d787  lea     ebx, [ecx+ebp]
0x1001d78a  test    eax, eax
0x1001d78c  jnz     short loc_1001D794
0x1001d78e  mov     edi, [esp+10h+lDistanceToMove]
0x1001d792  jmp     short loc_1001D7A8
0x1001d794  cmp     eax, 2
0x1001d797  jnz     short loc_1001D7A2
0x1001d799  mov     edi, [esi+4Ch]
0x1001d79c  add     edi, [esp+10h+lDistanceToMove]
0x1001d7a0  jmp     short loc_1001D7A8
0x1001d7a2  mov     edi, [esp+10h+lDistanceToMove]
0x1001d7a6  add     edi, ebx
0x1001d7a8  cmp     edi, ebx
0x1001d7aa  jz      short loc_1001D823
0x1001d7ac  cmp     edi, edx
0x1001d7ae  jl      short loc_1001D7C9
0x1001d7b0  mov     eax, [esi]
0x1001d7b2  dec     eax
0x1001d7b3  add     eax, edx
0x1001d7b5  cmp     edi, eax
0x1001d7b7  jg      short loc_1001D7C9
0x1001d7b9  sub     ecx, ebx
0x1001d7bb  add     ecx, edi
0x1001d7bd  xor     eax, eax
0x1001d7bf  pop     edi
0x1001d7c0  mov     [esi+8], ecx
0x1001d7c3  pop     esi
0x1001d7c4  pop     ebp
0x1001d7c5  pop     ebx
0x1001d7c6  retn    0Ch
0x1001d7c9  mov     eax, [esi]
0x1001d7cb  add     eax, edx
0x1001d7cd  cmp     eax, [esi+4Ch]
0x1001d7d0  jnz     short loc_1001D7FB
0x1001d7d2  cmp     edi, edx
0x1001d7d4  jl      short loc_1001D7FB
0x1001d7d6  mov     eax, [esi+34h]
0x1001d7d9  dec     eax
0x1001d7da  add     eax, edx
0x1001d7dc  cmp     edi, eax
0x1001d7de  jg      short loc_1001D7FB
0x1001d7e0  sub     ecx, ebx
0x1001d7e2  add     ecx, edi
0x1001d7e4  mov     [esi+8], ecx
0x1001d7e7  pop     edi
0x1001d7e8  lea     eax, [ecx+ebp]
0x1001d7eb  sub     ecx, [esi+4]
0x1001d7ee  mov     [esi+4Ch], eax
0x1001d7f1  xor     eax, eax
0x1001d7f3  mov     [esi], ecx
0x1001d7f5  pop     esi
0x1001d7f6  pop     ebp
0x1001d7f7  pop     ebx
0x1001d7f8  retn    0Ch
0x1001d7fb  cmp     dword ptr [esi+50h], 1
0x1001d7ff  jnz     short loc_1001D80B
0x1001d801  push    esi
0x1001d802  call    WriteFileBlock
0x1001d807  test    eax, eax
0x1001d809  js      short loc_1001D825
0x1001d80b  push    edi; lDistanceToMove
0x1001d80c  push    0; dwMoveMethod
0x1001d80e  push    dword ptr [esi+14h]; hFile
0x1001d811  mov     [esi+44h], edi
0x1001d814  call    _DOSSetFilePosition@12; DOSSetFilePosition(x,x,x)
0x1001d819  push    esi
0x1001d81a  call    ReadFileBlock
0x1001d81f  test    eax, eax
0x1001d821  js      short loc_1001D825
0x1001d823  xor     eax, eax
0x1001d825  pop     edi
0x1001d826  pop     esi
0x1001d827  pop     ebp
0x1001d828  pop     ebx
0x1001d829  retn    0Ch
```
