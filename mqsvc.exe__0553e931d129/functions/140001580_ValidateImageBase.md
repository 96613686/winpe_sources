# _ValidateImageBase

- ea: `0x140001580`
- end: `0x1400015ab`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001530`

## callees

- `0x140001580`

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
0x140001580  mov     eax, 5A4Dh
0x140001585  cmp     [rcx], ax
0x140001588  jnz     short loc_1400015A8
0x14000158a  movsxd  rdx, dword ptr [rcx+3Ch]
0x14000158e  add     rdx, rcx
0x140001591  cmp     dword ptr [rdx], 4550h
0x140001597  jnz     short loc_1400015A8
0x140001599  xor     eax, eax
0x14000159b  mov     ecx, 20Bh
0x1400015a0  cmp     [rdx+18h], cx
0x1400015a4  setz    al
0x1400015a7  retn
0x1400015a8  xor     eax, eax
0x1400015aa  retn
```
