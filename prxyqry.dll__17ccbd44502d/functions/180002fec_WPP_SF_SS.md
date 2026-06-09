# WPP_SF_SS

- ea: `0x180002fec`
- end: `0x180003090`
- name: `WPP_SF_SS`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800021c0`

## callees

- `0x180002fec`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000307d`
- `ntdll!EtwTraceMessage` at `0x18000307d`

## pseudocode

```c
__int64 __fastcall WPP_SF_SS(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4, __int64 a5)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  bool v7; // zf

  v5 = -1;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a5 + 2 * v6) );
  }
  v7 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v7 = a4 == 0;
  }
  if ( v7 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, WPP_f9f245b695a1313fa77432e2631acac1_Traceguids, 36, a4);
}

```

## disassembly

```asm
0x180002fec  push    rbx
0x180002fee  sub     rsp, 50h
0x180002ff2  mov     r8, [rsp+58h+arg_20]
0x180002ffa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002ffe  xor     r11d, r11d
0x180003001  mov     r10d, 0Ah
0x180003007  test    r8, r8
0x18000300a  jz      short loc_180003023
0x18000300c  mov     rdx, rax
0x18000300f  inc     rdx
0x180003012  cmp     [r8+rdx*2], r11w
0x180003017  jnz     short loc_18000300F
0x180003019  lea     rdx, ds:2[rdx*2]
0x180003021  jmp     short loc_180003026
0x180003023  mov     rdx, r10
0x180003026  test    r8, r8
0x180003029  lea     rbx, aNull; "NULL"
0x180003030  cmovz   r8, rbx
0x180003034  test    r9, r9
0x180003037  jz      short loc_18000304E
0x180003039  inc     rax
0x18000303c  cmp     [r9+rax*2], r11w
0x180003041  jnz     short loc_180003039
0x180003043  lea     r10, ds:2[rax*2]
0x18000304b  test    r9, r9
0x18000304e  mov     [rsp+58h+var_18], r11
0x180003053  mov     eax, 24h ; '$'
0x180003058  mov     [rsp+58h+var_20], rdx
0x18000305d  cmovz   r9, rbx
0x180003061  mov     [rsp+58h+var_28], r8
0x180003066  lea     r8, WPP_f9f245b695a1313fa77432e2631acac1_Traceguids
0x18000306d  mov     [rsp+58h+var_30], r10
0x180003072  mov     [rsp+58h+var_38], r9
0x180003077  lea     edx, [rax+7]
0x18000307a  mov     r9d, eax
0x18000307d  call    cs:__imp_EtwTraceMessage
0x180003084  nop     dword ptr [rax+rax+00h]
0x180003089  add     rsp, 50h
0x18000308d  pop     rbx
0x18000308e  retn
```
