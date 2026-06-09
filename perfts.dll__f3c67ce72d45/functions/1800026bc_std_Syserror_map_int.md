# std::_Syserror_map(int)

- ea: `0x1800026bc`
- end: `0x1800026e4`
- name: `?_Syserror_map@std@@YAPEBDH@Z`
- size: `40`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002390`
- `0x180002510`
- `0x180002580`

## callees

- `0x1800026bc`

## pseudocode

```c
const char *__fastcall std::_Syserror_map(int a1)
{
  _QWORD *v1; // rax

  v1 = &unk_18000C5A0;
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
0x1800026bc  cmp     cs:off_18000C5A8, 0; "address family not supported"
0x1800026c4  lea     rax, unk_18000C5A0
0x1800026cb  jz      short loc_1800026DC
0x1800026cd  cmp     [rax], ecx
0x1800026cf  jz      short loc_1800026DF
0x1800026d1  add     rax, 10h
0x1800026d5  cmp     qword ptr [rax+8], 0
0x1800026da  jnz     short loc_1800026CD
0x1800026dc  xor     eax, eax
0x1800026de  retn
0x1800026df  mov     rax, [rax+8]
0x1800026e3  retn
```
