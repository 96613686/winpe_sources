# _ValidateImageBase

- ea: `0x1800017c0`
- end: `0x1800017eb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001770`

## callees

- `0x1800017c0`

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
0x1800017c0  mov     eax, 5A4Dh
0x1800017c5  cmp     [rcx], ax
0x1800017c8  jnz     short loc_1800017E8
0x1800017ca  movsxd  rdx, dword ptr [rcx+3Ch]
0x1800017ce  add     rdx, rcx
0x1800017d1  cmp     dword ptr [rdx], 4550h
0x1800017d7  jnz     short loc_1800017E8
0x1800017d9  xor     eax, eax
0x1800017db  mov     ecx, 20Bh
0x1800017e0  cmp     [rdx+18h], cx
0x1800017e4  setz    al
0x1800017e7  retn
0x1800017e8  xor     eax, eax
0x1800017ea  retn
```
