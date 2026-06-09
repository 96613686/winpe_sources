# ConfigReadRegSpec(x,x,x,x,x)

- ea: `0x10009fc0`
- end: `0x10009ff5`
- name: `_ConfigReadRegSpec@20`
- size: `53`
- prototype: `int __stdcall(STRSAFE_LPCWSTR pszSrc, int, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x100148d0`

## callees

- `0x10009db0`
- `0x10009fc0`
- `0x1000aa30`

## pseudocode

```c
int __stdcall ConfigReadRegSpec(STRSAFE_LPCWSTR pszSrc, char *a2, int a3, char *a4, int **a5)
{
  int result; // eax

  AssignDefaults(a5);
  result = ReadRegSpec(pszSrc, 0, a2, a5);
  if ( !result )
    return ReadRegSpec(pszSrc, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x10009fc0  push    esi
0x10009fc1  mov     esi, [esp+4+arg_10]
0x10009fc5  push    esi
0x10009fc6  call    AssignDefaults
0x10009fcb  push    esi; int
0x10009fcc  push    [esp+8+arg_4]; int
0x10009fd0  push    0; int
0x10009fd2  push    [esp+10h+pszSrc]; pszSrc
0x10009fd6  call    ReadRegSpec
0x10009fdb  test    eax, eax
0x10009fdd  jnz     short loc_10009FF1
0x10009fdf  push    esi; int
0x10009fe0  push    [esp+8+arg_C]; int
0x10009fe4  push    [esp+0Ch+arg_8]; int
0x10009fe8  push    [esp+10h+pszSrc]; pszSrc
0x10009fec  call    ReadRegSpec
0x10009ff1  pop     esi
0x10009ff2  retn    14h
```
