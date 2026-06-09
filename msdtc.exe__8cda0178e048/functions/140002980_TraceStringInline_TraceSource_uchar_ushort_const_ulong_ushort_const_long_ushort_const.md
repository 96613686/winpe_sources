# TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)

- ea: `0x140002980`
- end: `0x1400029e0`
- name: `?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ`
- size: `96`
- prototype: `void(int, unsigned __int8, __int64, int, __int64, int, wchar_t *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011e0`
- `0x1400029f0`
- `0x140005dd4`
- `0x1400060d8`

## callees

- `0x140002980`
- `0x1400056c0`

## pseudocode

```c
void TraceStringInline(int a1, unsigned __int8 a2, __int64 a3, int a4, __int64 a5, int a6, wchar_t *a7, ...)
{
  va_list va; // [rsp+98h] [rbp+40h] BYREF

  va_start(va, a7);
  if ( LODWORD(qword_14000E010[3 * a1]) >= a2 )
    _TraceString(a1, a2, a3, a4, a5, a6, a7, va);
}

```

## disassembly

```asm
0x140002980  sub     rsp, 58h
0x140002984  movsxd  rax, ecx
0x140002987  lea     r11, qword_14000E010
0x14000298e  lea     r10, [rax+rax*2]
0x140002992  movzx   eax, dl
0x140002995  cmp     [r11+r10*8], eax
0x140002999  jb      short loc_1400029DB
0x14000299b  lea     rax, [rsp+58h+arg_38]
0x1400029a3  mov     [rsp+58h+var_18], 0
0x1400029ac  mov     [rsp+58h+var_20], rax
0x1400029b1  mov     rax, [rsp+58h+arg_30]
0x1400029b9  mov     [rsp+58h+var_28], rax
0x1400029be  mov     eax, [rsp+58h+arg_28]
0x1400029c5  mov     [rsp+58h+var_30], eax
0x1400029c9  mov     rax, [rsp+58h+arg_20]
0x1400029d1  mov     [rsp+58h+var_38], rax
0x1400029d6  call    ?_TraceString@@YAXW4TraceSource@@EPEBGK1J1PEAD@Z; _TraceString(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,char *)
0x1400029db  add     rsp, 58h
0x1400029df  retn
```
