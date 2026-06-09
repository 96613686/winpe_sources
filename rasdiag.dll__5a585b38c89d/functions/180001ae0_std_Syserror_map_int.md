# std::_Syserror_map(int)

- ea: `0x180001ae0`
- end: `0x180001b08`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017c0`
- `0x180001940`
- `0x1800019b0`

## callees

- `0x180001ae0`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_180010590;
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
0x180001ae0  cmp     cs:off_180010598, 0; "address family not supported"
0x180001ae8  lea     rax, qword_180010590
0x180001aef  jz      short loc_180001B00
0x180001af1  cmp     [rax], ecx
0x180001af3  jz      short loc_180001B03
0x180001af5  add     rax, 10h
0x180001af9  cmp     qword ptr [rax+8], 0
0x180001afe  jnz     short loc_180001AF1
0x180001b00  xor     eax, eax
0x180001b02  retn
0x180001b03  mov     rax, [rax+8]
0x180001b07  retn
```
