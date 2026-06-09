# WPP_SF_sd

- ea: `0x180010dcc`
- end: `0x180010e3f`
- name: `WPP_SF_sd`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010e48`
- `0x180010e94`
- `0x180010ee8`

## callees

- `0x180010dcc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180010e34`
- `ntdll!EtwTraceMessage` at `0x180010e34`

## pseudocode

```c
__int64 WPP_SF_sd(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4, ...)
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
  return EtwTraceMessage(a1, 43, WPP_31db98138fb435665e7e2ac66d980c98_Traceguids, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x180010dcc  sub     rsp, 58h
0x180010dd0  test    r9, r9
0x180010dd3  jz      short loc_180010DE8
0x180010dd5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010dd9  inc     rax
0x180010ddc  cmp     byte ptr [r9+rax], 0
0x180010de1  jnz     short loc_180010DD9
0x180010de3  inc     rax
0x180010de6  jmp     short loc_180010DED
0x180010de8  mov     eax, 5
0x180010ded  mov     [rsp+58h+var_18], 0
0x180010df6  lea     r8, aNull; "NULL"
0x180010dfd  test    r9, r9
0x180010e00  mov     [rsp+58h+var_20], 4
0x180010e09  cmovz   r9, r8
0x180010e0d  lea     r8, [rsp+58h+arg_20]
0x180010e15  mov     [rsp+58h+var_28], r8
0x180010e1a  lea     r8, WPP_31db98138fb435665e7e2ac66d980c98_Traceguids
0x180010e21  mov     [rsp+58h+var_30], rax
0x180010e26  mov     [rsp+58h+var_38], r9
0x180010e2b  movzx   r9d, dx
0x180010e2f  mov     edx, 2Bh ; '+'
0x180010e34  call    cs:__imp_EtwTraceMessage
0x180010e3a  add     rsp, 58h
0x180010e3e  retn
```
