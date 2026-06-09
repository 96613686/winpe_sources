# std::_Syserror_map(int)

- ea: `0x1800012b8`
- end: `0x1800012e0`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004da0`
- `0x180004f10`
- `0x180004f80`

## callees

- `0x1800012b8`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000C4D0;
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
0x1800012b8  cmp     cs:off_18000C4D8, 0; "address family not supported"
0x1800012c0  lea     rax, qword_18000C4D0
0x1800012c7  jz      short loc_1800012D8
0x1800012c9  cmp     [rax], ecx
0x1800012cb  jz      short loc_1800012DB
0x1800012cd  add     rax, 10h
0x1800012d1  cmp     qword ptr [rax+8], 0
0x1800012d6  jnz     short loc_1800012C9
0x1800012d8  xor     eax, eax
0x1800012da  retn
0x1800012db  mov     rax, [rax+8]
0x1800012df  retn
```
