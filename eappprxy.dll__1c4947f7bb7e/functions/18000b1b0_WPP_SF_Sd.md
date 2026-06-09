# WPP_SF_Sd

- ea: `0x18000b1b0`
- end: `0x18000b227`
- name: `WPP_SF_Sd`
- size: `119`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005ab0`
- `0x18000b6ac`
- `0x18000b8bc`
- `0x18000bd30`
- `0x18000ca10`

## callees

- `0x18000b1b0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b215`
- `ntdll!EtwTraceMessage` at `0x18000b215`

## pseudocode

```c
__int64 __fastcall WPP_SF_Sd(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
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
0x18000b1b0  sub     rsp, 58h
0x18000b1b4  xor     r11d, r11d
0x18000b1b7  test    r9, r9
0x18000b1ba  jz      short loc_18000B1D4
0x18000b1bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b1c0  inc     rax
0x18000b1c3  cmp     [r9+rax*2], r11w
0x18000b1c8  jnz     short loc_18000B1C0
0x18000b1ca  lea     rax, ds:2[rax*2]
0x18000b1d2  jmp     short loc_18000B1D9
0x18000b1d4  mov     eax, 0Ah
0x18000b1d9  mov     [rsp+58h+var_18], r11
0x18000b1de  lea     r10, aNull; "NULL"
0x18000b1e5  test    r9, r9
0x18000b1e8  mov     [rsp+58h+var_20], 4
0x18000b1f1  cmovz   r9, r10
0x18000b1f5  lea     r10, [rsp+58h+arg_20]
0x18000b1fd  mov     [rsp+58h+var_28], r10
0x18000b202  mov     [rsp+58h+var_30], rax
0x18000b207  mov     [rsp+58h+var_38], r9
0x18000b20c  movzx   r9d, dx
0x18000b210  mov     edx, 2Bh ; '+'
0x18000b215  call    cs:__imp_EtwTraceMessage
0x18000b21c  nop     dword ptr [rax+rax+00h]
0x18000b221  add     rsp, 58h
0x18000b225  retn
```
