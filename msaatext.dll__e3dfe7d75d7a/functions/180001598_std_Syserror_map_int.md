# std::_Syserror_map(int)

- ea: `0x180001598`
- end: `0x1800015c0`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033b0`
- `0x180003520`
- `0x180003590`

## callees

- `0x180001598`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1800154D0;
  if ( !"address family not supported" )
    return 0;
  while ( *(_DWORD *)v1 != a1 )
  {
    v1 += 2;
    if ( !v1[1] )
      return 0;
  }
  return (const char *)v1[1];
}

```

## disassembly

```asm
0x180001598  cmp     cs:off_1800154D8, 0; "address family not supported"
0x1800015a0  lea     rax, qword_1800154D0
0x1800015a7  jz      short loc_1800015B8
0x1800015a9  cmp     [rax], ecx
0x1800015ab  jz      short loc_1800015BB
0x1800015ad  add     rax, 10h
0x1800015b1  cmp     qword ptr [rax+8], 0
0x1800015b6  jnz     short loc_1800015A9
0x1800015b8  xor     eax, eax
0x1800015ba  retn
0x1800015bb  mov     rax, [rax+8]
0x1800015bf  retn
```
