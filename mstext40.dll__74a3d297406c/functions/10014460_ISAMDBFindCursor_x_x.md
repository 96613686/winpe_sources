# ISAMDBFindCursor(x,x)

- ea: `0x10014460`
- end: `0x100144dd`
- name: `_ISAMDBFindCursor@8`
- size: `125`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x1000f530`
- `0x1000f8f0`
- `0x1000fa40`
- `0x10012e70`
- `0x100130e0`
- `0x100131b0`
- `0x10013640`
- `0x10013660`
- `0x10013680`
- `0x100136b0`
- `0x100137e0`
- `0x10013800`
- `0x10013ae0`
- `0x10015580`
- `0x100155a0`
- `0x100155f0`
- `0x10015640`
- `0x10015680`
- `0x10015740`
- `0x100158b0`
- `0x10015960`
- `0x10015c80`
- `0x10015cb0`
- `0x100160b0`
- `0x100178b0`
- `0x10017ea0`

## callees

- `0x1000a3d0`
- `0x10014460`

## pseudocode

```c
_DWORD *__stdcall ISAMDBFindCursor(int a1, int a2)
{
  _DWORD *v2; // esi
  _DWORD *v3; // eax
  _DWORD *result; // eax
  _DWORD *v5; // esi
  _DWORD *v6; // ecx

  v2 = (_DWORD *)dword_10040FBC;
  if ( !dword_10040FBC )
    return 0;
  while ( 1 )
  {
    v3 = (_DWORD *)v2[1];
    if ( v3 )
      break;
LABEL_5:
    v2 = (_DWORD *)*v2;
    if ( !v2 )
      return 0;
  }
  while ( v3[3] != a1 )
  {
    v3 = (_DWORD *)*v3;
    if ( !v3 )
      goto LABEL_5;
  }
  ErrorSetSession(v3[4]);
  v5 = (_DWORD *)v2[2];
  if ( !v5 )
    return 0;
  while ( 1 )
  {
    v6 = (_DWORD *)v5[13];
    if ( v6 )
      break;
LABEL_13:
    v5 = (_DWORD *)*v5;
    if ( !v5 )
      return 0;
  }
  while ( 1 )
  {
    result = (_DWORD *)v6[217];
    if ( result )
      break;
LABEL_12:
    v6 = (_DWORD *)*v6;
    if ( !v6 )
      goto LABEL_13;
  }
  while ( result[3] != a2 )
  {
    result = (_DWORD *)*result;
    if ( !result )
      goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x10014460  push    esi
0x10014461  mov     esi, dword_10040FBC
0x10014467  test    esi, esi
0x10014469  jz      short loc_100144D7
0x1001446b  mov     ecx, [esp+4+arg_0]
0x1001446f  nop
0x10014470  mov     eax, [esi+4]
0x10014473  test    eax, eax
0x10014475  jz      short loc_10014482
0x10014477  cmp     [eax+0Ch], ecx
0x1001447a  jz      short loc_1001448E
0x1001447c  mov     eax, [eax]
0x1001447e  test    eax, eax
0x10014480  jnz     short loc_10014477
0x10014482  mov     esi, [esi]
0x10014484  test    esi, esi
0x10014486  jnz     short loc_10014470
0x10014488  xor     eax, eax
0x1001448a  pop     esi
0x1001448b  retn    8
0x1001448e  push    dword ptr [eax+10h]
0x10014491  call    _ErrorSetSession@4; ErrorSetSession(x)
0x10014496  mov     esi, [esi+8]
0x10014499  test    esi, esi
0x1001449b  jz      short loc_100144D7
0x1001449d  mov     edx, [esp+4+arg_4]
0x100144a1  mov     ecx, [esi+34h]
0x100144a4  test    ecx, ecx
0x100144a6  jz      short loc_100144D1
0x100144a8  jmp     short loc_100144B0
0x100144b0  mov     eax, [ecx+364h]
0x100144b6  test    eax, eax
0x100144b8  jz      short loc_100144CB
0x100144ba  lea     ebx, [ebx+0]
0x100144c0  cmp     [eax+0Ch], edx
0x100144c3  jz      short loc_100144D9
0x100144c5  mov     eax, [eax]
0x100144c7  test    eax, eax
0x100144c9  jnz     short loc_100144C0
0x100144cb  mov     ecx, [ecx]
0x100144cd  test    ecx, ecx
0x100144cf  jnz     short loc_100144B0
0x100144d1  mov     esi, [esi]
0x100144d3  test    esi, esi
0x100144d5  jnz     short loc_100144A1
0x100144d7  xor     eax, eax
0x100144d9  pop     esi
0x100144da  retn    8
```
