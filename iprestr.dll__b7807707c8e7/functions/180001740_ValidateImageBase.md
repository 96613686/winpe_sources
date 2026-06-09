# _ValidateImageBase

- ea: `0x180001740`
- end: `0x18000176b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016f0`

## callees

- `0x180001740`

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
0x180001740  mov     eax, 5A4Dh
0x180001745  cmp     [rcx], ax
0x180001748  jnz     short loc_180001768
0x18000174a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000174e  add     rdx, rcx
0x180001751  cmp     dword ptr [rdx], 4550h
0x180001757  jnz     short loc_180001768
0x180001759  xor     eax, eax
0x18000175b  mov     ecx, 20Bh
0x180001760  cmp     [rdx+18h], cx
0x180001764  setz    al
0x180001767  retn
0x180001768  xor     eax, eax
0x18000176a  retn
```
