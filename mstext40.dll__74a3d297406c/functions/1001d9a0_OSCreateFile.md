# OSCreateFile

- ea: `0x1001d9a0`
- end: `0x1001d9f3`
- name: `OSCreateFile`
- size: `83`
- prototype: `int __stdcall(LPCWSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1001d4b0`

## callees

- `0x1000b410`
- `0x1001d9a0`

## pseudocode

```c
int __stdcall OSCreateFile(LPCWSTR lpFileName, _DWORD *a2)
{
  bool v2; // zf
  int v3; // eax

  v2 = a2[3] == 0;
  a2[4] = 2;
  if ( !v2 )
    return 0;
  v3 = DOSCreateFile(lpFileName, a2 + 5);
  switch ( v3 )
  {
    case 0:
      return 0;
    case -4:
      return -1;
    case -5:
      return -2;
  }
  return 8 * (v3 == -3) - 11;
}

```

## disassembly

```asm
0x1001d9a0  mov     eax, [esp+arg_4]
0x1001d9a4  cmp     dword ptr [eax+0Ch], 0
0x1001d9a8  mov     dword ptr [eax+10h], 2
0x1001d9af  jnz     short loc_1001D9EE
0x1001d9b1  add     eax, 14h
0x1001d9b4  push    eax; int
0x1001d9b5  push    [esp+4+lpFileName]; lpFileName
0x1001d9b9  call    _DOSCreateFile@8; DOSCreateFile(x,x)
0x1001d9be  mov     ecx, eax
0x1001d9c0  test    ecx, ecx
0x1001d9c2  jz      short loc_1001D9EE
0x1001d9c4  cmp     ecx, 0FFFFFFFCh
0x1001d9c7  jnz     short loc_1001D9CF
0x1001d9c9  or      eax, 0FFFFFFFFh
0x1001d9cc  retn    8
0x1001d9cf  cmp     ecx, 0FFFFFFFBh
0x1001d9d2  jnz     short loc_1001D9DC
0x1001d9d4  mov     eax, 0FFFFFFFEh
0x1001d9d9  retn    8
0x1001d9dc  xor     eax, eax
0x1001d9de  cmp     ecx, 0FFFFFFFDh
0x1001d9e1  setz    al
0x1001d9e4  lea     eax, ds:0FFFFFFF5h[eax*8]
0x1001d9eb  retn    8
0x1001d9ee  xor     eax, eax
0x1001d9f0  retn    8
```
