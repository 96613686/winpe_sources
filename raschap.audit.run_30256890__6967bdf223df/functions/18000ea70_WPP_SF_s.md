# WPP_SF_s

- ea: `0x18000ea70`
- end: `0x18000eac9`
- name: `WPP_SF_s`
- size: `89`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003530`
- `0x180005df0`
- `0x180006c60`
- `0x180007060`
- `0x180007370`
- `0x18000cd68`
- `0x1800106f4`
- `0x180014bd8`
- `0x18001f6a8`

## callees

- `0x18000ea70`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000eabe`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000eabe`

## pseudocode

```c
ULONG __fastcall WPP_SF_s(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x18000ea70  sub     rsp, 48h
0x18000ea74  test    r9, r9
0x18000ea77  jz      short loc_18000EA8F
0x18000ea79  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ea80  inc     rax
0x18000ea83  cmp     byte ptr [r9+rax], 0
0x18000ea88  jnz     short loc_18000EA80
0x18000ea8a  inc     rax
0x18000ea8d  jmp     short loc_18000EA94
0x18000ea8f  mov     eax, 5
0x18000ea94  test    r9, r9
0x18000ea97  mov     [rsp+48h+var_18], 0
0x18000eaa0  lea     r10, aNull; "NULL"
0x18000eaa7  mov     [rsp+48h+var_20], rax
0x18000eaac  cmovz   r9, r10
0x18000eab0  mov     [rsp+48h+var_28], r9
0x18000eab5  movzx   r9d, dx; MessageNumber
0x18000eab9  mov     edx, 2Bh ; '+'; MessageFlags
0x18000eabe  call    cs:__imp_TraceMessage
0x18000eac4  add     rsp, 48h
0x18000eac8  retn
```
