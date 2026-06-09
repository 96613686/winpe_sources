# RasTapiTrace

- ea: `0x18000d92c`
- end: `0x18000d984`
- name: `RasTapiTrace`
- size: `88`
- prototype: `__int64 __fastcall(LPCSTR lpszFormat)`
- caller_count: `65`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b6c`
- `0x180001cf4`
- `0x180001e5c`
- `0x180001fdc`
- `0x18000212c`
- `0x1800022a0`
- `0x1800023d4`
- `0x1800024bc`
- `0x1800025d8`
- `0x18000272c`
- `0x180002b20`
- `0x180002e20`
- `0x1800030f0`
- `0x1800033d0`
- `0x180003504`
- `0x18000c5e0`
- `0x18000c8bc`
- `0x18000c918`
- `0x18000c974`
- `0x18000caac`
- `0x18000cb80`
- `0x18000db80`
- `0x18000dc2c`
- `0x18000de88`
- `0x18000f108`
- `0x18000f53c`
- `0x18000f670`
- `0x18000f7a0`
- `0x18000f810`
- `0x18000fee0`
- `0x18000ff60`
- `0x1800101d0`
- `0x1800102b0`
- `0x180010330`
- `0x1800107a8`
- `0x1800108a0`
- `0x180010c04`
- `0x180010d70`
- `0x180011698`
- `0x1800118f0`
- `0x180012a40`
- `0x180012b00`
- `0x180012f64`
- `0x180013040`
- `0x1800131f0`
- `0x180013770`
- `0x1800138b0`
- `0x180013b60`
- `0x180013ccc`
- `0x180014240`

## callees

- `0x1800292b0`

## import_xrefs

- `rtutils!TraceVprintfExA` at `0x18000d96c`
- `rtutils!TraceVprintfExA` at `0x18000d96c`

## pseudocode

```c
DWORD RasTapiTrace(LPCSTR lpszFormat, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, lpszFormat);
  return TraceVprintfExA(dwTraceId, 0x1000Eu, lpszFormat, va);
}

```

## disassembly

```asm
0x18000d92c  mov     r11, rsp
0x18000d92f  mov     [r11+8], rcx
0x18000d933  mov     [r11+10h], rdx
0x18000d937  mov     [r11+18h], r8
0x18000d93b  mov     [r11+20h], r9
0x18000d93f  sub     rsp, 38h
0x18000d943  mov     rax, cs:__security_cookie
0x18000d94a  xor     rax, rsp
0x18000d94d  mov     [rsp+38h+var_10], rax
0x18000d952  mov     r8, rcx; lpszFormat
0x18000d955  mov     qword ptr [r11-18h], 0
0x18000d95d  mov     ecx, cs:dwTraceId; dwTraceID
0x18000d963  lea     r9, [r11+10h]; arglist
0x18000d967  mov     edx, 1000Eh; dwFlags
0x18000d96c  call    cs:__imp_TraceVprintfExA
0x18000d972  mov     rcx, [rsp+38h+var_10]
0x18000d977  xor     rcx, rsp; StackCookie
0x18000d97a  call    __security_check_cookie
0x18000d97f  add     rsp, 38h
0x18000d983  retn
```
