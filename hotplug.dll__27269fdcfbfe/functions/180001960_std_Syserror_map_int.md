# std::_Syserror_map(int)

- ea: `0x180001960`
- end: `0x180001988`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001640`
- `0x1800017c0`
- `0x180001830`

## callees

- `0x180001960`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_18000A590;
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
0x180001960  cmp     cs:off_18000A598, 0; "address family not supported"
0x180001968  lea     rax, qword_18000A590
0x18000196f  jz      short loc_180001980
0x180001971  cmp     [rax], ecx
0x180001973  jz      short loc_180001983
0x180001975  add     rax, 10h
0x180001979  cmp     qword ptr [rax+8], 0
0x18000197e  jnz     short loc_180001971
0x180001980  xor     eax, eax
0x180001982  retn
0x180001983  mov     rax, [rax+8]
0x180001987  retn
```
