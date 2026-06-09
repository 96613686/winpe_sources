# write_string

- ea: `0x10033387`
- end: `0x10033400`
- name: `write_string`
- size: `121`
- prototype: `int __cdecl(int, int, FILE *Stream, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10032721`

## callees

- `0x10033325`
- `0x10033387`

## pseudocode

```c
_DWORD *__cdecl write_string(wchar_t *a1, int a2, FILE *Stream, _DWORD *a4, _DWORD **a5)
{
  _DWORD *result; // eax
  int v7; // ebx
  _DWORD *v8; // [esp+20h] [ebp+18h]

  result = *a5;
  v8 = *a5;
  if ( (Stream->_flag & 0x40) != 0 && !Stream->_base )
  {
    result = (_DWORD *)a2;
    *a4 += a2;
    return result;
  }
  *a5 = 0;
  v7 = a2;
  if ( a2 <= 0 )
    goto LABEL_12;
  result = a4;
  do
  {
    --v7;
    write_char(*a1, Stream, result);
    result = a4;
    ++a1;
    if ( *a4 == -1 )
    {
      if ( *a5 != (_DWORD *)42 )
        break;
      write_char(0x3Fu, Stream, a4);
      result = a4;
    }
  }
  while ( v7 > 0 );
  if ( !*a5 )
  {
    result = v8;
LABEL_12:
    *a5 = result;
  }
  return result;
}

```

## disassembly

```asm
0x10033387  push    ebp
0x10033388  mov     ebp, esp
0x1003338a  push    esi
0x1003338b  mov     esi, [ebp+arg_10]
0x1003338e  push    edi
0x1003338f  mov     edi, [ebp+Stream]
0x10033392  mov     eax, [esi]
0x10033394  mov     [ebp+arg_10], eax
0x10033397  test    byte ptr [edi+0Ch], 40h
0x1003339b  jz      short loc_100333AD
0x1003339d  cmp     dword ptr [edi+8], 0
0x100333a1  jnz     short loc_100333AD
0x100333a3  mov     ecx, [ebp+arg_C]
0x100333a6  mov     eax, [ebp+arg_4]
0x100333a9  add     [ecx], eax
0x100333ab  jmp     short loc_100333FC
0x100333ad  and     dword ptr [esi], 0
0x100333b0  push    ebx
0x100333b1  mov     ebx, [ebp+arg_4]
0x100333b4  test    ebx, ebx
0x100333b6  jle     short loc_100333F9
0x100333b8  mov     eax, [ebp+arg_C]
0x100333bb  push    eax; int
0x100333bc  mov     eax, [ebp+arg_0]
0x100333bf  dec     ebx
0x100333c0  push    edi; Stream
0x100333c1  movzx   eax, word ptr [eax]
0x100333c4  push    eax; Character
0x100333c5  call    write_char
0x100333ca  mov     eax, [ebp+arg_C]
0x100333cd  add     esp, 0Ch
0x100333d0  add     [ebp+arg_0], 2
0x100333d4  cmp     dword ptr [eax], 0FFFFFFFFh
0x100333d7  jnz     short loc_100333ED
0x100333d9  cmp     dword ptr [esi], 2Ah ; '*'
0x100333dc  jnz     short loc_100333F1
0x100333de  push    eax; int
0x100333df  push    edi; Stream
0x100333e0  push    3Fh ; '?'; Character
0x100333e2  call    write_char
0x100333e7  mov     eax, [ebp+arg_C]
0x100333ea  add     esp, 0Ch
0x100333ed  test    ebx, ebx
0x100333ef  jg      short loc_100333BB
0x100333f1  cmp     dword ptr [esi], 0
0x100333f4  jnz     short loc_100333FB
0x100333f6  mov     eax, [ebp+arg_10]
0x100333f9  mov     [esi], eax
0x100333fb  pop     ebx
0x100333fc  pop     edi
0x100333fd  pop     esi
0x100333fe  pop     ebp
0x100333ff  retn
```
