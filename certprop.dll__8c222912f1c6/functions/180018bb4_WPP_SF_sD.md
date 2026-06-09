# WPP_SF_sD

- ea: `0x180018bb4`
- end: `0x180018c20`
- name: `WPP_SF_sD`
- size: `108`
- prototype: ``
- caller_count: `79`
- callee_count: `1`
- tags: ``

## callers

- `0x180001570`
- `0x1800019d8`
- `0x180001c98`
- `0x180001e90`
- `0x180002690`
- `0x180002aa0`
- `0x180002df0`
- `0x180002ee0`
- `0x180003070`
- `0x180003230`
- `0x180003370`
- `0x180003510`
- `0x180004900`
- `0x180004fa0`
- `0x180005e10`
- `0x180006010`
- `0x1800061c0`
- `0x1800062e0`
- `0x180006a40`
- `0x1800093c0`
- `0x180009c00`
- `0x18000a050`
- `0x18000aa00`
- `0x18000b09c`
- `0x18000bfe0`
- `0x18000c8f0`
- `0x18000ce50`
- `0x18000d350`
- `0x18000d588`
- `0x18000d7c0`
- `0x18000dd30`
- `0x18000e4ac`
- `0x18000e888`
- `0x18000ec48`
- `0x18000f240`
- `0x18000fe80`
- `0x1800103f0`
- `0x180010d90`
- `0x180011190`
- `0x1800115c0`
- `0x180011c10`
- `0x180012690`
- `0x180012d90`
- `0x180014210`
- `0x1800144d0`
- `0x180014a30`
- `0x180014ca0`
- `0x180014fa8`
- `0x1800151e4`
- `0x1800178a4`

## callees

- `0x180018bb4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180018c15`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180018c15`

## pseudocode

```c
ULONG WPP_SF_sD(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
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
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x180018bb4  sub     rsp, 58h
0x180018bb8  test    r9, r9
0x180018bbb  jz      short loc_180018BD0
0x180018bbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018bc1  inc     rax
0x180018bc4  cmp     byte ptr [r9+rax], 0
0x180018bc9  jnz     short loc_180018BC1
0x180018bcb  inc     rax
0x180018bce  jmp     short loc_180018BD5
0x180018bd0  mov     eax, 5
0x180018bd5  mov     [rsp+58h+var_18], 0
0x180018bde  lea     r10, aNull; "NULL"
0x180018be5  test    r9, r9
0x180018be8  mov     [rsp+58h+var_20], 4
0x180018bf1  cmovz   r9, r10
0x180018bf5  lea     r10, [rsp+58h+arg_20]
0x180018bfd  mov     [rsp+58h+var_28], r10
0x180018c02  mov     [rsp+58h+var_30], rax
0x180018c07  mov     [rsp+58h+var_38], r9
0x180018c0c  movzx   r9d, dx; MessageNumber
0x180018c10  mov     edx, 2Bh ; '+'; MessageFlags
0x180018c15  call    cs:__imp_TraceMessage
0x180018c1b  add     rsp, 58h
0x180018c1f  retn
```
