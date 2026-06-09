# std::_Syserror_map(int)

- ea: `0x180001f1c`
- end: `0x180001f44`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d5e0`
- `0x18000d750`
- `0x18000d7c0`

## callees

- `0x180001f1c`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1800114D0;
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
0x180001f1c  cmp     cs:off_1800114D8, 0; "address family not supported"
0x180001f24  lea     rax, qword_1800114D0
0x180001f2b  jz      short loc_180001F3C
0x180001f2d  cmp     [rax], ecx
0x180001f2f  jz      short loc_180001F3F
0x180001f31  add     rax, 10h
0x180001f35  cmp     qword ptr [rax+8], 0
0x180001f3a  jnz     short loc_180001F2D
0x180001f3c  xor     eax, eax
0x180001f3e  retn
0x180001f3f  mov     rax, [rax+8]
0x180001f43  retn
```
