# write_char

- ea: `0x10033325`
- end: `0x1003335b`
- name: `write_char`
- size: `54`
- prototype: `int __cdecl(wchar_t Character, FILE *Stream, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x10032721`
- `0x1003335b`
- `0x10033387`

## callees

- `0x10033325`
- `0x10037ef0`

## pseudocode

```c
_DWORD *__cdecl write_char(wchar_t Character, FILE *Stream, _DWORD *a3)
{
  _DWORD *result; // eax

  if ( ((Stream->_flag & 0x40) == 0 || Stream->_base) && _fputwc_nolock(Character, Stream) == 0xFFFF )
  {
    result = a3;
    *a3 = -1;
  }
  else
  {
    result = a3;
    ++*a3;
  }
  return result;
}

```

## disassembly

```asm
0x10033325  push    ebp
0x10033326  mov     ebp, esp
0x10033328  mov     eax, [ebp+Stream]
0x1003332b  test    byte ptr [eax+0Ch], 40h
0x1003332f  jz      short loc_10033337
0x10033331  cmp     dword ptr [eax+8], 0
0x10033335  jz      short loc_10033354
0x10033337  push    eax; Stream
0x10033338  push    dword ptr [ebp+Character]; Character
0x1003333b  call    __fputwc_nolock
0x10033340  pop     ecx
0x10033341  pop     ecx
0x10033342  mov     ecx, 0FFFFh
0x10033347  cmp     ax, cx
0x1003334a  jnz     short loc_10033354
0x1003334c  mov     eax, [ebp+arg_8]
0x1003334f  or      dword ptr [eax], 0FFFFFFFFh
0x10033352  pop     ebp
0x10033353  retn
0x10033354  mov     eax, [ebp+arg_8]
0x10033357  inc     dword ptr [eax]
0x10033359  pop     ebp
0x1003335a  retn
```
