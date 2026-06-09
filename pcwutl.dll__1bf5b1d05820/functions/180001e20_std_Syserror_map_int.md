# std::_Syserror_map(int)

- ea: `0x180001e20`
- end: `0x180001e48`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b00`
- `0x180001c80`
- `0x180001cf0`

## callees

- `0x180001e20`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18001B590;
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
0x180001e20  cmp     cs:off_18001B598, 0; "address family not supported"
0x180001e28  lea     rax, qword_18001B590
0x180001e2f  jz      short loc_180001E40
0x180001e31  cmp     [rax], ecx
0x180001e33  jz      short loc_180001E43
0x180001e35  add     rax, 10h
0x180001e39  cmp     qword ptr [rax+8], 0
0x180001e3e  jnz     short loc_180001E31
0x180001e40  xor     eax, eax
0x180001e42  retn
0x180001e43  mov     rax, [rax+8]
0x180001e47  retn
```
