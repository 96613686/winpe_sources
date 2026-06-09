# _ValidateImageBase

- ea: `0x180002ee0`
- end: `0x180002f0b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e90`

## callees

- `0x180002ee0`

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
0x180002ee0  mov     eax, 5A4Dh
0x180002ee5  cmp     [rcx], ax
0x180002ee8  jnz     short loc_180002F08
0x180002eea  movsxd  rdx, dword ptr [rcx+3Ch]
0x180002eee  add     rdx, rcx
0x180002ef1  cmp     dword ptr [rdx], 4550h
0x180002ef7  jnz     short loc_180002F08
0x180002ef9  xor     eax, eax
0x180002efb  mov     ecx, 20Bh
0x180002f00  cmp     [rdx+18h], cx
0x180002f04  setz    al
0x180002f07  retn
0x180002f08  xor     eax, eax
0x180002f0a  retn
```
