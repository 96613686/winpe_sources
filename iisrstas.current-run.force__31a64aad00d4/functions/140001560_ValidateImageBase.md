# _ValidateImageBase

- ea: `0x140001560`
- end: `0x14000158b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001510`

## callees

- `0x140001560`

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
0x140001560  mov     eax, 5A4Dh
0x140001565  cmp     [rcx], ax
0x140001568  jnz     short loc_140001588
0x14000156a  movsxd  rdx, dword ptr [rcx+3Ch]
0x14000156e  add     rdx, rcx
0x140001571  cmp     dword ptr [rdx], 4550h
0x140001577  jnz     short loc_140001588
0x140001579  xor     eax, eax
0x14000157b  mov     ecx, 20Bh
0x140001580  cmp     [rdx+18h], cx
0x140001584  setz    al
0x140001587  retn
0x140001588  xor     eax, eax
0x14000158a  retn
```
