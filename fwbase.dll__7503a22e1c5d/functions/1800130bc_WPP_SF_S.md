# WPP_SF_S

- ea: `0x1800130bc`
- end: `0x180013116`
- name: `WPP_SF_S`
- size: `90`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001720`
- `0x1800024a0`
- `0x180002c10`
- `0x180002e70`
- `0x1800031a0`
- `0x1800043a0`
- `0x1800045f0`
- `0x1800053c0`
- `0x180013a20`
- `0x1800210b0`
- `0x180021270`

## callees

- `0x1800130bc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180013104`
- `ntdll!EtwTraceMessage` at `0x180013104`

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
0x1800130bc  sub     rsp, 48h
0x1800130c0  xor     r11d, r11d
0x1800130c3  test    r9, r9
0x1800130c6  jz      short loc_18001310F
0x1800130c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800130cc  inc     rax
0x1800130cf  cmp     [r9+rax*2], r11w
0x1800130d4  jnz     short loc_1800130CC
0x1800130d6  lea     rax, ds:2[rax*2]
0x1800130de  test    r9, r9
0x1800130e1  mov     [rsp+48h+var_18], r11
0x1800130e6  lea     r10, aNull_0; "NULL"
0x1800130ed  mov     [rsp+48h+var_20], rax
0x1800130f2  cmovz   r9, r10
0x1800130f6  mov     [rsp+48h+var_28], r9
0x1800130fb  movzx   r9d, dx
0x1800130ff  mov     edx, 2Bh ; '+'
0x180013104  call    cs:__imp_EtwTraceMessage
0x18001310a  add     rsp, 48h
0x18001310e  retn
0x18001310f  mov     eax, 0Ah
0x180013114  jmp     short loc_1800130DE
```
