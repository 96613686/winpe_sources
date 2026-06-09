# WPP_SF_sdd

- ea: `0x180009a2c`
- end: `0x180009ab2`
- name: `WPP_SF_sdd`
- size: `134`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003cf0`
- `0x180004a40`
- `0x180006b50`
- `0x18000b600`

## callees

- `0x180009a2c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180009aa0`
- `ADVAPI32!TraceMessage` at `0x180009aa0`

## pseudocode

```c
ULONG WPP_SF_sdd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v7; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v7 = va_arg(va1, _QWORD);
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, va1, 4, 0);
}

```

## disassembly

```asm
0x180009a2c  sub     rsp, 68h
0x180009a30  test    r9, r9
0x180009a33  jz      short loc_180009A48
0x180009a35  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a39  inc     rax
0x180009a3c  cmp     byte ptr [r9+rax], 0
0x180009a41  jnz     short loc_180009A39
0x180009a43  inc     rax
0x180009a46  jmp     short loc_180009A4D
0x180009a48  mov     eax, 5
0x180009a4d  mov     [rsp+68h+var_18], 0
0x180009a56  lea     r10, aNull; "NULL"
0x180009a5d  mov     r11d, 4
0x180009a63  test    r9, r9
0x180009a66  mov     [rsp+68h+var_20], r11
0x180009a6b  cmovz   r9, r10
0x180009a6f  lea     r10, [rsp+68h+arg_28]
0x180009a77  mov     [rsp+68h+var_28], r10
0x180009a7c  lea     r10, [rsp+68h+arg_20]
0x180009a84  mov     [rsp+68h+var_30], r11
0x180009a89  mov     [rsp+68h+var_38], r10
0x180009a8e  mov     [rsp+68h+var_40], rax
0x180009a93  mov     [rsp+68h+var_48], r9
0x180009a98  movzx   r9d, dx; MessageNumber
0x180009a9c  lea     edx, [r11+27h]; MessageFlags
0x180009aa0  call    cs:__imp_TraceMessage
0x180009aa7  nop     dword ptr [rax+rax+00h]
0x180009aac  add     rsp, 68h
0x180009ab0  retn
```
