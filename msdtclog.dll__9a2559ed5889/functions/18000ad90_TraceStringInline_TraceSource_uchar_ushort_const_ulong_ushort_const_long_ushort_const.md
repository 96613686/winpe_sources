# TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)

- ea: `0x18000ad90`
- end: `0x18000adf0`
- name: `?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ`
- size: `96`
- prototype: `void(int, unsigned __int8, __int64, int, __int64, int, wchar_t *, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180001210`
- `0x18000bc44`
- `0x18000e090`
- `0x1800116e4`
- `0x1800119e8`
- `0x180014144`
- `0x1800141a8`

## callees

- `0x18000ad90`
- `0x180010fd0`

## pseudocode

```c
void TraceStringInline(int a1, unsigned __int8 a2, __int64 a3, int a4, __int64 a5, int a6, wchar_t *a7, ...)
{
  va_list va; // [rsp+98h] [rbp+40h] BYREF

  va_start(va, a7);
  if ( LODWORD(qword_18001F010[3 * a1]) >= a2 )
    _TraceString(a1, a2, a3, a4, a5, a6, a7, va);
}

```

## disassembly

```asm
0x18000ad90  sub     rsp, 58h
0x18000ad94  movsxd  rax, ecx
0x18000ad97  lea     r11, qword_18001F010
0x18000ad9e  lea     r10, [rax+rax*2]
0x18000ada2  movzx   eax, dl
0x18000ada5  cmp     [r11+r10*8], eax
0x18000ada9  jb      short loc_18000ADEB
0x18000adab  lea     rax, [rsp+58h+arg_38]
0x18000adb3  mov     [rsp+58h+var_18], 0
0x18000adbc  mov     [rsp+58h+var_20], rax
0x18000adc1  mov     rax, [rsp+58h+arg_30]
0x18000adc9  mov     [rsp+58h+var_28], rax
0x18000adce  mov     eax, [rsp+58h+arg_28]
0x18000add5  mov     [rsp+58h+var_30], eax
0x18000add9  mov     rax, [rsp+58h+arg_20]
0x18000ade1  mov     [rsp+58h+var_38], rax
0x18000ade6  call    ?_TraceString@@YAXW4TraceSource@@EPEBGK1J1PEAD@Z; _TraceString(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,char *)
0x18000adeb  add     rsp, 58h
0x18000adef  retn
```
