# MupiArmUncHardeningConfigurationRefreshTimer

- ea: `0x1400151c0`
- end: `0x1400151f6`
- name: `MupiArmUncHardeningConfigurationRefreshTimer`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140014ea0`
- `0x1400153e0`

## callees

- `0x14000521c`
- `0x1400151c0`

## pseudocode

```c
__int64 __fastcall MupiArmUncHardeningConfigurationRefreshTimer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // r9

  if ( *(_QWORD *)(a1 + 32) )
  {
    v3 = -150000000;
    v4 = 2000;
  }
  else
  {
    v3 = -5000000;
    v4 = 500;
  }
  return RfsTimerSet(a1 + 88, v3, a3, v4);
}

```

## disassembly

```asm
0x1400151c0  sub     rsp, 28h
0x1400151c4  cmp     qword ptr [rcx+20h], 0
0x1400151c9  jnz     short loc_1400151DA
0x1400151cb  mov     rdx, 0FFFFFFFFFFB3B4C0h
0x1400151d2  mov     r9d, 1F4h
0x1400151d8  jmp     short loc_1400151E7
0x1400151da  mov     rdx, 0FFFFFFFFF70F2E80h
0x1400151e1  mov     r9d, 7D0h
0x1400151e7  add     rcx, 58h ; 'X'
0x1400151eb  call    RfsTimerSet
0x1400151f0  add     rsp, 28h
0x1400151f4  retn
```
