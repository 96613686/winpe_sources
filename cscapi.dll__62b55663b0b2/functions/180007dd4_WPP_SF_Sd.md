# WPP_SF_Sd

- ea: `0x180007dd4`
- end: `0x180007e4b`
- name: `WPP_SF_Sd`
- size: `119`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004000`
- `0x1800045b0`
- `0x180004cf0`
- `0x1800052f0`
- `0x1800057f0`
- `0x180007ff4`
- `0x180008118`

## callees

- `0x180007dd4`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180007e40`
- `ntdll!EtwTraceMessage` at `0x180007e40`

## pseudocode

```c
__int64 WPP_SF_Sd(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4, ...)
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
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x180007dd4  sub     rsp, 58h
0x180007dd8  xor     r10d, r10d
0x180007ddb  test    r9, r9
0x180007dde  jz      short loc_180007DF8
0x180007de0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007de4  inc     rax
0x180007de7  cmp     [r9+rax*2], r10w
0x180007dec  jnz     short loc_180007DE4
0x180007dee  lea     rax, ds:2[rax*2]
0x180007df6  jmp     short loc_180007DFD
0x180007df8  mov     eax, 0Ah
0x180007dfd  mov     [rsp+58h+var_18], r10
0x180007e02  lea     r8, aNull_0; "NULL"
0x180007e09  test    r9, r9
0x180007e0c  mov     [rsp+58h+var_20], 4
0x180007e15  cmovz   r9, r8
0x180007e19  lea     r8, [rsp+58h+arg_20]
0x180007e21  mov     [rsp+58h+var_28], r8
0x180007e26  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x180007e2d  mov     [rsp+58h+var_30], rax
0x180007e32  mov     [rsp+58h+var_38], r9
0x180007e37  movzx   r9d, dx
0x180007e3b  mov     edx, 2Bh ; '+'
0x180007e40  call    cs:__imp_EtwTraceMessage
0x180007e46  add     rsp, 58h
0x180007e4a  retn
```
