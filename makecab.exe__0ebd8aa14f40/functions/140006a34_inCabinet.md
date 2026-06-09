# inCabinet

- ea: `0x140006a34`
- end: `0x140006a66`
- name: `inCabinet`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000488c`
- `0x140004f94`
- `0x1400072bc`

## callees

- `0x140006a34`
- `0x14000dfd8`

## import_xrefs

- `msvcrt!atoi` at `0x140006a5f`

## pseudocode

```c
int __fastcall inCabinet(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  const char *v3; // rcx

  v2 = VarFind(*(_QWORD *)(a1 + 16), (__int64)"Cabinet", a2);
  v3 = "On";
  if ( v2 )
    v3 = *(const char **)(v2 + 8);
  return atoi(v3);
}

```

## disassembly

```asm
0x140006a34  sub     rsp, 28h
0x140006a38  mov     rcx, [rcx+10h]
0x140006a3c  mov     r8, rdx
0x140006a3f  lea     rdx, aCabinet; "Cabinet"
0x140006a46  call    VarFind
0x140006a4b  lea     rcx, aOn; "On"
0x140006a52  test    rax, rax
0x140006a55  jz      short loc_140006A5B
0x140006a57  mov     rcx, [rax+8]
0x140006a5b  add     rsp, 28h
0x140006a5f  jmp     cs:__imp_atoi
```
