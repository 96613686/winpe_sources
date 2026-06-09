# MupiArmParametersKeyRefreshTimer

- ea: `0x140016858`
- end: `0x14001688e`
- name: `MupiArmParametersKeyRefreshTimer`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046c0`
- `0x1400048f0`
- `0x140004c30`
- `0x140004e60`

## callees

- `0x14000521c`
- `0x140016858`

## pseudocode

```c
__int64 __fastcall MupiArmParametersKeyRefreshTimer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // r9

  if ( *(_QWORD *)(a1 + 24) )
  {
    v3 = -150000000;
    v4 = 2000;
  }
  else
  {
    v3 = -5000000;
    v4 = 500;
  }
  return RfsTimerSet(a1 + 80, v3, a3, v4);
}

```

## disassembly

```asm
0x140016858  sub     rsp, 28h
0x14001685c  cmp     qword ptr [rcx+18h], 0
0x140016861  jnz     short loc_140016872
0x140016863  mov     rdx, 0FFFFFFFFFFB3B4C0h
0x14001686a  mov     r9d, 1F4h
0x140016870  jmp     short loc_14001687F
0x140016872  mov     rdx, 0FFFFFFFFF70F2E80h
0x140016879  mov     r9d, 7D0h
0x14001687f  add     rcx, 50h ; 'P'
0x140016883  call    RfsTimerSet
0x140016888  add     rsp, 28h
0x14001688c  retn
```
