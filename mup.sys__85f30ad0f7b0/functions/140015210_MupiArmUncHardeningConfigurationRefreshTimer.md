# MupiArmUncHardeningConfigurationRefreshTimer

- ea: `0x140015210`
- end: `0x140015246`
- name: `MupiArmUncHardeningConfigurationRefreshTimer`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140014ef0`
- `0x140015430`

## callees

- `0x14000521c`
- `0x140015210`

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
0x140015210  sub     rsp, 28h
0x140015214  cmp     qword ptr [rcx+20h], 0
0x140015219  jnz     short loc_14001522A
0x14001521b  mov     rdx, 0FFFFFFFFFFB3B4C0h
0x140015222  mov     r9d, 1F4h
0x140015228  jmp     short loc_140015237
0x14001522a  mov     rdx, 0FFFFFFFFF70F2E80h
0x140015231  mov     r9d, 7D0h
0x140015237  add     rcx, 58h ; 'X'
0x14001523b  call    RfsTimerSet
0x140015240  add     rsp, 28h
0x140015244  retn
```
