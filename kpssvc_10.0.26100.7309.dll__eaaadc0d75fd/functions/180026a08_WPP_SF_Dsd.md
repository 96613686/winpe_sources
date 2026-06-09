# WPP_SF_Dsd

- ea: `0x180026a08`
- end: `0x180026a98`
- name: `WPP_SF_Dsd`
- size: `144`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, __int64, ...)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e520`
- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x18001f048`
- `0x18001f390`
- `0x18001f5ec`
- `0x18001fd08`
- `0x180020038`
- `0x180020610`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x1800215c0`
- `0x1800216f4`
- `0x1800222f0`
- `0x1800223fc`
- `0x180022708`
- `0x180022a5c`
- `0x180027af8`
- `0x1800285a0`
- `0x1800289f8`
- `0x1800291e4`
- `0x18002a42c`
- `0x18002a5a8`
- `0x18002aae8`
- `0x18002b24c`
- `0x18002b4e0`

## callees

- `0x180026a08`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180026a86`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180026a86`

## pseudocode

```c
ULONG WPP_SF_Dsd(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, const char *a5, ...)
{
  const char *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  int v9; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v9 = a4;
  v5 = a5;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  if ( !a5 )
    v5 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, &v9, 4, v5, v7, va, 4, 0);
}

```

## disassembly

```asm
0x180026a08  mov     [rsp+arg_18], r9d
0x180026a0d  sub     rsp, 68h
0x180026a11  mov     r9, [rsp+68h+arg_20]
0x180026a19  test    r9, r9
0x180026a1c  jz      short loc_180026A31
0x180026a1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026a22  inc     rax
0x180026a25  cmp     byte ptr [r9+rax], 0
0x180026a2a  jnz     short loc_180026A22
0x180026a2c  inc     rax
0x180026a2f  jmp     short loc_180026A36
0x180026a31  mov     eax, 5
0x180026a36  mov     r11d, 4
0x180026a3c  lea     r10, aNull; "NULL"
0x180026a43  test    r9, r9
0x180026a46  cmovz   r9, r10
0x180026a4a  and     [rsp+68h+var_18], 0
0x180026a50  mov     [rsp+68h+var_20], r11
0x180026a55  lea     r10, [rsp+68h+arg_28]
0x180026a5d  mov     [rsp+68h+var_28], r10
0x180026a62  mov     [rsp+68h+var_30], rax
0x180026a67  lea     rax, [rsp+68h+arg_18]
0x180026a6f  mov     [rsp+68h+var_38], r9
0x180026a74  movzx   r9d, dx; MessageNumber
0x180026a78  lea     edx, [r11+27h]; MessageFlags
0x180026a7c  mov     [rsp+68h+var_40], r11
0x180026a81  mov     [rsp+68h+var_48], rax
0x180026a86  call    cs:__imp_TraceMessage
0x180026a8d  nop     dword ptr [rax+rax+00h]
0x180026a92  add     rsp, 68h
0x180026a96  retn
```
