# _ValidateImageBase

- ea: `0x1400015b0`
- end: `0x1400015db`
- name: `_ValidateImageBase`
- size: `43`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001560`

## callees

- `0x1400015b0`

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
0x1400015b0  mov     eax, 5A4Dh
0x1400015b5  cmp     [rcx], ax
0x1400015b8  jnz     short loc_1400015D8
0x1400015ba  movsxd  rdx, dword ptr [rcx+3Ch]
0x1400015be  add     rdx, rcx
0x1400015c1  cmp     dword ptr [rdx], 4550h
0x1400015c7  jnz     short loc_1400015D8
0x1400015c9  xor     eax, eax
0x1400015cb  mov     ecx, 20Bh
0x1400015d0  cmp     [rdx+18h], cx
0x1400015d4  setz    al
0x1400015d7  retn
0x1400015d8  xor     eax, eax
0x1400015da  retn
```
