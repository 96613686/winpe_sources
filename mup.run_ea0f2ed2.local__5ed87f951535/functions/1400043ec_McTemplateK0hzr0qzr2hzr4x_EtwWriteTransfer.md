# McTemplateK0hzr0qzr2hzr4x_EtwWriteTransfer

- ea: `0x1400043ec`
- end: `0x1400044b5`
- name: `McTemplateK0hzr0qzr2hzr4x_EtwWriteTransfer`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015e60`

## callees

- `0x140004158`
- `0x1400054a0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0hzr0qzr2hzr4x_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned __int16 a8,
        __int64 a9,
        char a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  __int16 *v12; // [rsp+40h] [rbp-59h]
  __int64 v13; // [rsp+48h] [rbp-51h]
  __int64 v14; // [rsp+50h] [rbp-49h]
  int v15; // [rsp+58h] [rbp-41h]
  int v16; // [rsp+5Ch] [rbp-3Dh]
  int *v17; // [rsp+60h] [rbp-39h]
  __int64 v18; // [rsp+68h] [rbp-31h]
  __int64 v19; // [rsp+70h] [rbp-29h]
  int v20; // [rsp+78h] [rbp-21h]
  int v21; // [rsp+7Ch] [rbp-1Dh]
  unsigned __int16 *v22; // [rsp+80h] [rbp-19h]
  __int64 v23; // [rsp+88h] [rbp-11h]
  __int64 v24; // [rsp+90h] [rbp-9h]
  int v25; // [rsp+98h] [rbp-1h]
  int v26; // [rsp+9Ch] [rbp+3h]
  char *v27; // [rsp+A0h] [rbp+7h]
  __int64 v28; // [rsp+A8h] [rbp+Fh]
  unsigned __int16 v29; // [rsp+E8h] [rbp+4Fh] BYREF

  v29 = a4;
  v13 = 2;
  v16 = 0;
  v12 = (__int16 *)&v29;
  v14 = a5;
  v21 = 0;
  v15 = 2 * a4;
  v17 = &a6;
  v19 = a7;
  v26 = 0;
  v20 = 2 * a6;
  v18 = 4;
  v22 = &a8;
  v24 = a9;
  v23 = 2;
  v25 = 2 * a8;
  v27 = &a10;
  v28 = 8;
  return McGenEventWrite_EtwWriteTransfer(
           a1,
           (const EVENT_DESCRIPTOR *)UncHardening_UnsupportedProperty_IntValue,
           a3,
           8u,
           &v11);
}

```

## disassembly

```asm
0x1400043ec  mov     [rsp-8+arg_18], r9w
0x1400043f2  push    rbp
0x1400043f3  lea     rbp, [rsp-27h]
0x1400043f8  sub     rsp, 0C0h
0x1400043ff  mov     rax, cs:__security_cookie
0x140004406  xor     rax, rsp
0x140004409  mov     [rbp+27h+var_10], rax
0x14000440d  xor     edx, edx
0x14000440f  mov     [rbp+27h+var_78], 2
0x140004417  lea     rax, [rbp+27h+arg_18]
0x14000441b  mov     [rbp+27h+var_64], edx
0x14000441e  mov     [rbp+27h+var_80], rax
0x140004422  mov     rax, [rbp+27h+arg_20]
0x140004426  mov     [rbp+27h+var_70], rax
0x14000442a  movzx   eax, r9w
0x14000442e  lea     r9d, [rdx+8]
0x140004432  add     eax, eax
0x140004434  mov     [rbp+27h+var_44], edx
0x140004437  mov     [rbp+27h+var_68], eax
0x14000443a  lea     rax, [rbp+27h+arg_28]
0x14000443e  mov     [rbp+27h+var_60], rax
0x140004442  mov     rax, [rbp+27h+arg_30]
0x140004446  mov     [rbp+27h+var_50], rax
0x14000444a  mov     eax, [rbp+27h+arg_28]
0x14000444d  add     eax, eax
0x14000444f  mov     [rbp+27h+var_24], edx
0x140004452  mov     [rbp+27h+var_48], eax
0x140004455  lea     rdx, UncHardening_UnsupportedProperty_IntValue
0x14000445c  lea     rax, [rbp+27h+arg_38]
0x140004460  mov     [rbp+27h+var_58], 4
0x140004468  mov     [rbp+27h+var_40], rax
0x14000446c  mov     rax, [rbp+27h+arg_40]
0x140004470  mov     [rbp+27h+var_30], rax
0x140004474  movzx   eax, [rbp+27h+arg_38]
0x140004478  add     eax, eax
0x14000447a  mov     [rbp+27h+var_38], 2
0x140004482  mov     [rbp+27h+var_28], eax
0x140004485  lea     rax, [rbp+27h+arg_48]
0x140004489  mov     [rbp+27h+var_20], rax
0x14000448d  lea     rax, [rbp+27h+var_90]
0x140004491  mov     [rsp+0C0h+var_A0], rax
0x140004496  mov     [rbp+27h+var_18], r9
0x14000449a  call    McGenEventWrite_EtwWriteTransfer
0x14000449f  mov     rcx, [rbp+27h+var_10]
0x1400044a3  xor     rcx, rsp; StackCookie
0x1400044a6  call    __security_check_cookie
0x1400044ab  add     rsp, 0C0h
0x1400044b2  pop     rbp
0x1400044b3  retn
```
