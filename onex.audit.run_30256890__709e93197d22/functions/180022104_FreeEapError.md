# FreeEapError

- ea: `0x180022104`
- end: `0x180022162`
- name: `FreeEapError`
- size: `94`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001510`
- `0x18000ade0`
- `0x18000ecd0`
- `0x180017f70`
- `0x180018d60`
- `0x18001be88`
- `0x180026194`

## callees

- `0x180022104`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x180022123`
- `MobileNetworking!FreeMemory` at `0x18002213f`
- `MobileNetworking!FreeMemory` at `0x180022157`
- `MobileNetworking!FreeMemory` at `0x180022123`
- `MobileNetworking!FreeMemory` at `0x18002213f`
- `MobileNetworking!FreeMemory` at `0x180022157`

## pseudocode

```c
__int64 __fastcall FreeEapError(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v2 = a1;
    FreeMemory(a1 + 72, "FreeEapError", 1097);
    FreeMemory(v2 + 80, "FreeEapError", 1098);
    return FreeMemory(&v2, "FreeEapError", 1099);
  }
  return result;
}

```

## disassembly

```asm
0x180022104  test    rcx, rcx
0x180022107  jz      short locret_180022161
0x180022109  mov     [rsp+arg_0], rcx
0x18002210e  sub     rsp, 28h
0x180022112  add     rcx, 48h ; 'H'
0x180022116  lea     rdx, aFreeeaperror; "FreeEapError"
0x18002211d  mov     r8d, 449h
0x180022123  call    cs:__imp_FreeMemory
0x180022129  mov     rcx, [rsp+28h+arg_0]
0x18002212e  lea     rdx, aFreeeaperror; "FreeEapError"
0x180022135  add     rcx, 50h ; 'P'
0x180022139  mov     r8d, 44Ah
0x18002213f  call    cs:__imp_FreeMemory
0x180022145  mov     r8d, 44Bh
0x18002214b  lea     rdx, aFreeeaperror; "FreeEapError"
0x180022152  lea     rcx, [rsp+28h+arg_0]
0x180022157  call    cs:__imp_FreeMemory
0x18002215d  add     rsp, 28h
0x180022161  retn
```
