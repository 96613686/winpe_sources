# WritePszTmp

- ea: `0x180002a28`
- end: `0x180002a5c`
- name: `WritePszTmp`
- size: `52`
- prototype: `__int64 __fastcall(int, __int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003340`
- `0x1800039b8`

## callees

- `0x180002a28`
- `0x180004640`

## pseudocode

```c
__int64 __fastcall WritePszTmp(int a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // r8

  v6 = -1;
  do
    ++v6;
  while ( *(_BYTE *)(a2 + v6) );
  return WriteCount(a1, a2, (int)v6 + 1, a3, a4, a5);
}

```

## disassembly

```asm
0x180002a28  sub     rsp, 38h
0x180002a2c  mov     r10, r8
0x180002a2f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002a33  inc     r8
0x180002a36  cmp     byte ptr [rdx+r8], 0
0x180002a3b  jnz     short loc_180002A33
0x180002a3d  mov     rax, [rsp+38h+arg_20]
0x180002a42  inc     r8d
0x180002a45  mov     [rsp+38h+var_10], rax
0x180002a4a  mov     [rsp+38h+var_18], r9
0x180002a4f  mov     r9, r10
0x180002a52  call    WriteCount
0x180002a57  add     rsp, 38h
0x180002a5b  retn
```
