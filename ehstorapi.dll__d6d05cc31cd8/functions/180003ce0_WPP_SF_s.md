# WPP_SF_s

- ea: `0x180003ce0`
- end: `0x180003d36`
- name: `WPP_SF_s`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026f0`
- `0x1800028f0`
- `0x1800029a0`
- `0x180002a00`
- `0x180002a60`
- `0x180002bf0`
- `0x1800034c0`
- `0x180003520`
- `0x180003ed0`
- `0x180004380`
- `0x180004a60`
- `0x18000521c`
- `0x180005960`
- `0x180007090`
- `0x180007290`
- `0x1800082b0`
- `0x180008af8`

## callees

- `0x180003ce0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180003d2b`
- `ADVAPI32!TraceMessage` at `0x180003d2b`

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
0x180003ce0  sub     rsp, 48h
0x180003ce4  test    r9, r9
0x180003ce7  jz      short loc_180003CFC
0x180003ce9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003ced  inc     rax
0x180003cf0  cmp     byte ptr [r9+rax], 0
0x180003cf5  jnz     short loc_180003CED
0x180003cf7  inc     rax
0x180003cfa  jmp     short loc_180003D01
0x180003cfc  mov     eax, 5
0x180003d01  test    r9, r9
0x180003d04  mov     [rsp+48h+var_18], 0
0x180003d0d  lea     r10, aNull; "NULL"
0x180003d14  mov     [rsp+48h+var_20], rax
0x180003d19  cmovz   r9, r10
0x180003d1d  mov     [rsp+48h+var_28], r9
0x180003d22  movzx   r9d, dx; MessageNumber
0x180003d26  mov     edx, 2Bh ; '+'; MessageFlags
0x180003d2b  call    cs:__imp_TraceMessage
0x180003d31  add     rsp, 48h
0x180003d35  retn
```
