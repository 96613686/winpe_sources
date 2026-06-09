# McTemplateU0pxubr2_EtwWriteTransfer

- ea: `0x1400427e0`
- end: `0x140042872`
- name: `McTemplateU0pxubr2_EtwWriteTransfer`
- size: `146`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140003fac`
- `0x1400049b0`
- `0x140007b30`
- `0x1400099b4`
- `0x1400108c0`
- `0x14001eee0`
- `0x140021e20`
- `0x140022b44`
- `0x1400436c8`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS McTemplateU0pxubr2_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+38h] [rbp-19h] BYREF
  va_list v4; // [rsp+48h] [rbp-9h]
  __int64 v5; // [rsp+50h] [rbp-1h]
  va_list v6; // [rsp+58h] [rbp+7h]
  __int64 v7; // [rsp+60h] [rbp+Fh]
  va_list v8; // [rsp+68h] [rbp+17h]
  __int64 v9; // [rsp+70h] [rbp+1Fh]
  __int64 v10; // [rsp+78h] [rbp+27h]
  int v11; // [rsp+80h] [rbp+2Fh]
  int v12; // [rsp+84h] [rbp+33h]
  __int64 v13; // [rsp+B8h] [rbp+67h] BYREF
  va_list va; // [rsp+B8h] [rbp+67h]
  __int64 v15; // [rsp+C0h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+C0h] [rbp+6Fh]
  __int64 v17; // [rsp+C8h] [rbp+77h] BYREF
  va_list va2; // [rsp+C8h] [rbp+77h]
  __int64 v19; // [rsp+D0h] [rbp+7Fh]
  va_list va3; // [rsp+D8h] [rbp+87h] BYREF

  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v17 = va_arg(va3, _QWORD);
  v19 = va_arg(va3, _QWORD);
  v5 = 8;
  v7 = 8;
  va_copy(v4, va);
  va_copy(v6, va1);
  va_copy(v8, va2);
  v10 = v19;
  v11 = (unsigned __int8)v17;
  v9 = 1;
  v12 = 0;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, 0, 5u, &v3);
}

```

## disassembly

```asm
0x1400427e0  mov     r11, rsp
0x1400427e3  mov     [r11+20h], r9
0x1400427e7  mov     [r11+18h], r8
0x1400427eb  push    rbp
0x1400427ec  lea     rbp, [r11-4Fh]
0x1400427f0  sub     rsp, 90h
0x1400427f7  mov     rax, cs:__security_cookie
0x1400427fe  xor     rax, rsp
0x140042801  mov     [rbp+47h+var_10], rax
0x140042805  xor     r8d, r8d
0x140042808  mov     [rbp+47h+var_48], 8
0x140042810  lea     rax, [rbp+47h+arg_10]
0x140042814  mov     [rbp+47h+var_38], 8
0x14004281c  mov     [rbp+47h+var_50], rax
0x140042820  lea     rax, [rbp+47h+arg_18]
0x140042824  mov     [rbp+47h+var_40], rax
0x140042828  lea     rax, [rbp+47h+arg_20]
0x14004282c  mov     [rbp+47h+var_30], rax
0x140042830  lea     r9d, [r8+5]
0x140042834  mov     rax, [rbp+47h+arg_28]
0x140042838  mov     [rbp+47h+var_20], rax
0x14004283c  movzx   eax, byte ptr [rbp+47h+arg_20]
0x140042840  mov     [rbp+47h+var_18], eax
0x140042843  lea     rax, [rbp+47h+var_60]
0x140042847  mov     [r11-78h], rax
0x14004284b  mov     [rbp+47h+var_28], 1
0x140042853  mov     [rbp+47h+var_14], r8d
0x140042857  call    McGenEventWrite_EtwWriteTransfer
0x14004285c  mov     rcx, [rbp+47h+var_10]
0x140042860  xor     rcx, rsp; StackCookie
0x140042863  call    __security_check_cookie
0x140042868  add     rsp, 90h
0x14004286f  pop     rbp
0x140042870  retn
```
