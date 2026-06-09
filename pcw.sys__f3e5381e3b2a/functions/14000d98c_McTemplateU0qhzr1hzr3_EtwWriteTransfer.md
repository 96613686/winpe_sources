# McTemplateU0qhzr1hzr3_EtwWriteTransfer

- ea: `0x14000d98c`
- end: `0x14000da37`
- name: `McTemplateU0qhzr1hzr3_EtwWriteTransfer`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000da40`
- `0x14000db70`

## callees

- `0x140001370`
- `0x14000acd0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0qhzr1hzr3_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        unsigned __int16 a4,
        __int64 a5,
        unsigned __int16 a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-31h] BYREF
  int *v9; // [rsp+40h] [rbp-21h]
  __int64 v10; // [rsp+48h] [rbp-19h]
  __int16 *v11; // [rsp+50h] [rbp-11h]
  __int64 v12; // [rsp+58h] [rbp-9h]
  __int64 v13; // [rsp+60h] [rbp-1h]
  int v14; // [rsp+68h] [rbp+7h]
  int v15; // [rsp+6Ch] [rbp+Bh]
  unsigned __int16 *v16; // [rsp+70h] [rbp+Fh]
  __int64 v17; // [rsp+78h] [rbp+17h]
  __int64 v18; // [rsp+80h] [rbp+1Fh]
  int v19; // [rsp+88h] [rbp+27h]
  int v20; // [rsp+8Ch] [rbp+2Bh]
  int v21; // [rsp+C0h] [rbp+5Fh] BYREF
  unsigned __int16 v22; // [rsp+C8h] [rbp+67h] BYREF

  v22 = a4;
  v21 = a3;
  v10 = 4;
  v12 = 2;
  v9 = &v21;
  v11 = (__int16 *)&v22;
  v13 = a5;
  v15 = 0;
  v14 = 2 * a4;
  v16 = &a6;
  v18 = a7;
  v17 = 2;
  v19 = 2 * a6;
  v20 = 0;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, 0, 6u, &v8);
}

```

## disassembly

```asm
0x14000d98c  mov     [rsp-8+arg_18], r9w
0x14000d992  mov     [rsp-8+arg_10], r8d
0x14000d997  push    rbp
0x14000d998  lea     rbp, [rsp-3Fh]
0x14000d99d  sub     rsp, 0A0h
0x14000d9a4  mov     rax, cs:__security_cookie
0x14000d9ab  xor     rax, rsp
0x14000d9ae  mov     [rbp+3Fh+var_10], rax
0x14000d9b2  xor     r8d, r8d
0x14000d9b5  mov     [rbp+3Fh+var_58], 4
0x14000d9bd  lea     rax, [rbp+3Fh+arg_10]
0x14000d9c1  mov     [rbp+3Fh+var_48], 2
0x14000d9c9  mov     [rbp+3Fh+var_60], rax
0x14000d9cd  lea     rax, [rbp+3Fh+arg_18]
0x14000d9d1  mov     [rbp+3Fh+var_50], rax
0x14000d9d5  mov     rax, [rbp+3Fh+arg_20]
0x14000d9d9  mov     [rbp+3Fh+var_40], rax
0x14000d9dd  movzx   eax, r9w
0x14000d9e1  lea     r9d, [r8+6]
0x14000d9e5  add     eax, eax
0x14000d9e7  mov     [rbp+3Fh+var_34], r8d
0x14000d9eb  mov     [rbp+3Fh+var_38], eax
0x14000d9ee  lea     rax, [rbp+3Fh+arg_28]
0x14000d9f2  mov     [rbp+3Fh+var_30], rax
0x14000d9f6  mov     rax, [rbp+3Fh+arg_30]
0x14000d9fa  mov     [rbp+3Fh+var_20], rax
0x14000d9fe  movzx   eax, [rbp+3Fh+arg_28]
0x14000da02  add     eax, eax
0x14000da04  mov     [rbp+3Fh+var_28], 2
0x14000da0c  mov     [rbp+3Fh+var_18], eax
0x14000da0f  lea     rax, [rbp+3Fh+var_70]
0x14000da13  mov     [rsp+0A0h+var_80], rax
0x14000da18  mov     [rbp+3Fh+var_14], r8d
0x14000da1c  call    McGenEventWrite_EtwWriteTransfer
0x14000da21  mov     rcx, [rbp+3Fh+var_10]
0x14000da25  xor     rcx, rsp; StackCookie
0x14000da28  call    __security_check_cookie
0x14000da2d  add     rsp, 0A0h
0x14000da34  pop     rbp
0x14000da35  retn
```
