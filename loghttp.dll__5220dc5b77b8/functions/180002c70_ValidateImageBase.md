# _ValidateImageBase

- ea: `0x180002c70`
- end: `0x180002c9b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c20`

## callees

- `0x180002c70`

## pseudocode

```c
_BOOL8 __fastcall ValidateImageBase(__int64 a1)
{
  __int64 v1; // rdx

  if ( *(_WORD *)a1 == 23117 && (v1 = a1 + *(int *)(a1 + 60), *(_DWORD *)v1 == 17744) )
    return *(_WORD *)(v1 + 24) == 523;
  else
    return 0;
}

```

## disassembly

```asm
0x180002c70  mov     eax, 5A4Dh
0x180002c75  cmp     [rcx], ax
0x180002c78  jnz     short loc_180002C98
0x180002c7a  movsxd  rdx, dword ptr [rcx+3Ch]
0x180002c7e  add     rdx, rcx
0x180002c81  cmp     dword ptr [rdx], 4550h
0x180002c87  jnz     short loc_180002C98
0x180002c89  xor     eax, eax
0x180002c8b  mov     ecx, 20Bh
0x180002c90  cmp     [rdx+18h], cx
0x180002c94  setz    al
0x180002c97  retn
0x180002c98  xor     eax, eax
0x180002c9a  retn
```
