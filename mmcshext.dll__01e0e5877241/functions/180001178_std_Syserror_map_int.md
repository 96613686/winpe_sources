# std::_Syserror_map(int)

- ea: `0x180001178`
- end: `0x1800011a0`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028a0`
- `0x180002a10`
- `0x180002a80`

## callees

- `0x180001178`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000C4B0;
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
0x180001178  cmp     cs:off_18000C4B8, 0; "address family not supported"
0x180001180  lea     rax, qword_18000C4B0
0x180001187  jz      short loc_180001198
0x180001189  cmp     [rax], ecx
0x18000118b  jz      short loc_18000119B
0x18000118d  add     rax, 10h
0x180001191  cmp     qword ptr [rax+8], 0
0x180001196  jnz     short loc_180001189
0x180001198  xor     eax, eax
0x18000119a  retn
0x18000119b  mov     rax, [rax+8]
0x18000119f  retn
```
