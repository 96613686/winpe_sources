# WPP_SF_qdS

- ea: `0x1800104e4`
- end: `0x180010577`
- name: `WPP_SF_qdS`
- size: `147`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f3ec`
- `0x18001a9e0`
- `0x18001aad0`
- `0x18001abac`
- `0x18001afd0`

## callees

- `0x1800104e4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001056c`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001056c`

## pseudocode

```c
ULONG WPP_SF_qdS(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  const wchar_t *v3; // r9
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v7; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v9; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  const wchar_t *v11; // [rsp+98h] [rbp+30h]
  va_list va2; // [rsp+A0h] [rbp+38h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v9 = va_arg(va2, _QWORD);
  v11 = va_arg(va2, const wchar_t *);
  v3 = v11;
  if ( v11 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v11[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !v11 )
    v3 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, va1, 4, v3, v5, 0);
}

```

## disassembly

```asm
0x1800104e4  mov     [rsp+arg_18], r9
0x1800104e9  sub     rsp, 68h
0x1800104ed  mov     r9, [rsp+68h+arg_28]
0x1800104f5  xor     r11d, r11d
0x1800104f8  test    r9, r9
0x1800104fb  jz      short loc_180010515
0x1800104fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010501  inc     rax
0x180010504  cmp     [r9+rax*2], r11w
0x180010509  jnz     short loc_180010501
0x18001050b  lea     rax, ds:2[rax*2]
0x180010513  jmp     short loc_18001051A
0x180010515  mov     eax, 0Ah
0x18001051a  mov     [rsp+68h+var_18], r11
0x18001051f  lea     r10, aNull_0; "NULL"
0x180010526  mov     [rsp+68h+var_20], rax
0x18001052b  test    r9, r9
0x18001052e  lea     rax, [rsp+68h+arg_20]
0x180010536  cmovz   r9, r10
0x18001053a  mov     [rsp+68h+var_28], r9
0x18001053f  mov     [rsp+68h+var_30], 4
0x180010548  mov     [rsp+68h+var_38], rax
0x18001054d  lea     rax, [rsp+68h+arg_18]
0x180010555  movzx   r9d, dx; MessageNumber
0x180010559  mov     edx, 2Bh ; '+'; MessageFlags
0x18001055e  mov     [rsp+68h+var_40], 8
0x180010567  mov     [rsp+68h+var_48], rax
0x18001056c  call    cs:__imp_TraceMessage
0x180010572  add     rsp, 68h
0x180010576  retn
```
