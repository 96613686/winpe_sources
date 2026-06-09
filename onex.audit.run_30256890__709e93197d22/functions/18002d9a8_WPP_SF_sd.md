# WPP_SF_sd

- ea: `0x18002d9a8`
- end: `0x18002da1b`
- name: `WPP_SF_sd`
- size: `115`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003c80`
- `0x180004780`
- `0x180004b40`
- `0x180005640`
- `0x18000e230`
- `0x18000f8c0`
- `0x180012cc0`
- `0x180012f90`
- `0x180013a30`
- `0x180013e50`
- `0x180014e50`
- `0x1800170c0`
- `0x180018700`

## callees

- `0x18002d9a8`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002da10`
- `ntdll!EtwTraceMessage` at `0x18002da10`

## pseudocode

```c
__int64 __fastcall WPP_SF_sd(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
  }
  if ( !a4 )
    a4 = "NULL";
  return EtwTraceMessage(a1, 43, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, a2, a4);
}

```

## disassembly

```asm
0x18002d9a8  sub     rsp, 58h
0x18002d9ac  test    r9, r9
0x18002d9af  jz      short loc_18002D9C4
0x18002d9b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d9b5  inc     rax
0x18002d9b8  cmp     byte ptr [r9+rax], 0
0x18002d9bd  jnz     short loc_18002D9B5
0x18002d9bf  inc     rax
0x18002d9c2  jmp     short loc_18002D9C9
0x18002d9c4  mov     eax, 5
0x18002d9c9  mov     [rsp+58h+var_18], 0
0x18002d9d2  lea     r8, aNull; "NULL"
0x18002d9d9  test    r9, r9
0x18002d9dc  mov     [rsp+58h+var_20], 4
0x18002d9e5  cmovz   r9, r8
0x18002d9e9  lea     r8, [rsp+58h+arg_20]
0x18002d9f1  mov     [rsp+58h+var_28], r8
0x18002d9f6  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18002d9fd  mov     [rsp+58h+var_30], rax
0x18002da02  mov     [rsp+58h+var_38], r9
0x18002da07  movzx   r9d, dx
0x18002da0b  mov     edx, 2Bh ; '+'
0x18002da10  call    cs:__imp_EtwTraceMessage
0x18002da16  add     rsp, 58h
0x18002da1a  retn
```
