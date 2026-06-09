# CmpsValidateHandle

- ea: `0x180011d6c`
- end: `0x180011d94`
- name: `CmpsValidateHandle`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180011760`
- `0x1800117c0`
- `0x1800175ac`
- `0x180017660`
- `0x1800176fc`

## callees

- `0x180011d6c`

## pseudocode

```c
__int64 __fastcall CmpsValidateHandle(_DWORD *a1, int a2)
{
  if ( !a1 || (unsigned int)*(unsigned __int8 *)a1 - 1 > 4 )
    return 6;
  if ( (*a1 & 0x40000000) != 0 )
  {
    if ( !a2 )
      return 6;
  }
  else if ( a2 )
  {
    return 6;
  }
  return 0;
}

```

## disassembly

```asm
0x180011d6c  test    rcx, rcx
0x180011d6f  jz      short loc_180011D87
0x180011d71  movzx   eax, byte ptr [rcx]
0x180011d74  dec     eax
0x180011d76  cmp     eax, 4
0x180011d79  ja      short loc_180011D87
0x180011d7b  test    dword ptr [rcx], 40000000h
0x180011d81  jnz     short loc_180011D8D
0x180011d83  test    edx, edx
0x180011d85  jz      short loc_180011D91
0x180011d87  mov     eax, 6
0x180011d8c  retn
0x180011d8d  test    edx, edx
0x180011d8f  jz      short loc_180011D87
0x180011d91  xor     eax, eax
0x180011d93  retn
```
