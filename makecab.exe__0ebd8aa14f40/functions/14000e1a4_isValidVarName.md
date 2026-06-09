# isValidVarName

- ea: `0x14000e1a4`
- end: `0x14000e1ed`
- name: `isValidVarName`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dcf8`
- `0x14000dfd8`
- `0x14000e028`

## callees

- `0x140008620`
- `0x14000e1a4`

## pseudocode

```c
__int64 __fastcall isValidVarName(const char *a1, __int64 a2)
{
  unsigned __int64 v2; // rax

  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  if ( v2 < 0x20 )
    return 1;
  ErrSet(a2, (int)"Variable name is longer than maximum (%1 chars): %2", "%d%s", 32, a1);
  return 0;
}

```

## disassembly

```asm
0x14000e1a4  sub     rsp, 38h
0x14000e1a8  mov     r10, rdx
0x14000e1ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e1af  inc     rax
0x14000e1b2  cmp     byte ptr [rcx+rax], 0
0x14000e1b6  jnz     short loc_14000E1AF
0x14000e1b8  cmp     rax, 20h ; ' '
0x14000e1bc  jb      short loc_14000E1E3
0x14000e1be  mov     [rsp+38h+var_18], rcx
0x14000e1c3  lea     r8, aDS; "%d%s"
0x14000e1ca  mov     rcx, r10
0x14000e1cd  lea     rdx, aVariableNameIs; "Variable name is longer than maximum (%"...
0x14000e1d4  mov     r9d, 20h ; ' '
0x14000e1da  call    ErrSet
0x14000e1df  xor     eax, eax
0x14000e1e1  jmp     short loc_14000E1E8
0x14000e1e3  mov     eax, 1
0x14000e1e8  add     rsp, 38h
0x14000e1ec  retn
```
