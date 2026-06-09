# PsmpLookupApplicationHelper

- ea: `0x180013480`
- end: `0x1800134be`
- name: `PsmpLookupApplicationHelper`
- size: `62`
- prototype: `bool __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800133f0`

## callees

- `0x180013480`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x1800134a9`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800134a9`

## pseudocode

```c
bool __fastcall PsmpLookupApplicationHelper(__int64 a1, __int64 a2, _QWORD *a3)
{
  char v4; // [rsp+20h] [rbp-18h]

  if ( *a3 != *(_QWORD *)(a1 + 16) )
    return 0;
  v4 = 1;
  return (unsigned int)RtlCompareUnicodeStrings(*(_QWORD *)(a1 + 8), *a3 >> 1, a2, *a3 >> 1, v4) == 0;
}

```

## disassembly

```asm
0x180013480  sub     rsp, 38h
0x180013484  mov     rax, rdx
0x180013487  mov     rdx, [r8]
0x18001348a  cmp     rdx, [rcx+10h]
0x18001348e  jz      short loc_180013497
0x180013490  xor     al, al
0x180013492  add     rsp, 38h
0x180013496  retn
0x180013497  mov     rcx, [rcx+8]
0x18001349b  mov     r8, rax
0x18001349e  shr     rdx, 1
0x1800134a1  mov     r9, rdx
0x1800134a4  mov     [rsp+38h+var_18], 1
0x1800134a9  call    cs:__imp_RtlCompareUnicodeStrings
0x1800134af  test    eax, eax
0x1800134b1  jnz     short loc_1800134BA
0x1800134b3  mov     al, 1
0x1800134b5  add     rsp, 38h
0x1800134b9  retn
0x1800134ba  xor     eax, eax
0x1800134bc  jmp     short loc_180013492
```
