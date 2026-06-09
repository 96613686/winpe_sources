# std::_Syserror_map(int)

- ea: `0x140001738`
- end: `0x140001760`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400032f0`
- `0x140003470`
- `0x1400034e0`

## callees

- `0x140001738`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  __int64 *v1; // rax

  v1 = &qword_1400134D0;
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
0x140001738  cmp     cs:off_1400134D8, 0; "address family not supported"
0x140001740  lea     rax, qword_1400134D0
0x140001747  jz      short loc_140001758
0x140001749  cmp     [rax], ecx
0x14000174b  jz      short loc_14000175B
0x14000174d  add     rax, 10h
0x140001751  cmp     qword ptr [rax+8], 0
0x140001756  jnz     short loc_140001749
0x140001758  xor     eax, eax
0x14000175a  retn
0x14000175b  mov     rax, [rax+8]
0x14000175f  retn
```
