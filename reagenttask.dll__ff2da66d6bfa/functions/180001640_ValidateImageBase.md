# _ValidateImageBase

- ea: `0x180001640`
- end: `0x18000166b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015e0`

## callees

- `0x180001640`

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
0x180001640  mov     eax, 5A4Dh
0x180001645  cmp     [rcx], ax
0x180001648  jnz     short loc_180001668
0x18000164a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000164e  add     rdx, rcx
0x180001651  cmp     dword ptr [rdx], 4550h
0x180001657  jnz     short loc_180001668
0x180001659  xor     eax, eax
0x18000165b  mov     ecx, 20Bh
0x180001660  cmp     [rdx+18h], cx
0x180001664  setz    al
0x180001667  retn
0x180001668  xor     eax, eax
0x18000166a  retn
```
