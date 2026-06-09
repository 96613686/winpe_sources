# WPP_SF_sd

- ea: `0x140002fbc`
- end: `0x140003028`
- name: `WPP_SF_sd`
- size: `108`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, const char *, ...)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140002300`
- `0x140002650`
- `0x1400030c0`
- `0x140003a48`
- `0x140007860`
- `0x140007dd0`
- `0x140008280`
- `0x1400085f0`
- `0x140008b50`
- `0x140009180`
- `0x140009710`

## callees

- `0x140002fbc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x14000301d`
- `ADVAPI32!TraceMessage` at `0x14000301d`

## pseudocode

```c
ULONG WPP_SF_sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
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
0x140002fbc  sub     rsp, 58h
0x140002fc0  test    r9, r9
0x140002fc3  jz      short loc_140002FD8
0x140002fc5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002fc9  inc     rax
0x140002fcc  cmp     byte ptr [r9+rax], 0
0x140002fd1  jnz     short loc_140002FC9
0x140002fd3  inc     rax
0x140002fd6  jmp     short loc_140002FDD
0x140002fd8  mov     eax, 5
0x140002fdd  mov     [rsp+58h+var_18], 0
0x140002fe6  lea     r10, aNull; "NULL"
0x140002fed  test    r9, r9
0x140002ff0  mov     [rsp+58h+var_20], 4
0x140002ff9  cmovz   r9, r10
0x140002ffd  lea     r10, [rsp+58h+arg_20]
0x140003005  mov     [rsp+58h+var_28], r10
0x14000300a  mov     [rsp+58h+var_30], rax
0x14000300f  mov     [rsp+58h+var_38], r9
0x140003014  movzx   r9d, dx; MessageNumber
0x140003018  mov     edx, 2Bh ; '+'; MessageFlags
0x14000301d  call    cs:__imp_TraceMessage
0x140003023  add     rsp, 58h
0x140003027  retn
```
