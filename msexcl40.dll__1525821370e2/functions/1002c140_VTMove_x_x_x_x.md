# VTMove(x,x,x,x)

- ea: `0x1002c140`
- end: `0x1002c223`
- name: `_VTMove@16`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1002a869`
- `0x1002c065`
- `0x1002c140`

## pseudocode

```c
int __stdcall VTMove(int a1, int a2, int a3, int a4)
{
  int v4; // eax
  int result; // eax
  int *v6; // ecx
  int v7; // eax
  char v8; // dl
  int v9; // edx

  v4 = ISAMDBFindSession(a1);
  if ( !v4 )
    return -1104;
  v6 = *(int **)(v4 + 8);
  if ( !v6 )
    return -1310;
  while ( v6[3] != a2 )
  {
    v6 = (int *)*v6;
    if ( !v6 )
      return -1310;
  }
  if ( a4 )
    return -1312;
  if ( !v6[8] )
    return -1603;
  if ( a3 )
  {
    if ( a3 == 0x80000000 )
    {
      v7 = 2;
    }
    else if ( a3 == 0x7FFFFFFF )
    {
      v7 = 3;
    }
    else
    {
      v7 = 0;
      if ( a3 != 1 )
      {
        if ( a3 == -1 )
        {
          v7 = 1;
        }
        else
        {
          LOBYTE(v7) = a3 <= 0;
          v7 += 4;
        }
      }
    }
    v8 = *((_BYTE *)v6 + 36);
    if ( v8 )
    {
      if ( v8 == 1 && v7 == 1 )
        v7 = 3;
    }
    else if ( !v7 )
    {
      v7 = 2;
    }
    v9 = v6[2];
    if ( !v9 || (unsigned int)(v9 - 1) <= 1 )
      XVTMove(v7, a3);
  }
  result = -1603;
  if ( *((_BYTE *)v6 + 36) == 2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1002c140  mov     edi, edi
0x1002c142  push    ebp
0x1002c143  mov     ebp, esp
0x1002c145  mov     ecx, [ebp+arg_0]
0x1002c148  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x1002c14d  test    eax, eax
0x1002c14f  jnz     short loc_1002C158
0x1002c151  mov     eax, 0FFFFFBB0h
0x1002c156  jmp     short loc_1002C172
0x1002c158  mov     ecx, [eax+8]
0x1002c15b  test    ecx, ecx
0x1002c15d  jz      short loc_1002C16D
0x1002c15f  mov     eax, [ebp+arg_4]
0x1002c162  cmp     [ecx+0Ch], eax
0x1002c165  jz      short loc_1002C176
0x1002c167  mov     ecx, [ecx]
0x1002c169  test    ecx, ecx
0x1002c16b  jnz     short loc_1002C162
0x1002c16d  mov     eax, 0FFFFFAE2h
0x1002c172  pop     ebp
0x1002c173  retn    10h
0x1002c176  test    ecx, ecx
0x1002c178  jz      short loc_1002C16D
0x1002c17a  cmp     [ebp+arg_C], 0
0x1002c17e  jz      short loc_1002C187
0x1002c180  mov     eax, 0FFFFFAE0h
0x1002c185  jmp     short loc_1002C172
0x1002c187  cmp     dword ptr [ecx+20h], 0
0x1002c18b  jz      loc_1002C219
0x1002c191  push    esi
0x1002c192  mov     esi, [ebp+arg_8]
0x1002c195  test    esi, esi
0x1002c197  jz      short loc_1002C205
0x1002c199  push    edi
0x1002c19a  push    3
0x1002c19c  pop     edi
0x1002c19d  cmp     esi, 80000000h
0x1002c1a3  jnz     short loc_1002C1AA
0x1002c1a5  push    2
0x1002c1a7  pop     eax
0x1002c1a8  jmp     short loc_1002C1CD
0x1002c1aa  cmp     esi, 7FFFFFFFh
0x1002c1b0  jnz     short loc_1002C1B6
0x1002c1b2  mov     eax, edi
0x1002c1b4  jmp     short loc_1002C1CD
0x1002c1b6  xor     eax, eax
0x1002c1b8  cmp     esi, 1
0x1002c1bb  jz      short loc_1002C1CD
0x1002c1bd  cmp     esi, 0FFFFFFFFh
0x1002c1c0  jnz     short loc_1002C1C5
0x1002c1c2  inc     eax
0x1002c1c3  jmp     short loc_1002C1CD
0x1002c1c5  test    esi, esi
0x1002c1c7  setle   al
0x1002c1ca  add     eax, 4
0x1002c1cd  mov     dl, [ecx+24h]
0x1002c1d0  test    dl, dl
0x1002c1d2  jnz     short loc_1002C1DD
0x1002c1d4  test    eax, eax
0x1002c1d6  jnz     short loc_1002C1E8
0x1002c1d8  push    2
0x1002c1da  pop     eax
0x1002c1db  jmp     short loc_1002C1E8
0x1002c1dd  cmp     dl, 1
0x1002c1e0  jnz     short loc_1002C1E8
0x1002c1e2  cmp     eax, 1
0x1002c1e5  cmovz   eax, edi
0x1002c1e8  mov     edx, [ecx+8]
0x1002c1eb  pop     edi
0x1002c1ec  sub     edx, 0
0x1002c1ef  jz      short loc_1002C1FB
0x1002c1f1  sub     edx, 1
0x1002c1f4  jz      short loc_1002C1FB
0x1002c1f6  sub     edx, 1
0x1002c1f9  jnz     short loc_1002C205
0x1002c1fb  push    esi
0x1002c1fc  push    eax
0x1002c1fd  lea     edx, [ecx+28h]
0x1002c200  call    XVTMove
0x1002c205  xor     edx, edx
0x1002c207  mov     eax, 0FFFFF9BDh
0x1002c20c  cmp     byte ptr [ecx+24h], 2
0x1002c210  pop     esi
0x1002c211  cmovz   eax, edx
0x1002c214  jmp     loc_1002C172
0x1002c219  mov     eax, 0FFFFF9BDh
0x1002c21e  jmp     loc_1002C172
```
