# WPP_SF_sSd

- ea: `0x140004f0c`
- end: `0x140004fc3`
- name: `WPP_SF_sSd`
- size: `183`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, const char *, const wchar_t *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030c0`
- `0x140003a48`
- `0x140009180`
- `0x140009710`

## callees

- `0x140004f0c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x140004fb2`
- `ADVAPI32!TraceMessage` at `0x140004fb2`

## pseudocode

```c
ULONG WPP_SF_sSd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // r11
  __int64 v6; // rax
  __int64 v7; // r10
  __int64 v8; // r10
  __int64 v9; // rax
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = a5;
  v6 = -1;
  if ( a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a5[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v9 = v6 + 1;
  }
  else
  {
    v9 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v9, v5, v8, va, 4, 0);
}

```

## disassembly

```asm
0x140004f0c  mov     [rsp+arg_0], rbx
0x140004f11  push    rdi
0x140004f12  sub     rsp, 60h
0x140004f16  mov     r11, [rsp+68h+arg_20]
0x140004f1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004f22  xor     edi, edi
0x140004f24  test    r11, r11
0x140004f27  jz      short loc_140004F40
0x140004f29  mov     r10, rax
0x140004f2c  inc     r10
0x140004f2f  cmp     [r11+r10*2], di
0x140004f34  jnz     short loc_140004F2C
0x140004f36  lea     r10, ds:2[r10*2]
0x140004f3e  jmp     short loc_140004F46
0x140004f40  mov     r10d, 0Ah
0x140004f46  test    r11, r11
0x140004f49  lea     rbx, aNull_1; "NULL"
0x140004f50  cmovz   r11, rbx
0x140004f54  test    r9, r9
0x140004f57  jz      short loc_140004F67
0x140004f59  inc     rax
0x140004f5c  cmp     [r9+rax], dil
0x140004f60  jnz     short loc_140004F59
0x140004f62  inc     rax
0x140004f65  jmp     short loc_140004F6C
0x140004f67  mov     eax, 5
0x140004f6c  mov     [rsp+68h+var_18], rdi
0x140004f71  lea     rbx, aNull; "NULL"
0x140004f78  mov     [rsp+68h+var_20], 4
0x140004f81  test    r9, r9
0x140004f84  cmovz   r9, rbx
0x140004f88  lea     rbx, [rsp+68h+arg_28]
0x140004f90  mov     [rsp+68h+var_28], rbx
0x140004f95  mov     [rsp+68h+var_30], r10
0x140004f9a  mov     [rsp+68h+var_38], r11
0x140004f9f  mov     [rsp+68h+var_40], rax
0x140004fa4  mov     [rsp+68h+var_48], r9
0x140004fa9  movzx   r9d, dx; MessageNumber
0x140004fad  mov     edx, 2Bh ; '+'; MessageFlags
0x140004fb2  call    cs:__imp_TraceMessage
0x140004fb8  mov     rbx, [rsp+68h+arg_0]
0x140004fbd  add     rsp, 60h
0x140004fc1  pop     rdi
0x140004fc2  retn
```
