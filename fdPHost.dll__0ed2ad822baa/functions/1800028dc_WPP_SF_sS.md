# WPP_SF_sS

- ea: `0x1800028dc`
- end: `0x18000295e`
- name: `WPP_SF_sS`
- size: `130`
- prototype: `ULONG __fastcall(TRACEHANDLE, __int64, __int64, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001950`

## callees

- `0x1800028dc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180002953`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180002953`

## pseudocode

```c
ULONG __fastcall WPP_SF_sS(TRACEHANDLE a1, __int64 a2, __int64 a3, __int64 a4, const wchar_t *a5)
{
  const wchar_t *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax

  v5 = a5;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  return TraceMessage(a1, 0x2Bu, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids, 0xBu, " ", 2, v5, v7, 0);
}

```

## disassembly

```asm
0x1800028dc  sub     rsp, 58h
0x1800028e0  mov     rdx, [rsp+58h+arg_20]
0x1800028e8  xor     r9d, r9d
0x1800028eb  test    rdx, rdx
0x1800028ee  jz      short loc_180002908
0x1800028f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800028f4  inc     rax
0x1800028f7  cmp     [rdx+rax*2], r9w
0x1800028fc  jnz     short loc_1800028F4
0x1800028fe  lea     rax, ds:2[rax*2]
0x180002906  jmp     short loc_18000290D
0x180002908  mov     eax, 0Ah
0x18000290d  mov     [rsp+58h+var_18], r9
0x180002912  lea     r8, aNull; "NULL"
0x180002919  mov     [rsp+58h+var_20], rax
0x18000291e  test    rdx, rdx
0x180002921  lea     rax, asc_1800055C4; " "
0x180002928  cmovz   rdx, r8
0x18000292c  mov     r8d, 0Bh
0x180002932  mov     [rsp+58h+var_28], rdx
0x180002937  mov     r9d, r8d; MessageNumber
0x18000293a  mov     [rsp+58h+var_30], 2
0x180002943  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids; MessageGuid
0x18000294a  mov     [rsp+58h+var_38], rax
0x18000294f  lea     edx, [r9+20h]; MessageFlags
0x180002953  call    cs:__imp_TraceMessage
0x180002959  add     rsp, 58h
0x18000295d  retn
```
