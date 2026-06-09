# GetCpIndexFromProtocol

- ea: `0x180010cfc`
- end: `0x180010d3a`
- name: `GetCpIndexFromProtocol`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800023a8`
- `0x180003770`
- `0x180006118`
- `0x1800066d0`
- `0x180009560`
- `0x18000aed4`
- `0x18000bfc0`
- `0x18000c4ac`
- `0x18000e100`
- `0x18000e86c`
- `0x180013630`
- `0x1800149e0`
- `0x180014d00`
- `0x180014ff0`
- `0x1800151d0`
- `0x1800152a0`
- `0x1800155b8`
- `0x180017790`
- `0x180017990`

## callees

- `0x180010cfc`

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
0x180010cfc  mov     r9d, dword ptr cs:PppConfigInfo+4
0x180010d03  xor     r8d, r8d
0x180010d06  mov     r10d, dword ptr cs:PppConfigInfo
0x180010d0d  mov     r11, cs:CpTable
0x180010d14  lea     eax, [r9+r10]
0x180010d18  cmp     r8d, eax
0x180010d1b  jnb     short loc_180010D36
0x180010d1d  mov     eax, r8d
0x180010d20  imul    rdx, rax, 0B0h
0x180010d27  cmp     [rdx+r11], ecx
0x180010d2b  jz      short loc_180010D32
0x180010d2d  inc     r8d
0x180010d30  jmp     short loc_180010D14
0x180010d32  mov     eax, r8d
0x180010d35  retn
0x180010d36  or      eax, 0FFFFFFFFh
0x180010d39  retn
```
