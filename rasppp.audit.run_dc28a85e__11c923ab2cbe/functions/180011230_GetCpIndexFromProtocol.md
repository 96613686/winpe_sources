# GetCpIndexFromProtocol

- ea: `0x180011230`
- end: `0x18001126f`
- name: `GetCpIndexFromProtocol`
- size: `63`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800023c0`
- `0x18000380c`
- `0x18000638c`
- `0x180006970`
- `0x180009920`
- `0x18000b2e8`
- `0x18000c3e8`
- `0x18000c8d4`
- `0x18000e540`
- `0x18000ecac`
- `0x180013cf4`
- `0x180015100`
- `0x180015430`
- `0x180015730`
- `0x180015920`
- `0x180015a00`
- `0x180015d28`
- `0x180017fa0`
- `0x1800181b0`

## callees

- `0x180011230`

## pseudocode

```c
__int64 __fastcall GetCpIndexFromProtocol(int a1)
{
  unsigned int i; // r8d

  for ( i = 0; i < HIDWORD(PppConfigInfo) + (int)PppConfigInfo; ++i )
  {
    if ( *((_DWORD *)CpTable + 44 * i) == a1 )
      return i;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180011230  mov     r9d, dword ptr cs:PppConfigInfo+4
0x180011237  xor     r8d, r8d
0x18001123a  mov     r10d, dword ptr cs:PppConfigInfo
0x180011241  mov     r11, cs:CpTable
0x180011248  lea     eax, [r9+r10]
0x18001124c  cmp     r8d, eax
0x18001124f  jnb     short loc_18001126B
0x180011251  mov     eax, r8d
0x180011254  imul    rdx, rax, 0B0h
0x18001125b  cmp     [rdx+r11], ecx
0x18001125f  jz      short loc_180011266
0x180011261  inc     r8d
0x180011264  jmp     short loc_180011248
0x180011266  mov     eax, r8d
0x180011269  retn
0x18001126b  or      eax, 0FFFFFFFFh
0x18001126e  retn
```
