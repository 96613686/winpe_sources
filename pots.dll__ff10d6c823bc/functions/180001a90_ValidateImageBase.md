# _ValidateImageBase

- ea: `0x180001a90`
- end: `0x180001abb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a40`

## callees

- `0x180001a90`

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
0x180001a90  mov     eax, 5A4Dh
0x180001a95  cmp     [rcx], ax
0x180001a98  jnz     short loc_180001AB8
0x180001a9a  movsxd  rdx, dword ptr [rcx+3Ch]
0x180001a9e  add     rdx, rcx
0x180001aa1  cmp     dword ptr [rdx], 4550h
0x180001aa7  jnz     short loc_180001AB8
0x180001aa9  xor     eax, eax
0x180001aab  mov     ecx, 20Bh
0x180001ab0  cmp     [rdx+18h], cx
0x180001ab4  setz    al
0x180001ab7  retn
0x180001ab8  xor     eax, eax
0x180001aba  retn
```
