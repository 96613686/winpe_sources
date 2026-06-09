# WPP_SF_S

- ea: `0x180019dac`
- end: `0x180019e0d`
- name: `WPP_SF_S`
- size: `97`
- prototype: `__int64(__int64, unsigned __int16, __int64, const wchar_t *, ...)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002d50`
- `0x180003240`
- `0x180019178`
- `0x180019b04`
- `0x180019c70`
- `0x18001a00c`
- `0x18001a38c`

## callees

- `0x180019dac`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180019dfb`
- `ntdll!EtwTraceMessage` at `0x180019dfb`

## pseudocode

```c
__int64 WPP_SF_S(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x180019dac  sub     rsp, 48h
0x180019db0  xor     r11d, r11d
0x180019db3  test    r9, r9
0x180019db6  jz      short loc_180019DD0
0x180019db8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019dbc  inc     rax
0x180019dbf  cmp     [r9+rax*2], r11w
0x180019dc4  jnz     short loc_180019DBC
0x180019dc6  lea     rax, ds:2[rax*2]
0x180019dce  jmp     short loc_180019DD5
0x180019dd0  mov     eax, 0Ah
0x180019dd5  test    r9, r9
0x180019dd8  mov     [rsp+48h+var_18], r11
0x180019ddd  lea     r10, aNull_0; "NULL"
0x180019de4  mov     [rsp+48h+var_20], rax
0x180019de9  cmovz   r9, r10
0x180019ded  mov     [rsp+48h+var_28], r9
0x180019df2  movzx   r9d, dx
0x180019df6  mov     edx, 2Bh ; '+'
0x180019dfb  call    cs:__imp_EtwTraceMessage
0x180019e02  nop     dword ptr [rax+rax+00h]
0x180019e07  add     rsp, 48h
0x180019e0b  retn
```
