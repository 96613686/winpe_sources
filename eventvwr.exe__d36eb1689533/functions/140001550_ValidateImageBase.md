# _ValidateImageBase

- ea: `0x140001550`
- end: `0x14000157b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001500`

## callees

- `0x140001550`

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
0x140001550  mov     eax, 5A4Dh
0x140001555  cmp     [rcx], ax
0x140001558  jnz     short loc_140001578
0x14000155a  movsxd  rdx, dword ptr [rcx+3Ch]
0x14000155e  add     rdx, rcx
0x140001561  cmp     dword ptr [rdx], 4550h
0x140001567  jnz     short loc_140001578
0x140001569  xor     eax, eax
0x14000156b  mov     ecx, 20Bh
0x140001570  cmp     [rdx+18h], cx
0x140001574  setz    al
0x140001577  retn
0x140001578  xor     eax, eax
0x14000157a  retn
```
