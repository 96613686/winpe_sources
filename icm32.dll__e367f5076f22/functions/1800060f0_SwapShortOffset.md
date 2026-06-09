# SwapShortOffset

- ea: `0x1800060f0`
- end: `0x18000611c`
- name: `SwapShortOffset`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042fc`
- `0x18000464c`
- `0x180006f00`
- `0x180007130`
- `0x180007418`
- `0x180019b00`
- `0x18001bb30`
- `0x18001c4a0`
- `0x18001de14`
- `0x180021060`

## callees

- `0x1800060f0`

## pseudocode

```c
__int64 __fastcall SwapShortOffset(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 i; // r8
  __int64 result; // rax

  v3 = a1 + a3;
  for ( i = a1 + a2; i < v3; i += 2LL )
  {
    result = *(unsigned __int8 *)(i + 1);
    *(_WORD *)i = _byteswap_ushort(*(_WORD *)i);
  }
  return result;
}

```

## disassembly

```asm
0x1800060f0  mov     r9d, r8d
0x1800060f3  add     r9, rcx
0x1800060f6  mov     r8d, edx
0x1800060f9  add     r8, rcx
0x1800060fc  jmp     short loc_180006116
0x1800060fe  movzx   ecx, byte ptr [r8]
0x180006102  movzx   eax, byte ptr [r8+1]
0x180006107  shl     cx, 8
0x18000610b  or      cx, ax
0x18000610e  mov     [r8], cx
0x180006112  add     r8, 2
0x180006116  cmp     r8, r9
0x180006119  jb      short loc_1800060FE
0x18000611b  retn
```
