# ConvertToInternalChainingMode

- ea: `0x140001170`
- end: `0x1400011b9`
- name: `ConvertToInternalChainingMode`
- size: `73`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002270`
- `0x140002510`
- `0x140002670`

## callees

- `0x140001170`
- `0x140003cf6`

## pseudocode

```c
__int64 __fastcall ConvertToInternalChainingMode(wchar_t *Str1, unsigned __int64 a2)
{
  if ( a2 < 0x20 )
    return 0;
  if ( !wcscmp_0(Str1, L"ChainingModeCBC") )
    return 1;
  return wcscmp_0(Str1, L"ChainingModeECB") == 0 ? 2 : 0;
}

```

## disassembly

```asm
0x140001170  push    rbx
0x140001172  sub     rsp, 20h
0x140001176  mov     rbx, rcx
0x140001179  cmp     rdx, 20h ; ' '
0x14000117d  jb      short loc_1400011B0
0x14000117f  lea     rdx, aChainingmodecb; "ChainingModeCBC"
0x140001186  call    wcscmp_0
0x14000118b  test    eax, eax
0x14000118d  jnz     short loc_140001196
0x14000118f  mov     eax, 1
0x140001194  jmp     short loc_1400011B2
0x140001196  lea     rdx, aChainingmodeec; "ChainingModeECB"
0x14000119d  mov     rcx, rbx; Str1
0x1400011a0  call    wcscmp_0
0x1400011a5  neg     eax
0x1400011a7  sbb     eax, eax
0x1400011a9  not     eax
0x1400011ab  and     eax, 2
0x1400011ae  jmp     short loc_1400011B2
0x1400011b0  xor     eax, eax
0x1400011b2  add     rsp, 20h
0x1400011b6  pop     rbx
0x1400011b7  retn
```
