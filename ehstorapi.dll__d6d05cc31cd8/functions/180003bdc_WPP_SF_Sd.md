# WPP_SF_Sd

- ea: `0x180003bdc`
- end: `0x180003c4c`
- name: `WPP_SF_Sd`
- size: `112`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d68`
- `0x180004a60`
- `0x18000521c`
- `0x180005d50`
- `0x180006af0`
- `0x180007430`
- `0x180007f00`

## callees

- `0x180003bdc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180003c41`
- `ADVAPI32!TraceMessage` at `0x180003c41`

## pseudocode

```c
ULONG WPP_SF_Sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x180003bdc  sub     rsp, 58h
0x180003be0  xor     r11d, r11d
0x180003be3  test    r9, r9
0x180003be6  jz      short loc_180003C00
0x180003be8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003bec  inc     rax
0x180003bef  cmp     [r9+rax*2], r11w
0x180003bf4  jnz     short loc_180003BEC
0x180003bf6  lea     rax, ds:2[rax*2]
0x180003bfe  jmp     short loc_180003C05
0x180003c00  mov     eax, 0Ah
0x180003c05  mov     [rsp+58h+var_18], r11
0x180003c0a  lea     r10, aNull_0; "NULL"
0x180003c11  test    r9, r9
0x180003c14  mov     [rsp+58h+var_20], 4
0x180003c1d  cmovz   r9, r10
0x180003c21  lea     r10, [rsp+58h+arg_20]
0x180003c29  mov     [rsp+58h+var_28], r10
0x180003c2e  mov     [rsp+58h+var_30], rax
0x180003c33  mov     [rsp+58h+var_38], r9
0x180003c38  movzx   r9d, dx; MessageNumber
0x180003c3c  mov     edx, 2Bh ; '+'; MessageFlags
0x180003c41  call    cs:__imp_TraceMessage
0x180003c47  add     rsp, 58h
0x180003c4b  retn
```
