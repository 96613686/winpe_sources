# WPP_SF_S

- ea: `0x180008aa0`
- end: `0x180008afa`
- name: `WPP_SF_S`
- size: `90`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ffc`
- `0x180006410`
- `0x180007330`
- `0x180007bc0`
- `0x180009f04`
- `0x18000a468`
- `0x18000a92c`
- `0x18000b314`

## callees

- `0x180008aa0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008aef`
- `ADVAPI32!TraceMessage` at `0x180008aef`

## pseudocode

```c
ULONG __fastcall WPP_SF_S(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4)
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x180008aa0  sub     rsp, 48h
0x180008aa4  xor     r11d, r11d
0x180008aa7  test    r9, r9
0x180008aaa  jz      short loc_180008AC4
0x180008aac  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008ab0  inc     rax
0x180008ab3  cmp     [r9+rax*2], r11w
0x180008ab8  jnz     short loc_180008AB0
0x180008aba  lea     rax, ds:2[rax*2]
0x180008ac2  jmp     short loc_180008AC9
0x180008ac4  mov     eax, 0Ah
0x180008ac9  test    r9, r9
0x180008acc  mov     [rsp+48h+var_18], r11
0x180008ad1  lea     r10, aNull_0; "NULL"
0x180008ad8  mov     [rsp+48h+var_20], rax
0x180008add  cmovz   r9, r10
0x180008ae1  mov     [rsp+48h+var_28], r9
0x180008ae6  movzx   r9d, dx; MessageNumber
0x180008aea  mov     edx, 2Bh ; '+'; MessageFlags
0x180008aef  call    cs:__imp_TraceMessage
0x180008af5  add     rsp, 48h
0x180008af9  retn
```
