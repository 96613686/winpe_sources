# WPP_SF_PSD

- ea: `0x18000a670`
- end: `0x18000a715`
- name: `WPP_SF_PSD`
- size: `165`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba30`
- `0x18000d100`
- `0x180010c90`
- `0x180011310`
- `0x180011950`
- `0x180017990`

## callees

- `0x18000a670`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a703`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a703`

## pseudocode

```c
ULONG WPP_SF_PSD(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  const wchar_t *v3; // r8
  __int64 v4; // rax
  __int64 v6; // rax
  __int64 v8; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  const wchar_t *v10; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v10 = va_arg(va1, const wchar_t *);
  v3 = v10;
  if ( v10 )
  {
    v4 = -1;
    while ( v10[++v4] != 0 )
      ;
    v6 = 2 * v4 + 2;
  }
  else
  {
    v6 = 10;
  }
  if ( !v10 )
    v3 = L"NULL";
  return TraceMessage(a1, 0x2Bu, &WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids, a2, va, 8, v3, v6, va1, 4, 0);
}

```

## disassembly

```asm
0x18000a670  mov     [rsp+arg_18], r9
0x18000a675  sub     rsp, 68h
0x18000a679  mov     r8, [rsp+68h+arg_20]
0x18000a681  test    r8, r8
0x18000a684  jz      loc_18000A70E
0x18000a68a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a691  cmp     word ptr [r8+rax*2+2], 0
0x18000a698  lea     rax, [rax+1]
0x18000a69c  jnz     short loc_18000A691
0x18000a69e  lea     rax, ds:2[rax*2]
0x18000a6a6  mov     [rsp+68h+var_18], 0
0x18000a6af  lea     r9, aNull_0; "NULL"
0x18000a6b6  mov     [rsp+68h+var_20], 4
0x18000a6bf  test    r8, r8
0x18000a6c2  cmovz   r8, r9
0x18000a6c6  lea     r9, [rsp+68h+arg_28]
0x18000a6ce  mov     [rsp+68h+var_28], r9
0x18000a6d3  mov     [rsp+68h+var_30], rax
0x18000a6d8  lea     rax, [rsp+68h+arg_18]
0x18000a6e0  mov     [rsp+68h+var_38], r8
0x18000a6e5  lea     r8, WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids; MessageGuid
0x18000a6ec  movzx   r9d, dx; MessageNumber
0x18000a6f0  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a6f5  mov     [rsp+68h+var_40], 8
0x18000a6fe  mov     [rsp+68h+var_48], rax
0x18000a703  call    cs:__imp_TraceMessage
0x18000a709  add     rsp, 68h
0x18000a70d  retn
0x18000a70e  mov     eax, 0Ah
0x18000a713  jmp     short loc_18000A6A6
```
