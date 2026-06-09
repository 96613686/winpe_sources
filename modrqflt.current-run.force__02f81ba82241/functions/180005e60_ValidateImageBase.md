# _ValidateImageBase

- ea: `0x180005e60`
- end: `0x180005e8b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e10`

## callees

- `0x180005e60`

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
0x180005e60  mov     eax, 5A4Dh
0x180005e65  cmp     [rcx], ax
0x180005e68  jnz     short loc_180005E88
0x180005e6a  movsxd  rdx, dword ptr [rcx+3Ch]
0x180005e6e  add     rdx, rcx
0x180005e71  cmp     dword ptr [rdx], 4550h
0x180005e77  jnz     short loc_180005E88
0x180005e79  xor     eax, eax
0x180005e7b  mov     ecx, 20Bh
0x180005e80  cmp     [rdx+18h], cx
0x180005e84  setz    al
0x180005e87  retn
0x180005e88  xor     eax, eax
0x180005e8a  retn
```
