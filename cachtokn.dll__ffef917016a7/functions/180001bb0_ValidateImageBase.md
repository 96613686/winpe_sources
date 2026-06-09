# _ValidateImageBase

- ea: `0x180001bb0`
- end: `0x180001bdb`
- name: `_ValidateImageBase`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b60`

## callees

- `0x180001bb0`

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
0x180001bb0  mov     eax, 5A4Dh
0x180001bb5  cmp     [rcx], ax
0x180001bb8  jnz     short loc_180001BD8
0x180001bba  movsxd  rdx, dword ptr [rcx+3Ch]
0x180001bbe  add     rdx, rcx
0x180001bc1  cmp     dword ptr [rdx], 4550h
0x180001bc7  jnz     short loc_180001BD8
0x180001bc9  xor     eax, eax
0x180001bcb  mov     ecx, 20Bh
0x180001bd0  cmp     [rdx+18h], cx
0x180001bd4  setz    al
0x180001bd7  retn
0x180001bd8  xor     eax, eax
0x180001bda  retn
```
