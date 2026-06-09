# std::_Syserror_map(int)

- ea: `0x180001b50`
- end: `0x180001b78`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001830`
- `0x1800019b0`
- `0x180001a20`

## callees

- `0x180001b50`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_180013590;
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
0x180001b50  cmp     cs:off_180013598, 0; "address family not supported"
0x180001b58  lea     rax, qword_180013590
0x180001b5f  jz      short loc_180001B70
0x180001b61  cmp     [rax], ecx
0x180001b63  jz      short loc_180001B73
0x180001b65  add     rax, 10h
0x180001b69  cmp     qword ptr [rax+8], 0
0x180001b6e  jnz     short loc_180001B61
0x180001b70  xor     eax, eax
0x180001b72  retn
0x180001b73  mov     rax, [rax+8]
0x180001b77  retn
```
