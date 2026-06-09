# _ValidateImageBase

- ea: `0x180002380`
- end: `0x1800023ab`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002330`

## callees

- `0x180002380`

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
0x180002380  mov     eax, 5A4Dh
0x180002385  cmp     [rcx], ax
0x180002388  jnz     short loc_1800023A8
0x18000238a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000238e  add     rdx, rcx
0x180002391  cmp     dword ptr [rdx], 4550h
0x180002397  jnz     short loc_1800023A8
0x180002399  xor     eax, eax
0x18000239b  mov     ecx, 20Bh
0x1800023a0  cmp     [rdx+18h], cx
0x1800023a4  setz    al
0x1800023a7  retn
0x1800023a8  xor     eax, eax
0x1800023aa  retn
```
