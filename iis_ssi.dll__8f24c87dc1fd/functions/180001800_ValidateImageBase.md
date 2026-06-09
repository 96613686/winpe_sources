# _ValidateImageBase

- ea: `0x180001800`
- end: `0x18000182b`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017b0`

## callees

- `0x180001800`

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
0x180001800  mov     eax, 5A4Dh
0x180001805  cmp     [rcx], ax
0x180001808  jnz     short loc_180001828
0x18000180a  movsxd  rdx, dword ptr [rcx+3Ch]
0x18000180e  add     rdx, rcx
0x180001811  cmp     dword ptr [rdx], 4550h
0x180001817  jnz     short loc_180001828
0x180001819  xor     eax, eax
0x18000181b  mov     ecx, 20Bh
0x180001820  cmp     [rdx+18h], cx
0x180001824  setz    al
0x180001827  retn
0x180001828  xor     eax, eax
0x18000182a  retn
```
