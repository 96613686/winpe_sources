# _ValidateImageBase

- ea: `0x180001940`
- end: `0x18000196b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800018f0`

## callees

- `0x180001940`

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
0x180001940  mov     eax, 5A4Dh
0x180001945  cmp     [rcx], ax
0x180001948  jnz     short loc_180001968
0x18000194a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000194e  add     rdx, rcx
0x180001951  cmp     dword ptr [rdx], 4550h
0x180001957  jnz     short loc_180001968
0x180001959  xor     eax, eax
0x18000195b  mov     ecx, 20Bh
0x180001960  cmp     [rdx+18h], cx
0x180001964  setz    al
0x180001967  retn
0x180001968  xor     eax, eax
0x18000196a  retn
```
