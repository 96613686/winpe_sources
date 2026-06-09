# WPP_SF_Sd

- ea: `0x180008bac`
- end: `0x180008c23`
- name: `WPP_SF_Sd`
- size: `119`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005850`
- `0x180006410`
- `0x180007330`
- `0x180007bc0`

## callees

- `0x180008bac`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008c18`
- `ADVAPI32!TraceMessage` at `0x180008c18`

## pseudocode

```c
ULONG WPP_SF_Sd(TRACEHANDLE a1, USHORT a2, __int64 a3, const wchar_t *a4, ...)
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
  return TraceMessage(a1, 0x2Bu, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x180008bac  sub     rsp, 58h
0x180008bb0  xor     r10d, r10d
0x180008bb3  test    r9, r9
0x180008bb6  jz      short loc_180008BD0
0x180008bb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008bbc  inc     rax
0x180008bbf  cmp     [r9+rax*2], r10w
0x180008bc4  jnz     short loc_180008BBC
0x180008bc6  lea     rax, ds:2[rax*2]
0x180008bce  jmp     short loc_180008BD5
0x180008bd0  mov     eax, 0Ah
0x180008bd5  mov     [rsp+58h+var_18], r10
0x180008bda  lea     r8, aNull_0; "NULL"
0x180008be1  test    r9, r9
0x180008be4  mov     [rsp+58h+var_20], 4
0x180008bed  cmovz   r9, r8
0x180008bf1  lea     r8, [rsp+58h+arg_20]
0x180008bf9  mov     [rsp+58h+var_28], r8
0x180008bfe  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids; MessageGuid
0x180008c05  mov     [rsp+58h+var_30], rax
0x180008c0a  mov     [rsp+58h+var_38], r9
0x180008c0f  movzx   r9d, dx; MessageNumber
0x180008c13  mov     edx, 2Bh ; '+'; MessageFlags
0x180008c18  call    cs:__imp_TraceMessage
0x180008c1e  add     rsp, 58h
0x180008c22  retn
```
