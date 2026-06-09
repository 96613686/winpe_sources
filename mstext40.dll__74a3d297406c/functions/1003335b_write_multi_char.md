# write_multi_char

- ea: `0x1003335b`
- end: `0x10033387`
- name: `write_multi_char`
- size: `44`
- prototype: `int __cdecl(wchar_t Character, int, FILE *Stream, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10032721`

## callees

- `0x10033325`
- `0x1003335b`

## pseudocode

```c
_DWORD *__cdecl write_multi_char(wchar_t Character, int a2, FILE *Stream, _DWORD *a4)
{
  int v4; // esi
  _DWORD *result; // eax

  v4 = a2;
  if ( a2 > 0 )
  {
    do
    {
      --v4;
      result = write_char(Character, Stream, a4);
    }
    while ( *a4 != -1 && v4 > 0 );
  }
  return result;
}

```

## disassembly

```asm
0x1003335b  push    ebp
0x1003335c  mov     ebp, esp
0x1003335e  push    esi
0x1003335f  mov     esi, [ebp+arg_4]
0x10033362  test    esi, esi
0x10033364  jle     short loc_10033384
0x10033366  push    edi
0x10033367  mov     edi, [ebp+arg_C]
0x1003336a  push    edi; int
0x1003336b  push    [ebp+Stream]; Stream
0x1003336e  dec     esi
0x1003336f  push    dword ptr [ebp+Character]; Character
0x10033372  call    write_char
0x10033377  add     esp, 0Ch
0x1003337a  cmp     dword ptr [edi], 0FFFFFFFFh
0x1003337d  jz      short loc_10033383
0x1003337f  test    esi, esi
0x10033381  jg      short loc_1003336A
0x10033383  pop     edi
0x10033384  pop     esi
0x10033385  pop     ebp
0x10033386  retn
```
