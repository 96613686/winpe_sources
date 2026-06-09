# RtlStartTimerWheelEntryTimer

- ea: `0x1400054c4`
- end: `0x1400054e4`
- name: `RtlStartTimerWheelEntryTimer`
- size: `32`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002700`
- `0x1400056b4`
- `0x140005a9c`

## callees

- `0x1400054c4`

## pseudocode

```c
bool __fastcall RtlStartTimerWheelEntryTimer(__int64 a1, __int64 a2, int a3)
{
  int v3; // eax
  int v4; // edx

  v3 = 1;
  if ( a3 )
    v3 = a3;
  *(_DWORD *)(a1 + 20) = v3;
  v4 = *(_DWORD *)(a1 + 16);
  return !v4 || v3 - v4 < 0;
}

```

## disassembly

```asm
0x1400054c4  test    r8d, r8d
0x1400054c7  mov     eax, 1
0x1400054cc  cmovnz  eax, r8d
0x1400054d0  mov     [rcx+14h], eax
0x1400054d3  mov     edx, [rcx+10h]
0x1400054d6  test    edx, edx
0x1400054d8  jz      short loc_1400054E1
0x1400054da  cmp     eax, edx
0x1400054dc  sets    al
0x1400054df  retn
0x1400054e1  mov     al, 1
0x1400054e3  retn
```
