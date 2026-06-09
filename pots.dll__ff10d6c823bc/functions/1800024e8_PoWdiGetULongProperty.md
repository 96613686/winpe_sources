# PoWdiGetULongProperty

- ea: `0x1800024e8`
- end: `0x180002527`
- name: `PoWdiGetULongProperty`
- size: `63`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f6c`
- `0x1800028c0`
- `0x180002974`
- `0x180003b70`
- `0x180003bc0`
- `0x180003cc0`
- `0x180003f80`
- `0x180004020`
- `0x1800042f0`
- `0x180004390`

## callees

- `0x1800022dc`
- `0x1800024e8`

## pseudocode

```c
_BOOL8 __fastcall PoWdiGetULongProperty(struct _EVENT_RECORD *a1, ULONGLONG a2, BYTE *a3)
{
  __int64 v4; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(v4) = 0;
  return !PoWdiGetProperty(a1, a2, (__int64)a3, a3, 4u, (ULONG *)&v4) && (_DWORD)v4 == 4;
}

```

## disassembly

```asm
0x1800024e8  sub     rsp, 38h
0x1800024ec  lea     rax, [rsp+38h+arg_18]
0x1800024f1  mov     dword ptr [rsp+38h+arg_18], 0
0x1800024f9  mov     [rsp+38h+var_10], rax; __int64
0x1800024fe  mov     r9, r8
0x180002501  mov     [rsp+38h+var_18], 4; int
0x180002509  call    PoWdiGetProperty
0x18000250e  test    eax, eax
0x180002510  jnz     short loc_180002520
0x180002512  cmp     dword ptr [rsp+38h+arg_18], 4
0x180002517  jnz     short loc_180002520
0x180002519  mov     eax, 1
0x18000251e  jmp     short loc_180002522
0x180002520  xor     eax, eax
0x180002522  add     rsp, 38h
0x180002526  retn
```
