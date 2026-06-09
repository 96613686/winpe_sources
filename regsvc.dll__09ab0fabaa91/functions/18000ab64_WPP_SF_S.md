# WPP_SF_S

- ea: `0x18000ab64`
- end: `0x18000abbe`
- name: `WPP_SF_S`
- size: `90`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004f00`
- `0x18000a2a4`
- `0x18000e1a8`
- `0x180011b08`
- `0x180011b88`
- `0x180011d10`
- `0x18001335c`
- `0x1800136b0`

## callees

- `0x18000ab64`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000abb3`
- `ntdll!EtwTraceMessage` at `0x18000abb3`

## pseudocode

```c
__int64 __fastcall WPP_SF_S(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x18000ab64  sub     rsp, 48h
0x18000ab68  xor     r11d, r11d
0x18000ab6b  test    r9, r9
0x18000ab6e  jz      short loc_18000AB88
0x18000ab70  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ab74  inc     rax
0x18000ab77  cmp     [r9+rax*2], r11w
0x18000ab7c  jnz     short loc_18000AB74
0x18000ab7e  lea     rax, ds:2[rax*2]
0x18000ab86  jmp     short loc_18000AB8D
0x18000ab88  mov     eax, 0Ah
0x18000ab8d  test    r9, r9
0x18000ab90  mov     [rsp+48h+var_18], r11
0x18000ab95  lea     r10, aNull_0; "NULL"
0x18000ab9c  mov     [rsp+48h+var_20], rax
0x18000aba1  cmovz   r9, r10
0x18000aba5  mov     [rsp+48h+var_28], r9
0x18000abaa  movzx   r9d, dx
0x18000abae  mov     edx, 2Bh ; '+'
0x18000abb3  call    cs:__imp_EtwTraceMessage
0x18000abb9  add     rsp, 48h
0x18000abbd  retn
```
