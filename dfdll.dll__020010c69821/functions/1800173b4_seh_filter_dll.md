# _seh_filter_dll

- ea: `0x1800173b4`
- end: `0x1800173c7`
- name: `_seh_filter_dll`
- size: `19`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012d58`

## callees

- `0x1800173b4`
- `0x1800173c8`

## pseudocode

```c
int __cdecl seh_filter_dll(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( ExceptionNum == -529697949 )
    return seh_filter_exe(0xE06D7363, ExceptionPtr);
  else
    return 0;
}

```

## disassembly

```asm
0x1800173b4  mov     eax, 0E06D7363h
0x1800173b9  cmp     ecx, eax
0x1800173bb  jz      short loc_1800173C0
0x1800173bd  xor     eax, eax
0x1800173bf  retn
0x1800173c0  mov     ecx, eax
0x1800173c2  jmp     _seh_filter_exe
```
