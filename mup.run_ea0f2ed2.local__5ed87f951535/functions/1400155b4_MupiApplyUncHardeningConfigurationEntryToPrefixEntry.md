# MupiApplyUncHardeningConfigurationEntryToPrefixEntry

- ea: `0x1400155b4`
- end: `0x140015608`
- name: `MupiApplyUncHardeningConfigurationEntryToPrefixEntry`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017f00`
- `0x140018520`
- `0x14001a8d0`

## callees

- `0x1400155b4`

## pseudocode

```c
__int64 __fastcall MupiApplyUncHardeningConfigurationEntryToPrefixEntry(_DWORD *a1, __int64 a2)
{
  int v2; // r10d
  int v3; // eax
  int v5; // r8d
  int v6; // edx
  int v7; // edx
  __int64 result; // rax

  v2 = a1[20];
  v3 = 0;
  if ( v2 <= 0 )
  {
    v5 = 0;
    v3 = v2 < 0;
  }
  else
  {
    v5 = 1;
  }
  v6 = a1[21];
  if ( v6 <= 0 )
  {
    if ( v6 < 0 )
      v3 |= 2u;
  }
  else
  {
    v5 |= 2u;
  }
  v7 = a1[22];
  if ( v7 <= 0 )
  {
    if ( v7 < 0 )
      v3 |= 4u;
  }
  else
  {
    v5 |= 4u;
  }
  result = v5 | *(_DWORD *)(a2 + 88) & (unsigned int)~v3;
  *(_DWORD *)(a2 + 88) = result;
  return result;
}

```

## disassembly

```asm
0x1400155b4  mov     r10d, [rcx+50h]
0x1400155b8  xor     eax, eax
0x1400155ba  mov     r11, rdx
0x1400155bd  test    r10d, r10d
0x1400155c0  jle     short loc_1400155C8
0x1400155c2  lea     r8d, [rax+1]
0x1400155c6  jmp     short loc_1400155D6
0x1400155c8  xor     r8d, r8d
0x1400155cb  test    r10d, r10d
0x1400155ce  lea     r9d, [r8+1]
0x1400155d2  cmovs   eax, r9d
0x1400155d6  mov     edx, [rcx+54h]
0x1400155d9  test    edx, edx
0x1400155db  jle     short loc_1400155E3
0x1400155dd  or      r8d, 2
0x1400155e1  jmp     short loc_1400155E8
0x1400155e3  jns     short loc_1400155E8
0x1400155e5  or      eax, 2
0x1400155e8  mov     edx, [rcx+58h]
0x1400155eb  test    edx, edx
0x1400155ed  jle     short loc_1400155F5
0x1400155ef  or      r8d, 4
0x1400155f3  jmp     short loc_1400155FA
0x1400155f5  jns     short loc_1400155FA
0x1400155f7  or      eax, 4
0x1400155fa  not     eax
0x1400155fc  and     eax, [r11+58h]
0x140015600  or      eax, r8d
0x140015603  mov     [r11+58h], eax
0x140015607  retn
```
