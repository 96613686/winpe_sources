# McTemplateK0dhzr1hzr3_EtwWriteTransfer

- ea: `0x140004160`
- end: `0x140004205`
- name: `McTemplateK0dhzr1hzr3_EtwWriteTransfer`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d988`
- `0x14002e374`

## callees

- `0x140004100`
- `0x14000ba20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dhzr1hzr3_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        unsigned __int16 a5,
        __int64 a6,
        unsigned __int16 a7,
        __int64 a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-39h] BYREF
  int *v10; // [rsp+40h] [rbp-29h]
  __int64 v11; // [rsp+48h] [rbp-21h]
  unsigned __int16 *v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  __int64 v14; // [rsp+60h] [rbp-9h]
  int v15; // [rsp+68h] [rbp-1h]
  int v16; // [rsp+6Ch] [rbp+3h]
  unsigned __int16 *v17; // [rsp+70h] [rbp+7h]
  __int64 v18; // [rsp+78h] [rbp+Fh]
  __int64 v19; // [rsp+80h] [rbp+17h]
  int v20; // [rsp+88h] [rbp+1Fh]
  int v21; // [rsp+8Ch] [rbp+23h]
  int v22; // [rsp+C8h] [rbp+5Fh] BYREF

  v22 = a4;
  v11 = 4;
  v13 = 2;
  v10 = &v22;
  v12 = &a5;
  v14 = a6;
  v16 = 0;
  v15 = 2 * a5;
  v17 = &a7;
  v19 = a8;
  v18 = 2;
  v20 = 2 * a7;
  v21 = 0;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, 0, 6u, &v9);
}

```

## disassembly

```asm
0x140004160  mov     [rsp-8+arg_18], r9d
0x140004165  push    rbp
0x140004166  lea     rbp, [rsp-37h]
0x14000416b  sub     rsp, 0A0h
0x140004172  mov     rax, cs:__security_cookie
0x140004179  xor     rax, rsp
0x14000417c  mov     [rbp+37h+var_10], rax
0x140004180  xor     r8d, r8d
0x140004183  mov     [rbp+37h+var_58], 4
0x14000418b  lea     rax, [rbp+37h+arg_18]
0x14000418f  mov     [rbp+37h+var_48], 2
0x140004197  mov     [rbp+37h+var_60], rax
0x14000419b  lea     rax, [rbp+37h+arg_20]
0x14000419f  mov     [rbp+37h+var_50], rax
0x1400041a3  mov     rax, [rbp+37h+arg_28]
0x1400041a7  lea     r9d, [r8+6]
0x1400041ab  mov     [rbp+37h+var_40], rax
0x1400041af  movzx   eax, [rbp+37h+arg_20]
0x1400041b3  add     eax, eax
0x1400041b5  mov     [rbp+37h+var_34], r8d
0x1400041b9  mov     [rbp+37h+var_38], eax
0x1400041bc  lea     rax, [rbp+37h+arg_30]
0x1400041c0  mov     [rbp+37h+var_30], rax
0x1400041c4  mov     rax, [rbp+37h+arg_38]
0x1400041c8  mov     [rbp+37h+var_20], rax
0x1400041cc  movzx   eax, [rbp+37h+arg_30]
0x1400041d0  add     eax, eax
0x1400041d2  mov     [rbp+37h+var_28], 2
0x1400041da  mov     [rbp+37h+var_18], eax
0x1400041dd  lea     rax, [rbp+37h+var_70]
0x1400041e1  mov     [rsp+0A0h+var_80], rax
0x1400041e6  mov     [rbp+37h+var_14], r8d
0x1400041ea  call    McGenEventWrite_EtwWriteTransfer
0x1400041ef  mov     rcx, [rbp+37h+var_10]
0x1400041f3  xor     rcx, rsp; StackCookie
0x1400041f6  call    __security_check_cookie
0x1400041fb  add     rsp, 0A0h
0x140004202  pop     rbp
0x140004203  retn
```
