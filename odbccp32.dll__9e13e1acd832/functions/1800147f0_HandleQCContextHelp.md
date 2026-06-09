# HandleQCContextHelp

- ea: `0x1800147f0`
- end: `0x18001480e`
- name: `HandleQCContextHelp`
- size: `30`
- prototype: `_BOOL8 __fastcall(__int64, int, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aeb0`
- `0x18000af80`
- `0x18000b9c0`
- `0x18000c440`
- `0x18000dc70`

## callees

- `0x1800147f0`

## pseudocode

```c
_BOOL8 __fastcall HandleQCContextHelp(__int64 a1, int a2, __int64 a3)
{
  if ( a2 == 83 )
    return *(_DWORD *)(a3 + 4) == 1;
  else
    return a2 == 123;
}

```

## disassembly

```asm
0x1800147f0  cmp     edx, 53h ; 'S'
0x1800147f3  jz      short loc_180014803
0x1800147f5  cmp     edx, 7Bh ; '{'
0x1800147f8  jz      short loc_1800147FD
0x1800147fa  xor     eax, eax
0x1800147fc  retn
0x1800147fd  mov     eax, 1
0x180014802  retn
0x180014803  xor     eax, eax
0x180014805  cmp     dword ptr [r8+4], 1
0x18001480a  setz    al
0x18001480d  retn
```
